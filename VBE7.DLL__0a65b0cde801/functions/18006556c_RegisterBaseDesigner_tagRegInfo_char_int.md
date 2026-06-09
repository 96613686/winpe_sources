# _RegisterBaseDesigner(tagRegInfo *,char *,int)

- ea: `0x18006556c`
- end: `0x1800657b1`
- name: `?_RegisterBaseDesigner@@YAIPEAUtagRegInfo@@PEADH@Z`
- size: `581`
- prototype: `unsigned int __fastcall(struct tagRegInfo *, char *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180063218`
- `0x1800657b8`

## callees

- `0x180015ae8`
- `0x180016790`
- `0x18003acb4`
- `0x18005acac`
- `0x18005b0d4`
- `0x18006556c`
- `0x180379380`
- `0x180379520`
- `0x1803796b4`

## import_xrefs

- `KERNEL32!lstrcpyA` at `0x1800655b1`
- `KERNEL32!lstrcpyA` at `0x1800655b1`
- `KERNEL32!lstrcatA` at `0x1800655e0`
- `KERNEL32!lstrcatA` at `0x1800655e0`
- `KERNEL32!FreeLibrary` at `0x18006577a`
- `KERNEL32!FreeLibrary` at `0x18006577a`
- `KERNEL32!GetProcAddress` at `0x180065734`
- `KERNEL32!GetProcAddress` at `0x180065734`
- `ADVAPI32!RegOpenKeyExA` at `0x180065608`
- `ADVAPI32!RegOpenKeyExA` at `0x180065608`
- `ADVAPI32!RegQueryValueExA` at `0x18006564b`
- `ADVAPI32!RegQueryValueExA` at `0x18006564b`
- `ADVAPI32!RegCloseKey` at `0x18006567a`
- `ADVAPI32!RegCloseKey` at `0x18006567a`
- `OLEAUT32!__imp_SysFreeString` at `0x18006578a`
- `OLEAUT32!__imp_SysFreeString` at `0x18006578a`

## string_xrefs

- `0x1800655a2`: `CLSID\`
- `0x18006571c`: `DllRegisterDesigner`
- `0x180065723`: `DllUnregisterDesigner`

## pseudocode

```c
unsigned int __fastcall _RegisterBaseDesigner(struct tagRegInfo *a1, char *a2, int a3)
{
  LSTATUS v6; // ebx
  HMODULE Library; // rdi
  const CHAR *v9; // rdx
  FARPROC ProcAddress; // rax
  int v11; // eax
  unsigned int v12; // ebx
  DWORD cbData; // [rsp+34h] [rbp-994h] BYREF
  DWORD Type; // [rsp+38h] [rbp-990h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-988h] BYREF
  HMODULE v16; // [rsp+48h] [rbp-980h]
  _DWORD v17[2]; // [rsp+50h] [rbp-978h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-970h]
  __int128 v19; // [rsp+60h] [rbp-968h]
  __int128 v20; // [rsp+70h] [rbp-958h]
  __int16 v21; // [rsp+80h] [rbp-948h]
  __int16 v22; // [rsp+82h] [rbp-946h]
  __int64 v23; // [rsp+88h] [rbp-940h]
  CHAR String1[6]; // [rsp+90h] [rbp-938h] BYREF
  char v25[250]; // [rsp+96h] [rbp-932h] BYREF
  BYTE Data[2048]; // [rsp+190h] [rbp-838h] BYREF

  v16 = 0;
  lstrcpyA(String1, "CLSID\\");
  StringFromGUID2Ansi((const struct _GUID *)((char *)a1 + 132), v25, 250);
  lstrcatA(String1, "\\InprocServer32");
  v6 = RegOpenKeyExA(HKEY_CLASSES_ROOT, String1, 0, 0x20019u, &hKey);
  if ( !v6 )
  {
    Type = 1;
    cbData = 2048;
    v6 = RegQueryValueExA(hKey, 0, 0, &Type, Data, &cbData);
    if ( !v6 )
    {
      if ( cbData - 1 >= 0x800uLL )
        _report_gsfailure(0);
      Data[cbData - 1] = v6;
    }
    RegCloseKey(hKey);
  }
  if ( v6 )
    return ErrFromRegError(v6);
  bstrString = 0;
  Library = (HMODULE)IsolationAwareLoadLibraryExA(Data, 0, 8);
  v16 = Library;
  if ( !Library )
    return 48;
  v17[0] = 64;
  v17[1] = 2 - (*((_DWORD *)a1 + 26) != 0);
  bstrString = AllocBstrWfromA(a2);
  v19 = *((_OWORD *)a1 + 2);
  v20 = *((_OWORD *)a1 + 5);
  v21 = *((_WORD *)a1 + 60);
  v22 = *((_WORD *)a1 + 61);
  v23 = *((_QWORD *)a1 + 19);
  v9 = "DllUnregisterDesigner";
  if ( a3 )
    v9 = "DllRegisterDesigner";
  ProcAddress = GetProcAddress(Library, v9);
  if ( ProcAddress )
  {
    v11 = ((__int64 (__fastcall *)(_DWORD *))ProcAddress)(v17);
    if ( v11 < 0 )
      v12 = _ErrFromHrDefault(v11);
    else
      v12 = 0;
  }
  else
  {
    v12 = 48;
  }
  FreeLibrary(Library);
  if ( bstrString )
    SysFreeString(bstrString);
  return v12;
}

