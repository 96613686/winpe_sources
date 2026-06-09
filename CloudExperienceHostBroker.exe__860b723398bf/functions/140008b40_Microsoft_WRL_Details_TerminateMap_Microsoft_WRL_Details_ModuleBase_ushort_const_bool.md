# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x140008b40`
- end: `0x140008c6e`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `302`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, RTL_SRWLOCK *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140007380`
- `0x140008d1c`

## callees

- `0x140008124`
- `0x140008b40`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008bf2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008c10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008bf2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008c10`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140008c22`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140008c22`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Details::TerminateMap(
        Microsoft::WRL::Details *this,
        RTL_SRWLOCK *a2,
        const unsigned __int16 *a3)
{
  char v3; // bp
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r14
  __int64 v7; // rax
  void **v8; // rcx
  void *v9; // rsi
  PVOID v10; // rax
  PSRWLOCK SRWLock; // [rsp+48h] [rbp+10h] BYREF

  SRWLock = a2;
  v3 = (char)a3;
  v5 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 32LL))(this) + 8;
  v6 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
  while ( v5 < v6 )
  {
    if ( *(_QWORD *)v5 )
    {
      if ( (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) && !v3 )
        return 0;
      if ( **(_QWORD **)(*(_QWORD *)v5 + 24LL) )
      {
        v7 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
        Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v7);
        v8 = *(void ***)(*(_QWORD *)v5 + 24LL);
        v9 = *v8;
        if ( *v8 )
        {
          *v8 = 0;
          if ( SRWLock )
          {
            ReleaseSRWLockExclusive(SRWLock);
            SRWLock = 0;
          }
          v10 = DecodePointer(v9);
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)v10 + 16LL))(v10);
        }
        else if ( SRWLock )
        {
          ReleaseSRWLockExclusive(SRWLock);
          SRWLock = 0;
        }
      }
    }
    v5 += 8LL;
  }
  return (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) == 0;
}

```

## disassembly

```asm
0x140008b40  mov     [rsp+arg_0], rbx
0x140008b45  mov     [rsp+arg_10], rbp
0x140008b4a  mov     [rsp+SRWLock], rdx
0x140008b4f  push    rsi
0x140008b50  push    rdi
0x140008b51  push    r14
0x140008b53  sub     rsp, 20h
0x140008b57  mov     bpl, r8b
0x140008b5a  mov     rdi, rcx
0x140008b5d  mov     rax, [rcx]
0x140008b60  mov     rax, [rax+20h]
0x140008b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008b69  lea     rbx, [rax+8]
0x140008b6d  mov     rdx, [rdi]
0x140008b70  mov     rcx, rdi
0x140008b73  mov     rax, [rdx+30h]
0x140008b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008b7c  mov     r14, rax
0x140008b7f  cmp     rbx, r14
0x140008b82  jnb     loc_140008C47
0x140008b88  cmp     qword ptr [rbx], 0
0x140008b8c  jz      loc_140008C3A
0x140008b92  mov     rcx, [rdi]
0x140008b95  mov     rax, [rcx+18h]
0x140008b99  mov     rcx, rdi
0x140008b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008ba1  test    eax, eax
0x140008ba3  jz      short loc_140008BAE
0x140008ba5  test    bpl, bpl
0x140008ba8  jz      loc_140008C43
0x140008bae  mov     rax, [rbx]
0x140008bb1  mov     rcx, [rax+18h]
0x140008bb5  mov     rax, [rcx]
0x140008bb8  test    rax, rax
0x140008bbb  jz      short loc_140008C3A
0x140008bbd  mov     rax, [rdi]
0x140008bc0  mov     rcx, rdi
0x140008bc3  mov     rax, [rax+38h]
0x140008bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008bcc  mov     rdx, rax
0x140008bcf  lea     rcx, [rsp+38h+SRWLock]
0x140008bd4  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x140008bd9  mov     rax, [rbx]
0x140008bdc  mov     rcx, [rax+18h]
0x140008be0  mov     rsi, [rcx]
0x140008be3  test    rsi, rsi
0x140008be6  jnz     short loc_140008BFF
0x140008be8  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x140008bed  test    rcx, rcx
0x140008bf0  jz      short loc_140008C3A
0x140008bf2  call    cs:__imp_ReleaseSRWLockExclusive
0x140008bf8  mov     [rsp+38h+SRWLock], rsi
0x140008bfd  jmp     short loc_140008C3A
0x140008bff  mov     qword ptr [rcx], 0
0x140008c06  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x140008c0b  test    rcx, rcx
0x140008c0e  jz      short loc_140008C1F
0x140008c10  call    cs:__imp_ReleaseSRWLockExclusive
0x140008c16  mov     [rsp+38h+SRWLock], 0
0x140008c1f  mov     rcx, rsi; Ptr
0x140008c22  call    cs:__imp_DecodePointer
0x140008c28  mov     rdx, rax
0x140008c2b  mov     rcx, [rax]
0x140008c2e  mov     rax, [rcx+10h]
0x140008c32  mov     rcx, rdx
0x140008c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c3a  add     rbx, 8
0x140008c3e  jmp     loc_140008B7F
0x140008c43  xor     al, al
0x140008c45  jmp     short loc_140008C5B
0x140008c47  mov     rax, [rdi]
0x140008c4a  mov     rcx, rdi
0x140008c4d  mov     rax, [rax+18h]
0x140008c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c56  test    eax, eax
0x140008c58  setz    al
0x140008c5b  mov     rbx, [rsp+38h+arg_0]
0x140008c60  mov     rbp, [rsp+38h+arg_10]
0x140008c65  add     rsp, 20h
0x140008c69  pop     r14
0x140008c6b  pop     rdi
0x140008c6c  pop     rsi
0x140008c6d  retn
```
