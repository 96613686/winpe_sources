# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140006a30`
- end: `0x140006b00`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `208`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140004420`

## callees

- `0x140005bb8`
- `0x14000667c`
- `0x140006a30`

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
0x140006a30  push    rbx
0x140006a32  push    rbp
0x140006a33  push    rsi
0x140006a34  push    rdi
0x140006a35  sub     rsp, 28h
0x140006a39  cmp     qword ptr [rcx+18h], 0
0x140006a3e  mov     rsi, rdx
0x140006a41  mov     edi, [rcx+10h]
0x140006a44  mov     rbx, rcx
0x140006a47  mov     ebp, 50h ; 'P'
0x140006a4c  jnz     short loc_140006A83
0x140006a4e  test    edi, edi
0x140006a50  jz      short loc_140006A83
0x140006a52  mov     edx, 190h; dwBytes
0x140006a57  lea     ecx, [rbp-48h]; dwFlags
0x140006a5a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006a5f  mov     [rbx+18h], rax
0x140006a63  test    rax, rax
0x140006a66  jz      short loc_140006A83
0x140006a68  mov     dword ptr [rbx+20h], 5
0x140006a6f  lea     rcx, [rax+190h]
0x140006a76  jmp     short loc_140006A7E
0x140006a78  mov     [rax], bp
0x140006a7b  add     rax, rbp
0x140006a7e  cmp     rax, rcx
0x140006a81  jnz     short loc_140006A78
0x140006a83  mov     r9, [rbx+18h]
0x140006a87  test    r9, r9
0x140006a8a  jz      short loc_140006AF6
0x140006a8c  test    edi, edi
0x140006a8e  jz      short loc_140006ABC
0x140006a90  movzx   eax, word ptr [rbx+20h]
0x140006a94  mov     rcx, r9
0x140006a97  lea     rdx, [rax+rax*4]
0x140006a9b  shl     rdx, 4
0x140006a9f  add     rdx, r9
0x140006aa2  cmp     rcx, rdx
0x140006aa5  jz      short loc_140006ABC
0x140006aa7  mov     eax, [rbx+10h]
0x140006aaa  cmp     [rcx+4], eax
0x140006aad  jbe     short loc_140006AB7
0x140006aaf  mov     eax, [rsi+8]
0x140006ab2  cmp     [rcx+8], eax
0x140006ab5  jz      short loc_140006AF6
0x140006ab7  add     rcx, rbp
0x140006aba  jmp     short loc_140006AA2
0x140006abc  movzx   eax, word ptr [rbx+22h]
0x140006ac0  xor     edx, edx
0x140006ac2  movzx   ecx, word ptr [rbx+20h]
0x140006ac6  inc     eax
0x140006ac8  div     ecx
0x140006aca  mov     rax, [rbx+8]
0x140006ace  mov     r8d, 1
0x140006ad4  mov     [rbx+22h], dx
0x140006ad8  lock xadd [rax], r8d
0x140006add  movzx   eax, dx
0x140006ae0  inc     r8d; unsigned int
0x140006ae3  mov     rdx, rsi; struct wil::FailureInfo *
0x140006ae6  lea     rcx, [rax+rax*4]
0x140006aea  shl     rcx, 4
0x140006aee  add     rcx, r9; this
0x140006af1  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140006af6  add     rsp, 28h
0x140006afa  pop     rdi
0x140006afb  pop     rsi
0x140006afc  pop     rbp
0x140006afd  pop     rbx
0x140006afe  retn
```
