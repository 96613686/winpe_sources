# BthUsb_GetConfigDescriptor(_DEVICE_EXTENSION *)

- ea: `0x14001a4a8`
- end: `0x14001a6e1`
- name: `?BthUsb_GetConfigDescriptor@@_Y2PAGE@@AJPEAU_DEVICE_EXTENSION@@@Z`
- size: `569`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140018b90`

## callees

- `0x14000175c`
- `0x140006db0`
- `0x14000e1c0`
- `0x14001a4a8`
- `0x14001bd90`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001a540`
- `ntoskrnl!ExAllocatePool2` at `0x14001a540`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a5b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a6b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a5b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a6b5`

## pseudocode

```c
__int64 __fastcall BthUsb_GetConfigDescriptor(struct _DEVICE_EXTENSION *a1)
{
  int v2; // edx
  char v3; // di
  unsigned int v5; // esi
  _USB_CONFIGURATION_DESCRIPTOR *Pool2; // rax
  struct _DEVICE_OBJECT *TopOfStack; // rcx
  unsigned int wTotalLength; // edx
  int v9; // r8d
  int v10; // r14d
  _USB_CONFIGURATION_DESCRIPTOR *ConfigDescriptor; // rcx
  int v12; // edx
  int v13; // r8d
  int v14; // edx
  _QWORD v15[26]; // [rsp+50h] [rbp-79h] BYREF

  memset(v15, 0, 0x98u);
  v3 = 1;
  LOBYTE(v2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v2,
    (unsigned int)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    2,
    29,
    (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
  if ( a1->ConfigDescriptor )
    return 0;
  v5 = 9;
  while ( 1 )
  {
    Pool2 = (_USB_CONFIGURATION_DESCRIPTOR *)ExAllocatePool2(64, v5, 1111642965);
    a1->ConfigDescriptor = Pool2;
    if ( !Pool2 )
      break;
    TopOfStack = a1->TopOfStack;
    LODWORD(v15[0]) = 721032;
    HIDWORD(v15[4]) = v5;
    v15[6] = 0;
    v15[5] = Pool2;
    *(_DWORD *)((char *)&v15[16] + 2) = 512;
    v15[7] = 0;
    v10 = USBCallSyncEx(TopOfStack, (unsigned __int64)v15, 500, &a1->RemoveLock);
    if ( v10 < 0 )
    {
      ExFreePoolWithTag(a1->ConfigDescriptor, 0);
      a1->ConfigDescriptor = 0;
      return (unsigned int)v10;
    }
    if ( !HIDWORD(v15[4])
      || (ConfigDescriptor = a1->ConfigDescriptor, wTotalLength = ConfigDescriptor->wTotalLength, wTotalLength <= v5) )
    {
      LOBYTE(wTotalLength) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        wTotalLength,
        v9,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        2,
        30,
        (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
      LOBYTE(v12) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v12,
        v13,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        2,
        31,
        (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        v3 = 0;
      LOBYTE(v14) = v3;
      WPP_RECORDER_AND_TRACE_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        v14,
        a1->ConfigDescriptor->bNumInterfaces,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        2,
        32,
        (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
        a1->ConfigDescriptor->wTotalLength,
        a1->ConfigDescriptor->bNumInterfaces);
      return (unsigned int)v10;
    }
    v5 = ConfigDescriptor->wTotalLength;
    ExFreePoolWithTag(ConfigDescriptor, 0);
    a1->ConfigDescriptor = 0;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14001a4a8  push    rbp
0x14001a4aa  push    rbx
0x14001a4ab  push    rsi
0x14001a4ac  push    rdi
0x14001a4ad  push    r13
0x14001a4af  push    r14
0x14001a4b1  lea     rbp, [rsp-2Fh]
0x14001a4b6  sub     rsp, 0F8h
0x14001a4bd  mov     rbx, rcx
0x14001a4c0  xor     edx, edx; Val
0x14001a4c2  lea     rcx, [rbp+57h+var_D0]; void *
0x14001a4c6  mov     r8d, 98h; Size
0x14001a4cc  call    memset
0x14001a4d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a4d8  mov     r13d, 2
0x14001a4de  mov     dil, 1
0x14001a4e1  mov     eax, [rcx+2Ch]
0x14001a4e4  test    r13b, al
0x14001a4e7  jz      short loc_14001A4F4
0x14001a4e9  cmp     byte ptr [rcx+29h], 4
0x14001a4ed  jb      short loc_14001A4F4
0x14001a4ef  mov     dl, dil
0x14001a4f2  jmp     short loc_14001A4F6
0x14001a4f4  xor     dl, dl
0x14001a4f6  mov     r9, [rcx+40h]
0x14001a4fa  lea     r8, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001a501  mov     rcx, [rcx+18h]
0x14001a505  mov     [rsp+120h+var_E8], r8
0x14001a50a  mov     [rsp+120h+var_F0], 1Dh
0x14001a511  mov     [rsp+120h+var_F8], r13d
0x14001a516  mov     [rsp+120h+var_100], 4
0x14001a51b  call    WPP_RECORDER_AND_TRACE_SF_
0x14001a520  cmp     qword ptr [rbx+68h], 0
0x14001a525  jz      short loc_14001A52E
0x14001a527  xor     eax, eax
0x14001a529  jmp     loc_14001A6D0
0x14001a52e  mov     esi, 9
0x14001a533  mov     edx, esi
0x14001a535  mov     ecx, 40h ; '@'
0x14001a53a  mov     r8d, 42425355h
0x14001a540  call    cs:__imp_ExAllocatePool2
0x14001a547  nop     dword ptr [rax+rax+00h]
0x14001a54c  mov     [rbx+68h], rax
0x14001a550  test    rax, rax
0x14001a553  jz      loc_14001A6CB
0x14001a559  mov     rcx, [rbx+28h]; Tag
0x14001a55d  lea     r9, [rbx+30h]
0x14001a561  mov     r8d, 1F4h
0x14001a567  mov     [rbp+57h+var_D0], 0B0088h
0x14001a56e  lea     rdx, [rbp+57h+var_D0]
0x14001a572  mov     [rbp+57h+var_AC], esi
0x14001a575  mov     [rbp+57h+var_A0], 0
0x14001a57d  mov     [rbp+57h+var_A8], rax
0x14001a581  mov     [rbp+57h+var_4E], 200h
0x14001a588  mov     [rbp+57h+var_98], 0
0x14001a590  call    USBCallSyncEx
0x14001a595  mov     r14d, eax
0x14001a598  test    eax, eax
0x14001a59a  js      loc_14001A6AF
0x14001a5a0  cmp     [rbp+57h+var_AC], 0
0x14001a5a4  jbe     short loc_14001A5CF
0x14001a5a6  mov     rcx, [rbx+68h]; P
0x14001a5aa  movzx   edx, word ptr [rcx+2]
0x14001a5ae  cmp     edx, esi
0x14001a5b0  jbe     short loc_14001A5CF
0x14001a5b2  mov     esi, edx
0x14001a5b4  xor     edx, edx; Tag
0x14001a5b6  call    cs:__imp_ExFreePoolWithTag
0x14001a5bd  nop     dword ptr [rax+rax+00h]
0x14001a5c2  mov     qword ptr [rbx+68h], 0
0x14001a5ca  jmp     loc_14001A533
0x14001a5cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a5d6  mov     eax, [rcx+2Ch]
0x14001a5d9  test    r13b, al
0x14001a5dc  jz      short loc_14001A5E9
0x14001a5de  cmp     byte ptr [rcx+29h], 4
0x14001a5e2  jb      short loc_14001A5E9
0x14001a5e4  mov     dl, dil
0x14001a5e7  jmp     short loc_14001A5EB
0x14001a5e9  xor     dl, dl
0x14001a5eb  mov     r9, [rcx+40h]
0x14001a5ef  lea     rsi, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001a5f6  mov     rcx, [rcx+18h]
0x14001a5fa  mov     [rsp+120h+var_E8], rsi
0x14001a5ff  mov     [rsp+120h+var_F0], 1Eh
0x14001a606  mov     [rsp+120h+var_F8], r13d
0x14001a60b  mov     [rsp+120h+var_100], 4
0x14001a610  call    WPP_RECORDER_AND_TRACE_SF_
0x14001a615  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a61c  mov     eax, [rcx+2Ch]
0x14001a61f  test    r13b, al
0x14001a622  jz      short loc_14001A62F
0x14001a624  cmp     byte ptr [rcx+29h], 4
0x14001a628  jb      short loc_14001A62F
0x14001a62a  mov     dl, dil
0x14001a62d  jmp     short loc_14001A631
0x14001a62f  xor     dl, dl
0x14001a631  mov     r9, [rcx+40h]
0x14001a635  mov     rcx, [rcx+18h]
0x14001a639  mov     [rsp+120h+var_E8], rsi
0x14001a63e  mov     [rsp+120h+var_F0], 1Fh
0x14001a645  mov     [rsp+120h+var_F8], r13d
0x14001a64a  mov     [rsp+120h+var_100], 4
0x14001a64f  call    WPP_RECORDER_AND_TRACE_SF_
0x14001a654  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a65b  mov     eax, [rcx+2Ch]
0x14001a65e  test    r13b, al
0x14001a661  jz      short loc_14001A669
0x14001a663  cmp     byte ptr [rcx+29h], 4
0x14001a667  jnb     short loc_14001A66C
0x14001a669  xor     dil, dil
0x14001a66c  mov     rax, [rbx+68h]
0x14001a670  mov     dl, dil
0x14001a673  movzx   r9d, word ptr [rax+2]
0x14001a678  movzx   r8d, byte ptr [rax+4]
0x14001a67d  mov     [rsp+120h+var_D8], r8d
0x14001a682  mov     [rsp+120h+var_E0], r9d
0x14001a687  mov     r9, [rcx+40h]
0x14001a68b  mov     rcx, [rcx+18h]
0x14001a68f  mov     [rsp+120h+var_E8], rsi
0x14001a694  mov     [rsp+120h+var_F0], 20h ; ' '
0x14001a69b  mov     [rsp+120h+var_F8], r13d
0x14001a6a0  mov     [rsp+120h+var_100], 4
0x14001a6a5  call    WPP_RECORDER_AND_TRACE_SF_dd
0x14001a6aa  mov     eax, r14d
0x14001a6ad  jmp     short loc_14001A6D0
0x14001a6af  mov     rcx, [rbx+68h]; P
0x14001a6b3  xor     edx, edx; Tag
0x14001a6b5  call    cs:__imp_ExFreePoolWithTag
0x14001a6bc  nop     dword ptr [rax+rax+00h]
0x14001a6c1  mov     qword ptr [rbx+68h], 0
0x14001a6c9  jmp     short loc_14001A6AA
0x14001a6cb  mov     eax, 0C000009Ah
0x14001a6d0  add     rsp, 0F8h
0x14001a6d7  pop     r14
0x14001a6d9  pop     r13
0x14001a6db  pop     rdi
0x14001a6dc  pop     rsi
0x14001a6dd  pop     rbx
0x14001a6de  pop     rbp
0x14001a6df  retn
```
