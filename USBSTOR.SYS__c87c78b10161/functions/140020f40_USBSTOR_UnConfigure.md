# USBSTOR_UnConfigure

- ea: `0x140020f40`
- end: `0x140021084`
- name: `USBSTOR_UnConfigure`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14002077c`

## callees

- `0x140001950`
- `0x140003630`
- `0x1400105e8`
- `0x140010664`
- `0x140020f40`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140020fae`
- `ntoskrnl!ExAllocatePool2` at `0x140020fae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020fdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020ffe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020fdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020ffe`

## pseudocode

```c
__int64 __fastcall USBSTOR_UnConfigure(__int64 a1)
{
  _QWORD *v2; // rbx
  __int64 Pool2; // rax
  void *v4; // rsi
  int v5; // edi
  void *v6; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 164, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1313817429, a1, 0, 0);
  v2 = *(_QWORD **)(a1 + 64);
  Pool2 = ExAllocatePool2(64, 40, 1396788565);
  v4 = (void *)Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 40;
    *(_QWORD *)(Pool2 + 24) = 0;
    v5 = USBSTOR_SyncSendUsbRequest(a1, Pool2);
    ExFreePoolWithTag(v4, 0);
    v6 = (void *)v2[11];
    v2[10] = 0;
    if ( v6 )
    {
      ExFreePoolWithTag(v6, 0);
      v2[11] = 0;
    }
    v2[12] = 0;
    v2[13] = 0;
    v2[14] = 0;
  }
  else
  {
    v5 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 165, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1852793717, v5, 0, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140020f40  push    rbx
0x140020f42  push    rsi
0x140020f43  push    rdi
0x140020f44  push    r14
0x140020f46  push    r15
0x140020f48  sub     rsp, 20h
0x140020f4c  mov     rdi, rcx
0x140020f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140020f56  lea     r14, WPP_GLOBAL_Control
0x140020f5d  cmp     rcx, r14
0x140020f60  jz      short loc_140020F84
0x140020f62  mov     eax, [rcx+2Ch]
0x140020f65  test    al, 1
0x140020f67  jz      short loc_140020F84
0x140020f69  cmp     byte ptr [rcx+29h], 4
0x140020f6d  jb      short loc_140020F84
0x140020f6f  mov     rcx, [rcx+18h]
0x140020f73  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140020f7a  mov     edx, 0A4h
0x140020f7f  call    WPP_SF_
0x140020f84  xor     r9d, r9d
0x140020f87  xor     r8d, r8d
0x140020f8a  mov     rdx, rdi
0x140020f8d  mov     ecx, 4E4F4355h
0x140020f92  call    USBSTOR_LogEntry
0x140020f97  mov     rbx, [rdi+40h]
0x140020f9b  mov     r15d, 28h ; '('
0x140020fa1  mov     r8d, 53414D55h
0x140020fa7  mov     edx, r15d
0x140020faa  lea     ecx, [r15+18h]
0x140020fae  call    cs:__imp_ExAllocatePool2
0x140020fb5  nop     dword ptr [rax+rax+00h]
0x140020fba  mov     rsi, rax
0x140020fbd  test    rax, rax
0x140020fc0  jz      short loc_14002102C
0x140020fc2  mov     rdx, rax
0x140020fc5  mov     [rax], r15d
0x140020fc8  mov     rcx, rdi
0x140020fcb  mov     qword ptr [rax+18h], 0
0x140020fd3  call    USBSTOR_SyncSendUsbRequest
0x140020fd8  xor     edx, edx; Tag
0x140020fda  mov     rcx, rsi; P
0x140020fdd  mov     edi, eax
0x140020fdf  call    cs:__imp_ExFreePoolWithTag
0x140020fe6  nop     dword ptr [rax+rax+00h]
0x140020feb  mov     rcx, [rbx+58h]; P
0x140020fef  mov     qword ptr [rbx+50h], 0
0x140020ff7  test    rcx, rcx
0x140020ffa  jz      short loc_140021012
0x140020ffc  xor     edx, edx; Tag
0x140020ffe  call    cs:__imp_ExFreePoolWithTag
0x140021005  nop     dword ptr [rax+rax+00h]
0x14002100a  mov     qword ptr [rbx+58h], 0
0x140021012  mov     qword ptr [rbx+60h], 0
0x14002101a  mov     qword ptr [rbx+68h], 0
0x140021022  mov     qword ptr [rbx+70h], 0
0x14002102a  jmp     short loc_140021031
0x14002102c  mov     edi, 0C000009Ah
0x140021031  mov     rcx, cs:WPP_GLOBAL_Control
0x140021038  cmp     rcx, r14
0x14002103b  jz      short loc_140021062
0x14002103d  mov     eax, [rcx+2Ch]
0x140021040  test    al, 1
0x140021042  jz      short loc_140021062
0x140021044  cmp     byte ptr [rcx+29h], 4
0x140021048  jb      short loc_140021062
0x14002104a  mov     rcx, [rcx+18h]
0x14002104e  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140021055  mov     edx, 0A5h
0x14002105a  mov     r9d, edi
0x14002105d  call    WPP_SF_d
0x140021062  movsxd  rdx, edi
0x140021065  xor     r9d, r9d
0x140021068  xor     r8d, r8d
0x14002106b  mov     ecx, 6E6F6375h
0x140021070  call    USBSTOR_LogEntry
0x140021075  mov     eax, edi
0x140021077  add     rsp, 20h
0x14002107b  pop     r15
0x14002107d  pop     r14
0x14002107f  pop     rdi
0x140021080  pop     rsi
0x140021081  pop     rbx
0x140021082  retn
```
