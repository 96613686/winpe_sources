# __abi_FTMWeakRefData::__abi_QueryInterface(Platform::Guid &,void * *)

- ea: `0x140008470`
- end: `0x14000854a`
- name: `?__abi_QueryInterface@__abi_FTMWeakRefData@@QEAAJAEAVGuid@Platform@@PEAPEAX@Z`
- size: `218`
- prototype: `__int64 __fastcall(__abi_FTMWeakRefData *__hidden this, struct Platform::Guid *, void **)`
- caller_count: `35`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400081a0`
- `0x140008340`
- `0x14000eb70`
- `0x14000ee90`
- `0x14000f070`
- `0x14000f340`
- `0x14000f570`
- `0x14000f6b0`
- `0x14001fd10`
- `0x14001fe50`
- `0x14001ff90`
- `0x1400200d0`
- `0x140020210`
- `0x140020440`
- `0x140020670`
- `0x140020ac0`
- `0x140020f10`
- `0x140021030`
- `0x140021170`
- `0x140023db0`
- `0x140026200`
- `0x1400263e0`
- `0x14002e320`
- `0x14002e460`
- `0x14002e580`
- `0x14002e8a0`
- `0x14002ebc0`
- `0x14002edf0`
- `0x14002f170`
- `0x14002f430`
- `0x14002f610`
- `0x14002f7f0`
- `0x14002f9d0`
- `0x14002fb70`
- `0x14002fcb0`

## callees

- `0x1400039e6`
- `0x140008470`
- `0x1400086b0`
- `0x140031960`
- `0x140035010`

## pseudocode

```c
__int64 __fastcall __abi_FTMWeakRefData::__abi_QueryInterface(
        __abi_FTMWeakRefData *this,
        struct Platform::Guid *a2,
        void **a3)
{
  __int64 v6; // rcx
  HRESULT v7; // eax
  LPUNKNOWN ppunkMarshal; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_QWORD *)this + 1)
    || *(_DWORD *)a2 != 3
    || *((_DWORD *)a2 + 1) != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
    || *((_DWORD *)a2 + 2) != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4
    || *((_DWORD *)a2 + 3) != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4] )
  {
    return 2147500034LL;
  }
  if ( *((_QWORD *)this + 1) == -1 )
  {
    v6 = *(_QWORD *)this;
    ppunkMarshal = 0;
    v7 = CoCreateFreeThreadedMarshaler_0(*(LPUNKNOWN *)(v6 + 16), &ppunkMarshal);
    if ( v7 < 0 )
      __abi_WinRTraiseException(v7);
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 1, (signed __int64)ppunkMarshal, -1) != -1 )
      ((void (__fastcall *)(LPUNKNOWN))ppunkMarshal->lpVtbl->Release)(ppunkMarshal);
  }
  return (***((__int64 (__fastcall ****)(_QWORD, struct Platform::Guid *, void **))this + 1))(
           *((_QWORD *)this + 1),
           a2,
           a3);
}

```

## disassembly

```asm
0x140008470  push    rbx
0x140008472  push    rsi
0x140008473  push    rdi
0x140008474  sub     rsp, 30h
0x140008478  mov     rax, cs:__security_cookie
0x14000847f  xor     rax, rsp
0x140008482  mov     [rsp+48h+var_20], rax
0x140008487  mov     rax, [rcx+8]
0x14000848b  mov     rsi, r8
0x14000848e  mov     rbx, rdx
0x140008491  mov     rdi, rcx
0x140008494  test    rax, rax
0x140008497  jz      loc_140008528
0x14000849d  cmp     dword ptr [rdx], 3
0x1400084a0  jnz     loc_140008528
0x1400084a6  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x1400084ac  cmp     [rdx+4], eax
0x1400084af  jnz     short loc_140008528
0x1400084b1  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x1400084b7  cmp     [rdx+8], eax
0x1400084ba  jnz     short loc_140008528
0x1400084bc  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x1400084c2  cmp     [rdx+0Ch], eax
0x1400084c5  jnz     short loc_140008528
0x1400084c7  mov     rax, [rcx+8]
0x1400084cb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400084cf  jnz     short loc_140008511
0x1400084d1  mov     rcx, [rcx]
0x1400084d4  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1400084d9  mov     [rsp+48h+ppunkMarshal], 0
0x1400084e2  mov     rcx, [rcx+10h]; punkOuter
0x1400084e6  call    CoCreateFreeThreadedMarshaler_0
0x1400084eb  test    eax, eax
0x1400084ed  js      short loc_140008542
0x1400084ef  mov     rcx, [rsp+48h+ppunkMarshal]
0x1400084f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400084f8  lock cmpxchg [rdi+8], rcx
0x1400084fe  jz      short loc_140008511
0x140008500  mov     rcx, [rsp+48h+ppunkMarshal]
0x140008505  mov     rax, [rcx]
0x140008508  mov     rax, [rax+10h]
0x14000850c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008511  mov     rcx, [rdi+8]
0x140008515  mov     r8, rsi
0x140008518  mov     rdx, rbx
0x14000851b  mov     rax, [rcx]
0x14000851e  mov     rax, [rax]
0x140008521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008526  jmp     short loc_14000852D
0x140008528  mov     eax, 80004002h
0x14000852d  mov     rcx, [rsp+48h+var_20]
0x140008532  xor     rcx, rsp; StackCookie
0x140008535  call    __security_check_cookie
0x14000853a  add     rsp, 30h
0x14000853e  pop     rdi
0x14000853f  pop     rsi
0x140008540  pop     rbx
0x140008541  retn
0x140008542  mov     ecx, eax; int
0x140008544  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
