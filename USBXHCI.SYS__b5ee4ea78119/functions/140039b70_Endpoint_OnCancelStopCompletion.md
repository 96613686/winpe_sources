# Endpoint_OnCancelStopCompletion

- ea: `0x140039b70`
- end: `0x14003a166`
- name: `Endpoint_OnCancelStopCompletion`
- size: `1526`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002568`
- `0x140005d48`
- `0x14000c264`
- `0x1400246f0`
- `0x1400248c8`
- `0x14002792c`
- `0x14002b2c0`
- `0x14002b300`
- `0x1400324c0`
- `0x140039b70`
- `0x14003e79c`
- `0x140057db0`

## string_xrefs

- `0x140039f02`: `Stop Endpoint Command failed`

## pseudocode

```c
__int64 __fastcall Endpoint_OnCancelStopCompletion(__int64 a1, int a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 EndpointState; // rsi
  int v7; // r9d
  char *v8; // r14
  _QWORD *v9; // r15
  __int64 v10; // rcx
  int v11; // edx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // edi
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rax
  unsigned int v20; // ecx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 result; // rax
  int v25; // edx
  bool v26; // zf
  __int64 v27; // rax
  unsigned int v28; // edi
  __int64 v29; // rax
  __int64 v30; // r8
  __int64 v31; // rax
  unsigned int v32; // ecx
  unsigned int v33; // eax

  v3 = *(_QWORD *)(a1 + 48);
  if ( a2 != 3 )
  {
    EndpointState = (unsigned int)UsbDevice_GetEndpointState(*(_QWORD *)(v3 + 16), *(unsigned int *)(v3 + 152));
    UsbDevice_GetXhciEndpointDequeuePointer(*(_QWORD *)(v3 + 16), *(unsigned int *)(v3 + 152));
    v8 = (char *)(a1 + 60);
    v9 = (_QWORD *)(v3 + 80);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_ddLLi(*v9, (unsigned __int8)*v8, *(unsigned __int8 *)(*(_QWORD *)(v3 + 16) + 143LL), v7);
    v10 = *(_QWORD *)v3;
    if ( (*(_BYTE *)(*(_QWORD *)v3 + 744LL) & 0x20) == 0 || *v8 != 19 || (_DWORD)EndpointState != 4 )
    {
      v11 = (unsigned __int8)*v8 - 1;
      if ( *v8 != 1 )
      {
        if ( *v8 != 19 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v25 = *(unsigned __int8 *)(*(_QWORD *)(v3 + 16) + 143LL);
            LOBYTE(v25) = 2;
            WPP_RECORDER_SF_ddL(
              *v9,
              v25,
              13,
              87,
              (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
              *(_BYTE *)(*(_QWORD *)(v3 + 16) + 143LL),
              *(_DWORD *)(v3 + 152),
              *v8);
          }
          Controller_HwVerifierBreakIfEnabled(
            *(_QWORD *)v3,
            *(_QWORD *)(v3 + 8),
            *(_QWORD *)(v3 + 24),
            0x800000,
            (__int64)"Stop Endpoint Command failed",
            a1 + 24,
            a3);
          v26 = (unsigned int)Feature_ATFUR__private_IsEnabledDeviceUsageNoInline() == 0;
          v27 = *(_QWORD *)(v3 + 16);
          if ( v26 )
            Controller_ReportFatalError(*(_QWORD *)v3, 2, 4099, 0, v27, v3, 0);
          else
            Controller_ReportFatalErrorEx(*(_QWORD *)v3, 2, 4099, 4097, (unsigned __int8)*v8, v27, v3, 0);
          goto LABEL_34;
        }
        if ( (_DWORD)EndpointState != 1 )
        {
          if ( (_DWORD)EndpointState == 2 )
          {
            if ( (*(_BYTE *)(v3 + 99) & 3) != 1 )
            {
              v16 = 0;
              if ( *(_BYTE *)(v10 + 1046) && *(_DWORD *)(v3 + 164) != 1 )
              {
                if ( *(_BYTE *)(v3 + 1380) )
                {
                  ++*(_DWORD *)(v10 + 920);
                  ++*(_DWORD *)(v10 + 984);
                  *(_BYTE *)(v10 + 872) = 1;
                  v17 = *(_QWORD *)v3;
                  v18 = *(unsigned int *)(v3 + 164);
                  if ( (unsigned int)v18 > *(_DWORD *)(*(_QWORD *)v3 + 936LL) )
                  {
                    *(_DWORD *)(v17 + 936) = v18;
                    *(_BYTE *)(v17 + 872) = 1;
                    v18 = *(unsigned int *)(v3 + 164);
                  }
                  if ( *(_DWORD *)(*(_QWORD *)v3 + 644LL) == 1 )
                    v16 = *(unsigned __int16 *)(*(_QWORD *)v3 + 652LL)
                        | (*(unsigned __int16 *)(*(_QWORD *)v3 + 648LL) << 16);
                  MicrosoftTelemetryAssertTriggeredArgsMsgKM(
                    "USBXHCI.SYS",
                    v16,
                    v18,
                    "Feature_RetryStopEpOnSuccessWithStateNotStopped was effective (NOT STOPPED -> HALTED)");
                }
                v19 = *(_QWORD *)v3;
                v20 = *(_DWORD *)(v3 + 164);
                if ( v20 > *(_DWORD *)(*(_QWORD *)v3 + 908LL) )
                {
                  *(_DWORD *)(v19 + 908) = v20;
                  *(_BYTE *)(v19 + 872) = 1;
                }
              }
              v15 = 28;
              return ESM_AddEsmEvent(v3, v15);
            }
            IsEnabledDeviceUsageNoInline = Feature_ATFUR__private_IsEnabledDeviceUsageNoInline();
            v22 = *(_QWORD *)(v3 + 16);
            v23 = *(_QWORD *)v3;
            if ( IsEnabledDeviceUsageNoInline )
              Controller_ReportFatalErrorEx(v23, 2, 4099, 4098, 0, v22, v3, 0);
            else
              Controller_ReportFatalError(v23, 2, 4099, 0, v22, v3, 0);
          }
          else
          {
            if ( (_DWORD)EndpointState == 3 )
            {
              ++*(_DWORD *)(v10 + 904);
              v15 = 36;
              ++*(_DWORD *)(v10 + 972);
              *(_BYTE *)(v10 + 872) = 1;
              return ESM_AddEsmEvent(v3, v15);
            }
            v12 = Feature_ATFUR__private_IsEnabledDeviceUsageNoInline();
            v13 = *(_QWORD *)(v3 + 16);
            v14 = *(_QWORD *)v3;
            if ( v12 )
              Controller_ReportFatalErrorEx(v14, 2, 4100, 8193, EndpointState, v13, v3, 0);
            else
              Controller_ReportFatalError(v14, 2, 4100, 0, v13, v3, 0);
          }
          goto LABEL_34;
        }
        ++*(_DWORD *)(v10 + 904);
        ++*(_DWORD *)(v10 + 972);
        *(_BYTE *)(v10 + 872) = 1;
LABEL_38:
        v15 = 32;
        return ESM_AddEsmEvent(v3, v15);
      }
      v28 = 0;
      if ( *(_BYTE *)(v10 + 1046) )
      {
        if ( (_DWORD)EndpointState != 3 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v11) = 2;
            WPP_RECORDER_SF_ddL(
              *v9,
              v11,
              13,
              85,
              (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
              *(_BYTE *)(*(_QWORD *)(v3 + 16) + 143LL),
              *(_DWORD *)(v3 + 152),
              EndpointState);
          }
          *(_BYTE *)(v3 + 1380) = 1;
          _InterlockedAnd((volatile signed __int32 *)(v3 + 32), 0xFFFFFFEF);
          goto LABEL_38;
        }
        if ( *(_DWORD *)(v3 + 164) != 1 )
        {
          if ( *(_BYTE *)(v3 + 1380) )
          {
            ++*(_DWORD *)(v10 + 920);
            ++*(_DWORD *)(v10 + 984);
            *(_BYTE *)(v10 + 872) = 1;
            v29 = *(_QWORD *)v3;
            v30 = *(unsigned int *)(v3 + 164);
            if ( (unsigned int)v30 > *(_DWORD *)(*(_QWORD *)v3 + 936LL) )
            {
              *(_DWORD *)(v29 + 936) = v30;
              *(_BYTE *)(v29 + 872) = 1;
              v30 = *(unsigned int *)(v3 + 164);
            }
            if ( *(_DWORD *)(*(_QWORD *)v3 + 644LL) == 1 )
              v28 = *(unsigned __int16 *)(*(_QWORD *)v3 + 652LL) | (*(unsigned __int16 *)(*(_QWORD *)v3 + 648LL) << 16);
            MicrosoftTelemetryAssertTriggeredArgsMsgKM(
              "USBXHCI.SYS",
              v28,
              v30,
              "Feature_RetryStopEpOnSuccessWithStateNotStopped was effective (NOT STOPPED -> STOPPED)");
          }
          v31 = *(_QWORD *)v3;
          v32 = *(_DWORD *)(v3 + 164);
          if ( v32 > *(_DWORD *)(*(_QWORD *)v3 + 908LL) )
          {
            *(_DWORD *)(v31 + 908) = v32;
            *(_BYTE *)(v31 + 872) = 1;
          }
        }
      }
      else
      {
        if ( (_DWORD)EndpointState != 3 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v11) = 2;
            WPP_RECORDER_SF_ddL(
              *v9,
              v11,
              13,
              86,
              (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
              *(_BYTE *)(*(_QWORD *)(v3 + 16) + 143LL),
              *(_DWORD *)(v3 + 152),
              EndpointState);
          }
          Controller_ReportFatalError(*(_QWORD *)v3, 2, 4131, 0, *(_QWORD *)(v3 + 16), v3, 0);
          _m_prefetchw((const void *)(v3 + 32));
          result = (unsigned int)_InterlockedOr((volatile signed __int32 *)(v3 + 32), 2u);
          goto LABEL_35;
        }
        v33 = *(_DWORD *)(v3 + 164);
        if ( v33 != 1 && v33 > *(_DWORD *)(v10 + 908) )
        {
          *(_DWORD *)(v10 + 908) = v33;
          *(_BYTE *)(v10 + 872) = 1;
        }
      }
    }
    v15 = 16;
    return ESM_AddEsmEvent(v3, v15);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_DD(
      *(_QWORD *)(v3 + 80),
      a2,
      13,
      83,
      (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
      *(_BYTE *)(*(_QWORD *)(v3 + 16) + 143LL),
      *(_DWORD *)(v3 + 152));
  }
