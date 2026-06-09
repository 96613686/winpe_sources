# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1400064b8`
- end: `0x140006587`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400047d0`

## callees

- `0x1400058d4`
- `0x140006254`
- `0x1400064b8`

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
0x1400064b8  push    rbx
0x1400064ba  push    rbp
0x1400064bb  push    rsi
0x1400064bc  push    rdi
0x1400064bd  sub     rsp, 28h
0x1400064c1  cmp     qword ptr [rcx+18h], 0
0x1400064c6  mov     rsi, rdx
0x1400064c9  mov     edi, [rcx+10h]
0x1400064cc  mov     rbx, rcx
0x1400064cf  mov     ebp, 50h ; 'P'
0x1400064d4  jnz     short loc_14000650B
0x1400064d6  test    edi, edi
0x1400064d8  jz      short loc_14000650B
0x1400064da  mov     edx, 190h; dwBytes
0x1400064df  lea     ecx, [rbp-48h]; dwFlags
0x1400064e2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400064e7  mov     [rbx+18h], rax
0x1400064eb  test    rax, rax
0x1400064ee  jz      short loc_14000650B
0x1400064f0  mov     dword ptr [rbx+20h], 5
0x1400064f7  lea     rcx, [rax+190h]
0x1400064fe  jmp     short loc_140006506
0x140006500  mov     [rax], bp
0x140006503  add     rax, rbp
0x140006506  cmp     rax, rcx
0x140006509  jnz     short loc_140006500
0x14000650b  mov     r9, [rbx+18h]
0x14000650f  test    r9, r9
0x140006512  jz      short loc_14000657E
0x140006514  test    edi, edi
0x140006516  jz      short loc_140006544
0x140006518  movzx   eax, word ptr [rbx+20h]
0x14000651c  mov     rcx, r9
0x14000651f  lea     rdx, [rax+rax*4]
0x140006523  shl     rdx, 4
0x140006527  add     rdx, r9
0x14000652a  cmp     rcx, rdx
0x14000652d  jz      short loc_140006544
0x14000652f  mov     eax, [rbx+10h]
0x140006532  cmp     [rcx+4], eax
0x140006535  jbe     short loc_14000653F
0x140006537  mov     eax, [rsi+8]
0x14000653a  cmp     [rcx+8], eax
0x14000653d  jz      short loc_14000657E
0x14000653f  add     rcx, rbp
0x140006542  jmp     short loc_14000652A
0x140006544  movzx   eax, word ptr [rbx+22h]
0x140006548  xor     edx, edx
0x14000654a  movzx   ecx, word ptr [rbx+20h]
0x14000654e  inc     eax
0x140006550  div     ecx
0x140006552  mov     rax, [rbx+8]
0x140006556  mov     r8d, 1
0x14000655c  mov     [rbx+22h], dx
0x140006560  lock xadd [rax], r8d
0x140006565  movzx   eax, dx
0x140006568  inc     r8d; unsigned int
0x14000656b  mov     rdx, rsi; struct wil::FailureInfo *
0x14000656e  lea     rcx, [rax+rax*4]
0x140006572  shl     rcx, 4
0x140006576  add     rcx, r9; this
0x140006579  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000657e  add     rsp, 28h
0x140006582  pop     rdi
0x140006583  pop     rsi
0x140006584  pop     rbp
0x140006585  pop     rbx
0x140006586  retn
```
