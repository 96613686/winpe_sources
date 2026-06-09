# SystemSettings::WorkplaceHandlers::CEnrollmentHelper::GetOmadmValue(ulong)

- ea: `0x1801b0b90`
- end: `0x1801b0e94`
- name: `?GetOmadmValue@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@SAJK@Z`
- size: `772`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801ac3f0`
- `0x1801aefa0`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x180019a20`
- `0x18001a64c`
- `0x18004d1ac`
- `0x1801ad640`
- `0x1801b091c`
- `0x1801b0b90`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1801b0e3c`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b0e3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b0d01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b0d4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b0d5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b0e02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b0d01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b0d4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b0d5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b0e02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b0c70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b0da7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b0c70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b0da7`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x1801b0e56`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x1801b0e56`
- `omadmapi!__imp_OmaDmGetAllAcctInfo` at `0x1801b0c89`
- `omadmapi!__imp_OmaDmGetAllAcctInfo` at `0x1801b0c89`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x1801b0bfc`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x1801b0c22`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x1801b0bfc`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x1801b0c22`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::WorkplaceHandlers::CEnrollmentHelper::GetOmadmValue(int a1)
{
  int AllAcctInfo; // eax
  unsigned int v3; // edi
  __int64 v4; // rdx
  PCWSTR StringRawBuffer; // rax
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  unsigned __int16 *v9; // rdi
  HSTRING *v10; // r8
  int ResourceStringById; // eax
  __int64 v12; // rdx
  HSTRING v13; // rcx
  HSTRING *v14; // r8
  HSTRING v15; // rbx
  const unsigned __int16 *v16; // rax
  int v17; // eax
  unsigned __int16 *v18; // rcx
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v21; // [rsp+28h] [rbp-D8h] BYREF
  UINT32 length; // [rsp+30h] [rbp-D0h] BYREF
  int *v23; // [rsp+38h] [rbp-C8h]
  char v24; // [rsp+40h] [rbp-C0h]
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[28]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 *v27; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v28; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v29; // [rsp+1C0h] [rbp+C0h]
  unsigned __int16 *v30; // [rsp+1C8h] [rbp+C8h]
  unsigned int v31; // [rsp+1DCh] [rbp+DCh]
  unsigned __int16 v32[264]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+378h]

  memset_0(v26, 0, 0x1FCu);
  v25 = 512;
  v21 = 0;
  v23 = &v25;
  v24 = 1;
  AllAcctInfo = OmaDmSetNodeValuePresence(48, &v25);
  v3 = AllAcctInfo;
  if ( AllAcctInfo >= 0 )
  {
    AllAcctInfo = OmaDmSetNodeValuePresence(45, &v25);
    v3 = AllAcctInfo;
    if ( AllAcctInfo < 0 )
    {
      v4 = 205;
      goto LABEL_5;
    }
    if ( !SystemSettings::WorkplaceHandlers::CEnrollmentHelper::spAccountEnthusiastSingleton )
    {
      v3 = -2147467261;
      goto LABEL_35;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(
                        *(HSTRING *)(SystemSettings::WorkplaceHandlers::CEnrollmentHelper::spAccountEnthusiastSingleton
                                   + 8),
                        0);
    AllAcctInfo = OmaDmGetAllAcctInfo(StringRawBuffer, 1, &v25);
    v3 = AllAcctInfo;
    if ( AllAcctInfo < 0 )
    {
      v4 = 212;
      goto LABEL_5;
    }
    if ( a1 )
    {
      v6 = a1 - 1;
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            if ( v8 == 1 )
              v9 = v28;
            else
              v9 = (unsigned __int16 *)&LocaleName;
          }
          else
          {
            v9 = v27;
          }
          goto LABEL_34;
        }
        if ( !v29 )
        {
          v9 = L"CorpDeviceManagementNoValue";
LABEL_34:
          SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value = (HSTRING)SysAllocString(v9);
          v3 = 0;
          goto LABEL_35;
        }
        if ( v31 )
        {
          WindowsDeleteString(0);
          string = 0;
          ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                                 (SystemSettings::DataModel *)L"SystemSettings_Workplace_CorpDeviceManagement_SyncFailure",
                                 &string,
                                 v14);
          v3 = ResourceStringById;
          if ( ResourceStringById < 0 )
          {
            v12 = 251;
            goto LABEL_23;
          }
        }
        else
        {
          WindowsDeleteString(0);
          string = 0;
          ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                                 (SystemSettings::DataModel *)L"SystemSettings_Workplace_CorpDeviceManagement_SyncSuccess",
                                 &string,
                                 v10);
          v3 = ResourceStringById;
          if ( ResourceStringById < 0 )
          {
            v12 = 247;
LABEL_23:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v12,
              (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\workplace\\src\\enrollmenthelper.cpp",
              (const char *)(unsigned int)ResourceStringById,
              (int)string);
            v13 = string;
            goto LABEL_24;
          }
        }
        length = 0;
        v15 = string;
        v16 = WindowsGetStringRawBuffer(string, &length);
        v17 = StringCchPrintfW(v32, 0x104u, v16, v31);
        v3 = v17;
        if ( v17 >= 0 )
        {
          v9 = v32;
          WindowsDeleteString(v15);
          goto LABEL_34;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFF,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\workplace\\src\\enrollmenthelper.cpp",
          (const char *)(unsigned int)v17,
          (int)string);
        v13 = v15;
