# WriteMessageOutput

- ea: `0x14002074c`
- end: `0x1400207e0`
- name: `WriteMessageOutput`
- size: `148`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14001dd4c`
- `0x14001ded4`
- `0x14001e20c`
- `0x14001fe30`
- `0x140020c24`

## callees

- `0x14002074c`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x1400207bb`
- `ntdll!NtDeviceIoControlFile` at `0x1400207bb`

## pseudocode

```c
NTSTATUS __fastcall WriteMessageOutput(void **a1, __int64 a2, int a3, __int64 a4, int a5)
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
  v6 = a3 + *(_DWORD *)(a2 + 40);
  v7 = *a1;
  v10[0] = v5;
  v12 = v6;
  v10[1] = a4;
  v9 = 0;
  v11 = a5;
  result = NtDeviceIoControlFile(v7, 0, 0, 0, &v9, 0x500013u, v10, 0x18u, 0, 0);
  if ( result >= 0 )
    return a5 != v9.Information ? 0xC0000001 : 0;
  return result;
}

```

## disassembly

```asm
0x14002074c  mov     r11, rsp
0x14002074f  push    rbx
0x140020750  sub     rsp, 80h
0x140020757  mov     rax, [rdx+60h]
0x14002075b  xorps   xmm0, xmm0
0x14002075e  mov     edx, [rdx+28h]
0x140020761  mov     ebx, [rsp+88h+arg_20]
0x140020768  add     edx, r8d
0x14002076b  mov     rcx, [rcx]; FileHandle
0x14002076e  xor     r8d, r8d; ApcRoutine
0x140020771  mov     [r11-28h], rax
0x140020775  lea     rax, [r11-28h]
0x140020779  mov     [rsp+88h+OutputBufferLength], 0; OutputBufferLength
0x140020781  mov     qword ptr [r11-48h], 0
0x140020789  mov     [rsp+88h+InputBufferLength], 18h; InputBufferLength
0x140020791  mov     [r11-58h], rax
0x140020795  lea     rax, [r11-38h]
0x140020799  mov     [rsp+88h+var_14], edx
0x14002079d  xor     edx, edx; Event
0x14002079f  mov     [r11-20h], r9
0x1400207a3  xor     r9d, r9d; ApcContext
0x1400207a6  mov     [rsp+88h+IoControlCode], 500013h; IoControlCode
0x1400207ae  mov     [r11-68h], rax
0x1400207b2  movups  [rsp+88h+var_38], xmm0
0x1400207b7  mov     [rsp+88h+var_18], ebx
0x1400207bb  call    cs:__imp_NtDeviceIoControlFile
0x1400207c1  test    eax, eax
0x1400207c3  js      short loc_1400207D7
0x1400207c5  mov     rcx, qword ptr [rsp+88h+var_38+8]
0x1400207ca  sub     rcx, rbx
0x1400207cd  neg     rcx
0x1400207d0  sbb     eax, eax
0x1400207d2  and     eax, 0C0000001h
0x1400207d7  add     rsp, 80h
0x1400207de  pop     rbx
0x1400207df  retn
```
