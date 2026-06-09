# MbbUtilWwanToMbbSetUiccOpenChannel<_MBB_SET_UICC_OPEN_CHANNEL>(_WWAN_SET_UICC_OPEN_CHANNEL *,_MBB_SET_UICC_OPEN_CHANNEL * *,ulong *)

- ea: `0x14001d530`
- end: `0x14001d5f0`
- name: `??$MbbUtilWwanToMbbSetUiccOpenChannel@U_MBB_SET_UICC_OPEN_CHANNEL@@@@YAHPEAU_WWAN_SET_UICC_OPEN_CHANNEL@@PEAPEAU_MBB_SET_UICC_OPEN_CHANNEL@@PEAK@Z`
- size: `192`
- prototype: `__int64 __fastcall(__int64, __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400168f0`

## callees

- `0x14001d530`
- `0x140020d40`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001d57b`
- `ntoskrnl!ExAllocatePool2` at `0x14001d57b`

## pseudocode

```c
__int64 __fastcall MbbUtilWwanToMbbSetUiccOpenChannel<_MBB_SET_UICC_OPEN_CHANNEL>(
        __int64 a1,
        __int64 *a2,
        unsigned int *a3)
{
  int v4; // esi
  unsigned int v7; // esi
  __int64 Pool2; // rbx
  __int64 result; // rax
  size_t Size; // [rsp+28h] [rbp-20h]
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  v4 = *(_DWORD *)a1 + 3;
  *a2 = 0;
  *a3 = 0;
  v11 = 0;
  v7 = (v4 & 0xFFFFFFFC) + 16;
  Pool2 = ExAllocatePool2(64, v7, 1683505741);
  if ( !Pool2 )
    return 3221225626LL;
  LODWORD(Size) = *(_DWORD *)a1;
  MbbUtilWriteStringToBuffer(
    (unsigned __int8 *)Pool2,
    v7,
    16,
    (struct _MBB_STRING *)&v11,
    (const unsigned __int8 *)(a1 + 4),
    Size);
  *(_DWORD *)Pool2 = HIDWORD(v11);
  *(_DWORD *)(Pool2 + 4) = v11;
  *(_DWORD *)(Pool2 + 8) = *(_DWORD *)(a1 + 36);
  *(_DWORD *)(Pool2 + 12) = *(_DWORD *)(a1 + 40);
  result = 0;
  *a2 = Pool2;
  *a3 = v7;
  return result;
}

```

## disassembly

```asm
0x14001d530  mov     [rsp+arg_8], rbx
0x14001d535  mov     [rsp+arg_10], rsi
0x14001d53a  push    rdi
0x14001d53b  push    r14
0x14001d53d  push    r15
0x14001d53f  sub     rsp, 30h
0x14001d543  mov     esi, [rcx]
0x14001d545  mov     r14, r8
0x14001d548  add     esi, 3
0x14001d54b  mov     qword ptr [rdx], 0
0x14001d552  mov     r15, rdx
0x14001d555  mov     dword ptr [r8], 0
0x14001d55c  mov     rdi, rcx
0x14001d55f  mov     [rsp+48h+arg_0], 0
0x14001d568  and     esi, 0FFFFFFFCh
0x14001d56b  mov     ecx, 40h ; '@'
0x14001d570  add     esi, 10h
0x14001d573  mov     r8d, 6458424Dh
0x14001d579  mov     edx, esi
0x14001d57b  call    cs:__imp_ExAllocatePool2
0x14001d582  nop     dword ptr [rax+rax+00h]
0x14001d587  mov     rbx, rax
0x14001d58a  test    rax, rax
0x14001d58d  jnz     short loc_14001D596
0x14001d58f  mov     eax, 0C000009Ah
0x14001d594  jmp     short loc_14001D5DB
0x14001d596  mov     eax, [rdi]
0x14001d598  lea     rcx, [rdi+4]
0x14001d59c  mov     dword ptr [rsp+48h+Size], eax; Size
0x14001d5a0  lea     r9, [rsp+48h+arg_0]; struct _MBB_STRING *
0x14001d5a5  mov     [rsp+48h+Src], rcx; Src
0x14001d5aa  mov     r8d, 10h; unsigned int
0x14001d5b0  mov     rcx, rbx; unsigned __int8 *
0x14001d5b3  mov     edx, esi; unsigned int
0x14001d5b5  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x14001d5ba  mov     eax, dword ptr [rsp+48h+arg_0+4]
0x14001d5be  mov     [rbx], eax
0x14001d5c0  mov     eax, dword ptr [rsp+48h+arg_0]
0x14001d5c4  mov     [rbx+4], eax
0x14001d5c7  mov     eax, [rdi+24h]
0x14001d5ca  mov     [rbx+8], eax
0x14001d5cd  mov     eax, [rdi+28h]
0x14001d5d0  mov     [rbx+0Ch], eax
0x14001d5d3  xor     eax, eax
0x14001d5d5  mov     [r15], rbx
0x14001d5d8  mov     [r14], esi
0x14001d5db  mov     rbx, [rsp+48h+arg_8]
0x14001d5e0  mov     rsi, [rsp+48h+arg_10]
0x14001d5e5  add     rsp, 30h
0x14001d5e9  pop     r15
0x14001d5eb  pop     r14
0x14001d5ed  pop     rdi
0x14001d5ee  retn
```
