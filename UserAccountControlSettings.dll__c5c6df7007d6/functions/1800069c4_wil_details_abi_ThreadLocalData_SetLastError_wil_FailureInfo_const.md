# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800069c4`
- end: `0x180006a93`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005340`

## callees

- `0x180006450`
- `0x18000684c`
- `0x1800069c4`

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
0x1800069c4  push    rbx
0x1800069c6  push    rbp
0x1800069c7  push    rsi
0x1800069c8  push    rdi
0x1800069c9  sub     rsp, 28h
0x1800069cd  cmp     qword ptr [rcx+18h], 0
0x1800069d2  mov     rsi, rdx
0x1800069d5  mov     edi, [rcx+10h]
0x1800069d8  mov     rbx, rcx
0x1800069db  mov     ebp, 50h ; 'P'
0x1800069e0  jnz     short loc_180006A17
0x1800069e2  test    edi, edi
0x1800069e4  jz      short loc_180006A17
0x1800069e6  mov     edx, 190h; dwBytes
0x1800069eb  lea     ecx, [rbp-48h]; dwFlags
0x1800069ee  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800069f3  mov     [rbx+18h], rax
0x1800069f7  test    rax, rax
0x1800069fa  jz      short loc_180006A17
0x1800069fc  mov     dword ptr [rbx+20h], 5
0x180006a03  lea     rcx, [rax+190h]
0x180006a0a  jmp     short loc_180006A12
0x180006a0c  mov     [rax], bp
0x180006a0f  add     rax, rbp
0x180006a12  cmp     rax, rcx
0x180006a15  jnz     short loc_180006A0C
0x180006a17  mov     r9, [rbx+18h]
0x180006a1b  test    r9, r9
0x180006a1e  jz      short loc_180006A8A
0x180006a20  test    edi, edi
0x180006a22  jz      short loc_180006A50
0x180006a24  movzx   eax, word ptr [rbx+20h]
0x180006a28  mov     rcx, r9
0x180006a2b  lea     rdx, [rax+rax*4]
0x180006a2f  shl     rdx, 4
0x180006a33  add     rdx, r9
0x180006a36  cmp     rcx, rdx
0x180006a39  jz      short loc_180006A50
0x180006a3b  mov     eax, [rbx+10h]
0x180006a3e  cmp     [rcx+4], eax
0x180006a41  jbe     short loc_180006A4B
0x180006a43  mov     eax, [rsi+8]
0x180006a46  cmp     [rcx+8], eax
0x180006a49  jz      short loc_180006A8A
0x180006a4b  add     rcx, rbp
0x180006a4e  jmp     short loc_180006A36
0x180006a50  movzx   eax, word ptr [rbx+22h]
0x180006a54  xor     edx, edx
0x180006a56  movzx   ecx, word ptr [rbx+20h]
0x180006a5a  inc     eax
0x180006a5c  div     ecx
0x180006a5e  mov     rax, [rbx+8]
0x180006a62  mov     r8d, 1
0x180006a68  mov     [rbx+22h], dx
0x180006a6c  lock xadd [rax], r8d
0x180006a71  movzx   eax, dx
0x180006a74  inc     r8d; unsigned int
0x180006a77  mov     rdx, rsi; struct wil::FailureInfo *
0x180006a7a  lea     rcx, [rax+rax*4]
0x180006a7e  shl     rcx, 4
0x180006a82  add     rcx, r9; this
0x180006a85  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180006a8a  add     rsp, 28h
0x180006a8e  pop     rdi
0x180006a8f  pop     rsi
0x180006a90  pop     rbp
0x180006a91  pop     rbx
0x180006a92  retn
```
