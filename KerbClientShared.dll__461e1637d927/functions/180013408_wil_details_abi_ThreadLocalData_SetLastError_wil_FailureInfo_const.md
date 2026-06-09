# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180013408`
- end: `0x1800134d7`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800110c0`

## callees

- `0x1800127a0`
- `0x1800131a4`
- `0x180013408`

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
0x180013408  push    rbx
0x18001340a  push    rbp
0x18001340b  push    rsi
0x18001340c  push    rdi
0x18001340d  sub     rsp, 28h
0x180013411  cmp     qword ptr [rcx+18h], 0
0x180013416  mov     rsi, rdx
0x180013419  mov     edi, [rcx+10h]
0x18001341c  mov     rbx, rcx
0x18001341f  mov     ebp, 50h ; 'P'
0x180013424  jnz     short loc_18001345B
0x180013426  test    edi, edi
0x180013428  jz      short loc_18001345B
0x18001342a  mov     edx, 190h; dwBytes
0x18001342f  lea     ecx, [rbp-48h]; dwFlags
0x180013432  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180013437  mov     [rbx+18h], rax
0x18001343b  test    rax, rax
0x18001343e  jz      short loc_18001345B
0x180013440  mov     dword ptr [rbx+20h], 5
0x180013447  lea     rcx, [rax+190h]
0x18001344e  jmp     short loc_180013456
0x180013450  mov     [rax], bp
0x180013453  add     rax, rbp
0x180013456  cmp     rax, rcx
0x180013459  jnz     short loc_180013450
0x18001345b  mov     r9, [rbx+18h]
0x18001345f  test    r9, r9
0x180013462  jz      short loc_1800134CE
0x180013464  test    edi, edi
0x180013466  jz      short loc_180013494
0x180013468  movzx   eax, word ptr [rbx+20h]
0x18001346c  mov     rcx, r9
0x18001346f  lea     rdx, [rax+rax*4]
0x180013473  shl     rdx, 4
0x180013477  add     rdx, r9
0x18001347a  cmp     rcx, rdx
0x18001347d  jz      short loc_180013494
0x18001347f  mov     eax, [rbx+10h]
0x180013482  cmp     [rcx+4], eax
0x180013485  jbe     short loc_18001348F
0x180013487  mov     eax, [rsi+8]
0x18001348a  cmp     [rcx+8], eax
0x18001348d  jz      short loc_1800134CE
0x18001348f  add     rcx, rbp
0x180013492  jmp     short loc_18001347A
0x180013494  movzx   eax, word ptr [rbx+22h]
0x180013498  xor     edx, edx
0x18001349a  movzx   ecx, word ptr [rbx+20h]
0x18001349e  inc     eax
0x1800134a0  div     ecx
0x1800134a2  mov     rax, [rbx+8]
0x1800134a6  mov     r8d, 1
0x1800134ac  mov     [rbx+22h], dx
0x1800134b0  lock xadd [rax], r8d
0x1800134b5  movzx   eax, dx
0x1800134b8  inc     r8d; unsigned int
0x1800134bb  mov     rdx, rsi; struct wil::FailureInfo *
0x1800134be  lea     rcx, [rax+rax*4]
0x1800134c2  shl     rcx, 4
0x1800134c6  add     rcx, r9; this
0x1800134c9  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800134ce  add     rsp, 28h
0x1800134d2  pop     rdi
0x1800134d3  pop     rsi
0x1800134d4  pop     rbp
0x1800134d5  pop     rbx
0x1800134d6  retn
```
