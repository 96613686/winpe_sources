# BatchFilterPropVariantCopyString(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x14000e6f0`
- end: `0x14000e74a`
- name: `?BatchFilterPropVariantCopyString@@YAPEA_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `90`
- prototype: `void *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000e7ec`

## callees

- `0x140005205`
- `0x14000e6f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000e71b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000e71b`

## pseudocode

```c
void *__fastcall BatchFilterPropVariantCopyString(__int64 a1)
{
  SIZE_T v3; // rsi
  void *v4; // rax
  void *v5; // rdi

  if ( !*(_QWORD *)(a1 + 8) )
    return 0;
  v3 = (unsigned int)(2 * *(_DWORD *)(a1 + 8) + 2);
  v4 = CoTaskMemAlloc(v3);
  v5 = v4;
  if ( v4 )
    memcpy_0(v4, *(const void **)a1, (unsigned int)v3);
  return v5;
}

```

## disassembly

```asm
0x14000e6f0  mov     [rsp+arg_0], rbx
0x14000e6f5  mov     [rsp+arg_8], rsi
0x14000e6fa  push    rdi
0x14000e6fb  sub     rsp, 20h
0x14000e6ff  cmp     qword ptr [rcx+8], 0
0x14000e704  mov     rbx, rcx
0x14000e707  jnz     short loc_14000E70D
0x14000e709  xor     eax, eax
0x14000e70b  jmp     short loc_14000E73A
0x14000e70d  mov     eax, [rcx+8]
0x14000e710  lea     eax, ds:2[rax*2]
0x14000e717  mov     ecx, eax; cb
0x14000e719  mov     esi, eax
0x14000e71b  call    cs:__imp_CoTaskMemAlloc
0x14000e721  mov     rdi, rax
0x14000e724  test    rax, rax
0x14000e727  jz      short loc_14000E737
0x14000e729  mov     rdx, [rbx]; Src
0x14000e72c  mov     r8d, esi; Size
0x14000e72f  mov     rcx, rax; void *
0x14000e732  call    memcpy_0
0x14000e737  mov     rax, rdi
0x14000e73a  mov     rbx, [rsp+28h+arg_0]
0x14000e73f  mov     rsi, [rsp+28h+arg_8]
0x14000e744  add     rsp, 20h
0x14000e748  pop     rdi
0x14000e749  retn
```