LABEL_34:
  _m_prefetchw((const void *)(v3 + 32));
  result = (unsigned int)_InterlockedOr((volatile signed __int32 *)(v3 + 32), 2u);
LABEL_35:
  if ( (result & 2) != 0 )
    return result;
  v15 = 12;
  return ESM_AddEsmEvent(v3, v15);
}

```

## disassembly

```asm
0x140039b70  push    rbx
0x140039b72  push    rbp
0x140039b73  push    rsi
0x140039b74  push    rdi
0x140039b75  push    r12
0x140039b77  push    r14
0x140039b79  push    r15
0x140039b7b  sub     rsp, 50h
0x140039b7f  mov     rbx, [rcx+30h]
0x140039b83  mov     r12, r8
0x140039b86  mov     rdi, rcx
0x140039b89  cmp     edx, 3
0x140039b8c  jnz     short loc_140039BEE
0x140039b8e  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140039b95  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140039b9c  jz      short loc_140039BD6
0x140039b9e  mov     rax, [rbx+10h]
0x140039ba2  lea     r9d, [rdx+50h]
0x140039ba6  lea     r8d, [rdx+0Ah]
0x140039baa  mov     dl, 4
0x140039bac  movzx   ecx, byte ptr [rax+8Fh]
0x140039bb3  mov     eax, [rbx+98h]
0x140039bb9  mov     dword ptr [rsp+88h+var_58], eax
0x140039bbd  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x140039bc4  mov     dword ptr [rsp+88h+var_60], ecx
0x140039bc8  mov     rcx, [rbx+50h]
0x140039bcc  mov     [rsp+88h+var_68], rax
0x140039bd1  call    WPP_RECORDER_SF_DD
0x140039bd6  prefetchw byte ptr [rbx+20h]
0x140039bda  mov     eax, [rbx+20h]
0x140039bdd  mov     ecx, eax
0x140039bdf  or      ecx, 2
0x140039be2  lock cmpxchg [rbx+20h], ecx
0x140039be7  jnz     short loc_140039BDD
0x140039be9  jmp     loc_140039E6D
0x140039bee  mov     edx, [rbx+98h]
0x140039bf4  mov     rcx, [rbx+10h]
0x140039bf8  call    UsbDevice_GetEndpointState
0x140039bfd  mov     edx, [rbx+98h]
0x140039c03  mov     rcx, [rbx+10h]
0x140039c07  mov     esi, eax
0x140039c09  call    UsbDevice_GetXhciEndpointDequeuePointer
0x140039c0e  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140039c15  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140039c1c  lea     r14, [rdi+3Ch]
0x140039c20  lea     r15, [rbx+50h]
0x140039c24  jz      short loc_140039C5A
0x140039c26  mov     rcx, [rbx+10h]
0x140039c2a  movzx   edx, byte ptr [r14]
0x140039c2e  mov     [rsp+88h+var_40], rax
0x140039c33  mov     eax, [rbx+98h]
0x140039c39  movzx   r8d, byte ptr [rcx+8Fh]
0x140039c41  mov     rcx, [r15]
0x140039c44  mov     [rsp+88h+var_48], esi
0x140039c48  mov     dword ptr [rsp+88h+var_50], edx
0x140039c4c  mov     dword ptr [rsp+88h+var_58], eax
0x140039c50  mov     dword ptr [rsp+88h+var_60], r8d
0x140039c55  call    WPP_RECORDER_SF_ddLLi
0x140039c5a  mov     rcx, [rbx]
0x140039c5d  test    byte ptr [rcx+2E8h], 20h
0x140039c64  jz      short loc_140039C75
0x140039c66  cmp     byte ptr [r14], 13h
0x140039c6a  jnz     short loc_140039C75
0x140039c6c  cmp     esi, 4
0x140039c6f  jz      loc_14003A149
0x140039c75  movzx   r8d, byte ptr [r14]
0x140039c79  mov     edx, r8d
0x140039c7c  sub     edx, 1
0x140039c7f  jz      loc_140039F85
0x140039c85  sub     edx, 0Ah
0x140039c88  jz      loc_140039E9C
0x140039c8e  cmp     edx, 8
0x140039c91  jnz     loc_140039E9C
0x140039c97  mov     eax, esi
0x140039c99  sub     eax, 1
0x140039c9c  jz      loc_140039E7F
0x140039ca2  sub     eax, 1
0x140039ca5  jz      loc_140039D3C
0x140039cab  cmp     eax, 1
0x140039cae  jz      short loc_140039D1F
0x140039cb0  call    Feature_ATFUR__private_IsEnabledDeviceUsageNoInline
0x140039cb5  mov     rdx, [rbx+10h]
0x140039cb9  xor     edi, edi
0x140039cbb  mov     rcx, [rbx]
0x140039cbe  mov     r8d, 1004h
0x140039cc4  test    eax, eax
0x140039cc6  jz      short loc_140039CEC
0x140039cc8  mov     [rsp+88h+var_50], rdi
0x140039ccd  mov     r9d, 2001h
0x140039cd3  mov     [rsp+88h+var_58], rbx
0x140039cd8  mov     [rsp+88h+var_60], rdx
0x140039cdd  lea     edx, [rdi+2]
0x140039ce0  mov     [rsp+88h+var_68], rsi
0x140039ce5  call    Controller_ReportFatalErrorEx
0x140039cea  jmp     short loc_140039D07
0x140039cec  xor     r9d, r9d
0x140039cef  mov     [rsp+88h+var_58], rdi
0x140039cf4  mov     [rsp+88h+var_60], rbx
0x140039cf9  mov     [rsp+88h+var_68], rdx
0x140039cfe  lea     edx, [r9+2]
0x140039d02  call    Controller_ReportFatalError
0x140039d07  prefetchw byte ptr [rbx+20h]
0x140039d0b  mov     eax, [rbx+20h]
0x140039d0e  mov     ecx, eax
0x140039d10  or      ecx, 2
0x140039d13  lock cmpxchg [rbx+20h], ecx
0x140039d18  jnz     short loc_140039D0E
0x140039d1a  jmp     loc_140039E6D
0x140039d1f  inc     dword ptr [rcx+388h]
0x140039d25  mov     edx, 24h ; '$'
0x140039d2a  inc     dword ptr [rcx+3CCh]
0x140039d30  mov     byte ptr [rcx+368h], 1
0x140039d37  jmp     loc_14003A14E
0x140039d3c  mov     al, [rbx+63h]
0x140039d3f  and     al, 3
0x140039d41  cmp     al, 1
0x140039d43  jz      loc_140039E05
0x140039d49  xor     edi, edi
0x140039d4b  cmp     [rcx+416h], dil
0x140039d52  jz      loc_140039DFB
0x140039d58  cmp     dword ptr [rbx+0A4h], 1
0x140039d5f  jz      loc_140039DFB
0x140039d65  cmp     [rbx+564h], dil
0x140039d6c  jz      short loc_140039DDD
0x140039d6e  inc     dword ptr [rcx+398h]
0x140039d74  inc     dword ptr [rcx+3D8h]
0x140039d7a  mov     byte ptr [rcx+368h], 1
0x140039d81  mov     rax, [rbx]
0x140039d84  mov     r8d, [rbx+0A4h]
0x140039d8b  cmp     r8d, [rax+3A8h]
0x140039d92  jbe     short loc_140039DA9
0x140039d94  mov     [rax+3A8h], r8d
0x140039d9b  mov     byte ptr [rax+368h], 1
0x140039da2  mov     r8d, [rbx+0A4h]
0x140039da9  mov     rax, [rbx]; __annotation("Debug", "TelemetryAssert", "FALSE", "Feature_RetryStopEpOnSuccessWithStateNotStopped was effective (NOT STOPPED -> HALTED)")
0x140039dac  cmp     dword ptr [rax+284h], 1
0x140039db3  jnz     short loc_140039DC8
0x140039db5  movzx   edi, word ptr [rax+288h]
0x140039dbc  movzx   eax, word ptr [rax+28Ch]
0x140039dc3  shl     edi, 10h
0x140039dc6  or      edi, eax
0x140039dc8  lea     r9, aFeatureRetryst_0; "Feature_RetryStopEpOnSuccessWithStateNo"...
0x140039dcf  mov     edx, edi
0x140039dd1  lea     rcx, aUsbxhciSys_0; "USBXHCI.SYS"
0x140039dd8  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x140039ddd  mov     rax, [rbx]
0x140039de0  mov     ecx, [rbx+0A4h]
0x140039de6  cmp     ecx, [rax+38Ch]
0x140039dec  jbe     short loc_140039DFB
0x140039dee  mov     [rax+38Ch], ecx
0x140039df4  mov     byte ptr [rax+368h], 1
0x140039dfb  mov     edx, 1Ch
0x140039e00  jmp     loc_14003A14E
0x140039e05  call    Feature_ATFUR__private_IsEnabledDeviceUsageNoInline
0x140039e0a  mov     rdx, [rbx+10h]
0x140039e0e  xor     edi, edi
0x140039e10  mov     rcx, [rbx]
0x140039e13  mov     r8d, 1003h
0x140039e19  test    eax, eax
0x140039e1b  jz      short loc_140039E3F
0x140039e1d  mov     [rsp+88h+var_50], rdi
0x140039e22  lea     r9d, [r8-1]
0x140039e26  mov     [rsp+88h+var_58], rbx
0x140039e2b  mov     [rsp+88h+var_60], rdx
0x140039e30  lea     edx, [rdi+2]
0x140039e33  mov     [rsp+88h+var_68], rdi
0x140039e38  call    Controller_ReportFatalErrorEx
0x140039e3d  jmp     short loc_140039E5A
0x140039e3f  xor     r9d, r9d
0x140039e42  mov     [rsp+88h+var_58], rdi
0x140039e47  mov     [rsp+88h+var_60], rbx
0x140039e4c  mov     [rsp+88h+var_68], rdx
0x140039e51  lea     edx, [r9+2]
0x140039e55  call    Controller_ReportFatalError
0x140039e5a  prefetchw byte ptr [rbx+20h]
0x140039e5e  mov     eax, [rbx+20h]
0x140039e61  mov     ecx, eax
0x140039e63  or      ecx, 2
0x140039e66  lock cmpxchg [rbx+20h], ecx
0x140039e6b  jnz     short loc_140039E61
0x140039e6d  test    al, 2
0x140039e6f  jnz     loc_14003A156
0x140039e75  mov     edx, 0Ch
0x140039e7a  jmp     loc_14003A14E
0x140039e7f  inc     dword ptr [rcx+388h]
0x140039e85  inc     dword ptr [rcx+3CCh]
0x140039e8b  mov     byte ptr [rcx+368h], 1
0x140039e92  mov     edx, 20h ; ' '
0x140039e97  jmp     loc_14003A14E
0x140039e9c  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140039ea3  jz      short loc_140039EE3
0x140039ea5  mov     rax, [rbx+10h]
0x140039ea9  mov     r9d, 57h ; 'W'
0x140039eaf  mov     rcx, [r15]
0x140039eb2  mov     dword ptr [rsp+88h+var_50], r8d
0x140039eb7  movzx   edx, byte ptr [rax+8Fh]
0x140039ebe  lea     r8d, [r9-4Ah]
0x140039ec2  mov     eax, [rbx+98h]
0x140039ec8  mov     dword ptr [rsp+88h+var_58], eax
0x140039ecc  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x140039ed3  mov     dword ptr [rsp+88h+var_60], edx
0x140039ed7  mov     dl, 2
0x140039ed9  mov     [rsp+88h+var_68], rax
0x140039ede  call    WPP_RECORDER_SF_ddL
0x140039ee3  mov     r8, [rbx+18h]
0x140039ee7  lea     rax, [rdi+18h]
0x140039eeb  mov     rdx, [rbx+8]
0x140039eef  mov     r9d, 800000h
0x140039ef5  mov     rcx, [rbx]
0x140039ef8  mov     [rsp+88h+var_58], r12
0x140039efd  mov     [rsp+88h+var_60], rax
0x140039f02  lea     rax, aStopEndpointCo; "Stop Endpoint Command failed"
0x140039f09  mov     [rsp+88h+var_68], rax
0x140039f0e  call    Controller_HwVerifierBreakIfEnabled
0x140039f13  call    Feature_ATFUR__private_IsEnabledDeviceUsageNoInline
0x140039f18  xor     edi, edi
0x140039f1a  mov     r8d, 1003h
0x140039f20  test    eax, eax
0x140039f22  mov     rax, [rbx+10h]
0x140039f26  lea     edx, [rdi+2]
0x140039f29  jnz     short loc_140039F47
0x140039f2b  mov     rcx, [rbx]
0x140039f2e  xor     r9d, r9d
0x140039f31  mov     [rsp+88h+var_58], rdi
0x140039f36  mov     [rsp+88h+var_60], rbx
0x140039f3b  mov     [rsp+88h+var_68], rax
0x140039f40  call    Controller_ReportFatalError
0x140039f45  jmp     short loc_140039F6D
0x140039f47  movzx   ecx, byte ptr [r14]
0x140039f4b  mov     r9d, 1001h
0x140039f51  mov     [rsp+88h+var_50], rdi
0x140039f56  mov     [rsp+88h+var_58], rbx
0x140039f5b  mov     [rsp+88h+var_60], rax
0x140039f60  mov     [rsp+88h+var_68], rcx
0x140039f65  mov     rcx, [rbx]
0x140039f68  call    Controller_ReportFatalErrorEx
0x140039f6d  prefetchw byte ptr [rbx+20h]
0x140039f71  mov     eax, [rbx+20h]
0x140039f74  mov     ecx, eax
0x140039f76  or      ecx, 2
0x140039f79  lock cmpxchg [rbx+20h], ecx
0x140039f7e  jnz     short loc_140039F74
0x140039f80  jmp     loc_140039E6D
0x140039f85  xor     edi, edi
0x140039f87  cmp     [rcx+416h], dil
0x140039f8e  jz      loc_14003A09A
0x140039f94  cmp     esi, 3
0x140039f97  jz      short loc_140039FEE
0x140039f99  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140039fa0  jz      short loc_140039FDD
0x140039fa2  mov     rax, [rbx+10h]
0x140039fa6  lea     r9d, [rdi+55h]
0x140039faa  mov     dword ptr [rsp+88h+var_50], esi
0x140039fae  lea     r8d, [rdi+0Dh]
0x140039fb2  mov     dl, 2
0x140039fb4  movzx   ecx, byte ptr [rax+8Fh]
0x140039fbb  mov     eax, [rbx+98h]
0x140039fc1  mov     dword ptr [rsp+88h+var_58], eax
0x140039fc5  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x140039fcc  mov     dword ptr [rsp+88h+var_60], ecx
0x140039fd0  mov     rcx, [r15]
0x140039fd3  mov     [rsp+88h+var_68], rax
0x140039fd8  call    WPP_RECORDER_SF_ddL
0x140039fdd  mov     byte ptr [rbx+564h], 1
0x140039fe4  lock and dword ptr [rbx+20h], 0FFFFFFEFh
0x140039fe9  jmp     loc_140039E92
0x140039fee  cmp     dword ptr [rbx+0A4h], 1
0x140039ff5  jz      loc_14003A149
0x140039ffb  cmp     [rbx+564h], dil
0x14003a002  jz      short loc_14003A073
0x14003a004  inc     dword ptr [rcx+398h]
0x14003a00a  inc     dword ptr [rcx+3D8h]
0x14003a010  mov     byte ptr [rcx+368h], 1
0x14003a017  mov     rax, [rbx]
0x14003a01a  mov     r8d, [rbx+0A4h]
0x14003a021  cmp     r8d, [rax+3A8h]
0x14003a028  jbe     short loc_14003A03F
0x14003a02a  mov     [rax+3A8h], r8d
0x14003a031  mov     byte ptr [rax+368h], 1
0x14003a038  mov     r8d, [rbx+0A4h]
0x14003a03f  mov     rax, [rbx]; __annotation("Debug", "TelemetryAssert", "FALSE", "Feature_RetryStopEpOnSuccessWithStateNotStopped was effective (NOT STOPPED -> STOPPED)")
0x14003a042  cmp     dword ptr [rax+284h], 1
0x14003a049  jnz     short loc_14003A05E
0x14003a04b  movzx   edi, word ptr [rax+288h]
0x14003a052  movzx   eax, word ptr [rax+28Ch]
0x14003a059  shl     edi, 10h
0x14003a05c  or      edi, eax
0x14003a05e  lea     r9, aFeatureRetryst; "Feature_RetryStopEpOnSuccessWithStateNo"...
0x14003a065  mov     edx, edi
0x14003a067  lea     rcx, aUsbxhciSys_0; "USBXHCI.SYS"
0x14003a06e  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x14003a073  mov     rax, [rbx]
0x14003a076  mov     ecx, [rbx+0A4h]
0x14003a07c  cmp     ecx, [rax+38Ch]
0x14003a082  jbe     loc_14003A149
0x14003a088  mov     [rax+38Ch], ecx
0x14003a08e  mov     byte ptr [rax+368h], 1
0x14003a095  jmp     loc_14003A149
0x14003a09a  cmp     esi, 3
0x14003a09d  jz      loc_14003A129
  ... truncated ...
```
