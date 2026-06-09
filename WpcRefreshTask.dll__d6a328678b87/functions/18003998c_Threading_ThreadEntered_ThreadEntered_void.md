# Threading::ThreadEntered::~ThreadEntered(void)

- ea: `0x18003998c`
- end: `0x180039a41`
- name: `??1ThreadEntered@Threading@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(Threading::ThreadEntered *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x1800318e0`
- `0x180046ecc`
- `0x18005f880`
- `0x1800a55be`
- `0x1800a63de`
- `0x1800a8263`

## callees

- `0x180038ffc`
- `0x18003998c`
- `0x18003bc18`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800399d0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800399e5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800399d0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800399e5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180039a0e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180039a0e`
- `api-ms-win-core-fibers-l2-1-0!ConvertFiberToThread` at `0x1800399f1`
- `api-ms-win-core-fibers-l2-1-0!ConvertFiberToThread` at `0x1800399f1`

## pseudocode

```c
void __fastcall Threading::ThreadEntered::~ThreadEntered(Threading::ThreadEntered *this, __int64 a2, int a3)
{
  int v4; // r9d
  __int64 v5; // rdx
  char *v6; // rbx
  char *v7; // rcx
  Threading::ThreadEntered *v8; // [rsp+40h] [rbp+8h] BYREF

  v4 = *((_DWORD *)this + 16);
  if ( v4
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 )
  {
    WPP_SF_DS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, a3, v4, (__int64)this);
  }
  if ( TlsGetValue(dword_1801079C8) == (char *)this + 72 )
  {
    if ( *((_BYTE *)TlsGetValue(dword_1801079C8) + 10) )
      ConvertFiberToThread();
    v8 = this;
    stdext::try_execute__lambda_44e58872765d3f65c41832ed1a0da78f___(&v8);
    TlsSetValue(dword_1801079C8, 0);
  }
  v6 = (char *)this + 88;
  v7 = (char *)*((_QWORD *)v6 + 7);
  if ( v7 )
  {
    LOBYTE(v5) = v7 != v6;
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 32LL))(v7, v5);
    *((_QWORD *)v6 + 7) = 0;
  }
}

```

## disassembly

```asm
0x18003998c  push    rbx
0x18003998e  sub     rsp, 30h
0x180039992  mov     rbx, rcx
0x180039995  mov     r9d, [rcx+40h]
0x180039999  test    r9d, r9d
0x18003999c  jz      short loc_1800399CA
0x18003999e  lea     rax, WPP_GLOBAL_Control
0x1800399a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800399ac  cmp     rcx, rax
0x1800399af  jz      short loc_1800399CA
0x1800399b1  test    byte ptr [rcx+1Ch], 10h
0x1800399b5  jz      short loc_1800399CA
0x1800399b7  mov     edx, 14h
0x1800399bc  mov     [rsp+38h+var_18], rbx
0x1800399c1  mov     rcx, [rcx+10h]
0x1800399c5  call    WPP_SF_DS
0x1800399ca  mov     ecx, cs:dword_1801079C8; dwTlsIndex
0x1800399d0  call    cs:__imp_TlsGetValue
0x1800399d6  lea     rcx, [rbx+48h]
0x1800399da  cmp     rax, rcx
0x1800399dd  jnz     short loc_180039A14
0x1800399df  mov     ecx, cs:dword_1801079C8; dwTlsIndex
0x1800399e5  call    cs:__imp_TlsGetValue
0x1800399eb  cmp     byte ptr [rax+0Ah], 0
0x1800399ef  jz      short loc_1800399F7
0x1800399f1  call    cs:__imp_ConvertFiberToThread
0x1800399f7  mov     [rsp+38h+arg_0], rbx
0x1800399fc  lea     rcx, [rsp+38h+arg_0]
0x180039a01  call    stdext__try_execute__lambda_44e58872765d3f65c41832ed1a0da78f___
0x180039a06  xor     edx, edx; lpTlsValue
0x180039a08  mov     ecx, cs:dword_1801079C8; dwTlsIndex
0x180039a0e  call    cs:__imp_TlsSetValue
0x180039a14  add     rbx, 58h ; 'X'
0x180039a18  mov     rcx, [rbx+38h]
0x180039a1c  test    rcx, rcx
0x180039a1f  jz      short loc_180039A3B
0x180039a21  mov     rax, [rcx]
0x180039a24  cmp     rcx, rbx
0x180039a27  setnz   dl
0x180039a2a  mov     rax, [rax+20h]
0x180039a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a33  mov     qword ptr [rbx+38h], 0
0x180039a3b  add     rsp, 30h
0x180039a3f  pop     rbx
0x180039a40  retn
```
