# AddReaderDriver(ushort const *,ulong)

- ea: `0x18002c850`
- end: `0x18002cb31`
- name: `?AddReaderDriver@@YAKPEBGK@Z`
- size: `737`
- prototype: `__int64 __fastcall(LPCWSTR lpString1, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops`

## callees

- `0x1800016c0`
- `0x1800022b0`
- `0x180010670`
- `0x180014180`
- `0x180014450`
- `0x180014dc0`
- `0x180019bc4`
- `0x18001c330`
- `0x180029f78`
- `0x18002c668`
- `0x18002c7dc`
- `0x18002c850`
- `0x18002cd58`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c89e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c89e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AddReaderDriver(LPCWSTR lpString1, unsigned int a2)
{
  char *FileW; // r15
  DWORD LastError; // edi
  const unsigned __int8 *v6; // rcx
  unsigned __int16 *v7; // rcx
  const unsigned __int8 *v9; // rcx
  unsigned __int16 *v10; // rcx
  CReaderDriver *v11; // rax
  const unsigned __int8 *v12; // rcx
  const unsigned __int16 *v13; // r9
  CReaderDriver *v14; // rdi
  unsigned __int16 *v15; // rcx
  const unsigned __int8 *v16; // rcx
  const unsigned __int16 *v17; // r9
  unsigned __int16 *v18; // rcx
  unsigned int v19; // eax
  unsigned __int16 *v20; // rcx
  const unsigned __int16 *dwCreationDisposition; // [rsp+20h] [rbp-88h]
  ulong pExceptionObject; // [rsp+40h] [rbp-68h] BYREF
  CReaderDriver *v23; // [rsp+48h] [rbp-60h]
  char *v24; // [rsp+50h] [rbp-58h] BYREF
  DWORD v25; // [rsp+58h] [rbp-50h]
  unsigned __int16 **v26; // [rsp+60h] [rbp-48h] BYREF
  unsigned __int16 *v27; // [rsp+68h] [rbp-40h] BYREF
  char v28; // [rsp+70h] [rbp-38h]
  unsigned __int16 *v29; // [rsp+C8h] [rbp+20h] BYREF

  v24 = 0;
  v29 = 0;
  FileW = (char *)CreateFileW(lpString1, 0xC0000000, 0, 0, 3u, 0x40000000u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v25 = LastError;
  }
  else
  {
    LastError = 0;
    v25 = 0;
  }
  if ( (unsigned int)CHandleObject::IsValid((CHandleObject *)&v24) )
  {
    CHandleObject::Close((CHandleObject *)&v24);
    LastError = v25;
  }
  v24 = FileW;
  if ( !(unsigned int)CHandleObject::IsValid((CHandleObject *)&v24) )
  {
    if ( LastError != 1200 && LastError != 20 && LastError != 2 )
      CalaisError(v6, 0x25Au, LastError, 0, 0, 0);
    v7 = v29;
    v29 = 0;
    if ( v7 )
      ConstStringHeapFree(v7);
LABEL_13:
    CHandleObject::~CHandleObject((CHandleObject *)&v24);
    return LastError;
  }
  v26 = &v29;
  v27 = 0;
  v28 = 1;
  LastError = GetDeviceInstanceIdFromDeviceId(lpString1, &v27);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v26);
  if ( LastError )
  {
    CalaisError(v9, 0x263u, LastError, 0, 0, 0);
    v10 = v29;
    v29 = 0;
    if ( v10 )
      ConstStringHeapFree(v10);
    goto LABEL_13;
  }
  v11 = (CReaderDriver *)operator new(0x398u);
  v23 = v11;
  if ( v11 )
    v14 = CReaderDriver::CReaderDriver(v11, FileW, lpString1, v29, a2);
  else
    v14 = 0;
  if ( !v14 )
  {
    CalaisError(v12, 0x25Bu, lpString1, v13, dwCreationDisposition);
    v15 = v29;
    v29 = 0;
    if ( v15 )
      ConstStringHeapFree(v15);
LABEL_24:
    CHandleObject::~CHandleObject((CHandleObject *)&v24);
    return 2148532230LL;
  }
  if ( (unsigned int)CReader::InitFailed(v14) )
  {
    CalaisError(v16, 0x263u, 0, v17, dwCreationDisposition);
    (**(void (__fastcall ***)(CReaderDriver *, __int64))v14)(v14, 1);
    v18 = v29;
    v29 = 0;
    if ( v18 )
      ConstStringHeapFree(v18);
    goto LABEL_24;
  }
  v24 = 0;
  (*(void (__fastcall **)(CReaderDriver *))(*(_QWORD *)v14 + 8LL))(v14);
  v19 = CalaisAddReader(v14);
  if ( v19 )
  {
    pExceptionObject = v19;
    throw &pExceptionObject;
  }
  v20 = v29;
  v29 = 0;
  if ( v20 )
    ConstStringHeapFree(v20);
  CHandleObject::~CHandleObject((CHandleObject *)&v24);
  return 0;
}

