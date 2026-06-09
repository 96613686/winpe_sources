# CReaderProxy::Disconnect(CReader::ActiveState *,ulong,ulong *)

- ea: `0x1800106f0`
- end: `0x180010860`
- name: `?Disconnect@CReaderProxy@@QEAAXPEAUActiveState@CReader@@KPEAK@Z`
- size: `368`
- prototype: `void __fastcall(CReaderProxy *this, struct CReader::ActiveState *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180006030`

## callees

- `0x18000c640`
- `0x18000fac0`
- `0x18000fb50`
- `0x1800106f0`
- `0x180012380`
- `0x180018d4c`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010755`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010816`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010755`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010816`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CReaderProxy::Disconnect(
        CReaderProxy *this,
        struct CReader::ActiveState *a2,
        unsigned int a3,
        unsigned int *a4)
{
  __int64 v8; // rbx
  __int64 v9[9]; // [rsp+20h] [rbp-48h] BYREF
  __int64 pExceptionObject; // [rsp+70h] [rbp+8h] BYREF

  (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 1))((char *)this + 8, 0, 0);
  if ( !*(_QWORD *)this )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
    LODWORD(pExceptionObject) = -2146435049;
    throw (ulong *)&pExceptionObject;
  }
  v8 = *(_QWORD *)this + 512LL;
  v9[0] = v8;
  pExceptionObject = v8;
  (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v8)(v8, 0, 0);
  if ( *(LPVOID *)(v8 + 104) != TlsGetValue(dwTlsIndex) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    while ( 1 )
    {
      CAccessLock::WaitOnWriters((CAccessLock *)v8);
      pExceptionObject = v8;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v8)(v8, 0, 0);
      if ( !*(_DWORD *)(v8 + 60) || *(LPVOID *)(v8 + 104) == TlsGetValue(dwTlsIndex) )
        break;
      COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&pExceptionObject);
    }
  }
  ++*(_DWORD *)(v8 + 56);
  CAccessLock::UnsignalNoReaders((CAccessLock *)v8);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
  CReader::Disconnect(*(CReader **)this, a2, a3, a4);
  CLockRead::~CLockRead((CLockRead *)v9);
}

```

## disassembly

```asm
0x1800106f0  push    rbx
0x1800106f2  push    rbp
0x1800106f3  push    rsi
0x1800106f4  push    rdi
0x1800106f5  push    r14
0x1800106f7  push    r15
0x1800106f9  sub     rsp, 38h
0x1800106fd  mov     rbp, r9
0x180010700  mov     r14d, r8d
0x180010703  mov     r15, rdx
0x180010706  mov     rsi, rcx
0x180010709  mov     rax, [rcx+8]
0x18001070d  xor     r8d, r8d
0x180010710  xor     edx, edx
0x180010712  add     rcx, 8
0x180010716  mov     rax, [rax]
0x180010719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001071e  mov     rbx, [rsi]
0x180010721  test    rbx, rbx
0x180010724  jz      loc_180010835
0x18001072a  add     rbx, 200h
0x180010731  mov     [rsp+68h+var_48], rbx
0x180010736  mov     [rsp+68h+pExceptionObject], rbx
0x18001073b  mov     rax, [rbx]
0x18001073e  xor     r8d, r8d
0x180010741  xor     edx, edx
0x180010743  mov     rcx, rbx
0x180010746  mov     rax, [rax]
0x180010749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001074e  nop
0x18001074f  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180010755  call    cs:__imp_TlsGetValue
0x18001075b  cmp     [rbx+68h], rax
0x18001075f  jz      loc_1800107F2
0x180010765  mov     rax, [rbx]
0x180010768  mov     rcx, rbx
0x18001076b  mov     rax, [rax+8]
0x18001076f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010774  nop
0x180010775  mov     rcx, rbx; this
0x180010778  call    ?WaitOnWriters@CAccessLock@@IEAAXXZ; CAccessLock::WaitOnWriters(void)
0x18001077d  mov     [rsp+68h+pExceptionObject], rbx
0x180010782  mov     rax, [rbx]
0x180010785  xor     r8d, r8d
0x180010788  xor     edx, edx
0x18001078a  mov     rcx, rbx
0x18001078d  mov     rax, [rax]
0x180010790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010795  nop
0x180010796  cmp     dword ptr [rbx+3Ch], 0
0x18001079a  jnz     short loc_180010810
0x18001079c  inc     dword ptr [rbx+38h]
0x18001079f  mov     rcx, rbx; this
0x1800107a2  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x1800107a7  nop
0x1800107a8  mov     rax, [rbx]
0x1800107ab  mov     rcx, rbx
0x1800107ae  mov     rax, [rax+8]
0x1800107b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107b7  nop
0x1800107b8  mov     rax, [rsi+8]
0x1800107bc  lea     rcx, [rsi+8]
0x1800107c0  mov     rax, [rax+8]
0x1800107c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107c9  mov     r9, rbp; unsigned int *
0x1800107cc  mov     r8d, r14d; unsigned int
0x1800107cf  mov     rdx, r15; struct CReader::ActiveState *
0x1800107d2  mov     rcx, [rsi]; this
0x1800107d5  call    ?Disconnect@CReader@@QEAAXPEAUActiveState@1@KPEAK@Z; CReader::Disconnect(CReader::ActiveState *,ulong,ulong *)
0x1800107da  nop
0x1800107db  lea     rcx, [rsp+68h+var_48]; this
0x1800107e0  call    ??1CLockRead@@QEAA@XZ; CLockRead::~CLockRead(void)
0x1800107e5  add     rsp, 38h
0x1800107e9  pop     r15
0x1800107eb  pop     r14
0x1800107ed  pop     rdi
0x1800107ee  pop     rsi
0x1800107ef  pop     rbp
0x1800107f0  pop     rbx
0x1800107f1  retn
0x1800107f2  inc     dword ptr [rbx+38h]
0x1800107f5  mov     rcx, rbx; this
0x1800107f8  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x1800107fd  nop
0x1800107fe  mov     rax, [rbx]
0x180010801  mov     rcx, rbx
0x180010804  mov     rax, [rax+8]
0x180010808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001080d  nop
0x18001080e  jmp     short loc_1800107B8
0x180010810  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180010816  call    cs:__imp_TlsGetValue
0x18001081c  cmp     [rbx+68h], rax
0x180010820  jz      loc_18001079C
0x180010826  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18001082b  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x180010830  jmp     loc_180010775
0x180010835  mov     rax, [rsi+8]
0x180010839  lea     rcx, [rsi+8]
0x18001083d  mov     rax, [rax+8]
0x180010841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010846  mov     dword ptr [rsp+68h+pExceptionObject], 80100017h
0x18001084e  lea     rdx, _TI1K; pThrowInfo
0x180010855  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001085a  call    _CxxThrowException_0
```
