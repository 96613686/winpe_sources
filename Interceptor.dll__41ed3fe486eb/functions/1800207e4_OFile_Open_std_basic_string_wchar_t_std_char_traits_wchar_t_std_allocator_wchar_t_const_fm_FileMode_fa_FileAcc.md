# OFile::Open(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,fm::FileMode,fa::FileAccess,fs::FileShare,bool)

- ea: `0x1800207e4`
- end: `0x180020a7a`
- name: `?Open@OFile@@QEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4FileMode@fm@@W4FileAccess@fa@@W4FileShare@fs@@_N@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180021610`

## callees

- `0x180003a80`
- `0x180004044`
- `0x18000ac10`
- `0x1800207e4`
- `0x180021d84`
- `0x180021e20`
- `0x1800266e0`
- `0x1800282a0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180020a3c`
- `KERNEL32!SetLastError` at `0x180020a3c`
- `KERNEL32!GetLastError` at `0x1800209d4`
- `KERNEL32!GetLastError` at `0x180020a4b`
- `KERNEL32!GetLastError` at `0x1800209d4`
- `KERNEL32!GetLastError` at `0x180020a4b`
- `KERNEL32!HeapFree` at `0x180020958`
- `KERNEL32!HeapFree` at `0x180020958`
- `KERNEL32!GetProcessHeap` at `0x18002094a`
- `KERNEL32!GetProcessHeap` at `0x18002094a`
- `KERNEL32!CloseHandle` at `0x180020a31`
- `KERNEL32!CloseHandle` at `0x180020a31`
- `KERNEL32!SetFilePointerEx` at `0x180020926`
- `KERNEL32!SetFilePointerEx` at `0x180020926`
- `KERNEL32!CreateFileW` at `0x1800208de`
- `KERNEL32!CreateFileW` at `0x1800208de`
- `KERNEL32!GetFileType` at `0x1800208f0`
- `KERNEL32!GetFileType` at `0x1800208f0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002099f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002099f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800209a6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800209a6`

## string_xrefs

