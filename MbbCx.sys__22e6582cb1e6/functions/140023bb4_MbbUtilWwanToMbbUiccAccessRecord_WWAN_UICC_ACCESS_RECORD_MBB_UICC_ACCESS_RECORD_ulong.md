# MbbUtilWwanToMbbUiccAccessRecord(_WWAN_UICC_ACCESS_RECORD *,_MBB_UICC_ACCESS_RECORD * *,ulong *)

- ea: `0x140023bb4`
- end: `0x140023cde`
- name: `?MbbUtilWwanToMbbUiccAccessRecord@@YAHPEAU_WWAN_UICC_ACCESS_RECORD@@PEAPEAU_MBB_UICC_ACCESS_RECORD@@PEAK@Z`
- size: `298`
- prototype: `__int64 __fastcall(struct _WWAN_UICC_ACCESS_RECORD *, struct _MBB_UICC_ACCESS_RECORD **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140020b38`

## callees

- `0x140020d40`
- `0x140023bb4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140023c15`
- `ntoskrnl!ExAllocatePool2` at `0x140023c15`

## pseudocode

```c
__int64 __fastcall MbbUtilWwanToMbbUiccAccessRecord(
        struct _WWAN_UICC_ACCESS_RECORD *a1,
        struct _MBB_UICC_ACCESS_RECORD **a2,
        unsigned int *a3)
{
  int v3; // r9d
  unsigned int v5; // edi
  int v8; // ebp
  unsigned int v9; // eax
  unsigned int v10; // ebp
  __int64 Pool2; // rsi
  int v12; // eax
  int v13; // eax
  int v14; // eax
  size_t Size; // [rsp+28h] [rbp-40h]
  size_t Sizea; // [rsp+28h] [rbp-40h]
  size_t Sizeb; // [rsp+28h] [rbp-40h]
  size_t Sizec; // [rsp+28h] [rbp-40h]

  v3 = *((unsigned __int8 *)a1 + 73);
  v5 = 0;
  *a2 = 0;
  v8 = *((unsigned __int8 *)a1 + 88);
  v9 = (*((unsigned __int8 *)a1 + 106) + 3) & 0xFFFFFFFC;
  *a3 = 0;
  v10 = ((*((unsigned __int8 *)a1 + 40) + 3) & 0xFFFFFFFC) + v9 + ((v3 + 3) & 0xFFFFFFFC) + ((v8 + 3) & 0xFFFFFFFC) + 40;
  Pool2 = ExAllocatePool2(64, v10, 1683505741);
  if ( Pool2 )
  {
    LODWORD(Size) = *((unsigned __int8 *)a1 + 40);
    v12 = MbbUtilWriteStringToBuffer(
            (unsigned __int8 *)Pool2,
            v10,
            40,
            (struct _MBB_STRING *)(Pool2 + 4),
            (const unsigned __int8 *)a1 + 41,
            Size);
    LODWORD(Sizea) = *((unsigned __int8 *)a1 + 73);
    v13 = MbbUtilWriteStringToBuffer(
            (unsigned __int8 *)Pool2,
            v10,
            v12,
            (struct _MBB_STRING *)(Pool2 + 12),
            (const unsigned __int8 *)a1 + 74,
            Sizea);
    LODWORD(Sizeb) = *((unsigned __int8 *)a1 + 88);
    v14 = MbbUtilWriteStringToBuffer(
            (unsigned __int8 *)Pool2,
            v10,
            v13,
            (struct _MBB_STRING *)(Pool2 + 24),
            (const unsigned __int8 *)a1 + 89,
            Sizeb);
    LODWORD(Sizec) = *((unsigned __int8 *)a1 + 106);
    MbbUtilWriteStringToBuffer(
      (unsigned __int8 *)Pool2,
      v10,
      v14,
      (struct _MBB_STRING *)(Pool2 + 32),
      (const unsigned __int8 *)a1 + 107,
      Sizec);
    *(_DWORD *)Pool2 = *(_DWORD *)a1;
    *(_DWORD *)(Pool2 + 20) = *((_DWORD *)a1 + 21);
    *a2 = (struct _MBB_UICC_ACCESS_RECORD *)Pool2;
    *a3 = v10;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v5;
}

```

## disassembly

