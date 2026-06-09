# CReader::ActivityHash(void)

- ea: `0x180009230`
- end: `0x18000940c`
- name: `?ActivityHash@CReader@@QEAAGXZ`
- size: `476`
- prototype: `__int64 __fastcall(CReader *this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009b30`

## callees

- `0x180009230`
- `0x18000c870`
- `0x18000fb50`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800092db`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800092db`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009337`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009262`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000928c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800093af`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009262`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000928c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800093af`

## pseudocode

```c
__int64 __fastcall CReader::ActivityHash(CReader *this)
{
  char *v2; // rbx
  __int64 v3; // rdi
  LPVOID Value; // rsi
  unsigned int v5; // eax
  unsigned __int16 v6; // di
  bool v7; // zf
  char *pExceptionObject; // [rsp+40h] [rbp+8h] BYREF
  char *v10; // [rsp+48h] [rbp+10h]

  v2 = (char *)this + 56;
  pExceptionObject = (char *)this + 56;
  (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 7))((char *)this + 56, 0, 0);
  if ( *((LPVOID *)v2 + 13) == TlsGetValue(dwTlsIndex) )
  {
    ++*((_DWORD *)v2 + 14);
    CAccessLock::UnsignalNoReaders((CAccessLock *)v2);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  }
  else
  {
    do
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
      v3 = *((_QWORD *)v2 + 11);
      Value = TlsGetValue(dword_18004B240);
      while ( 1 )
      {
        v5 = WaitForAnyObject(0xFFFFFFFF, v3, Value, 0);
        if ( v5 == 1 )
          break;
        if ( v5 == 2 )
        {
          LODWORD(pExceptionObject) = -2146435070;
          throw (ulong *)&pExceptionObject;
        }
      }
      v10 = v2;
      (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v2)(v2, 0, 0);
    }
    while ( *((_DWORD *)v2 + 15) && *((LPVOID *)v2 + 13) != TlsGetValue(dwTlsIndex) );
    ++*((_DWORD *)v2 + 14);
    if ( !ResetEvent(*((HANDLE *)v2 + 9)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  }
  v6 = *((_WORD *)this + 98) + *((_WORD *)this + 100);
  if ( !(*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
  {
    (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v2)(v2, 0, 0);
    v7 = (*((_DWORD *)v2 + 14))-- == 1;
    if ( v7 && !SetEvent(*((HANDLE *)v2 + 9)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  }
  return v6;
}

```

## disassembly

```asm
0x180009230  mov     [rsp+arg_10], rbx
0x180009235  push    rbp
0x180009236  push    rsi
0x180009237  push    rdi
0x180009238  sub     rsp, 20h
0x18000923c  mov     rbp, rcx
0x18000923f  lea     rbx, [rcx+38h]
0x180009243  mov     [rsp+38h+pExceptionObject], rbx
0x180009248  mov     rax, [rbx]
0x18000924b  xor     r8d, r8d
0x18000924e  xor     edx, edx
0x180009250  mov     rcx, rbx
0x180009253  mov     rax, [rax]
0x180009256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000925b  nop
0x18000925c  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180009262  call    cs:__imp_TlsGetValue
0x180009268  cmp     [rbx+68h], rax
0x18000926c  jz      loc_180009388
0x180009272  mov     rax, [rbx]
0x180009275  mov     rcx, rbx
0x180009278  mov     rax, [rax+8]
0x18000927c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009281  nop
0x180009282  mov     rdi, [rbx+58h]
0x180009286  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000928c  call    cs:__imp_TlsGetValue
0x180009292  mov     rsi, rax
0x180009295  xor     r9d, r9d
0x180009298  mov     r8, rsi
0x18000929b  mov     rdx, rdi
0x18000929e  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x1800092a3  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x1800092a8  cmp     eax, 1
0x1800092ab  jnz     loc_180009365
0x1800092b1  mov     [rsp+38h+arg_8], rbx
0x1800092b6  mov     rax, [rbx]
0x1800092b9  xor     r8d, r8d
0x1800092bc  xor     edx, edx
0x1800092be  mov     rcx, rbx
0x1800092c1  mov     rax, [rax]
0x1800092c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092c9  nop
0x1800092ca  cmp     dword ptr [rbx+3Ch], 0
0x1800092ce  jnz     loc_1800093A9
0x1800092d4  inc     dword ptr [rbx+38h]
0x1800092d7  mov     rcx, [rbx+48h]; hEvent
0x1800092db  call    cs:__imp_ResetEvent
0x1800092e1  test    eax, eax
0x1800092e3  jz      loc_1800093D4
0x1800092e9  mov     rax, [rbx]
0x1800092ec  mov     rcx, rbx
0x1800092ef  mov     rax, [rax+8]
0x1800092f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092f8  nop
0x1800092f9  movzx   edi, word ptr [rbp+0C8h]
0x180009300  add     di, [rbp+0C4h]
0x180009307  mov     rax, [rbx]
0x18000930a  mov     rcx, rbx
0x18000930d  mov     rax, [rax+10h]
0x180009311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009316  test    eax, eax
0x180009318  jnz     short loc_180009355
0x18000931a  mov     rax, [rbx]
0x18000931d  xor     r8d, r8d
0x180009320  xor     edx, edx
0x180009322  mov     rcx, rbx
0x180009325  mov     rax, [rax]
0x180009328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000932d  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x180009331  jnz     short loc_180009345
0x180009333  mov     rcx, [rbx+48h]; hEvent
0x180009337  call    cs:__imp_SetEvent
0x18000933d  test    eax, eax
0x18000933f  jz      loc_1800093F0
0x180009345  mov     rax, [rbx]
0x180009348  mov     rcx, rbx
0x18000934b  mov     rax, [rax+8]
0x18000934f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009354  nop
0x180009355  movzx   eax, di
0x180009358  mov     rbx, [rsp+38h+arg_10]
0x18000935d  add     rsp, 20h
0x180009361  pop     rdi
0x180009362  pop     rsi
0x180009363  pop     rbp
0x180009364  retn
0x180009365  cmp     eax, 2
0x180009368  jnz     loc_180009295
0x18000936e  mov     dword ptr [rsp+38h+pExceptionObject], 80100002h
0x180009376  lea     rdx, _TI1K; pThrowInfo
0x18000937d  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180009382  call    _CxxThrowException_0
0x180009388  inc     dword ptr [rbx+38h]
0x18000938b  mov     rcx, rbx; this
0x18000938e  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x180009393  nop
0x180009394  mov     rax, [rbx]
0x180009397  mov     rcx, rbx
0x18000939a  mov     rax, [rax+8]
0x18000939e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093a3  nop
0x1800093a4  jmp     loc_1800092F9
0x1800093a9  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800093af  call    cs:__imp_TlsGetValue
0x1800093b5  cmp     [rbx+68h], rax
0x1800093b9  jz      loc_1800092D4
0x1800093bf  mov     rax, [rbx]
0x1800093c2  mov     rcx, rbx
0x1800093c5  mov     rax, [rax+8]
0x1800093c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093ce  nop
0x1800093cf  jmp     loc_180009282
0x1800093d4  call    cs:__imp_GetLastError
0x1800093da  mov     dword ptr [rsp+38h+pExceptionObject], eax
0x1800093de  lea     rdx, _TI1K; pThrowInfo
0x1800093e5  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800093ea  call    _CxxThrowException_0
0x1800093f0  call    cs:__imp_GetLastError
0x1800093f6  mov     dword ptr [rsp+38h+pExceptionObject], eax
0x1800093fa  lea     rdx, _TI1K; pThrowInfo
0x180009401  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180009406  call    _CxxThrowException_0
```
