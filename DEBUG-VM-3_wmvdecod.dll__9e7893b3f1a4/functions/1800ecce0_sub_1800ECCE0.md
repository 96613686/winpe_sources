# sub_1800ECCE0

- ea: `0x1800ecce0`
- end: `0x1800ecda0`
- name: `sub_1800ECCE0`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800edf70`

## callees

- `0x180057fe4`
- `0x1800695b4`
- `0x1800ecce0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ecd2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ecd2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eccf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ecd0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ecd4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eccf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ecd0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ecd4c`

## pseudocode

```c
__int64 __fastcall sub_1800ECCE0(__int64 a1, __int64 a2, unsigned int a3)
{
  void *v6; // rcx
  LPVOID v7; // rax
  int v8; // esi
  __int64 (__fastcall *v10)(__int64, __int64, _QWORD); // rbx

  CoTaskMemFree(*(LPVOID *)(a1 + 8));
  v6 = *(void **)(a1 + 16);
  *(_QWORD *)(a1 + 8) = 0;
  CoTaskMemFree(v6);
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 24) = 0;
  v7 = CoTaskMemAlloc(0x110u);
  *(_QWORD *)(a1 + 16) = v7;
  if ( v7 )
  {
    v10 = (__int64 (__fastcall *)(__int64, __int64, _QWORD))sub_1800695B4(word_18025E3DA);
    v8 = v10(a1, a2, a3);
    sub_180057FE4(v10);
    if ( v8 >= 0 )
    {
      *(_DWORD *)(a1 + 24) = 1;
      return (unsigned int)v8;
    }
  }
  else
  {
    v8 = -2147024882;
  }
  CoTaskMemFree(*(LPVOID *)(a1 + 16));
  *(_QWORD *)(a1 + 16) = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800ecce0  push    rbx
0x1800ecce2  push    rbp
0x1800ecce3  push    rsi
0x1800ecce4  push    rdi
0x1800ecce5  sub     rsp, 28h
0x1800ecce9  mov     rdi, rcx
0x1800eccec  mov     esi, r8d
0x1800eccef  mov     rcx, [rcx+8]; pv
0x1800eccf3  mov     rbp, rdx
0x1800eccf6  call    cs:CoTaskMemFree
0x1800eccfd  nop     dword ptr [rax+rax+00h]
0x1800ecd02  mov     rcx, [rdi+10h]; pv
0x1800ecd06  mov     qword ptr [rdi+8], 0
0x1800ecd0e  call    cs:CoTaskMemFree
0x1800ecd15  nop     dword ptr [rax+rax+00h]
0x1800ecd1a  mov     ecx, 110h; cb
0x1800ecd1f  mov     qword ptr [rdi+10h], 0
0x1800ecd27  mov     dword ptr [rdi+18h], 0
0x1800ecd2e  call    cs:CoTaskMemAlloc
0x1800ecd35  nop     dword ptr [rax+rax+00h]
0x1800ecd3a  mov     [rdi+10h], rax
0x1800ecd3e  test    rax, rax
0x1800ecd41  jnz     short loc_1800ECD6C
0x1800ecd43  mov     esi, 8007000Eh
0x1800ecd48  mov     rcx, [rdi+10h]; pv
0x1800ecd4c  call    cs:CoTaskMemFree
0x1800ecd53  nop     dword ptr [rax+rax+00h]
0x1800ecd58  mov     qword ptr [rdi+10h], 0
0x1800ecd60  mov     eax, esi
0x1800ecd62  add     rsp, 28h
0x1800ecd66  pop     rdi
0x1800ecd67  pop     rsi
0x1800ecd68  pop     rbp
0x1800ecd69  pop     rbx
0x1800ecd6a  retn
0x1800ecd6c  lea     rcx, word_18025E3DA
0x1800ecd73  call    sub_1800695B4
0x1800ecd78  mov     r8d, esi
0x1800ecd7b  mov     rdx, rbp
0x1800ecd7e  mov     rcx, rdi
0x1800ecd81  mov     rbx, rax
0x1800ecd84  call    rax
0x1800ecd86  nop     dword ptr [rax]
0x1800ecd89  mov     rcx, rbx
0x1800ecd8c  mov     esi, eax
0x1800ecd8e  call    sub_180057FE4
0x1800ecd93  test    esi, esi
0x1800ecd95  js      short loc_1800ECD48
0x1800ecd97  mov     dword ptr [rdi+18h], 1
0x1800ecd9e  jmp     short loc_1800ECD60
```