```asm
0x140023bb4  push    rbx
0x140023bb6  push    rbp
0x140023bb7  push    rsi
0x140023bb8  push    rdi
0x140023bb9  push    r14
0x140023bbb  push    r15
0x140023bbd  sub     rsp, 38h
0x140023bc1  movzx   r9d, byte ptr [rcx+49h]
0x140023bc6  mov     rbx, rcx
0x140023bc9  mov     ecx, 0FFFFFFFCh
0x140023bce  add     r9d, 3
0x140023bd2  and     r9d, ecx
0x140023bd5  xor     edi, edi
0x140023bd7  mov     r14, r8
0x140023bda  mov     [rdx], rdi
0x140023bdd  movzx   eax, byte ptr [rbx+6Ah]
0x140023be1  mov     r15, rdx
0x140023be4  movzx   ebp, byte ptr [rbx+58h]
0x140023be8  add     eax, 3
0x140023beb  and     eax, ecx
0x140023bed  mov     [r8], edi
0x140023bf0  add     r9d, eax
0x140023bf3  add     ebp, 3
0x140023bf6  movzx   eax, byte ptr [rbx+28h]
0x140023bfa  and     ebp, ecx
0x140023bfc  add     eax, 3
0x140023bff  add     ebp, 28h ; '('
0x140023c02  and     eax, ecx
0x140023c04  mov     r8d, 6458424Dh
0x140023c0a  add     r9d, eax
0x140023c0d  lea     ecx, [rdi+40h]
0x140023c10  add     ebp, r9d
0x140023c13  mov     edx, ebp
0x140023c15  call    cs:__imp_ExAllocatePool2
0x140023c1c  nop     dword ptr [rax+rax+00h]
0x140023c21  mov     rsi, rax
0x140023c24  test    rax, rax
0x140023c27  jnz     short loc_140023C33
0x140023c29  mov     edi, 0C000009Ah
0x140023c2e  jmp     loc_140023CCE
0x140023c33  movzx   eax, byte ptr [rbx+28h]
0x140023c37  lea     rcx, [rbx+29h]
0x140023c3b  mov     dword ptr [rsp+68h+Size], eax; Size
0x140023c3f  lea     r9, [rsi+4]; struct _MBB_STRING *
0x140023c43  mov     [rsp+68h+Src], rcx; Src
0x140023c48  mov     r8d, 28h ; '('; unsigned int
0x140023c4e  mov     rcx, rsi; unsigned __int8 *
0x140023c51  mov     edx, ebp; unsigned int
0x140023c53  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x140023c58  movzx   ecx, byte ptr [rbx+49h]
0x140023c5c  lea     rdx, [rbx+4Ah]
0x140023c60  mov     dword ptr [rsp+68h+Size], ecx; Size
0x140023c64  lea     r9, [rsi+0Ch]; struct _MBB_STRING *
0x140023c68  mov     [rsp+68h+Src], rdx; Src
0x140023c6d  mov     r8d, eax; unsigned int
0x140023c70  mov     edx, ebp; unsigned int
0x140023c72  mov     rcx, rsi; unsigned __int8 *
0x140023c75  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x140023c7a  movzx   ecx, byte ptr [rbx+58h]
0x140023c7e  lea     rdx, [rbx+59h]
0x140023c82  mov     dword ptr [rsp+68h+Size], ecx; Size
0x140023c86  lea     r9, [rsi+18h]; struct _MBB_STRING *
0x140023c8a  mov     [rsp+68h+Src], rdx; Src
0x140023c8f  mov     r8d, eax; unsigned int
0x140023c92  mov     edx, ebp; unsigned int
0x140023c94  mov     rcx, rsi; unsigned __int8 *
0x140023c97  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x140023c9c  movzx   ecx, byte ptr [rbx+6Ah]
0x140023ca0  lea     rdx, [rbx+6Bh]
0x140023ca4  mov     dword ptr [rsp+68h+Size], ecx; Size
0x140023ca8  lea     r9, [rsi+20h]; struct _MBB_STRING *
0x140023cac  mov     [rsp+68h+Src], rdx; Src
0x140023cb1  mov     r8d, eax; unsigned int
0x140023cb4  mov     edx, ebp; unsigned int
0x140023cb6  mov     rcx, rsi; unsigned __int8 *
0x140023cb9  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x140023cbe  mov     ecx, [rbx]
0x140023cc0  mov     [rsi], ecx
0x140023cc2  mov     ecx, [rbx+54h]
0x140023cc5  mov     [rsi+14h], ecx
0x140023cc8  mov     [r15], rsi
0x140023ccb  mov     [r14], ebp
0x140023cce  mov     eax, edi
0x140023cd0  add     rsp, 38h
0x140023cd4  pop     r15
0x140023cd6  pop     r14
0x140023cd8  pop     rdi
0x140023cd9  pop     rsi
0x140023cda  pop     rbp
0x140023cdb  pop     rbx
0x140023cdc  retn
```
