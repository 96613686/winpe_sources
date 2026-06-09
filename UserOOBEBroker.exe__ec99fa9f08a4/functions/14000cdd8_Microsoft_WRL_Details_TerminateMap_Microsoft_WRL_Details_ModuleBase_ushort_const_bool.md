# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x14000cdd8`
- end: `0x14000cee7`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `271`
- prototype: `bool __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *, bool)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007bf0`
- `0x1400082d4`
- `0x140008500`

## callees

- `0x14000cdd8`
- `0x14000f010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ce60`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ce60`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ce7d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ce94`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ce7d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ce94`
- `KERNEL32!DecodePointer` at `0x14000ce9d`
- `KERNEL32!DecodePointer` at `0x14000ce9d`

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
0x14000cdd8  push    rbx
0x14000cdda  push    rbp
0x14000cddb  push    rsi
0x14000cddc  push    rdi
0x14000cddd  push    r14
0x14000cddf  push    r15
0x14000cde1  sub     rsp, 28h
0x14000cde5  mov     r15b, r8b
0x14000cde8  mov     rsi, rcx
0x14000cdeb  mov     rax, [rcx]
0x14000cdee  mov     rax, [rax+20h]
0x14000cdf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cdf7  lea     rbx, [rax+8]
0x14000cdfb  mov     rdx, [rsi]
0x14000cdfe  mov     rcx, rsi
0x14000ce01  mov     rax, [rdx+30h]
0x14000ce05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce0a  mov     r14, rax
0x14000ce0d  cmp     rbx, rax
0x14000ce10  jnb     loc_14000CEC2
0x14000ce16  cmp     qword ptr [rbx], 0
0x14000ce1a  jz      loc_14000CEB5
0x14000ce20  mov     rcx, [rsi]
0x14000ce23  mov     rax, [rcx+18h]
0x14000ce27  mov     rcx, rsi
0x14000ce2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce2f  test    eax, eax
0x14000ce31  jz      short loc_14000CE3C
0x14000ce33  test    r15b, r15b
0x14000ce36  jz      loc_14000CEE3
0x14000ce3c  mov     rax, [rbx]
0x14000ce3f  mov     rcx, [rax+18h]
0x14000ce43  mov     rax, [rcx]
0x14000ce46  test    rax, rax
0x14000ce49  jz      short loc_14000CEB5
0x14000ce4b  mov     rax, [rsi]
0x14000ce4e  mov     rcx, rsi
0x14000ce51  mov     rax, [rax+38h]
0x14000ce55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce5a  mov     rdi, rax
0x14000ce5d  mov     rcx, rax; SRWLock
0x14000ce60  call    cs:__imp_AcquireSRWLockExclusive
0x14000ce66  mov     rcx, [rbx]
0x14000ce69  mov     rax, [rcx+18h]
0x14000ce6d  mov     rbp, [rax]
0x14000ce70  test    rbp, rbp
0x14000ce73  jnz     short loc_14000CE85
0x14000ce75  test    rdi, rdi
0x14000ce78  jz      short loc_14000CEB5
0x14000ce7a  mov     rcx, rdi; SRWLock
0x14000ce7d  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ce83  jmp     short loc_14000CEB5
0x14000ce85  mov     qword ptr [rax], 0
0x14000ce8c  test    rdi, rdi
0x14000ce8f  jz      short loc_14000CE9A
0x14000ce91  mov     rcx, rdi; SRWLock
0x14000ce94  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ce9a  mov     rcx, rbp; Ptr
0x14000ce9d  call    cs:__imp_DecodePointer
0x14000cea3  mov     rdx, rax
0x14000cea6  mov     rcx, [rax]
0x14000cea9  mov     rax, [rcx+10h]
0x14000cead  mov     rcx, rdx
0x14000ceb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ceb5  add     rbx, 8
0x14000ceb9  cmp     rbx, r14
0x14000cebc  jb      loc_14000CE16
0x14000cec2  mov     rax, [rsi]
0x14000cec5  mov     rcx, rsi
0x14000cec8  mov     rax, [rax+18h]
0x14000cecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ced1  test    eax, eax
0x14000ced3  setz    al
0x14000ced6  add     rsp, 28h
0x14000ceda  pop     r15
0x14000cedc  pop     r14
0x14000cede  pop     rdi
0x14000cedf  pop     rsi
0x14000cee0  pop     rbp
0x14000cee1  pop     rbx
0x14000cee2  retn
0x14000cee3  xor     al, al
0x14000cee5  jmp     short loc_14000CED6
```
