# SiRemoveDrives(_SU_POOL_OBJECT *,_LIST_ENTRY *,uchar)

- ea: `0x14000d1e8`
- end: `0x14000d295`
- name: `?SiRemoveDrives@@YAHPEAU_SU_POOL_OBJECT@@PEAU_LIST_ENTRY@@E@Z`
- size: `173`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _LIST_ENTRY *, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ee10`
- `0x140019310`

## callees

- `0x14000c8b8`
- `0x14000d1e8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000d27d`
- `KERNEL32!LocalFree` at `0x14000d27d`
- `KERNEL32!DeviceIoControl` at `0x14000d26d`
- `KERNEL32!DeviceIoControl` at `0x14000d26d`

## pseudocode

```c
__int64 __fastcall SiRemoveDrives(struct _SU_POOL_OBJECT *a1, struct _LIST_ENTRY *a2, char a3)
{
  unsigned int v4; // eax
  void *v5; // rbx
  unsigned int v6; // edi
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF
  LPVOID lpInBuffer; // [rsp+68h] [rbp+20h] BYREF

  BytesReturned = 0;
  lpInBuffer = 0;
  v4 = SiIdsExFromList((struct _GUID *)((char *)a1 + 40), a2, (struct _SP_IDS_EX **)&lpInBuffer);
  v5 = lpInBuffer;
  v6 = v4;
  if ( v4 )
    v6 = DeviceIoControl(
           Spaceport,
           a3 != 0 ? 15139872 : 15189012,
           lpInBuffer,
           16 * *((_DWORD *)lpInBuffer + 8) + 36,
           0,
           0,
           &BytesReturned,
           0);
  if ( v5 )
    LocalFree(v5);
  return v6;
}

```

## disassembly

```asm
0x14000d1e8  mov     rax, rsp
0x14000d1eb  mov     [rax+10h], rbx
0x14000d1ef  mov     [rax+18h], rsi
0x14000d1f3  push    rdi
0x14000d1f4  sub     rsp, 40h
0x14000d1f8  mov     sil, r8b
0x14000d1fb  mov     dword ptr [rax+8], 0
0x14000d202  lea     r8, [rax+20h]; struct _SP_IDS_EX **
0x14000d206  mov     qword ptr [rax+20h], 0
0x14000d20e  add     rcx, 28h ; '('; struct _GUID *
0x14000d212  call    ?SiIdsExFromList@@YAHPEAU_GUID@@PEAU_LIST_ENTRY@@PEAPEAU_SP_IDS_EX@@@Z; SiIdsExFromList(_GUID *,_LIST_ENTRY *,_SP_IDS_EX * *)
0x14000d217  mov     rbx, [rsp+48h+lpInBuffer]
0x14000d21c  mov     edi, eax
0x14000d21e  test    eax, eax
0x14000d220  jz      short loc_14000D275
0x14000d222  mov     r9d, [rbx+20h]
0x14000d226  lea     rax, [rsp+48h+BytesReturned]
0x14000d22b  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x14000d232  mov     r8, rbx; lpInBuffer
0x14000d235  shl     r9d, 4
0x14000d239  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x14000d242  add     r9d, 24h ; '$'; nInBufferSize
0x14000d246  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x14000d24b  neg     sil
0x14000d24e  mov     [rsp+48h+nOutBufferSize], 0; nOutBufferSize
0x14000d256  sbb     edx, edx
0x14000d258  mov     [rsp+48h+lpOutBuffer], 0; lpOutBuffer
0x14000d261  and     edx, 0FFFF400Ch
0x14000d267  add     edx, 0E7C414h; dwIoControlCode
0x14000d26d  call    cs:__imp_DeviceIoControl
0x14000d273  mov     edi, eax
0x14000d275  test    rbx, rbx
0x14000d278  jz      short loc_14000D283
0x14000d27a  mov     rcx, rbx; hMem
0x14000d27d  call    cs:__imp_LocalFree
0x14000d283  mov     rbx, [rsp+48h+arg_8]
0x14000d288  mov     eax, edi
0x14000d28a  mov     rsi, [rsp+48h+arg_10]
0x14000d28f  add     rsp, 40h
0x14000d293  pop     rdi
0x14000d294  retn
```
