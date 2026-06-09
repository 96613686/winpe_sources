# wil::details::ThreadFailureCallbackFn__lambda_6b1d65cd1938606b4159120d1307db23___::NotifyFailure

- ea: `0x180006810`
- end: `0x1800068bf`
- name: `wil::details::ThreadFailureCallbackFn__lambda_6b1d65cd1938606b4159120d1307db23___::NotifyFailure`
- size: `175`
- prototype: `char __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180004f20`
- `0x180006810`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000687b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006884`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000687b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006884`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800068a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800068a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006838`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006838`

## pseudocode

```c
char __fastcall wil::details::ThreadFailureCallbackFn__lambda_6b1d65cd1938606b4159120d1307db23___::NotifyFailure(
        __int64 a1)
{
  RTL_SRWLOCK *v1; // rbp
  int v2; // r12d
  ProcessWatcherDesc ***Ptr; // r14
  ProcessWatcherDesc **v4; // rdi
  ProcessWatcherDesc **v5; // rsi
  ProcessWatcherDesc *v6; // rdx
  ProcessWatcherDesc **v7; // r15
  ProcessWatcherDesc *v8; // rsi

  v1 = *(RTL_SRWLOCK **)(a1 + 56);
  v2 = **(_DWORD **)(a1 + 64);
  AcquireSRWLockExclusive(v1 + 13);
  Ptr = (ProcessWatcherDesc ***)v1[11].Ptr;
  v4 = *Ptr;
  while ( v4 != (ProcessWatcherDesc **)Ptr )
  {
    v5 = v4 + 2;
    if ( *((_DWORD *)v4[2] + 12) == v2 )
    {
      v6 = v4[1];
      v7 = v4;
      v4 = (ProcessWatcherDesc **)*v4;
      *(_QWORD *)v6 = v4;
      v4[1] = v6;
      v8 = *v5;
      if ( v8 )
      {
        ProcessWatcherDesc::~ProcessWatcherDesc(v8, (__int64)v6);
        operator delete(v8);
      }
      operator delete(v7);
      --v1[12].Ptr;
    }
    else
    {
      v4 = (ProcessWatcherDesc **)*v4;
    }
  }
  if ( v1 != (RTL_SRWLOCK *)-104LL )
    ReleaseSRWLockExclusive(v1 + 13);
  return 0;
}

```

## disassembly

```asm
0x180006810  mov     [rsp+arg_8], rbx
0x180006815  mov     [rsp+arg_10], rbp
0x18000681a  push    rsi
0x18000681b  push    rdi
0x18000681c  push    r12
0x18000681e  push    r14
0x180006820  push    r15
0x180006822  sub     rsp, 20h
0x180006826  mov     rbp, [rcx+38h]
0x18000682a  mov     rax, [rcx+40h]
0x18000682e  lea     rbx, [rbp+68h]
0x180006832  mov     r12d, [rax]
0x180006835  mov     rcx, rbx; SRWLock
0x180006838  call    cs:__imp_AcquireSRWLockExclusive
0x18000683e  mov     r14, [rbp+58h]
0x180006842  mov     rdi, [r14]
0x180006845  jmp     short loc_180006893
0x180006847  lea     rsi, [rdi+10h]
0x18000684b  mov     rax, [rsi]
0x18000684e  cmp     [rax+30h], r12d
0x180006852  jnz     short loc_180006890
0x180006854  mov     rdx, [rdi+8]
0x180006858  mov     r15, rdi
0x18000685b  mov     rax, [rdi]
0x18000685e  mov     rdi, rax
0x180006861  mov     [rdx], rax
0x180006864  mov     [rax+8], rdx
0x180006868  mov     rsi, [rsi]
0x18000686b  test    rsi, rsi
0x18000686e  jz      short loc_180006881
0x180006870  mov     rcx, rsi; this
0x180006873  call    ??1ProcessWatcherDesc@@QEAA@XZ; ProcessWatcherDesc::~ProcessWatcherDesc(void)
0x180006878  mov     rcx, rsi
0x18000687b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006881  mov     rcx, r15
0x180006884  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000688a  dec     qword ptr [rbp+60h]
0x18000688e  jmp     short loc_180006893
0x180006890  mov     rdi, [rdi]
0x180006893  cmp     rdi, r14
0x180006896  jnz     short loc_180006847
0x180006898  test    rbx, rbx
0x18000689b  jz      short loc_1800068A6
0x18000689d  mov     rcx, rbx; SRWLock
0x1800068a0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800068a6  mov     rbx, [rsp+48h+arg_8]
0x1800068ab  xor     al, al
0x1800068ad  mov     rbp, [rsp+48h+arg_10]
0x1800068b2  add     rsp, 20h
0x1800068b6  pop     r15
0x1800068b8  pop     r14
0x1800068ba  pop     r12
0x1800068bc  pop     rdi
0x1800068bd  pop     rsi
0x1800068be  retn
```
