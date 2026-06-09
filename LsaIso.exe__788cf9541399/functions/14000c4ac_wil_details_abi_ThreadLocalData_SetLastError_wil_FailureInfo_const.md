# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x14000c4ac`
- end: `0x14000c57b`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400099b0`

## callees

- `0x14000b3b4`
- `0x14000c038`
- `0x14000c4ac`

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
0x14000c4ac  push    rbx
0x14000c4ae  push    rbp
0x14000c4af  push    rsi
0x14000c4b0  push    rdi
0x14000c4b1  sub     rsp, 28h
0x14000c4b5  cmp     qword ptr [rcx+18h], 0
0x14000c4ba  mov     rsi, rdx
0x14000c4bd  mov     edi, [rcx+10h]
0x14000c4c0  mov     rbx, rcx
0x14000c4c3  mov     ebp, 50h ; 'P'
0x14000c4c8  jnz     short loc_14000C4FF
0x14000c4ca  test    edi, edi
0x14000c4cc  jz      short loc_14000C4FF
0x14000c4ce  mov     edx, 190h; dwBytes
0x14000c4d3  lea     ecx, [rbp-48h]; dwFlags
0x14000c4d6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000c4db  mov     [rbx+18h], rax
0x14000c4df  test    rax, rax
0x14000c4e2  jz      short loc_14000C4FF
0x14000c4e4  mov     dword ptr [rbx+20h], 5
0x14000c4eb  lea     rcx, [rax+190h]
0x14000c4f2  jmp     short loc_14000C4FA
0x14000c4f4  mov     [rax], bp
0x14000c4f7  add     rax, rbp
0x14000c4fa  cmp     rax, rcx
0x14000c4fd  jnz     short loc_14000C4F4
0x14000c4ff  mov     r9, [rbx+18h]
0x14000c503  test    r9, r9
0x14000c506  jz      short loc_14000C572
0x14000c508  test    edi, edi
0x14000c50a  jz      short loc_14000C538
0x14000c50c  movzx   eax, word ptr [rbx+20h]
0x14000c510  mov     rcx, r9
0x14000c513  lea     rdx, [rax+rax*4]
0x14000c517  shl     rdx, 4
0x14000c51b  add     rdx, r9
0x14000c51e  cmp     rcx, rdx
0x14000c521  jz      short loc_14000C538
0x14000c523  mov     eax, [rbx+10h]
0x14000c526  cmp     [rcx+4], eax
0x14000c529  jbe     short loc_14000C533
0x14000c52b  mov     eax, [rsi+8]
0x14000c52e  cmp     [rcx+8], eax
0x14000c531  jz      short loc_14000C572
0x14000c533  add     rcx, rbp
0x14000c536  jmp     short loc_14000C51E
0x14000c538  movzx   eax, word ptr [rbx+22h]
0x14000c53c  xor     edx, edx
0x14000c53e  movzx   ecx, word ptr [rbx+20h]
0x14000c542  inc     eax
0x14000c544  div     ecx
0x14000c546  mov     rax, [rbx+8]
0x14000c54a  mov     r8d, 1
0x14000c550  mov     [rbx+22h], dx
0x14000c554  lock xadd [rax], r8d
0x14000c559  movzx   eax, dx
0x14000c55c  inc     r8d; unsigned int
0x14000c55f  mov     rdx, rsi; struct wil::FailureInfo *
0x14000c562  lea     rcx, [rax+rax*4]
0x14000c566  shl     rcx, 4
0x14000c56a  add     rcx, r9; this
0x14000c56d  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000c572  add     rsp, 28h
0x14000c576  pop     rdi
0x14000c577  pop     rsi
0x14000c578  pop     rbp
0x14000c579  pop     rbx
0x14000c57a  retn
```
