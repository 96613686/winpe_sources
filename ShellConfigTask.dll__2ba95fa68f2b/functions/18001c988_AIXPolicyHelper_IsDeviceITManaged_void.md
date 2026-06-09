# AIXPolicyHelper::IsDeviceITManaged(void)

- ea: `0x18001c988`
- end: `0x18001cb6d`
- name: `?IsDeviceITManaged@AIXPolicyHelper@@YA_NXZ`
- size: `485`
- prototype: `bool __fastcall(AIXPolicyHelper *__hidden this)`
- caller_count: `6`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001438c`
- `0x18001bf24`
- `0x18001e518`
- `0x180028844`
- `0x18002a514`
- `0x18002b864`

## callees

- `0x180002590`
- `0x180006cb8`
- `0x18000e634`
- `0x18000e718`
- `0x18001c988`
- `0x18001cf90`
- `0x18002062c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ca0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ca0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ca26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ca26`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001c9ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001c9ee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ca8d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ca8d`
- `MDMRegistration!IsDeviceRegisteredWithManagement` at `0x18001c9c7`
- `MDMRegistration!IsDeviceRegisteredWithManagement` at `0x18001c9c7`

## string_xrefs

- `0x18001ca06`: `ntdll.dll`
- `0x18001ca4b`: `InstallType`
- `0x18001caaa`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`
- `0x18001cb5b`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
bool __fastcall AIXPolicyHelper::IsDeviceITManaged(AIXPolicyHelper *this)
{
  bool v1; // cf
  int v2; // ebx
  bool v3; // di
  HMODULE ModuleHandleW; // rax
  const char *v5; // r9
  FARPROC ProcAddress; // rax
  int ValueW; // eax
  AIXPolicyHelper *v8; // rcx
  bool v9; // sf
  DWORD v10; // esi
  bool IsOOBEComplete; // al
  char v12; // r14
  __int64 v13; // rcx
  int pdwType; // [rsp+20h] [rbp-E0h]
  char v16; // [rsp+40h] [rbp-C0h] BYREF
  bool v17[3]; // [rsp+41h] [rbp-BFh] BYREF
  DWORD nSize; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR Buffer[256]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  nSize = 0;
  IsDeviceRegisteredWithManagement(&nSize, 0, 0);
  v1 = nSize != 0;
  nSize = 256;
  v2 = v1 ? 2 : 0;
  v3 = 1;
  if ( GetComputerNameExW(ComputerNamePhysicalDnsDomain, Buffer, &nSize) && Buffer[0] )
    v2 |= 1u;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  if ( !ModuleHandleW )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x143,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      v5);
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlIsFeatureEnabledForEnterprise");
  if ( !((unsigned __int8 (__fastcall *)(__int64))ProcAddress)(51549795) )
    v2 |= 4u;
  v20 = v2;
  nSize = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
             L"InstallType",
             0x10u,
             0,
             &nSize,
             &pcbData);
  v9 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    v9 = ValueW < 0;
  }
  if ( v9 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xEB,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      (const char *)(unsigned int)ValueW,
      pdwType);
  v10 = nSize;
  pcbData = nSize;
  IsOOBEComplete = AIXPolicyHelper::IsOOBEComplete(v8);
  v17[0] = IsOOBEComplete;
  v16 = 0;
  if ( v10 - 3 <= 1 || v10 == 15 || (v12 = 0, v10 == 16) )
  {
    if ( IsOOBEComplete )
    {
      v12 = 0;
    }
    else
    {
      v16 = 1;
      v12 = 1;
    }
  }
  AIXTelemetry::IsPBRInProgress<bool &,bool const &,unsigned long const &>(&v16, v17, &pcbData);
  if ( v12 )
  {
    v3 = (v2 & 3) != 0;
  }
  else if ( (v2 & 3) == 0 && (v2 & 4) == 0 )
  {
    v3 = 0;
  }
  AIXTelemetry::IsDeviceITManaged<bool (&)(void),enum AIXPolicyHelper::IsDeviceITManagedFlags const &>(v13, &v20);
  return v3;
}

```

