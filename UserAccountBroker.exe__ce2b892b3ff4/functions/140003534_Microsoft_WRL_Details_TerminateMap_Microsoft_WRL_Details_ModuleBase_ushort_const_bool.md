# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x140003534`
- end: `0x140003643`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `271`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400025dc`
- `0x140002880`
- `0x14000369c`

## callees

- `0x140003534`
- `0x140007010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400035d9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400035f0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400035d9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400035f0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400035bc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400035bc`
- `KERNEL32!DecodePointer` at `0x1400035f9`
- `KERNEL32!DecodePointer` at `0x1400035f9`

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
0x140003534  push    rbx
0x140003536  push    rbp
0x140003537  push    rsi
0x140003538  push    rdi
0x140003539  push    r14
0x14000353b  push    r15
0x14000353d  sub     rsp, 28h
0x140003541  mov     rax, [rcx]
0x140003544  mov     r15b, r8b
0x140003547  mov     rsi, rcx
0x14000354a  mov     rax, [rax+20h]
0x14000354e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003553  mov     rdx, [rsi]
0x140003556  mov     rcx, rsi
0x140003559  lea     rbx, [rax+8]
0x14000355d  mov     rax, [rdx+30h]
0x140003561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003566  mov     r14, rax
0x140003569  cmp     rbx, rax
0x14000356c  jnb     loc_14000361E
0x140003572  cmp     qword ptr [rbx], 0
0x140003576  jz      loc_140003611
0x14000357c  mov     rcx, [rsi]
0x14000357f  mov     rax, [rcx+18h]
0x140003583  mov     rcx, rsi
0x140003586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000358b  test    eax, eax
0x14000358d  jz      short loc_140003598
0x14000358f  test    r15b, r15b
0x140003592  jz      loc_14000363F
0x140003598  mov     rax, [rbx]
0x14000359b  mov     rcx, [rax+18h]
0x14000359f  mov     rax, [rcx]
0x1400035a2  test    rax, rax
0x1400035a5  jz      short loc_140003611
0x1400035a7  mov     rax, [rsi]
0x1400035aa  mov     rcx, rsi
0x1400035ad  mov     rax, [rax+38h]
0x1400035b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035b6  mov     rcx, rax; SRWLock
0x1400035b9  mov     rdi, rax
0x1400035bc  call    cs:__imp_AcquireSRWLockExclusive
0x1400035c2  mov     rcx, [rbx]
0x1400035c5  mov     rax, [rcx+18h]
0x1400035c9  mov     rbp, [rax]
0x1400035cc  test    rbp, rbp
0x1400035cf  jnz     short loc_1400035E1
0x1400035d1  test    rdi, rdi
0x1400035d4  jz      short loc_140003611
0x1400035d6  mov     rcx, rdi; SRWLock
0x1400035d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400035df  jmp     short loc_140003611
0x1400035e1  mov     qword ptr [rax], 0
0x1400035e8  test    rdi, rdi
0x1400035eb  jz      short loc_1400035F6
0x1400035ed  mov     rcx, rdi; SRWLock
0x1400035f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1400035f6  mov     rcx, rbp; Ptr
0x1400035f9  call    cs:__imp_DecodePointer
0x1400035ff  mov     rdx, rax
0x140003602  mov     rcx, [rax]
0x140003605  mov     rax, [rcx+10h]
0x140003609  mov     rcx, rdx
0x14000360c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003611  add     rbx, 8
0x140003615  cmp     rbx, r14
0x140003618  jb      loc_140003572
0x14000361e  mov     rax, [rsi]
0x140003621  mov     rcx, rsi
0x140003624  mov     rax, [rax+18h]
0x140003628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000362d  test    eax, eax
0x14000362f  setz    al
0x140003632  add     rsp, 28h
0x140003636  pop     r15
0x140003638  pop     r14
0x14000363a  pop     rdi
0x14000363b  pop     rsi
0x14000363c  pop     rbp
0x14000363d  pop     rbx
0x14000363e  retn
0x14000363f  xor     al, al
0x140003641  jmp     short loc_140003632
```
