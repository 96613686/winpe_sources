# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180004fd4`
- end: `0x1800050a3`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003770`

## callees

- `0x1800047b8`
- `0x180004c3c`
- `0x180004fd4`

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
0x180004fd4  push    rbx
0x180004fd6  push    rbp
0x180004fd7  push    rsi
0x180004fd8  push    rdi
0x180004fd9  sub     rsp, 28h
0x180004fdd  cmp     qword ptr [rcx+18h], 0
0x180004fe2  mov     rsi, rdx
0x180004fe5  mov     edi, [rcx+10h]
0x180004fe8  mov     rbx, rcx
0x180004feb  mov     ebp, 50h ; 'P'
0x180004ff0  jnz     short loc_180005027
0x180004ff2  test    edi, edi
0x180004ff4  jz      short loc_180005027
0x180004ff6  mov     edx, 190h; dwBytes
0x180004ffb  lea     ecx, [rbp-48h]; dwFlags
0x180004ffe  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005003  mov     [rbx+18h], rax
0x180005007  test    rax, rax
0x18000500a  jz      short loc_180005027
0x18000500c  mov     dword ptr [rbx+20h], 5
0x180005013  lea     rcx, [rax+190h]
0x18000501a  jmp     short loc_180005022
0x18000501c  mov     [rax], bp
0x18000501f  add     rax, rbp
0x180005022  cmp     rax, rcx
0x180005025  jnz     short loc_18000501C
0x180005027  mov     r9, [rbx+18h]
0x18000502b  test    r9, r9
0x18000502e  jz      short loc_18000509A
0x180005030  test    edi, edi
0x180005032  jz      short loc_180005060
0x180005034  movzx   eax, word ptr [rbx+20h]
0x180005038  mov     rcx, r9
0x18000503b  lea     rdx, [rax+rax*4]
0x18000503f  shl     rdx, 4
0x180005043  add     rdx, r9
0x180005046  cmp     rcx, rdx
0x180005049  jz      short loc_180005060
0x18000504b  mov     eax, [rbx+10h]
0x18000504e  cmp     [rcx+4], eax
0x180005051  jbe     short loc_18000505B
0x180005053  mov     eax, [rsi+8]
0x180005056  cmp     [rcx+8], eax
0x180005059  jz      short loc_18000509A
0x18000505b  add     rcx, rbp
0x18000505e  jmp     short loc_180005046
0x180005060  movzx   eax, word ptr [rbx+22h]
0x180005064  xor     edx, edx
0x180005066  movzx   ecx, word ptr [rbx+20h]
0x18000506a  inc     eax
0x18000506c  div     ecx
0x18000506e  mov     rax, [rbx+8]
0x180005072  mov     r8d, 1
0x180005078  mov     [rbx+22h], dx
0x18000507c  lock xadd [rax], r8d
0x180005081  movzx   eax, dx
0x180005084  inc     r8d; unsigned int
0x180005087  mov     rdx, rsi; struct wil::FailureInfo *
0x18000508a  lea     rcx, [rax+rax*4]
0x18000508e  shl     rcx, 4
0x180005092  add     rcx, r9; this
0x180005095  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000509a  add     rsp, 28h
0x18000509e  pop     rdi
0x18000509f  pop     rsi
0x1800050a0  pop     rbp
0x1800050a1  pop     rbx
0x1800050a2  retn
```