## disassembly

```asm
0x18001c988  push    rbp
0x18001c98a  push    rbx
0x18001c98b  push    rsi
0x18001c98c  push    rdi
0x18001c98d  push    r12
0x18001c98f  push    r13
0x18001c991  push    r14
0x18001c993  push    r15
0x18001c995  lea     rbp, [rsp-168h]
0x18001c99d  sub     rsp, 268h
0x18001c9a4  mov     rax, cs:__security_cookie
0x18001c9ab  xor     rax, rsp
0x18001c9ae  mov     [rbp+1A0h+var_50], rax
0x18001c9b5  xor     r13d, r13d
0x18001c9b8  lea     rcx, [rsp+2A0h+nSize]
0x18001c9bd  xor     r8d, r8d
0x18001c9c0  mov     [rsp+2A0h+nSize], r13d
0x18001c9c5  xor     edx, edx
0x18001c9c7  call    cs:__imp_IsDeviceRegisteredWithManagement
0x18001c9cd  mov     eax, [rsp+2A0h+nSize]
0x18001c9d1  lea     r8, [rsp+2A0h+nSize]; nSize
0x18001c9d6  neg     eax
0x18001c9d8  mov     [rsp+2A0h+nSize], 100h
0x18001c9e0  lea     rdx, [rsp+2A0h+Buffer]; lpBuffer
0x18001c9e5  sbb     ebx, ebx
0x18001c9e7  lea     ecx, [r13+6]; NameType
0x18001c9eb  and     ebx, 2
0x18001c9ee  call    cs:__imp_GetComputerNameExW
0x18001c9f4  lea     edi, [r13+1]
0x18001c9f8  test    eax, eax
0x18001c9fa  jz      short loc_18001CA06
0x18001c9fc  cmp     [rsp+2A0h+Buffer], r13w
0x18001ca02  jz      short loc_18001CA06
0x18001ca04  or      ebx, edi
0x18001ca06  lea     rcx, ModuleName; "ntdll.dll"
0x18001ca0d  call    cs:__imp_GetModuleHandleW
0x18001ca13  test    rax, rax
0x18001ca16  jz      loc_18001CB54
0x18001ca1c  lea     rdx, aRtlisfeatureen; "RtlIsFeatureEnabledForEnterprise"
0x18001ca23  mov     rcx, rax; hModule
0x18001ca26  call    cs:__imp_GetProcAddress
0x18001ca2c  mov     ecx, 3129663h
0x18001ca31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca36  test    al, al
0x18001ca38  jnz     short loc_18001CA3D
0x18001ca3a  or      ebx, 4
0x18001ca3d  lea     rax, [rsp+2A0h+var_258]
0x18001ca42  mov     [rsp+2A0h+var_254], ebx
0x18001ca46  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18001ca4b  lea     r8, Value; "InstallType"
0x18001ca52  lea     rax, [rsp+2A0h+nSize]
0x18001ca57  mov     [rsp+2A0h+nSize], r13d
0x18001ca5c  mov     [rsp+2A0h+pvData], rax; pvData
0x18001ca61  lea     rdx, aHklmSoftwareMi; "HKLM\\SOFTWARE\\Microsoft\\Windows\\Cur"...
0x18001ca68  mov     r15d, ebx
0x18001ca6b  mov     [rsp+2A0h+pdwType], r13; int
0x18001ca70  and     r15d, 3
0x18001ca74  mov     [rsp+2A0h+var_258], 4
0x18001ca7c  mov     r9d, 10h; dwFlags
0x18001ca82  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001ca89  setnz   r12b
0x18001ca8d  call    cs:__imp_RegGetValueW
0x18001ca93  test    eax, eax
0x18001ca95  jle     short loc_18001CAA1
0x18001ca97  movzx   eax, ax
0x18001ca9a  or      eax, 80070000h
0x18001ca9f  test    eax, eax
0x18001caa1  jns     short loc_18001CABE
0x18001caa3  mov     rcx, [rbp+1A8h]; this
0x18001caaa  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x18001cab1  mov     r9d, eax; char *
0x18001cab4  mov     edx, 0EBh; void *
0x18001cab9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cabe  mov     esi, [rsp+2A0h+nSize]
0x18001cac2  mov     [rsp+2A0h+var_258], esi
0x18001cac6  call    ?IsOOBEComplete@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsOOBEComplete(void)
0x18001cacb  lea     ecx, [rsi-3]
0x18001cace  mov     [rsp+2A0h+var_25F], al
0x18001cad2  mov     [rsp+2A0h+var_260], r13b
0x18001cad7  cmp     ecx, edi
0x18001cad9  jbe     short loc_18001CAE8
0x18001cadb  cmp     esi, 0Fh
0x18001cade  jz      short loc_18001CAE8
0x18001cae0  mov     r14b, r13b
0x18001cae3  cmp     esi, 10h
0x18001cae6  jnz     short loc_18001CAF9
0x18001cae8  test    al, al
0x18001caea  jnz     short loc_18001CAF6
0x18001caec  mov     [rsp+2A0h+var_260], dil
0x18001caf1  mov     r14b, dil
0x18001caf4  jmp     short loc_18001CAF9
0x18001caf6  mov     r14b, r13b
0x18001caf9  lea     r8, [rsp+2A0h+var_258]
0x18001cafe  lea     rdx, [rsp+2A0h+var_25F]
0x18001cb03  lea     rcx, [rsp+2A0h+var_260]
0x18001cb08  call    ??$IsPBRInProgress@AEA_NAEB_NAEBK@AIXTelemetry@@SAXAEA_NAEB_NAEBK@Z; AIXTelemetry::IsPBRInProgress<bool &,bool const &,ulong const &>(bool &,bool const &,ulong const &)
0x18001cb0d  test    r14b, r14b
0x18001cb10  jnz     short loc_18001CB21
0x18001cb12  test    r15d, r15d
0x18001cb15  jnz     short loc_18001CB24
0x18001cb17  test    bl, 4
0x18001cb1a  jnz     short loc_18001CB24
0x18001cb1c  mov     dil, r13b
0x18001cb1f  jmp     short loc_18001CB24
0x18001cb21  mov     dil, r12b
0x18001cb24  lea     rdx, [rsp+2A0h+var_254]
0x18001cb29  call    ??$IsDeviceITManaged@A6A_NXZAEBW4IsDeviceITManagedFlags@AIXPolicyHelper@@@AIXTelemetry@@SAXA6A_NXZAEBW4IsDeviceITManagedFlags@AIXPolicyHelper@@@Z; AIXTelemetry::IsDeviceITManaged<bool (&)(void),AIXPolicyHelper::IsDeviceITManagedFlags const &>(bool (&)(void),AIXPolicyHelper::IsDeviceITManagedFlags const &)
0x18001cb2e  mov     al, dil
0x18001cb31  mov     rcx, [rbp+1A0h+var_50]
0x18001cb38  xor     rcx, rsp; StackCookie
0x18001cb3b  call    __security_check_cookie
0x18001cb40  add     rsp, 268h
0x18001cb47  pop     r15
0x18001cb49  pop     r14
0x18001cb4b  pop     r13
0x18001cb4d  pop     r12
0x18001cb4f  pop     rdi
0x18001cb50  pop     rsi
0x18001cb51  pop     rbx
0x18001cb52  pop     rbp
0x18001cb53  retn
0x18001cb54  mov     rcx, [rbp+1A8h]; this
0x18001cb5b  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x18001cb62  mov     edx, 143h; void *
0x18001cb67  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
