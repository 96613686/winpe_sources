# HCI_InitDefaultLocalRadioName(HCI_INTERFACE *)

- ea: `0x140074960`
- end: `0x140074dbf`
- name: `?HCI_InitDefaultLocalRadioName@@YAXPEAUHCI_INTERFACE@@@Z`
- size: `1119`
- prototype: `void __fastcall(struct HCI_INTERFACE *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140029448`
- `0x1400719d4`
- `0x140077144`

## callees

- `0x140005608`
- `0x140005690`
- `0x140029568`
- `0x140068098`
- `0x140074960`
- `0x1400796b8`
- `0x140079f5c`
- `0x140163464`
- `0x14016423c`
- `0x14016506c`
- `0x140165640`
- `0x140165940`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140074d4a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140074d4a`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140074b1d`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140074b1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140074d34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140074d34`

## pseudocode

```c
void __fastcall HCI_InitDefaultLocalRadioName(struct HCI_INTERFACE *a1)
{
  char v2; // bl
  char v3; // dl
  __int16 DeviceType; // ax
  __int64 v5; // rcx
  int PolicyString; // esi
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  int v10; // edx
  int v11; // r8d
  unsigned int v12; // r14d
  __int64 v13; // rdx
  __int64 v14; // rcx
  int RegistryValues; // eax
  size_t *v16; // r8
  void *v17; // rsi
  int v18; // eax
  int v19; // edx
  int v20; // r8d
  unsigned int v21; // r14d
  __int64 *v22; // r8
  int v23; // edx
  int v24; // r8d
  __int16 v25; // ax
  int cchToCopy; // [rsp+20h] [rbp-A9h]
  size_t cchToCopya; // [rsp+20h] [rbp-A9h]
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-79h] BYREF
  void *Src[2]; // [rsp+60h] [rbp-69h] BYREF
  _QWORD v30[22]; // [rsp+70h] [rbp-59h] BYREF

  *(_OWORD *)Src = 0;
  UnicodeString = 0;
  v2 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v3 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v3 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v3 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      DeviceType != 0,
      a1->IfrLog,
      5,
      2,
      185,
      (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids);
  memset(a1->defLocalName, 0, sizeof(a1->defLocalName));
  PolicyString = BthGetPolicyString(v5, &UnicodeString);
  if ( PolicyString < 0 )
  {
    Feature_58647029__private_ReportDeviceUsage();
    v12 = 0;
    while ( PolicyString < 0 )
    {
      memset(v30, 0, 0x70u);
      LODWORD(v30[1]) = 292;
      LODWORD(v30[4]) = 16777217;
      v13 = qword_140170950[3 * v12 + 1];
      v14 = LODWORD(qword_140170950[3 * v12]);
      v30[2] = qword_140170950[3 * v12 + 2];
      v30[3] = &UnicodeString;
      RegistryValues = RtlQueryRegistryValuesEx(v14, v13, v30, 0, 0);
      ++v12;
      PolicyString = RegistryValues;
      if ( v12 >= 2 )
      {
        if ( RegistryValues >= 0 )
          break;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v10) = 0;
        LOBYTE(v11) = 1;
        WPP_RECORDER_AND_TRACE_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          v10,
          v11,
          a1->IfrLog,
          2,
          2,
          189,
          (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids,
          RegistryValues);
        v17 = Src[1];
        UnicodeString.Buffer = 0;
        goto LABEL_41;
      }
    }
  }
  else
  {
    v7 = BthReportPolicyLocalDeviceName(&UnicodeString);
    if ( v7 < 0 )
    {
      if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu)
        || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      {
        LOBYTE(v8) = 0;
      }
      LOBYTE(v9) = 1;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v8,
        v9,
        a1->IfrLog,
        3,
        12,
        186,
        (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids,
        v7);
    }
    if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu)
      || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    {
      LOBYTE(v8) = 0;
    }
    WPP_RECORDER_AND_TRACE_SF_S(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      v9,
      a1->IfrLog,
      cchToCopy,
      12,
      187,
      (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids,
      (__int64)UnicodeString.Buffer);
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    LOBYTE(v10) = 0;
  WPP_RECORDER_AND_TRACE_SF_S(
    WPP_GLOBAL_Control->AttachedDevice,
    v10,
    v11,
    a1->IfrLog,
    cchToCopy,
    2,
    190,
    (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids,
    (__int64)UnicodeString.Buffer);
  v18 = EUnicodeStringToUtf8String(Src, &UnicodeString);
  if ( v18 >= 0 )
  {
    v21 = LOWORD(Src[0]) + 1;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v19) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
      LOBYTE(v19) = 0;
    v22 = WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids;
    LOBYTE(v22) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v19,
      (_DWORD)v22,
      a1->IfrLog,
      4,
      2,
      192,
      (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids,
      LOBYTE(Src[0]) + 1);
    v17 = Src[1];
    if ( v21 <= 0xF8 )
    {
      memmove(a1->defLocalName, Src[1], v21);
      a1->defLocalName[247] = 0;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v23) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
        LOBYTE(v23) = 0;
      LOBYTE(v24) = 1;
      WPP_RECORDER_AND_TRACE_SF_s(
        WPP_GLOBAL_Control->AttachedDevice,
        v23,
        v24,
        a1->IfrLog,
        4,
        2,
        193,
        (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids,
        (__int64)a1->defLocalName);
    }
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v19) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v19) = 0;
    LOBYTE(v20) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v19,
      v20,
      a1->IfrLog,
      2,
      2,
      191,
      (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids,
      v18);
    v17 = 0;
  }
