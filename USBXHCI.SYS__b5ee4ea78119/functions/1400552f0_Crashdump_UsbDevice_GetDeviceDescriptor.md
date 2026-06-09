# Crashdump_UsbDevice_GetDeviceDescriptor

- ea: `0x1400552f0`
- end: `0x14005547d`
- name: `Crashdump_UsbDevice_GetDeviceDescriptor`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140054cf4`

## callees

- `0x140054620`
- `0x1400552f0`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140055320`
- `ntoskrnl!DbgPrintEx` at `0x140055421`
- `ntoskrnl!DbgPrintEx` at `0x140055453`
- `ntoskrnl!DbgPrintEx` at `0x140055320`
- `ntoskrnl!DbgPrintEx` at `0x140055421`
- `ntoskrnl!DbgPrintEx` at `0x140055453`

## string_xrefs

- `0x14005530f`: `XHCIDUMP: Crashdump_UsbDevice_GetDeviceDescriptor: begin\n`
- `0x140055442`: `XHCIDUMP: Crashdump_UsbDevice_GetDeviceDescriptor: end 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_UsbDevice_GetDeviceDescriptor(_QWORD *a1, unsigned __int8 **a2)
{
  __int64 v3; // rbx
  __int64 v4; // rcx
  unsigned __int8 *v5; // r13
  unsigned int v6; // ebx
  int v8; // [rsp+D0h] [rbp+8h] BYREF
  int v9; // [rsp+D4h] [rbp+Ch]
  unsigned __int8 **v10; // [rsp+D8h] [rbp+10h]

  v10 = a2;
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_GetDeviceDescriptor: begin\n");
  v3 = *a1;
  memset(*(void **)(*a1 + 448LL), 0, *(unsigned int *)(*a1 + 456LL));
  v4 = a1[15];
  v5 = *(unsigned __int8 **)(v3 + 448);
  v8 = 16778880;
  v9 = 0x400000;
  v8 = Crashdump_Endpoint_SendControlTransfer(v4, &v8, 18, v3 + 440);
  v6 = v8;
  if ( v8 >= 0 )
  {
    DbgPrintEx(
      0x93u,
      3u,
      "XHCIDUMP: %u, %u, %u, %u, %u, %u, %u, %u, %u, %u, %u, %u, %u, %u\n",
      *v5,
      v5[1],
      *((unsigned __int16 *)v5 + 1),
      v5[4],
      v5[5],
      v5[6],
      v5[7],
      *((unsigned __int16 *)v5 + 4),
      *((unsigned __int16 *)v5 + 5),
      *((unsigned __int16 *)v5 + 6),
      v5[14],
      v5[15],
      v5[16],
      v5[17]);
    v6 = v8;
    *v10 = v5;
  }
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_GetDeviceDescriptor: end 0x%X\n", v6);
  return v6;
}

```

## disassembly

