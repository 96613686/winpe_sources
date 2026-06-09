# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x180006abc`
- end: `0x180006bcb`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `271`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003c90`
- `0x180007890`

## callees

- `0x180006abc`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b78`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b44`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006b81`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006b81`

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
0x180006abc  push    rbx
0x180006abe  push    rbp
0x180006abf  push    rsi
0x180006ac0  push    rdi
0x180006ac1  push    r14
0x180006ac3  push    r15
0x180006ac5  sub     rsp, 28h
0x180006ac9  mov     r15b, r8b
0x180006acc  mov     rsi, rcx
0x180006acf  mov     rax, [rcx]
0x180006ad2  mov     rax, [rax+20h]
0x180006ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006adb  lea     rbx, [rax+8]
0x180006adf  mov     rdx, [rsi]
0x180006ae2  mov     rcx, rsi
0x180006ae5  mov     rax, [rdx+30h]
0x180006ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aee  mov     r14, rax
0x180006af1  cmp     rbx, rax
0x180006af4  jnb     loc_180006BA6
0x180006afa  cmp     qword ptr [rbx], 0
0x180006afe  jz      loc_180006B99
0x180006b04  mov     rcx, [rsi]
0x180006b07  mov     rax, [rcx+18h]
0x180006b0b  mov     rcx, rsi
0x180006b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b13  test    eax, eax
0x180006b15  jz      short loc_180006B20
0x180006b17  test    r15b, r15b
0x180006b1a  jz      loc_180006BC7
0x180006b20  mov     rax, [rbx]
0x180006b23  mov     rcx, [rax+18h]
0x180006b27  mov     rax, [rcx]
0x180006b2a  test    rax, rax
0x180006b2d  jz      short loc_180006B99
0x180006b2f  mov     rax, [rsi]
0x180006b32  mov     rcx, rsi
0x180006b35  mov     rax, [rax+38h]
0x180006b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b3e  mov     rdi, rax
0x180006b41  mov     rcx, rax; SRWLock
0x180006b44  call    cs:__imp_AcquireSRWLockExclusive
0x180006b4a  mov     rcx, [rbx]
0x180006b4d  mov     rax, [rcx+18h]
0x180006b51  mov     rbp, [rax]
0x180006b54  test    rbp, rbp
0x180006b57  jnz     short loc_180006B69
0x180006b59  test    rdi, rdi
0x180006b5c  jz      short loc_180006B99
0x180006b5e  mov     rcx, rdi; SRWLock
0x180006b61  call    cs:__imp_ReleaseSRWLockExclusive
0x180006b67  jmp     short loc_180006B99
0x180006b69  mov     qword ptr [rax], 0
0x180006b70  test    rdi, rdi
0x180006b73  jz      short loc_180006B7E
0x180006b75  mov     rcx, rdi; SRWLock
0x180006b78  call    cs:__imp_ReleaseSRWLockExclusive
0x180006b7e  mov     rcx, rbp; Ptr
0x180006b81  call    cs:__imp_DecodePointer
0x180006b87  mov     rdx, rax
0x180006b8a  mov     rcx, [rax]
0x180006b8d  mov     rax, [rcx+10h]
0x180006b91  mov     rcx, rdx
0x180006b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b99  add     rbx, 8
0x180006b9d  cmp     rbx, r14
0x180006ba0  jb      loc_180006AFA
0x180006ba6  mov     rax, [rsi]
0x180006ba9  mov     rcx, rsi
0x180006bac  mov     rax, [rax+18h]
0x180006bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bb5  test    eax, eax
0x180006bb7  setz    al
0x180006bba  add     rsp, 28h
0x180006bbe  pop     r15
0x180006bc0  pop     r14
0x180006bc2  pop     rdi
0x180006bc3  pop     rsi
0x180006bc4  pop     rbp
0x180006bc5  pop     rbx
0x180006bc6  retn
0x180006bc7  xor     al, al
0x180006bc9  jmp     short loc_180006BBA
```
