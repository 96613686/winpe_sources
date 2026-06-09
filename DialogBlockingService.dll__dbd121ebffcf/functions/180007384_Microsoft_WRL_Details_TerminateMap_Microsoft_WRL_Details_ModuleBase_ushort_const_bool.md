# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x180007384`
- end: `0x1800074d0`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `332`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003c6c`
- `0x180003cdc`
- `0x1800043e0`
- `0x180004440`
- `0x18000791c`

## callees

- `0x180007384`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007447`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007447`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007464`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000747b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007464`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000747b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007484`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007484`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Details::TerminateMap(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        const unsigned __int16 *a3)
{
  char v3; // r12
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // r15
  struct Microsoft::WRL::Details::ModuleBase *v8; // rcx
  char *v9; // r8
  int v10; // edx
  int v11; // eax
  RTL_SRWLOCK *v12; // rdi
  void **v13; // rax
  void *v14; // rbp
  PVOID v15; // rax

  v3 = (char)a3;
  v6 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 32LL))(this) + 8;
  v7 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
  if ( v6 >= v7 )
    return (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) == 0;
  while ( 1 )
  {
    if ( *(_QWORD *)v6 )
    {
      if ( !a2 )
        break;
      v8 = *(struct Microsoft::WRL::Details::ModuleBase **)(*(_QWORD *)v6 + 32LL);
      if ( v8 )
      {
        v9 = (char *)(a2 - v8);
        do
        {
          v10 = *(unsigned __int16 *)&v9[(_QWORD)v8];
          v11 = *(unsigned __int16 *)v8 - v10;
          if ( v11 )
            break;
          v8 = (struct Microsoft::WRL::Details::ModuleBase *)((char *)v8 + 2);
        }
        while ( v10 );
        if ( !v11 )
          break;
      }
    }
LABEL_18:
    v6 += 8LL;
    if ( v6 >= v7 )
      return (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) == 0;
  }
  if ( !(*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) || v3 )
  {
    if ( **(_QWORD **)(*(_QWORD *)v6 + 24LL) )
    {
      v12 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
      AcquireSRWLockExclusive(v12);
      v13 = *(void ***)(*(_QWORD *)v6 + 24LL);
      v14 = *v13;
      if ( *v13 )
      {
        *v13 = 0;
        if ( v12 )
          ReleaseSRWLockExclusive(v12);
        v15 = DecodePointer(v14);
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)v15 + 16LL))(v15);
      }
      else if ( v12 )
      {
        ReleaseSRWLockExclusive(v12);
      }
    }
    goto LABEL_18;
  }
  return 0;
}

```

## disassembly

```asm
0x180007384  push    rbx
0x180007386  push    rbp
0x180007387  push    rsi
0x180007388  push    rdi
0x180007389  push    r12
0x18000738b  push    r14
0x18000738d  push    r15
0x18000738f  sub     rsp, 20h
0x180007393  mov     r12b, r8b
0x180007396  mov     r14, rdx
0x180007399  mov     rsi, rcx
0x18000739c  mov     rax, [rcx]
0x18000739f  mov     rax, [rax+20h]
0x1800073a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073a8  lea     rbx, [rax+8]
0x1800073ac  mov     r9, [rsi]
0x1800073af  mov     rcx, rsi
0x1800073b2  mov     rax, [r9+30h]
0x1800073b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073bb  mov     r15, rax
0x1800073be  cmp     rbx, rax
0x1800073c1  jnb     loc_1800074A9
0x1800073c7  mov     rcx, [rbx]
0x1800073ca  test    rcx, rcx
0x1800073cd  jz      loc_18000749C
0x1800073d3  test    r14, r14
0x1800073d6  jz      short loc_180007407
0x1800073d8  mov     rcx, [rcx+20h]
0x1800073dc  test    rcx, rcx
0x1800073df  jz      loc_18000749C
0x1800073e5  mov     r8, r14
0x1800073e8  sub     r8, rcx
0x1800073eb  movzx   eax, word ptr [rcx]
0x1800073ee  movzx   edx, word ptr [rcx+r8]
0x1800073f3  sub     eax, edx
0x1800073f5  jnz     short loc_1800073FF
0x1800073f7  add     rcx, 2
0x1800073fb  test    edx, edx
0x1800073fd  jnz     short loc_1800073EB
0x1800073ff  test    eax, eax
0x180007401  jnz     loc_18000749C
0x180007407  mov     rax, [rsi]
0x18000740a  mov     rcx, rsi
0x18000740d  mov     rax, [rax+18h]
0x180007411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007416  test    eax, eax
0x180007418  jz      short loc_180007423
0x18000741a  test    r12b, r12b
0x18000741d  jz      loc_1800074CC
0x180007423  mov     rax, [rbx]
0x180007426  mov     rcx, [rax+18h]
0x18000742a  mov     rax, [rcx]
0x18000742d  test    rax, rax
0x180007430  jz      short loc_18000749C
0x180007432  mov     rax, [rsi]
0x180007435  mov     rcx, rsi
0x180007438  mov     rax, [rax+38h]
0x18000743c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007441  mov     rdi, rax
0x180007444  mov     rcx, rax; SRWLock
0x180007447  call    cs:__imp_AcquireSRWLockExclusive
0x18000744d  mov     rcx, [rbx]
0x180007450  mov     rax, [rcx+18h]
0x180007454  mov     rbp, [rax]
0x180007457  test    rbp, rbp
0x18000745a  jnz     short loc_18000746C
0x18000745c  test    rdi, rdi
0x18000745f  jz      short loc_18000749C
0x180007461  mov     rcx, rdi; SRWLock
0x180007464  call    cs:__imp_ReleaseSRWLockExclusive
0x18000746a  jmp     short loc_18000749C
0x18000746c  mov     qword ptr [rax], 0
0x180007473  test    rdi, rdi
0x180007476  jz      short loc_180007481
0x180007478  mov     rcx, rdi; SRWLock
0x18000747b  call    cs:__imp_ReleaseSRWLockExclusive
0x180007481  mov     rcx, rbp; Ptr
0x180007484  call    cs:__imp_DecodePointer
0x18000748a  mov     rdx, rax
0x18000748d  mov     rcx, [rax]
0x180007490  mov     rax, [rcx+10h]
0x180007494  mov     rcx, rdx
0x180007497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000749c  add     rbx, 8
0x1800074a0  cmp     rbx, r15
0x1800074a3  jb      loc_1800073C7
0x1800074a9  mov     rax, [rsi]
0x1800074ac  mov     rcx, rsi
0x1800074af  mov     rax, [rax+18h]
0x1800074b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074b8  test    eax, eax
0x1800074ba  setz    al
0x1800074bd  add     rsp, 20h
0x1800074c1  pop     r15
0x1800074c3  pop     r14
0x1800074c5  pop     r12
0x1800074c7  pop     rdi
0x1800074c8  pop     rsi
0x1800074c9  pop     rbp
0x1800074ca  pop     rbx
0x1800074cb  retn
0x1800074cc  xor     al, al
0x1800074ce  jmp     short loc_1800074BD
```
