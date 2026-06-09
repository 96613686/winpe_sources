# BfpCreatePathTree

- ea: `0x140020180`
- end: `0x14002021f`
- name: `BfpCreatePathTree`
- size: `159`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140019c44`
- `0x14001b280`
- `0x14001cd84`
- `0x14002001c`

## callees

- `0x140003304`
- `0x140020180`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400201a0`
- `ntoskrnl!ExAllocatePool2` at `0x1400201a0`

## pseudocode

```c
__int64 __fastcall BfpCreatePathTree(_QWORD *a1)
{
  _QWORD *Pool2; // rax
  int v3; // edx

  *a1 = 0;
  Pool2 = (_QWORD *)ExAllocatePool2(256, 16, 1886209602);
  if ( Pool2 )
  {
    *Pool2 = 0;
    Pool2[1] = 0;
    *a1 = Pool2;
    return 0;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v3,
        8,
        12,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        242);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140020180  push    rbx
0x140020182  sub     rsp, 40h
0x140020186  mov     rbx, rcx
0x140020189  mov     qword ptr [rcx], 0
0x140020190  mov     ecx, 100h
0x140020195  mov     edx, 10h
0x14002019a  mov     r8d, 706D4642h
0x1400201a0  call    cs:__imp_ExAllocatePool2
0x1400201a7  nop     dword ptr [rax+rax+00h]
0x1400201ac  test    rax, rax
0x1400201af  jz      short loc_1400201CC
0x1400201b1  mov     qword ptr [rax], 0
0x1400201b8  mov     qword ptr [rax+8], 0
0x1400201c0  mov     [rbx], rax
0x1400201c3  xor     eax, eax
0x1400201c5  add     rsp, 40h
0x1400201c9  pop     rbx
0x1400201ca  retn
0x1400201cc  lea     rax, WPP_RECORDER_INITIALIZED
0x1400201d3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400201da  jz      short loc_140020218
0x1400201dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400201e3  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400201ea  mov     r9d, 0Ch
0x1400201f0  mov     [rsp+48h+var_18], 1F2h
0x1400201f8  mov     [rsp+48h+var_20], rax
0x1400201fd  mov     dl, 2
0x1400201ff  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140020206  mov     rcx, [rcx+40h]
0x14002020a  lea     r8d, [r9-4]
0x14002020e  mov     [rsp+48h+var_28], rax
0x140020213  call    WPP_RECORDER_SF_sD
0x140020218  mov     eax, 0C000009Ah
0x14002021d  jmp     short loc_1400201C5
```
