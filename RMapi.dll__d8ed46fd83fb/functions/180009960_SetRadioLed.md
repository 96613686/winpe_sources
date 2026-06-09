# SetRadioLed

- ea: `0x180009960`
- end: `0x180009da9`
- name: `SetRadioLed`
- size: `1097`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18000970c`

## callees

- `0x180002ec0`
- `0x180003d50`
- `0x180007c48`
- `0x180009960`
- `0x18000d2a0`
- `0x18000df4c`
- `0x180024a48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009a78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009b88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009a78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009b88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d6a`
- `HID!HidP_UnsetUsages` at `0x180009c3f`
- `HID!HidP_UnsetUsages` at `0x180009c3f`
- `HID!HidP_SetUsages` at `0x180009bd9`
- `HID!HidP_SetUsages` at `0x180009bd9`
- `HID!HidP_MaxUsageListLength` at `0x180009a0b`
- `HID!HidP_MaxUsageListLength` at `0x180009a0b`
- `HID!HidD_SetOutputReport` at `0x180009cca`
- `HID!HidD_SetOutputReport` at `0x180009cca`

## pseudocode

```c
void __fastcall SetRadioLed(__int64 a1, int a2)
{
  CHAR *Report; // rdi
  ULONG v5; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  unsigned int v8; // eax
  USHORT *v9; // rax
  USHORT *v10; // rbx
  __int64 v11; // r8
  __int64 v12; // rbp
  size_t ReportLength; // r14
  SIZE_T v14; // rcx
  CHAR *v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rdx
  struct _HIDP_PREPARSED_DATA *PreparsedData; // [rsp+28h] [rbp-50h]
  ULONG UsageLength; // [rsp+40h] [rbp-38h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation>::GetImpl'::`2'::impl)
    || a1 && *(_QWORD *)(a1 + 528) )
  {
    Report = 0;
    v5 = HidP_MaxUsageListLength(HidP_Output, 1u, *(PHIDP_PREPARSED_DATA *)(a1 + 528));
    UsageLength = v5;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 84, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids, v5);
      v5 = UsageLength;
      v6 = WPP_GLOBAL_Control;
    }
    v7 = v5;
    if ( v5 )
    {
      if ( 0xFFFFFFFFFFFFFFFFuLL / v5 < 2 )
      {
        v10 = 0;
        goto LABEL_73;
      }
      v8 = 2 * v5;
      if ( (unsigned __int64)(2 * v7) > 0x7FFFFFFF )
      {
        v10 = 0;
        goto LABEL_73;
      }
    }
    else
    {
      v8 = 0;
    }
    v9 = (USHORT *)CoTaskMemAlloc(v8);
    v10 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, 2LL * UsageLength);
      v12 = 0;
      if ( UsageLength )
      {
        do
        {
          v10[v12] = 199;
          v6 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
          {
            WPP_SF_dD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 85, v11, (unsigned int)v12, 199);
            v6 = WPP_GLOBAL_Control;
          }
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (_DWORD)v12 != UsageLength );
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
      }
      ReportLength = *(unsigned __int16 *)(a1 + 542);
      if ( (_UNKNOWN *)v6 != &WPP_GLOBAL_Control && (*(_BYTE *)(v6 + 28) & 1) != 0 && *(_BYTE *)(v6 + 25) >= 4u )
      {
        WPP_SF_d(
          *(_QWORD *)(v6 + 16),
          86,
          &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids,
          *(unsigned __int16 *)(a1 + 542));
        v6 = WPP_GLOBAL_Control;
      }
      if ( (_DWORD)ReportLength )
      {
        if ( !(0xFFFFFFFFFFFFFFFFuLL / ReportLength) )
        {
LABEL_68:
          if ( (_UNKNOWN *)v6 == &WPP_GLOBAL_Control || (*(_BYTE *)(v6 + 28) & 1) == 0 || *(_BYTE *)(v6 + 25) < 2u )
            goto LABEL_78;
          v21 = 94;
          goto LABEL_77;
        }
        v14 = ReportLength;
      }
      else
      {
        v14 = 0;
      }
      v15 = (CHAR *)CoTaskMemAlloc(v14);
      Report = v15;
      if ( v15 )
      {
        memset_0(v15, 0, ReportLength);
        PreparsedData = *(struct _HIDP_PREPARSED_DATA **)(a1 + 528);
        if ( a2 == 1 )
        {
          v16 = HidP_SetUsages(HidP_Output, 1u, 0, v10, &UsageLength, PreparsedData, Report, ReportLength);
          if ( v16 == 1114112 )
          {
            v17 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
              && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
            {
              v18 = 87;
LABEL_57:
              WPP_SF_(*(_QWORD *)(v17 + 16), v18, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
              goto LABEL_58;
            }
            goto LABEL_58;
          }
          v19 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0
            || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u )
          {
            goto LABEL_78;
          }
          v20 = 88;
        }
        else
        {
          v16 = HidP_UnsetUsages(HidP_Output, 1u, 0, v10, &UsageLength, PreparsedData, Report, ReportLength);
          if ( v16 == 1114112 || v16 == -1072627697 )
          {
            v17 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
              && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
            {
              v18 = 89;
              goto LABEL_57;
            }
LABEL_58:
            if ( HidD_SetOutputReport(*(HANDLE *)a1, Report, ReportLength) )
            {
              v6 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0
                || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u )
              {
                goto LABEL_78;
              }
              v21 = 92;
            }
            else
            {
              v6 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0
                || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u )
              {
                goto LABEL_78;
              }
              v21 = 93;
            }
            goto LABEL_77;
          }
          v19 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0
            || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u )
          {
            goto LABEL_78;
          }
          v20 = 90;
        }
        WPP_SF_d(*(_QWORD *)(v19 + 16), v20, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids, v16);