```asm
0x1400552f0  mov     [rsp+arg_10], rbx
0x1400552f5  mov     [rsp+arg_8], rdx
0x1400552fa  push    rbp
0x1400552fb  push    rsi
0x1400552fc  push    rdi
0x1400552fd  push    r12
0x1400552ff  push    r13
0x140055301  push    r14
0x140055303  push    r15
0x140055305  sub     rsp, 90h
0x14005530c  mov     rdi, rcx
0x14005530f  lea     r8, aXhcidumpCrashd_48; "XHCIDUMP: Crashdump_UsbDevice_GetDevice"...
0x140055316  mov     ecx, 93h; ComponentId
0x14005531b  mov     edx, 3; Level
0x140055320  call    cs:__imp_DbgPrintEx
0x140055327  nop     dword ptr [rax+rax+00h]
0x14005532c  mov     rbx, [rdi]
0x14005532f  xor     edx, edx; Val
0x140055331  mov     r8d, [rbx+1C8h]; Size
0x140055338  mov     rcx, [rbx+1C0h]; void *
0x14005533f  call    memset
0x140055344  mov     rcx, [rdi+78h]
0x140055348  lea     r9, [rbx+1B8h]
0x14005534f  mov     r13, [r9+8]
0x140055353  lea     rdx, [rsp+0C8h+arg_0]
0x14005535b  mov     r8d, 12h
0x140055361  mov     [rsp+0C8h+arg_0], 1000680h
0x14005536c  mov     [rsp+0C8h+arg_4], 400000h
0x140055377  call    Crashdump_Endpoint_SendControlTransfer
0x14005537c  mov     [rsp+0C8h+arg_0], eax
0x140055383  mov     ebx, eax
0x140055385  test    eax, eax
0x140055387  js      loc_14005543F
0x14005538d  movzx   ecx, byte ptr [r13+11h]
0x140055392  movzx   edx, byte ptr [r13+10h]
0x140055397  movzx   r8d, byte ptr [r13+0Fh]
0x14005539c  movzx   r10d, byte ptr [r13+0Eh]
0x1400553a1  movzx   r11d, word ptr [r13+0Ch]
0x1400553a6  movzx   ebx, word ptr [r13+0Ah]
0x1400553ab  movzx   edi, word ptr [r13+8]
0x1400553b0  movzx   esi, byte ptr [r13+7]
0x1400553b5  movzx   ebp, byte ptr [r13+6]
0x1400553ba  movzx   r14d, byte ptr [r13+5]
0x1400553bf  movzx   r15d, byte ptr [r13+4]
0x1400553c4  movzx   eax, word ptr [r13+2]
0x1400553c9  movzx   r12d, byte ptr [r13+1]
0x1400553ce  movzx   r9d, byte ptr [r13+0]
0x1400553d3  mov     [rsp+0C8h+var_48], ecx
0x1400553da  mov     ecx, 93h; ComponentId
0x1400553df  mov     [rsp+0C8h+var_50], edx
0x1400553e3  mov     edx, 3; Level
0x1400553e8  mov     [rsp+0C8h+var_58], r8d
0x1400553ed  lea     r8, aXhcidumpUUUUUU; "XHCIDUMP: %u, %u, %u, %u, %u, %u, %u, %"...
0x1400553f4  mov     [rsp+0C8h+var_60], r10d
0x1400553f9  mov     [rsp+0C8h+var_68], r11d
0x1400553fe  mov     [rsp+0C8h+var_70], ebx
0x140055402  mov     [rsp+0C8h+var_78], edi
0x140055406  mov     [rsp+0C8h+var_80], esi
0x14005540a  mov     [rsp+0C8h+var_88], ebp
0x14005540e  mov     [rsp+0C8h+var_90], r14d
0x140055413  mov     [rsp+0C8h+var_98], r15d
0x140055418  mov     [rsp+0C8h+var_A0], eax
0x14005541c  mov     [rsp+0C8h+var_A8], r12d
0x140055421  call    cs:__imp_DbgPrintEx
0x140055428  nop     dword ptr [rax+rax+00h]
0x14005542d  mov     rax, [rsp+0C8h+arg_8]
0x140055435  mov     ebx, [rsp+0C8h+arg_0]
0x14005543c  mov     [rax], r13
0x14005543f  mov     r9d, ebx
0x140055442  lea     r8, aXhcidumpCrashd_50; "XHCIDUMP: Crashdump_UsbDevice_GetDevice"...
0x140055449  mov     edx, 3; Level
0x14005544e  mov     ecx, 93h; ComponentId
0x140055453  call    cs:__imp_DbgPrintEx
0x14005545a  nop     dword ptr [rax+rax+00h]
0x14005545f  mov     eax, ebx
0x140055461  mov     rbx, [rsp+0C8h+arg_10]
0x140055469  add     rsp, 90h
0x140055470  pop     r15
0x140055472  pop     r14
0x140055474  pop     r13
0x140055476  pop     r12
0x140055478  pop     rdi
0x140055479  pop     rsi
0x14005547a  pop     rbp
0x14005547b  retn
```
