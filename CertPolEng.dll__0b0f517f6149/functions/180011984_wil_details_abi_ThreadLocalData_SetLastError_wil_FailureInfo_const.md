# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180011984`
- end: `0x180011a53`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fd40`

## callees

- `0x180010bf8`
- `0x180011510`
- `0x180011984`

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
0x180011984  push    rbx
0x180011986  push    rbp
0x180011987  push    rsi
0x180011988  push    rdi
0x180011989  sub     rsp, 28h
0x18001198d  cmp     qword ptr [rcx+18h], 0
0x180011992  mov     rsi, rdx
0x180011995  mov     edi, [rcx+10h]
0x180011998  mov     rbx, rcx
0x18001199b  mov     ebp, 50h ; 'P'
0x1800119a0  jnz     short loc_1800119D7
0x1800119a2  test    edi, edi
0x1800119a4  jz      short loc_1800119D7
0x1800119a6  mov     edx, 190h; dwBytes
0x1800119ab  lea     ecx, [rbp-48h]; dwFlags
0x1800119ae  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800119b3  mov     [rbx+18h], rax
0x1800119b7  test    rax, rax
0x1800119ba  jz      short loc_1800119D7
0x1800119bc  mov     dword ptr [rbx+20h], 5
0x1800119c3  lea     rcx, [rax+190h]
0x1800119ca  jmp     short loc_1800119D2
0x1800119cc  mov     [rax], bp
0x1800119cf  add     rax, rbp
0x1800119d2  cmp     rax, rcx
0x1800119d5  jnz     short loc_1800119CC
0x1800119d7  mov     r9, [rbx+18h]
0x1800119db  test    r9, r9
0x1800119de  jz      short loc_180011A4A
0x1800119e0  test    edi, edi
0x1800119e2  jz      short loc_180011A10
0x1800119e4  movzx   eax, word ptr [rbx+20h]
0x1800119e8  mov     rcx, r9
0x1800119eb  lea     rdx, [rax+rax*4]
0x1800119ef  shl     rdx, 4
0x1800119f3  add     rdx, r9
0x1800119f6  cmp     rcx, rdx
0x1800119f9  jz      short loc_180011A10
0x1800119fb  mov     eax, [rbx+10h]
0x1800119fe  cmp     [rcx+4], eax
0x180011a01  jbe     short loc_180011A0B
0x180011a03  mov     eax, [rsi+8]
0x180011a06  cmp     [rcx+8], eax
0x180011a09  jz      short loc_180011A4A
0x180011a0b  add     rcx, rbp
0x180011a0e  jmp     short loc_1800119F6
0x180011a10  movzx   eax, word ptr [rbx+22h]
0x180011a14  xor     edx, edx
0x180011a16  movzx   ecx, word ptr [rbx+20h]
0x180011a1a  inc     eax
0x180011a1c  div     ecx
0x180011a1e  mov     rax, [rbx+8]
0x180011a22  mov     r8d, 1
0x180011a28  mov     [rbx+22h], dx
0x180011a2c  lock xadd [rax], r8d
0x180011a31  movzx   eax, dx
0x180011a34  inc     r8d; unsigned int
0x180011a37  mov     rdx, rsi; struct wil::FailureInfo *
0x180011a3a  lea     rcx, [rax+rax*4]
0x180011a3e  shl     rcx, 4
0x180011a42  add     rcx, r9; this
0x180011a45  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180011a4a  add     rsp, 28h
0x180011a4e  pop     rdi
0x180011a4f  pop     rsi
0x180011a50  pop     rbp
0x180011a51  pop     rbx
0x180011a52  retn
```