LABEL_78:
        CoTaskMemFree(Report);
        CoTaskMemFree(v10);
        return;
      }
      v6 = WPP_GLOBAL_Control;
      goto LABEL_68;
    }
    v6 = WPP_GLOBAL_Control;
LABEL_73:
    if ( (_UNKNOWN *)v6 == &WPP_GLOBAL_Control || (*(_BYTE *)(v6 + 28) & 1) == 0 || *(_BYTE *)(v6 + 25) < 2u )
      goto LABEL_78;
    v21 = 95;
LABEL_77:
    WPP_SF_(*(_QWORD *)(v6 + 16), v21, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
    goto LABEL_78;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 83, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
  }
}

```

## disassembly

```asm
0x180009960  push    rsi
0x180009962  push    r13
0x180009964  push    r15
0x180009966  sub     rsp, 60h
0x18000996a  mov     rax, cs:__security_cookie
0x180009971  xor     rax, rsp
0x180009974  mov     [rsp+78h+var_30], rax
0x180009979  mov     r13d, edx
0x18000997c  mov     r15, rcx
0x18000997f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation> `wil::Feature<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation>::GetImpl(void)'::`2'::impl
0x180009986  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation>::__private_IsEnabled(void)
0x18000998b  test    al, al
0x18000998d  jz      short loc_1800099E3
0x18000998f  test    r15, r15
0x180009992  jz      short loc_18000999E
0x180009994  cmp     qword ptr [r15+210h], 0
0x18000999c  jnz     short loc_1800099E3
0x18000999e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099a5  lea     rsi, WPP_GLOBAL_Control
0x1800099ac  cmp     rcx, rsi
0x1800099af  jz      loc_180009D92
0x1800099b5  test    byte ptr [rcx+1Ch], 1
0x1800099b9  jz      loc_180009D92
0x1800099bf  cmp     byte ptr [rcx+19h], 2
0x1800099c3  jb      loc_180009D92
0x1800099c9  mov     rcx, [rcx+10h]
0x1800099cd  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x1800099d4  mov     edx, 53h ; 'S'
0x1800099d9  call    WPP_SF_
0x1800099de  jmp     loc_180009D92
0x1800099e3  mov     r8, [r15+210h]; PreparsedData
0x1800099ea  mov     edx, 1; UsagePage
0x1800099ef  mov     [rsp+78h+arg_8], rbx
0x1800099f7  mov     ecx, edx; ReportType
0x1800099f9  mov     [rsp+78h+arg_18], rdi
0x180009a01  xor     edi, edi
0x180009a03  mov     [rsp+78h+var_38], 0
0x180009a0b  call    cs:__imp_HidP_MaxUsageListLength
0x180009a11  mov     [rsp+78h+var_38], eax
0x180009a15  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a1c  lea     rsi, WPP_GLOBAL_Control
0x180009a23  cmp     rcx, rsi
0x180009a26  jz      short loc_180009A57
0x180009a28  test    byte ptr [rcx+1Ch], 1
0x180009a2c  jz      short loc_180009A57
0x180009a2e  cmp     byte ptr [rcx+19h], 4
0x180009a32  jb      short loc_180009A57
0x180009a34  mov     rcx, [rcx+10h]
0x180009a38  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180009a3f  mov     edx, 54h ; 'T'
0x180009a44  mov     r9d, eax
0x180009a47  call    WPP_SF_d
0x180009a4c  mov     eax, [rsp+78h+var_38]
0x180009a50  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a57  mov     [rsp+78h+arg_10], rbp
0x180009a5f  mov     [rsp+78h+var_20], r12
0x180009a64  mov     [rsp+78h+var_28], r14
0x180009a69  mov     r8d, eax
0x180009a6c  test    eax, eax
0x180009a6e  jnz     loc_180009AF4
0x180009a74  xor     eax, eax
0x180009a76  mov     ecx, eax; cb
0x180009a78  call    cs:__imp_CoTaskMemAlloc
0x180009a7e  mov     rbx, rax
0x180009a81  test    rax, rax
0x180009a84  jz      loc_180009D31
0x180009a8a  mov     r8d, [rsp+78h+var_38]
0x180009a8f  xor     edx, edx; Val
0x180009a91  add     r8, r8; Size
0x180009a94  mov     rcx, rax; void *
0x180009a97  call    memset_0
0x180009a9c  xor     ebp, ebp
0x180009a9e  mov     r12, rbx
0x180009aa1  cmp     [rsp+78h+var_38], edi
0x180009aa5  jz      short loc_180009B24
0x180009aa7  mov     r14d, 0C7h
0x180009aad  nop     dword ptr [rax]
0x180009ab0  mov     [rbx+rbp*2], r14w
0x180009ab5  mov     rcx, cs:WPP_GLOBAL_Control
0x180009abc  cmp     rcx, rsi
0x180009abf  jz      short loc_180009AEA
0x180009ac1  test    byte ptr [rcx+1Ch], 1
0x180009ac5  jz      short loc_180009AEA
0x180009ac7  cmp     byte ptr [rcx+19h], 4
0x180009acb  jb      short loc_180009AEA
0x180009acd  mov     rcx, [rcx+10h]
0x180009ad1  mov     edx, 55h ; 'U'
0x180009ad6  mov     r9d, ebp
0x180009ad9  mov     dword ptr [rsp+78h+UsageLength], r14d
0x180009ade  call    WPP_SF_dD
0x180009ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009aea  inc     ebp
0x180009aec  cmp     ebp, [rsp+78h+var_38]
0x180009af0  jnz     short loc_180009AB0
0x180009af2  jmp     short loc_180009B2B
0x180009af4  xor     edx, edx
0x180009af6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009afd  div     r8
0x180009b00  cmp     rax, 2
0x180009b04  jnb     short loc_180009B0D
0x180009b06  xor     ebx, ebx
0x180009b08  jmp     loc_180009D38
0x180009b0d  lea     rax, [r8+r8]
0x180009b11  cmp     rax, 7FFFFFFFh
0x180009b17  jbe     loc_180009A76
0x180009b1d  xor     ebx, ebx
0x180009b1f  jmp     loc_180009D38
0x180009b24  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b2b  movzx   r14d, word ptr [r15+21Eh]
0x180009b33  cmp     rcx, rsi
0x180009b36  jz      short loc_180009B63
0x180009b38  test    byte ptr [rcx+1Ch], 1
0x180009b3c  jz      short loc_180009B63
0x180009b3e  cmp     byte ptr [rcx+19h], 4
0x180009b42  jb      short loc_180009B63
0x180009b44  mov     rcx, [rcx+10h]
0x180009b48  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180009b4f  mov     edx, 56h ; 'V'
0x180009b54  mov     r9d, r14d
0x180009b57  call    WPP_SF_d
0x180009b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b63  mov     rbp, r14
0x180009b66  test    r14d, r14d
0x180009b69  jnz     short loc_180009B6F
0x180009b6b  xor     ecx, ecx
0x180009b6d  jmp     short loc_180009B88
0x180009b6f  xor     edx, edx
0x180009b71  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009b78  div     rbp
0x180009b7b  cmp     rax, 1
0x180009b7f  jb      loc_180009D19
0x180009b85  mov     rcx, rbp; cb
0x180009b88  call    cs:__imp_CoTaskMemAlloc
0x180009b8e  mov     rdi, rax
0x180009b91  test    rax, rax
0x180009b94  jz      loc_180009D12
0x180009b9a  mov     r8, rbp; Size
0x180009b9d  xor     edx, edx; Val
0x180009b9f  mov     rcx, rax; void *
0x180009ba2  call    memset_0
0x180009ba7  mov     rax, [r15+210h]
0x180009bae  mov     edx, 1; UsagePage
0x180009bb3  mov     [rsp+78h+ReportLength], r14d; ReportLength
0x180009bb8  xor     r8d, r8d; LinkCollection
0x180009bbb  mov     [rsp+78h+Report], rdi; Report
0x180009bc0  mov     r9, r12; UsageList
0x180009bc3  mov     [rsp+78h+PreparsedData], rax; PreparsedData
0x180009bc8  lea     rax, [rsp+78h+var_38]
0x180009bcd  mov     [rsp+78h+UsageLength], rax; UsageLength
0x180009bd2  mov     ecx, edx; ReportType
0x180009bd4  cmp     r13d, edx
0x180009bd7  jnz     short loc_180009C3F
0x180009bd9  call    cs:__imp_HidP_SetUsages
0x180009bdf  cmp     eax, 110000h
0x180009be4  jnz     short loc_180009C14
0x180009be6  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bed  cmp     rcx, rsi
0x180009bf0  jz      loc_180009CC1
0x180009bf6  test    byte ptr [rcx+1Ch], 1
0x180009bfa  jz      loc_180009CC1
0x180009c00  cmp     byte ptr [rcx+19h], 4
0x180009c04  jb      loc_180009CC1
0x180009c0a  mov     edx, 57h ; 'W'
0x180009c0f  jmp     loc_180009CB1
0x180009c14  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c1b  cmp     rcx, rsi
0x180009c1e  jz      loc_180009D5E
0x180009c24  test    byte ptr [rcx+1Ch], 1
0x180009c28  jz      loc_180009D5E
0x180009c2e  cmp     byte ptr [rcx+19h], 4
0x180009c32  jb      loc_180009D5E
0x180009c38  mov     edx, 58h ; 'X'
0x180009c3d  jmp     short loc_180009C7C
0x180009c3f  call    cs:__imp_HidP_UnsetUsages
0x180009c45  cmp     eax, 110000h
0x180009c4a  jz      short loc_180009C94
0x180009c4c  cmp     eax, 0C011000Fh
0x180009c51  jz      short loc_180009C94
0x180009c53  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c5a  cmp     rcx, rsi
0x180009c5d  jz      loc_180009D5E
0x180009c63  test    byte ptr [rcx+1Ch], 1
0x180009c67  jz      loc_180009D5E
0x180009c6d  cmp     byte ptr [rcx+19h], 4
0x180009c71  jb      loc_180009D5E
0x180009c77  mov     edx, 5Ah ; 'Z'
0x180009c7c  mov     rcx, [rcx+10h]
0x180009c80  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180009c87  mov     r9d, eax
0x180009c8a  call    WPP_SF_d
0x180009c8f  jmp     loc_180009D5E
0x180009c94  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c9b  cmp     rcx, rsi
0x180009c9e  jz      short loc_180009CC1
0x180009ca0  test    byte ptr [rcx+1Ch], 1
0x180009ca4  jz      short loc_180009CC1
0x180009ca6  cmp     byte ptr [rcx+19h], 4
0x180009caa  jb      short loc_180009CC1
0x180009cac  mov     edx, 59h ; 'Y'
0x180009cb1  mov     rcx, [rcx+10h]
0x180009cb5  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180009cbc  call    WPP_SF_
0x180009cc1  mov     rcx, [r15]; HidDeviceObject
0x180009cc4  mov     r8d, r14d; ReportBufferLength
0x180009cc7  mov     rdx, rdi; ReportBuffer
0x180009cca  call    cs:__imp_HidD_SetOutputReport
0x180009cd0  test    al, al
0x180009cd2  jz      short loc_180009CF3
0x180009cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cdb  cmp     rcx, rsi
0x180009cde  jz      short loc_180009D5E
0x180009ce0  test    byte ptr [rcx+1Ch], 1
0x180009ce4  jz      short loc_180009D5E
0x180009ce6  cmp     byte ptr [rcx+19h], 4
0x180009cea  jb      short loc_180009D5E
0x180009cec  mov     edx, 5Ch ; '\'
0x180009cf1  jmp     short loc_180009D4E
0x180009cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cfa  cmp     rcx, rsi
0x180009cfd  jz      short loc_180009D5E
0x180009cff  test    byte ptr [rcx+1Ch], 1
0x180009d03  jz      short loc_180009D5E
0x180009d05  cmp     byte ptr [rcx+19h], 4
0x180009d09  jb      short loc_180009D5E
0x180009d0b  mov     edx, 5Dh ; ']'
0x180009d10  jmp     short loc_180009D4E
0x180009d12  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d19  cmp     rcx, rsi
0x180009d1c  jz      short loc_180009D5E
0x180009d1e  test    byte ptr [rcx+1Ch], 1
0x180009d22  jz      short loc_180009D5E
0x180009d24  cmp     byte ptr [rcx+19h], 2
0x180009d28  jb      short loc_180009D5E
0x180009d2a  mov     edx, 5Eh ; '^'
0x180009d2f  jmp     short loc_180009D4E
0x180009d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d38  cmp     rcx, rsi
0x180009d3b  jz      short loc_180009D5E
0x180009d3d  test    byte ptr [rcx+1Ch], 1
0x180009d41  jz      short loc_180009D5E
0x180009d43  cmp     byte ptr [rcx+19h], 2
0x180009d47  jb      short loc_180009D5E
0x180009d49  mov     edx, 5Fh ; '_'
0x180009d4e  mov     rcx, [rcx+10h]
0x180009d52  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180009d59  call    WPP_SF_
0x180009d5e  mov     rcx, rdi; pv
0x180009d61  call    cs:__imp_CoTaskMemFree
0x180009d67  mov     rcx, rbx; pv
0x180009d6a  call    cs:__imp_CoTaskMemFree
0x180009d70  mov     r14, [rsp+78h+var_28]
0x180009d75  mov     r12, [rsp+78h+var_20]
0x180009d7a  mov     rdi, [rsp+78h+arg_18]
0x180009d82  mov     rbp, [rsp+78h+arg_10]
0x180009d8a  mov     rbx, [rsp+78h+arg_8]
0x180009d92  mov     rcx, [rsp+78h+var_30]
0x180009d97  xor     rcx, rsp; StackCookie
0x180009d9a  call    __security_check_cookie
0x180009d9f  add     rsp, 60h
0x180009da3  pop     r15
0x180009da5  pop     r13
0x180009da7  pop     rsi
0x180009da8  retn
```
