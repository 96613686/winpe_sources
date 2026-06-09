# VidExoVppDelete

- ea: `0x140085cc4`
- end: `0x140085df2`
- name: `VidExoVppDelete`
- size: `302`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400855e0`
- `0x1400858ec`
- `0x140085a04`

## callees

- `0x140012ec4`
- `0x140085cc4`
- `0x1400efed0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140085dc1`
- `ntoskrnl!ObfDereferenceObject` at `0x140085dc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085dd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085dd5`
- `winhvr!WinHvDeleteVp` at `0x140085dac`
- `winhvr!WinHvDeleteVp` at `0x140085dac`
- `winhvr!WinHvUnmapStatsPage` at `0x140085d53`
- `winhvr!WinHvUnmapStatsPage` at `0x140085d70`
- `winhvr!WinHvUnmapStatsPage` at `0x140085d53`
- `winhvr!WinHvUnmapStatsPage` at `0x140085d70`

## pseudocode

```c
void __fastcall VidExoVppDelete(__int64 a1, unsigned int *a2, char a3)
{
  int v6; // edx
  __int64 v7; // rcx
  void *v8; // rcx

  VidClientBufferUninitialize(a2 + 26);
  VidClientBufferUninitialize(a2 + 44);
  VidExoVppUnmapStatePage(a1, *a2, (_DWORD)a2 + 248, 0);
  v6 = *a2;
  *((_QWORD *)a2 + 40) = 0;
  VidExoVppUnmapStatePage(a1, v6, (_DWORD)a2 + 328, 1);
  v7 = *((_QWORD *)a2 + 10);
  *((_QWORD *)a2 + 50) = 0;
  if ( v7 )
  {
    WinHvUnmapStatsPage();
    *((_QWORD *)a2 + 10) = 0;
  }
  if ( *((_QWORD *)a2 + 11) )
  {
    WinHvUnmapStatsPage();
    *((_QWORD *)a2 + 11) = 0;
  }
  if ( *((_BYTE *)a2 + 408) && (!a3 || (*((_DWORD *)VidDeviceExtension + 162) & 0x20) != 0) )
    WinHvDeleteVp(*(_QWORD *)(a1 + 648), *a2);
  v8 = (void *)*((_QWORD *)a2 + 9);
  if ( v8 )
    ObfDereferenceObject(v8);
  ExFreePoolWithTag(a2, 0x72446456u);
}

```

## disassembly

```asm
0x140085cc4  mov     [rsp+arg_0], rbx
0x140085cc9  mov     [rsp+arg_8], rsi
0x140085cce  push    rdi
0x140085ccf  sub     rsp, 30h
0x140085cd3  mov     rdi, rcx
0x140085cd6  mov     sil, r8b
0x140085cd9  lea     rcx, [rdx+68h]
0x140085cdd  mov     rbx, rdx
0x140085ce0  call    VidClientBufferUninitialize
0x140085ce5  lea     rcx, [rbx+0B0h]
0x140085cec  call    VidClientBufferUninitialize
0x140085cf1  mov     rax, [rbx+140h]
0x140085cf8  lea     r8, [rbx+0F8h]
0x140085cff  mov     edx, [rbx]
0x140085d01  xor     r9d, r9d
0x140085d04  mov     rcx, rdi
0x140085d07  mov     [rsp+38h+var_10], rax
0x140085d0c  call    VidExoVppUnmapStatePage
0x140085d11  mov     rax, [rbx+190h]
0x140085d18  lea     r8, [rbx+148h]
0x140085d1f  mov     edx, [rbx]
0x140085d21  mov     r9d, 1
0x140085d27  mov     rcx, rdi
0x140085d2a  mov     [rsp+38h+var_10], rax
0x140085d2f  mov     qword ptr [rbx+140h], 0
0x140085d3a  call    VidExoVppUnmapStatePage
0x140085d3f  mov     rcx, [rbx+50h]
0x140085d43  mov     qword ptr [rbx+190h], 0
0x140085d4e  test    rcx, rcx
0x140085d51  jz      short loc_140085D67
0x140085d53  call    cs:__imp_WinHvUnmapStatsPage
0x140085d5a  nop     dword ptr [rax+rax+00h]
0x140085d5f  mov     qword ptr [rbx+50h], 0
0x140085d67  mov     rcx, [rbx+58h]
0x140085d6b  test    rcx, rcx
0x140085d6e  jz      short loc_140085D84
0x140085d70  call    cs:__imp_WinHvUnmapStatsPage
0x140085d77  nop     dword ptr [rax+rax+00h]
0x140085d7c  mov     qword ptr [rbx+58h], 0
0x140085d84  cmp     byte ptr [rbx+198h], 0
0x140085d8b  jz      short loc_140085DB8
0x140085d8d  test    sil, sil
0x140085d90  jz      short loc_140085DA3
0x140085d92  mov     rax, cs:VidDeviceExtension
0x140085d99  mov     eax, [rax+288h]
0x140085d9f  test    al, 20h
0x140085da1  jz      short loc_140085DB8
0x140085da3  mov     edx, [rbx]
0x140085da5  mov     rcx, [rdi+288h]
0x140085dac  call    cs:__imp_WinHvDeleteVp
0x140085db3  nop     dword ptr [rax+rax+00h]
0x140085db8  mov     rcx, [rbx+48h]; Object
0x140085dbc  test    rcx, rcx
0x140085dbf  jz      short loc_140085DCD
0x140085dc1  call    cs:__imp_ObfDereferenceObject
0x140085dc8  nop     dword ptr [rax+rax+00h]
0x140085dcd  mov     edx, 72446456h; Tag
0x140085dd2  mov     rcx, rbx; P
0x140085dd5  call    cs:__imp_ExFreePoolWithTag
0x140085ddc  nop     dword ptr [rax+rax+00h]
0x140085de1  mov     rbx, [rsp+38h+arg_0]
0x140085de6  mov     rsi, [rsp+38h+arg_8]
0x140085deb  add     rsp, 30h
0x140085def  pop     rdi
0x140085df0  retn
```
