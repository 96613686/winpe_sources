# ReadSwitchState

- ea: `0x180024b00`
- end: `0x180024fd4`
- name: `ReadSwitchState`
- size: `1236`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180009500`

## callees

- `0x180002ec0`
- `0x180003c70`
- `0x180003d50`
- `0x1800070b8`
- `0x180007c48`
- `0x1800090bc`
- `0x18000d2a0`
- `0x18000df4c`
- `0x180024a48`
- `0x180024b00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024f9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024fa4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024f9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024fa4`
- `HID!HidD_GetInputReport` at `0x180024cb4`
- `HID!HidD_GetInputReport` at `0x180024cb4`
- `HID!HidP_GetUsages` at `0x180024d7f`
- `HID!HidP_GetUsages` at `0x180024d7f`
- `HID!HidP_GetSpecificButtonCaps` at `0x180024c2c`
- `HID!HidP_GetSpecificButtonCaps` at `0x180024c2c`
- `HID!HidP_MaxUsageListLength` at `0x180024cf6`
- `HID!HidP_MaxUsageListLength` at `0x180024cf6`

## pseudocode

```c
__int64 __fastcall ReadSwitchState(__int64 a1, int a2, unsigned __int8 *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rdx
  USHORT *v9; // rbx
  _BYTE *v10; // rdi
  USAGE v11; // cx
  unsigned int SpecificButtonCaps; // r15d
  size_t ReportLength; // r15
  ULONG v14; // eax
  unsigned int Usages; // eax
  unsigned __int8 *v16; // rax
  __int64 v17; // r13
  ULONG v18; // edx
  __int64 v19; // rcx
  USAGE v20; // r8
  __int64 v21; // rdx
  USAGE v23; // [rsp+48h] [rbp-61h]
  PUSAGE UsageList; // [rsp+50h] [rbp-59h] BYREF
  PVOID ReportBuffer; // [rsp+58h] [rbp-51h] BYREF
  ULONG UsageLength; // [rsp+60h] [rbp-49h] BYREF
  USHORT ButtonCapsLength[6]; // [rsp+64h] [rbp-45h] BYREF
  struct _HIDP_BUTTON_CAPS ButtonCaps; // [rsp+70h] [rbp-39h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation>::GetImpl'::`2'::impl) )
  {
    if ( !a1 || !*(_QWORD *)(a1 + 528) )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0
        || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      {
        return 3221225473LL;
      }
      v7 = 96;
      goto LABEL_13;
    }
    if ( !a3 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0
        || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      {
        return 3221225473LL;
      }
      v7 = 97;
LABEL_13:
      WPP_SF_(*(_QWORD *)(v6 + 16), v7, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
      return 3221225473LL;
    }
  }
  v9 = 0;
  UsageLength = 0;
  v10 = 0;
  UsageList = 0;
  ReportBuffer = 0;
  ButtonCapsLength[0] = 1;
  memset_0(&ButtonCaps, 0, sizeof(ButtonCaps));
  v11 = 200;
  *a3 = 1;
  if ( a2 != 4 )
    v11 = 198;
  v23 = v11;
  SpecificButtonCaps = HidP_GetSpecificButtonCaps(
                         HidP_Input,
                         1u,
                         0,
                         v11,
                         &ButtonCaps,
                         ButtonCapsLength,
                         *(PHIDP_PREPARSED_DATA *)(a1 + 528));
  if ( SpecificButtonCaps != 1114112 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_79;
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_74;
    v21 = 108;
LABEL_72:
    WPP_SF_(*(_QWORD *)(v19 + 16), v21, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
    goto LABEL_73;
  }
  ReportLength = *(unsigned __int16 *)(a1 + 540);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      98,
      &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids,
      *(unsigned __int16 *)(a1 + 540));
  }
  if ( !(unsigned __int8)ATL::CHeapPtr<char,ATL::CComAllocator>::Allocate(&ReportBuffer, ReportLength) )
  {
    SpecificButtonCaps = -1073741823;
    v19 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    {
      v10 = ReportBuffer;
      goto LABEL_79;
    }
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 107, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
      v10 = ReportBuffer;
      goto LABEL_73;
    }
    v10 = ReportBuffer;
