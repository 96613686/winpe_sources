# CRYPT_XML_REFERENCE_DATA_PROVIDER_READ

- ea: `0x180011490`
- end: `0x1800114db`
- name: `CRYPT_XML_REFERENCE_DATA_PROVIDER_READ`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180011490`
- `0x18001860d`

## pseudocode

```c
__int64 __fastcall CRYPT_XML_REFERENCE_DATA_PROVIDER_READ(__int64 a1, void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v5; // eax

  v5 = *(_DWORD *)(a1 + 12) - *(_DWORD *)(a1 + 24);
  if ( v5 > a3 )
    v5 = a3;
  *a4 = v5;
  if ( v5 )
  {
    memcpy_0(a2, (const void *)(*(_QWORD *)(a1 + 16) + *(unsigned int *)(a1 + 24)), v5);
    *(_DWORD *)(a1 + 24) += *a4;
  }
  return 0;
}

```

## disassembly

```asm
0x180011490  mov     [rsp+arg_0], rbx
0x180011495  push    rdi
0x180011496  sub     rsp, 20h
0x18001149a  mov     eax, [rcx+0Ch]
0x18001149d  mov     rdi, r9
0x1800114a0  sub     eax, [rcx+18h]
0x1800114a3  mov     r9, rdx
0x1800114a6  cmp     eax, r8d
0x1800114a9  mov     rbx, rcx
0x1800114ac  cmova   eax, r8d
0x1800114b0  mov     [rdi], eax
0x1800114b2  test    eax, eax
0x1800114b4  jz      short loc_1800114CD
0x1800114b6  mov     edx, [rcx+18h]
0x1800114b9  add     rdx, [rcx+10h]; Src
0x1800114bd  mov     rcx, r9; void *
0x1800114c0  mov     r8d, eax; Size
0x1800114c3  call    memcpy_0
0x1800114c8  mov     eax, [rdi]
0x1800114ca  add     [rbx+18h], eax
0x1800114cd  mov     rbx, [rsp+28h+arg_0]
0x1800114d2  xor     eax, eax
0x1800114d4  add     rsp, 20h
0x1800114d8  pop     rdi
0x1800114d9  retn
```
