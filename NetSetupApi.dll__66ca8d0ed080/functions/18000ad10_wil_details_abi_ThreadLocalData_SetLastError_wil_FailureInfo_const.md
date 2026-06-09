# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000ad10`
- end: `0x18000ade6`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `214`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009ae0`

## callees

- `0x18000a8fc`
- `0x18000abd4`
- `0x18000ad10`

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
0x18000ad10  mov     [rsp+arg_10], rbx
0x18000ad15  push    rbp
0x18000ad16  push    rsi
0x18000ad17  push    rdi
0x18000ad18  sub     rsp, 20h
0x18000ad1c  cmp     qword ptr [rcx+18h], 0
0x18000ad21  mov     rsi, rdx
0x18000ad24  mov     edi, [rcx+10h]
0x18000ad27  mov     rbx, rcx
0x18000ad2a  mov     ebp, 50h ; 'P'
0x18000ad2f  jnz     short loc_18000AD66
0x18000ad31  test    edi, edi
0x18000ad33  jz      short loc_18000AD66
0x18000ad35  mov     edx, 190h; dwBytes
0x18000ad3a  lea     ecx, [rbp-48h]; dwFlags
0x18000ad3d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ad42  mov     [rbx+18h], rax
0x18000ad46  test    rax, rax
0x18000ad49  jz      short loc_18000AD66
0x18000ad4b  mov     dword ptr [rbx+20h], 5
0x18000ad52  lea     rcx, [rax+190h]
0x18000ad59  jmp     short loc_18000AD61
0x18000ad5b  mov     [rax], bp
0x18000ad5e  add     rax, rbp
0x18000ad61  cmp     rax, rcx
0x18000ad64  jnz     short loc_18000AD5B
0x18000ad66  mov     r9, [rbx+18h]
0x18000ad6a  test    r9, r9
0x18000ad6d  jz      short loc_18000ADD9
0x18000ad6f  test    edi, edi
0x18000ad71  jz      short loc_18000AD9F
0x18000ad73  movzx   eax, word ptr [rbx+20h]
0x18000ad77  mov     rcx, r9
0x18000ad7a  lea     rdx, [rax+rax*4]
0x18000ad7e  shl     rdx, 4
0x18000ad82  add     rdx, r9
0x18000ad85  cmp     rcx, rdx
0x18000ad88  jz      short loc_18000AD9F
0x18000ad8a  mov     eax, [rbx+10h]
0x18000ad8d  cmp     [rcx+4], eax
0x18000ad90  jbe     short loc_18000AD9A
0x18000ad92  mov     eax, [rsi+8]
0x18000ad95  cmp     [rcx+8], eax
0x18000ad98  jz      short loc_18000ADD9
0x18000ad9a  add     rcx, rbp
0x18000ad9d  jmp     short loc_18000AD85
0x18000ad9f  movzx   eax, word ptr [rbx+22h]
0x18000ada3  xor     edx, edx
0x18000ada5  movzx   ecx, word ptr [rbx+20h]
0x18000ada9  inc     eax
0x18000adab  div     ecx
0x18000adad  mov     rax, [rbx+8]
0x18000adb1  mov     r8d, 1
0x18000adb7  mov     [rbx+22h], dx
0x18000adbb  lock xadd [rax], r8d
0x18000adc0  movzx   eax, dx
0x18000adc3  inc     r8d; unsigned int
0x18000adc6  mov     rdx, rsi; struct wil::FailureInfo *
0x18000adc9  lea     rcx, [rax+rax*4]
0x18000adcd  shl     rcx, 4
0x18000add1  add     rcx, r9; this
0x18000add4  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000add9  mov     rbx, [rsp+38h+arg_10]
0x18000adde  add     rsp, 20h
0x18000ade2  pop     rdi
0x18000ade3  pop     rsi
0x18000ade4  pop     rbp
0x18000ade5  retn
```
