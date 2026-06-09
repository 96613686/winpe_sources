# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140005ae8`
- end: `0x140005bb7`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400044b0`

## callees

- `0x140005488`
- `0x140005750`
- `0x140005ae8`

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
0x140005ae8  push    rbx
0x140005aea  push    rbp
0x140005aeb  push    rsi
0x140005aec  push    rdi
0x140005aed  sub     rsp, 28h
0x140005af1  cmp     qword ptr [rcx+18h], 0
0x140005af6  mov     rsi, rdx
0x140005af9  mov     edi, [rcx+10h]
0x140005afc  mov     rbx, rcx
0x140005aff  mov     ebp, 50h ; 'P'
0x140005b04  jnz     short loc_140005B3B
0x140005b06  test    edi, edi
0x140005b08  jz      short loc_140005B3B
0x140005b0a  mov     edx, 190h; dwBytes
0x140005b0f  lea     ecx, [rbp-48h]; dwFlags
0x140005b12  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005b17  mov     [rbx+18h], rax
0x140005b1b  test    rax, rax
0x140005b1e  jz      short loc_140005B3B
0x140005b20  mov     dword ptr [rbx+20h], 5
0x140005b27  lea     rcx, [rax+190h]
0x140005b2e  jmp     short loc_140005B36
0x140005b30  mov     [rax], bp
0x140005b33  add     rax, rbp
0x140005b36  cmp     rax, rcx
0x140005b39  jnz     short loc_140005B30
0x140005b3b  mov     r9, [rbx+18h]
0x140005b3f  test    r9, r9
0x140005b42  jz      short loc_140005BAE
0x140005b44  test    edi, edi
0x140005b46  jz      short loc_140005B74
0x140005b48  movzx   eax, word ptr [rbx+20h]
0x140005b4c  mov     rcx, r9
0x140005b4f  lea     rdx, [rax+rax*4]
0x140005b53  shl     rdx, 4
0x140005b57  add     rdx, r9
0x140005b5a  cmp     rcx, rdx
0x140005b5d  jz      short loc_140005B74
0x140005b5f  mov     eax, [rbx+10h]
0x140005b62  cmp     [rcx+4], eax
0x140005b65  jbe     short loc_140005B6F
0x140005b67  mov     eax, [rsi+8]
0x140005b6a  cmp     [rcx+8], eax
0x140005b6d  jz      short loc_140005BAE
0x140005b6f  add     rcx, rbp
0x140005b72  jmp     short loc_140005B5A
0x140005b74  movzx   eax, word ptr [rbx+22h]
0x140005b78  xor     edx, edx
0x140005b7a  movzx   ecx, word ptr [rbx+20h]
0x140005b7e  inc     eax
0x140005b80  div     ecx
0x140005b82  mov     rax, [rbx+8]
0x140005b86  mov     r8d, 1
0x140005b8c  mov     [rbx+22h], dx
0x140005b90  lock xadd [rax], r8d
0x140005b95  movzx   eax, dx
0x140005b98  inc     r8d; unsigned int
0x140005b9b  mov     rdx, rsi; struct wil::FailureInfo *
0x140005b9e  lea     rcx, [rax+rax*4]
0x140005ba2  shl     rcx, 4
0x140005ba6  add     rcx, r9; this
0x140005ba9  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140005bae  add     rsp, 28h
0x140005bb2  pop     rdi
0x140005bb3  pop     rsi
0x140005bb4  pop     rbp
0x140005bb5  pop     rbx
0x140005bb6  retn
```
