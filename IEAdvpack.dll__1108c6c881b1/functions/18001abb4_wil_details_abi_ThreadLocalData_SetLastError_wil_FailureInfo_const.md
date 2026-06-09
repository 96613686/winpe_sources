# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18001abb4`
- end: `0x18001ac83`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018f80`

## callees

- `0x18001a760`
- `0x18001aa3c`
- `0x18001abb4`

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
0x18001abb4  push    rbx
0x18001abb6  push    rbp
0x18001abb7  push    rsi
0x18001abb8  push    rdi
0x18001abb9  sub     rsp, 28h
0x18001abbd  cmp     qword ptr [rcx+18h], 0
0x18001abc2  mov     rsi, rdx
0x18001abc5  mov     edi, [rcx+10h]
0x18001abc8  mov     rbx, rcx
0x18001abcb  mov     ebp, 50h ; 'P'
0x18001abd0  jnz     short loc_18001AC07
0x18001abd2  test    edi, edi
0x18001abd4  jz      short loc_18001AC07
0x18001abd6  mov     edx, 190h; dwBytes
0x18001abdb  lea     ecx, [rbp-48h]; dwFlags
0x18001abde  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001abe3  mov     [rbx+18h], rax
0x18001abe7  test    rax, rax
0x18001abea  jz      short loc_18001AC07
0x18001abec  mov     dword ptr [rbx+20h], 5
0x18001abf3  lea     rcx, [rax+190h]
0x18001abfa  jmp     short loc_18001AC02
0x18001abfc  mov     [rax], bp
0x18001abff  add     rax, rbp
0x18001ac02  cmp     rax, rcx
0x18001ac05  jnz     short loc_18001ABFC
0x18001ac07  mov     r9, [rbx+18h]
0x18001ac0b  test    r9, r9
0x18001ac0e  jz      short loc_18001AC7A
0x18001ac10  test    edi, edi
0x18001ac12  jz      short loc_18001AC40
0x18001ac14  movzx   eax, word ptr [rbx+20h]
0x18001ac18  mov     rcx, r9
0x18001ac1b  lea     rdx, [rax+rax*4]
0x18001ac1f  shl     rdx, 4
0x18001ac23  add     rdx, r9
0x18001ac26  cmp     rcx, rdx
0x18001ac29  jz      short loc_18001AC40
0x18001ac2b  mov     eax, [rbx+10h]
0x18001ac2e  cmp     [rcx+4], eax
0x18001ac31  jbe     short loc_18001AC3B
0x18001ac33  mov     eax, [rsi+8]
0x18001ac36  cmp     [rcx+8], eax
0x18001ac39  jz      short loc_18001AC7A
0x18001ac3b  add     rcx, rbp
0x18001ac3e  jmp     short loc_18001AC26
0x18001ac40  movzx   eax, word ptr [rbx+22h]
0x18001ac44  xor     edx, edx
0x18001ac46  movzx   ecx, word ptr [rbx+20h]
0x18001ac4a  inc     eax
0x18001ac4c  div     ecx
0x18001ac4e  mov     rax, [rbx+8]
0x18001ac52  mov     r8d, 1
0x18001ac58  mov     [rbx+22h], dx
0x18001ac5c  lock xadd [rax], r8d
0x18001ac61  movzx   eax, dx
0x18001ac64  inc     r8d; unsigned int
0x18001ac67  mov     rdx, rsi; struct wil::FailureInfo *
0x18001ac6a  lea     rcx, [rax+rax*4]
0x18001ac6e  shl     rcx, 4
0x18001ac72  add     rcx, r9; this
0x18001ac75  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18001ac7a  add     rsp, 28h
0x18001ac7e  pop     rdi
0x18001ac7f  pop     rsi
0x18001ac80  pop     rbp
0x18001ac81  pop     rbx
0x18001ac82  retn
```
