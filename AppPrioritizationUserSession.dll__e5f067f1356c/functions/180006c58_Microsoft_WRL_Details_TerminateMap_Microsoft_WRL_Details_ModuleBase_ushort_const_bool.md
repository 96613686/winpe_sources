# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x180006c58`
- end: `0x180006d67`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `271`
- prototype: `bool __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004200`
- `0x1800073a0`

## callees

- `0x180006c58`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006ce0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006ce0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006cfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006d14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006cfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006d14`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006d1d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006d1d`

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
0x180006c58  push    rbx
0x180006c5a  push    rbp
0x180006c5b  push    rsi
0x180006c5c  push    rdi
0x180006c5d  push    r14
0x180006c5f  push    r15
0x180006c61  sub     rsp, 28h
0x180006c65  mov     r15b, r8b
0x180006c68  mov     rsi, rcx
0x180006c6b  mov     rax, [rcx]
0x180006c6e  mov     rax, [rax+20h]
0x180006c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c77  lea     rbx, [rax+8]
0x180006c7b  mov     rcx, [rsi]
0x180006c7e  mov     rax, [rcx+30h]
0x180006c82  mov     rcx, rsi
0x180006c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c8a  mov     r14, rax
0x180006c8d  cmp     rbx, rax
0x180006c90  jnb     loc_180006D42
0x180006c96  cmp     qword ptr [rbx], 0
0x180006c9a  jz      loc_180006D35
0x180006ca0  mov     rcx, [rsi]
0x180006ca3  mov     rax, [rcx+18h]
0x180006ca7  mov     rcx, rsi
0x180006caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006caf  test    eax, eax
0x180006cb1  jz      short loc_180006CBC
0x180006cb3  test    r15b, r15b
0x180006cb6  jz      loc_180006D63
0x180006cbc  mov     rax, [rbx]
0x180006cbf  mov     rcx, [rax+18h]
0x180006cc3  mov     rax, [rcx]
0x180006cc6  test    rax, rax
0x180006cc9  jz      short loc_180006D35
0x180006ccb  mov     rax, [rsi]
0x180006cce  mov     rcx, rsi
0x180006cd1  mov     rax, [rax+38h]
0x180006cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cda  mov     rdi, rax
0x180006cdd  mov     rcx, rax; SRWLock
0x180006ce0  call    cs:__imp_AcquireSRWLockExclusive
0x180006ce6  mov     rcx, [rbx]
0x180006ce9  mov     rax, [rcx+18h]
0x180006ced  mov     rbp, [rax]
0x180006cf0  test    rbp, rbp
0x180006cf3  jnz     short loc_180006D05
0x180006cf5  test    rdi, rdi
0x180006cf8  jz      short loc_180006D35
0x180006cfa  mov     rcx, rdi; SRWLock
0x180006cfd  call    cs:__imp_ReleaseSRWLockExclusive
0x180006d03  jmp     short loc_180006D35
0x180006d05  mov     qword ptr [rax], 0
0x180006d0c  test    rdi, rdi
0x180006d0f  jz      short loc_180006D1A
0x180006d11  mov     rcx, rdi; SRWLock
0x180006d14  call    cs:__imp_ReleaseSRWLockExclusive
0x180006d1a  mov     rcx, rbp; Ptr
0x180006d1d  call    cs:__imp_DecodePointer
0x180006d23  mov     rdx, rax
0x180006d26  mov     rcx, [rax]
0x180006d29  mov     rax, [rcx+10h]
0x180006d2d  mov     rcx, rdx
0x180006d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d35  add     rbx, 8
0x180006d39  cmp     rbx, r14
0x180006d3c  jb      loc_180006C96
0x180006d42  mov     rax, [rsi]
0x180006d45  mov     rcx, rsi
0x180006d48  mov     rax, [rax+18h]
0x180006d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d51  test    eax, eax
0x180006d53  setz    al
0x180006d56  add     rsp, 28h
0x180006d5a  pop     r15
0x180006d5c  pop     r14
0x180006d5e  pop     rdi
0x180006d5f  pop     rsi
0x180006d60  pop     rbp
0x180006d61  pop     rbx
0x180006d62  retn
0x180006d63  xor     al, al
0x180006d65  jmp     short loc_180006D56
```
