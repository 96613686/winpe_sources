# GetTransformFromModule(ushort const *,HINSTANCE__ * *,_GUID const &,void * *)

- ea: `0x18002eb3c`
- end: `0x18002ecba`
- name: `?GetTransformFromModule@@YAJPEBGPEAPEAUHINSTANCE__@@AEBU_GUID@@PEAPEAX@Z`
- size: `382`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HINSTANCE *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f698`

## callees

- `0x180005f98`
- `0x1800060f8`
- `0x180006a98`
- `0x18002eb3c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18002ebb9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18002ebb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ebfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ebfa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ec99`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ec99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec05`

## string_xrefs

- `0x18002ebf0`: `DMFTCreateInstance`

## pseudocode

```c
__int64 __fastcall GetTransformFromModule(const unsigned __int16 *a1, HINSTANCE *a2, const struct _GUID *a3, void **a4)
{
  signed int v6; // ebx
  int v7; // ecx
  __int64 v8; // rdx
  HMODULE LibraryW; // rax
  HMODULE v10; // rdi
  signed int v11; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  __int64 v14; // rdx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, void **); // [rsp+70h] [rbp+18h] BYREF

  v16 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v8 = (unsigned int)(v7 + 47);
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids, 0, v6);
      goto LABEL_27;
    }
    goto LABEL_27;
  }
  if ( !a4 )
  {
    v6 = -2147467261;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_27;
    v8 = 48;
    goto LABEL_4;
  }
  *a4 = 0;
  LibraryW = LoadLibraryW(a1);
  v10 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "DMFTCreateInstance");
    if ( ProcAddress )
    {
      v6 = ((__int64 (__fastcall *)(__int64 (__fastcall ****)(_QWORD, GUID *, void **)))ProcAddress)(&v16);
      if ( v6 >= 0 )
      {
        v6 = (**v16)(v16, &GUID_00000000_0000_0000_c000_000000000046, a4);
        if ( v6 >= 0 )
        {
          *a2 = v10;
          goto LABEL_27;
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_25;
        v14 = 52;
      }
      else
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
LABEL_25:
          FreeLibrary(v10);
          goto LABEL_27;
        }
        v14 = 51;
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_25;
      v14 = 50;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids, 0, v6);
    goto LABEL_25;
  }
  v11 = GetLastError();
  v6 = v11;
  if ( v11 > 0 )
    v6 = (unsigned __int16)v11 | 0x80070000;
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v8 = 49;
    goto LABEL_4;
  }
LABEL_27:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002eb3c  mov     [rsp+arg_10], r8
0x18002eb41  push    rbx
0x18002eb42  push    rsi
0x18002eb43  push    rdi
0x18002eb44  push    r14
0x18002eb46  sub     rsp, 38h
0x18002eb4a  mov     [rsp+58h+arg_10], 0
0x18002eb53  mov     rsi, r9
0x18002eb56  mov     r14, rdx
0x18002eb59  test    rcx, rcx
0x18002eb5c  jnz     short loc_18002EB96
0x18002eb5e  mov     ebx, 80070057h
0x18002eb63  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002eb68  cmp     al, 1
0x18002eb6a  jb      loc_18002ECA4
0x18002eb70  lea     edx, [rcx+2Fh]
0x18002eb73  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb7a  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x18002eb81  xor     r9d, r9d
0x18002eb84  mov     [rsp+58h+var_38], ebx
0x18002eb88  mov     rcx, [rcx+10h]
0x18002eb8c  call    WPP_SF_qD
0x18002eb91  jmp     loc_18002ECA4
0x18002eb96  test    rsi, rsi
0x18002eb99  jnz     short loc_18002EBB2
0x18002eb9b  mov     ebx, 80004003h
0x18002eba0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002eba5  cmp     al, 1
0x18002eba7  jb      loc_18002ECA4
0x18002ebad  lea     edx, [rsi+30h]
0x18002ebb0  jmp     short loc_18002EB73
0x18002ebb2  mov     qword ptr [r9], 0
0x18002ebb9  call    cs:__imp_LoadLibraryW
0x18002ebbf  mov     rdi, rax
0x18002ebc2  test    rax, rax
0x18002ebc5  jnz     short loc_18002EBF0
0x18002ebc7  call    cs:__imp_GetLastError
0x18002ebcd  mov     ebx, eax
0x18002ebcf  test    eax, eax
0x18002ebd1  jle     short loc_18002EBDC
0x18002ebd3  movzx   ebx, ax
0x18002ebd6  or      ebx, 80070000h
0x18002ebdc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002ebe1  cmp     al, 1
0x18002ebe3  jb      loc_18002ECA4
0x18002ebe9  mov     edx, 31h ; '1'
0x18002ebee  jmp     short loc_18002EB73
0x18002ebf0  lea     rdx, aDmftcreateinst; "DMFTCreateInstance"
0x18002ebf7  mov     rcx, rdi; hModule
0x18002ebfa  call    cs:__imp_GetProcAddress
0x18002ec00  test    rax, rax
0x18002ec03  jnz     short loc_18002EC2A
0x18002ec05  call    cs:__imp_GetLastError
0x18002ec0b  mov     ebx, eax
0x18002ec0d  test    eax, eax
0x18002ec0f  jle     short loc_18002EC1A
0x18002ec11  movzx   ebx, ax
0x18002ec14  or      ebx, 80070000h
0x18002ec1a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002ec1f  cmp     al, 1
0x18002ec21  jb      short loc_18002EC96
0x18002ec23  mov     edx, 32h ; '2'
0x18002ec28  jmp     short loc_18002EC78
0x18002ec2a  lea     rcx, [rsp+58h+arg_10]
0x18002ec2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec34  mov     ebx, eax
0x18002ec36  test    eax, eax
0x18002ec38  jns     short loc_18002EC4A
0x18002ec3a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002ec3f  cmp     al, 1
0x18002ec41  jb      short loc_18002EC96
0x18002ec43  mov     edx, 33h ; '3'
0x18002ec48  jmp     short loc_18002EC78
0x18002ec4a  mov     rcx, [rsp+58h+arg_10]
0x18002ec4f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002ec56  mov     r8, rsi
0x18002ec59  mov     rax, [rcx]
0x18002ec5c  mov     rax, [rax]
0x18002ec5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec64  mov     ebx, eax
0x18002ec66  test    eax, eax
0x18002ec68  jns     short loc_18002ECA1
0x18002ec6a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002ec6f  cmp     al, 1
0x18002ec71  jb      short loc_18002EC96
0x18002ec73  mov     edx, 34h ; '4'
0x18002ec78  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec7f  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x18002ec86  xor     r9d, r9d
0x18002ec89  mov     [rsp+58h+var_38], ebx
0x18002ec8d  mov     rcx, [rcx+10h]
0x18002ec91  call    WPP_SF_qD
0x18002ec96  mov     rcx, rdi; hLibModule
0x18002ec99  call    cs:__imp_FreeLibrary
0x18002ec9f  jmp     short loc_18002ECA4
0x18002eca1  mov     [r14], rdi
0x18002eca4  lea     rcx, [rsp+58h+arg_10]
0x18002eca9  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18002ecae  mov     eax, ebx
0x18002ecb0  add     rsp, 38h
0x18002ecb4  pop     r14
0x18002ecb6  pop     rdi
0x18002ecb7  pop     rsi
0x18002ecb8  pop     rbx
0x18002ecb9  retn
```
