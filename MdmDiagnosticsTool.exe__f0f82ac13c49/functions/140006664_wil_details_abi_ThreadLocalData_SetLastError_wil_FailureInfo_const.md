# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140006664`
- end: `0x140006733`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400041c0`

## callees

- `0x1400058c8`
- `0x1400062cc`
- `0x140006664`

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
0x140006664  push    rbx
0x140006666  push    rbp
0x140006667  push    rsi
0x140006668  push    rdi
0x140006669  sub     rsp, 28h
0x14000666d  cmp     qword ptr [rcx+18h], 0
0x140006672  mov     rsi, rdx
0x140006675  mov     edi, [rcx+10h]
0x140006678  mov     rbx, rcx
0x14000667b  mov     ebp, 50h ; 'P'
0x140006680  jnz     short loc_1400066B7
0x140006682  test    edi, edi
0x140006684  jz      short loc_1400066B7
0x140006686  mov     edx, 190h; dwBytes
0x14000668b  lea     ecx, [rbp-48h]; dwFlags
0x14000668e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006693  mov     [rbx+18h], rax
0x140006697  test    rax, rax
0x14000669a  jz      short loc_1400066B7
0x14000669c  mov     dword ptr [rbx+20h], 5
0x1400066a3  lea     rcx, [rax+190h]
0x1400066aa  jmp     short loc_1400066B2
0x1400066ac  mov     [rax], bp
0x1400066af  add     rax, rbp
0x1400066b2  cmp     rax, rcx
0x1400066b5  jnz     short loc_1400066AC
0x1400066b7  mov     r9, [rbx+18h]
0x1400066bb  test    r9, r9
0x1400066be  jz      short loc_14000672A
0x1400066c0  test    edi, edi
0x1400066c2  jz      short loc_1400066F0
0x1400066c4  movzx   eax, word ptr [rbx+20h]
0x1400066c8  mov     rcx, r9
0x1400066cb  lea     rdx, [rax+rax*4]
0x1400066cf  shl     rdx, 4
0x1400066d3  add     rdx, r9
0x1400066d6  cmp     rcx, rdx
0x1400066d9  jz      short loc_1400066F0
0x1400066db  mov     eax, [rbx+10h]
0x1400066de  cmp     [rcx+4], eax
0x1400066e1  jbe     short loc_1400066EB
0x1400066e3  mov     eax, [rsi+8]
0x1400066e6  cmp     [rcx+8], eax
0x1400066e9  jz      short loc_14000672A
0x1400066eb  add     rcx, rbp
0x1400066ee  jmp     short loc_1400066D6
0x1400066f0  movzx   eax, word ptr [rbx+22h]
0x1400066f4  xor     edx, edx
0x1400066f6  movzx   ecx, word ptr [rbx+20h]
0x1400066fa  inc     eax
0x1400066fc  div     ecx
0x1400066fe  mov     rax, [rbx+8]
0x140006702  mov     r8d, 1
0x140006708  mov     [rbx+22h], dx
0x14000670c  lock xadd [rax], r8d
0x140006711  movzx   eax, dx
0x140006714  inc     r8d; unsigned int
0x140006717  mov     rdx, rsi; struct wil::FailureInfo *
0x14000671a  lea     rcx, [rax+rax*4]
0x14000671e  shl     rcx, 4
0x140006722  add     rcx, r9; this
0x140006725  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000672a  add     rsp, 28h
0x14000672e  pop     rdi
0x14000672f  pop     rsi
0x140006730  pop     rbp
0x140006731  pop     rbx
0x140006732  retn
```
