# DsqFreeObject(tagDSDeployment *,ulong)

- ea: `0x18004d3e4`
- end: `0x18004d4d6`
- name: `?DsqFreeObject@@YAXPEAUtagDSDeployment@@K@Z`
- size: `242`
- prototype: `void __fastcall(struct tagDSDeployment *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022790`
- `0x1800255c0`
- `0x180025664`
- `0x18003a330`

## callees

- `0x18004d3e4`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d413`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d438`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d447`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d456`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d468`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d47a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d48c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d49e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d4b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d413`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d438`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d447`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d456`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d468`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d47a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d48c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d49e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d4b0`

## pseudocode

```c
void __fastcall DsqFreeObject(struct tagDSDeployment *a1)
{
  __int64 i; // rsi
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx

  if ( a1 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 9); i = (unsigned int)(i + 1) )
    {
      v3 = *(void **)(*((_QWORD *)a1 + 5) + 8 * i);
      if ( v3 )
        CoTaskMemFree(v3);
    }
    v4 = (void *)*((_QWORD *)a1 + 5);
    if ( v4 )
      CoTaskMemFree(v4);
    v5 = (void *)*((_QWORD *)a1 + 12);
    if ( v5 )
      CoTaskMemFree(v5);
    v6 = (void *)*((_QWORD *)a1 + 13);
    if ( v6 )
      CoTaskMemFree(v6);
    v7 = (void *)*((_QWORD *)a1 + 15);
    if ( v7 )
      CoTaskMemFree(v7);
    v8 = (void *)*((_QWORD *)a1 + 16);
    if ( v8 )
      CoTaskMemFree(v8);
    v9 = (void *)*((_QWORD *)a1 + 17);
    if ( v9 )
      CoTaskMemFree(v9);
    v10 = (void *)*((_QWORD *)a1 + 18);
    if ( v10 )
      CoTaskMemFree(v10);
    v11 = (void *)*((_QWORD *)a1 + 19);
    if ( v11 )
      CoTaskMemFree(v11);
    v12 = (void *)*((_QWORD *)a1 + 20);
    if ( v12 )
      CoTaskMemFree(v12);
    memset(a1, 0, 0xA8u);
  }
}

```

## disassembly

```asm
0x18004d3e4  test    rcx, rcx
0x18004d3e7  jz      locret_18004D4D5
0x18004d3ed  mov     [rsp+arg_0], rbx
0x18004d3f2  mov     [rsp+arg_8], rsi
0x18004d3f7  push    rdi
0x18004d3f8  sub     rsp, 20h
0x18004d3fc  xor     esi, esi
0x18004d3fe  mov     rbx, rcx
0x18004d401  cmp     [rcx+24h], esi
0x18004d404  jbe     short loc_18004D420
0x18004d406  mov     rax, [rbx+28h]
0x18004d40a  mov     rcx, [rax+rsi*8]; pv
0x18004d40e  test    rcx, rcx
0x18004d411  jz      short loc_18004D419
0x18004d413  call    cs:__imp_CoTaskMemFree
0x18004d419  inc     esi
0x18004d41b  cmp     esi, [rbx+24h]
0x18004d41e  jb      short loc_18004D406
0x18004d420  mov     rcx, [rbx+28h]; pv
0x18004d424  test    rcx, rcx
0x18004d427  jz      short loc_18004D42F
0x18004d429  call    cs:__imp_CoTaskMemFree
0x18004d42f  mov     rcx, [rbx+60h]; pv
0x18004d433  test    rcx, rcx
0x18004d436  jz      short loc_18004D43E
0x18004d438  call    cs:__imp_CoTaskMemFree
0x18004d43e  mov     rcx, [rbx+68h]; pv
0x18004d442  test    rcx, rcx
0x18004d445  jz      short loc_18004D44D
0x18004d447  call    cs:__imp_CoTaskMemFree
0x18004d44d  mov     rcx, [rbx+78h]; pv
0x18004d451  test    rcx, rcx
0x18004d454  jz      short loc_18004D45C
0x18004d456  call    cs:__imp_CoTaskMemFree
0x18004d45c  mov     rcx, [rbx+80h]; pv
0x18004d463  test    rcx, rcx
0x18004d466  jz      short loc_18004D46E
0x18004d468  call    cs:__imp_CoTaskMemFree
0x18004d46e  mov     rcx, [rbx+88h]; pv
0x18004d475  test    rcx, rcx
0x18004d478  jz      short loc_18004D480
0x18004d47a  call    cs:__imp_CoTaskMemFree
0x18004d480  mov     rcx, [rbx+90h]; pv
0x18004d487  test    rcx, rcx
0x18004d48a  jz      short loc_18004D492
0x18004d48c  call    cs:__imp_CoTaskMemFree
0x18004d492  mov     rcx, [rbx+98h]; pv
0x18004d499  test    rcx, rcx
0x18004d49c  jz      short loc_18004D4A4
0x18004d49e  call    cs:__imp_CoTaskMemFree
0x18004d4a4  mov     rcx, [rbx+0A0h]; pv
0x18004d4ab  test    rcx, rcx
0x18004d4ae  jz      short loc_18004D4B6
0x18004d4b0  call    cs:__imp_CoTaskMemFree
0x18004d4b6  xor     edx, edx; Val
0x18004d4b8  mov     r8d, 0A8h; Size
0x18004d4be  mov     rcx, rbx; void *
0x18004d4c1  call    memset
0x18004d4c6  mov     rbx, [rsp+28h+arg_0]
0x18004d4cb  mov     rsi, [rsp+28h+arg_8]
0x18004d4d0  add     rsp, 20h
0x18004d4d4  pop     rdi
0x18004d4d5  retn
```
