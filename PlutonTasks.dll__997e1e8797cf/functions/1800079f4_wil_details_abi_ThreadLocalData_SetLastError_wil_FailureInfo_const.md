# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800079f4`
- end: `0x180007ac3`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004cc0`

## callees

- `0x1800062c4`
- `0x180007570`
- `0x1800079f4`

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
0x1800079f4  push    rbx
0x1800079f6  push    rbp
0x1800079f7  push    rsi
0x1800079f8  push    rdi
0x1800079f9  sub     rsp, 28h
0x1800079fd  cmp     qword ptr [rcx+18h], 0
0x180007a02  mov     rsi, rdx
0x180007a05  mov     edi, [rcx+10h]
0x180007a08  mov     rbx, rcx
0x180007a0b  mov     ebp, 50h ; 'P'
0x180007a10  jnz     short loc_180007A47
0x180007a12  test    edi, edi
0x180007a14  jz      short loc_180007A47
0x180007a16  mov     edx, 190h; dwBytes
0x180007a1b  lea     ecx, [rbp-48h]; dwFlags
0x180007a1e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007a23  mov     [rbx+18h], rax
0x180007a27  test    rax, rax
0x180007a2a  jz      short loc_180007A47
0x180007a2c  mov     dword ptr [rbx+20h], 5
0x180007a33  lea     rcx, [rax+190h]
0x180007a3a  jmp     short loc_180007A42
0x180007a3c  mov     [rax], bp
0x180007a3f  add     rax, rbp
0x180007a42  cmp     rax, rcx
0x180007a45  jnz     short loc_180007A3C
0x180007a47  mov     r9, [rbx+18h]
0x180007a4b  test    r9, r9
0x180007a4e  jz      short loc_180007ABA
0x180007a50  test    edi, edi
0x180007a52  jz      short loc_180007A80
0x180007a54  movzx   eax, word ptr [rbx+20h]
0x180007a58  mov     rcx, r9
0x180007a5b  lea     rdx, [rax+rax*4]
0x180007a5f  shl     rdx, 4
0x180007a63  add     rdx, r9
0x180007a66  cmp     rcx, rdx
0x180007a69  jz      short loc_180007A80
0x180007a6b  mov     eax, [rbx+10h]
0x180007a6e  cmp     [rcx+4], eax
0x180007a71  jbe     short loc_180007A7B
0x180007a73  mov     eax, [rsi+8]
0x180007a76  cmp     [rcx+8], eax
0x180007a79  jz      short loc_180007ABA
0x180007a7b  add     rcx, rbp
0x180007a7e  jmp     short loc_180007A66
0x180007a80  movzx   eax, word ptr [rbx+22h]
0x180007a84  xor     edx, edx
0x180007a86  movzx   ecx, word ptr [rbx+20h]
0x180007a8a  inc     eax
0x180007a8c  div     ecx
0x180007a8e  mov     rax, [rbx+8]
0x180007a92  mov     r8d, 1
0x180007a98  mov     [rbx+22h], dx
0x180007a9c  lock xadd [rax], r8d
0x180007aa1  movzx   eax, dx
0x180007aa4  inc     r8d; unsigned int
0x180007aa7  mov     rdx, rsi; struct wil::FailureInfo *
0x180007aaa  lea     rcx, [rax+rax*4]
0x180007aae  shl     rcx, 4
0x180007ab2  add     rcx, r9; this
0x180007ab5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007aba  add     rsp, 28h
0x180007abe  pop     rdi
0x180007abf  pop     rsi
0x180007ac0  pop     rbp
0x180007ac1  pop     rbx
0x180007ac2  retn
```
