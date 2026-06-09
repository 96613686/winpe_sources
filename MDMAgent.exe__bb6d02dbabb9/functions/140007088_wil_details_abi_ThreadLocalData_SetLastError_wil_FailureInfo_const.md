# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140007088`
- end: `0x140007158`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `208`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005470`

## callees

- `0x140006798`
- `0x140006cd4`
- `0x140007088`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v3; // edi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // r9
  __int64 i; // rcx
  unsigned __int16 v9; // dx
  volatile signed __int32 *v10; // rax

  v3 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v3 )
    {
      v5 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 8) = 5;
        v6 = v5 + 200;
        while ( v5 != v6 )
        {
          *v5 = 80;
          v5 += 40;
        }
      }
    }
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( v3 )
    {
      for ( i = *((_QWORD *)this + 3); i != v7 + 80LL * *((unsigned __int16 *)this + 16); i += 80 )
      {
        if ( *(_DWORD *)(i + 4) > *((_DWORD *)this + 4) && *(_DWORD *)(i + 8) == *((_DWORD *)a2 + 2) )
          return;
      }
    }
    v9 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
    v10 = (volatile signed __int32 *)*((_QWORD *)this + 1);
    *((_WORD *)this + 17) = v9;
    wil::details_abi::ThreadLocalFailureInfo::Set(
      (wil::details_abi::ThreadLocalFailureInfo *)(v7 + 80LL * v9),
      a2,
      _InterlockedIncrement(v10));
  }
}

```

## disassembly

```asm
0x140007088  push    rbx
0x14000708a  push    rbp
0x14000708b  push    rsi
0x14000708c  push    rdi
0x14000708d  sub     rsp, 28h
0x140007091  cmp     qword ptr [rcx+18h], 0
0x140007096  mov     rsi, rdx
0x140007099  mov     edi, [rcx+10h]
0x14000709c  mov     rbx, rcx
0x14000709f  mov     ebp, 50h ; 'P'
0x1400070a4  jnz     short loc_1400070DB
0x1400070a6  test    edi, edi
0x1400070a8  jz      short loc_1400070DB
0x1400070aa  mov     edx, 190h; dwBytes
0x1400070af  lea     ecx, [rbp-48h]; dwFlags
0x1400070b2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400070b7  mov     [rbx+18h], rax
0x1400070bb  test    rax, rax
0x1400070be  jz      short loc_1400070DB
0x1400070c0  mov     dword ptr [rbx+20h], 5
0x1400070c7  lea     rcx, [rax+190h]
0x1400070ce  jmp     short loc_1400070D6
0x1400070d0  mov     [rax], bp
0x1400070d3  add     rax, rbp
0x1400070d6  cmp     rax, rcx
0x1400070d9  jnz     short loc_1400070D0
0x1400070db  mov     r9, [rbx+18h]
0x1400070df  test    r9, r9
0x1400070e2  jz      short loc_14000714E
0x1400070e4  test    edi, edi
0x1400070e6  jz      short loc_140007114
0x1400070e8  movzx   eax, word ptr [rbx+20h]
0x1400070ec  mov     rcx, r9
0x1400070ef  lea     rdx, [rax+rax*4]
0x1400070f3  shl     rdx, 4
0x1400070f7  add     rdx, r9
0x1400070fa  cmp     rcx, rdx
0x1400070fd  jz      short loc_140007114
0x1400070ff  mov     eax, [rbx+10h]
0x140007102  cmp     [rcx+4], eax
0x140007105  jbe     short loc_14000710F
0x140007107  mov     eax, [rsi+8]
0x14000710a  cmp     [rcx+8], eax
0x14000710d  jz      short loc_14000714E
0x14000710f  add     rcx, rbp
0x140007112  jmp     short loc_1400070FA
0x140007114  movzx   eax, word ptr [rbx+22h]
0x140007118  xor     edx, edx
0x14000711a  movzx   ecx, word ptr [rbx+20h]
0x14000711e  inc     eax
0x140007120  div     ecx
0x140007122  mov     rax, [rbx+8]
0x140007126  mov     r8d, 1
0x14000712c  mov     [rbx+22h], dx
0x140007130  lock xadd [rax], r8d
0x140007135  movzx   eax, dx
0x140007138  inc     r8d; unsigned int
0x14000713b  mov     rdx, rsi; struct wil::FailureInfo *
0x14000713e  lea     rcx, [rax+rax*4]
0x140007142  shl     rcx, 4
0x140007146  add     rcx, r9; this
0x140007149  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000714e  add     rsp, 28h
0x140007152  pop     rdi
0x140007153  pop     rsi
0x140007154  pop     rbp
0x140007155  pop     rbx
0x140007156  retn
```
