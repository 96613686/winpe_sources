# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000bde8`
- end: `0x18000beb7`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009520`

## callees

- `0x18000a9b0`
- `0x18000b960`
- `0x18000bde8`

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
0x18000bde8  push    rbx
0x18000bdea  push    rbp
0x18000bdeb  push    rsi
0x18000bdec  push    rdi
0x18000bded  sub     rsp, 28h
0x18000bdf1  cmp     qword ptr [rcx+18h], 0
0x18000bdf6  mov     rsi, rdx
0x18000bdf9  mov     edi, [rcx+10h]
0x18000bdfc  mov     rbx, rcx
0x18000bdff  mov     ebp, 50h ; 'P'
0x18000be04  jnz     short loc_18000BE3B
0x18000be06  test    edi, edi
0x18000be08  jz      short loc_18000BE3B
0x18000be0a  mov     edx, 190h; dwBytes
0x18000be0f  lea     ecx, [rbp-48h]; dwFlags
0x18000be12  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000be17  mov     [rbx+18h], rax
0x18000be1b  test    rax, rax
0x18000be1e  jz      short loc_18000BE3B
0x18000be20  mov     dword ptr [rbx+20h], 5
0x18000be27  lea     rcx, [rax+190h]
0x18000be2e  jmp     short loc_18000BE36
0x18000be30  mov     [rax], bp
0x18000be33  add     rax, rbp
0x18000be36  cmp     rax, rcx
0x18000be39  jnz     short loc_18000BE30
0x18000be3b  mov     r9, [rbx+18h]
0x18000be3f  test    r9, r9
0x18000be42  jz      short loc_18000BEAE
0x18000be44  test    edi, edi
0x18000be46  jz      short loc_18000BE74
0x18000be48  movzx   eax, word ptr [rbx+20h]
0x18000be4c  mov     rcx, r9
0x18000be4f  lea     rdx, [rax+rax*4]
0x18000be53  shl     rdx, 4
0x18000be57  add     rdx, r9
0x18000be5a  cmp     rcx, rdx
0x18000be5d  jz      short loc_18000BE74
0x18000be5f  mov     eax, [rbx+10h]
0x18000be62  cmp     [rcx+4], eax
0x18000be65  jbe     short loc_18000BE6F
0x18000be67  mov     eax, [rsi+8]
0x18000be6a  cmp     [rcx+8], eax
0x18000be6d  jz      short loc_18000BEAE
0x18000be6f  add     rcx, rbp
0x18000be72  jmp     short loc_18000BE5A
0x18000be74  movzx   eax, word ptr [rbx+22h]
0x18000be78  xor     edx, edx
0x18000be7a  movzx   ecx, word ptr [rbx+20h]
0x18000be7e  inc     eax
0x18000be80  div     ecx
0x18000be82  mov     rax, [rbx+8]
0x18000be86  mov     r8d, 1
0x18000be8c  mov     [rbx+22h], dx
0x18000be90  lock xadd [rax], r8d
0x18000be95  movzx   eax, dx
0x18000be98  inc     r8d; unsigned int
0x18000be9b  mov     rdx, rsi; struct wil::FailureInfo *
0x18000be9e  lea     rcx, [rax+rax*4]
0x18000bea2  shl     rcx, 4
0x18000bea6  add     rcx, r9; this
0x18000bea9  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000beae  add     rsp, 28h
0x18000beb2  pop     rdi
0x18000beb3  pop     rsi
0x18000beb4  pop     rbp
0x18000beb5  pop     rbx
0x18000beb6  retn
```
