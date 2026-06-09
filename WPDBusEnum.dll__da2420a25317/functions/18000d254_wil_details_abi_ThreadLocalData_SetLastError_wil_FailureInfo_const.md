# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000d254`
- end: `0x18000d323`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bea0`

## callees

- `0x18000cb5c`
- `0x18000cebc`
- `0x18000d254`

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
0x18000d254  push    rbx
0x18000d256  push    rbp
0x18000d257  push    rsi
0x18000d258  push    rdi
0x18000d259  sub     rsp, 28h
0x18000d25d  cmp     qword ptr [rcx+18h], 0
0x18000d262  mov     rsi, rdx
0x18000d265  mov     edi, [rcx+10h]
0x18000d268  mov     rbx, rcx
0x18000d26b  mov     ebp, 50h ; 'P'
0x18000d270  jnz     short loc_18000D2A7
0x18000d272  test    edi, edi
0x18000d274  jz      short loc_18000D2A7
0x18000d276  mov     edx, 190h; dwBytes
0x18000d27b  lea     ecx, [rbp-48h]; dwFlags
0x18000d27e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d283  mov     [rbx+18h], rax
0x18000d287  test    rax, rax
0x18000d28a  jz      short loc_18000D2A7
0x18000d28c  mov     dword ptr [rbx+20h], 5
0x18000d293  lea     rcx, [rax+190h]
0x18000d29a  jmp     short loc_18000D2A2
0x18000d29c  mov     [rax], bp
0x18000d29f  add     rax, rbp
0x18000d2a2  cmp     rax, rcx
0x18000d2a5  jnz     short loc_18000D29C
0x18000d2a7  mov     r9, [rbx+18h]
0x18000d2ab  test    r9, r9
0x18000d2ae  jz      short loc_18000D31A
0x18000d2b0  test    edi, edi
0x18000d2b2  jz      short loc_18000D2E0
0x18000d2b4  movzx   eax, word ptr [rbx+20h]
0x18000d2b8  mov     rcx, r9
0x18000d2bb  lea     rdx, [rax+rax*4]
0x18000d2bf  shl     rdx, 4
0x18000d2c3  add     rdx, r9
0x18000d2c6  cmp     rcx, rdx
0x18000d2c9  jz      short loc_18000D2E0
0x18000d2cb  mov     eax, [rbx+10h]
0x18000d2ce  cmp     [rcx+4], eax
0x18000d2d1  jbe     short loc_18000D2DB
0x18000d2d3  mov     eax, [rsi+8]
0x18000d2d6  cmp     [rcx+8], eax
0x18000d2d9  jz      short loc_18000D31A
0x18000d2db  add     rcx, rbp
0x18000d2de  jmp     short loc_18000D2C6
0x18000d2e0  movzx   eax, word ptr [rbx+22h]
0x18000d2e4  xor     edx, edx
0x18000d2e6  movzx   ecx, word ptr [rbx+20h]
0x18000d2ea  inc     eax
0x18000d2ec  div     ecx
0x18000d2ee  mov     rax, [rbx+8]
0x18000d2f2  mov     r8d, 1
0x18000d2f8  mov     [rbx+22h], dx
0x18000d2fc  lock xadd [rax], r8d
0x18000d301  movzx   eax, dx
0x18000d304  inc     r8d; unsigned int
0x18000d307  mov     rdx, rsi; struct wil::FailureInfo *
0x18000d30a  lea     rcx, [rax+rax*4]
0x18000d30e  shl     rcx, 4
0x18000d312  add     rcx, r9; this
0x18000d315  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000d31a  add     rsp, 28h
0x18000d31e  pop     rdi
0x18000d31f  pop     rsi
0x18000d320  pop     rbp
0x18000d321  pop     rbx
0x18000d322  retn
```
