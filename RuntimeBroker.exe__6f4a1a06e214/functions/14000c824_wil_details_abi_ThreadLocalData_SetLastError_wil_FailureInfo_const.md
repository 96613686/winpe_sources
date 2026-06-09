# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x14000c824`
- end: `0x14000c8f3`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007244`

## callees

- `0x14000837c`
- `0x14000c664`
- `0x14000c824`

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
0x14000c824  push    rbx
0x14000c826  push    rbp
0x14000c827  push    rsi
0x14000c828  push    rdi
0x14000c829  sub     rsp, 28h
0x14000c82d  cmp     qword ptr [rcx+18h], 0
0x14000c832  mov     rsi, rdx
0x14000c835  mov     edi, [rcx+10h]
0x14000c838  mov     rbx, rcx
0x14000c83b  mov     ebp, 50h ; 'P'
0x14000c840  jnz     short loc_14000C877
0x14000c842  test    edi, edi
0x14000c844  jz      short loc_14000C877
0x14000c846  mov     edx, 190h; dwBytes
0x14000c84b  lea     ecx, [rbp-48h]; dwFlags
0x14000c84e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000c853  mov     [rbx+18h], rax
0x14000c857  test    rax, rax
0x14000c85a  jz      short loc_14000C877
0x14000c85c  mov     dword ptr [rbx+20h], 5
0x14000c863  lea     rcx, [rax+190h]
0x14000c86a  jmp     short loc_14000C872
0x14000c86c  mov     [rax], bp
0x14000c86f  add     rax, rbp
0x14000c872  cmp     rax, rcx
0x14000c875  jnz     short loc_14000C86C
0x14000c877  mov     r9, [rbx+18h]
0x14000c87b  test    r9, r9
0x14000c87e  jz      short loc_14000C8EA
0x14000c880  test    edi, edi
0x14000c882  jz      short loc_14000C8B0
0x14000c884  movzx   eax, word ptr [rbx+20h]
0x14000c888  mov     rcx, r9
0x14000c88b  lea     rdx, [rax+rax*4]
0x14000c88f  shl     rdx, 4
0x14000c893  add     rdx, r9
0x14000c896  cmp     rcx, rdx
0x14000c899  jz      short loc_14000C8B0
0x14000c89b  mov     eax, [rbx+10h]
0x14000c89e  cmp     [rcx+4], eax
0x14000c8a1  jbe     short loc_14000C8AB
0x14000c8a3  mov     eax, [rsi+8]
0x14000c8a6  cmp     [rcx+8], eax
0x14000c8a9  jz      short loc_14000C8EA
0x14000c8ab  add     rcx, rbp
0x14000c8ae  jmp     short loc_14000C896
0x14000c8b0  movzx   eax, word ptr [rbx+22h]
0x14000c8b4  xor     edx, edx
0x14000c8b6  movzx   ecx, word ptr [rbx+20h]
0x14000c8ba  inc     eax
0x14000c8bc  div     ecx
0x14000c8be  mov     rax, [rbx+8]
0x14000c8c2  mov     r8d, 1
0x14000c8c8  mov     [rbx+22h], dx
0x14000c8cc  lock xadd [rax], r8d
0x14000c8d1  movzx   eax, dx
0x14000c8d4  inc     r8d; unsigned int
0x14000c8d7  mov     rdx, rsi; struct wil::FailureInfo *
0x14000c8da  lea     rcx, [rax+rax*4]
0x14000c8de  shl     rcx, 4
0x14000c8e2  add     rcx, r9; this
0x14000c8e5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000c8ea  add     rsp, 28h
0x14000c8ee  pop     rdi
0x14000c8ef  pop     rsi
0x14000c8f0  pop     rbp
0x14000c8f1  pop     rbx
0x14000c8f2  retn
```
