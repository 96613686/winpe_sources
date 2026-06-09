# CReaderProxy::VerifyActive(CReader::ActiveState const *)

- ea: `0x180010994`
- end: `0x180010ae6`
- name: `?VerifyActive@CReaderProxy@@QEAAXPEBUActiveState@CReader@@@Z`
- size: `338`
- prototype: `void(CReaderProxy *__hidden this, const struct CReader::ActiveState *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004804`

## callees

- `0x18000c640`
- `0x18000fac0`
- `0x18000fb50`
- `0x180010390`
- `0x180010994`
- `0x180012380`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010a19`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010a80`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010a19`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010a80`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CReaderProxy::VerifyActive(CReaderProxy *this, const struct CReader::ActiveState *a2)
{
  char *v4; // rdi
  __int64 v5; // rbx
  __int64 pExceptionObject; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+50h] [rbp+18h] BYREF

  v4 = (char *)this + 8;
  (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 1))((char *)this + 8, 0, 0);
  if ( !*(_QWORD *)this )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    LODWORD(pExceptionObject) = -2146435049;
    throw (ulong *)&pExceptionObject;
  }
  v5 = *(_QWORD *)this + 512LL;
  v7 = v5;
  pExceptionObject = v5;
  (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v5)(v5, 0, 0);
  if ( *(LPVOID *)(v5 + 104) != TlsGetValue(dwTlsIndex) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    while ( 1 )
    {
      CAccessLock::WaitOnWriters((CAccessLock *)v5);
      pExceptionObject = v5;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v5)(v5, 0, 0);
      if ( !*(_DWORD *)(v5 + 60) || *(LPVOID *)(v5 + 104) == TlsGetValue(dwTlsIndex) )
        break;
      COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&pExceptionObject);
    }
  }
  ++*(_DWORD *)(v5 + 56);
  CAccessLock::UnsignalNoReaders((HANDLE *)v5);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  CReader::VerifyActive(*(CReader **)this, a2);
  CLockRead::~CLockRead((CLockRead *)&v7);
}

```

## disassembly

```asm
0x180010994  mov     [rsp+arg_8], rbx
0x180010999  push    rbp
0x18001099a  push    rsi
0x18001099b  push    rdi
0x18001099c  sub     rsp, 20h
0x1800109a0  mov     rbp, rdx
0x1800109a3  mov     rsi, rcx
0x1800109a6  lea     rdi, [rcx+8]
0x1800109aa  mov     rax, [rdi]
0x1800109ad  xor     r8d, r8d
0x1800109b0  xor     edx, edx
0x1800109b2  mov     rcx, rdi
0x1800109b5  mov     rax, [rax]
0x1800109b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109bd  mov     rbx, [rsi]
0x1800109c0  test    rbx, rbx
0x1800109c3  jnz     short loc_1800109EE
0x1800109c5  mov     rax, [rdi]
0x1800109c8  mov     rcx, rdi
0x1800109cb  mov     rax, [rax+8]
0x1800109cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109d4  mov     dword ptr [rsp+38h+pExceptionObject], 80100017h
0x1800109dc  lea     rdx, _TI1K; pThrowInfo
0x1800109e3  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800109e8  call    _CxxThrowException_0
0x1800109ee  add     rbx, 200h
0x1800109f5  mov     [rsp+38h+arg_10], rbx
0x1800109fa  mov     [rsp+38h+pExceptionObject], rbx
0x1800109ff  mov     rax, [rbx]
0x180010a02  xor     r8d, r8d
0x180010a05  xor     edx, edx
0x180010a07  mov     rcx, rbx
0x180010a0a  mov     rax, [rax]
0x180010a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a12  nop
0x180010a13  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180010a19  call    cs:__imp_TlsGetValue
0x180010a1f  cmp     [rbx+68h], rax
0x180010a23  jnz     short loc_180010A43
0x180010a25  inc     dword ptr [rbx+38h]
0x180010a28  mov     rcx, rbx; this
0x180010a2b  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x180010a30  nop
0x180010a31  mov     rax, [rbx]
0x180010a34  mov     rcx, rbx
0x180010a37  mov     rax, [rax+8]
0x180010a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a40  nop
0x180010a41  jmp     short loc_180010AB4
0x180010a43  mov     rax, [rbx]
0x180010a46  mov     rcx, rbx
0x180010a49  mov     rax, [rax+8]
0x180010a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a52  nop
0x180010a53  mov     rcx, rbx; this
0x180010a56  call    ?WaitOnWriters@CAccessLock@@IEAAXXZ; CAccessLock::WaitOnWriters(void)
0x180010a5b  mov     [rsp+38h+pExceptionObject], rbx
0x180010a60  mov     rax, [rbx]
0x180010a63  xor     r8d, r8d
0x180010a66  xor     edx, edx
0x180010a68  mov     rcx, rbx
0x180010a6b  mov     rax, [rax]
0x180010a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a73  nop
0x180010a74  cmp     dword ptr [rbx+3Ch], 0
0x180010a78  jz      short loc_180010A98
0x180010a7a  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180010a80  call    cs:__imp_TlsGetValue
0x180010a86  cmp     [rbx+68h], rax
0x180010a8a  jz      short loc_180010A98
0x180010a8c  lea     rcx, [rsp+38h+pExceptionObject]; this
0x180010a91  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x180010a96  jmp     short loc_180010A53
0x180010a98  inc     dword ptr [rbx+38h]
0x180010a9b  mov     rcx, rbx; this
0x180010a9e  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x180010aa3  nop
0x180010aa4  mov     rax, [rbx]
0x180010aa7  mov     rcx, rbx
0x180010aaa  mov     rax, [rax+8]
0x180010aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ab3  nop
0x180010ab4  mov     rax, [rdi]
0x180010ab7  mov     rcx, rdi
0x180010aba  mov     rax, [rax+8]
0x180010abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac3  mov     rdx, rbp; struct CReader::ActiveState *
0x180010ac6  mov     rcx, [rsi]; this
0x180010ac9  call    ?VerifyActive@CReader@@QEAAXPEBUActiveState@1@@Z; CReader::VerifyActive(CReader::ActiveState const *)
0x180010ace  nop
0x180010acf  lea     rcx, [rsp+38h+arg_10]; this
0x180010ad4  call    ??1CLockRead@@QEAA@XZ; CLockRead::~CLockRead(void)
0x180010ad9  mov     rbx, [rsp+38h+arg_8]
0x180010ade  add     rsp, 20h
0x180010ae2  pop     rdi
0x180010ae3  pop     rsi
0x180010ae4  pop     rbp
0x180010ae5  retn
```
