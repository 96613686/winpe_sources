# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x180006144`
- end: `0x180006253`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `271`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005cc0`
- `0x180006260`

## callees

- `0x180006144`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800061cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800061cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800061e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006200`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800061e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006200`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006209`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006209`

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
0x180006144  push    rbx
0x180006146  push    rbp
0x180006147  push    rsi
0x180006148  push    rdi
0x180006149  push    r14
0x18000614b  push    r15
0x18000614d  sub     rsp, 28h
0x180006151  mov     r15b, r8b
0x180006154  mov     rsi, rcx
0x180006157  mov     rax, [rcx]
0x18000615a  mov     rax, [rax+20h]
0x18000615e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006163  lea     rbx, [rax+8]
0x180006167  mov     rdx, [rsi]
0x18000616a  mov     rcx, rsi
0x18000616d  mov     rax, [rdx+30h]
0x180006171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006176  mov     r14, rax
0x180006179  cmp     rbx, rax
0x18000617c  jnb     loc_18000622E
0x180006182  cmp     qword ptr [rbx], 0
0x180006186  jz      loc_180006221
0x18000618c  mov     rcx, [rsi]
0x18000618f  mov     rax, [rcx+18h]
0x180006193  mov     rcx, rsi
0x180006196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000619b  test    eax, eax
0x18000619d  jz      short loc_1800061A8
0x18000619f  test    r15b, r15b
0x1800061a2  jz      loc_18000624F
0x1800061a8  mov     rax, [rbx]
0x1800061ab  mov     rcx, [rax+18h]
0x1800061af  mov     rax, [rcx]
0x1800061b2  test    rax, rax
0x1800061b5  jz      short loc_180006221
0x1800061b7  mov     rax, [rsi]
0x1800061ba  mov     rcx, rsi
0x1800061bd  mov     rax, [rax+38h]
0x1800061c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061c6  mov     rdi, rax
0x1800061c9  mov     rcx, rax; SRWLock
0x1800061cc  call    cs:__imp_AcquireSRWLockExclusive
0x1800061d2  mov     rcx, [rbx]
0x1800061d5  mov     rax, [rcx+18h]
0x1800061d9  mov     rbp, [rax]
0x1800061dc  test    rbp, rbp
0x1800061df  jnz     short loc_1800061F1
0x1800061e1  test    rdi, rdi
0x1800061e4  jz      short loc_180006221
0x1800061e6  mov     rcx, rdi; SRWLock
0x1800061e9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800061ef  jmp     short loc_180006221
0x1800061f1  mov     qword ptr [rax], 0
0x1800061f8  test    rdi, rdi
0x1800061fb  jz      short loc_180006206
0x1800061fd  mov     rcx, rdi; SRWLock
0x180006200  call    cs:__imp_ReleaseSRWLockExclusive
0x180006206  mov     rcx, rbp; Ptr
0x180006209  call    cs:__imp_DecodePointer
0x18000620f  mov     rdx, rax
0x180006212  mov     rcx, [rax]
0x180006215  mov     rax, [rcx+10h]
0x180006219  mov     rcx, rdx
0x18000621c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006221  add     rbx, 8
0x180006225  cmp     rbx, r14
0x180006228  jb      loc_180006182
0x18000622e  mov     rax, [rsi]
0x180006231  mov     rcx, rsi
0x180006234  mov     rax, [rax+18h]
0x180006238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000623d  test    eax, eax
0x18000623f  setz    al
0x180006242  add     rsp, 28h
0x180006246  pop     r15
0x180006248  pop     r14
0x18000624a  pop     rdi
0x18000624b  pop     rsi
0x18000624c  pop     rbp
0x18000624d  pop     rbx
0x18000624e  retn
0x18000624f  xor     al, al
0x180006251  jmp     short loc_180006242
```
