# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180009184`
- end: `0x18000930a`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008f10`
- `0x18000afc0`

## callees

- `0x180009184`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800091d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800091d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009215`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000922a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009215`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000922a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009270`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009270`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800092bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800092bb`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800091e6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000929b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800091e6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000929b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000928c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000928c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        _QWORD *Ptr)
{
  _QWORD *v5; // r14
  RTL_SRWLOCK *v10; // rbx
  void *v11; // rcx
  unsigned int v12; // edi
  __int64 result; // rax
  RTL_SRWLOCK *v14; // rsi
  void *v15; // rcx
  PVOID v16; // rbx

  v5 = Ptr;
  Ptr = 0;
  *v5 = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v10 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v10);
    v11 = **(void ***)a4[1].Data4;
    if ( v11 )
    {
      Ptr = DecodePointer(v11);
      v12 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *, _QWORD *))*Ptr)(Ptr, a3, v5);
      if ( v10 )
        ReleaseSRWLockShared(v10);
      return v12;
    }
    if ( v10 )
      ReleaseSRWLockShared(v10);
  }
  result = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, const struct _GUID *, unsigned int *, _QWORD **))&a4->Data1)(
             a2,
             a4,
             a3,
             &Ptr);
  if ( (int)result >= 0 )
  {
    if ( (*(_BYTE *)a2 & 4) != 0 )
      goto LABEL_17;
    v14 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockExclusive(v14);
    v15 = **(void ***)a4[1].Data4;
    if ( v15 )
    {
      v16 = DecodePointer(v15);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v16 + 8LL))(v16);
    }
    else
    {
      v16 = 0;
      **(_QWORD **)a4[1].Data4 = EncodePointer(Ptr);
    }
    if ( v14 )
      ReleaseSRWLockExclusive(v14);
    if ( !v16 )
    {
LABEL_17:
      v16 = Ptr;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
    }
    *v5 = v16;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009184  mov     rax, rsp
0x180009187  push    rbx
0x180009188  push    rbp
0x180009189  push    rsi
0x18000918a  push    rdi
0x18000918b  push    r14
0x18000918d  push    r15
0x18000918f  sub     rsp, 38h
0x180009193  mov     r14, [rsp+68h+Ptr]
0x18000919b  mov     rdi, r9
0x18000919e  mov     qword ptr [rax+28h], 0
0x1800091a6  mov     r15, r8
0x1800091a9  mov     rbp, rdx
0x1800091ac  mov     rsi, rcx
0x1800091af  mov     qword ptr [r14], 0
0x1800091b6  mov     rax, [r9+18h]
0x1800091ba  mov     r10, [rax]
0x1800091bd  test    r10, r10
0x1800091c0  jz      short loc_180009230
0x1800091c2  mov     rax, [rcx]
0x1800091c5  mov     rax, [rax+38h]
0x1800091c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091ce  mov     rcx, rax; SRWLock
0x1800091d1  mov     rbx, rax
0x1800091d4  call    cs:__imp_AcquireSRWLockShared
0x1800091da  mov     rcx, [rdi+18h]
0x1800091de  mov     rcx, [rcx]; Ptr
0x1800091e1  test    rcx, rcx
0x1800091e4  jz      short loc_180009222
0x1800091e6  call    cs:__imp_DecodePointer
0x1800091ec  mov     [rsp+68h+Ptr], rax
0x1800091f4  mov     r8, r14
0x1800091f7  mov     r9, rax
0x1800091fa  mov     rdx, r15
0x1800091fd  mov     rcx, [rax]
0x180009200  mov     rax, [rcx]
0x180009203  mov     rcx, r9
0x180009206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000920b  mov     edi, eax
0x18000920d  test    rbx, rbx
0x180009210  jz      short loc_18000921B
0x180009212  mov     rcx, rbx; SRWLock
0x180009215  call    cs:__imp_ReleaseSRWLockShared
0x18000921b  mov     eax, edi
0x18000921d  jmp     loc_1800092FD
0x180009222  test    rbx, rbx
0x180009225  jz      short loc_180009230
0x180009227  mov     rcx, rbx; SRWLock
0x18000922a  call    cs:__imp_ReleaseSRWLockShared
0x180009230  mov     rax, [rdi]
0x180009233  lea     r9, [rsp+68h+Ptr]
0x18000923b  mov     r8, r15
0x18000923e  mov     rdx, rdi
0x180009241  mov     rcx, rbp
0x180009244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009249  test    eax, eax
0x18000924b  js      loc_1800092FD
0x180009251  test    byte ptr [rbp+0], 4
0x180009255  jnz     loc_1800092F0
0x18000925b  mov     rax, [rsi]
0x18000925e  mov     rcx, rsi
0x180009261  mov     rax, [rax+38h]
0x180009265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000926a  mov     rcx, rax; SRWLock
0x18000926d  mov     rsi, rax
0x180009270  call    cs:__imp_AcquireSRWLockExclusive
0x180009276  mov     rcx, [rdi+18h]
0x18000927a  mov     rcx, [rcx]; Ptr
0x18000927d  test    rcx, rcx
0x180009280  jnz     short loc_18000929B
0x180009282  mov     rcx, [rsp+68h+Ptr]; Ptr
0x18000928a  xor     ebx, ebx
0x18000928c  call    cs:__imp_EncodePointer
0x180009292  mov     rcx, [rdi+18h]
0x180009296  mov     [rcx], rax
0x180009299  jmp     short loc_1800092B3
0x18000929b  call    cs:__imp_DecodePointer
0x1800092a1  mov     rbx, rax
0x1800092a4  mov     rcx, [rax]
0x1800092a7  mov     rax, [rcx+8]
0x1800092ab  mov     rcx, rbx
0x1800092ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092b3  test    rsi, rsi
0x1800092b6  jz      short loc_1800092C1
0x1800092b8  mov     rcx, rsi; SRWLock
0x1800092bb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800092c1  test    rbx, rbx
0x1800092c4  jz      short loc_1800092F0
0x1800092c6  mov     rcx, [rsp+68h+Ptr]
0x1800092ce  mov     rax, [rcx]
0x1800092d1  mov     rax, [rax+10h]
0x1800092d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092da  mov     rcx, [rsp+68h+Ptr]
0x1800092e2  mov     rax, [rcx]
0x1800092e5  mov     rax, [rax+10h]
0x1800092e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ee  jmp     short loc_1800092F8
0x1800092f0  mov     rbx, [rsp+68h+Ptr]
0x1800092f8  mov     [r14], rbx
0x1800092fb  xor     eax, eax
0x1800092fd  add     rsp, 38h
0x180009301  pop     r15
0x180009303  pop     r14
0x180009305  pop     rdi
0x180009306  pop     rsi
0x180009307  pop     rbp
0x180009308  pop     rbx
0x180009309  retn
```