```

## disassembly

```asm
0x18006556c  push    rbx
0x18006556e  push    rsi
0x18006556f  push    rdi
0x180065570  push    r14
0x180065572  push    r15
0x180065574  mov     eax, 9A0h
0x180065579  call    _alloca_probe
0x18006557e  sub     rsp, rax
0x180065581  mov     rax, cs:__security_cookie
0x180065588  xor     rax, rsp
0x18006558b  mov     [rsp+9C8h+var_38], rax
0x180065593  mov     r15d, r8d
0x180065596  mov     r14, rdx
0x180065599  mov     rsi, rcx
0x18006559c  and     [rsp+9C8h+var_980], 0
0x1800655a2  lea     rdx, String2; "CLSID\\"
0x1800655a9  lea     rcx, [rsp+9C8h+String1]; lpString1
0x1800655b1  call    cs:__imp_lstrcpyA
0x1800655b7  lea     rcx, [rsi+84h]; struct _GUID *
0x1800655be  mov     r8d, 0FAh; int
0x1800655c4  lea     rdx, [rsp+9C8h+var_932]; char *
0x1800655cc  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x1800655d1  lea     rdx, aInprocserver32_0; "\\InprocServer32"
0x1800655d8  lea     rcx, [rsp+9C8h+String1]; lpString1
0x1800655e0  call    cs:__imp_lstrcatA
0x1800655e6  lea     r11, [rsp+9C8h+hKey]
0x1800655eb  mov     [rsp+9C8h+phkResult], r11; phkResult
0x1800655f0  mov     r9d, 20019h; samDesired
0x1800655f6  xor     r8d, r8d; ulOptions
0x1800655f9  lea     rdx, [rsp+9C8h+String1]; lpSubKey
0x180065601  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180065608  call    cs:__imp_RegOpenKeyExA
0x18006560e  mov     ebx, eax
0x180065610  test    eax, eax
0x180065612  jnz     short loc_180065680
0x180065614  mov     [rsp+9C8h+Type], 1
0x18006561c  mov     edi, 800h
0x180065621  mov     [rsp+9C8h+cbData], edi
0x180065625  lea     rax, [rsp+9C8h+cbData]
0x18006562a  mov     [rsp+9C8h+lpcbData], rax; lpcbData
0x18006562f  lea     rax, [rsp+9C8h+Data]
0x180065637  mov     [rsp+9C8h+phkResult], rax; lpData
0x18006563c  lea     r9, [rsp+9C8h+Type]; lpType
0x180065641  xor     r8d, r8d; lpReserved
0x180065644  xor     edx, edx; lpValueName
0x180065646  mov     rcx, [rsp+9C8h+hKey]; hKey
0x18006564b  call    cs:__imp_RegQueryValueExA
0x180065651  mov     ebx, eax
0x180065653  test    eax, eax
0x180065655  jnz     short loc_180065675
0x180065657  mov     eax, [rsp+9C8h+cbData]
0x18006565b  dec     eax
0x18006565d  mov     ecx, eax
0x18006565f  cmp     rcx, rdi
0x180065662  jnb     short loc_18006566D
0x180065664  mov     [rsp+rax+9C8h+Data], bl
0x18006566b  jmp     short loc_180065675
0x18006566d  xor     ecx, ecx; StackCookie
0x18006566f  call    __report_gsfailure
0x180065675  mov     rcx, [rsp+9C8h+hKey]; hKey
0x18006567a  call    cs:__imp_RegCloseKey
0x180065680  test    ebx, ebx
0x180065682  jz      short loc_180065690
0x180065684  mov     ecx, ebx; int
0x180065686  call    ?ErrFromRegError@@YAIJ@Z; ErrFromRegError(long)
0x18006568b  jmp     loc_180065792
0x180065690  and     [rsp+9C8h+bstrString], 0
0x180065696  xor     edx, edx
0x180065698  lea     r8d, [rdx+8]
0x18006569c  lea     rcx, [rsp+9C8h+Data]
0x1800656a4  call    IsolationAwareLoadLibraryExA
0x1800656a9  mov     rdi, rax
0x1800656ac  mov     [rsp+9C8h+var_980], rax
0x1800656b1  test    rax, rax
0x1800656b4  jnz     short loc_1800656BE
0x1800656b6  lea     eax, [rdi+30h]
0x1800656b9  jmp     loc_180065792
0x1800656be  mov     [rsp+9C8h+var_978], 40h ; '@'
0x1800656c6  mov     eax, [rsi+68h]
0x1800656c9  neg     eax
0x1800656cb  sbb     edx, edx
0x1800656cd  add     edx, 2
0x1800656d0  mov     [rsp+9C8h+var_974], edx
0x1800656d4  mov     rcx, r14; char *
0x1800656d7  call    ?AllocBstrWfromA@@YAPEA_WPEBD@Z; AllocBstrWfromA(char const *)
0x1800656dc  mov     [rsp+9C8h+bstrString], rax
0x1800656e1  movups  xmm0, xmmword ptr [rsi+20h]
0x1800656e5  movdqu  [rsp+9C8h+var_968], xmm0
0x1800656eb  movups  xmm1, xmmword ptr [rsi+50h]
0x1800656ef  movdqu  [rsp+9C8h+var_958], xmm1
0x1800656f5  movzx   eax, word ptr [rsi+78h]
0x1800656f9  mov     [rsp+9C8h+var_948], ax
0x180065701  movzx   eax, word ptr [rsi+7Ah]
0x180065705  mov     [rsp+9C8h+var_946], ax
0x18006570d  mov     rax, [rsi+98h]
0x180065714  mov     [rsp+9C8h+var_940], rax
0x18006571c  lea     rax, aDllregisterdes; "DllRegisterDesigner"
0x180065723  lea     rdx, aDllunregisterd; "DllUnregisterDesigner"
0x18006572a  test    r15d, r15d
0x18006572d  cmovnz  rdx, rax; lpProcName
0x180065731  mov     rcx, rdi; hModule
0x180065734  call    cs:__imp_GetProcAddress
0x18006573a  test    rax, rax
0x18006573d  jz      short loc_180065759
0x18006573f  lea     rcx, [rsp+9C8h+var_978]
0x180065744  call    rax
0x180065746  test    eax, eax
0x180065748  js      short loc_18006574E
0x18006574a  xor     ebx, ebx
0x18006574c  jmp     short loc_18006575E
0x18006574e  mov     ecx, eax; int
0x180065750  call    ?_ErrFromHrDefault@@YAIJ@Z; _ErrFromHrDefault(long)
0x180065755  mov     ebx, eax
0x180065757  jmp     short loc_18006575E
0x180065759  mov     ebx, 30h ; '0'
0x18006575e  mov     [rsp+9C8h+var_998], ebx
0x180065762  jmp     short loc_180065772
0x180065764  mov     ebx, 30h ; '0'
0x180065769  mov     [rsp+9C8h+var_998], ebx
0x18006576d  mov     rdi, [rsp+9C8h+var_980]
0x180065772  test    rdi, rdi
0x180065775  jz      short loc_180065780
0x180065777  mov     rcx, rdi; hLibModule
0x18006577a  call    cs:__imp_FreeLibrary
0x180065780  mov     rcx, [rsp+9C8h+bstrString]; bstrString
0x180065785  test    rcx, rcx
0x180065788  jz      short loc_180065790
0x18006578a  call    cs:__imp_SysFreeString
0x180065790  mov     eax, ebx
0x180065792  mov     rcx, [rsp+9C8h+var_38]
0x18006579a  xor     rcx, rsp; StackCookie
0x18006579d  call    __security_check_cookie
0x1800657a2  add     rsp, 9A0h
0x1800657a9  pop     r15
0x1800657ab  pop     r14
0x1800657ad  pop     rdi
0x1800657ae  pop     rsi
0x1800657af  pop     rbx
0x1800657b0  retn
0x180380bba  push    rbp
0x180380bbc  mov     eax, 30h ; '0'
0x180380bc1  call    _alloca_probe
0x180380bc6  sub     rsp, rax
0x180380bc9  mov     rbp, rdx
0x180380bcc  mov     rax, [rcx]
0x180380bcf  xor     ecx, ecx
0x180380bd1  cmp     dword ptr [rax], 0C0000005h
0x180380bd7  setz    cl
0x180380bda  mov     eax, ecx
0x180380bdc  mov     eax, ecx
0x180380bde  add     rsp, 30h
0x180380be2  pop     rbp
0x180380be3  retn
```
