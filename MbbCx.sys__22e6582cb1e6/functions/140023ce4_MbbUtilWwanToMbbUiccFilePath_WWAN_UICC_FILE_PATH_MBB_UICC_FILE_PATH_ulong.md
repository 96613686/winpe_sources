# MbbUtilWwanToMbbUiccFilePath(_WWAN_UICC_FILE_PATH *,_MBB_UICC_FILE_PATH * *,ulong *)

- ea: `0x140023ce4`
- end: `0x140023da9`
- name: `?MbbUtilWwanToMbbUiccFilePath@@YAHPEAU_WWAN_UICC_FILE_PATH@@PEAPEAU_MBB_UICC_FILE_PATH@@PEAK@Z`
- size: `197`
- prototype: `__int64 __fastcall(struct _WWAN_UICC_FILE_PATH *, struct _MBB_UICC_FILE_PATH **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140011a30`
- `0x1400142f0`

## callees

- `0x140020d40`
- `0x140023ce4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140023d2e`
- `ntoskrnl!ExAllocatePool2` at `0x140023d2e`

## pseudocode

```c
__int64 __fastcall MbbUtilWwanToMbbUiccFilePath(
        struct _WWAN_UICC_FILE_PATH *a1,
        struct _MBB_UICC_FILE_PATH **a2,
        unsigned int *a3)
{
  unsigned int v6; // esi
  __int64 Pool2; // rdi
  __int64 result; // rax
  int v9; // eax
  size_t Size; // [rsp+28h] [rbp-30h]
  size_t Sizea; // [rsp+28h] [rbp-30h]

  *a3 = 0;
  v6 = ((*((unsigned __int8 *)a1 + 4) + 3) & 0xFFFFFFFC) + 20 + ((*((unsigned __int8 *)a1 + 37) + 3) & 0xFFFFFFFC);
  Pool2 = ExAllocatePool2(64, v6, 1683505741);
  if ( !Pool2 )
    return 3221225626LL;
  LODWORD(Size) = *((unsigned __int8 *)a1 + 4);
  v9 = MbbUtilWriteStringToBuffer(
         (unsigned __int8 *)Pool2,
         v6,
         20,
         (struct _MBB_STRING *)(Pool2 + 4),
         (const unsigned __int8 *)a1 + 5,
         Size);
  LODWORD(Sizea) = *((unsigned __int8 *)a1 + 37);
  MbbUtilWriteStringToBuffer(
    (unsigned __int8 *)Pool2,
    v6,
    v9,
    (struct _MBB_STRING *)(Pool2 + 12),
    (const unsigned __int8 *)a1 + 38,
    Sizea);
  *(_DWORD *)Pool2 = *(_DWORD *)a1;
  result = 0;
  *a2 = (struct _MBB_UICC_FILE_PATH *)Pool2;
  *a3 = v6;
  return result;
}

```

## disassembly

```asm
0x140023ce4  push    rbx
0x140023ce6  push    rsi
0x140023ce7  push    rdi
0x140023ce8  push    r14
0x140023cea  push    r15
0x140023cec  sub     rsp, 30h
0x140023cf0  mov     rbx, rcx
0x140023cf3  mov     dword ptr [r8], 0
0x140023cfa  movzx   r9d, byte ptr [rcx+4]
0x140023cff  mov     r14, r8
0x140023d02  add     r9d, 3
0x140023d06  mov     ecx, 0FFFFFFFCh
0x140023d0b  and     r9d, ecx
0x140023d0e  mov     r15, rdx
0x140023d11  movzx   esi, byte ptr [rbx+25h]
0x140023d15  add     r9d, 14h
0x140023d19  add     esi, 3
0x140023d1c  mov     r8d, 6458424Dh
0x140023d22  and     esi, ecx
0x140023d24  mov     ecx, 40h ; '@'
0x140023d29  add     esi, r9d
0x140023d2c  mov     edx, esi
0x140023d2e  call    cs:__imp_ExAllocatePool2
0x140023d35  nop     dword ptr [rax+rax+00h]
0x140023d3a  mov     rdi, rax
0x140023d3d  test    rax, rax
0x140023d40  jnz     short loc_140023D49
0x140023d42  mov     eax, 0C000009Ah
0x140023d47  jmp     short loc_140023D9C
0x140023d49  movzx   eax, byte ptr [rbx+4]
0x140023d4d  lea     rcx, [rbx+5]
0x140023d51  mov     dword ptr [rsp+58h+Size], eax; Size
0x140023d55  lea     r9, [rdi+4]; struct _MBB_STRING *
0x140023d59  mov     [rsp+58h+Src], rcx; Src
0x140023d5e  mov     r8d, 14h; unsigned int
0x140023d64  mov     rcx, rdi; unsigned __int8 *
0x140023d67  mov     edx, esi; unsigned int
0x140023d69  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x140023d6e  movzx   ecx, byte ptr [rbx+25h]
0x140023d72  lea     rdx, [rbx+26h]
0x140023d76  mov     dword ptr [rsp+58h+Size], ecx; Size
0x140023d7a  lea     r9, [rdi+0Ch]; struct _MBB_STRING *
0x140023d7e  mov     [rsp+58h+Src], rdx; Src
0x140023d83  mov     r8d, eax; unsigned int
0x140023d86  mov     edx, esi; unsigned int
0x140023d88  mov     rcx, rdi; unsigned __int8 *
0x140023d8b  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x140023d90  mov     eax, [rbx]
0x140023d92  mov     [rdi], eax
0x140023d94  xor     eax, eax
0x140023d96  mov     [r15], rdi
0x140023d99  mov     [r14], esi
0x140023d9c  add     rsp, 30h
0x140023da0  pop     r15
0x140023da2  pop     r14
0x140023da4  pop     rdi
0x140023da5  pop     rsi
0x140023da6  pop     rbx
0x140023da7  retn
```
