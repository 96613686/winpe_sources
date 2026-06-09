# GetTransformFromModule(ushort const *,HINSTANCE__ * *,_GUID const &,void * *)

- ea: `0x1800bebb8`
- end: `0x1800bed3a`
- name: `?GetTransformFromModule@@YAJPEBGPEAPEAUHINSTANCE__@@AEBU_GUID@@PEAPEAX@Z`
- size: `386`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HINSTANCE *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c25f0`

## callees

- `0x180008cf0`
- `0x180009608`
- `0x1800bebb8`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bed19`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bed19`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bec76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bec76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bec43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bec81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bec43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bec81`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800bec35`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800bec35`

## string_xrefs

- `0x1800bec6c`: `DMFTCreateInstance`

## pseudocode

```c
__int64 __fastcall GetTransformFromModule(const unsigned __int16 *a1, HINSTANCE *a2, const struct _GUID *a3, void **a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HMODULE LibraryW; // rax
  HMODULE v9; // rdi
  signed int v10; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  int v13; // eax
  __int64 v14; // rdx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, void **); // [rsp+70h] [rbp+18h] BYREF

  v16 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    if ( g_wppLevels )
    {
      v7 = 47;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids, 0, v6);
      goto LABEL_27;
    }
    goto LABEL_27;
  }
  if ( !a4 )
  {
    v6 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_27;
    v7 = 48;
    goto LABEL_4;
  }
  *a4 = 0;
  LibraryW = LoadLibraryW(a1);
  v9 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "DMFTCreateInstance");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids, 0, v6);
      goto LABEL_25;
    }
    v13 = ((__int64 (__fastcall *)(__int64 (__fastcall ****)(_QWORD, GUID *, void **)))ProcAddress)(&v16);
    v6 = v13;
    if ( v13 >= 0 )
    {
      v13 = (**v16)(v16, &GUID_eed9c2ee_66b4_4f18_a697_ac7d3960215c, a4);
      v6 = v13;
      if ( v13 >= 0 )
      {
        *a2 = v9;
        goto LABEL_27;
      }
      if ( !g_wppLevels )
        goto LABEL_25;
      v14 = 52;
    }
    else
    {
      if ( !g_wppLevels )
      {
LABEL_25:
        FreeLibrary(v9);
        goto LABEL_27;
      }
      v14 = 51;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids, 0, v13);
    goto LABEL_25;
  }
  v10 = GetLastError();
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( g_wppLevels )
  {
    v7 = 49;
    goto LABEL_4;
  }
LABEL_27:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v16);
  return v6;
}

```

## disassembly

```asm
0x1800bebb8  mov     [rsp+arg_10], r8
0x1800bebbd  push    rbx
0x1800bebbe  push    rsi
0x1800bebbf  push    rdi
0x1800bebc0  push    r14
0x1800bebc2  sub     rsp, 38h
0x1800bebc6  mov     [rsp+58h+arg_10], 0
0x1800bebcf  mov     rsi, r9
0x1800bebd2  mov     r14, rdx
0x1800bebd5  test    rcx, rcx
0x1800bebd8  jnz     short loc_1800BEC12
0x1800bebda  mov     ebx, 80070057h
0x1800bebdf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bebe6  jb      loc_1800BED24
0x1800bebec  lea     edx, [rcx+2Fh]
0x1800bebef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bebf6  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x1800bebfd  xor     r9d, r9d
0x1800bec00  mov     [rsp+58h+var_38], ebx
0x1800bec04  mov     rcx, [rcx+10h]
0x1800bec08  call    WPP_SF_qD
0x1800bec0d  jmp     loc_1800BED24
0x1800bec12  test    rsi, rsi
0x1800bec15  jnz     short loc_1800BEC2E
0x1800bec17  mov     ebx, 80004003h
0x1800bec1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bec23  jb      loc_1800BED24
0x1800bec29  lea     edx, [rsi+30h]
0x1800bec2c  jmp     short loc_1800BEBEF
0x1800bec2e  mov     qword ptr [r9], 0
0x1800bec35  call    cs:__imp_LoadLibraryW
0x1800bec3b  mov     rdi, rax
0x1800bec3e  test    rax, rax
0x1800bec41  jnz     short loc_1800BEC6C
0x1800bec43  call    cs:__imp_GetLastError
0x1800bec49  mov     ebx, eax
0x1800bec4b  test    eax, eax
0x1800bec4d  jle     short loc_1800BEC58
0x1800bec4f  movzx   ebx, ax
0x1800bec52  or      ebx, 80070000h
0x1800bec58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bec5f  jb      loc_1800BED24
0x1800bec65  mov     edx, 31h ; '1'
0x1800bec6a  jmp     short loc_1800BEBEF
0x1800bec6c  lea     rdx, aDmftcreateinst; "DMFTCreateInstance"
0x1800bec73  mov     rcx, rdi; hModule
0x1800bec76  call    cs:__imp_GetProcAddress
0x1800bec7c  test    rax, rax
0x1800bec7f  jnz     short loc_1800BECAA
0x1800bec81  call    cs:__imp_GetLastError
0x1800bec87  mov     ebx, eax
0x1800bec89  test    eax, eax
0x1800bec8b  jle     short loc_1800BEC96
0x1800bec8d  movzx   ebx, ax
0x1800bec90  or      ebx, 80070000h
0x1800bec96  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bec9d  jb      short loc_1800BED16
0x1800bec9f  mov     edx, 32h ; '2'
0x1800beca4  mov     [rsp+58h+var_38], ebx
0x1800beca8  jmp     short loc_1800BECFC
0x1800becaa  lea     rcx, [rsp+58h+arg_10]
0x1800becaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800becb4  mov     ebx, eax
0x1800becb6  test    eax, eax
0x1800becb8  jns     short loc_1800BECCA
0x1800becba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800becc1  jb      short loc_1800BED16
0x1800becc3  mov     edx, 33h ; '3'
0x1800becc8  jmp     short loc_1800BECF8
0x1800becca  mov     rcx, [rsp+58h+arg_10]
0x1800beccf  lea     rdx, _GUID_eed9c2ee_66b4_4f18_a697_ac7d3960215c
0x1800becd6  mov     r8, rsi
0x1800becd9  mov     rax, [rcx]
0x1800becdc  mov     rax, [rax]
0x1800becdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bece4  mov     ebx, eax
0x1800bece6  test    eax, eax
0x1800bece8  jns     short loc_1800BED21
0x1800becea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800becf1  jb      short loc_1800BED16
0x1800becf3  mov     edx, 34h ; '4'
0x1800becf8  mov     [rsp+58h+var_38], eax
0x1800becfc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bed03  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x1800bed0a  xor     r9d, r9d
0x1800bed0d  mov     rcx, [rcx+10h]
0x1800bed11  call    WPP_SF_qD
0x1800bed16  mov     rcx, rdi; hLibModule
0x1800bed19  call    cs:__imp_FreeLibrary
0x1800bed1f  jmp     short loc_1800BED24
0x1800bed21  mov     [r14], rdi
0x1800bed24  lea     rcx, [rsp+58h+arg_10]; void *
0x1800bed29  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bed2e  mov     eax, ebx
0x1800bed30  add     rsp, 38h
0x1800bed34  pop     r14
0x1800bed36  pop     rdi
0x1800bed37  pop     rsi
0x1800bed38  pop     rbx
0x1800bed39  retn
```
