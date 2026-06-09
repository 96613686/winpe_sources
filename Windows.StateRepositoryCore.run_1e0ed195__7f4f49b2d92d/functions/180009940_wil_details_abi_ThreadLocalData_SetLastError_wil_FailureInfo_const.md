# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180009940`
- end: `0x180009a0f`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005c20`

## callees

- `0x180007b48`
- `0x1800094b0`
- `0x180009940`

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
0x180009940  push    rbx
0x180009942  push    rbp
0x180009943  push    rsi
0x180009944  push    rdi
0x180009945  sub     rsp, 28h
0x180009949  cmp     qword ptr [rcx+18h], 0
0x18000994e  mov     rsi, rdx
0x180009951  mov     edi, [rcx+10h]
0x180009954  mov     rbx, rcx
0x180009957  mov     ebp, 50h ; 'P'
0x18000995c  jnz     short loc_180009993
0x18000995e  test    edi, edi
0x180009960  jz      short loc_180009993
0x180009962  mov     edx, 190h; dwBytes
0x180009967  lea     ecx, [rbp-48h]; dwFlags
0x18000996a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000996f  mov     [rbx+18h], rax
0x180009973  test    rax, rax
0x180009976  jz      short loc_180009993
0x180009978  mov     dword ptr [rbx+20h], 5
0x18000997f  lea     rcx, [rax+190h]
0x180009986  jmp     short loc_18000998E
0x180009988  mov     [rax], bp
0x18000998b  add     rax, rbp
0x18000998e  cmp     rax, rcx
0x180009991  jnz     short loc_180009988
0x180009993  mov     r9, [rbx+18h]
0x180009997  test    r9, r9
0x18000999a  jz      short loc_180009A06
0x18000999c  test    edi, edi
0x18000999e  jz      short loc_1800099CC
0x1800099a0  movzx   eax, word ptr [rbx+20h]
0x1800099a4  mov     rcx, r9
0x1800099a7  lea     rdx, [rax+rax*4]
0x1800099ab  shl     rdx, 4
0x1800099af  add     rdx, r9
0x1800099b2  cmp     rcx, rdx
0x1800099b5  jz      short loc_1800099CC
0x1800099b7  mov     eax, [rbx+10h]
0x1800099ba  cmp     [rcx+4], eax
0x1800099bd  jbe     short loc_1800099C7
0x1800099bf  mov     eax, [rsi+8]
0x1800099c2  cmp     [rcx+8], eax
0x1800099c5  jz      short loc_180009A06
0x1800099c7  add     rcx, rbp
0x1800099ca  jmp     short loc_1800099B2
0x1800099cc  movzx   eax, word ptr [rbx+22h]
0x1800099d0  xor     edx, edx
0x1800099d2  movzx   ecx, word ptr [rbx+20h]
0x1800099d6  inc     eax
0x1800099d8  div     ecx
0x1800099da  mov     rax, [rbx+8]
0x1800099de  mov     r8d, 1
0x1800099e4  mov     [rbx+22h], dx
0x1800099e8  lock xadd [rax], r8d
0x1800099ed  movzx   eax, dx
0x1800099f0  inc     r8d; unsigned int
0x1800099f3  mov     rdx, rsi; struct wil::FailureInfo *
0x1800099f6  lea     rcx, [rax+rax*4]
0x1800099fa  shl     rcx, 4
0x1800099fe  add     rcx, r9; this
0x180009a01  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180009a06  add     rsp, 28h
0x180009a0a  pop     rdi
0x180009a0b  pop     rsi
0x180009a0c  pop     rbp
0x180009a0d  pop     rbx
0x180009a0e  retn
```
