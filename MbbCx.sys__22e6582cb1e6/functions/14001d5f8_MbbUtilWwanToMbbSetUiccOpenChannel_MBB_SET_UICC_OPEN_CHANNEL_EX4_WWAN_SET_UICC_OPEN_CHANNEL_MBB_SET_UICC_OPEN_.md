# MbbUtilWwanToMbbSetUiccOpenChannel<_MBB_SET_UICC_OPEN_CHANNEL_EX4>(_WWAN_SET_UICC_OPEN_CHANNEL *,_MBB_SET_UICC_OPEN_CHANNEL_EX4 * *,ulong *)

- ea: `0x14001d5f8`
- end: `0x14001d6be`
- name: `??$MbbUtilWwanToMbbSetUiccOpenChannel@U_MBB_SET_UICC_OPEN_CHANNEL_EX4@@@@YAHPEAU_WWAN_SET_UICC_OPEN_CHANNEL@@PEAPEAU_MBB_SET_UICC_OPEN_CHANNEL_EX4@@PEAK@Z`
- size: `198`
- prototype: `__int64 __fastcall(__int64, __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400168f0`

## callees

- `0x14001d5f8`
- `0x140020d40`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001d643`
- `ntoskrnl!ExAllocatePool2` at `0x14001d643`

## pseudocode

```c
__int64 __fastcall MbbUtilWwanToMbbSetUiccOpenChannel<_MBB_SET_UICC_OPEN_CHANNEL_EX4>(
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
  v7 = (v4 & 0xFFFFFFFC) + 20;
  Pool2 = ExAllocatePool2(64, v7, 1683505741);
  if ( !Pool2 )
    return 3221225626LL;
  LODWORD(Size) = *(_DWORD *)a1;
  MbbUtilWriteStringToBuffer(
    (unsigned __int8 *)Pool2,
    v7,
    20,
    (struct _MBB_STRING *)&v11,
    (const unsigned __int8 *)(a1 + 4),
    Size);
  *(_DWORD *)Pool2 = HIDWORD(v11);
  *(_DWORD *)(Pool2 + 4) = v11;
  *(_DWORD *)(Pool2 + 8) = *(_DWORD *)(a1 + 36);
  *(_DWORD *)(Pool2 + 12) = *(_DWORD *)(a1 + 40);
  *(_DWORD *)(Pool2 + 16) = *(_DWORD *)(a1 + 44);
  result = 0;
  *a2 = Pool2;
  *a3 = v7;
  return result;
}

```

## disassembly

```asm
0x14001d5f8  mov     [rsp+arg_8], rbx
0x14001d5fd  mov     [rsp+arg_10], rsi
0x14001d602  push    rdi
0x14001d603  push    r14
0x14001d605  push    r15
0x14001d607  sub     rsp, 30h
0x14001d60b  mov     esi, [rcx]
0x14001d60d  mov     r14, r8
0x14001d610  add     esi, 3
0x14001d613  mov     qword ptr [rdx], 0
0x14001d61a  mov     r15, rdx
0x14001d61d  mov     dword ptr [r8], 0
0x14001d624  mov     rdi, rcx
0x14001d627  mov     [rsp+48h+arg_0], 0
0x14001d630  and     esi, 0FFFFFFFCh
0x14001d633  mov     ecx, 40h ; '@'
0x14001d638  add     esi, 14h
0x14001d63b  mov     r8d, 6458424Dh
0x14001d641  mov     edx, esi
0x14001d643  call    cs:__imp_ExAllocatePool2
0x14001d64a  nop     dword ptr [rax+rax+00h]
0x14001d64f  mov     rbx, rax
0x14001d652  test    rax, rax
0x14001d655  jnz     short loc_14001D65E
0x14001d657  mov     eax, 0C000009Ah
0x14001d65c  jmp     short loc_14001D6A9
0x14001d65e  mov     eax, [rdi]
0x14001d660  lea     rcx, [rdi+4]
0x14001d664  mov     dword ptr [rsp+48h+Size], eax; Size
0x14001d668  lea     r9, [rsp+48h+arg_0]; struct _MBB_STRING *
0x14001d66d  mov     [rsp+48h+Src], rcx; Src
0x14001d672  mov     r8d, 14h; unsigned int
0x14001d678  mov     rcx, rbx; unsigned __int8 *
0x14001d67b  mov     edx, esi; unsigned int
0x14001d67d  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x14001d682  mov     eax, dword ptr [rsp+48h+arg_0+4]
0x14001d686  mov     [rbx], eax
0x14001d688  mov     eax, dword ptr [rsp+48h+arg_0]
0x14001d68c  mov     [rbx+4], eax
0x14001d68f  mov     eax, [rdi+24h]
0x14001d692  mov     [rbx+8], eax
0x14001d695  mov     eax, [rdi+28h]
0x14001d698  mov     [rbx+0Ch], eax
0x14001d69b  mov     eax, [rdi+2Ch]
0x14001d69e  mov     [rbx+10h], eax
0x14001d6a1  xor     eax, eax
0x14001d6a3  mov     [r15], rbx
0x14001d6a6  mov     [r14], esi
0x14001d6a9  mov     rbx, [rsp+48h+arg_8]
0x14001d6ae  mov     rsi, [rsp+48h+arg_10]
0x14001d6b3  add     rsp, 30h
0x14001d6b7  pop     r15
0x14001d6b9  pop     r14
0x14001d6bb  pop     rdi
0x14001d6bc  retn
```
