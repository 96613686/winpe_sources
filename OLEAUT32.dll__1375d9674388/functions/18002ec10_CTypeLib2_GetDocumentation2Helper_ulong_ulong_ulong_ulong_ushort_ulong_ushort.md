# CTypeLib2::GetDocumentation2Helper(ulong,ulong,ulong,ulong,ushort * *,ulong *,ushort * *)

- ea: `0x18002ec10`
- end: `0x18002ef85`
- name: `?GetDocumentation2Helper@CTypeLib2@@QEAAJKKKKPEAPEAGPEAK0@Z`
- size: `885`
- prototype: `__int64 __fastcall(CTypeLib2 *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int16 **, unsigned int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18002e8a0`
- `0x18002e970`

## callees

- `0x18001a954`
- `0x180021dc0`
- `0x18002ec10`
- `0x18002fe08`
- `0x180030014`
- `0x18004d900`
- `0x18004dcf0`
- `0x180067d88`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18002ee20`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18002ee20`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18002ed35`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18002ed35`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002ed97`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002ed97`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002eec3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002eec3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ee62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ee62`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002ed6c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002ee32`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002ed6c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002ee32`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18002ed51`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18002ee44`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18002ee52`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18002ed51`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18002ee44`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18002ee52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ee8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eefe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ee8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eefe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ecd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ecd5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002edf5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002edf5`

## string_xrefs

- `0x18002ee58`: `DLLGetDocumentation`

## pseudocode

```c
__int64 __fastcall CTypeLib2::GetDocumentation2Helper(
        CTypeLib2 *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int16 **a6,
        unsigned int *a7,
        unsigned __int16 **a8)
{
  int v8; // edi
  unsigned __int16 **v9; // r14
  OLECHAR *v10; // r13
  int v11; // r12d
  unsigned int v12; // r15d
  __int64 v14; // rsi
  int v15; // eax
  int v16; // r15d
  __int64 (__fastcall *v17)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // r14
  HMODULE Library; // rsi
  _WORD *v19; // rsi
  unsigned __int64 v20; // rax
  UINT v21; // r14d
  _WORD *v22; // rax
  __int64 v23; // rsi
  int v24; // eax
  FARPROC ProcAddress; // rax
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v29; // [rsp+50h] [rbp-B0h]
  BSTR v30; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 **v31; // [rsp+60h] [rbp-A0h]
  unsigned int *v32; // [rsp+68h] [rbp-98h]
  unsigned __int16 **v33; // [rsp+70h] [rbp-90h]
  CHAR LibFileName[272]; // [rsp+80h] [rbp-80h] BYREF
  CHAR MultiByteStr[272]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR WideCharStr[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v8 = 0;
  v9 = a6;
  v10 = 0;
  v32 = a7;
  v11 = 0;
  v12 = a3;
  v33 = a8;
  v29 = a4;
  v14 = a2;
  v31 = a6;
  bstrString = 0;
  v30 = 0;
  if ( a2 != -1 )
  {
    if ( a8 )
    {
      v15 = CTypeLib2::BstrOfHstring(this, a2, &v30);
      v10 = v30;
      v8 = v15;
      if ( v15 < 0 )
        goto LABEL_36;
    }
    if ( !a6 || !v12 )
    {
LABEL_30:
      if ( bstrString )
        goto LABEL_33;
      goto LABEL_31;
    }
    v16 = 1;
    if ( (_DWORD)v14 == *((_DWORD *)this + 112) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
      v17 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))*((_QWORD *)this + 75);
      v11 = 1;
      if ( v17 )
      {
        Library = 0;
        goto LABEL_25;
      }
    }
    v8 = CTypeLib2::EnsureStringsReadable(this);
    if ( v8 < 0 )
      goto LABEL_33;
    if ( (unsigned int)v14 < *((_DWORD *)this + 57) )
      v19 = (_WORD *)(*((_QWORD *)this + 30) + v14);
    else
      v19 = 0;
    if ( *v19 >= 0x104u )
      goto LABEL_32;
    _o_strncpy_s(LibFileName, 260, v19 + 1, 259);
    v20 = (unsigned __int16)*v19;
    if ( v20 >= 0x104 )
      _report_rangecheckfailure();
    LibFileName[v20] = 0;
    v21 = SetErrorMode(0x8001u);
    TraceGetDocumentationDllLoad(LibFileName);
    Library = LoadLibraryExA(LibFileName, 0, 0);
    if ( (unsigned __int64)Library < 0x20 )
    {
      _o_wcsncpy_s(WideCharStr, 260, *((_QWORD *)this + 65));
      v22 = (_WORD *)IsolateFilename(WideCharStr, (*((unsigned __int16 *)this + 202) >> 3) & 1);
      if ( !v22 )
      {
LABEL_32:
        v8 = CTypeLib2::BstrOfHstring(this, v29, &bstrString);
        goto LABEL_33;
      }
      v23 = -1;
      *v22 = 0;
      v24 = WideCharToMultiByte(0, 0, WideCharStr, -1, MultiByteStr, 260, 0, 0);
      do
        ++v23;
      while ( LibFileName[v23] );
      if ( (unsigned __int64)(v23 + v24) >= 0x104
        || (_o_strcat_s(MultiByteStr, 260, LibFileName),
            Library = LoadLibraryExA(MultiByteStr, 0, 0),
            (unsigned __int64)Library < 0x20) )
      {
        SetErrorMode(v21);
        goto LABEL_32;
      }
    }
    SetErrorMode(v21);
    ProcAddress = GetProcAddress(Library, "DLLGetDocumentation");
    v17 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
    if ( !ProcAddress )
      goto LABEL_27;
    v16 = v11;
    if ( !v11 )
    {
LABEL_26:
      v8 = v17(this, 0, a5, a3, &bstrString);
      if ( v16 )
      {
LABEL_28:
        if ( v8 < 0 )
          goto LABEL_33;
        v9 = v31;
        goto LABEL_30;
      }
LABEL_27:
      FreeLibrary(Library);
      goto LABEL_28;
    }
    *((_QWORD *)this + 75) = ProcAddress;
    *((_QWORD *)this + 74) = Library;
LABEL_25:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
    v11 = 0;
    goto LABEL_26;
  }
