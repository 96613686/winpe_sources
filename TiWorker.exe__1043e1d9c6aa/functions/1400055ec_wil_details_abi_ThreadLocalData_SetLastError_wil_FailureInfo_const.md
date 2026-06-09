# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1400055ec`
- end: `0x1400056c2`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `214`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400041e0`

## callees

- `0x1400051f0`
- `0x140005474`
- `0x1400055ec`

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
0x1400055ec  mov     [rsp+arg_10], rbx
0x1400055f1  push    rbp
0x1400055f2  push    rsi
0x1400055f3  push    rdi
0x1400055f4  sub     rsp, 20h
0x1400055f8  cmp     qword ptr [rcx+18h], 0
0x1400055fd  mov     rsi, rdx
0x140005600  mov     edi, [rcx+10h]
0x140005603  mov     rbx, rcx
0x140005606  mov     ebp, 50h ; 'P'
0x14000560b  jnz     short loc_140005642
0x14000560d  test    edi, edi
0x14000560f  jz      short loc_140005642
0x140005611  mov     edx, 190h; dwBytes
0x140005616  lea     ecx, [rbp-48h]; dwFlags
0x140005619  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000561e  mov     [rbx+18h], rax
0x140005622  test    rax, rax
0x140005625  jz      short loc_140005642
0x140005627  mov     dword ptr [rbx+20h], 5
0x14000562e  lea     rcx, [rax+190h]
0x140005635  jmp     short loc_14000563D
0x140005637  mov     [rax], bp
0x14000563a  add     rax, rbp
0x14000563d  cmp     rax, rcx
0x140005640  jnz     short loc_140005637
0x140005642  mov     r9, [rbx+18h]
0x140005646  test    r9, r9
0x140005649  jz      short loc_1400056B5
0x14000564b  test    edi, edi
0x14000564d  jz      short loc_14000567B
0x14000564f  movzx   eax, word ptr [rbx+20h]
0x140005653  mov     rcx, r9
0x140005656  lea     rdx, [rax+rax*4]
0x14000565a  shl     rdx, 4
0x14000565e  add     rdx, r9
0x140005661  cmp     rcx, rdx
0x140005664  jz      short loc_14000567B
0x140005666  mov     eax, [rbx+10h]
0x140005669  cmp     [rcx+4], eax
0x14000566c  jbe     short loc_140005676
0x14000566e  mov     eax, [rsi+8]
0x140005671  cmp     [rcx+8], eax
0x140005674  jz      short loc_1400056B5
0x140005676  add     rcx, rbp
0x140005679  jmp     short loc_140005661
0x14000567b  movzx   eax, word ptr [rbx+22h]
0x14000567f  xor     edx, edx
0x140005681  movzx   ecx, word ptr [rbx+20h]
0x140005685  inc     eax
0x140005687  div     ecx
0x140005689  mov     rax, [rbx+8]
0x14000568d  mov     r8d, 1
0x140005693  mov     [rbx+22h], dx
0x140005697  lock xadd [rax], r8d
0x14000569c  movzx   eax, dx
0x14000569f  inc     r8d; unsigned int
0x1400056a2  mov     rdx, rsi; struct wil::FailureInfo *
0x1400056a5  lea     rcx, [rax+rax*4]
0x1400056a9  shl     rcx, 4
0x1400056ad  add     rcx, r9; this
0x1400056b0  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1400056b5  mov     rbx, [rsp+38h+arg_10]
0x1400056ba  add     rsp, 20h
0x1400056be  pop     rdi
0x1400056bf  pop     rsi
0x1400056c0  pop     rbp
0x1400056c1  retn
```