LABEL_41:
  if ( !a1->defLocalName[0] )
    RtlStringCopyWorkerA(a1->defLocalName, 0xF8u, v16, "Windows Device", cchToCopya);
  if ( v17 )
    ExFreePoolWithTag(v17, 0);
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v2 = 0;
  v25 = WPP_GLOBAL_Control->DeviceType;
  if ( v2 || v25 )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      v25 != 0,
      a1->IfrLog,
      5,
      2,
      194,
      (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids);
}

```

## disassembly

```asm
0x140074960  push    rbp
0x140074962  push    rbx
0x140074963  push    rsi
0x140074964  push    rdi
0x140074965  push    r12
0x140074967  push    r13
0x140074969  push    r14
0x14007496b  push    r15
0x14007496d  lea     rbp, [rsp-1Fh]
0x140074972  sub     rsp, 0E8h
0x140074979  xorps   xmm0, xmm0
0x14007497c  xorps   xmm1, xmm1
0x14007497f  movups  xmmword ptr [rbp+57h+Src], xmm0
0x140074983  mov     rdi, rcx
0x140074986  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm1
0x14007498a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140074991  xor     r12d, r12d
0x140074994  mov     eax, [rcx+2Ch]
0x140074997  lea     r13d, [r12+2]
0x14007499c  lea     ebx, [r12+1]
0x1400749a1  test    r13b, al
0x1400749a4  jz      short loc_1400749AE
0x1400749a6  cmp     byte ptr [rcx+29h], 5
0x1400749aa  mov     dl, bl
0x1400749ac  jnb     short loc_1400749B1
0x1400749ae  mov     dl, r12b
0x1400749b1  movzx   eax, word ptr [rcx+48h]
0x1400749b5  lea     r14, WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids
0x1400749bc  test    ax, ax
0x1400749bf  setnz   r8b
0x1400749c3  test    dl, dl
0x1400749c5  jnz     short loc_1400749CC
0x1400749c7  test    ax, ax
0x1400749ca  jz      short loc_1400749F2
0x1400749cc  mov     r9, [rdi+10B0h]
0x1400749d3  mov     rcx, [rcx+18h]
0x1400749d7  mov     [rsp+120h+var_E8], r14
0x1400749dc  mov     [rsp+120h+var_F0], 0B9h
0x1400749e3  mov     [rsp+120h+var_F8], r13d
0x1400749e8  mov     byte ptr [rsp+120h+cchToCopy], 5
0x1400749ed  call    WPP_RECORDER_AND_TRACE_SF_
0x1400749f2  lea     r15, [rdi+24h]
0x1400749f6  xor     edx, edx; Val
0x1400749f8  mov     rcx, r15; void *
0x1400749fb  mov     r8d, 0F8h; Size
0x140074a01  call    memset
0x140074a06  lea     rdx, [rbp+57h+UnicodeString]
0x140074a0a  call    BthGetPolicyString
0x140074a0f  mov     esi, eax
0x140074a11  test    eax, eax
0x140074a13  js      loc_140074ABC
0x140074a19  lea     rcx, [rbp+57h+UnicodeString]
0x140074a1d  call    BthReportPolicyLocalDeviceName
0x140074a22  test    eax, eax
0x140074a24  jns     short loc_140074A71
0x140074a26  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140074a2d  bt      dword ptr [r10+2Ch], 0Bh
0x140074a33  jnb     short loc_140074A3E
0x140074a35  cmp     byte ptr [r10+29h], 3
0x140074a3a  mov     dl, bl
0x140074a3c  jnb     short loc_140074A41
0x140074a3e  mov     dl, r12b
0x140074a41  mov     r9, [rdi+10B0h]
0x140074a48  mov     r8b, bl
0x140074a4b  mov     rcx, [r10+18h]
0x140074a4f  mov     dword ptr [rsp+120h+var_E0], eax
0x140074a53  mov     [rsp+120h+var_E8], r14
0x140074a58  mov     [rsp+120h+var_F0], 0BAh
0x140074a5f  mov     [rsp+120h+var_F8], 0Ch
0x140074a67  mov     byte ptr [rsp+120h+cchToCopy], 3
0x140074a6c  call    WPP_RECORDER_AND_TRACE_SF_d
0x140074a71  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140074a78  bt      dword ptr [rcx+2Ch], 0Bh
0x140074a7d  jnb     short loc_140074A87
0x140074a7f  cmp     byte ptr [rcx+29h], 4
0x140074a83  mov     dl, bl
0x140074a85  jnb     short loc_140074A8A
0x140074a87  mov     dl, r12b
0x140074a8a  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x140074a8e  mov     r9, [rdi+10B0h]
0x140074a95  mov     rcx, [rcx+18h]
0x140074a99  mov     [rsp+120h+var_E0], rax
0x140074a9e  mov     [rsp+120h+var_E8], r14
0x140074aa3  mov     [rsp+120h+var_F0], 0BBh
0x140074aaa  mov     [rsp+120h+var_F8], 0Ch
0x140074ab2  call    WPP_RECORDER_AND_TRACE_SF_S
0x140074ab7  jmp     loc_140074B99
0x140074abc  call    Feature_58647029__private_ReportDeviceUsage
0x140074ac1  mov     r14d, r12d
0x140074ac4  test    esi, esi
0x140074ac6  jns     loc_140074B92
0x140074acc  xor     edx, edx; Val
0x140074ace  lea     rcx, [rbp+57h+var_B0]; void *
0x140074ad2  lea     r8d, [rdx+70h]; Size
0x140074ad6  call    memset
0x140074adb  lea     r10, qword_140170950
0x140074ae2  mov     eax, r14d
0x140074ae5  xor     r9d, r9d
0x140074ae8  mov     [rbp+57h+var_A8], 124h
0x140074aef  lea     r8, [rbp+57h+var_B0]
0x140074af3  mov     [rbp+57h+var_90], 1000001h
0x140074afa  mov     [rsp+120h+cchToCopy], r12
0x140074aff  lea     rcx, [rax+rax*2]
0x140074b03  mov     rax, [r10+rcx*8+10h]
0x140074b08  mov     rdx, [r10+rcx*8+8]
0x140074b0d  mov     ecx, [r10+rcx*8]
0x140074b11  mov     [rbp+57h+var_A0], rax
0x140074b15  lea     rax, [rbp+57h+UnicodeString]
0x140074b19  mov     [rbp+57h+var_98], rax
0x140074b1d  call    cs:__imp_RtlQueryRegistryValuesEx
0x140074b24  nop     dword ptr [rax+rax+00h]
0x140074b29  add     r14d, ebx
0x140074b2c  mov     esi, eax
0x140074b2e  cmp     r14d, r13d
0x140074b31  jb      short loc_140074AC4
0x140074b33  test    eax, eax
0x140074b35  jns     short loc_140074B92
0x140074b37  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140074b3e  mov     eax, [rcx+2Ch]
0x140074b41  test    r13b, al
0x140074b44  jz      short loc_140074B4E
0x140074b46  mov     dl, bl
0x140074b48  cmp     [rcx+29h], r13b
0x140074b4c  jnb     short loc_140074B51
0x140074b4e  mov     dl, r12b
0x140074b51  mov     r9, [rdi+10B0h]
0x140074b58  lea     r14, WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids
0x140074b5f  mov     rcx, [rcx+18h]
0x140074b63  mov     r8b, bl
0x140074b66  mov     dword ptr [rsp+120h+var_E0], esi
0x140074b6a  mov     [rsp+120h+var_E8], r14
0x140074b6f  mov     [rsp+120h+var_F0], 0BDh
0x140074b76  mov     [rsp+120h+var_F8], r13d
0x140074b7b  mov     byte ptr [rsp+120h+cchToCopy], r13b
0x140074b80  call    WPP_RECORDER_AND_TRACE_SF_d
0x140074b85  mov     rsi, [rbp+57h+Src+8]
0x140074b89  mov     [rbp+57h+UnicodeString.Buffer], r12
0x140074b8d  jmp     loc_140074D0F
0x140074b92  lea     r14, WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids
0x140074b99  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140074ba0  mov     eax, [rcx+2Ch]
0x140074ba3  test    r13b, al
0x140074ba6  jz      short loc_140074BB0
0x140074ba8  cmp     byte ptr [rcx+29h], 4
0x140074bac  mov     dl, bl
0x140074bae  jnb     short loc_140074BB3
0x140074bb0  mov     dl, r12b
0x140074bb3  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x140074bb7  mov     r9, [rdi+10B0h]
0x140074bbe  mov     rcx, [rcx+18h]
0x140074bc2  mov     [rsp+120h+var_E0], rax
0x140074bc7  mov     [rsp+120h+var_E8], r14
0x140074bcc  mov     [rsp+120h+var_F0], 0BEh
0x140074bd3  mov     [rsp+120h+var_F8], r13d
0x140074bd8  call    WPP_RECORDER_AND_TRACE_SF_S
0x140074bdd  lea     rdx, [rbp+57h+UnicodeString]
0x140074be1  lea     rcx, [rbp+57h+Src]
0x140074be5  call    EUnicodeStringToUtf8String
0x140074bea  test    eax, eax
0x140074bec  jns     short loc_140074C3E
0x140074bee  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140074bf5  mov     ecx, [r10+2Ch]
0x140074bf9  test    r13b, cl
0x140074bfc  jz      short loc_140074C06
0x140074bfe  mov     dl, bl
0x140074c00  cmp     [r10+29h], r13b
0x140074c04  jnb     short loc_140074C09
0x140074c06  mov     dl, r12b
0x140074c09  mov     r9, [rdi+10B0h]
0x140074c10  mov     r8b, bl
0x140074c13  mov     rcx, [r10+18h]
0x140074c17  mov     dword ptr [rsp+120h+var_E0], eax
0x140074c1b  mov     [rsp+120h+var_E8], r14
0x140074c20  mov     [rsp+120h+var_F0], 0BFh
0x140074c27  mov     [rsp+120h+var_F8], r13d
0x140074c2c  mov     byte ptr [rsp+120h+cchToCopy], r13b
0x140074c31  call    WPP_RECORDER_AND_TRACE_SF_d
0x140074c36  mov     rsi, r12
0x140074c39  jmp     loc_140074D0F
0x140074c3e  movzx   r14d, word ptr [rbp+57h+Src]
0x140074c43  inc     r14d
0x140074c46  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140074c4d  mov     eax, [rcx+2Ch]
0x140074c50  test    r13b, al
0x140074c53  jz      short loc_140074C5D
0x140074c55  cmp     byte ptr [rcx+29h], 4
0x140074c59  mov     dl, bl
0x140074c5b  jnb     short loc_140074C60
0x140074c5d  mov     dl, r12b
0x140074c60  mov     r9, [rdi+10B0h]
0x140074c67  lea     r8, WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids
0x140074c6e  mov     rcx, [rcx+18h]
0x140074c72  mov     dword ptr [rsp+120h+var_E0], r14d
0x140074c77  mov     [rsp+120h+var_E8], r8
0x140074c7c  mov     r8b, bl
0x140074c7f  mov     [rsp+120h+var_F0], 0C0h
0x140074c86  mov     [rsp+120h+var_F8], r13d
0x140074c8b  mov     byte ptr [rsp+120h+cchToCopy], 4; cchToCopy
0x140074c90  call    WPP_RECORDER_AND_TRACE_SF_d
0x140074c95  mov     rsi, [rbp+57h+Src+8]
0x140074c99  cmp     r14d, 0F8h
0x140074ca0  ja      short loc_140074D08
0x140074ca2  mov     r8d, r14d; Size
0x140074ca5  mov     rdx, rsi; Src
0x140074ca8  mov     rcx, r15; void *
0x140074cab  call    memmove
0x140074cb0  mov     [rdi+11Bh], r12b
0x140074cb7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140074cbe  mov     eax, [rcx+2Ch]
0x140074cc1  test    r13b, al
0x140074cc4  jz      short loc_140074CCE
0x140074cc6  cmp     byte ptr [rcx+29h], 4
0x140074cca  mov     dl, bl
0x140074ccc  jnb     short loc_140074CD1
0x140074cce  mov     dl, r12b
0x140074cd1  mov     r9, [rdi+10B0h]
0x140074cd8  lea     r14, WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids
0x140074cdf  mov     rcx, [rcx+18h]
0x140074ce3  mov     r8b, bl
0x140074ce6  mov     [rsp+120h+var_E0], r15
0x140074ceb  mov     [rsp+120h+var_E8], r14
0x140074cf0  mov     [rsp+120h+var_F0], 0C1h
0x140074cf7  mov     [rsp+120h+var_F8], r13d
0x140074cfc  mov     byte ptr [rsp+120h+cchToCopy], 4
0x140074d01  call    WPP_RECORDER_AND_TRACE_SF_s
0x140074d06  jmp     short loc_140074D0F
0x140074d08  lea     r14, WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids
0x140074d0f  cmp     [rdi+24h], r12b
0x140074d13  jnz     short loc_140074D2A
0x140074d15  lea     rcx, [rdi+24h]; pszDest
0x140074d19  mov     edx, 0F8h; cchDest
0x140074d1e  lea     r9, pszSrc; "Windows Device"
0x140074d25  call    RtlStringCopyWorkerA
0x140074d2a  test    rsi, rsi
0x140074d2d  jz      short loc_140074D40
0x140074d2f  xor     edx, edx; Tag
0x140074d31  mov     rcx, rsi; P
0x140074d34  call    cs:__imp_ExFreePoolWithTag
0x140074d3b  nop     dword ptr [rax+rax+00h]
0x140074d40  cmp     [rbp+57h+UnicodeString.Buffer], r12
0x140074d44  jz      short loc_140074D56
0x140074d46  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x140074d4a  call    cs:__imp_RtlFreeUnicodeString
0x140074d51  nop     dword ptr [rax+rax+00h]
0x140074d56  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140074d5d  mov     eax, [rcx+2Ch]
0x140074d60  test    r13b, al
0x140074d63  jz      short loc_140074D6B
0x140074d65  cmp     byte ptr [rcx+29h], 5
0x140074d69  jnb     short loc_140074D6E
0x140074d6b  mov     bl, r12b
0x140074d6e  movzx   eax, word ptr [rcx+48h]
0x140074d72  test    ax, ax
0x140074d75  setnz   r8b
0x140074d79  test    bl, bl
0x140074d7b  jnz     short loc_140074D82
0x140074d7d  test    ax, ax
0x140074d80  jz      short loc_140074DAA
0x140074d82  mov     r9, [rdi+10B0h]
0x140074d89  mov     dl, bl
0x140074d8b  mov     rcx, [rcx+18h]
0x140074d8f  mov     [rsp+120h+var_E8], r14
0x140074d94  mov     [rsp+120h+var_F0], 0C2h
0x140074d9b  mov     [rsp+120h+var_F8], r13d
0x140074da0  mov     byte ptr [rsp+120h+cchToCopy], 5
0x140074da5  call    WPP_RECORDER_AND_TRACE_SF_
0x140074daa  add     rsp, 0E8h
0x140074db1  pop     r15
0x140074db3  pop     r14
0x140074db5  pop     r13
0x140074db7  pop     r12
0x140074db9  pop     rdi
0x140074dba  pop     rsi
0x140074dbb  pop     rbx
0x140074dbc  pop     rbp
0x140074dbd  retn
```
