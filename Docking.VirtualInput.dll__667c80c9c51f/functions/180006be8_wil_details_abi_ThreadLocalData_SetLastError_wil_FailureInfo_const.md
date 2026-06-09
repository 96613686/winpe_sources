# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180006be8`
- end: `0x180006cb7`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005570`

## callees

- `0x1800065c0`
- `0x180006850`
- `0x180006be8`

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
0x180006be8  push    rbx
0x180006bea  push    rbp
0x180006beb  push    rsi
0x180006bec  push    rdi
0x180006bed  sub     rsp, 28h
0x180006bf1  cmp     qword ptr [rcx+18h], 0
0x180006bf6  mov     rsi, rdx
0x180006bf9  mov     edi, [rcx+10h]
0x180006bfc  mov     rbx, rcx
0x180006bff  mov     ebp, 50h ; 'P'
0x180006c04  jnz     short loc_180006C3B
0x180006c06  test    edi, edi
0x180006c08  jz      short loc_180006C3B
0x180006c0a  mov     edx, 190h; dwBytes
0x180006c0f  lea     ecx, [rbp-48h]; dwFlags
0x180006c12  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006c17  mov     [rbx+18h], rax
0x180006c1b  test    rax, rax
0x180006c1e  jz      short loc_180006C3B
0x180006c20  mov     dword ptr [rbx+20h], 5
0x180006c27  lea     rcx, [rax+190h]
0x180006c2e  jmp     short loc_180006C36
0x180006c30  mov     [rax], bp
0x180006c33  add     rax, rbp
0x180006c36  cmp     rax, rcx
0x180006c39  jnz     short loc_180006C30
0x180006c3b  mov     r9, [rbx+18h]
0x180006c3f  test    r9, r9
0x180006c42  jz      short loc_180006CAE
0x180006c44  test    edi, edi
0x180006c46  jz      short loc_180006C74
0x180006c48  movzx   eax, word ptr [rbx+20h]
0x180006c4c  mov     rcx, r9
0x180006c4f  lea     rdx, [rax+rax*4]
0x180006c53  shl     rdx, 4
0x180006c57  add     rdx, r9
0x180006c5a  cmp     rcx, rdx
0x180006c5d  jz      short loc_180006C74
0x180006c5f  mov     eax, [rbx+10h]
0x180006c62  cmp     [rcx+4], eax
0x180006c65  jbe     short loc_180006C6F
0x180006c67  mov     eax, [rsi+8]
0x180006c6a  cmp     [rcx+8], eax
0x180006c6d  jz      short loc_180006CAE
0x180006c6f  add     rcx, rbp
0x180006c72  jmp     short loc_180006C5A
0x180006c74  movzx   eax, word ptr [rbx+22h]
0x180006c78  xor     edx, edx
0x180006c7a  movzx   ecx, word ptr [rbx+20h]
0x180006c7e  inc     eax
0x180006c80  div     ecx
0x180006c82  mov     rax, [rbx+8]
0x180006c86  mov     r8d, 1
0x180006c8c  mov     [rbx+22h], dx
0x180006c90  lock xadd [rax], r8d
0x180006c95  movzx   eax, dx
0x180006c98  inc     r8d; unsigned int
0x180006c9b  mov     rdx, rsi; struct wil::FailureInfo *
0x180006c9e  lea     rcx, [rax+rax*4]
0x180006ca2  shl     rcx, 4
0x180006ca6  add     rcx, r9; this
0x180006ca9  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180006cae  add     rsp, 28h
0x180006cb2  pop     rdi
0x180006cb3  pop     rsi
0x180006cb4  pop     rbp
0x180006cb5  pop     rbx
0x180006cb6  retn
```