- `0x180020a56`: `failed to open file '%s'`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall OFile::Open(__int64 a1, __int64 a2, int a3)
{
  DWORD dwCreationDisposition; // eax
  const WCHAR *v7; // rcx
  HANDLE v8; // rax
  __int64 v9; // rdi
  void *v10; // rdi
  HANDLE ProcessHeap; // rax
  void *v12; // rcx
  DWORD v14; // eax
  __int64 v15; // rdx
  DWORD LastError; // eax
  __int64 v17; // rdx
  LARGE_INTEGER NewFilePointer; // [rsp+40h] [rbp-C0h] BYREF
  void **v19; // [rsp+50h] [rbp-B0h]
  int v20; // [rsp+58h] [rbp-A8h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-88h]
  void *Block[2]; // [rsp+80h] [rbp-80h]
  __m128i si128; // [rsp+90h] [rbp-70h]
  int v25; // [rsp+A0h] [rbp-60h]
  _BYTE pExceptionObject[912]; // [rsp+B0h] [rbp-50h] BYREF

  v20 = 0;
  v19 = &OSecurityAttributes::`vftable';
  lpMem = 0;
  *(_OWORD *)Block = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Block[0]) = 0;
  v25 = 139;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_11;
    case 1:
      dwCreationDisposition = 2;
      break;
    case 2:
      dwCreationDisposition = 1;
      break;
    case 3:
LABEL_11:
      dwCreationDisposition = 3;
      break;
    case 4:
      dwCreationDisposition = 4;
      break;
    case 5:
      dwCreationDisposition = 5;
      break;
    default:
      OException::OException(pExceptionObject, 29, L"Unexpected 'mode' parameter");
      throw (OException *)pExceptionObject;
  }
  v7 = (const WCHAR *)a2;
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v7 = *(const WCHAR **)a2;
  v8 = CreateFileW(v7, 0x40000000u, 1u, &SecurityAttributes, dwCreationDisposition, 0x100080u, 0);
  v9 = (__int64)v8;
  if ( v8 != (HANDLE)-1LL && GetFileType(v8) != 1 )
  {
    MsoShipAssertTagProc(4773843);
    CloseHandle((HANDLE)v9);
    SetLastError(0x1Au);
    v9 = -1;
  }
  *(_QWORD *)(a1 + 48) = v9;
  if ( v9 == -1 )
  {
    LastError = GetLastError();
    OException::OException(pExceptionObject, v17, LastError, L"failed to open file '%s'", a2);
    throw (OException *)pExceptionObject;
  }
  if ( !a3 )
  {
    NewFilePointer.QuadPart = 0;
    if ( !SetFilePointerEx((HANDLE)v9, 0, &NewFilePointer, 2u) )
    {
      v14 = GetLastError();
      OException::OException(pExceptionObject, v15, v14, L"Failed to set the file pointer");
      throw (OException *)pExceptionObject;
    }
  }
  std::wstring::operator=((void *)(a1 + 16));
  v10 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v12 = Block[0];
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v12 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v12 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v12);
  }
  return 1;
}

```

## disassembly

```asm
0x1800207e4  mov     [rsp-8+arg_10], rbx
0x1800207e9  push    rbp
0x1800207ea  push    rsi
0x1800207eb  push    rdi
0x1800207ec  push    r14
0x1800207ee  push    r15
0x1800207f0  lea     rbp, [rsp-350h]
0x1800207f8  sub     rsp, 450h
0x1800207ff  mov     rax, cs:__security_cookie
0x180020806  xor     rax, rsp
0x180020809  mov     [rbp+370h+var_30], rax
0x180020810  mov     r15d, r8d
0x180020813  mov     rsi, rdx
0x180020816  mov     r14, rcx
0x180020819  lea     rax, ??_7RefCounted@@6B@; const RefCounted::`vftable'
0x180020820  mov     [rsp+470h+var_420], rax
0x180020825  xor     ebx, ebx
0x180020827  mov     [rsp+470h+var_418], ebx
0x18002082b  lea     rax, ??_7OSecurityAttributes@@6B@; const OSecurityAttributes::`vftable'
0x180020832  mov     [rsp+470h+var_420], rax
0x180020837  mov     [rsp+470h+lpMem], rbx
0x18002083c  xorps   xmm0, xmm0
0x18002083f  movups  xmmword ptr [rbp+370h+Block], xmm0
0x180020843  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002084b  movdqa  [rbp+370h+var_3E0], xmm1
0x180020850  mov     word ptr [rbp+370h+Block], bx
0x180020854  mov     [rbp+370h+var_3D0], 8Bh
0x18002085b  mov     [rsp+470h+SecurityAttributes.nLength], 18h
0x180020863  mov     [rsp+470h+SecurityAttributes.bInheritHandle], ebx
0x180020867  mov     [rsp+470h+SecurityAttributes.lpSecurityDescriptor], rbx
0x18002086c  mov     ecx, r8d
0x18002086f  test    r8d, r8d
0x180020872  jz      short loc_1800208AB
0x180020874  sub     ecx, 1
0x180020877  jz      short loc_1800208A4
0x180020879  sub     ecx, 1
0x18002087c  jz      short loc_18002089D
0x18002087e  sub     ecx, 1
0x180020881  jz      short loc_1800208AB
0x180020883  sub     ecx, 1
0x180020886  jz      short loc_180020896
0x180020888  cmp     ecx, 1
0x18002088b  jnz     loc_1800209FE
0x180020891  lea     eax, [rbx+5]
0x180020894  jmp     short loc_1800208B0
0x180020896  mov     eax, 4
0x18002089b  jmp     short loc_1800208B0
0x18002089d  mov     eax, 1
0x1800208a2  jmp     short loc_1800208B0
0x1800208a4  mov     eax, 2
0x1800208a9  jmp     short loc_1800208B0
0x1800208ab  mov     eax, 3
0x1800208b0  mov     rcx, rsi
0x1800208b3  cmp     qword ptr [rdx+18h], 7
0x1800208b8  jbe     short loc_1800208BD
0x1800208ba  mov     rcx, [rdx]; lpFileName
0x1800208bd  mov     [rsp+470h+hTemplateFile], rbx; hTemplateFile
0x1800208c2  mov     [rsp+470h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1800208ca  mov     [rsp+470h+dwCreationDisposition], eax; dwCreationDisposition
0x1800208ce  lea     r9, [rsp+470h+SecurityAttributes]; lpSecurityAttributes
0x1800208d3  mov     edx, 40000000h; dwDesiredAccess
0x1800208d8  mov     r8d, 1; dwShareMode
0x1800208de  call    cs:__imp_CreateFileW
0x1800208e4  mov     rdi, rax
0x1800208e7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800208eb  jz      short loc_1800208FF
0x1800208ed  mov     rcx, rax; hFile
0x1800208f0  call    cs:__imp_GetFileType
0x1800208f6  cmp     eax, 1
0x1800208f9  jnz     loc_180020A24
0x1800208ff  mov     [r14+30h], rdi
0x180020903  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180020907  jz      loc_180020A4B
0x18002090d  test    r15d, r15d
0x180020910  jnz     short loc_180020934
0x180020912  mov     qword ptr [rsp+470h+NewFilePointer], rbx
0x180020917  lea     r9d, [r15+2]; dwMoveMethod
0x18002091b  lea     r8, [rsp+470h+NewFilePointer]; lpNewFilePointer
0x180020920  mov     rdx, rbx; liDistanceToMove
0x180020923  mov     rcx, rdi; hFile
0x180020926  call    cs:__imp_SetFilePointerEx
0x18002092c  test    eax, eax
0x18002092e  jz      loc_1800209D4
0x180020934  lea     rcx, [r14+10h]; void *
0x180020938  mov     rdx, rsi
0x18002093b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180020940  mov     rdi, [rsp+470h+lpMem]
0x180020945  test    rdi, rdi
0x180020948  jz      short loc_18002095E
0x18002094a  call    cs:__imp_GetProcessHeap
0x180020950  mov     r8, rdi; lpMem
0x180020953  xor     edx, edx; dwFlags
0x180020955  mov     rcx, rax; hHeap
0x180020958  call    cs:__imp_HeapFree
0x18002095e  mov     rax, qword ptr [rbp+370h+var_3E0+8]
0x180020962  cmp     rax, 7
0x180020966  jbe     short loc_1800209AC
0x180020968  mov     rcx, [rbp+370h+Block]; Block
0x18002096c  mov     rdx, rcx
0x18002096f  lea     rax, ds:2[rax*2]
0x180020977  cmp     rax, 1000h
0x18002097d  jb      short loc_1800209A6
0x18002097f  mov     rcx, [rcx-8]
0x180020983  sub     rdx, rcx
0x180020986  lea     rax, [rdx-8]
0x18002098a  cmp     rax, 1Fh
0x18002098e  jbe     short loc_1800209A6
0x180020990  mov     qword ptr [rsp+470h+dwCreationDisposition], rbx; Reserved
0x180020995  xor     r9d, r9d; LineNo
0x180020998  xor     r8d, r8d; FileName
0x18002099b  xor     edx, edx; FunctionName
0x18002099d  xor     ecx, ecx; Expression
0x18002099f  call    cs:__imp__invoke_watson
0x1800209a6  call    cs:__imp_free
0x1800209ac  mov     al, 1
0x1800209ae  mov     rcx, [rbp+370h+var_30]
0x1800209b5  xor     rcx, rsp; StackCookie
0x1800209b8  call    __security_check_cookie
0x1800209bd  mov     rbx, [rsp+470h+arg_10]
0x1800209c5  add     rsp, 450h
0x1800209cc  pop     r15
0x1800209ce  pop     r14
0x1800209d0  pop     rdi
0x1800209d1  pop     rsi
0x1800209d2  pop     rbp
0x1800209d3  retn
0x1800209d4  call    cs:__imp_GetLastError
0x1800209da  mov     r8d, eax
0x1800209dd  lea     r9, aFailedToSetThe; "Failed to set the file pointer"
0x1800209e4  lea     rcx, [rbp+370h+pExceptionObject]
0x1800209e8  call    ??$?0$0BP@@OException@@QEAA@W4exceptionType@et@@IAEAY0BP@$$CB_W@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[31])
0x1800209ed  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x1800209f4  lea     rcx, [rbp+370h+pExceptionObject]; pExceptionObject
0x1800209f8  call    _CxxThrowException
0x1800209fe  lea     r8, aUnexpectedMode; "Unexpected 'mode' parameter"
0x180020a05  mov     edx, 1Dh
0x180020a0a  lea     rcx, [rbp+370h+pExceptionObject]
0x180020a0e  call    ??$?0$0BM@@OException@@QEAA@W4exceptionType@et@@AEAY0BM@$$CB_W@Z; OException::OException(et::exceptionType,wchar_t const (&)[28])
0x180020a13  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180020a1a  lea     rcx, [rbp+370h+pExceptionObject]; pExceptionObject
0x180020a1e  call    _CxxThrowException
0x180020a24  mov     ecx, 48D7D3h
0x180020a29  call    MsoShipAssertTagProc
0x180020a2e  mov     rcx, rdi; hObject
0x180020a31  call    cs:__imp_CloseHandle
0x180020a37  mov     ecx, 1Ah; dwErrCode
0x180020a3c  call    cs:__imp_SetLastError
0x180020a42  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180020a46  jmp     loc_1800208FF
0x180020a4b  call    cs:__imp_GetLastError
0x180020a51  mov     qword ptr [rsp+470h+dwCreationDisposition], rsi
0x180020a56  lea     r9, aFailedToOpenFi; "failed to open file '%s'"
0x180020a5d  mov     r8d, eax
0x180020a60  lea     rcx, [rbp+370h+pExceptionObject]
0x180020a64  call    ??$?0$0BJ@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@OException@@QEAA@W4exceptionType@et@@IAEAY0BJ@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[25],std::wstring const &)
0x180020a69  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180020a70  lea     rcx, [rbp+370h+pExceptionObject]; pExceptionObject
0x180020a74  call    _CxxThrowException
```
