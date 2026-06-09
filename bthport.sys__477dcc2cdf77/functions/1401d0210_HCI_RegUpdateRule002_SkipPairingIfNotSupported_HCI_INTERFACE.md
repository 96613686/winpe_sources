# HCI_RegUpdateRule002_SkipPairingIfNotSupported(HCI_INTERFACE *)

- ea: `0x1401d0210`
- end: `0x1401d08f8`
- name: `?HCI_RegUpdateRule002_SkipPairingIfNotSupported@@YAJPEAUHCI_INTERFACE@@@Z`
- size: `1768`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1401b99bc`

## callees

- `0x140005608`
- `0x140005690`
- `0x1400a95f0`
- `0x140165540`
- `0x140165640`
- `0x1401d0210`
- `0x140209168`
- `0x140209540`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x1401d04a5`
- `ntoskrnl!ZwEnumerateKey` at `0x1401d0519`
- `ntoskrnl!ZwEnumerateKey` at `0x1401d04a5`
- `ntoskrnl!ZwEnumerateKey` at `0x1401d0519`
- `ntoskrnl!ZwClose` at `0x1401d05c0`
- `ntoskrnl!ZwClose` at `0x1401d07dc`
- `ntoskrnl!ZwClose` at `0x1401d07f5`
- `ntoskrnl!ZwClose` at `0x1401d05c0`
- `ntoskrnl!ZwClose` at `0x1401d07dc`
- `ntoskrnl!ZwClose` at `0x1401d07f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d04c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d07a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d07c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d080f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0847`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0868`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d04c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d07a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d07c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d080f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0847`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0868`
- `ntoskrnl!ExAllocatePool2` at `0x1401d033a`
- `ntoskrnl!ExAllocatePool2` at `0x1401d03c4`
- `ntoskrnl!ExAllocatePool2` at `0x1401d041f`
- `ntoskrnl!ExAllocatePool2` at `0x1401d04e0`
- `ntoskrnl!ExAllocatePool2` at `0x1401d0579`
- `ntoskrnl!ExAllocatePool2` at `0x1401d033a`
- `ntoskrnl!ExAllocatePool2` at `0x1401d03c4`
- `ntoskrnl!ExAllocatePool2` at `0x1401d041f`
- `ntoskrnl!ExAllocatePool2` at `0x1401d04e0`
- `ntoskrnl!ExAllocatePool2` at `0x1401d0579`

## string_xrefs

- `0x1401d02c1`: `\Registry\Machine\System\CurrentControlSet\Services\BTHPORT\Parameters\ExceptionDB\Rules\002_SkipPairingIfNotSupported`
- `0x1401d0725`: `\Registry\Machine\System\CurrentControlSet\Services\BTHPORT\Parameters\ExceptionDB\Rules\002_SkipPairingIfNotSupported`

## pseudocode

```c
__int64 __fastcall HCI_RegUpdateRule002_SkipPairingIfNotSupported(struct HCI_INTERFACE *a1)
{
  ULONG v1; // r12d
  _LIST_ENTRY *v3; // rsi
  char v4; // di
  char v5; // dl
  __int16 DeviceType; // ax
  NTSTATUS KeyValueUlong; // ebx
  _DEVICE_EXCEPTION *v8; // r14
  char v9; // dl
  int v10; // r8d
  _DEVICE_EXCEPTION *Pool2; // rax
  PDEVICE_OBJECT v12; // rcx
  char v13; // dl
  ULONG Length; // ebx
  unsigned int *v15; // r15
  char v16; // dl
  NTSTATUS v17; // eax
  int v18; // edx
  PVOID v19; // rsi
  int v20; // edx
  int v21; // edx
  void **p_Flink; // rax
  PVOID v23; // r12
  bool v24; // dl
  bool v25; // dl
  _LIST_ENTRY *Flink; // rcx
  _LIST_ENTRY *v27; // rax
  _LIST_ENTRY *Blink; // rdx
  __int16 v29; // ax
  __int64 *v30; // rdx
  __int16 v32; // [rsp+30h] [rbp-59h]
  ULONG ResultLength; // [rsp+50h] [rbp-39h] BYREF
  PVOID P; // [rsp+58h] [rbp-31h]
  HANDLE KeyHandle; // [rsp+60h] [rbp-29h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-21h] BYREF
  int v37; // [rsp+70h] [rbp-19h]
  __int64 v38; // [rsp+78h] [rbp-11h]
  int v39; // [rsp+88h] [rbp-1h]

  v1 = 0;
  KeyHandle = 0;
  v3 = 0;
  Handle = 0;
  v37 = 0;
  ResultLength = 0;
  v4 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v5 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v5 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v5 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      DeviceType != 0,
      a1->IfrLog,
      5,
      2,
      184,
      (__int64)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids);
  v39 = 4;
  KeyValueUlong = BthOpenKey(
                    0,
                    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\BTHPORT\\Parameters\\ExceptionDB\\Rules\\0"
                     "02_SkipPairingIfNotSupported",
                    &KeyHandle);
  if ( KeyValueUlong < 0 )
  {
    v8 = 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v9 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      v9 = 0;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v9,
      1,
      a1->IfrLog,
      2,
      2,
      185,
      (__int64)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids);
    goto LABEL_72;
  }
  Pool2 = (_DEVICE_EXCEPTION *)ExAllocatePool2(256, 16, 1346917442);
  v8 = Pool2;
  if ( !Pool2 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v13 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      v13 = 0;
    v32 = 186;
LABEL_17:
    WPP_RECORDER_AND_TRACE_SF_(
      v12->AttachedDevice,
      v13,
      1,
      a1->IfrLog,
      2,
      2,
      v32,
      (__int64)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids);
    KeyValueUlong = -1073741670;
    goto LABEL_72;
  }
  Pool2->ExceptionRules.Blink = &Pool2->ExceptionRules;
  Length = 78;
  Pool2->ExceptionRules.Flink = &Pool2->ExceptionRules;
  a1->DeviceExceptions[1] = Pool2;
  v38 = 78;
  v15 = (unsigned int *)ExAllocatePool2(256, 78, 1346917442);
  if ( !v15 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v13 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      v13 = 0;
    v32 = 187;
    goto LABEL_17;
  }
  P = (PVOID)ExAllocatePool2(256, 512, 1346917442);
  if ( !P )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v16 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      v16 = 0;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v16,
      1,
      a1->IfrLog,
      2,
      2,
      188,
      (__int64)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids);
    KeyValueUlong = -1073741670;
    goto LABEL_71;
  }
  while ( 1 )
  {
    v17 = ZwEnumerateKey(KeyHandle, v1, KeyBasicInformation, v15, Length, &ResultLength);
    KeyValueUlong = v17;
    if ( v17 == -2147483643 || v17 == -1073741789 )
    {
      ExFreePoolWithTag(v15, 0);
      v15 = (unsigned int *)ExAllocatePool2(256, ResultLength, 1346917442);
      if ( !v15 )
      {
        v25 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v25,
          1,
          a1->IfrLog,
          2,
          2,
          189,
          (__int64)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids);
        v3 = 0;
        goto LABEL_68;
      }
      v38 = ResultLength;
      KeyValueUlong = ZwEnumerateKey(KeyHandle, v1, KeyBasicInformation, v15, ResultLength, &ResultLength);
    }
    if ( KeyValueUlong == -2147483622 )
    {
      KeyValueUlong = 0;
LABEL_56:
      v3 = 0;
LABEL_69:
      v23 = P;
      goto LABEL_70;
    }
    if ( KeyValueUlong < 0 )
    {
      LOBYTE(v18) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      WPP_RECORDER_AND_TRACE_SF_Sd(
        WPP_GLOBAL_Control->AttachedDevice,
        v18,
        (unsigned int)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids,
        a1->IfrLog,
        2,
        2,
        190,
        (__int64)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids,
        (__int64)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\BTHPORT\\Parameters\\ExceptionDB\\Rules\\002_"
                  "SkipPairingIfNotSupported",
        KeyValueUlong);
      goto LABEL_56;
    }
    v19 = P;
    memmove(P, v15 + 4, v15[3]);
    KeyValueUlong = BthOpenKey(KeyHandle, v19, &Handle);
    if ( KeyValueUlong < 0 )
    {
      LOBYTE(v20) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      WPP_RECORDER_AND_TRACE_SF_Sd(
        WPP_GLOBAL_Control->AttachedDevice,
        v20,
        (unsigned int)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids,
        a1->IfrLog,
        2,
        2,
        191,
        (__int64)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids,
        (__int64)v19,
        KeyValueUlong);
      goto LABEL_56;
    }
    v3 = (_LIST_ENTRY *)ExAllocatePool2(256, 24, 1346917442);
    if ( !v3 )
    {
      v24 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v24,
        1,
        a1->IfrLog,
        2,
        2,
        192,
        (__int64)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids);
