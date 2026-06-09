# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180004e44`
- end: `0x180004f13`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003600`

## callees

- `0x180004628`
- `0x180004aac`
- `0x180004e44`

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
0x180004e44  push    rbx
0x180004e46  push    rbp
0x180004e47  push    rsi
0x180004e48  push    rdi
0x180004e49  sub     rsp, 28h
0x180004e4d  cmp     qword ptr [rcx+18h], 0
0x180004e52  mov     rsi, rdx
0x180004e55  mov     edi, [rcx+10h]
0x180004e58  mov     rbx, rcx
0x180004e5b  mov     ebp, 50h ; 'P'
0x180004e60  jnz     short loc_180004E97
0x180004e62  test    edi, edi
0x180004e64  jz      short loc_180004E97
0x180004e66  mov     edx, 190h; dwBytes
0x180004e6b  lea     ecx, [rbp-48h]; dwFlags
0x180004e6e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004e73  mov     [rbx+18h], rax
0x180004e77  test    rax, rax
0x180004e7a  jz      short loc_180004E97
0x180004e7c  mov     dword ptr [rbx+20h], 5
0x180004e83  lea     rcx, [rax+190h]
0x180004e8a  jmp     short loc_180004E92
0x180004e8c  mov     [rax], bp
0x180004e8f  add     rax, rbp
0x180004e92  cmp     rax, rcx
0x180004e95  jnz     short loc_180004E8C
0x180004e97  mov     r9, [rbx+18h]
0x180004e9b  test    r9, r9
0x180004e9e  jz      short loc_180004F0A
0x180004ea0  test    edi, edi
0x180004ea2  jz      short loc_180004ED0
0x180004ea4  movzx   eax, word ptr [rbx+20h]
0x180004ea8  mov     rcx, r9
0x180004eab  lea     rdx, [rax+rax*4]
0x180004eaf  shl     rdx, 4
0x180004eb3  add     rdx, r9
0x180004eb6  cmp     rcx, rdx
0x180004eb9  jz      short loc_180004ED0
0x180004ebb  mov     eax, [rbx+10h]
0x180004ebe  cmp     [rcx+4], eax
0x180004ec1  jbe     short loc_180004ECB
0x180004ec3  mov     eax, [rsi+8]
0x180004ec6  cmp     [rcx+8], eax
0x180004ec9  jz      short loc_180004F0A
0x180004ecb  add     rcx, rbp
0x180004ece  jmp     short loc_180004EB6
0x180004ed0  movzx   eax, word ptr [rbx+22h]
0x180004ed4  xor     edx, edx
0x180004ed6  movzx   ecx, word ptr [rbx+20h]
0x180004eda  inc     eax
0x180004edc  div     ecx
0x180004ede  mov     rax, [rbx+8]
0x180004ee2  mov     r8d, 1
0x180004ee8  mov     [rbx+22h], dx
0x180004eec  lock xadd [rax], r8d
0x180004ef1  movzx   eax, dx
0x180004ef4  inc     r8d; unsigned int
0x180004ef7  mov     rdx, rsi; struct wil::FailureInfo *
0x180004efa  lea     rcx, [rax+rax*4]
0x180004efe  shl     rcx, 4
0x180004f02  add     rcx, r9; this
0x180004f05  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004f0a  add     rsp, 28h
0x180004f0e  pop     rdi
0x180004f0f  pop     rsi
0x180004f10  pop     rbp
0x180004f11  pop     rbx
0x180004f12  retn
```
