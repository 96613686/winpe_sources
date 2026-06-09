# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18001719c`
- end: `0x18001726b`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016300`

## callees

- `0x18000de80`
- `0x180017024`
- `0x18001719c`

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
0x18001719c  push    rbx
0x18001719e  push    rbp
0x18001719f  push    rsi
0x1800171a0  push    rdi
0x1800171a1  sub     rsp, 28h
0x1800171a5  cmp     qword ptr [rcx+18h], 0
0x1800171aa  mov     rsi, rdx
0x1800171ad  mov     edi, [rcx+10h]
0x1800171b0  mov     rbx, rcx
0x1800171b3  mov     ebp, 50h ; 'P'
0x1800171b8  jnz     short loc_1800171EF
0x1800171ba  test    edi, edi
0x1800171bc  jz      short loc_1800171EF
0x1800171be  mov     edx, 190h; dwBytes
0x1800171c3  lea     ecx, [rbp-48h]; dwFlags
0x1800171c6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800171cb  mov     [rbx+18h], rax
0x1800171cf  test    rax, rax
0x1800171d2  jz      short loc_1800171EF
0x1800171d4  mov     dword ptr [rbx+20h], 5
0x1800171db  lea     rcx, [rax+190h]
0x1800171e2  jmp     short loc_1800171EA
0x1800171e4  mov     [rax], bp
0x1800171e7  add     rax, rbp
0x1800171ea  cmp     rax, rcx
0x1800171ed  jnz     short loc_1800171E4
0x1800171ef  mov     r9, [rbx+18h]
0x1800171f3  test    r9, r9
0x1800171f6  jz      short loc_180017262
0x1800171f8  test    edi, edi
0x1800171fa  jz      short loc_180017228
0x1800171fc  movzx   eax, word ptr [rbx+20h]
0x180017200  mov     rcx, r9
0x180017203  lea     rdx, [rax+rax*4]
0x180017207  shl     rdx, 4
0x18001720b  add     rdx, r9
0x18001720e  cmp     rcx, rdx
0x180017211  jz      short loc_180017228
0x180017213  mov     eax, [rbx+10h]
0x180017216  cmp     [rcx+4], eax
0x180017219  jbe     short loc_180017223
0x18001721b  mov     eax, [rsi+8]
0x18001721e  cmp     [rcx+8], eax
0x180017221  jz      short loc_180017262
0x180017223  add     rcx, rbp
0x180017226  jmp     short loc_18001720E
0x180017228  movzx   eax, word ptr [rbx+22h]
0x18001722c  xor     edx, edx
0x18001722e  movzx   ecx, word ptr [rbx+20h]
0x180017232  inc     eax
0x180017234  div     ecx
0x180017236  mov     rax, [rbx+8]
0x18001723a  mov     r8d, 1
0x180017240  mov     [rbx+22h], dx
0x180017244  lock xadd [rax], r8d
0x180017249  movzx   eax, dx
0x18001724c  inc     r8d; unsigned int
0x18001724f  mov     rdx, rsi; struct wil::FailureInfo *
0x180017252  lea     rcx, [rax+rax*4]
0x180017256  shl     rcx, 4
0x18001725a  add     rcx, r9; this
0x18001725d  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180017262  add     rsp, 28h
0x180017266  pop     rdi
0x180017267  pop     rsi
0x180017268  pop     rbp
0x180017269  pop     rbx
0x18001726a  retn
```
