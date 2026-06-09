# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180009538`
- end: `0x180009607`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007b70`

## callees

- `0x180008bc0`
- `0x1800091a0`
- `0x180009538`

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
0x180009538  push    rbx
0x18000953a  push    rbp
0x18000953b  push    rsi
0x18000953c  push    rdi
0x18000953d  sub     rsp, 28h
0x180009541  cmp     qword ptr [rcx+18h], 0
0x180009546  mov     rsi, rdx
0x180009549  mov     edi, [rcx+10h]
0x18000954c  mov     rbx, rcx
0x18000954f  mov     ebp, 50h ; 'P'
0x180009554  jnz     short loc_18000958B
0x180009556  test    edi, edi
0x180009558  jz      short loc_18000958B
0x18000955a  mov     edx, 190h; dwBytes
0x18000955f  lea     ecx, [rbp-48h]; dwFlags
0x180009562  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009567  mov     [rbx+18h], rax
0x18000956b  test    rax, rax
0x18000956e  jz      short loc_18000958B
0x180009570  mov     dword ptr [rbx+20h], 5
0x180009577  lea     rcx, [rax+190h]
0x18000957e  jmp     short loc_180009586
0x180009580  mov     [rax], bp
0x180009583  add     rax, rbp
0x180009586  cmp     rax, rcx
0x180009589  jnz     short loc_180009580
0x18000958b  mov     r9, [rbx+18h]
0x18000958f  test    r9, r9
0x180009592  jz      short loc_1800095FE
0x180009594  test    edi, edi
0x180009596  jz      short loc_1800095C4
0x180009598  movzx   eax, word ptr [rbx+20h]
0x18000959c  mov     rcx, r9
0x18000959f  lea     rdx, [rax+rax*4]
0x1800095a3  shl     rdx, 4
0x1800095a7  add     rdx, r9
0x1800095aa  cmp     rcx, rdx
0x1800095ad  jz      short loc_1800095C4
0x1800095af  mov     eax, [rbx+10h]
0x1800095b2  cmp     [rcx+4], eax
0x1800095b5  jbe     short loc_1800095BF
0x1800095b7  mov     eax, [rsi+8]
0x1800095ba  cmp     [rcx+8], eax
0x1800095bd  jz      short loc_1800095FE
0x1800095bf  add     rcx, rbp
0x1800095c2  jmp     short loc_1800095AA
0x1800095c4  movzx   eax, word ptr [rbx+22h]
0x1800095c8  xor     edx, edx
0x1800095ca  movzx   ecx, word ptr [rbx+20h]
0x1800095ce  inc     eax
0x1800095d0  div     ecx
0x1800095d2  mov     rax, [rbx+8]
0x1800095d6  mov     r8d, 1
0x1800095dc  mov     [rbx+22h], dx
0x1800095e0  lock xadd [rax], r8d
0x1800095e5  movzx   eax, dx
0x1800095e8  inc     r8d; unsigned int
0x1800095eb  mov     rdx, rsi; struct wil::FailureInfo *
0x1800095ee  lea     rcx, [rax+rax*4]
0x1800095f2  shl     rcx, 4
0x1800095f6  add     rcx, r9; this
0x1800095f9  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800095fe  add     rsp, 28h
0x180009602  pop     rdi
0x180009603  pop     rsi
0x180009604  pop     rbp
0x180009605  pop     rbx
0x180009606  retn
```
