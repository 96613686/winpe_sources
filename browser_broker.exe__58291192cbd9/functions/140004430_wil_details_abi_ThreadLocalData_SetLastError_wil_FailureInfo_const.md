# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140004430`
- end: `0x1400044ff`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140002ea0`

## callees

- `0x140003e78`
- `0x1400042b8`
- `0x140004430`

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
0x140004430  push    rbx
0x140004432  push    rbp
0x140004433  push    rsi
0x140004434  push    rdi
0x140004435  sub     rsp, 28h
0x140004439  cmp     qword ptr [rcx+18h], 0
0x14000443e  mov     rsi, rdx
0x140004441  mov     edi, [rcx+10h]
0x140004444  mov     rbx, rcx
0x140004447  mov     ebp, 50h ; 'P'
0x14000444c  jnz     short loc_140004483
0x14000444e  test    edi, edi
0x140004450  jz      short loc_140004483
0x140004452  mov     edx, 190h; dwBytes
0x140004457  lea     ecx, [rbp-48h]; dwFlags
0x14000445a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000445f  mov     [rbx+18h], rax
0x140004463  test    rax, rax
0x140004466  jz      short loc_140004483
0x140004468  mov     dword ptr [rbx+20h], 5
0x14000446f  lea     rcx, [rax+190h]
0x140004476  jmp     short loc_14000447E
0x140004478  mov     [rax], bp
0x14000447b  add     rax, rbp
0x14000447e  cmp     rax, rcx
0x140004481  jnz     short loc_140004478
0x140004483  mov     r9, [rbx+18h]
0x140004487  test    r9, r9
0x14000448a  jz      short loc_1400044F6
0x14000448c  test    edi, edi
0x14000448e  jz      short loc_1400044BC
0x140004490  movzx   eax, word ptr [rbx+20h]
0x140004494  mov     rcx, r9
0x140004497  lea     rdx, [rax+rax*4]
0x14000449b  shl     rdx, 4
0x14000449f  add     rdx, r9
0x1400044a2  cmp     rcx, rdx
0x1400044a5  jz      short loc_1400044BC
0x1400044a7  mov     eax, [rbx+10h]
0x1400044aa  cmp     [rcx+4], eax
0x1400044ad  jbe     short loc_1400044B7
0x1400044af  mov     eax, [rsi+8]
0x1400044b2  cmp     [rcx+8], eax
0x1400044b5  jz      short loc_1400044F6
0x1400044b7  add     rcx, rbp
0x1400044ba  jmp     short loc_1400044A2
0x1400044bc  movzx   eax, word ptr [rbx+22h]
0x1400044c0  xor     edx, edx
0x1400044c2  movzx   ecx, word ptr [rbx+20h]
0x1400044c6  inc     eax
0x1400044c8  div     ecx
0x1400044ca  mov     rax, [rbx+8]
0x1400044ce  mov     r8d, 1
0x1400044d4  mov     [rbx+22h], dx
0x1400044d8  lock xadd [rax], r8d
0x1400044dd  movzx   eax, dx
0x1400044e0  inc     r8d; unsigned int
0x1400044e3  mov     rdx, rsi; struct wil::FailureInfo *
0x1400044e6  lea     rcx, [rax+rax*4]
0x1400044ea  shl     rcx, 4
0x1400044ee  add     rcx, r9; this
0x1400044f1  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1400044f6  add     rsp, 28h
0x1400044fa  pop     rdi
0x1400044fb  pop     rsi
0x1400044fc  pop     rbp
0x1400044fd  pop     rbx
0x1400044fe  retn
```
