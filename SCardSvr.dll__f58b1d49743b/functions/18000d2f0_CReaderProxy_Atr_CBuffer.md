# CReaderProxy::Atr(CBuffer &)

- ea: `0x18000d2f0`
- end: `0x18000d78e`
- name: `?Atr@CReaderProxy@@QEAAXAEAVCBuffer@@@Z`
- size: `1182`
- prototype: `void __fastcall(CReaderProxy *__hidden this, struct CBuffer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000f2a0`

## callees

- `0x18000c870`
- `0x18000d2f0`
- `0x18000fb50`
- `0x180023168`
- `0x180023174`
- `0x180023276`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000d3d1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000d4a8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000d3d1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000d4a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d561`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d5af`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d561`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d5af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d772`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d355`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d37f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d42f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d459`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d689`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d6b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d355`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d37f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d42f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d459`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d689`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d6b4`

## pseudocode

```c
void __fastcall CReaderProxy::Atr(CReaderProxy *this, struct CBuffer *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rsi
  LPVOID Value; // r15
  unsigned int v7; // eax
  unsigned int *v8; // rbp
  HANDLE *v9; // rdi
  void (__fastcall *v10)(_QWORD, _QWORD, _QWORD); // rsi
  LPVOID v11; // r15
  unsigned int v12; // eax
  size_t v13; // rsi
  const WCHAR *v14; // r15
  void *v15; // rbp
  void *v16; // rcx
  bool v17; // zf
  void (__fastcall **pExceptionObject)(_QWORD, _QWORD, _QWORD); // [rsp+70h] [rbp+8h] BYREF
  __int64 v19; // [rsp+80h] [rbp+18h]
  void (__fastcall **v20)(_QWORD, _QWORD, _QWORD); // [rsp+88h] [rbp+20h]

  (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 1))((char *)this + 8, 0, 0);
  if ( !*(_QWORD *)this )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
    LODWORD(pExceptionObject) = -2146435049;
    throw (ulong *)&pExceptionObject;
  }
  v4 = *(_QWORD *)this + 512LL;
  v19 = v4;
  pExceptionObject = (void (__fastcall **)(_QWORD, _QWORD, _QWORD))v4;
  (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v4)(v4, 0, 0);
  if ( *(LPVOID *)(v4 + 104) == TlsGetValue(dwTlsIndex) )
  {
    ++*(_DWORD *)(v4 + 56);
    CAccessLock::UnsignalNoReaders((CAccessLock *)v4);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  }
  else
  {
    do
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
      v5 = *(_QWORD *)(v4 + 88);
      Value = TlsGetValue(dword_18004B240);
      while ( 1 )
      {
        v7 = WaitForAnyObject(0xFFFFFFFF, v5, Value, 0);
        if ( v7 == 1 )
          break;
        if ( v7 == 2 )
        {
          LODWORD(pExceptionObject) = -2146435070;
          throw (ulong *)&pExceptionObject;
        }
      }
      v20 = (void (__fastcall **)(_QWORD, _QWORD, _QWORD))v4;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v4)(v4, 0, 0);
    }
    while ( *(_DWORD *)(v4 + 60) && *(LPVOID *)(v4 + 104) != TlsGetValue(dwTlsIndex) );
    ++*(_DWORD *)(v4 + 56);
    if ( !ResetEvent(*(HANDLE *)(v4 + 72)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
  v8 = *(unsigned int **)this;
  v9 = (HANDLE *)(v8 + 14);
  v20 = (void (__fastcall **)(_QWORD, _QWORD, _QWORD))(v8 + 14);
  pExceptionObject = (void (__fastcall **)(_QWORD, _QWORD, _QWORD))(v8 + 14);
  (**((void (__fastcall ***)(__int64, _QWORD, _QWORD))v8 + 7))((__int64)(v8 + 14), 0, 0);
  if ( *((LPVOID *)v8 + 20) == TlsGetValue(dwTlsIndex) )
  {
    ++v8[28];
    CAccessLock::UnsignalNoReaders((CAccessLock *)(v8 + 14));
    (*((void (__fastcall **)(void (__fastcall **)(_QWORD, _QWORD, _QWORD)))*v9 + 1))((void (__fastcall **)(_QWORD, _QWORD, _QWORD))v8 + 7);
  }
  else
  {
    do
    {
      (*((void (__fastcall **)(void (__fastcall **)(_QWORD, _QWORD, _QWORD)))*v9 + 1))((void (__fastcall **)(_QWORD, _QWORD, _QWORD))v8 + 7);
      v10 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD))*((_QWORD *)v8 + 18);
      v11 = TlsGetValue(dword_18004B240);
      while ( 1 )
      {
        v12 = WaitForAnyObject(0xFFFFFFFF, v10, v11, 0);
        if ( v12 == 1 )
          break;
        if ( v12 == 2 )
        {
          LODWORD(pExceptionObject) = -2146435070;
          throw (ulong *)&pExceptionObject;
        }
      }
      (*(void (__fastcall **)(unsigned int *, _QWORD, _QWORD))*v9)(v8 + 14, 0, 0);
    }
    while ( v8[29] && *((LPVOID *)v8 + 20) != TlsGetValue(dwTlsIndex) );
    ++v8[28];
    if ( !ResetEvent(*((HANDLE *)v8 + 16)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*((void (__fastcall **)(void (__fastcall **)(_QWORD, _QWORD, _QWORD)))*v9 + 1))((void (__fastcall **)(_QWORD, _QWORD, _QWORD))v8 + 7);
  }
  v13 = v8[46];
  if ( v8[47] )
    v14 = (const WCHAR *)*((_QWORD *)v8 + 22);
  else
    v14 = &Data;
  if ( *((_DWORD *)a2 + 5) >= (unsigned int)v13 )
  {
    v15 = (void *)*((_QWORD *)a2 + 1);
  }
  else
  {
    v15 = operator new[](v8[46]);
    if ( !v15 )
    {
      LODWORD(pExceptionObject) = 14;
      throw (ulong *)&pExceptionObject;
    }
    v16 = (void *)*((_QWORD *)a2 + 1);
    if ( v16 )
      operator delete[](v16);
    *((_QWORD *)a2 + 1) = v15;
    *((_DWORD *)a2 + 5) = v13;
  }
  *((_DWORD *)a2 + 4) = 0;
  if ( (_DWORD)v13 )
    memcpy_0(v15, v14, v13);
  *((_DWORD *)a2 + 4) = v13;
  if ( !(*((unsigned int (__fastcall **)(HANDLE *))*v9 + 2))(v9) )
  {
    (*(void (__fastcall **)(HANDLE *, _QWORD, _QWORD))*v9)(v9, 0, 0);
    v17 = (*((_DWORD *)v9 + 14))-- == 1;
    if ( v17 && !SetEvent(v9[9]) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*((void (__fastcall **)(HANDLE *))*v9 + 1))(v9);
  }
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4) )
  {
    (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v4)(v4, 0, 0);
    v17 = (*(_DWORD *)(v4 + 56))-- == 1;
    if ( v17 && !SetEvent(*(HANDLE *)(v4 + 72)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  }
}

```

## disassembly

```asm
0x18000d2f0  push    rbx
0x18000d2f2  push    rbp
0x18000d2f3  push    rsi
0x18000d2f4  push    rdi
0x18000d2f5  push    r12
0x18000d2f7  push    r14
0x18000d2f9  push    r15
0x18000d2fb  sub     rsp, 30h
0x18000d2ff  mov     r14, rdx
0x18000d302  mov     rbp, rcx
0x18000d305  mov     rax, [rcx+8]
0x18000d309  xor     r8d, r8d
0x18000d30c  xor     edx, edx
0x18000d30e  add     rcx, 8
0x18000d312  mov     rax, [rax]
0x18000d315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d31a  mov     rbx, [rbp+0]
0x18000d31e  test    rbx, rbx
0x18000d321  jz      loc_18000D6D9
0x18000d327  add     rbx, 200h
0x18000d32e  mov     [rsp+68h+arg_10], rbx
0x18000d336  mov     [rsp+68h+pExceptionObject], rbx
0x18000d33b  mov     rax, [rbx]
0x18000d33e  xor     r8d, r8d
0x18000d341  xor     edx, edx
0x18000d343  mov     rcx, rbx
0x18000d346  mov     rax, [rax]
0x18000d349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d34e  nop
0x18000d34f  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000d355  call    cs:__imp_TlsGetValue
0x18000d35b  cmp     [rbx+68h], rax
0x18000d35f  jz      loc_18000D637
0x18000d365  mov     rax, [rbx]
0x18000d368  mov     rcx, rbx
0x18000d36b  mov     rax, [rax+8]
0x18000d36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d374  nop
0x18000d375  mov     rsi, [rbx+58h]
0x18000d379  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000d37f  call    cs:__imp_TlsGetValue
0x18000d385  mov     r15, rax
0x18000d388  xor     r9d, r9d
0x18000d38b  mov     r8, r15
0x18000d38e  mov     rdx, rsi
0x18000d391  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x18000d396  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x18000d39b  cmp     eax, 1
0x18000d39e  jnz     loc_18000D5F1
0x18000d3a4  mov     [rsp+68h+arg_18], rbx
0x18000d3ac  mov     rax, [rbx]
0x18000d3af  xor     r8d, r8d
0x18000d3b2  xor     edx, edx
0x18000d3b4  mov     rcx, rbx
0x18000d3b7  mov     rax, [rax]
0x18000d3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3bf  nop
0x18000d3c0  cmp     dword ptr [rbx+3Ch], 0
0x18000d3c4  jnz     loc_18000D683
0x18000d3ca  inc     dword ptr [rbx+38h]
0x18000d3cd  mov     rcx, [rbx+48h]; hEvent
0x18000d3d1  call    cs:__imp_ResetEvent
0x18000d3d7  test    eax, eax
0x18000d3d9  jz      loc_18000D704
0x18000d3df  mov     rax, [rbx]
0x18000d3e2  mov     rcx, rbx
0x18000d3e5  mov     rax, [rax+8]
0x18000d3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3ee  nop
0x18000d3ef  mov     rax, [rbp+8]
0x18000d3f3  lea     rcx, [rbp+8]
0x18000d3f7  mov     rax, [rax+8]
0x18000d3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d400  mov     rbp, [rbp+0]
0x18000d404  lea     rdi, [rbp+38h]
0x18000d408  mov     [rsp+68h+arg_18], rdi
0x18000d410  mov     [rsp+68h+pExceptionObject], rdi
0x18000d415  mov     rax, [rdi]
0x18000d418  xor     r8d, r8d
0x18000d41b  xor     edx, edx
0x18000d41d  mov     rcx, rdi
0x18000d420  mov     rax, [rax]
0x18000d423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d428  nop
0x18000d429  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000d42f  call    cs:__imp_TlsGetValue
0x18000d435  cmp     [rdi+68h], rax
0x18000d439  jz      loc_18000D658
0x18000d43f  mov     rax, [rdi]
0x18000d442  mov     rcx, rdi
0x18000d445  mov     rax, [rax+8]
0x18000d449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d44e  nop
0x18000d44f  mov     rsi, [rdi+58h]
0x18000d453  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000d459  call    cs:__imp_TlsGetValue
0x18000d45f  mov     r15, rax
0x18000d462  xor     r9d, r9d
0x18000d465  mov     r8, r15
0x18000d468  mov     rdx, rsi
0x18000d46b  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x18000d470  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x18000d475  cmp     eax, 1
0x18000d478  jnz     loc_18000D614
0x18000d47e  mov     [rsp+68h+var_48], rdi
0x18000d483  mov     rax, [rdi]
0x18000d486  xor     r8d, r8d
0x18000d489  xor     edx, edx
0x18000d48b  mov     rcx, rdi
0x18000d48e  mov     rax, [rax]
0x18000d491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d496  nop
0x18000d497  cmp     dword ptr [rdi+3Ch], 0
0x18000d49b  jnz     loc_18000D6AE
0x18000d4a1  inc     dword ptr [rdi+38h]
0x18000d4a4  mov     rcx, [rdi+48h]; hEvent
0x18000d4a8  call    cs:__imp_ResetEvent
0x18000d4ae  test    eax, eax
0x18000d4b0  jz      loc_18000D720
0x18000d4b6  mov     rax, [rdi]
0x18000d4b9  mov     rcx, rdi
0x18000d4bc  mov     rax, [rax+8]
0x18000d4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4c5  nop
0x18000d4c6  mov     esi, [rbp+0B8h]
0x18000d4cc  cmp     dword ptr [rbp+0BCh], 0
0x18000d4d3  ja      loc_18000D5DC
0x18000d4d9  lea     r15, Data
0x18000d4e0  cmp     [r14+14h], esi
0x18000d4e4  jnb     loc_18000D5E8
0x18000d4ea  mov     rcx, rsi; unsigned __int64
0x18000d4ed  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d4f2  mov     rbp, rax
0x18000d4f5  test    rax, rax
0x18000d4f8  jz      loc_18000D73C
0x18000d4fe  mov     rcx, [r14+8]; Block
0x18000d502  test    rcx, rcx
0x18000d505  jnz     loc_18000D679
0x18000d50b  mov     [r14+8], rbp
0x18000d50f  mov     [r14+14h], esi
0x18000d513  mov     dword ptr [r14+10h], 0
0x18000d51b  test    esi, esi
0x18000d51d  jz      short loc_18000D52D
0x18000d51f  mov     r8, rsi; Size
0x18000d522  mov     rdx, r15; Src
0x18000d525  mov     rcx, rbp; void *
0x18000d528  call    memcpy_0
0x18000d52d  mov     [r14+10h], esi
0x18000d531  mov     rax, [rdi]
0x18000d534  mov     rcx, rdi
0x18000d537  mov     rax, [rax+10h]
0x18000d53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d540  test    eax, eax
0x18000d542  jnz     short loc_18000D57F
0x18000d544  mov     rax, [rdi]
0x18000d547  xor     r8d, r8d
0x18000d54a  xor     edx, edx
0x18000d54c  mov     rcx, rdi
0x18000d54f  mov     rax, [rax]
0x18000d552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d557  add     dword ptr [rdi+38h], 0FFFFFFFFh
0x18000d55b  jnz     short loc_18000D56F
0x18000d55d  mov     rcx, [rdi+48h]; hEvent
0x18000d561  call    cs:__imp_SetEvent
0x18000d567  test    eax, eax
0x18000d569  jz      loc_18000D756
0x18000d56f  mov     rax, [rdi]
0x18000d572  mov     rcx, rdi
0x18000d575  mov     rax, [rax+8]
0x18000d579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d57e  nop
0x18000d57f  mov     rax, [rbx]
0x18000d582  mov     rcx, rbx
0x18000d585  mov     rax, [rax+10h]
0x18000d589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d58e  test    eax, eax
0x18000d590  jnz     short loc_18000D5CD
0x18000d592  mov     rax, [rbx]
0x18000d595  xor     r8d, r8d
0x18000d598  xor     edx, edx
0x18000d59a  mov     rcx, rbx
0x18000d59d  mov     rax, [rax]
0x18000d5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5a5  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x18000d5a9  jnz     short loc_18000D5BD
0x18000d5ab  mov     rcx, [rbx+48h]; hEvent
0x18000d5af  call    cs:__imp_SetEvent
0x18000d5b5  test    eax, eax
0x18000d5b7  jz      loc_18000D772
0x18000d5bd  mov     rax, [rbx]
0x18000d5c0  mov     rcx, rbx
0x18000d5c3  mov     rax, [rax+8]
0x18000d5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5cc  nop
0x18000d5cd  add     rsp, 30h
0x18000d5d1  pop     r15
0x18000d5d3  pop     r14
0x18000d5d5  pop     r12
0x18000d5d7  pop     rdi
0x18000d5d8  pop     rsi
0x18000d5d9  pop     rbp
0x18000d5da  pop     rbx
0x18000d5db  retn
0x18000d5dc  mov     r15, [rbp+0B0h]
0x18000d5e3  jmp     loc_18000D4E0
0x18000d5e8  mov     rbp, [r14+8]
0x18000d5ec  jmp     loc_18000D513
0x18000d5f1  cmp     eax, 2
0x18000d5f4  jnz     loc_18000D388
0x18000d5fa  mov     dword ptr [rsp+68h+pExceptionObject], 80100002h
0x18000d602  lea     rdx, _TI1K; pThrowInfo
0x18000d609  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000d60e  call    _CxxThrowException_0
0x18000d614  cmp     eax, 2
0x18000d617  jnz     loc_18000D462
0x18000d61d  mov     dword ptr [rsp+68h+pExceptionObject], 80100002h
0x18000d625  lea     rdx, _TI1K; pThrowInfo
0x18000d62c  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000d631  call    _CxxThrowException_0
0x18000d637  inc     dword ptr [rbx+38h]
0x18000d63a  mov     rcx, rbx; this
0x18000d63d  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000d642  nop
0x18000d643  mov     rax, [rbx]
0x18000d646  mov     rcx, rbx
0x18000d649  mov     rax, [rax+8]
0x18000d64d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d652  nop
0x18000d653  jmp     loc_18000D3EF
0x18000d658  inc     dword ptr [rdi+38h]
0x18000d65b  mov     rcx, rdi; this
0x18000d65e  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000d663  nop
0x18000d664  mov     rax, [rdi]
0x18000d667  mov     rcx, rdi
0x18000d66a  mov     rax, [rax+8]
0x18000d66e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d673  nop
0x18000d674  jmp     loc_18000D4C6
0x18000d679  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000d67e  jmp     loc_18000D50B
0x18000d683  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000d689  call    cs:__imp_TlsGetValue
0x18000d68f  cmp     [rbx+68h], rax
0x18000d693  jz      loc_18000D3CA
0x18000d699  mov     rax, [rbx]
0x18000d69c  mov     rcx, rbx
0x18000d69f  mov     rax, [rax+8]
0x18000d6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6a8  nop
0x18000d6a9  jmp     loc_18000D375
0x18000d6ae  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000d6b4  call    cs:__imp_TlsGetValue
0x18000d6ba  cmp     [rdi+68h], rax
0x18000d6be  jz      loc_18000D4A1
0x18000d6c4  mov     rax, [rdi]
0x18000d6c7  mov     rcx, rdi
0x18000d6ca  mov     rax, [rax+8]
0x18000d6ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6d3  nop
0x18000d6d4  jmp     loc_18000D44F
0x18000d6d9  mov     rax, [rbp+8]
0x18000d6dd  lea     rcx, [rbp+8]
0x18000d6e1  mov     rax, [rax+8]
0x18000d6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6ea  mov     dword ptr [rsp+68h+pExceptionObject], 80100017h
0x18000d6f2  lea     rdx, _TI1K; pThrowInfo
0x18000d6f9  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000d6fe  call    _CxxThrowException_0
0x18000d704  call    cs:__imp_GetLastError
0x18000d70a  mov     dword ptr [rsp+68h+pExceptionObject], eax
0x18000d70e  lea     rdx, _TI1K; pThrowInfo
0x18000d715  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000d71a  call    _CxxThrowException_0
0x18000d720  call    cs:__imp_GetLastError
0x18000d726  mov     dword ptr [rsp+68h+pExceptionObject], eax
0x18000d72a  lea     rdx, _TI1K; pThrowInfo
0x18000d731  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000d736  call    _CxxThrowException_0
0x18000d73c  mov     dword ptr [rsp+68h+pExceptionObject], 0Eh
0x18000d744  lea     rdx, _TI1K; pThrowInfo
0x18000d74b  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000d750  call    _CxxThrowException_0
0x18000d756  call    cs:__imp_GetLastError
0x18000d75c  mov     dword ptr [rsp+68h+pExceptionObject], eax
0x18000d760  lea     rdx, _TI1K; pThrowInfo
0x18000d767  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000d76c  call    _CxxThrowException_0
0x18000d772  call    cs:__imp_GetLastError
0x18000d778  mov     dword ptr [rsp+68h+pExceptionObject], eax
0x18000d77c  lea     rdx, _TI1K; pThrowInfo
0x18000d783  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000d788  call    _CxxThrowException_0
```