LABEL_68:
      KeyValueUlong = -1073741670;
      goto LABEL_69;
    }
    KeyValueUlong = BthQueryKeyValueUlong(Handle);
    if ( KeyValueUlong < 0 )
      break;
    LOWORD(v3[1].Flink) = v37;
    if ( Handle )
    {
      ZwClose(Handle);
      Handle = 0;
    }
    p_Flink = (void **)&v8->ExceptionRules.Blink->Flink;
    if ( *p_Flink != v8 )
LABEL_84:
      __fastfail(3u);
    Length = v38;
    ++v1;
    v3->Flink = &v8->ExceptionRules;
    v3->Blink = (_LIST_ENTRY *)p_Flink;
    *p_Flink = v3;
    v8->ExceptionRules.Blink = v3;
  }
  LOBYTE(v21) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  v23 = P;
  WPP_RECORDER_AND_TRACE_SF_Sd(
    WPP_GLOBAL_Control->AttachedDevice,
    v21,
    (unsigned int)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids,
    a1->IfrLog,
    2,
    2,
    193,
    (__int64)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids,
    (__int64)P,
    KeyValueUlong);
LABEL_70:
  ExFreePoolWithTag(v23, 0);
  if ( v15 )
LABEL_71:
    ExFreePoolWithTag(v15, 0);
