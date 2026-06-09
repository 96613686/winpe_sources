# SetConfigItem(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180009304`
- end: `0x180009766`
- name: `?SetConfigItem@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `1122`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004950`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x180008998`
- `0x180008aa8`
- `0x180008b30`
- `0x180008b6c`
- `0x180009304`
- `0x18000a17c`
- `0x18000a1bc`
- `0x18000a22c`
- `0x18000a290`
- `0x18000a2c0`
- `0x18000a358`
- `0x18000a7fc`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `mi!MI_Application_InitializeV1` at `0x180009427`
- `mi!MI_Application_InitializeV1` at `0x180009427`

## string_xrefs

- `0x180009378`: `MDM_ConfigSetting`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SetConfigItem(_QWORD *a1, _QWORD *a2)
{
  bool v4; // r14
  bool v5; // r15
  _QWORD *v6; // r9
  const MI_Char *v7; // rdx
  MI_Result v8; // ecx
  const MI_Char *v9; // r8
  MI_DestinationOptions *v10; // r9
  bool v11; // si
  unsigned int v12; // ecx
  unsigned int v13; // ebx
  LPCWSTR v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // rcx
  MI_Result v18; // ecx
  const MI_ClassDecl *v19; // r8
  const MI_Char *v20; // rdx
  MI_Result v21; // eax
  const MI_Char *v22; // rdx
  MI_Result v23; // ecx
  MI_Type v24; // r9d
  const MI_Char *v25; // rdx
  MI_Result v26; // ecx
  const MI_OperationFT *ft; // rax
  int v28; // edx
  int v29; // r8d
  int v30; // r9d
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  MI_Char **errorMessage; // [rsp+20h] [rbp-E0h]
  MI_Uint32 errorMessagea; // [rsp+20h] [rbp-E0h]
  MI_Uint32 errorMessageb; // [rsp+20h] [rbp-E0h]
  MI_Instance **completionDetails; // [rsp+28h] [rbp-D8h]
  MI_Boolean moreResults[4]; // [rsp+40h] [rbp-C0h] BYREF
  MI_Result result; // [rsp+44h] [rbp-BCh] BYREF
  MI_Instance *instance; // [rsp+48h] [rbp-B8h] BYREF
  MI_Char *v42; // [rsp+50h] [rbp-B0h] BYREF
  MI_Operation operation; // [rsp+58h] [rbp-A8h] BYREF
  MI_Instance *v44; // [rsp+70h] [rbp-90h] BYREF
  MI_Instance *v45; // [rsp+78h] [rbp-88h] BYREF
  MI_Session session; // [rsp+80h] [rbp-80h] BYREF
  MI_Application application; // [rsp+98h] [rbp-68h] BYREF
  MI_Value value; // [rsp+B0h] [rbp-50h] BYREF
  MI_Value v49; // [rsp+D8h] [rbp-28h] BYREF
  MI_Char *v50[4]; // [rsp+100h] [rbp+0h] BYREF
  MI_Char *name[4]; // [rsp+120h] [rbp+20h] BYREF
  MI_Char *className[4]; // [rsp+140h] [rbp+40h] BYREF

  result = MI_RESULT_FAILED;
  memset(&application, 0, sizeof(application));
  memset(&session, 0, sizeof(session));
  memset(&operation, 0, sizeof(operation));
  moreResults[0] = 1;
  v4 = 0;
  v5 = 0;
  std::wstring::wstring(className, L"MDM_ConfigSetting");
  std::wstring::wstring(name, L"SettingName");
  std::wstring::wstring(v50, L"SettingValue");
  memset(&value, 0, sizeof(value));
  memset(&v49, 0, sizeof(v49));
  instance = 0;
  v45 = 0;
  v44 = 0;
  v42 = 0;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    if ( a1[3] < 8u )
      v6 = a1;
    else
      v6 = (_QWORD *)*a1;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids, v6);
  }
  v8 = MI_Application_InitializeV1(0, 0, 0, &application);
  result = v8;
  if ( v8 )
  {
    v11 = 0;
    v13 = MIResultToHRESULT(v8);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v15 = 69;
LABEL_11:
      v16 = v12;
      v17 = *((_QWORD *)v14 + 2);
LABEL_12:
      WPP_SF_d(v17, v15, &WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids, v16);
    }
  }
  else
  {
    v11 = 1;
    v18 = MI_Application_NewSession(
            &application,
            v7,
            v9,
            v10,
            (MI_SessionCallbacks *)errorMessage,
            completionDetails,
            &session);
    result = v18;
    if ( v18 )
    {
      v13 = MIResultToHRESULT(v18);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v15 = 70;
        goto LABEL_11;
      }
    }
    else
    {
      v5 = 1;
      v20 = (const MI_Char *)className;
      if ( className[3] >= (MI_Char *)8 )
        v20 = className[0];
      v21 = MI_Application_NewInstance(&application, v20, v19, &instance);
      result = v21;
      if ( v21 )
      {
        v13 = MIResultToHRESULT(v21);
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          v15 = 71;
          v17 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          goto LABEL_12;
        }
      }
      else
      {
        if ( a1[3] >= 8u )
          a1 = (_QWORD *)*a1;
        value.uint64 = (MI_Uint64)a1;
        if ( a2[3] >= 8u )
          a2 = (_QWORD *)*a2;
        v49.uint64 = (MI_Uint64)a2;
        v22 = (const MI_Char *)name;
        if ( name[3] >= (MI_Char *)8 )
          v22 = name[0];
        v23 = MI_Instance_AddElement(instance, v22, &value, MI_BOOLEAN, errorMessagea);
        result = v23;
        if ( v23 )
        {
          v13 = MIResultToHRESULT(v23);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          {
            v15 = 72;
            goto LABEL_11;
          }
        }
        else
        {
          v25 = (const MI_Char *)v50;
          if ( v50[3] >= (MI_Char *)8 )
            v25 = v50[0];
          v26 = MI_Instance_AddElement(instance, v25, &v49, v24, errorMessageb);
          result = v26;
          if ( v26 )
          {
            v13 = MIResultToHRESULT(v26);
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
            {
              v15 = 73;
              goto LABEL_11;
            }
          }
          else
          {
            if ( session.ft )
            {
              ((void (__fastcall *)(MI_Session *, _QWORD, _QWORD, const unsigned __int16 *, MI_Instance *, _QWORD, MI_Operation *))session.ft->CreateInstance)(
                &session,
                0,
                0,
                L"root\\cimv2\\mdm",
                instance,
                0,
                &operation);
              ft = operation.ft;
            }
            else
            {
              ft = 0;
              memset(&operation, 0, sizeof(operation));
            }
            if ( ft )
            {
              v4 = 1;
              while ( 1 )
              {
                MI_Operation_GetInstance(
                  &operation,
                  (const MI_Instance **)&v45,
                  moreResults,
                  &result,
                  (const MI_Char **)&v42,
                  (const MI_Instance **)&v44);
                if ( result )
                  break;
                if ( moreResults[0] != 1 )
                {
                  v13 = 0;
                  goto LABEL_53;
                }
              }
              v13 = MIResultToHRESULT(result);
              if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, v29, v30, (__int64)v42);
            }
            else
            {
              v13 = -2147467259;
              if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids);
            }
          }
        }
      }
    }
  }
LABEL_53:
  if ( instance )
    MI_Instance_Delete(instance);
  MISessionCleanUp(&application, &session, &operation, v4, v5, v11);
  LOBYTE(v31) = 1;
  std::wstring::_Tidy(v50, v31, 0);
  LOBYTE(v32) = 1;
  std::wstring::_Tidy(name, v32, 0);
  LOBYTE(v33) = 1;
  std::wstring::_Tidy(className, v33, 0);
  return v13;
}

```