LABEL_74:
    v16 = a3;
LABEL_75:
    if ( (_UNKNOWN *)v19 != &WPP_GLOBAL_Control && (*(_BYTE *)(v19 + 28) & 1) != 0 && *(_BYTE *)(v19 + 25) >= 4u )
      WPP_SF_Dd(*(_QWORD *)(v19 + 16), 109, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids, SpecificButtonCaps, *v16);
    goto LABEL_79;
  }
  v10 = ReportBuffer;
  memset_0(ReportBuffer, 0, ReportLength);
  *v10 = ButtonCaps.ReportID;
  if ( !HidD_GetInputReport(*(HANDLE *)a1, v10, ReportLength) )
  {
    SpecificButtonCaps = -1073741823;
    v19 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_79;
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_74;
    v21 = 106;
    goto LABEL_72;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 99, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
  }
  v14 = HidP_MaxUsageListLength(HidP_Input, 1u, *(PHIDP_PREPARSED_DATA *)(a1 + 528));
  UsageLength = v14;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 101, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids, v14);
    v14 = UsageLength;
  }
  if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CComAllocator>::Allocate(&UsageList, v14) )
  {
    SpecificButtonCaps = -1073741823;
    v19 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    {
      v9 = UsageList;
      goto LABEL_79;
    }
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 105, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
      v9 = UsageList;
LABEL_73:
      v19 = WPP_GLOBAL_Control;
      goto LABEL_74;
    }
    v9 = UsageList;
    goto LABEL_74;
  }
  v9 = UsageList;
  memset_0(UsageList, 0, 2LL * UsageLength);
  Usages = HidP_GetUsages(HidP_Input, 1u, 0, v9, &UsageLength, *(PHIDP_PREPARSED_DATA *)(a1 + 528), v10, ReportLength);
  SpecificButtonCaps = Usages;
  if ( Usages == 1114112 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        102,
        &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids,
        UsageLength);
    }
    v16 = a3;
    v17 = 0;
    v18 = UsageLength;
    *a3 = 0;
    v19 = WPP_GLOBAL_Control;
    if ( v18 )
    {
      v20 = v23;
      do
      {
        if ( (_UNKNOWN *)v19 != &WPP_GLOBAL_Control && (*(_BYTE *)(v19 + 28) & 1) != 0 && *(_BYTE *)(v19 + 25) >= 5u )
        {
          WPP_SF_dD(*(_QWORD *)(v19 + 16), 103, v9[v17], (unsigned int)v17, v9[v17]);
          v18 = UsageLength;
          v19 = WPP_GLOBAL_Control;
          v20 = v23;
        }
        v16 = a3;
        if ( v9[v17] == v20 )
        {
          *a3 = 1;
          v19 = WPP_GLOBAL_Control;
        }
        v17 = (unsigned int)(v17 + 1);
      }
      while ( (_DWORD)v17 != v18 );
    }
    goto LABEL_75;
  }
  v19 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_74;
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 104, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids, Usages);
    goto LABEL_73;
  }
LABEL_79:
  CoTaskMemFree(v10);
  CoTaskMemFree(v9);
  return SpecificButtonCaps;
}

