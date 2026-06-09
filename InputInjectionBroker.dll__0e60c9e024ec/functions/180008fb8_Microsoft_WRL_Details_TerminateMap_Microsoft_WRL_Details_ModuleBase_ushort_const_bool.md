# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x180008fb8`
- end: `0x1800090c7`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `271`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008b90`
- `0x1800090d0`
- `0x180009238`

## callees

- `0x180008fb8`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000905d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009074`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000905d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009074`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009040`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009040`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000907d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000907d`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Details::TerminateMap(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        const unsigned __int16 *a3)
{
  char v3; // r15
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r14
  RTL_SRWLOCK *v7; // rdi
  void **v8; // rax
  void *v9; // rbp
  PVOID v10; // rax

  v3 = (char)a3;
  v5 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *, struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)this + 32LL))(
         this,
         a2)
     + 8;
  v6 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
  if ( v5 >= v6 )
    return (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) == 0;
  while ( !*(_QWORD *)v5 )
  {
LABEL_12:
    v5 += 8LL;
    if ( v5 >= v6 )
      return (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) == 0;
  }
  if ( !(*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) || v3 )
  {
    if ( **(_QWORD **)(*(_QWORD *)v5 + 24LL) )
    {
      v7 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
      AcquireSRWLockExclusive(v7);
      v8 = *(void ***)(*(_QWORD *)v5 + 24LL);
      v9 = *v8;
      if ( *v8 )
      {
        *v8 = 0;
        if ( v7 )
          ReleaseSRWLockExclusive(v7);
        v10 = DecodePointer(v9);
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)v10 + 16LL))(v10);
      }
      else if ( v7 )
      {
        ReleaseSRWLockExclusive(v7);
      }
    }
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x180008fb8  push    rbx
0x180008fba  push    rbp
0x180008fbb  push    rsi
0x180008fbc  push    rdi
0x180008fbd  push    r14
0x180008fbf  push    r15
0x180008fc1  sub     rsp, 28h
0x180008fc5  mov     r15b, r8b
0x180008fc8  mov     rsi, rcx
0x180008fcb  mov     rax, [rcx]
0x180008fce  mov     rax, [rax+20h]
0x180008fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fd7  lea     rbx, [rax+8]
0x180008fdb  mov     rdx, [rsi]
0x180008fde  mov     rcx, rsi
0x180008fe1  mov     rax, [rdx+30h]
0x180008fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fea  mov     r14, rax
0x180008fed  cmp     rbx, rax
0x180008ff0  jnb     loc_1800090A2
0x180008ff6  cmp     qword ptr [rbx], 0
0x180008ffa  jz      loc_180009095
0x180009000  mov     rcx, [rsi]
0x180009003  mov     rax, [rcx+18h]
0x180009007  mov     rcx, rsi
0x18000900a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000900f  test    eax, eax
0x180009011  jz      short loc_18000901C
0x180009013  test    r15b, r15b
0x180009016  jz      loc_1800090C3
0x18000901c  mov     rax, [rbx]
0x18000901f  mov     rcx, [rax+18h]
0x180009023  mov     rax, [rcx]
0x180009026  test    rax, rax
0x180009029  jz      short loc_180009095
0x18000902b  mov     rax, [rsi]
0x18000902e  mov     rcx, rsi
0x180009031  mov     rax, [rax+38h]
0x180009035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000903a  mov     rdi, rax
0x18000903d  mov     rcx, rax; SRWLock
0x180009040  call    cs:__imp_AcquireSRWLockExclusive
0x180009046  mov     rcx, [rbx]
0x180009049  mov     rax, [rcx+18h]
0x18000904d  mov     rbp, [rax]
0x180009050  test    rbp, rbp
0x180009053  jnz     short loc_180009065
0x180009055  test    rdi, rdi
0x180009058  jz      short loc_180009095
0x18000905a  mov     rcx, rdi; SRWLock
0x18000905d  call    cs:__imp_ReleaseSRWLockExclusive
0x180009063  jmp     short loc_180009095
0x180009065  mov     qword ptr [rax], 0
0x18000906c  test    rdi, rdi
0x18000906f  jz      short loc_18000907A
0x180009071  mov     rcx, rdi; SRWLock
0x180009074  call    cs:__imp_ReleaseSRWLockExclusive
0x18000907a  mov     rcx, rbp; Ptr
0x18000907d  call    cs:__imp_DecodePointer
0x180009083  mov     rdx, rax
0x180009086  mov     rcx, [rax]
0x180009089  mov     rax, [rcx+10h]
0x18000908d  mov     rcx, rdx
0x180009090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009095  add     rbx, 8
0x180009099  cmp     rbx, r14
0x18000909c  jb      loc_180008FF6
0x1800090a2  mov     rax, [rsi]
0x1800090a5  mov     rcx, rsi
0x1800090a8  mov     rax, [rax+18h]
0x1800090ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090b1  test    eax, eax
0x1800090b3  setz    al
0x1800090b6  add     rsp, 28h
0x1800090ba  pop     r15
0x1800090bc  pop     r14
0x1800090be  pop     rdi
0x1800090bf  pop     rsi
0x1800090c0  pop     rbp
0x1800090c1  pop     rbx
0x1800090c2  retn
0x1800090c3  xor     al, al
0x1800090c5  jmp     short loc_1800090B6
```
