# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x180006ca4`
- end: `0x180006db3`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `271`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006830`
- `0x180006dc0`
- `0x180006f28`

## callees

- `0x180006ca4`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006d49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006d60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006d49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006d60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006d2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006d2c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006d69`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006d69`

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
0x180006ca4  push    rbx
0x180006ca6  push    rbp
0x180006ca7  push    rsi
0x180006ca8  push    rdi
0x180006ca9  push    r14
0x180006cab  push    r15
0x180006cad  sub     rsp, 28h
0x180006cb1  mov     r15b, r8b
0x180006cb4  mov     rsi, rcx
0x180006cb7  mov     rax, [rcx]
0x180006cba  mov     rax, [rax+20h]
0x180006cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cc3  lea     rbx, [rax+8]
0x180006cc7  mov     rdx, [rsi]
0x180006cca  mov     rcx, rsi
0x180006ccd  mov     rax, [rdx+30h]
0x180006cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cd6  mov     r14, rax
0x180006cd9  cmp     rbx, rax
0x180006cdc  jnb     loc_180006D8E
0x180006ce2  cmp     qword ptr [rbx], 0
0x180006ce6  jz      loc_180006D81
0x180006cec  mov     rcx, [rsi]
0x180006cef  mov     rax, [rcx+18h]
0x180006cf3  mov     rcx, rsi
0x180006cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cfb  test    eax, eax
0x180006cfd  jz      short loc_180006D08
0x180006cff  test    r15b, r15b
0x180006d02  jz      loc_180006DAF
0x180006d08  mov     rax, [rbx]
0x180006d0b  mov     rcx, [rax+18h]
0x180006d0f  mov     rax, [rcx]
0x180006d12  test    rax, rax
0x180006d15  jz      short loc_180006D81
0x180006d17  mov     rax, [rsi]
0x180006d1a  mov     rcx, rsi
0x180006d1d  mov     rax, [rax+38h]
0x180006d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d26  mov     rdi, rax
0x180006d29  mov     rcx, rax; SRWLock
0x180006d2c  call    cs:__imp_AcquireSRWLockExclusive
0x180006d32  mov     rcx, [rbx]
0x180006d35  mov     rax, [rcx+18h]
0x180006d39  mov     rbp, [rax]
0x180006d3c  test    rbp, rbp
0x180006d3f  jnz     short loc_180006D51
0x180006d41  test    rdi, rdi
0x180006d44  jz      short loc_180006D81
0x180006d46  mov     rcx, rdi; SRWLock
0x180006d49  call    cs:__imp_ReleaseSRWLockExclusive
0x180006d4f  jmp     short loc_180006D81
0x180006d51  mov     qword ptr [rax], 0
0x180006d58  test    rdi, rdi
0x180006d5b  jz      short loc_180006D66
0x180006d5d  mov     rcx, rdi; SRWLock
0x180006d60  call    cs:__imp_ReleaseSRWLockExclusive
0x180006d66  mov     rcx, rbp; Ptr
0x180006d69  call    cs:__imp_DecodePointer
0x180006d6f  mov     rdx, rax
0x180006d72  mov     rcx, [rax]
0x180006d75  mov     rax, [rcx+10h]
0x180006d79  mov     rcx, rdx
0x180006d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d81  add     rbx, 8
0x180006d85  cmp     rbx, r14
0x180006d88  jb      loc_180006CE2
0x180006d8e  mov     rax, [rsi]
0x180006d91  mov     rcx, rsi
0x180006d94  mov     rax, [rax+18h]
0x180006d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d9d  test    eax, eax
0x180006d9f  setz    al
0x180006da2  add     rsp, 28h
0x180006da6  pop     r15
0x180006da8  pop     r14
0x180006daa  pop     rdi
0x180006dab  pop     rsi
0x180006dac  pop     rbp
0x180006dad  pop     rbx
0x180006dae  retn
0x180006daf  xor     al, al
0x180006db1  jmp     short loc_180006DA2
```
