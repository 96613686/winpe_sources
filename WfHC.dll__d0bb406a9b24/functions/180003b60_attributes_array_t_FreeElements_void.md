# _attributes_array_t::FreeElements(void)

- ea: `0x180003b60`
- end: `0x180003c04`
- name: `?FreeElements@_attributes_array_t@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(_attributes_array_t *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002880`
- `0x1800029f0`
- `0x1800033a0`
- `0x1800043a0`
- `0x180004500`
- `0x180006ebc`
- `0x1800073b0`
- `0x1800079b8`

## callees

- `0x180003b60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003bae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003bc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003bd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003bae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003bc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003bd9`

## pseudocode

```c
void __fastcall _attributes_array_t::FreeElements(_attributes_array_t *this)
{
  unsigned int i; // esi
  __int64 v3; // rbx
  __int64 v4; // rdi
  int v5; // eax

  if ( *((_QWORD *)this + 1) )
  {
    for ( i = 0; i < *(_DWORD *)this; *(_QWORD *)(v3 + 8 * v4) = 0 )
    {
      v3 = *((_QWORD *)this + 1);
      v4 = 18LL * i;
      v5 = *(_DWORD *)(v3 + 144LL * i + 8);
      if ( v5 == 10 )
      {
        CoTaskMemFree(*(LPVOID *)(v3 + 144LL * i + 16));
        *(_QWORD *)(v3 + 144LL * i + 16) = 0;
      }
      else if ( v5 == 14 )
      {
        CoTaskMemFree(*(LPVOID *)(v3 + 144LL * i + 24));
        *(_QWORD *)(v3 + 144LL * i + 24) = 0;
        *(_DWORD *)(v3 + 144LL * i + 16) = 0;
      }
      CoTaskMemFree(*(LPVOID *)(v3 + 144LL * i++));
    }
  }
}

```

## disassembly

```asm
0x180003b60  push    rbp
0x180003b62  sub     rsp, 20h
0x180003b66  cmp     qword ptr [rcx+8], 0
0x180003b6b  mov     rbp, rcx
0x180003b6e  jz      loc_180003BFE
0x180003b74  mov     [rsp+28h+arg_8], rsi
0x180003b79  mov     [rsp+28h+arg_18], r14
0x180003b7e  xor     r14d, r14d
0x180003b81  mov     esi, r14d
0x180003b84  cmp     [rcx], r14d
0x180003b87  jbe     short loc_180003BF4
0x180003b89  mov     [rsp+28h+arg_0], rbx
0x180003b8e  mov     [rsp+28h+arg_10], rdi
0x180003b93  mov     rbx, [rbp+8]
0x180003b97  mov     eax, esi
0x180003b99  lea     rdi, [rax+rax*8]
0x180003b9d  add     rdi, rdi
0x180003ba0  mov     eax, [rbx+rdi*8+8]
0x180003ba4  cmp     eax, 0Ah
0x180003ba7  jnz     short loc_180003BBB
0x180003ba9  mov     rcx, [rbx+rdi*8+10h]; pv
0x180003bae  call    cs:__imp_CoTaskMemFree
0x180003bb4  mov     [rbx+rdi*8+10h], r14
0x180003bb9  jmp     short loc_180003BD5
0x180003bbb  cmp     eax, 0Eh
0x180003bbe  jnz     short loc_180003BD5
0x180003bc0  mov     rcx, [rbx+rdi*8+18h]; pv
0x180003bc5  call    cs:__imp_CoTaskMemFree
0x180003bcb  mov     [rbx+rdi*8+18h], r14
0x180003bd0  mov     [rbx+rdi*8+10h], r14d
0x180003bd5  mov     rcx, [rbx+rdi*8]; pv
0x180003bd9  call    cs:__imp_CoTaskMemFree
0x180003bdf  inc     esi
0x180003be1  mov     [rbx+rdi*8], r14
0x180003be5  cmp     esi, [rbp+0]
0x180003be8  jb      short loc_180003B93
0x180003bea  mov     rdi, [rsp+28h+arg_10]
0x180003bef  mov     rbx, [rsp+28h+arg_0]
0x180003bf4  mov     rsi, [rsp+28h+arg_8]
0x180003bf9  mov     r14, [rsp+28h+arg_18]
0x180003bfe  add     rsp, 20h
0x180003c02  pop     rbp
0x180003c03  retn
```