LABEL_72:
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( Handle )
  {
    ZwClose(Handle);
    Handle = 0;
  }
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( KeyValueUlong < 0 && v8 )
  {
    while ( 1 )
    {
      Flink = v8->ExceptionRules.Flink;
      if ( (_DEVICE_EXCEPTION *)v8->ExceptionRules.Flink == v8 )
        break;
      v27 = Flink->Flink;
      if ( Flink->Flink->Blink != Flink )
        goto LABEL_84;
      Blink = Flink->Blink;
      if ( Blink->Flink != Flink )
        goto LABEL_84;
      Blink->Flink = v27;
      v27->Blink = Blink;
      ExFreePoolWithTag(Flink, 0);
    }
    a1->DeviceExceptions[1] = 0;
    ExFreePoolWithTag(v8, 0);
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v4 = 0;
  v29 = WPP_GLOBAL_Control->DeviceType;
  if ( v4 || v29 )
  {
    v30 = WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids;
    LOBYTE(v30) = v4;
    LOBYTE(v10) = v29 != 0;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v30,
      v10,
      a1->IfrLog,
      5,
      2,
      194,
      (__int64)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids,
      KeyValueUlong);
  }
  return (unsigned int)KeyValueUlong;
}

```

## disassembly

```asm
0x1401d0210  push    rbp
0x1401d0212  push    rbx
0x1401d0213  push    rsi
0x1401d0214  push    rdi
0x1401d0215  push    r12
0x1401d0217  push    r13
0x1401d0219  push    r14
0x1401d021b  push    r15
0x1401d021d  lea     rbp, [rsp-1Fh]
0x1401d0222  sub     rsp, 0A8h
0x1401d0229  mov     rax, cs:__security_cookie
0x1401d0230  xor     rax, rsp
0x1401d0233  mov     [rbp+57h+var_48], rax
0x1401d0237  xor     r12d, r12d
0x1401d023a  mov     r13, rcx
0x1401d023d  mov     [rbp+57h+KeyHandle], r12
0x1401d0241  mov     esi, r12d
0x1401d0244  mov     [rbp+57h+Handle], r12
0x1401d0248  mov     [rbp+57h+var_70], r12d
0x1401d024c  mov     [rbp+57h+var_90], r12d
0x1401d0250  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d0257  lea     r15d, [r12+2]
0x1401d025c  lea     edi, [r12+1]
0x1401d0261  mov     eax, [rcx+2Ch]
0x1401d0264  test    r15b, al
0x1401d0267  jz      short loc_1401D0272
0x1401d0269  cmp     byte ptr [rcx+29h], 5
0x1401d026d  mov     dl, dil
0x1401d0270  jnb     short loc_1401D0275
0x1401d0272  mov     dl, r12b
0x1401d0275  movzx   eax, word ptr [rcx+48h]
0x1401d0279  lea     r9, WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids
0x1401d0280  test    ax, ax
0x1401d0283  setnz   r8b
0x1401d0287  test    dl, dl
0x1401d0289  jnz     short loc_1401D0290
0x1401d028b  test    ax, ax
0x1401d028e  jz      short loc_1401D02B6
0x1401d0290  mov     rcx, [rcx+18h]
0x1401d0294  mov     [rsp+0E0h+var_A8], r9
0x1401d0299  mov     r9, [r13+10B0h]
0x1401d02a0  mov     [rsp+0E0h+var_B0], 0B8h
0x1401d02a7  mov     dword ptr [rsp+0E0h+ResultLength], r15d
0x1401d02ac  mov     byte ptr [rsp+0E0h+Length], 5
0x1401d02b1  call    WPP_RECORDER_AND_TRACE_SF_
0x1401d02b6  lea     r8, [rbp+57h+KeyHandle]
0x1401d02ba  mov     [rbp+57h+var_58], 4
0x1401d02c1  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x1401d02c8  xor     ecx, ecx
0x1401d02ca  call    BthOpenKey
0x1401d02cf  mov     ebx, eax
0x1401d02d1  test    eax, eax
0x1401d02d3  jns     short loc_1401D0328
0x1401d02d5  mov     r14, r12
0x1401d02d8  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d02df  mov     ecx, [rax+2Ch]
0x1401d02e2  test    r15b, cl
0x1401d02e5  jz      short loc_1401D02F0
0x1401d02e7  mov     dl, dil
0x1401d02ea  cmp     [rax+29h], r15b
0x1401d02ee  jnb     short loc_1401D02F3
0x1401d02f0  mov     dl, r12b
0x1401d02f3  mov     r9, [r13+10B0h]
0x1401d02fa  lea     r8, WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids
0x1401d0301  mov     rcx, [rax+18h]
0x1401d0305  mov     [rsp+0E0h+var_A8], r8
0x1401d030a  mov     r8b, dil
0x1401d030d  mov     [rsp+0E0h+var_B0], 0B9h
0x1401d0314  mov     dword ptr [rsp+0E0h+ResultLength], r15d
0x1401d0319  mov     byte ptr [rsp+0E0h+Length], r15b
0x1401d031e  call    WPP_RECORDER_AND_TRACE_SF_
0x1401d0323  jmp     loc_1401D07D3
0x1401d0328  mov     ebx, 50485442h
0x1401d032d  mov     edx, 10h
0x1401d0332  mov     r8d, ebx
0x1401d0335  mov     ecx, 100h
0x1401d033a  call    cs:__imp_ExAllocatePool2
0x1401d0341  nop     dword ptr [rax+rax+00h]
0x1401d0346  mov     r14, rax
0x1401d0349  test    rax, rax
0x1401d034c  jnz     short loc_1401D03A3
0x1401d034e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d0355  mov     eax, [rcx+2Ch]
0x1401d0358  test    r15b, al
0x1401d035b  jz      short loc_1401D0366
0x1401d035d  mov     dl, dil
0x1401d0360  cmp     [rcx+29h], r15b
0x1401d0364  jnb     short loc_1401D0369
0x1401d0366  mov     dl, r12b
0x1401d0369  lea     r8, WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids
0x1401d0370  mov     [rsp+0E0h+var_A8], r8
0x1401d0375  mov     [rsp+0E0h+var_B0], 0BAh
0x1401d037c  mov     r9, [r13+10B0h]
0x1401d0383  mov     r8b, dil
0x1401d0386  mov     rcx, [rcx+18h]
0x1401d038a  mov     dword ptr [rsp+0E0h+ResultLength], r15d
0x1401d038f  mov     byte ptr [rsp+0E0h+Length], r15b
0x1401d0394  call    WPP_RECORDER_AND_TRACE_SF_
0x1401d0399  mov     ebx, 0C000009Ah
0x1401d039e  jmp     loc_1401D07D3
0x1401d03a3  mov     r8d, ebx
0x1401d03a6  mov     [rax+8], r14
0x1401d03aa  mov     ebx, 4Eh ; 'N'
0x1401d03af  mov     [rax], r14
0x1401d03b2  mov     edx, ebx
0x1401d03b4  mov     [r13+10A8h], r14
0x1401d03bb  mov     ecx, 100h
0x1401d03c0  mov     [rbp+57h+var_68], rbx
0x1401d03c4  call    cs:__imp_ExAllocatePool2
0x1401d03cb  nop     dword ptr [rax+rax+00h]
0x1401d03d0  mov     r15, rax
0x1401d03d3  test    rax, rax
0x1401d03d6  jnz     short loc_1401D040F
0x1401d03d8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d03df  lea     r15d, [rbx-4Ch]
0x1401d03e3  mov     eax, [rcx+2Ch]
0x1401d03e6  test    r15b, al
0x1401d03e9  jz      short loc_1401D03F4
0x1401d03eb  mov     dl, dil
0x1401d03ee  cmp     [rcx+29h], r15b
0x1401d03f2  jnb     short loc_1401D03F7
0x1401d03f4  mov     dl, r12b
0x1401d03f7  lea     r8, WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids
0x1401d03fe  mov     [rsp+0E0h+var_A8], r8
0x1401d0403  mov     [rsp+0E0h+var_B0], 0BBh
0x1401d040a  jmp     loc_1401D037C
0x1401d040f  mov     edx, 200h
0x1401d0414  mov     ecx, 100h
0x1401d0419  mov     r8d, 50485442h
0x1401d041f  call    cs:__imp_ExAllocatePool2
0x1401d0426  nop     dword ptr [rax+rax+00h]
0x1401d042b  mov     [rbp+57h+P], rax
0x1401d042f  test    rax, rax
0x1401d0432  jnz     short loc_1401D048B
0x1401d0434  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d043b  mov     eax, [rcx+2Ch]
0x1401d043e  test    al, 2
0x1401d0440  jz      short loc_1401D044B
0x1401d0442  cmp     byte ptr [rcx+29h], 2
0x1401d0446  mov     dl, dil
0x1401d0449  jnb     short loc_1401D044E
0x1401d044b  mov     dl, r12b
0x1401d044e  mov     r9, [r13+10B0h]
0x1401d0455  lea     r8, WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids
0x1401d045c  mov     rcx, [rcx+18h]
0x1401d0460  mov     [rsp+0E0h+var_A8], r8
0x1401d0465  mov     r8b, dil
0x1401d0468  mov     [rsp+0E0h+var_B0], 0BCh
0x1401d046f  mov     dword ptr [rsp+0E0h+ResultLength], 2
0x1401d0477  mov     byte ptr [rsp+0E0h+Length], 2
0x1401d047c  call    WPP_RECORDER_AND_TRACE_SF_
0x1401d0481  mov     ebx, 0C000009Ah
0x1401d0486  jmp     loc_1401D07BC
0x1401d048b  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401d048f  lea     rax, [rbp+57h+var_90]
0x1401d0493  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1401d0498  mov     r9, r15; KeyInformation
0x1401d049b  xor     r8d, r8d; KeyInformationClass
0x1401d049e  mov     [rsp+0E0h+Length], ebx; Length
0x1401d04a2  mov     edx, r12d; Index
0x1401d04a5  call    cs:__imp_ZwEnumerateKey
0x1401d04ac  nop     dword ptr [rax+rax+00h]
0x1401d04b1  mov     ebx, eax
0x1401d04b3  cmp     eax, 80000005h
0x1401d04b8  jz      short loc_1401D04C1
0x1401d04ba  cmp     eax, 0C0000023h
0x1401d04bf  jnz     short loc_1401D0527
0x1401d04c1  xor     edx, edx; Tag
0x1401d04c3  mov     rcx, r15; P
0x1401d04c6  call    cs:__imp_ExFreePoolWithTag
0x1401d04cd  nop     dword ptr [rax+rax+00h]
0x1401d04d2  mov     edx, [rbp+57h+var_90]
0x1401d04d5  mov     ecx, 100h
0x1401d04da  mov     r8d, 50485442h
0x1401d04e0  call    cs:__imp_ExAllocatePool2
0x1401d04e7  nop     dword ptr [rax+rax+00h]
0x1401d04ec  mov     r15, rax
0x1401d04ef  test    rax, rax
0x1401d04f2  jz      loc_1401D074A
0x1401d04f8  mov     eax, [rbp+57h+var_90]
0x1401d04fb  lea     rcx, [rbp+57h+var_90]
0x1401d04ff  mov     [rsp+0E0h+ResultLength], rcx; ResultLength
0x1401d0504  mov     r9, r15; KeyInformation
0x1401d0507  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1401d050b  xor     r8d, r8d; KeyInformationClass
0x1401d050e  mov     edx, r12d; Index
0x1401d0511  mov     [rbp+57h+var_68], rax
0x1401d0515  mov     [rsp+0E0h+Length], eax; Length
0x1401d0519  call    cs:__imp_ZwEnumerateKey
0x1401d0520  nop     dword ptr [rax+rax+00h]
0x1401d0525  mov     ebx, eax
0x1401d0527  cmp     ebx, 8000001Ah
0x1401d052d  jz      loc_1401D0746
0x1401d0533  test    ebx, ebx
0x1401d0535  js      loc_1401D0706
0x1401d053b  mov     rsi, [rbp+57h+P]
0x1401d053f  lea     rdx, [r15+10h]; Src
0x1401d0543  mov     r8d, [r15+0Ch]; Size
0x1401d0547  mov     rcx, rsi; void *
0x1401d054a  call    memmove
0x1401d054f  mov     rcx, [rbp+57h+KeyHandle]
0x1401d0553  lea     r8, [rbp+57h+Handle]
0x1401d0557  mov     rdx, rsi
0x1401d055a  call    BthOpenKey
0x1401d055f  mov     ebx, eax
0x1401d0561  test    eax, eax
0x1401d0563  js      loc_1401D06AB
0x1401d0569  mov     edx, 18h
0x1401d056e  mov     ecx, 100h
0x1401d0573  mov     r8d, 50485442h
0x1401d0579  call    cs:__imp_ExAllocatePool2
0x1401d0580  nop     dword ptr [rax+rax+00h]
0x1401d0585  mov     rsi, rax
0x1401d0588  test    rax, rax
0x1401d058b  jz      loc_1401D0658
0x1401d0591  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1401d0595  lea     r9, [rbp+57h+var_70]
0x1401d0599  lea     r8, [rbp+57h+var_60]
0x1401d059d  lea     rdx, aManufacturerid_0; "ManufacturerID"
0x1401d05a4  call    BthQueryKeyValueUlong
0x1401d05a9  mov     ebx, eax
0x1401d05ab  test    eax, eax
0x1401d05ad  js      short loc_1401D05FB
0x1401d05af  movzx   eax, word ptr [rbp+57h+var_70]
0x1401d05b3  mov     [rsi+10h], ax
0x1401d05b7  mov     rcx, [rbp+57h+Handle]; Handle
0x1401d05bb  test    rcx, rcx
0x1401d05be  jz      short loc_1401D05D4
0x1401d05c0  call    cs:__imp_ZwClose
0x1401d05c7  nop     dword ptr [rax+rax+00h]
0x1401d05cc  mov     [rbp+57h+Handle], 0
0x1401d05d4  mov     rax, [r14+8]
0x1401d05d8  cmp     [rax], r14
0x1401d05db  jnz     loc_1401D0855
0x1401d05e1  mov     rbx, [rbp+57h+var_68]
0x1401d05e5  add     r12d, edi
0x1401d05e8  mov     [rsi], r14
0x1401d05eb  mov     [rsi+8], rax
0x1401d05ef  mov     [rax], rsi
0x1401d05f2  mov     [r14+8], rsi
0x1401d05f6  jmp     loc_1401D048B
0x1401d05fb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d0602  mov     eax, [rcx+2Ch]
0x1401d0605  test    al, 2
0x1401d0607  jz      short loc_1401D0614
0x1401d0609  cmp     byte ptr [rcx+29h], 2
0x1401d060d  jb      short loc_1401D0614
0x1401d060f  mov     dl, dil
0x1401d0612  jmp     short loc_1401D0616
0x1401d0614  xor     dl, dl
0x1401d0616  mov     r12, [rbp+57h+P]
0x1401d061a  lea     r8, WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids
0x1401d0621  mov     r9, [r13+10B0h]
0x1401d0628  mov     rcx, [rcx+18h]
0x1401d062c  mov     [rsp+0E0h+var_98], ebx
0x1401d0630  mov     [rsp+0E0h+var_A0], r12
0x1401d0635  mov     [rsp+0E0h+var_A8], r8
0x1401d063a  mov     [rsp+0E0h+var_B0], 0C1h
0x1401d0641  mov     dword ptr [rsp+0E0h+ResultLength], 2
0x1401d0649  mov     byte ptr [rsp+0E0h+Length], 2
0x1401d064e  call    WPP_RECORDER_AND_TRACE_SF_Sd
0x1401d0653  jmp     loc_1401D07A3
0x1401d0658  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d065f  mov     eax, [rcx+2Ch]
0x1401d0662  test    al, 2
0x1401d0664  jz      short loc_1401D0671
0x1401d0666  cmp     byte ptr [rcx+29h], 2
0x1401d066a  jb      short loc_1401D0671
0x1401d066c  mov     dl, dil
0x1401d066f  jmp     short loc_1401D0673
0x1401d0671  xor     dl, dl
0x1401d0673  mov     r9, [r13+10B0h]
0x1401d067a  lea     r8, WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids
0x1401d0681  mov     rcx, [rcx+18h]
0x1401d0685  mov     [rsp+0E0h+var_A8], r8
0x1401d068a  mov     r8b, dil
0x1401d068d  mov     [rsp+0E0h+var_B0], 0C0h
0x1401d0694  mov     dword ptr [rsp+0E0h+ResultLength], 2
0x1401d069c  mov     byte ptr [rsp+0E0h+Length], 2
0x1401d06a1  call    WPP_RECORDER_AND_TRACE_SF_
0x1401d06a6  jmp     loc_1401D079A
0x1401d06ab  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d06b2  mov     eax, [rcx+2Ch]
0x1401d06b5  test    al, 2
0x1401d06b7  jz      short loc_1401D06C4
0x1401d06b9  cmp     byte ptr [rcx+29h], 2
0x1401d06bd  jb      short loc_1401D06C4
0x1401d06bf  mov     dl, dil
0x1401d06c2  jmp     short loc_1401D06C6
0x1401d06c4  xor     dl, dl
0x1401d06c6  mov     [rsp+0E0h+var_98], ebx
0x1401d06ca  lea     r8, WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids
0x1401d06d1  mov     [rsp+0E0h+var_A0], rsi
0x1401d06d6  mov     [rsp+0E0h+var_A8], r8
0x1401d06db  mov     [rsp+0E0h+var_B0], 0BFh
0x1401d06e2  mov     r9, [r13+10B0h]
0x1401d06e9  mov     rcx, [rcx+18h]
0x1401d06ed  mov     dword ptr [rsp+0E0h+ResultLength], 2
0x1401d06f5  mov     byte ptr [rsp+0E0h+Length], 2
0x1401d06fa  call    WPP_RECORDER_AND_TRACE_SF_Sd
  ... truncated ...
```
