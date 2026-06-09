# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800095d4`
- end: `0x1800096a3`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007c10`

## callees

- `0x180008acc`
- `0x18000923c`
- `0x1800095d4`

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
0x1800095d4  push    rbx
0x1800095d6  push    rbp
0x1800095d7  push    rsi
0x1800095d8  push    rdi
0x1800095d9  sub     rsp, 28h
0x1800095dd  cmp     qword ptr [rcx+18h], 0
0x1800095e2  mov     rsi, rdx
0x1800095e5  mov     edi, [rcx+10h]
0x1800095e8  mov     rbx, rcx
0x1800095eb  mov     ebp, 50h ; 'P'
0x1800095f0  jnz     short loc_180009627
0x1800095f2  test    edi, edi
0x1800095f4  jz      short loc_180009627
0x1800095f6  mov     edx, 190h; dwBytes
0x1800095fb  lea     ecx, [rbp-48h]; dwFlags
0x1800095fe  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009603  mov     [rbx+18h], rax
0x180009607  test    rax, rax
0x18000960a  jz      short loc_180009627
0x18000960c  mov     dword ptr [rbx+20h], 5
0x180009613  lea     rcx, [rax+190h]
0x18000961a  jmp     short loc_180009622
0x18000961c  mov     [rax], bp
0x18000961f  add     rax, rbp
0x180009622  cmp     rax, rcx
0x180009625  jnz     short loc_18000961C
0x180009627  mov     r9, [rbx+18h]
0x18000962b  test    r9, r9
0x18000962e  jz      short loc_18000969A
0x180009630  test    edi, edi
0x180009632  jz      short loc_180009660
0x180009634  movzx   eax, word ptr [rbx+20h]
0x180009638  mov     rcx, r9
0x18000963b  lea     rdx, [rax+rax*4]
0x18000963f  shl     rdx, 4
0x180009643  add     rdx, r9
0x180009646  cmp     rcx, rdx
0x180009649  jz      short loc_180009660
0x18000964b  mov     eax, [rbx+10h]
0x18000964e  cmp     [rcx+4], eax
0x180009651  jbe     short loc_18000965B
0x180009653  mov     eax, [rsi+8]
0x180009656  cmp     [rcx+8], eax
0x180009659  jz      short loc_18000969A
0x18000965b  add     rcx, rbp
0x18000965e  jmp     short loc_180009646
0x180009660  movzx   eax, word ptr [rbx+22h]
0x180009664  xor     edx, edx
0x180009666  movzx   ecx, word ptr [rbx+20h]
0x18000966a  inc     eax
0x18000966c  div     ecx
0x18000966e  mov     rax, [rbx+8]
0x180009672  mov     r8d, 1
0x180009678  mov     [rbx+22h], dx
0x18000967c  lock xadd [rax], r8d
0x180009681  movzx   eax, dx
0x180009684  inc     r8d; unsigned int
0x180009687  mov     rdx, rsi; struct wil::FailureInfo *
0x18000968a  lea     rcx, [rax+rax*4]
0x18000968e  shl     rcx, 4
0x180009692  add     rcx, r9; this
0x180009695  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000969a  add     rsp, 28h
0x18000969e  pop     rdi
0x18000969f  pop     rsi
0x1800096a0  pop     rbp
0x1800096a1  pop     rbx
0x1800096a2  retn
```