LABEL_31:
  if ( v9 )
    goto LABEL_32;
LABEL_33:
  if ( v11 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  v12 = a3;
  v9 = v31;
LABEL_36:
  if ( v8 )
  {
    SysFreeString(bstrString);
    bstrString = 0;
    SysFreeString(v10);
    v10 = 0;
    v12 = 0;
  }
  if ( v9 )
    *v9 = bstrString;
  if ( v32 )
    *v32 = v12;
  if ( v33 )
    *v33 = v10;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002ec10  push    rbp
0x18002ec12  push    rbx
0x18002ec13  push    rsi
0x18002ec14  push    rdi
0x18002ec15  push    r12
0x18002ec17  push    r13
0x18002ec19  push    r14
0x18002ec1b  push    r15
0x18002ec1d  lea     rbp, [rsp-3C8h]
0x18002ec25  sub     rsp, 4C8h
0x18002ec2c  mov     rax, cs:__security_cookie
0x18002ec33  xor     rax, rsp
0x18002ec36  mov     [rbp+400h+var_50], rax
0x18002ec3d  mov     rax, [rbp+400h+arg_30]
0x18002ec44  xor     edi, edi
0x18002ec46  mov     r14, [rbp+400h+arg_28]
0x18002ec4d  xor     r13d, r13d
0x18002ec50  mov     [rsp+500h+var_498], rax
0x18002ec55  xor     r12d, r12d
0x18002ec58  mov     rax, [rbp+400h+arg_38]
0x18002ec5f  mov     r15d, r8d
0x18002ec62  mov     [rsp+500h+var_490], rax
0x18002ec67  mov     rbx, rcx
0x18002ec6a  mov     [rsp+500h+var_4B0], r9d
0x18002ec6f  mov     [rsp+500h+var_4C0], r8d
0x18002ec74  mov     esi, edx
0x18002ec76  mov     [rsp+500h+var_4A0], r14
0x18002ec7b  mov     [rsp+500h+bstrString], rdi
0x18002ec80  mov     [rsp+500h+var_4A8], r13
0x18002ec85  cmp     edx, 0FFFFFFFFh
0x18002ec88  jz      loc_18002EEDA
0x18002ec8e  test    rax, rax
0x18002ec91  jz      short loc_18002ECAE
0x18002ec93  lea     r8, [rsp+500h+var_4A8]; unsigned __int16 **
0x18002ec98  mov     edx, esi; unsigned int
0x18002ec9a  call    ?BstrOfHstring@CTypeLib2@@QEAAJKPEAPEAG@Z; CTypeLib2::BstrOfHstring(ulong,ushort * *)
0x18002ec9f  mov     r13, [rsp+500h+var_4A8]
0x18002eca4  mov     edi, eax
0x18002eca6  test    eax, eax
0x18002eca8  js      loc_18002EF0E
0x18002ecae  test    r14, r14
0x18002ecb1  jz      loc_18002EED2
0x18002ecb7  test    r15d, r15d
0x18002ecba  jz      loc_18002EED2
0x18002ecc0  mov     r15d, 1
0x18002ecc6  cmp     esi, [rbx+1C0h]
0x18002eccc  jnz     short loc_18002ECF1
0x18002ecce  lea     rcx, [rbx+260h]; lpCriticalSection
0x18002ecd5  call    cs:__imp_EnterCriticalSection
0x18002ecdb  mov     r14, [rbx+258h]
0x18002ece2  mov     r12d, r15d
0x18002ece5  test    r14, r14
0x18002ece8  jz      short loc_18002ECF1
0x18002ecea  xor     esi, esi
0x18002ecec  jmp     loc_18002EE86
0x18002ecf1  mov     rcx, rbx; this
0x18002ecf4  call    ?EnsureStringsReadable@CTypeLib2@@QEAAJXZ; CTypeLib2::EnsureStringsReadable(void)
0x18002ecf9  mov     edi, eax
0x18002ecfb  test    eax, eax
0x18002ecfd  js      loc_18002EEF2
0x18002ed03  cmp     esi, [rbx+0E4h]
0x18002ed09  jb      short loc_18002ED0F
0x18002ed0b  xor     esi, esi
0x18002ed0d  jmp     short loc_18002ED16
0x18002ed0f  add     rsi, [rbx+0F0h]
0x18002ed16  mov     r14d, 104h
0x18002ed1c  cmp     [rsi], r14w
0x18002ed20  jnb     loc_18002EEDF
0x18002ed26  lea     r8, [rsi+2]
0x18002ed2a  mov     edx, r14d
0x18002ed2d  lea     r9d, [r14-1]
0x18002ed31  lea     rcx, [rbp+400h+LibFileName]
0x18002ed35  call    cs:__imp__o_strncpy_s
0x18002ed3b  movzx   eax, word ptr [rsi]
0x18002ed3e  cmp     rax, r14
0x18002ed41  jnb     loc_18002EF7F
0x18002ed47  mov     ecx, 8001h; uMode
0x18002ed4c  mov     [rbp+rax+400h+LibFileName], 0
0x18002ed51  call    cs:__imp_SetErrorMode
0x18002ed57  lea     rcx, [rbp+400h+LibFileName]
0x18002ed5b  mov     r14d, eax
0x18002ed5e  call    TraceGetDocumentationDllLoad
0x18002ed63  xor     r8d, r8d; dwFlags
0x18002ed66  lea     rcx, [rbp+400h+LibFileName]; lpLibFileName
0x18002ed6a  xor     edx, edx; hFile
0x18002ed6c  call    cs:__imp_LoadLibraryExA
0x18002ed72  mov     rsi, rax
0x18002ed75  cmp     rax, 20h ; ' '
0x18002ed79  jnb     loc_18002EE4F
0x18002ed7f  mov     r8, [rbx+208h]
0x18002ed86  lea     rcx, [rbp+400h+WideCharStr]
0x18002ed8d  mov     r9d, 103h
0x18002ed93  lea     edx, [r9+1]
0x18002ed97  call    cs:__imp__o_wcsncpy_s
0x18002ed9d  movzx   edx, word ptr [rbx+194h]
0x18002eda4  lea     rcx, [rbp+400h+WideCharStr]
0x18002edab  shr     edx, 3
0x18002edae  and     edx, r15d
0x18002edb1  call    IsolateFilename
0x18002edb6  test    rax, rax
0x18002edb9  jz      loc_18002EEDF
0x18002edbf  xor     ecx, ecx; CodePage
0x18002edc1  lea     r8, [rbp+400h+WideCharStr]; lpWideCharStr
0x18002edc8  mov     [rsp+500h+lpUsedDefaultChar], rcx; lpUsedDefaultChar
0x18002edcd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002edd1  mov     [rsp+500h+lpDefaultChar], rcx; lpDefaultChar
0x18002edd6  mov     r15d, 104h
0x18002eddc  mov     [rax], cx
0x18002eddf  mov     r9d, esi; cchWideChar
0x18002ede2  lea     rax, [rbp+400h+MultiByteStr]
0x18002ede9  mov     [rsp+500h+cbMultiByte], r15d; cbMultiByte
0x18002edee  xor     edx, edx; dwFlags
0x18002edf0  mov     [rsp+500h+lpMultiByteStr], rax; lpMultiByteStr
0x18002edf5  call    cs:__imp_WideCharToMultiByte
0x18002edfb  lea     rcx, [rbp+400h+LibFileName]
0x18002edff  inc     rsi
0x18002ee02  cmp     byte ptr [rcx+rsi], 0
0x18002ee06  jnz     short loc_18002EDFF
0x18002ee08  cdqe
0x18002ee0a  add     rax, rsi
0x18002ee0d  cmp     rax, r15
0x18002ee10  jnb     short loc_18002EE41
0x18002ee12  lea     r8, [rbp+400h+LibFileName]
0x18002ee16  mov     rdx, r15
0x18002ee19  lea     rcx, [rbp+400h+MultiByteStr]
0x18002ee20  call    cs:__imp__o_strcat_s
0x18002ee26  xor     r8d, r8d; dwFlags
0x18002ee29  lea     rcx, [rbp+400h+MultiByteStr]; lpLibFileName
0x18002ee30  xor     edx, edx; hFile
0x18002ee32  call    cs:__imp_LoadLibraryExA
0x18002ee38  mov     rsi, rax
0x18002ee3b  cmp     rax, 20h ; ' '
0x18002ee3f  jnb     short loc_18002EE4F
0x18002ee41  mov     ecx, r14d; uMode
0x18002ee44  call    cs:__imp_SetErrorMode
0x18002ee4a  jmp     loc_18002EEDF
0x18002ee4f  mov     ecx, r14d; uMode
0x18002ee52  call    cs:__imp_SetErrorMode
0x18002ee58  lea     rdx, aDllgetdocument; "DLLGetDocumentation"
0x18002ee5f  mov     rcx, rsi; hModule
0x18002ee62  call    cs:__imp_GetProcAddress
0x18002ee68  mov     r14, rax
0x18002ee6b  test    rax, rax
0x18002ee6e  jz      short loc_18002EEC0
0x18002ee70  mov     r15d, r12d
0x18002ee73  test    r12d, r12d
0x18002ee76  jz      short loc_18002EE96
0x18002ee78  mov     [rbx+258h], rax
0x18002ee7f  mov     [rbx+250h], rsi
0x18002ee86  lea     rcx, [rbx+260h]; lpCriticalSection
0x18002ee8d  call    cs:__imp_LeaveCriticalSection
0x18002ee93  xor     r12d, r12d
0x18002ee96  mov     r9d, [rsp+500h+var_4C0]
0x18002ee9b  lea     rax, [rsp+500h+bstrString]
0x18002eea0  mov     r8d, [rbp+400h+arg_20]
0x18002eea7  xor     edx, edx
0x18002eea9  mov     [rsp+500h+lpMultiByteStr], rax
0x18002eeae  mov     rcx, rbx
0x18002eeb1  mov     rax, r14
0x18002eeb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eeb9  mov     edi, eax
0x18002eebb  test    r15d, r15d
0x18002eebe  jnz     short loc_18002EEC9
0x18002eec0  mov     rcx, rsi; hLibModule
0x18002eec3  call    cs:__imp_FreeLibrary
0x18002eec9  test    edi, edi
0x18002eecb  js      short loc_18002EEF2
0x18002eecd  mov     r14, [rsp+500h+var_4A0]
0x18002eed2  cmp     [rsp+500h+bstrString], 0
0x18002eed8  jnz     short loc_18002EEF2
0x18002eeda  test    r14, r14
0x18002eedd  jz      short loc_18002EEF2
0x18002eedf  mov     edx, [rsp+500h+var_4B0]; unsigned int
0x18002eee3  lea     r8, [rsp+500h+bstrString]; unsigned __int16 **
0x18002eee8  mov     rcx, rbx; this
0x18002eeeb  call    ?BstrOfHstring@CTypeLib2@@QEAAJKPEAPEAG@Z; CTypeLib2::BstrOfHstring(ulong,ushort * *)
0x18002eef0  mov     edi, eax
0x18002eef2  test    r12d, r12d
0x18002eef5  jz      short loc_18002EF04
0x18002eef7  lea     rcx, [rbx+260h]; lpCriticalSection
0x18002eefe  call    cs:__imp_LeaveCriticalSection
0x18002ef04  mov     r15d, [rsp+500h+var_4C0]
0x18002ef09  mov     r14, [rsp+500h+var_4A0]
0x18002ef0e  test    edi, edi
0x18002ef10  jz      short loc_18002EF33
0x18002ef12  mov     rcx, [rsp+500h+bstrString]; bstrString
0x18002ef17  call    SysFreeString
0x18002ef1c  mov     rcx, r13; bstrString
0x18002ef1f  mov     [rsp+500h+bstrString], 0
0x18002ef28  call    SysFreeString
0x18002ef2d  xor     r13d, r13d
0x18002ef30  xor     r15d, r15d
0x18002ef33  test    r14, r14
0x18002ef36  jz      short loc_18002EF40
0x18002ef38  mov     rax, [rsp+500h+bstrString]
0x18002ef3d  mov     [r14], rax
0x18002ef40  mov     rax, [rsp+500h+var_498]
0x18002ef45  test    rax, rax
0x18002ef48  jz      short loc_18002EF4D
0x18002ef4a  mov     [rax], r15d
0x18002ef4d  mov     rax, [rsp+500h+var_490]
0x18002ef52  test    rax, rax
0x18002ef55  jz      short loc_18002EF5A
0x18002ef57  mov     [rax], r13
0x18002ef5a  mov     eax, edi
0x18002ef5c  mov     rcx, [rbp+400h+var_50]
0x18002ef63  xor     rcx, rsp; StackCookie
0x18002ef66  call    __security_check_cookie
0x18002ef6b  add     rsp, 4C8h
0x18002ef72  pop     r15
0x18002ef74  pop     r14
0x18002ef76  pop     r13
0x18002ef78  pop     r12
0x18002ef7a  pop     rdi
0x18002ef7b  pop     rsi
0x18002ef7c  pop     rbx
0x18002ef7d  pop     rbp
0x18002ef7e  retn
0x18002ef7f  call    __report_rangecheckfailure
```
