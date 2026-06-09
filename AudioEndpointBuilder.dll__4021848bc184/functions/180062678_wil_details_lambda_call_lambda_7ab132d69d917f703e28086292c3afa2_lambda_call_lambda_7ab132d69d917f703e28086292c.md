# wil::details::lambda_call__lambda_7ab132d69d917f703e28086292c3afa2___::_lambda_call__lambda_7ab132d69d917f703e28086292c3afa2___

- ea: `0x180062678`
- end: `0x1800626dc`
- name: `wil::details::lambda_call__lambda_7ab132d69d917f703e28086292c3afa2___::_lambda_call__lambda_7ab132d69d917f703e28086292c3afa2___`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180067751`

## callees

- `0x180062678`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800626aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800626cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800626aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800626cd`

## pseudocode

```c
void __fastcall wil::details::lambda_call__lambda_7ab132d69d917f703e28086292c3afa2___::_lambda_call__lambda_7ab132d69d917f703e28086292c3afa2___(
        __int64 a1)
{
  LPVOID **v2; // rbx
  __int64 i; // rsi
  void *v4; // rcx

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    v2 = (LPVOID **)(a1 + 8);
    for ( i = 0; (unsigned int)i < **(_DWORD **)a1; i = (unsigned int)(i + 1) )
    {
      v4 = (void *)*((_QWORD *)**v2 + i);
      if ( v4 )
      {
        CoTaskMemFree(v4);
        *((_QWORD *)**v2 + i) = 0;
      }
    }
    CoTaskMemFree(**v2);
  }
}

```

## disassembly

```asm
0x180062678  push    rbx
0x18006267a  push    rbp
0x18006267b  push    rsi
0x18006267c  push    rdi
0x18006267d  sub     rsp, 28h
0x180062681  cmp     byte ptr [rcx+10h], 0
0x180062685  mov     rdi, rcx
0x180062688  jz      short loc_1800626D3
0x18006268a  mov     byte ptr [rcx+10h], 0
0x18006268e  lea     rbx, [rcx+8]
0x180062692  mov     rax, [rcx]
0x180062695  xor     esi, esi
0x180062697  cmp     [rax], esi
0x180062699  jbe     short loc_1800626C7
0x18006269b  mov     rax, [rbx]
0x18006269e  mov     rcx, [rax]
0x1800626a1  mov     rcx, [rcx+rsi*8]; pv
0x1800626a5  test    rcx, rcx
0x1800626a8  jz      short loc_1800626BE
0x1800626aa  call    cs:__imp_CoTaskMemFree
0x1800626b0  mov     rax, [rbx]
0x1800626b3  mov     rcx, [rax]
0x1800626b6  mov     qword ptr [rcx+rsi*8], 0
0x1800626be  mov     rax, [rdi]
0x1800626c1  inc     esi
0x1800626c3  cmp     esi, [rax]
0x1800626c5  jb      short loc_18006269B
0x1800626c7  mov     rcx, [rbx]
0x1800626ca  mov     rcx, [rcx]; pv
0x1800626cd  call    cs:__imp_CoTaskMemFree
0x1800626d3  add     rsp, 28h
0x1800626d7  pop     rdi
0x1800626d8  pop     rsi
0x1800626d9  pop     rbp
0x1800626da  pop     rbx
0x1800626db  retn
```
