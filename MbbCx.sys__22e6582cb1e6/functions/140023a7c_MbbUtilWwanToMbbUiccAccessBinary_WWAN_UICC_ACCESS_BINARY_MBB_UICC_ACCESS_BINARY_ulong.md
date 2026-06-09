# MbbUtilWwanToMbbUiccAccessBinary(_WWAN_UICC_ACCESS_BINARY *,_MBB_UICC_ACCESS_BINARY * *,ulong *)

- ea: `0x140023a7c`
- end: `0x140023bac`
- name: `?MbbUtilWwanToMbbUiccAccessBinary@@YAHPEAU_WWAN_UICC_ACCESS_BINARY@@PEAPEAU_MBB_UICC_ACCESS_BINARY@@PEAK@Z`
- size: `304`
- prototype: `__int64 __fastcall(struct _WWAN_UICC_ACCESS_BINARY *, struct _MBB_UICC_ACCESS_BINARY **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140020a58`

## callees

- `0x140020d40`
- `0x140023a7c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140023add`
- `ntoskrnl!ExAllocatePool2` at `0x140023add`

## pseudocode

```c
__int64 __fastcall MbbUtilWwanToMbbUiccAccessBinary(
        struct _WWAN_UICC_ACCESS_BINARY *a1,
        struct _MBB_UICC_ACCESS_BINARY **a2,
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
  v8 = *((unsigned __int8 *)a1 + 92);
  v9 = (*((unsigned __int16 *)a1 + 55) + 3) & 0xFFFFFFFC;
  *a3 = 0;
  v10 = ((*((unsigned __int8 *)a1 + 40) + 3) & 0xFFFFFFFC) + v9 + ((v3 + 3) & 0xFFFFFFFC) + ((v8 + 3) & 0xFFFFFFFC) + 44;
  Pool2 = ExAllocatePool2(64, v10, 1683505741);
  if ( Pool2 )
  {
    LODWORD(Size) = *((unsigned __int8 *)a1 + 40);
    v12 = MbbUtilWriteStringToBuffer(
            (unsigned __int8 *)Pool2,
            v10,
            44,
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
    LODWORD(Sizeb) = *((unsigned __int8 *)a1 + 92);
    v14 = MbbUtilWriteStringToBuffer(
            (unsigned __int8 *)Pool2,
            v10,
            v13,
            (struct _MBB_STRING *)(Pool2 + 28),
            (const unsigned __int8 *)a1 + 93,
            Sizeb);
    LODWORD(Sizec) = *((unsigned __int16 *)a1 + 55);
    MbbUtilWriteStringToBuffer(
      (unsigned __int8 *)Pool2,
      v10,
      v14,
      (struct _MBB_STRING *)(Pool2 + 36),
      (const unsigned __int8 *)a1 + 112,
      Sizec);
    *(_DWORD *)Pool2 = *(_DWORD *)a1;
    *(_DWORD *)(Pool2 + 20) = *((_DWORD *)a1 + 21);
    *(_DWORD *)(Pool2 + 24) = *((_DWORD *)a1 + 22);
    *a2 = (struct _MBB_UICC_ACCESS_BINARY *)Pool2;
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
0x140023a7c  push    rbx
0x140023a7e  push    rbp
0x140023a7f  push    rsi
0x140023a80  push    rdi
0x140023a81  push    r14
0x140023a83  push    r15
0x140023a85  sub     rsp, 38h
0x140023a89  movzx   r9d, byte ptr [rcx+49h]
0x140023a8e  mov     rbx, rcx
0x140023a91  mov     ecx, 0FFFFFFFCh
0x140023a96  add     r9d, 3
0x140023a9a  and     r9d, ecx
0x140023a9d  xor     edi, edi
0x140023a9f  mov     r14, r8
0x140023aa2  mov     [rdx], rdi
0x140023aa5  movzx   eax, word ptr [rbx+6Eh]
0x140023aa9  mov     r15, rdx
0x140023aac  movzx   ebp, byte ptr [rbx+5Ch]
0x140023ab0  add     eax, 3
0x140023ab3  and     eax, ecx
0x140023ab5  mov     [r8], edi
0x140023ab8  add     r9d, eax
0x140023abb  add     ebp, 3
0x140023abe  movzx   eax, byte ptr [rbx+28h]
0x140023ac2  and     ebp, ecx
0x140023ac4  add     eax, 3
0x140023ac7  add     ebp, 2Ch ; ','
0x140023aca  and     eax, ecx
0x140023acc  mov     r8d, 6458424Dh
0x140023ad2  add     r9d, eax
0x140023ad5  lea     ecx, [rdi+40h]
0x140023ad8  add     ebp, r9d
0x140023adb  mov     edx, ebp
0x140023add  call    cs:__imp_ExAllocatePool2
0x140023ae4  nop     dword ptr [rax+rax+00h]
0x140023ae9  mov     rsi, rax
0x140023aec  test    rax, rax
0x140023aef  jnz     short loc_140023AFB
0x140023af1  mov     edi, 0C000009Ah
0x140023af6  jmp     loc_140023B9C
0x140023afb  movzx   eax, byte ptr [rbx+28h]
0x140023aff  lea     rcx, [rbx+29h]
0x140023b03  mov     dword ptr [rsp+68h+Size], eax; Size
0x140023b07  lea     r9, [rsi+4]; struct _MBB_STRING *
0x140023b0b  mov     [rsp+68h+Src], rcx; Src
0x140023b10  mov     r8d, 2Ch ; ','; unsigned int
0x140023b16  mov     rcx, rsi; unsigned __int8 *
0x140023b19  mov     edx, ebp; unsigned int
0x140023b1b  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x140023b20  movzx   ecx, byte ptr [rbx+49h]
0x140023b24  lea     rdx, [rbx+4Ah]
0x140023b28  mov     dword ptr [rsp+68h+Size], ecx; Size
0x140023b2c  lea     r9, [rsi+0Ch]; struct _MBB_STRING *
0x140023b30  mov     [rsp+68h+Src], rdx; Src
0x140023b35  mov     r8d, eax; unsigned int
0x140023b38  mov     edx, ebp; unsigned int
0x140023b3a  mov     rcx, rsi; unsigned __int8 *
0x140023b3d  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x140023b42  movzx   ecx, byte ptr [rbx+5Ch]
0x140023b46  lea     rdx, [rbx+5Dh]
0x140023b4a  mov     dword ptr [rsp+68h+Size], ecx; Size
0x140023b4e  lea     r9, [rsi+1Ch]; struct _MBB_STRING *
0x140023b52  mov     [rsp+68h+Src], rdx; Src
0x140023b57  mov     r8d, eax; unsigned int
0x140023b5a  mov     edx, ebp; unsigned int
0x140023b5c  mov     rcx, rsi; unsigned __int8 *
0x140023b5f  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x140023b64  movzx   ecx, word ptr [rbx+6Eh]
0x140023b68  lea     rdx, [rbx+70h]
0x140023b6c  mov     dword ptr [rsp+68h+Size], ecx; Size
0x140023b70  lea     r9, [rsi+24h]; struct _MBB_STRING *
0x140023b74  mov     [rsp+68h+Src], rdx; Src
0x140023b79  mov     r8d, eax; unsigned int
0x140023b7c  mov     edx, ebp; unsigned int
0x140023b7e  mov     rcx, rsi; unsigned __int8 *
0x140023b81  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x140023b86  mov     ecx, [rbx]
0x140023b88  mov     [rsi], ecx
0x140023b8a  mov     ecx, [rbx+54h]
0x140023b8d  mov     [rsi+14h], ecx
0x140023b90  mov     ecx, [rbx+58h]
0x140023b93  mov     [rsi+18h], ecx
0x140023b96  mov     [r15], rsi
0x140023b99  mov     [r14], ebp
0x140023b9c  mov     eax, edi
0x140023b9e  add     rsp, 38h
0x140023ba2  pop     r15
0x140023ba4  pop     r14
0x140023ba6  pop     rdi
0x140023ba7  pop     rsi
0x140023ba8  pop     rbp
0x140023ba9  pop     rbx
0x140023baa  retn
```
