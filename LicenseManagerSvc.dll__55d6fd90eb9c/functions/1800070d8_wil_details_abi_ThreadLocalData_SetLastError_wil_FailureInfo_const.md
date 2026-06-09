# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800070d8`
- end: `0x1800071a7`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800056e0`

## callees

- `0x1800067cc`
- `0x180006d40`
- `0x1800070d8`

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
0x1800070d8  push    rbx
0x1800070da  push    rbp
0x1800070db  push    rsi
0x1800070dc  push    rdi
0x1800070dd  sub     rsp, 28h
0x1800070e1  cmp     qword ptr [rcx+18h], 0
0x1800070e6  mov     rsi, rdx
0x1800070e9  mov     edi, [rcx+10h]
0x1800070ec  mov     rbx, rcx
0x1800070ef  mov     ebp, 50h ; 'P'
0x1800070f4  jnz     short loc_18000712B
0x1800070f6  test    edi, edi
0x1800070f8  jz      short loc_18000712B
0x1800070fa  mov     edx, 190h; dwBytes
0x1800070ff  lea     ecx, [rbp-48h]; dwFlags
0x180007102  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007107  mov     [rbx+18h], rax
0x18000710b  test    rax, rax
0x18000710e  jz      short loc_18000712B
0x180007110  mov     dword ptr [rbx+20h], 5
0x180007117  lea     rcx, [rax+190h]
0x18000711e  jmp     short loc_180007126
0x180007120  mov     [rax], bp
0x180007123  add     rax, rbp
0x180007126  cmp     rax, rcx
0x180007129  jnz     short loc_180007120
0x18000712b  mov     r9, [rbx+18h]
0x18000712f  test    r9, r9
0x180007132  jz      short loc_18000719E
0x180007134  test    edi, edi
0x180007136  jz      short loc_180007164
0x180007138  movzx   eax, word ptr [rbx+20h]
0x18000713c  mov     rcx, r9
0x18000713f  lea     rdx, [rax+rax*4]
0x180007143  shl     rdx, 4
0x180007147  add     rdx, r9
0x18000714a  cmp     rcx, rdx
0x18000714d  jz      short loc_180007164
0x18000714f  mov     eax, [rbx+10h]
0x180007152  cmp     [rcx+4], eax
0x180007155  jbe     short loc_18000715F
0x180007157  mov     eax, [rsi+8]
0x18000715a  cmp     [rcx+8], eax
0x18000715d  jz      short loc_18000719E
0x18000715f  add     rcx, rbp
0x180007162  jmp     short loc_18000714A
0x180007164  movzx   eax, word ptr [rbx+22h]
0x180007168  xor     edx, edx
0x18000716a  movzx   ecx, word ptr [rbx+20h]
0x18000716e  inc     eax
0x180007170  div     ecx
0x180007172  mov     rax, [rbx+8]
0x180007176  mov     r8d, 1
0x18000717c  mov     [rbx+22h], dx
0x180007180  lock xadd [rax], r8d
0x180007185  movzx   eax, dx
0x180007188  inc     r8d; unsigned int
0x18000718b  mov     rdx, rsi; struct wil::FailureInfo *
0x18000718e  lea     rcx, [rax+rax*4]
0x180007192  shl     rcx, 4
0x180007196  add     rcx, r9; this
0x180007199  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000719e  add     rsp, 28h
0x1800071a2  pop     rdi
0x1800071a3  pop     rsi
0x1800071a4  pop     rbp
0x1800071a5  pop     rbx
0x1800071a6  retn
```
