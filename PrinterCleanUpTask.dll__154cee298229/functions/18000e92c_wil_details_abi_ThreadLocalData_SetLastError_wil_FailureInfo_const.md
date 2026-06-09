# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000e92c`
- end: `0x18000e9fb`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c2b0`

## callees

- `0x18000decc`
- `0x18000e7a8`
- `0x18000e92c`

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
0x18000e92c  push    rbx
0x18000e92e  push    rbp
0x18000e92f  push    rsi
0x18000e930  push    rdi
0x18000e931  sub     rsp, 28h
0x18000e935  cmp     qword ptr [rcx+18h], 0
0x18000e93a  mov     rsi, rdx
0x18000e93d  mov     edi, [rcx+10h]
0x18000e940  mov     rbx, rcx
0x18000e943  mov     ebp, 50h ; 'P'
0x18000e948  jnz     short loc_18000E97F
0x18000e94a  test    edi, edi
0x18000e94c  jz      short loc_18000E97F
0x18000e94e  mov     edx, 190h; dwBytes
0x18000e953  lea     ecx, [rbp-48h]; dwFlags
0x18000e956  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000e95b  mov     [rbx+18h], rax
0x18000e95f  test    rax, rax
0x18000e962  jz      short loc_18000E97F
0x18000e964  mov     dword ptr [rbx+20h], 5
0x18000e96b  lea     rcx, [rax+190h]
0x18000e972  jmp     short loc_18000E97A
0x18000e974  mov     [rax], bp
0x18000e977  add     rax, rbp
0x18000e97a  cmp     rax, rcx
0x18000e97d  jnz     short loc_18000E974
0x18000e97f  mov     r9, [rbx+18h]
0x18000e983  test    r9, r9
0x18000e986  jz      short loc_18000E9F2
0x18000e988  test    edi, edi
0x18000e98a  jz      short loc_18000E9B8
0x18000e98c  movzx   eax, word ptr [rbx+20h]
0x18000e990  mov     rcx, r9
0x18000e993  lea     rdx, [rax+rax*4]
0x18000e997  shl     rdx, 4
0x18000e99b  add     rdx, r9
0x18000e99e  cmp     rcx, rdx
0x18000e9a1  jz      short loc_18000E9B8
0x18000e9a3  mov     eax, [rbx+10h]
0x18000e9a6  cmp     [rcx+4], eax
0x18000e9a9  jbe     short loc_18000E9B3
0x18000e9ab  mov     eax, [rsi+8]
0x18000e9ae  cmp     [rcx+8], eax
0x18000e9b1  jz      short loc_18000E9F2
0x18000e9b3  add     rcx, rbp
0x18000e9b6  jmp     short loc_18000E99E
0x18000e9b8  movzx   eax, word ptr [rbx+22h]
0x18000e9bc  xor     edx, edx
0x18000e9be  movzx   ecx, word ptr [rbx+20h]
0x18000e9c2  inc     eax
0x18000e9c4  div     ecx
0x18000e9c6  mov     rax, [rbx+8]
0x18000e9ca  mov     r8d, 1
0x18000e9d0  mov     [rbx+22h], dx
0x18000e9d4  lock xadd [rax], r8d
0x18000e9d9  movzx   eax, dx
0x18000e9dc  inc     r8d; unsigned int
0x18000e9df  mov     rdx, rsi; struct wil::FailureInfo *
0x18000e9e2  lea     rcx, [rax+rax*4]
0x18000e9e6  shl     rcx, 4
0x18000e9ea  add     rcx, r9; this
0x18000e9ed  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000e9f2  add     rsp, 28h
0x18000e9f6  pop     rdi
0x18000e9f7  pop     rsi
0x18000e9f8  pop     rbp
0x18000e9f9  pop     rbx
0x18000e9fa  retn
```