```

## disassembly

```asm
0x180024b00  mov     [rsp-8+arg_8], rbx
0x180024b05  push    rbp
0x180024b06  push    rsi
0x180024b07  push    rdi
0x180024b08  push    r12
0x180024b0a  push    r13
0x180024b0c  push    r14
0x180024b0e  push    r15
0x180024b10  lea     rbp, [rsp-27h]
0x180024b15  sub     rsp, 0D0h
0x180024b1c  mov     rax, cs:__security_cookie
0x180024b23  xor     rax, rsp
0x180024b26  mov     [rbp+57h+var_40], rax
0x180024b2a  mov     r15, r8
0x180024b2d  mov     [rbp+57h+var_C0], r8
0x180024b31  mov     r14d, edx
0x180024b34  mov     r13, rcx
0x180024b37  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation> `wil::Feature<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation>::GetImpl(void)'::`2'::impl
0x180024b3e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation>::__private_IsEnabled(void)
0x180024b43  test    al, al
0x180024b45  jz      short loc_180024BC4
0x180024b47  test    r13, r13
0x180024b4a  jz      short loc_180024B83
0x180024b4c  cmp     qword ptr [r13+210h], 0
0x180024b54  jz      short loc_180024B83
0x180024b56  test    r15, r15
0x180024b59  jnz     short loc_180024BC4
0x180024b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b62  lea     r14, WPP_GLOBAL_Control
0x180024b69  cmp     rcx, r14
0x180024b6c  jz      short loc_180024BBA
0x180024b6e  lea     esi, [r15+1]
0x180024b72  test    [rcx+1Ch], sil
0x180024b76  jz      short loc_180024BBA
0x180024b78  cmp     byte ptr [rcx+19h], 2
0x180024b7c  jb      short loc_180024BBA
0x180024b7e  lea     edx, [rsi+60h]
0x180024b81  jmp     short loc_180024BAA
0x180024b83  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b8a  lea     r14, WPP_GLOBAL_Control
0x180024b91  cmp     rcx, r14
0x180024b94  jz      short loc_180024BBA
0x180024b96  mov     esi, 1
0x180024b9b  test    [rcx+1Ch], sil
0x180024b9f  jz      short loc_180024BBA
0x180024ba1  cmp     byte ptr [rcx+19h], 2
0x180024ba5  jb      short loc_180024BBA
0x180024ba7  lea     edx, [rsi+5Fh]
0x180024baa  mov     rcx, [rcx+10h]
0x180024bae  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180024bb5  call    WPP_SF_
0x180024bba  mov     eax, 0C0000001h
0x180024bbf  jmp     loc_180024FAD
0x180024bc4  xor     ebx, ebx
0x180024bc6  mov     [rbp+57h+UsageLength], 0
0x180024bcd  xor     edi, edi
0x180024bcf  mov     [rbp+57h+UsageList], rbx
0x180024bd3  xor     edx, edx; Val
0x180024bd5  mov     [rbp+57h+ReportBuffer], rdi
0x180024bd9  lea     rcx, [rbp+57h+var_90]; void *
0x180024bdd  lea     esi, [rbx+1]
0x180024be0  lea     r8d, [rbx+48h]; Size
0x180024be4  mov     [rbp+57h+var_9C], si
0x180024be8  call    memset_0
0x180024bed  mov     ecx, 0C8h
0x180024bf2  mov     [r15], sil
0x180024bf5  cmp     r14d, 4
0x180024bf9  mov     edx, esi; UsagePage
0x180024bfb  lea     eax, [rcx-2]
0x180024bfe  cmovnz  cx, ax
0x180024c02  mov     rax, [r13+210h]
0x180024c09  mov     [rsp+100h+PreparsedData], rax; PreparsedData
0x180024c0e  movzx   r9d, cx; Usage
0x180024c12  lea     rax, [rbp+57h+var_9C]
0x180024c16  mov     dword ptr [rbp+57h+var_B8], ecx
0x180024c19  mov     [rsp+100h+ButtonCapsLength], rax; ButtonCapsLength
0x180024c1e  xor     r8d, r8d; LinkCollection
0x180024c21  lea     rax, [rbp+57h+var_90]
0x180024c25  xor     ecx, ecx; ReportType
0x180024c27  mov     [rsp+100h+ButtonCaps], rax; ButtonCaps
0x180024c2c  call    cs:__imp_HidP_GetSpecificButtonCaps
0x180024c32  lea     r12, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180024c39  mov     r15d, eax
0x180024c3c  cmp     eax, 110000h
0x180024c41  jnz     loc_180024F31
0x180024c47  movzx   r15d, word ptr [r13+21Ch]
0x180024c4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c56  lea     r14, WPP_GLOBAL_Control
0x180024c5d  cmp     rcx, r14
0x180024c60  jz      short loc_180024C80
0x180024c62  test    [rcx+1Ch], sil
0x180024c66  jz      short loc_180024C80
0x180024c68  cmp     byte ptr [rcx+19h], 5
0x180024c6c  jb      short loc_180024C80
0x180024c6e  mov     rcx, [rcx+10h]
0x180024c72  lea     edx, [rbx+62h]
0x180024c75  mov     r9d, r15d
0x180024c78  mov     r8, r12
0x180024c7b  call    WPP_SF_d
0x180024c80  mov     rdx, r15
0x180024c83  lea     rcx, [rbp+57h+ReportBuffer]
0x180024c87  call    ?Allocate@?$CHeapPtr@DVCComAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<char,ATL::CComAllocator>::Allocate(unsigned __int64)
0x180024c8c  test    al, al
0x180024c8e  jz      loc_180024EF0
0x180024c94  mov     rdi, [rbp+57h+ReportBuffer]
0x180024c98  mov     r8, r15; Size
0x180024c9b  mov     rcx, rdi; void *
0x180024c9e  xor     edx, edx; Val
0x180024ca0  call    memset_0
0x180024ca5  mov     al, [rbp+57h+var_90.ReportID]
0x180024ca8  mov     r8d, r15d; ReportBufferLength
0x180024cab  mov     [rdi], al
0x180024cad  mov     rdx, rdi; ReportBuffer
0x180024cb0  mov     rcx, [r13+0]; HidDeviceObject
0x180024cb4  call    cs:__imp_HidD_GetInputReport
0x180024cba  test    al, al
0x180024cbc  jz      loc_180024EC3
0x180024cc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180024cc9  cmp     rcx, r14
0x180024ccc  jz      short loc_180024CEB
0x180024cce  test    [rcx+1Ch], sil
0x180024cd2  jz      short loc_180024CEB
0x180024cd4  cmp     byte ptr [rcx+19h], 4
0x180024cd8  jb      short loc_180024CEB
0x180024cda  mov     rcx, [rcx+10h]
0x180024cde  mov     edx, 63h ; 'c'
0x180024ce3  mov     r8, r12
0x180024ce6  call    WPP_SF_
0x180024ceb  mov     r8, [r13+210h]; PreparsedData
0x180024cf2  mov     edx, esi; UsagePage
0x180024cf4  xor     ecx, ecx; ReportType
0x180024cf6  call    cs:__imp_HidP_MaxUsageListLength
0x180024cfc  mov     [rbp+57h+UsageLength], eax
0x180024cff  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d06  cmp     rcx, r14
0x180024d09  jz      short loc_180024D2E
0x180024d0b  test    [rcx+1Ch], sil
0x180024d0f  jz      short loc_180024D2E
0x180024d11  cmp     byte ptr [rcx+19h], 4
0x180024d15  jb      short loc_180024D2E
0x180024d17  mov     rcx, [rcx+10h]
0x180024d1b  mov     edx, 65h ; 'e'
0x180024d20  mov     r9d, eax
0x180024d23  mov     r8, r12
0x180024d26  call    WPP_SF_d
0x180024d2b  mov     eax, [rbp+57h+UsageLength]
0x180024d2e  mov     edx, eax
0x180024d30  lea     rcx, [rbp+57h+UsageList]
0x180024d34  call    ?Allocate@?$CHeapPtr@GVCComAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CComAllocator>::Allocate(unsigned __int64)
0x180024d39  test    al, al
0x180024d3b  jz      loc_180024E79
0x180024d41  mov     r8d, [rbp+57h+UsageLength]
0x180024d45  xor     edx, edx; Val
0x180024d47  mov     rbx, [rbp+57h+UsageList]
0x180024d4b  add     r8, r8; Size
0x180024d4e  mov     rcx, rbx; void *
0x180024d51  call    memset_0
0x180024d56  mov     rax, [r13+210h]
0x180024d5d  xor     r8d, r8d; LinkCollection
0x180024d60  mov     [rsp+100h+ReportLength], r15d; ReportLength
0x180024d65  mov     edx, esi; UsagePage
0x180024d67  mov     [rsp+100h+PreparsedData], rdi; Report
0x180024d6c  mov     r9, rbx; UsageList
0x180024d6f  mov     [rsp+100h+ButtonCapsLength], rax; PreparsedData
0x180024d74  xor     ecx, ecx; ReportType
0x180024d76  lea     rax, [rbp+57h+UsageLength]
0x180024d7a  mov     [rsp+100h+ButtonCaps], rax; UsageLength
0x180024d7f  call    cs:__imp_HidP_GetUsages
0x180024d85  mov     r15d, eax
0x180024d88  cmp     eax, 110000h
0x180024d8d  jnz     loc_180024E3C
0x180024d93  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d9a  cmp     rcx, r14
0x180024d9d  jz      short loc_180024DC0
0x180024d9f  test    [rcx+1Ch], sil
0x180024da3  jz      short loc_180024DC0
0x180024da5  cmp     byte ptr [rcx+19h], 4
0x180024da9  jb      short loc_180024DC0
0x180024dab  mov     r9d, [rbp+57h+UsageLength]
0x180024daf  mov     edx, 66h ; 'f'
0x180024db4  mov     rcx, [rcx+10h]
0x180024db8  mov     r8, r12
0x180024dbb  call    WPP_SF_d
0x180024dc0  mov     rax, [rbp+57h+var_C0]
0x180024dc4  xor     r13d, r13d
0x180024dc7  mov     edx, [rbp+57h+UsageLength]
0x180024dca  mov     byte ptr [rax], 0
0x180024dcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180024dd4  test    edx, edx
0x180024dd6  jz      loc_180024F6C
0x180024ddc  mov     r8d, dword ptr [rbp+57h+var_B8]
0x180024de0  cmp     rcx, r14
0x180024de3  jz      short loc_180024E1A
0x180024de5  test    [rcx+1Ch], sil
0x180024de9  jz      short loc_180024E1A
0x180024deb  cmp     byte ptr [rcx+19h], 5
0x180024def  jb      short loc_180024E1A
0x180024df1  movzx   r8d, word ptr [rbx+r13*2]
0x180024df6  mov     edx, 67h ; 'g'
0x180024dfb  mov     rcx, [rcx+10h]
0x180024dff  mov     r9d, r13d
0x180024e02  mov     dword ptr [rsp+100h+ButtonCaps], r8d
0x180024e07  call    WPP_SF_dD
0x180024e0c  mov     edx, [rbp+57h+UsageLength]
0x180024e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e16  mov     r8d, dword ptr [rbp+57h+var_B8]
0x180024e1a  mov     rax, [rbp+57h+var_C0]
0x180024e1e  cmp     [rbx+r13*2], r8w
0x180024e23  jnz     short loc_180024E2F
0x180024e25  mov     [rax], sil
0x180024e28  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e2f  add     r13d, esi
0x180024e32  cmp     r13d, edx
0x180024e35  jnz     short loc_180024DE0
0x180024e37  jmp     loc_180024F6C
0x180024e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e43  cmp     rcx, r14
0x180024e46  jz      loc_180024F98
0x180024e4c  test    [rcx+1Ch], sil
0x180024e50  jz      loc_180024F68
0x180024e56  cmp     byte ptr [rcx+19h], 2
0x180024e5a  jb      loc_180024F68
0x180024e60  mov     rcx, [rcx+10h]
0x180024e64  mov     edx, 68h ; 'h'
0x180024e69  mov     r9d, eax
0x180024e6c  mov     r8, r12
0x180024e6f  call    WPP_SF_d
0x180024e74  jmp     loc_180024F61
0x180024e79  mov     r15d, 0C0000001h
0x180024e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e86  cmp     rcx, r14
0x180024e89  jz      short loc_180024EBA
0x180024e8b  test    [rcx+1Ch], sil
0x180024e8f  jz      short loc_180024EB1
0x180024e91  cmp     byte ptr [rcx+19h], 2
0x180024e95  jb      short loc_180024EB1
0x180024e97  mov     rcx, [rcx+10h]
0x180024e9b  mov     edx, 69h ; 'i'
0x180024ea0  mov     r8, r12
0x180024ea3  call    WPP_SF_
0x180024ea8  mov     rbx, [rbp+57h+UsageList]
0x180024eac  jmp     loc_180024F61
0x180024eb1  mov     rbx, [rbp+57h+UsageList]
0x180024eb5  jmp     loc_180024F68
0x180024eba  mov     rbx, [rbp+57h+UsageList]
0x180024ebe  jmp     loc_180024F98
0x180024ec3  mov     r15d, 0C0000001h
0x180024ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ed0  cmp     rcx, r14
0x180024ed3  jz      loc_180024F98
0x180024ed9  test    [rcx+1Ch], sil
0x180024edd  jz      loc_180024F68
0x180024ee3  cmp     byte ptr [rcx+19h], 2
0x180024ee7  jb      short loc_180024F68
0x180024ee9  mov     edx, 6Ah ; 'j'
0x180024eee  jmp     short loc_180024F55
0x180024ef0  mov     r15d, 0C0000001h
0x180024ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180024efd  cmp     rcx, r14
0x180024f00  jz      short loc_180024F2B
0x180024f02  test    [rcx+1Ch], sil
0x180024f06  jz      short loc_180024F25
0x180024f08  cmp     byte ptr [rcx+19h], 2
0x180024f0c  jb      short loc_180024F25
0x180024f0e  mov     rcx, [rcx+10h]
0x180024f12  mov     edx, 6Bh ; 'k'
0x180024f17  mov     r8, r12
0x180024f1a  call    WPP_SF_
0x180024f1f  mov     rdi, [rbp+57h+ReportBuffer]
0x180024f23  jmp     short loc_180024F61
0x180024f25  mov     rdi, [rbp+57h+ReportBuffer]
0x180024f29  jmp     short loc_180024F68
0x180024f2b  mov     rdi, [rbp+57h+ReportBuffer]
0x180024f2f  jmp     short loc_180024F98
0x180024f31  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f38  lea     r14, WPP_GLOBAL_Control
0x180024f3f  cmp     rcx, r14
0x180024f42  jz      short loc_180024F98
0x180024f44  test    [rcx+1Ch], sil
0x180024f48  jz      short loc_180024F68
0x180024f4a  cmp     byte ptr [rcx+19h], 2
0x180024f4e  jb      short loc_180024F68
0x180024f50  mov     edx, 6Ch ; 'l'
0x180024f55  mov     rcx, [rcx+10h]
0x180024f59  mov     r8, r12
0x180024f5c  call    WPP_SF_
0x180024f61  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f68  mov     rax, [rbp+57h+var_C0]
0x180024f6c  cmp     rcx, r14
0x180024f6f  jz      short loc_180024F98
0x180024f71  test    [rcx+1Ch], sil
0x180024f75  jz      short loc_180024F98
0x180024f77  cmp     byte ptr [rcx+19h], 4
0x180024f7b  jb      short loc_180024F98
0x180024f7d  movzx   eax, byte ptr [rax]
0x180024f80  mov     edx, 6Dh ; 'm'
0x180024f85  mov     rcx, [rcx+10h]
0x180024f89  mov     r9d, r15d
0x180024f8c  mov     r8, r12
0x180024f8f  mov     dword ptr [rsp+100h+ButtonCaps], eax
  ... truncated ...
```