LABEL_24:
        WindowsDeleteString(v13);
        goto LABEL_35;
      }
      v18 = v30;
    }
    else
    {
      v18 = v29;
    }
    v9 = L"CorpDeviceManagementNoValue";
    if ( (int)SystemSettings::WorkplaceHandlers::CEnrollmentHelper::ConvertISO8601StringToLocalizedString(v18, &v21) >= 0 )
      v9 = v21;
    goto LABEL_34;
  }
  v4 = 204;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\workplace\\src\\enrollmenthelper.cpp",
    (const char *)(unsigned int)AllAcctInfo,
    (int)string);
LABEL_35:
  OmaDmFreeAcctInfo(&v25);
  CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v21);
  return v3;
}

```

## disassembly

```asm
0x1801b0b90  mov     [rsp-8+arg_0], rbx
0x1801b0b95  mov     [rsp-8+arg_8], rdi
0x1801b0b9a  push    rbp
0x1801b0b9b  lea     rbp, [rsp-370h]
0x1801b0ba3  sub     rsp, 470h
0x1801b0baa  mov     rax, cs:__security_cookie
0x1801b0bb1  xor     rax, rsp
0x1801b0bb4  mov     [rbp+370h+var_10], rax
0x1801b0bbb  mov     ebx, ecx
0x1801b0bbd  xor     edx, edx; Val
0x1801b0bbf  mov     r8d, 1FCh; Size
0x1801b0bc5  lea     rcx, [rsp+470h+var_41C]; void *
0x1801b0bca  call    memset_0
0x1801b0bcf  mov     [rsp+470h+var_420], 200h
0x1801b0bd7  mov     [rsp+470h+var_448], 0
0x1801b0be0  lea     rax, [rsp+470h+var_420]
0x1801b0be5  mov     [rsp+470h+var_438], rax
0x1801b0bea  mov     [rsp+470h+var_430], 1
0x1801b0bef  or      r8d, 0FFFFFFFFh
0x1801b0bf3  lea     rdx, [rsp+470h+var_420]
0x1801b0bf8  lea     ecx, [r8+31h]
0x1801b0bfc  call    cs:__imp_OmaDmSetNodeValuePresence
0x1801b0c03  nop     dword ptr [rax+rax+00h]
0x1801b0c08  mov     edi, eax
0x1801b0c0a  test    eax, eax
0x1801b0c0c  jns     short loc_1801B0C15
0x1801b0c0e  mov     edx, 0CCh
0x1801b0c13  jmp     short loc_1801B0C39
0x1801b0c15  or      r8d, 0FFFFFFFFh
0x1801b0c19  lea     rdx, [rsp+470h+var_420]
0x1801b0c1e  lea     ecx, [r8+2Eh]
0x1801b0c22  call    cs:__imp_OmaDmSetNodeValuePresence
0x1801b0c29  nop     dword ptr [rax+rax+00h]
0x1801b0c2e  mov     edi, eax
0x1801b0c30  test    eax, eax
0x1801b0c32  jns     short loc_1801B0C54
0x1801b0c34  mov     edx, 0CDh; void *
0x1801b0c39  mov     rcx, [rbp+378h]; this
0x1801b0c40  mov     r9d, eax; char *
0x1801b0c43  lea     r8, aShellSystemset_23; "shell\\systemsettingsthreshold\\handler"...
0x1801b0c4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b0c4f  jmp     loc_1801B0E51
0x1801b0c54  mov     rcx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkplaceHandlers@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkplaceHandlers::CAccountEnthusiastData> SystemSettings::WorkplaceHandlers::CEnrollmentHelper::spAccountEnthusiastSingleton
0x1801b0c5b  test    rcx, rcx
0x1801b0c5e  jnz     short loc_1801B0C6A
0x1801b0c60  mov     edi, 80004003h
0x1801b0c65  jmp     loc_1801B0E51
0x1801b0c6a  xor     edx, edx; length
0x1801b0c6c  mov     rcx, [rcx+8]; string
0x1801b0c70  call    cs:__imp_WindowsGetStringRawBuffer
0x1801b0c77  nop     dword ptr [rax+rax+00h]
0x1801b0c7c  mov     rcx, rax
0x1801b0c7f  lea     r8, [rsp+470h+var_420]
0x1801b0c84  mov     edx, 1
0x1801b0c89  call    cs:__imp_OmaDmGetAllAcctInfo
0x1801b0c90  nop     dword ptr [rax+rax+00h]
0x1801b0c95  mov     edi, eax
0x1801b0c97  test    eax, eax
0x1801b0c99  jns     short loc_1801B0CA2
0x1801b0c9b  mov     edx, 0D4h
0x1801b0ca0  jmp     short loc_1801B0C39
0x1801b0ca2  test    ebx, ebx
0x1801b0ca4  jz      loc_1801B0E19
0x1801b0caa  sub     ebx, 1
0x1801b0cad  jz      loc_1801B0E10
0x1801b0cb3  sub     ebx, 1
0x1801b0cb6  jz      short loc_1801B0CE1
0x1801b0cb8  sub     ebx, 1
0x1801b0cbb  jz      short loc_1801B0CD7
0x1801b0cbd  cmp     ebx, 1
0x1801b0cc0  jz      short loc_1801B0CCE
0x1801b0cc2  lea     rdi, LocaleName
0x1801b0cc9  jmp     loc_1801B0E39
0x1801b0cce  mov     rdi, [rbp+370h+var_388]
0x1801b0cd2  jmp     loc_1801B0E39
0x1801b0cd7  mov     rdi, [rsp+470h+var_400]
0x1801b0cdc  jmp     loc_1801B0E39
0x1801b0ce1  cmp     [rbp+370h+var_2B0], 0
0x1801b0ce9  jnz     short loc_1801B0CF7
0x1801b0ceb  lea     rdi, aCorpdevicemana_4; "CorpDeviceManagementNoValue"
0x1801b0cf2  jmp     loc_1801B0E39
0x1801b0cf7  xor     ecx, ecx; string
0x1801b0cf9  cmp     [rbp+370h+var_294], ecx
0x1801b0cff  jnz     short loc_1801B0D5F
0x1801b0d01  call    cs:__imp_WindowsDeleteString
0x1801b0d08  nop     dword ptr [rax+rax+00h]
0x1801b0d0d  mov     [rsp+470h+string], 0; int
0x1801b0d16  lea     rdx, [rsp+470h+string]; HSTRING *
0x1801b0d1b  lea     rcx, aSystemsettings_315; "SystemSettings_Workplace_CorpDeviceMana"...
0x1801b0d22  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1801b0d27  mov     edi, eax
0x1801b0d29  test    eax, eax
0x1801b0d2b  jns     short loc_1801B0D92
0x1801b0d2d  mov     edx, 0F7h; void *
0x1801b0d32  lea     r8, aShellSystemset_23; "shell\\systemsettingsthreshold\\handler"...
0x1801b0d39  mov     r9d, eax; char *
0x1801b0d3c  mov     rcx, [rbp+378h]; this
0x1801b0d43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b0d48  nop
0x1801b0d49  mov     rcx, [rsp+470h+string]; string
0x1801b0d4e  call    cs:__imp_WindowsDeleteString
0x1801b0d55  nop     dword ptr [rax+rax+00h]
0x1801b0d5a  jmp     loc_1801B0E51
0x1801b0d5f  call    cs:__imp_WindowsDeleteString
0x1801b0d66  nop     dword ptr [rax+rax+00h]
0x1801b0d6b  mov     [rsp+470h+string], 0
0x1801b0d74  lea     rdx, [rsp+470h+string]; HSTRING *
0x1801b0d79  lea     rcx, aSystemsettings_681; "SystemSettings_Workplace_CorpDeviceMana"...
0x1801b0d80  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1801b0d85  mov     edi, eax
0x1801b0d87  test    eax, eax
0x1801b0d89  jns     short loc_1801B0D92
0x1801b0d8b  mov     edx, 0FBh
0x1801b0d90  jmp     short loc_1801B0D32
0x1801b0d92  mov     [rsp+470h+length], 0
0x1801b0d9a  lea     rdx, [rsp+470h+length]; length
0x1801b0d9f  mov     rbx, [rsp+470h+string]
0x1801b0da4  mov     rcx, rbx; string
0x1801b0da7  call    cs:__imp_WindowsGetStringRawBuffer
0x1801b0dae  nop     dword ptr [rax+rax+00h]
0x1801b0db3  mov     r9d, [rbp+370h+var_294]
0x1801b0dba  mov     r8, rax; unsigned __int16 *
0x1801b0dbd  mov     edx, 104h; unsigned __int64
0x1801b0dc2  lea     rcx, [rbp+370h+var_220]; unsigned __int16 *
0x1801b0dc9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801b0dce  mov     edi, eax
0x1801b0dd0  test    eax, eax
0x1801b0dd2  jns     short loc_1801B0DF8
0x1801b0dd4  mov     rcx, [rbp+378h]; this
0x1801b0ddb  mov     r9d, eax; char *
0x1801b0dde  lea     r8, aShellSystemset_23; "shell\\systemsettingsthreshold\\handler"...
0x1801b0de5  mov     edx, 0FFh; void *
0x1801b0dea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b0def  nop
0x1801b0df0  mov     rcx, rbx
0x1801b0df3  jmp     loc_1801B0D4E
0x1801b0df8  lea     rdi, [rbp+370h+var_220]
0x1801b0dff  mov     rcx, rbx; string
0x1801b0e02  call    cs:__imp_WindowsDeleteString
0x1801b0e09  nop     dword ptr [rax+rax+00h]
0x1801b0e0e  jmp     short loc_1801B0E39
0x1801b0e10  mov     rcx, [rbp+370h+var_2A8]
0x1801b0e17  jmp     short loc_1801B0E20
0x1801b0e19  mov     rcx, [rbp+370h+var_2B0]; unsigned __int16 *
0x1801b0e20  lea     rdx, [rsp+470h+var_448]; unsigned __int16 **
0x1801b0e25  call    ?ConvertISO8601StringToLocalizedString@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@SAJQEBGPEAPEAG@Z; SystemSettings::WorkplaceHandlers::CEnrollmentHelper::ConvertISO8601StringToLocalizedString(ushort const * const,ushort * *)
0x1801b0e2a  lea     rdi, aCorpdevicemana_4; "CorpDeviceManagementNoValue"
0x1801b0e31  test    eax, eax
0x1801b0e33  cmovns  rdi, [rsp+470h+var_448]
0x1801b0e39  mov     rcx, rdi; psz
0x1801b0e3c  call    cs:__imp_SysAllocString
0x1801b0e43  nop     dword ptr [rax+rax+00h]
0x1801b0e48  mov     cs:?_value@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@2PEAGEA, rax; ushort * SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value
0x1801b0e4f  xor     edi, edi
0x1801b0e51  lea     rcx, [rsp+470h+var_420]
0x1801b0e56  call    cs:__imp_OmaDmFreeAcctInfo
0x1801b0e5d  nop     dword ptr [rax+rax+00h]
0x1801b0e62  nop
0x1801b0e63  lea     rcx, [rsp+470h+var_448]
0x1801b0e68  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x1801b0e6d  mov     eax, edi
0x1801b0e6f  mov     rcx, [rbp+370h+var_10]
0x1801b0e76  xor     rcx, rsp; StackCookie
0x1801b0e79  call    __security_check_cookie
0x1801b0e7e  lea     r11, [rsp+470h+var_s0]
0x1801b0e86  mov     rbx, [r11+10h]
0x1801b0e8a  mov     rdi, [r11+18h]
0x1801b0e8e  mov     rsp, r11
0x1801b0e91  pop     rbp
0x1801b0e92  retn
```
