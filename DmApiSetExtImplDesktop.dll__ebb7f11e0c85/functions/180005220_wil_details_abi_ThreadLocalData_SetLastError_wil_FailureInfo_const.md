# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180005220`
- end: `0x1800052f0`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `208`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003830`

## callees

- `0x180004978`
- `0x180004e6c`
- `0x180005220`

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
0x180005220  push    rbx
0x180005222  push    rbp
0x180005223  push    rsi
0x180005224  push    rdi
0x180005225  sub     rsp, 28h
0x180005229  cmp     qword ptr [rcx+18h], 0
0x18000522e  mov     rsi, rdx
0x180005231  mov     edi, [rcx+10h]
0x180005234  mov     rbx, rcx
0x180005237  mov     ebp, 50h ; 'P'
0x18000523c  jnz     short loc_180005273
0x18000523e  test    edi, edi
0x180005240  jz      short loc_180005273
0x180005242  mov     edx, 190h; dwBytes
0x180005247  lea     ecx, [rbp-48h]; dwFlags
0x18000524a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000524f  mov     [rbx+18h], rax
0x180005253  test    rax, rax
0x180005256  jz      short loc_180005273
0x180005258  mov     dword ptr [rbx+20h], 5
0x18000525f  lea     rcx, [rax+190h]
0x180005266  jmp     short loc_18000526E
0x180005268  mov     [rax], bp
0x18000526b  add     rax, rbp
0x18000526e  cmp     rax, rcx
0x180005271  jnz     short loc_180005268
0x180005273  mov     r9, [rbx+18h]
0x180005277  test    r9, r9
0x18000527a  jz      short loc_1800052E6
0x18000527c  test    edi, edi
0x18000527e  jz      short loc_1800052AC
0x180005280  movzx   eax, word ptr [rbx+20h]
0x180005284  mov     rcx, r9
0x180005287  lea     rdx, [rax+rax*4]
0x18000528b  shl     rdx, 4
0x18000528f  add     rdx, r9
0x180005292  cmp     rcx, rdx
0x180005295  jz      short loc_1800052AC
0x180005297  mov     eax, [rbx+10h]
0x18000529a  cmp     [rcx+4], eax
0x18000529d  jbe     short loc_1800052A7
0x18000529f  mov     eax, [rsi+8]
0x1800052a2  cmp     [rcx+8], eax
0x1800052a5  jz      short loc_1800052E6
0x1800052a7  add     rcx, rbp
0x1800052aa  jmp     short loc_180005292
0x1800052ac  movzx   eax, word ptr [rbx+22h]
0x1800052b0  xor     edx, edx
0x1800052b2  movzx   ecx, word ptr [rbx+20h]
0x1800052b6  inc     eax
0x1800052b8  div     ecx
0x1800052ba  mov     rax, [rbx+8]
0x1800052be  mov     r8d, 1
0x1800052c4  mov     [rbx+22h], dx
0x1800052c8  lock xadd [rax], r8d
0x1800052cd  movzx   eax, dx
0x1800052d0  inc     r8d; unsigned int
0x1800052d3  mov     rdx, rsi; struct wil::FailureInfo *
0x1800052d6  lea     rcx, [rax+rax*4]
0x1800052da  shl     rcx, 4
0x1800052de  add     rcx, r9; this
0x1800052e1  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800052e6  add     rsp, 28h
0x1800052ea  pop     rdi
0x1800052eb  pop     rsi
0x1800052ec  pop     rbp
0x1800052ed  pop     rbx
0x1800052ee  retn
```
