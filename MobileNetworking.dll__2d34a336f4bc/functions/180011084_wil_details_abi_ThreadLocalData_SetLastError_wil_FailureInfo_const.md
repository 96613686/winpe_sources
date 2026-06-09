# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180011084`
- end: `0x180011153`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010090`

## callees

- `0x180010c88`
- `0x180010f0c`
- `0x180011084`

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
0x180011084  push    rbx
0x180011086  push    rbp
0x180011087  push    rsi
0x180011088  push    rdi
0x180011089  sub     rsp, 28h
0x18001108d  cmp     qword ptr [rcx+18h], 0
0x180011092  mov     rsi, rdx
0x180011095  mov     edi, [rcx+10h]
0x180011098  mov     rbx, rcx
0x18001109b  mov     ebp, 50h ; 'P'
0x1800110a0  jnz     short loc_1800110D7
0x1800110a2  test    edi, edi
0x1800110a4  jz      short loc_1800110D7
0x1800110a6  mov     edx, 190h; dwBytes
0x1800110ab  lea     ecx, [rbp-48h]; dwFlags
0x1800110ae  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800110b3  mov     [rbx+18h], rax
0x1800110b7  test    rax, rax
0x1800110ba  jz      short loc_1800110D7
0x1800110bc  mov     dword ptr [rbx+20h], 5
0x1800110c3  lea     rcx, [rax+190h]
0x1800110ca  jmp     short loc_1800110D2
0x1800110cc  mov     [rax], bp
0x1800110cf  add     rax, rbp
0x1800110d2  cmp     rax, rcx
0x1800110d5  jnz     short loc_1800110CC
0x1800110d7  mov     r9, [rbx+18h]
0x1800110db  test    r9, r9
0x1800110de  jz      short loc_18001114A
0x1800110e0  test    edi, edi
0x1800110e2  jz      short loc_180011110
0x1800110e4  movzx   eax, word ptr [rbx+20h]
0x1800110e8  mov     rcx, r9
0x1800110eb  lea     rdx, [rax+rax*4]
0x1800110ef  shl     rdx, 4
0x1800110f3  add     rdx, r9
0x1800110f6  cmp     rcx, rdx
0x1800110f9  jz      short loc_180011110
0x1800110fb  mov     eax, [rbx+10h]
0x1800110fe  cmp     [rcx+4], eax
0x180011101  jbe     short loc_18001110B
0x180011103  mov     eax, [rsi+8]
0x180011106  cmp     [rcx+8], eax
0x180011109  jz      short loc_18001114A
0x18001110b  add     rcx, rbp
0x18001110e  jmp     short loc_1800110F6
0x180011110  movzx   eax, word ptr [rbx+22h]
0x180011114  xor     edx, edx
0x180011116  movzx   ecx, word ptr [rbx+20h]
0x18001111a  inc     eax
0x18001111c  div     ecx
0x18001111e  mov     rax, [rbx+8]
0x180011122  mov     r8d, 1
0x180011128  mov     [rbx+22h], dx
0x18001112c  lock xadd [rax], r8d
0x180011131  movzx   eax, dx
0x180011134  inc     r8d; unsigned int
0x180011137  mov     rdx, rsi; struct wil::FailureInfo *
0x18001113a  lea     rcx, [rax+rax*4]
0x18001113e  shl     rcx, 4
0x180011142  add     rcx, r9; this
0x180011145  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18001114a  add     rsp, 28h
0x18001114e  pop     rdi
0x18001114f  pop     rsi
0x180011150  pop     rbp
0x180011151  pop     rbx
0x180011152  retn
```
