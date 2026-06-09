# _hypothesis_builder::SetCount(ulong)

- ea: `0x1800079b8`
- end: `0x180007a5a`
- name: `?SetCount@_hypothesis_builder@@QEAAJK@Z`
- size: `162`
- prototype: `__int64 __fastcall(_hypothesis_builder *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800033a0`

## callees

- `0x180003b60`
- `0x1800079b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800079d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800079d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180007a0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180007a0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a3f`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::SetCount(_hypothesis_builder *this)
{
  __int64 v2; // rbx
  _BYTE *v3; // rax
  __int64 v4; // rbp
  void *v5; // rcx
  _BYTE *v6; // rax
  _BYTE *v7; // rsi
  __int64 result; // rax

  if ( !*((_QWORD *)this + 4) )
  {
    v2 = 32;
    v3 = CoTaskMemAlloc(0x20u);
    *((_QWORD *)this + 4) = v3;
    if ( !v3 )
      return 2147942414LL;
    do
    {
      *v3++ = 0;
      --v2;
    }
    while ( v2 );
  }
  v4 = 432;
  v5 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 4) = 0;
  v6 = CoTaskMemRealloc(v5, 0x1B0u);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  do
  {
    *v6++ = 0;
    --v4;
  }
  while ( v4 );
  *(_QWORD *)(*((_QWORD *)this + 4) + 24LL) = v7;
  _attributes_array_t::FreeElements((_hypothesis_builder *)((char *)this + 16));
  CoTaskMemFree(*((LPVOID *)this + 3));
  result = 0;
  *((_DWORD *)this + 4) = 3;
  *((_QWORD *)this + 3) = v7;
  return result;
}

```

## disassembly

```asm
0x1800079b8  push    rbx
0x1800079ba  push    rbp
0x1800079bb  push    rsi
0x1800079bc  push    rdi
0x1800079bd  sub     rsp, 28h
0x1800079c1  cmp     qword ptr [rcx+20h], 0
0x1800079c6  mov     rdi, rcx
0x1800079c9  jnz     short loc_1800079ED
0x1800079cb  mov     ebx, 20h ; ' '
0x1800079d0  mov     ecx, ebx; cb
0x1800079d2  call    cs:__imp_CoTaskMemAlloc
0x1800079d8  mov     [rdi+20h], rax
0x1800079dc  test    rax, rax
0x1800079df  jz      short loc_180007A18
0x1800079e1  mov     byte ptr [rax], 0
0x1800079e4  inc     rax
0x1800079e7  sub     rbx, 1
0x1800079eb  jnz     short loc_1800079E1
0x1800079ed  lea     rbx, [rdi+10h]
0x1800079f1  mov     ebp, 1B0h
0x1800079f6  mov     rcx, [rbx+8]; pv
0x1800079fa  mov     edx, ebp; cb
0x1800079fc  mov     qword ptr [rbx+8], 0
0x180007a04  mov     dword ptr [rbx], 0
0x180007a0a  call    cs:__imp_CoTaskMemRealloc
0x180007a10  mov     rsi, rax
0x180007a13  test    rax, rax
0x180007a16  jnz     short loc_180007A1F
0x180007a18  mov     eax, 8007000Eh
0x180007a1d  jmp     short loc_180007A51
0x180007a1f  mov     byte ptr [rax], 0
0x180007a22  inc     rax
0x180007a25  sub     rbp, 1
0x180007a29  jnz     short loc_180007A1F
0x180007a2b  mov     rax, [rdi+20h]
0x180007a2f  mov     rcx, rbx; this
0x180007a32  mov     [rax+18h], rsi
0x180007a36  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x180007a3b  mov     rcx, [rbx+8]; pv
0x180007a3f  call    cs:__imp_CoTaskMemFree
0x180007a45  xor     eax, eax
0x180007a47  mov     dword ptr [rbx], 3
0x180007a4d  mov     [rbx+8], rsi
0x180007a51  add     rsp, 28h
0x180007a55  pop     rdi
0x180007a56  pop     rsi
0x180007a57  pop     rbp
0x180007a58  pop     rbx
0x180007a59  retn
```
