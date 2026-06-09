# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000f94c`
- end: `0x18000fa1c`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `208`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a3f0`

## callees

- `0x18000b8b4`
- `0x18000f650`
- `0x18000f94c`

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
0x18000f94c  push    rbx
0x18000f94e  push    rbp
0x18000f94f  push    rsi
0x18000f950  push    rdi
0x18000f951  sub     rsp, 28h
0x18000f955  cmp     qword ptr [rcx+18h], 0
0x18000f95a  mov     rsi, rdx
0x18000f95d  mov     edi, [rcx+10h]
0x18000f960  mov     rbx, rcx
0x18000f963  mov     ebp, 50h ; 'P'
0x18000f968  jnz     short loc_18000F99F
0x18000f96a  test    edi, edi
0x18000f96c  jz      short loc_18000F99F
0x18000f96e  mov     edx, 190h; dwBytes
0x18000f973  lea     ecx, [rbp-48h]; dwFlags
0x18000f976  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000f97b  mov     [rbx+18h], rax
0x18000f97f  test    rax, rax
0x18000f982  jz      short loc_18000F99F
0x18000f984  mov     dword ptr [rbx+20h], 5
0x18000f98b  lea     rcx, [rax+190h]
0x18000f992  jmp     short loc_18000F99A
0x18000f994  mov     [rax], bp
0x18000f997  add     rax, rbp
0x18000f99a  cmp     rax, rcx
0x18000f99d  jnz     short loc_18000F994
0x18000f99f  mov     r9, [rbx+18h]
0x18000f9a3  test    r9, r9
0x18000f9a6  jz      short loc_18000FA12
0x18000f9a8  test    edi, edi
0x18000f9aa  jz      short loc_18000F9D8
0x18000f9ac  movzx   eax, word ptr [rbx+20h]
0x18000f9b0  mov     rcx, r9
0x18000f9b3  lea     rdx, [rax+rax*4]
0x18000f9b7  shl     rdx, 4
0x18000f9bb  add     rdx, r9
0x18000f9be  cmp     rcx, rdx
0x18000f9c1  jz      short loc_18000F9D8
0x18000f9c3  mov     eax, [rbx+10h]
0x18000f9c6  cmp     [rcx+4], eax
0x18000f9c9  jbe     short loc_18000F9D3
0x18000f9cb  mov     eax, [rsi+8]
0x18000f9ce  cmp     [rcx+8], eax
0x18000f9d1  jz      short loc_18000FA12
0x18000f9d3  add     rcx, rbp
0x18000f9d6  jmp     short loc_18000F9BE
0x18000f9d8  movzx   eax, word ptr [rbx+22h]
0x18000f9dc  xor     edx, edx
0x18000f9de  movzx   ecx, word ptr [rbx+20h]
0x18000f9e2  inc     eax
0x18000f9e4  div     ecx
0x18000f9e6  mov     rax, [rbx+8]
0x18000f9ea  mov     r8d, 1
0x18000f9f0  mov     [rbx+22h], dx
0x18000f9f4  lock xadd [rax], r8d
0x18000f9f9  movzx   eax, dx
0x18000f9fc  inc     r8d; unsigned int
0x18000f9ff  mov     rdx, rsi; struct wil::FailureInfo *
0x18000fa02  lea     rcx, [rax+rax*4]
0x18000fa06  shl     rcx, 4
0x18000fa0a  add     rcx, r9; this
0x18000fa0d  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000fa12  add     rsp, 28h
0x18000fa16  pop     rdi
0x18000fa17  pop     rsi
0x18000fa18  pop     rbp
0x18000fa19  pop     rbx
0x18000fa1a  retn
```
