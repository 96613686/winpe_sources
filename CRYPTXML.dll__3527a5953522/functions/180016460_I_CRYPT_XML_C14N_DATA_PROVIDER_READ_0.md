# I_CRYPT_XML_C14N_DATA_PROVIDER_READ_0

- ea: `0x180016460`
- end: `0x1800164af`
- name: `I_CRYPT_XML_C14N_DATA_PROVIDER_READ_0`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180016460`
- `0x18001860d`

## pseudocode

```c
__int64 __fastcall I_CRYPT_XML_C14N_DATA_PROVIDER_READ_0(unsigned int *a1, void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v4; // esi

  v4 = a3;
  if ( a3 > *a1 )
    v4 = *a1;
  *a4 = v4;
  if ( v4 )
  {
    memcpy_0(a2, *((const void **)a1 + 1), v4);
    *((_QWORD *)a1 + 1) += v4;
    *a1 -= v4;
  }
  return 0;
}

```

## disassembly

```asm
0x180016460  mov     [rsp+arg_0], rbx
0x180016465  mov     [rsp+arg_8], rsi
0x18001646a  push    rdi
0x18001646b  sub     rsp, 20h
0x18001646f  cmp     r8d, [rcx]
0x180016472  mov     esi, r8d
0x180016475  mov     rax, rdx
0x180016478  mov     rdi, rcx
0x18001647b  cmova   esi, [rcx]
0x18001647e  mov     [r9], esi
0x180016481  test    esi, esi
0x180016483  jz      short loc_18001649C
0x180016485  mov     rdx, [rcx+8]; Src
0x180016489  mov     rcx, rax; void *
0x18001648c  mov     r8d, esi; Size
0x18001648f  mov     ebx, esi
0x180016491  call    memcpy_0
0x180016496  add     [rdi+8], rbx
0x18001649a  sub     [rdi], esi
0x18001649c  mov     rbx, [rsp+28h+arg_0]
0x1800164a1  xor     eax, eax
0x1800164a3  mov     rsi, [rsp+28h+arg_8]
0x1800164a8  add     rsp, 20h
0x1800164ac  pop     rdi
0x1800164ad  retn
```
