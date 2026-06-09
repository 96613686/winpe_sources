# ReadMessageInput

- ea: `0x14001f6b8`
- end: `0x14001f74c`
- name: `ReadMessageInput`
- size: `148`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14001bddc`
- `0x14001bf28`
- `0x14001e374`
- `0x140020550`
- `0x1400213bc`
- `0x140021484`
- `0x1400215b0`
- `0x140021738`
- `0x140021890`
- `0x1400219e4`

## callees

- `0x14001f6b8`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x14001f727`
- `ntdll!NtDeviceIoControlFile` at `0x14001f727`

## pseudocode

```c
NTSTATUS __fastcall ReadMessageInput(void **a1, __int64 a2, int a3, __int64 a4, int a5)
{
  __int64 v5; // rax
  int v6; // edx
  void *v7; // rcx
  NTSTATUS result; // eax
  struct _IO_STATUS_BLOCK v9; // [rsp+50h] [rbp-38h] BYREF
  _QWORD v10[2]; // [rsp+60h] [rbp-28h] BYREF
  int v11; // [rsp+70h] [rbp-18h]
  int v12; // [rsp+74h] [rbp-14h]

  v5 = *(_QWORD *)(a2 + 96);
  v6 = a3 + *(_DWORD *)(a2 + 44);
  v7 = *a1;
  v10[0] = v5;
  v12 = v6;
  v10[1] = a4;
  v9 = 0;
  v11 = a5;
  result = NtDeviceIoControlFile(v7, 0, 0, 0, &v9, 0x50000Fu, v10, 0x18u, 0, 0);
  if ( result >= 0 )
    return a5 != v9.Information ? 0xC0000001 : 0;
  return result;
}

```

## disassembly

```asm
0x14001f6b8  mov     r11, rsp
0x14001f6bb  push    rbx
0x14001f6bc  sub     rsp, 80h
0x14001f6c3  mov     rax, [rdx+60h]
0x14001f6c7  xorps   xmm0, xmm0
0x14001f6ca  mov     edx, [rdx+2Ch]
0x14001f6cd  mov     ebx, [rsp+88h+arg_20]
0x14001f6d4  add     edx, r8d
0x14001f6d7  mov     rcx, [rcx]; FileHandle
0x14001f6da  xor     r8d, r8d; ApcRoutine
0x14001f6dd  mov     [r11-28h], rax
0x14001f6e1  lea     rax, [r11-28h]
0x14001f6e5  mov     [rsp+88h+OutputBufferLength], 0; OutputBufferLength
0x14001f6ed  mov     qword ptr [r11-48h], 0
0x14001f6f5  mov     [rsp+88h+InputBufferLength], 18h; InputBufferLength
0x14001f6fd  mov     [r11-58h], rax
0x14001f701  lea     rax, [r11-38h]
0x14001f705  mov     [rsp+88h+var_14], edx
0x14001f709  xor     edx, edx; Event
0x14001f70b  mov     [r11-20h], r9
0x14001f70f  xor     r9d, r9d; ApcContext
0x14001f712  mov     [rsp+88h+IoControlCode], 50000Fh; IoControlCode
0x14001f71a  mov     [r11-68h], rax
0x14001f71e  movups  [rsp+88h+var_38], xmm0
0x14001f723  mov     [rsp+88h+var_18], ebx
0x14001f727  call    cs:__imp_NtDeviceIoControlFile
0x14001f72d  test    eax, eax
0x14001f72f  js      short loc_14001F743
0x14001f731  mov     rcx, qword ptr [rsp+88h+var_38+8]
0x14001f736  sub     rcx, rbx
0x14001f739  neg     rcx
0x14001f73c  sbb     eax, eax
0x14001f73e  and     eax, 0C0000001h
0x14001f743  add     rsp, 80h
0x14001f74a  pop     rbx
0x14001f74b  retn
```