```

## disassembly

```asm
0x18002c850  mov     rax, rsp
0x18002c853  mov     [rax+8], rbx
0x18002c857  push    rsi
0x18002c858  push    rdi
0x18002c859  push    r12
0x18002c85b  push    r14
0x18002c85d  push    r15
0x18002c85f  sub     rsp, 80h
0x18002c866  mov     r12d, edx
0x18002c869  mov     r14, rcx
0x18002c86c  xor     ebx, ebx
0x18002c86e  mov     [rax-58h], rbx
0x18002c872  mov     [rsp+0A8h+arg_10], rbx
0x18002c87a  mov     esi, ebx
0x18002c87c  mov     [rax+20h], rbx
0x18002c880  mov     [rax-78h], rbx
0x18002c884  mov     dword ptr [rax-80h], 40000000h
0x18002c88b  mov     [rsp+0A8h+dwCreationDisposition], 3; unsigned __int16 *
0x18002c893  xor     r9d, r9d; lpSecurityAttributes
0x18002c896  xor     r8d, r8d; dwShareMode
0x18002c899  mov     edx, 0C0000000h; dwDesiredAccess
0x18002c89e  call    cs:__imp_CreateFileW
0x18002c8a4  mov     r15, rax
0x18002c8a7  dec     rax
0x18002c8aa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c8ae  ja      short loc_18002C8B8
0x18002c8b0  mov     edi, ebx
0x18002c8b2  mov     [rsp+0A8h+var_50], ebx
0x18002c8b6  jmp     short loc_18002C8C4
0x18002c8b8  call    cs:__imp_GetLastError
0x18002c8be  mov     edi, eax
0x18002c8c0  mov     [rsp+0A8h+var_50], eax
0x18002c8c4  lea     rcx, [rsp+0A8h+var_58]; this
0x18002c8c9  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002c8ce  test    eax, eax
0x18002c8d0  jz      short loc_18002C8E0
0x18002c8d2  lea     rcx, [rsp+0A8h+var_58]; this
0x18002c8d7  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x18002c8dc  mov     edi, [rsp+0A8h+var_50]
0x18002c8e0  mov     [rsp+0A8h+var_58], r15
0x18002c8e5  lea     rcx, [rsp+0A8h+var_58]; this
0x18002c8ea  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002c8ef  test    eax, eax
0x18002c8f1  jnz     short loc_18002C94C
0x18002c8f3  cmp     edi, 4B0h
0x18002c8f9  jz      short loc_18002C920
0x18002c8fb  cmp     edi, 14h
0x18002c8fe  jz      short loc_18002C920
0x18002c900  cmp     edi, 2
0x18002c903  jz      short loc_18002C920
0x18002c905  mov     [rsp+0A8h+var_80], rbx; unsigned __int16 *
0x18002c90a  mov     qword ptr [rsp+0A8h+dwCreationDisposition], rbx; unsigned __int16 *
0x18002c90f  xor     r9d, r9d; unsigned __int16 *
0x18002c912  mov     r8d, edi; unsigned int
0x18002c915  mov     edx, 25Ah; unsigned int
0x18002c91a  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18002c91f  nop
0x18002c920  mov     rcx, [rsp+0A8h+arg_18]; unsigned __int16 *
0x18002c928  mov     [rsp+0A8h+arg_18], rbx
0x18002c930  test    rcx, rcx
0x18002c933  jz      short loc_18002C93B
0x18002c935  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x18002c93a  nop
0x18002c93b  lea     rcx, [rsp+0A8h+var_58]; this
0x18002c940  call    ??1CHandleObject@@QEAA@XZ; CHandleObject::~CHandleObject(void)
0x18002c945  mov     eax, edi
0x18002c947  jmp     loc_18002CB19
0x18002c94c  lea     rax, [rsp+0A8h+arg_18]
0x18002c954  mov     [rsp+0A8h+var_48], rax
0x18002c959  mov     [rsp+0A8h+var_40], rbx
0x18002c95e  mov     [rsp+0A8h+var_38], 1
0x18002c963  lea     rdx, [rsp+0A8h+var_40]; unsigned __int16 **
0x18002c968  mov     rcx, r14; lpString1
0x18002c96b  call    ?GetDeviceInstanceIdFromDeviceId@@YAKPEBGPEAPEAG@Z; GetDeviceInstanceIdFromDeviceId(ushort const *,ushort * *)
0x18002c970  mov     edi, eax
0x18002c972  lea     rcx, [rsp+0A8h+var_48]
0x18002c977  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18002c97c  test    edi, edi
0x18002c97e  jz      short loc_18002C9C7
0x18002c980  mov     [rsp+0A8h+var_80], rbx; unsigned __int16 *
0x18002c985  mov     qword ptr [rsp+0A8h+dwCreationDisposition], rbx; unsigned __int16 *
0x18002c98a  xor     r9d, r9d; unsigned __int16 *
0x18002c98d  mov     r8d, edi; unsigned int
0x18002c990  mov     edx, 263h; unsigned int
0x18002c995  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18002c99a  nop
0x18002c99b  mov     rcx, [rsp+0A8h+arg_18]; unsigned __int16 *
0x18002c9a3  mov     [rsp+0A8h+arg_18], rbx
0x18002c9ab  test    rcx, rcx
0x18002c9ae  jz      short loc_18002C9B6
0x18002c9b0  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x18002c9b5  nop
0x18002c9b6  lea     rcx, [rsp+0A8h+var_58]; this
0x18002c9bb  call    ??1CHandleObject@@QEAA@XZ; CHandleObject::~CHandleObject(void)
0x18002c9c0  mov     eax, edi
0x18002c9c2  jmp     loc_18002CB19
0x18002c9c7  mov     ecx, 398h; Size
0x18002c9cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c9d1  mov     [rsp+0A8h+var_60], rax
0x18002c9d6  test    rax, rax
0x18002c9d9  jz      short loc_18002C9FB
0x18002c9db  mov     [rsp+0A8h+dwCreationDisposition], r12d; unsigned int
0x18002c9e0  mov     r9, [rsp+0A8h+arg_18]; unsigned __int16 *
0x18002c9e8  mov     r8, r14; unsigned __int16 *
0x18002c9eb  mov     rdx, r15; void *
0x18002c9ee  mov     rcx, rax; this
0x18002c9f1  call    ??0CReaderDriver@@QEAA@PEAXPEBG1K@Z; CReaderDriver::CReaderDriver(void *,ushort const *,ushort const *,ulong)
0x18002c9f6  mov     rdi, rax
0x18002c9f9  jmp     short loc_18002C9FE
0x18002c9fb  mov     rdi, rbx
0x18002c9fe  mov     [rsp+0A8h+arg_10], rdi
0x18002ca06  test    rdi, rdi
0x18002ca09  jnz     short loc_18002CA48
0x18002ca0b  mov     r8, r14; unsigned __int16 *
0x18002ca0e  mov     edx, 25Bh; unsigned int
0x18002ca13  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x18002ca18  nop
0x18002ca19  mov     rcx, [rsp+0A8h+arg_18]; unsigned __int16 *
0x18002ca21  mov     [rsp+0A8h+arg_18], rbx
0x18002ca29  test    rcx, rcx
0x18002ca2c  jz      short loc_18002CA34
0x18002ca2e  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x18002ca33  nop
0x18002ca34  lea     rcx, [rsp+0A8h+var_58]; this
0x18002ca39  call    ??1CHandleObject@@QEAA@XZ; CHandleObject::~CHandleObject(void)
0x18002ca3e  mov     eax, 80100006h
0x18002ca43  jmp     loc_18002CB19
0x18002ca48  mov     rcx, rdi; this
0x18002ca4b  call    ?InitFailed@CReader@@QEAAHXZ; CReader::InitFailed(void)
0x18002ca50  test    eax, eax
0x18002ca52  jz      short loc_18002CAA8
0x18002ca54  xor     r8d, r8d; unsigned __int16 *
0x18002ca57  mov     edx, 263h; unsigned int
0x18002ca5c  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x18002ca61  mov     rax, [rdi]
0x18002ca64  mov     edx, 1
0x18002ca69  mov     rcx, rdi
0x18002ca6c  mov     rax, [rax]
0x18002ca6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca74  mov     [rsp+0A8h+arg_10], rbx
0x18002ca7c  mov     rcx, [rsp+0A8h+arg_18]; unsigned __int16 *
0x18002ca84  mov     [rsp+0A8h+arg_18], rbx
0x18002ca8c  test    rcx, rcx
0x18002ca8f  jz      short loc_18002CA97
0x18002ca91  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x18002ca96  nop
0x18002ca97  lea     rcx, [rsp+0A8h+var_58]; this
0x18002ca9c  call    ??1CHandleObject@@QEAA@XZ; CHandleObject::~CHandleObject(void)
0x18002caa1  mov     eax, 80100006h
0x18002caa6  jmp     short loc_18002CB19
0x18002caa8  mov     [rsp+0A8h+var_58], rbx
0x18002caad  mov     rax, [rdi]
0x18002cab0  mov     rcx, rdi
0x18002cab3  mov     rax, [rax+8]
0x18002cab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cabc  mov     rcx, rdi; struct CReader *
0x18002cabf  call    ?CalaisAddReader@@YAKPEAVCReader@@@Z; CalaisAddReader(CReader *)
0x18002cac4  test    eax, eax
0x18002cac6  jz      short loc_18002CADD
0x18002cac8  mov     [rsp+0A8h+pExceptionObject], eax
0x18002cacc  lea     rdx, _TI1K; pThrowInfo
0x18002cad3  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18002cad8  call    _CxxThrowException_0
0x18002cadd  mov     [rsp+0A8h+arg_10], rbx
0x18002cae5  jmp     short loc_18002CAF2
0x18002cae7  jmp     short $+2
0x18002cae9  mov     esi, dword ptr [rsp+0A8h+arg_10]
0x18002caf0  xor     ebx, ebx
0x18002caf2  mov     rcx, [rsp+0A8h+arg_18]; unsigned __int16 *
0x18002cafa  mov     [rsp+0A8h+arg_18], rbx
0x18002cb02  test    rcx, rcx
0x18002cb05  jz      short loc_18002CB0D
0x18002cb07  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x18002cb0c  nop
0x18002cb0d  lea     rcx, [rsp+0A8h+var_58]; this
0x18002cb12  call    ??1CHandleObject@@QEAA@XZ; CHandleObject::~CHandleObject(void)
0x18002cb17  mov     eax, esi
0x18002cb19  mov     rbx, [rsp+0A8h+arg_0]
0x18002cb21  add     rsp, 80h
0x18002cb28  pop     r15
0x18002cb2a  pop     r14
0x18002cb2c  pop     r12
0x18002cb2e  pop     rdi
0x18002cb2f  pop     rsi
0x18002cb30  retn
```