## disassembly

```asm
0x180009304  mov     [rsp-8+arg_10], rbx
0x180009309  mov     [rsp-8+arg_18], rsi
0x18000930e  push    rbp
0x18000930f  push    rdi
0x180009310  push    r13
0x180009312  push    r14
0x180009314  push    r15
0x180009316  lea     rbp, [rsp-70h]
0x18000931b  sub     rsp, 170h
0x180009322  mov     rax, cs:__security_cookie
0x180009329  xor     rax, rsp
0x18000932c  mov     [rbp+90h+var_30], rax
0x180009330  mov     rdi, rdx
0x180009333  mov     rbx, rcx
0x180009336  mov     [rsp+190h+result], 1
0x18000933e  mov     [rbp+90h+application.reserved1], 0
0x180009346  xorps   xmm0, xmm0
0x180009349  movdqu  xmmword ptr [rbp+90h+application.reserved2], xmm0
0x18000934e  mov     [rbp+90h+var_110.reserved1], 0
0x180009356  xorps   xmm1, xmm1
0x180009359  movdqu  xmmword ptr [rbp+90h+var_110.reserved2], xmm1
0x18000935e  mov     [rsp+190h+operation.reserved1], 0
0x180009367  movdqu  xmmword ptr [rsp+190h+operation.reserved2], xmm0
0x18000936d  mov     [rsp+190h+moreResults], 1
0x180009372  xor     r14b, r14b
0x180009375  xor     r15b, r15b
0x180009378  lea     rdx, aMdmConfigsetti; "MDM_ConfigSetting"
0x18000937f  lea     rcx, [rbp+90h+className]
0x180009383  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180009388  nop
0x180009389  lea     rdx, aSettingname; "SettingName"
0x180009390  lea     rcx, [rbp+90h+name]
0x180009394  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180009399  nop
0x18000939a  lea     rdx, aSettingvalue; "SettingValue"
0x1800093a1  lea     rcx, [rbp+90h+var_90]
0x1800093a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800093aa  nop
0x1800093ab  xorps   xmm0, xmm0
0x1800093ae  xor     eax, eax
0x1800093b0  movups  xmmword ptr [rbp+90h+value], xmm0
0x1800093b4  movups  xmmword ptr [rbp+90h+value+10h], xmm0
0x1800093b8  mov     qword ptr [rbp+90h+value+20h], rax
0x1800093bc  xorps   xmm1, xmm1
0x1800093bf  movups  xmmword ptr [rbp+90h+var_B8], xmm1
0x1800093c3  movups  xmmword ptr [rbp+90h+var_B8+10h], xmm1
0x1800093c7  mov     qword ptr [rbp+90h+var_B8+20h], rax
0x1800093cb  mov     [rsp+190h+instance], rax
0x1800093d0  mov     [rsp+190h+var_118], rax
0x1800093d5  mov     [rsp+190h+var_120], rax
0x1800093da  mov     [rsp+190h+var_140], rax
0x1800093df  lea     r13, WPP_GLOBAL_Control
0x1800093e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093ed  cmp     rcx, r13
0x1800093f0  jz      short loc_18000941C
0x1800093f2  test    byte ptr [rcx+1Ch], 1
0x1800093f6  jz      short loc_18000941C
0x1800093f8  cmp     qword ptr [rbx+18h], 8
0x1800093fd  jb      short loc_180009404
0x1800093ff  mov     r9, [rbx]
0x180009402  jmp     short loc_180009407
0x180009404  mov     r9, rbx
0x180009407  mov     edx, 44h ; 'D'
0x18000940c  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x180009413  mov     rcx, [rcx+10h]
0x180009417  call    WPP_SF_S
0x18000941c  lea     r9, [rbp+90h+application]; application
0x180009420  xor     r8d, r8d; extendedError
0x180009423  xor     edx, edx; applicationID
0x180009425  xor     ecx, ecx; flags
0x180009427  call    cs:__imp_MI_Application_InitializeV1
0x18000942e  nop     dword ptr [rax+rax+00h]
0x180009433  mov     ecx, eax; int
0x180009435  mov     [rsp+190h+result], eax
0x180009439  test    eax, eax
0x18000943b  jz      short loc_18000947E
0x18000943d  xor     sil, sil
0x180009440  call    ?MIResultToHRESULT@@YAJJ@Z; MIResultToHRESULT(long)
0x180009445  mov     ebx, eax
0x180009447  mov     rax, cs:WPP_GLOBAL_Control
0x18000944e  cmp     rax, r13
0x180009451  jz      loc_1800096E0
0x180009457  test    byte ptr [rax+1Ch], 4
0x18000945b  jz      loc_1800096E0
0x180009461  mov     edx, 45h ; 'E'
0x180009466  mov     r9d, ecx
0x180009469  mov     rcx, [rax+10h]
0x18000946d  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x180009474  call    WPP_SF_d
0x180009479  jmp     loc_1800096E0
0x18000947e  mov     sil, 1
0x180009481  lea     rax, [rbp+90h+var_110]
0x180009485  mov     [rsp+190h+session], rax; session
0x18000948a  lea     rcx, [rbp+90h+application]; application
0x18000948e  call    MI_Application_NewSession
0x180009493  mov     ecx, eax; int
0x180009495  mov     [rsp+190h+result], eax
0x180009499  test    eax, eax
0x18000949b  jz      short loc_1800094C5
0x18000949d  call    ?MIResultToHRESULT@@YAJJ@Z; MIResultToHRESULT(long)
0x1800094a2  mov     ebx, eax
0x1800094a4  mov     rax, cs:WPP_GLOBAL_Control
0x1800094ab  cmp     rax, r13
0x1800094ae  jz      loc_1800096E0
0x1800094b4  test    byte ptr [rax+1Ch], 4
0x1800094b8  jz      loc_1800096E0
0x1800094be  mov     edx, 46h ; 'F'
0x1800094c3  jmp     short loc_180009466
0x1800094c5  mov     r15b, sil
0x1800094c8  lea     rdx, [rbp+90h+className]
0x1800094cc  cmp     [rbp+90h+var_38], 8
0x1800094d1  cmovnb  rdx, [rbp+90h+className]; className
0x1800094d6  lea     r9, [rsp+190h+instance]; instance
0x1800094db  lea     rcx, [rbp+90h+application]; application
0x1800094df  call    MI_Application_NewInstance
0x1800094e4  mov     r9d, eax; type
0x1800094e7  mov     [rsp+190h+result], eax
0x1800094eb  test    eax, eax
0x1800094ed  jz      short loc_180009520
0x1800094ef  mov     ecx, eax; int
0x1800094f1  call    ?MIResultToHRESULT@@YAJJ@Z; MIResultToHRESULT(long)
0x1800094f6  mov     ebx, eax
0x1800094f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094ff  cmp     rcx, r13
0x180009502  jz      loc_1800096E0
0x180009508  test    byte ptr [rcx+1Ch], 4
0x18000950c  jz      loc_1800096E0
0x180009512  mov     edx, 47h ; 'G'
0x180009517  mov     rcx, [rcx+10h]
0x18000951b  jmp     loc_18000946D
0x180009520  cmp     qword ptr [rbx+18h], 8
0x180009525  jb      short loc_18000952A
0x180009527  mov     rbx, [rbx]
0x18000952a  mov     qword ptr [rbp+90h+value], rbx
0x18000952e  cmp     qword ptr [rdi+18h], 8
0x180009533  jb      short loc_180009538
0x180009535  mov     rdi, [rdi]
0x180009538  mov     qword ptr [rbp+90h+var_B8], rdi
0x18000953c  lea     rdx, [rbp+90h+name]
0x180009540  cmp     [rbp+90h+var_58], 8
0x180009545  cmovnb  rdx, [rbp+90h+name]; name
0x18000954a  lea     r8, [rbp+90h+value]; value
0x18000954e  mov     rcx, [rsp+190h+instance]; self
0x180009553  call    MI_Instance_AddElement
0x180009558  mov     ecx, eax; int
0x18000955a  mov     [rsp+190h+result], eax
0x18000955e  test    eax, eax
0x180009560  jz      short loc_18000958D
0x180009562  call    ?MIResultToHRESULT@@YAJJ@Z; MIResultToHRESULT(long)
0x180009567  mov     ebx, eax
0x180009569  mov     rax, cs:WPP_GLOBAL_Control
0x180009570  cmp     rax, r13
0x180009573  jz      loc_1800096E0
0x180009579  test    byte ptr [rax+1Ch], 4
0x18000957d  jz      loc_1800096E0
0x180009583  mov     edx, 48h ; 'H'
0x180009588  jmp     loc_180009466
0x18000958d  lea     rdx, [rbp+90h+var_90]
0x180009591  cmp     [rbp+90h+var_78], 8
0x180009596  cmovnb  rdx, [rbp+90h+var_90]; name
0x18000959b  lea     r8, [rbp+90h+var_B8]; value
0x18000959f  mov     rcx, [rsp+190h+instance]; self
0x1800095a4  call    MI_Instance_AddElement
0x1800095a9  mov     ecx, eax; int
0x1800095ab  mov     [rsp+190h+result], eax
0x1800095af  test    eax, eax
0x1800095b1  jz      short loc_1800095DE
0x1800095b3  call    ?MIResultToHRESULT@@YAJJ@Z; MIResultToHRESULT(long)
0x1800095b8  mov     ebx, eax
0x1800095ba  mov     rax, cs:WPP_GLOBAL_Control
0x1800095c1  cmp     rax, r13
0x1800095c4  jz      loc_1800096E0
0x1800095ca  test    byte ptr [rax+1Ch], 4
0x1800095ce  jz      loc_1800096E0
0x1800095d4  mov     edx, 49h ; 'I'
0x1800095d9  jmp     loc_180009466
0x1800095de  mov     rax, [rbp+90h+var_110.ft]
0x1800095e2  test    rax, rax
0x1800095e5  jz      short loc_180009624
0x1800095e7  lea     rcx, [rsp+190h+operation]
0x1800095ec  mov     [rsp+190h+session], rcx
0x1800095f1  mov     [rsp+190h+completionDetails], 0
0x1800095fa  mov     rcx, [rsp+190h+instance]
0x1800095ff  mov     [rsp+190h+errorMessage], rcx
0x180009604  lea     r9, ?c_clientConfigProviderNamespace@@3QBGB; "root\\cimv2\\mdm"
0x18000960b  xor     r8d, r8d
0x18000960e  xor     edx, edx
0x180009610  lea     rcx, [rbp+90h+var_110]
0x180009614  mov     rax, [rax+20h]
0x180009618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000961d  mov     rax, [rsp+190h+operation.ft]
0x180009622  jmp     short loc_180009633
0x180009624  xorps   xmm0, xmm0
0x180009627  xor     eax, eax
0x180009629  movups  xmmword ptr [rsp+190h+operation.reserved1], xmm0
0x18000962e  mov     [rsp+190h+operation.ft], rax
0x180009633  test    rax, rax
0x180009636  jnz     short loc_18000966C
0x180009638  mov     ebx, 80004005h
0x18000963d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009644  cmp     rcx, r13
0x180009647  jz      loc_1800096E0
0x18000964d  test    byte ptr [rcx+1Ch], 4
0x180009651  jz      loc_1800096E0
0x180009657  lea     edx, [rax+4Ah]
0x18000965a  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x180009661  mov     rcx, [rcx+10h]
0x180009665  call    WPP_SF_
0x18000966a  jmp     short loc_1800096E0
0x18000966c  mov     r14b, sil
0x18000966f  lea     rax, [rsp+190h+var_120]
0x180009674  mov     [rsp+190h+completionDetails], rax; completionDetails
0x180009679  lea     rax, [rsp+190h+var_140]
0x18000967e  mov     [rsp+190h+errorMessage], rax; errorMessage
0x180009683  lea     r9, [rsp+190h+result]; result
0x180009688  lea     r8, [rsp+190h+moreResults]; moreResults
0x18000968d  lea     rdx, [rsp+190h+var_118]; instance
0x180009692  lea     rcx, [rsp+190h+operation]; operation
0x180009697  call    MI_Operation_GetInstance
0x18000969c  mov     r9d, [rsp+190h+result]
0x1800096a1  test    r9d, r9d
0x1800096a4  jnz     short loc_1800096B1
0x1800096a6  cmp     [rsp+190h+moreResults], sil
0x1800096ab  jz      short loc_18000966F
0x1800096ad  xor     ebx, ebx
0x1800096af  jmp     short loc_1800096E0
0x1800096b1  mov     ecx, r9d; int
0x1800096b4  call    ?MIResultToHRESULT@@YAJJ@Z; MIResultToHRESULT(long)
0x1800096b9  mov     ebx, eax
0x1800096bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096c2  cmp     rcx, r13
0x1800096c5  jz      short loc_1800096E0
0x1800096c7  test    byte ptr [rcx+1Ch], 4
0x1800096cb  jz      short loc_1800096E0
0x1800096cd  mov     rax, [rsp+190h+var_140]
0x1800096d2  mov     [rsp+190h+errorMessage], rax
0x1800096d7  mov     rcx, [rcx+10h]
0x1800096db  call    WPP_SF_dS
0x1800096e0  mov     rcx, [rsp+190h+instance]; self
0x1800096e5  test    rcx, rcx
0x1800096e8  jz      short loc_1800096EF
0x1800096ea  call    MI_Instance_Delete
0x1800096ef  mov     byte ptr [rsp+190h+completionDetails], sil; bool
0x1800096f4  mov     byte ptr [rsp+190h+errorMessage], r15b; bool
0x1800096f9  mov     r9b, r14b; bool
0x1800096fc  lea     r8, [rsp+190h+operation]; struct _MI_Operation *
0x180009701  lea     rdx, [rbp+90h+var_110]; struct _MI_Session *
0x180009705  lea     rcx, [rbp+90h+application]; struct _MI_Application *
0x180009709  call    ?MISessionCleanUp@@YAXAEAU_MI_Application@@AEAU_MI_Session@@AEAU_MI_Operation@@_N33@Z; MISessionCleanUp(_MI_Application &,_MI_Session &,_MI_Operation &,bool,bool,bool)
0x18000970e  nop
0x18000970f  xor     r8d, r8d
0x180009712  mov     dl, 1
0x180009714  lea     rcx, [rbp+90h+var_90]
0x180009718  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000971d  nop
0x18000971e  xor     r8d, r8d
0x180009721  mov     dl, 1
0x180009723  lea     rcx, [rbp+90h+name]
0x180009727  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000972c  nop
0x18000972d  xor     r8d, r8d
0x180009730  mov     dl, 1
0x180009732  lea     rcx, [rbp+90h+className]
0x180009736  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000973b  mov     eax, ebx
0x18000973d  mov     rcx, [rbp+90h+var_30]
0x180009741  xor     rcx, rsp; StackCookie
0x180009744  call    __security_check_cookie
0x180009749  lea     r11, [rsp+190h+var_20]
0x180009751  mov     rbx, [r11+40h]
0x180009755  mov     rsi, [r11+48h]
0x180009759  mov     rsp, r11
0x18000975c  pop     r15
0x18000975e  pop     r14
0x180009760  pop     r13
0x180009762  pop     rdi
0x180009763  pop     rbp
0x180009764  retn
```
