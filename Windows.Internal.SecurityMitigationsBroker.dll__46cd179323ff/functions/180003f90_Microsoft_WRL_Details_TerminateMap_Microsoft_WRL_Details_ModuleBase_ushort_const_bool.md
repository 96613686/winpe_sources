# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x180003f90`
- end: `0x18000409f`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `271`
- prototype: `bool __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *, bool)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003730`
- `0x1800040b0`
- `0x180004210`

## callees

- `0x180003f90`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004055`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004055`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004018`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004018`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004035`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000404c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004035`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000404c`

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
0x180003f90  push    rbx
0x180003f92  push    rbp
0x180003f93  push    rsi
0x180003f94  push    rdi
0x180003f95  push    r14
0x180003f97  push    r15
0x180003f99  sub     rsp, 28h
0x180003f9d  mov     rax, [rcx]
0x180003fa0  mov     r15b, r8b
0x180003fa3  mov     rsi, rcx
0x180003fa6  mov     rax, [rax+20h]
0x180003faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003faf  mov     rdx, [rsi]
0x180003fb2  mov     rcx, rsi
0x180003fb5  lea     rbx, [rax+8]
0x180003fb9  mov     rax, [rdx+30h]
0x180003fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fc2  mov     r14, rax
0x180003fc5  cmp     rbx, rax
0x180003fc8  jnb     loc_18000407A
0x180003fce  cmp     qword ptr [rbx], 0
0x180003fd2  jz      loc_18000406D
0x180003fd8  mov     rcx, [rsi]
0x180003fdb  mov     rax, [rcx+18h]
0x180003fdf  mov     rcx, rsi
0x180003fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fe7  test    eax, eax
0x180003fe9  jz      short loc_180003FF4
0x180003feb  test    r15b, r15b
0x180003fee  jz      loc_18000409B
0x180003ff4  mov     rax, [rbx]
0x180003ff7  mov     rcx, [rax+18h]
0x180003ffb  mov     rax, [rcx]
0x180003ffe  test    rax, rax
0x180004001  jz      short loc_18000406D
0x180004003  mov     rax, [rsi]
0x180004006  mov     rcx, rsi
0x180004009  mov     rax, [rax+38h]
0x18000400d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004012  mov     rcx, rax; SRWLock
0x180004015  mov     rdi, rax
0x180004018  call    cs:__imp_AcquireSRWLockExclusive
0x18000401e  mov     rcx, [rbx]
0x180004021  mov     rax, [rcx+18h]
0x180004025  mov     rbp, [rax]
0x180004028  test    rbp, rbp
0x18000402b  jnz     short loc_18000403D
0x18000402d  test    rdi, rdi
0x180004030  jz      short loc_18000406D
0x180004032  mov     rcx, rdi; SRWLock
0x180004035  call    cs:__imp_ReleaseSRWLockExclusive
0x18000403b  jmp     short loc_18000406D
0x18000403d  mov     qword ptr [rax], 0
0x180004044  test    rdi, rdi
0x180004047  jz      short loc_180004052
0x180004049  mov     rcx, rdi; SRWLock
0x18000404c  call    cs:__imp_ReleaseSRWLockExclusive
0x180004052  mov     rcx, rbp; Ptr
0x180004055  call    cs:__imp_DecodePointer
0x18000405b  mov     rdx, rax
0x18000405e  mov     rcx, [rax]
0x180004061  mov     rax, [rcx+10h]
0x180004065  mov     rcx, rdx
0x180004068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000406d  add     rbx, 8
0x180004071  cmp     rbx, r14
0x180004074  jb      loc_180003FCE
0x18000407a  mov     rax, [rsi]
0x18000407d  mov     rcx, rsi
0x180004080  mov     rax, [rax+18h]
0x180004084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004089  test    eax, eax
0x18000408b  setz    al
0x18000408e  add     rsp, 28h
0x180004092  pop     r15
0x180004094  pop     r14
0x180004096  pop     rdi
0x180004097  pop     rsi
0x180004098  pop     rbp
0x180004099  pop     rbx
0x18000409a  retn
0x18000409b  xor     al, al
0x18000409d  jmp     short loc_18000408E
```
