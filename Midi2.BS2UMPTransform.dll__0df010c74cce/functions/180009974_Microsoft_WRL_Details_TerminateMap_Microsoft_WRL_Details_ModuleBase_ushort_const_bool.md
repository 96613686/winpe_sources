# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x180009974`
- end: `0x180009a83`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `271`
- prototype: `bool __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008d30`
- `0x180009ab0`

## callees

- `0x180009974`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800099fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800099fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a30`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009a39`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009a39`

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
0x180009974  push    rbx
0x180009976  push    rbp
0x180009977  push    rsi
0x180009978  push    rdi
0x180009979  push    r14
0x18000997b  push    r15
0x18000997d  sub     rsp, 28h
0x180009981  mov     r15b, r8b
0x180009984  mov     rsi, rcx
0x180009987  mov     rax, [rcx]
0x18000998a  mov     rax, [rax+20h]
0x18000998e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009993  lea     rbx, [rax+8]
0x180009997  mov     rdx, [rsi]
0x18000999a  mov     rcx, rsi
0x18000999d  mov     rax, [rdx+30h]
0x1800099a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099a6  mov     r14, rax
0x1800099a9  cmp     rbx, rax
0x1800099ac  jnb     loc_180009A5E
0x1800099b2  cmp     qword ptr [rbx], 0
0x1800099b6  jz      loc_180009A51
0x1800099bc  mov     rcx, [rsi]
0x1800099bf  mov     rax, [rcx+18h]
0x1800099c3  mov     rcx, rsi
0x1800099c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099cb  test    eax, eax
0x1800099cd  jz      short loc_1800099D8
0x1800099cf  test    r15b, r15b
0x1800099d2  jz      loc_180009A7F
0x1800099d8  mov     rax, [rbx]
0x1800099db  mov     rcx, [rax+18h]
0x1800099df  mov     rax, [rcx]
0x1800099e2  test    rax, rax
0x1800099e5  jz      short loc_180009A51
0x1800099e7  mov     rax, [rsi]
0x1800099ea  mov     rcx, rsi
0x1800099ed  mov     rax, [rax+38h]
0x1800099f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099f6  mov     rdi, rax
0x1800099f9  mov     rcx, rax; SRWLock
0x1800099fc  call    cs:__imp_AcquireSRWLockExclusive
0x180009a02  mov     rcx, [rbx]
0x180009a05  mov     rax, [rcx+18h]
0x180009a09  mov     rbp, [rax]
0x180009a0c  test    rbp, rbp
0x180009a0f  jnz     short loc_180009A21
0x180009a11  test    rdi, rdi
0x180009a14  jz      short loc_180009A51
0x180009a16  mov     rcx, rdi; SRWLock
0x180009a19  call    cs:__imp_ReleaseSRWLockExclusive
0x180009a1f  jmp     short loc_180009A51
0x180009a21  mov     qword ptr [rax], 0
0x180009a28  test    rdi, rdi
0x180009a2b  jz      short loc_180009A36
0x180009a2d  mov     rcx, rdi; SRWLock
0x180009a30  call    cs:__imp_ReleaseSRWLockExclusive
0x180009a36  mov     rcx, rbp; Ptr
0x180009a39  call    cs:__imp_DecodePointer
0x180009a3f  mov     rdx, rax
0x180009a42  mov     rcx, [rax]
0x180009a45  mov     rax, [rcx+10h]
0x180009a49  mov     rcx, rdx
0x180009a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a51  add     rbx, 8
0x180009a55  cmp     rbx, r14
0x180009a58  jb      loc_1800099B2
0x180009a5e  mov     rax, [rsi]
0x180009a61  mov     rcx, rsi
0x180009a64  mov     rax, [rax+18h]
0x180009a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a6d  test    eax, eax
0x180009a6f  setz    al
0x180009a72  add     rsp, 28h
0x180009a76  pop     r15
0x180009a78  pop     r14
0x180009a7a  pop     rdi
0x180009a7b  pop     rsi
0x180009a7c  pop     rbp
0x180009a7d  pop     rbx
0x180009a7e  retn
0x180009a7f  xor     al, al
0x180009a81  jmp     short loc_180009A72
```
