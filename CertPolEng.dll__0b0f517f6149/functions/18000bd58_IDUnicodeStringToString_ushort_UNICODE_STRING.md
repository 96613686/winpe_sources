# IDUnicodeStringToString(ushort * *,_UNICODE_STRING *)

- ea: `0x18000bd58`
- end: `0x18000bde5`
- name: `?IDUnicodeStringToString@@YAKPEAPEAGPEAU_UNICODE_STRING@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(unsigned __int16 **, struct _UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ac0`
- `0x1800066f0`
- `0x180014b54`
- `0x180016b9c`

## callees

- `0x18000bd58`
- `0x18000e8d6`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bd9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bd9a`

## pseudocode

```c
__int64 __fastcall IDUnicodeStringToString(unsigned __int16 **a1, struct _UNICODE_STRING *a2)
{
  unsigned int Length; // eax
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rsi

  if ( !a1 || !a2 )
    return 87;
  *a1 = 0;
  if ( a2->Length )
  {
    Length = a2->Length;
    if ( Length + 2 < Length )
      return 111;
    v6 = (unsigned __int16 *)LocalAlloc(0, Length + 2);
    v7 = v6;
    if ( !v6 )
      return 14;
    memcpy_0(v6, a2->Buffer, a2->Length);
    v7[(unsigned __int64)a2->Length >> 1] = 0;
    *a1 = v7;
  }
  return 0;
}

```

## disassembly

```asm
0x18000bd58  mov     [rsp+arg_0], rbx
0x18000bd5d  mov     [rsp+arg_8], rsi
0x18000bd62  push    rdi
0x18000bd63  sub     rsp, 20h
0x18000bd67  mov     rbx, rdx
0x18000bd6a  mov     rdi, rcx
0x18000bd6d  test    rcx, rcx
0x18000bd70  jz      short loc_18000BDD0
0x18000bd72  test    rdx, rdx
0x18000bd75  jz      short loc_18000BDD0
0x18000bd77  xor     eax, eax
0x18000bd79  mov     qword ptr [rcx], 0
0x18000bd80  cmp     ax, [rdx]
0x18000bd83  jz      short loc_18000BDCC
0x18000bd85  movzx   eax, word ptr [rdx]
0x18000bd88  lea     ecx, [rax+2]
0x18000bd8b  cmp     ecx, eax
0x18000bd8d  jnb     short loc_18000BD96
0x18000bd8f  mov     eax, 6Fh ; 'o'
0x18000bd94  jmp     short loc_18000BDD5
0x18000bd96  mov     edx, ecx; uBytes
0x18000bd98  xor     ecx, ecx; uFlags
0x18000bd9a  call    cs:__imp_LocalAlloc
0x18000bda0  mov     rsi, rax
0x18000bda3  test    rax, rax
0x18000bda6  jnz     short loc_18000BDAD
0x18000bda8  lea     eax, [rsi+0Eh]
0x18000bdab  jmp     short loc_18000BDD5
0x18000bdad  movzx   r8d, word ptr [rbx]; Size
0x18000bdb1  mov     rcx, rsi; void *
0x18000bdb4  mov     rdx, [rbx+8]; Src
0x18000bdb8  call    memcpy_0
0x18000bdbd  movzx   ecx, word ptr [rbx]
0x18000bdc0  shr     rcx, 1
0x18000bdc3  xor     eax, eax
0x18000bdc5  mov     [rsi+rcx*2], ax
0x18000bdc9  mov     [rdi], rsi
0x18000bdcc  xor     eax, eax
0x18000bdce  jmp     short loc_18000BDD5
0x18000bdd0  mov     eax, 57h ; 'W'
0x18000bdd5  mov     rbx, [rsp+28h+arg_0]
0x18000bdda  mov     rsi, [rsp+28h+arg_8]
0x18000bddf  add     rsp, 20h
0x18000bde3  pop     rdi
0x18000bde4  retn
```
