# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1400064f8`
- end: `0x1400065c7`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140003df0`

## callees

- `0x140005258`
- `0x140006070`
- `0x1400064f8`

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
0x1400064f8  push    rbx
0x1400064fa  push    rbp
0x1400064fb  push    rsi
0x1400064fc  push    rdi
0x1400064fd  sub     rsp, 28h
0x140006501  cmp     qword ptr [rcx+18h], 0
0x140006506  mov     rsi, rdx
0x140006509  mov     edi, [rcx+10h]
0x14000650c  mov     rbx, rcx
0x14000650f  mov     ebp, 50h ; 'P'
0x140006514  jnz     short loc_14000654B
0x140006516  test    edi, edi
0x140006518  jz      short loc_14000654B
0x14000651a  mov     edx, 190h; dwBytes
0x14000651f  lea     ecx, [rbp-48h]; dwFlags
0x140006522  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006527  mov     [rbx+18h], rax
0x14000652b  test    rax, rax
0x14000652e  jz      short loc_14000654B
0x140006530  mov     dword ptr [rbx+20h], 5
0x140006537  lea     rcx, [rax+190h]
0x14000653e  jmp     short loc_140006546
0x140006540  mov     [rax], bp
0x140006543  add     rax, rbp
0x140006546  cmp     rax, rcx
0x140006549  jnz     short loc_140006540
0x14000654b  mov     r9, [rbx+18h]
0x14000654f  test    r9, r9
0x140006552  jz      short loc_1400065BE
0x140006554  test    edi, edi
0x140006556  jz      short loc_140006584
0x140006558  movzx   eax, word ptr [rbx+20h]
0x14000655c  mov     rcx, r9
0x14000655f  lea     rdx, [rax+rax*4]
0x140006563  shl     rdx, 4
0x140006567  add     rdx, r9
0x14000656a  cmp     rcx, rdx
0x14000656d  jz      short loc_140006584
0x14000656f  mov     eax, [rbx+10h]
0x140006572  cmp     [rcx+4], eax
0x140006575  jbe     short loc_14000657F
0x140006577  mov     eax, [rsi+8]
0x14000657a  cmp     [rcx+8], eax
0x14000657d  jz      short loc_1400065BE
0x14000657f  add     rcx, rbp
0x140006582  jmp     short loc_14000656A
0x140006584  movzx   eax, word ptr [rbx+22h]
0x140006588  xor     edx, edx
0x14000658a  movzx   ecx, word ptr [rbx+20h]
0x14000658e  inc     eax
0x140006590  div     ecx
0x140006592  mov     rax, [rbx+8]
0x140006596  mov     r8d, 1
0x14000659c  mov     [rbx+22h], dx
0x1400065a0  lock xadd [rax], r8d
0x1400065a5  movzx   eax, dx
0x1400065a8  inc     r8d; unsigned int
0x1400065ab  mov     rdx, rsi; struct wil::FailureInfo *
0x1400065ae  lea     rcx, [rax+rax*4]
0x1400065b2  shl     rcx, 4
0x1400065b6  add     rcx, r9; this
0x1400065b9  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1400065be  add     rsp, 28h
0x1400065c2  pop     rdi
0x1400065c3  pop     rsi
0x1400065c4  pop     rbp
0x1400065c5  pop     rbx
0x1400065c6  retn
```
