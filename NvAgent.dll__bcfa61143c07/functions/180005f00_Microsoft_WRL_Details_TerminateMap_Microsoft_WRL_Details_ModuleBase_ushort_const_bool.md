# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x180005f00`
- end: `0x18000600f`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `271`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005cd0`
- `0x180006020`

## callees

- `0x180005f00`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005fa5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005fbc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005fa5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005fbc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005f88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005f88`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005fc5`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005fc5`

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
0x180005f00  push    rbx
0x180005f02  push    rbp
0x180005f03  push    rsi
0x180005f04  push    rdi
0x180005f05  push    r14
0x180005f07  push    r15
0x180005f09  sub     rsp, 28h
0x180005f0d  mov     r15b, r8b
0x180005f10  mov     rsi, rcx
0x180005f13  mov     rax, [rcx]
0x180005f16  mov     rax, [rax+20h]
0x180005f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f1f  lea     rbx, [rax+8]
0x180005f23  mov     rdx, [rsi]
0x180005f26  mov     rcx, rsi
0x180005f29  mov     rax, [rdx+30h]
0x180005f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f32  mov     r14, rax
0x180005f35  cmp     rbx, rax
0x180005f38  jnb     loc_180005FEA
0x180005f3e  cmp     qword ptr [rbx], 0
0x180005f42  jz      loc_180005FDD
0x180005f48  mov     rcx, [rsi]
0x180005f4b  mov     rax, [rcx+18h]
0x180005f4f  mov     rcx, rsi
0x180005f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f57  test    eax, eax
0x180005f59  jz      short loc_180005F64
0x180005f5b  test    r15b, r15b
0x180005f5e  jz      loc_18000600B
0x180005f64  mov     rax, [rbx]
0x180005f67  mov     rcx, [rax+18h]
0x180005f6b  mov     rax, [rcx]
0x180005f6e  test    rax, rax
0x180005f71  jz      short loc_180005FDD
0x180005f73  mov     rax, [rsi]
0x180005f76  mov     rcx, rsi
0x180005f79  mov     rax, [rax+38h]
0x180005f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f82  mov     rdi, rax
0x180005f85  mov     rcx, rax; SRWLock
0x180005f88  call    cs:__imp_AcquireSRWLockExclusive
0x180005f8e  mov     rcx, [rbx]
0x180005f91  mov     rax, [rcx+18h]
0x180005f95  mov     rbp, [rax]
0x180005f98  test    rbp, rbp
0x180005f9b  jnz     short loc_180005FAD
0x180005f9d  test    rdi, rdi
0x180005fa0  jz      short loc_180005FDD
0x180005fa2  mov     rcx, rdi; SRWLock
0x180005fa5  call    cs:__imp_ReleaseSRWLockExclusive
0x180005fab  jmp     short loc_180005FDD
0x180005fad  mov     qword ptr [rax], 0
0x180005fb4  test    rdi, rdi
0x180005fb7  jz      short loc_180005FC2
0x180005fb9  mov     rcx, rdi; SRWLock
0x180005fbc  call    cs:__imp_ReleaseSRWLockExclusive
0x180005fc2  mov     rcx, rbp; Ptr
0x180005fc5  call    cs:__imp_DecodePointer
0x180005fcb  mov     rdx, rax
0x180005fce  mov     rcx, [rax]
0x180005fd1  mov     rax, [rcx+10h]
0x180005fd5  mov     rcx, rdx
0x180005fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fdd  add     rbx, 8
0x180005fe1  cmp     rbx, r14
0x180005fe4  jb      loc_180005F3E
0x180005fea  mov     rax, [rsi]
0x180005fed  mov     rcx, rsi
0x180005ff0  mov     rax, [rax+18h]
0x180005ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ff9  test    eax, eax
0x180005ffb  setz    al
0x180005ffe  add     rsp, 28h
0x180006002  pop     r15
0x180006004  pop     r14
0x180006006  pop     rdi
0x180006007  pop     rsi
0x180006008  pop     rbp
0x180006009  pop     rbx
0x18000600a  retn
0x18000600b  xor     al, al
0x18000600d  jmp     short loc_180005FFE
```
