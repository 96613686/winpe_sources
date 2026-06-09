# GetConfigItem(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180007edc`
- end: `0x1800083f5`
- name: `?GetConfigItem@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z`
- size: `1305`
- prototype: ``
- caller_count: `6`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004950`
- `0x180007110`
- `0x180007a3c`
- `0x180007b5c`
- `0x180007c00`
- `0x18000e0a8`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x1800065f8`
- `0x180007edc`
- `0x180008998`
- `0x180008aa8`
- `0x180008b30`
- `0x180008b6c`
- `0x18000a17c`
- `0x18000a1bc`
- `0x18000a22c`
- `0x18000a290`
- `0x18000a2c0`
- `0x18000a358`
- `0x18000a734`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `mi!MI_Application_InitializeV1` at `0x180007fb6`
- `mi!MI_Application_InitializeV1` at `0x180007fb6`

## string_xrefs

- `0x180007f45`: `MDM_ConfigSetting`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetConfigItem(MI_Uint64 *a1, __int64 a2)
{
  bool v4; // r15
  bool v5; // r12
  MI_Result v6; // eax
  const MI_Char *v7; // rdx
  const MI_Char *v8; // r8
  bool v9; // si
  unsigned int v10; // ebx
  __int64 v11; // r9
  LPCWSTR v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  MI_Result v15; // ecx
  const MI_ClassDecl *v16; // r8
  unsigned int v17; // ecx
  LPCWSTR v18; // rax
  const MI_Char *v19; // rdx
  MI_Result v20; // ecx
  MI_Type v21; // r9d
  MI_Uint64 v22; // rax
  const MI_Char *v23; // rdx
  MI_Result v24; // eax
  const MI_OperationFT *ft; // rax
  int v26; // r8d
  MI_Result v27; // eax
  LPCWSTR v28; // rcx
  MI_Uint64 v29; // r9
  _QWORD *v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  MI_Char **errorMessage; // [rsp+20h] [rbp-E0h]
  MI_Uint32 errorMessagea; // [rsp+20h] [rbp-E0h]
  MI_Instance **completionDetails; // [rsp+28h] [rbp-D8h]
  MI_Boolean moreResults[4]; // [rsp+40h] [rbp-C0h] BYREF
  MI_Result result; // [rsp+44h] [rbp-BCh] BYREF
  MI_Instance *instance; // [rsp+48h] [rbp-B8h] BYREF
  int v41; // [rsp+50h] [rbp-B0h] BYREF
  int v42; // [rsp+54h] [rbp-ACh] BYREF
  int v43; // [rsp+58h] [rbp-A8h] BYREF
  MI_Char *v44; // [rsp+60h] [rbp-A0h] BYREF
  MI_Instance *v45; // [rsp+68h] [rbp-98h] BYREF
  MI_Operation operation; // [rsp+70h] [rbp-90h] BYREF
  MI_Instance *v47; // [rsp+88h] [rbp-78h] BYREF
  MI_Session session; // [rsp+90h] [rbp-70h] BYREF
  MI_Application application; // [rsp+A8h] [rbp-58h] BYREF
  MI_Value value; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v51[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v52; // [rsp+108h] [rbp+8h]
  _QWORD v53[4]; // [rsp+110h] [rbp+10h] BYREF
  MI_Char *name[4]; // [rsp+130h] [rbp+30h] BYREF
  MI_Char *className[4]; // [rsp+150h] [rbp+50h] BYREF

  memset(&application, 0, sizeof(application));
  memset(&session, 0, sizeof(session));
  memset(&operation, 0, sizeof(operation));
  moreResults[0] = 0;
  v4 = 0;
  v5 = 0;
  std::wstring::wstring(className, L"MDM_ConfigSetting");
  std::wstring::wstring(name, L"SettingName");
  std::wstring::wstring(v53, L"SettingValue");
  memset(&value, 0, sizeof(value));
  instance = 0;
  v45 = 0;
  v47 = 0;
  v44 = 0;
  std::wstring::assign(a2, &dword_180022F6C);
  v6 = MI_Application_InitializeV1(0, 0, 0, &application);
  result = v6;
  if ( v6 )
  {
    v9 = 0;
    v10 = MIResultToHRESULT(v6);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v13 = 60;
LABEL_5:
      v14 = *((_QWORD *)v12 + 2);
LABEL_6:
      WPP_SF_d(v14, v13, &WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids, v11);
      goto LABEL_67;
    }
    goto LABEL_67;
  }
  v9 = 1;
  v15 = MI_Application_NewSession(
          &application,
          v7,
          v8,
          0,
          (MI_SessionCallbacks *)errorMessage,
          completionDetails,
          &session);
  result = v15;
  if ( v15 )
  {
    v10 = MIResultToHRESULT(v15);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_67;
    v13 = 61;
    goto LABEL_11;
  }
  v5 = 1;
  v19 = (const MI_Char *)className;
  if ( className[3] >= (MI_Char *)8 )
    v19 = className[0];
  v20 = MI_Application_NewInstance(&application, v19, v16, &instance);
  result = v20;
  if ( v20 )
  {
    v10 = MIResultToHRESULT(v20);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_67;
    v13 = 62;
LABEL_11:
    v11 = v17;
    v14 = *((_QWORD *)v18 + 2);
    goto LABEL_6;
  }
  if ( a1[3] < 8 )
    v22 = (MI_Uint64)a1;
  else
    v22 = *a1;
  value.uint64 = v22;
  v23 = (const MI_Char *)name;
  if ( name[3] >= (MI_Char *)8 )
    v23 = name[0];
  v24 = MI_Instance_AddElement(instance, v23, &value, v21, errorMessagea);
  result = v24;
  if ( v24 == MI_RESULT_OK )
  {
    if ( session.ft )
    {
      ((void (__fastcall *)(MI_Session *, _QWORD, _QWORD, const unsigned __int16 *, MI_Instance *, _QWORD, MI_Operation *))session.ft->GetInstance)(
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
    if ( !ft )
    {
      v10 = -2147467259;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids);
      goto LABEL_67;
    }
    v4 = 1;
    while ( 1 )
    {
      MI_Operation_GetInstance(
        &operation,
        (const MI_Instance **)&v45,
        moreResults,
        &result,
        (const MI_Char **)&v44,
        (const MI_Instance **)&v47);
      v27 = result;
      if ( result )
        break;
      if ( moreResults[0] != 1 )
        goto LABEL_45;
    }
    if ( result == MI_RESULT_NOT_FOUND )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        if ( a1[3] < 8 )
          LODWORD(v29) = (_DWORD)a1;
        else
          v29 = *a1;
        WPP_SF_SdS(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, v26, v29, 6, (__int64)v44);
        v27 = result;
LABEL_45:
        v28 = WPP_GLOBAL_Control;
      }
      if ( !v45 )
      {
        if ( v28 != (LPCWSTR)&WPP_GLOBAL_Control && (v28[14] & 1) != 0 )
        {
          if ( a1[3] >= 8 )
            a1 = (MI_Uint64 *)*a1;
          WPP_SF_S(*((_QWORD *)v28 + 2), 67, &WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids, a1);
        }
        v10 = 0;
        goto LABEL_67;
      }
      if ( v27 == MI_RESULT_OK )
      {
        memset(v51, 0, sizeof(v51));
        v52 = 0;
        v43 = 0;
        v42 = 0;
        v41 = 0;
        v30 = v53;
        if ( v53[3] >= 8u )
          v30 = (_QWORD *)v53[0];
        if ( v45->ft )
        {
          v27 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD *, _OWORD *, int *, int *, int *))v45->ft->GetElement)(
                  v45,
                  v30,
                  v51,
                  &v43,
                  &v42,
                  &v41);
          result = v27;
          if ( v27 == MI_RESULT_OK )
          {
            std::wstring::assign(a2, *(_QWORD *)&v51[0]);
LABEL_65:
            v27 = result;
          }
        }
        else
        {
          v27 = MI_RESULT_INVALID_PARAMETER;
          result = MI_RESULT_INVALID_PARAMETER;
        }
      }
LABEL_66:
      v10 = MIResultToHRESULT(v27);
      goto LABEL_67;
    }
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_66;
    if ( a1[3] >= 8 )
      a1 = (MI_Uint64 *)*a1;
    WPP_SF_SdS(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, (_DWORD)v44, (_DWORD)a1, result, (__int64)v44);
    goto LABEL_65;
  }
  v10 = MIResultToHRESULT(v24);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    v13 = 63;
    goto LABEL_5;
  }
LABEL_67:
  if ( instance )
    MI_Instance_Delete(instance);
  MISessionCleanUp(&application, &session, &operation, v4, v5, v9);
  LOBYTE(v31) = 1;
  std::wstring::_Tidy(v53, v31, 0);
  LOBYTE(v32) = 1;
  std::wstring::_Tidy(name, v32, 0);
  LOBYTE(v33) = 1;
  std::wstring::_Tidy(className, v33, 0);
  return v10;
}

```

## disassembly

```asm
0x180007edc  mov     [rsp-8+arg_10], rbx
0x180007ee1  push    rbp
0x180007ee2  push    rsi
0x180007ee3  push    rdi
0x180007ee4  push    r12
0x180007ee6  push    r13
0x180007ee8  push    r14
0x180007eea  push    r15
0x180007eec  lea     rbp, [rsp-80h]
0x180007ef1  sub     rsp, 180h
0x180007ef8  mov     rax, cs:__security_cookie
0x180007eff  xor     rax, rsp
0x180007f02  mov     [rbp+0B0h+var_40], rax
0x180007f06  mov     r14, rdx
0x180007f09  mov     rbx, rcx
0x180007f0c  mov     [rsp+1B0h+result], 1
0x180007f14  xor     r13d, r13d
0x180007f17  mov     [rbp+0B0h+application.reserved1], r13
0x180007f1b  xorps   xmm0, xmm0
0x180007f1e  movdqu  xmmword ptr [rbp+0B0h+application.reserved2], xmm0
0x180007f23  mov     [rbp+0B0h+var_120.reserved1], r13
0x180007f27  xorps   xmm1, xmm1
0x180007f2a  movdqu  xmmword ptr [rbp+0B0h+var_120.reserved2], xmm1
0x180007f2f  mov     [rsp+1B0h+operation.reserved1], r13
0x180007f34  movdqu  xmmword ptr [rsp+1B0h+operation.reserved2], xmm0
0x180007f3a  mov     [rsp+1B0h+moreResults], r13b
0x180007f3f  mov     r15b, r13b
0x180007f42  mov     r12b, r13b
0x180007f45  lea     rdx, aMdmConfigsetti; "MDM_ConfigSetting"
0x180007f4c  lea     rcx, [rbp+0B0h+className]
0x180007f50  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180007f55  nop
0x180007f56  lea     rdx, aSettingname; "SettingName"
0x180007f5d  lea     rcx, [rbp+0B0h+name]
0x180007f61  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180007f66  nop
0x180007f67  lea     rdx, aSettingvalue; "SettingValue"
0x180007f6e  lea     rcx, [rbp+0B0h+var_A0]
0x180007f72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180007f77  nop
0x180007f78  xorps   xmm0, xmm0
0x180007f7b  xor     eax, eax
0x180007f7d  movups  xmmword ptr [rbp+0B0h+value], xmm0
0x180007f81  movups  xmmword ptr [rbp+0B0h+value+10h], xmm0
0x180007f85  mov     qword ptr [rbp+0B0h+value+20h], rax
0x180007f89  mov     [rsp+1B0h+instance], r13
0x180007f8e  mov     [rsp+1B0h+var_148], r13
0x180007f93  mov     [rbp+0B0h+var_128], r13
0x180007f97  mov     [rsp+1B0h+var_150], r13
0x180007f9c  lea     rdx, dword_180022F6C
0x180007fa3  mov     rcx, r14
0x180007fa6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180007fab  lea     r9, [rbp+0B0h+application]; application
0x180007faf  xor     r8d, r8d; extendedError
0x180007fb2  xor     edx, edx; applicationID
0x180007fb4  xor     ecx, ecx; flags
0x180007fb6  call    cs:__imp_MI_Application_InitializeV1
0x180007fbd  nop     dword ptr [rax+rax+00h]
0x180007fc2  mov     r9d, eax; options
0x180007fc5  mov     [rsp+1B0h+result], eax
0x180007fc9  test    eax, eax
0x180007fcb  jz      short loc_180008013
0x180007fcd  mov     sil, r13b
0x180007fd0  mov     ecx, eax; int
0x180007fd2  call    ?MIResultToHRESULT@@YAJJ@Z; MIResultToHRESULT(long)
0x180007fd7  mov     ebx, eax
0x180007fd9  lea     rdi, WPP_GLOBAL_Control
0x180007fe0  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fe7  cmp     rcx, rdi
0x180007fea  jz      loc_180008370
0x180007ff0  test    byte ptr [rcx+1Ch], 4
0x180007ff4  jz      loc_180008370
0x180007ffa  lea     edx, [r13+3Ch]
0x180007ffe  mov     rcx, [rcx+10h]
0x180008002  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x180008009  call    WPP_SF_d
0x18000800e  jmp     loc_180008370
0x180008013  mov     sil, 1
0x180008016  lea     rax, [rbp+0B0h+var_120]
0x18000801a  mov     [rsp+1B0h+session], rax; session
0x18000801f  lea     rcx, [rbp+0B0h+application]; application
0x180008023  call    MI_Application_NewSession
0x180008028  mov     ecx, eax; int
0x18000802a  mov     [rsp+1B0h+result], eax
0x18000802e  test    eax, eax
0x180008030  jz      short loc_180008068
0x180008032  call    ?MIResultToHRESULT@@YAJJ@Z; MIResultToHRESULT(long)
0x180008037  mov     ebx, eax
0x180008039  lea     rdi, WPP_GLOBAL_Control
0x180008040  mov     rax, cs:WPP_GLOBAL_Control
0x180008047  cmp     rax, rdi
0x18000804a  jz      loc_180008370
0x180008050  test    byte ptr [rax+1Ch], 4
0x180008054  jz      loc_180008370
0x18000805a  mov     edx, 3Dh ; '='
0x18000805f  mov     r9d, ecx
0x180008062  mov     rcx, [rax+10h]
0x180008066  jmp     short loc_180008002
0x180008068  mov     r12b, sil
0x18000806b  lea     rdx, [rbp+0B0h+className]
0x18000806f  cmp     [rbp+0B0h+var_48], 8
0x180008074  cmovnb  rdx, [rbp+0B0h+className]; className
0x180008079  lea     r9, [rsp+1B0h+instance]; instance
0x18000807e  lea     rcx, [rbp+0B0h+application]; application
0x180008082  call    MI_Application_NewInstance
0x180008087  mov     ecx, eax; int
0x180008089  mov     [rsp+1B0h+result], eax
0x18000808d  test    eax, eax
0x18000808f  jz      short loc_1800080C0
0x180008091  call    ?MIResultToHRESULT@@YAJJ@Z; MIResultToHRESULT(long)
0x180008096  mov     ebx, eax
0x180008098  lea     rdi, WPP_GLOBAL_Control
0x18000809f  mov     rax, cs:WPP_GLOBAL_Control
0x1800080a6  cmp     rax, rdi
0x1800080a9  jz      loc_180008370
0x1800080af  test    byte ptr [rax+1Ch], 4
0x1800080b3  jz      loc_180008370
0x1800080b9  mov     edx, 3Eh ; '>'
0x1800080be  jmp     short loc_18000805F
0x1800080c0  cmp     qword ptr [rbx+18h], 8
0x1800080c5  jb      short loc_1800080CC
0x1800080c7  mov     rax, [rbx]
0x1800080ca  jmp     short loc_1800080CF
0x1800080cc  mov     rax, rbx
0x1800080cf  mov     qword ptr [rbp+0B0h+value], rax
0x1800080d3  lea     rdx, [rbp+0B0h+name]
0x1800080d7  cmp     [rbp+0B0h+var_68], 8
0x1800080dc  cmovnb  rdx, [rbp+0B0h+name]; name
0x1800080e1  lea     r8, [rbp+0B0h+value]; value
0x1800080e5  mov     rcx, [rsp+1B0h+instance]; self
0x1800080ea  call    MI_Instance_AddElement
0x1800080ef  mov     r9d, eax
0x1800080f2  mov     [rsp+1B0h+result], eax
0x1800080f6  test    eax, eax
0x1800080f8  jz      short loc_18000812E
0x1800080fa  mov     ecx, eax; int
0x1800080fc  call    ?MIResultToHRESULT@@YAJJ@Z; MIResultToHRESULT(long)
0x180008101  mov     ebx, eax
0x180008103  lea     rdi, WPP_GLOBAL_Control
0x18000810a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008111  cmp     rcx, rdi
0x180008114  jz      loc_180008370
0x18000811a  test    byte ptr [rcx+1Ch], 4
0x18000811e  jz      loc_180008370
0x180008124  mov     edx, 3Fh ; '?'
0x180008129  jmp     loc_180007FFE
0x18000812e  mov     rax, [rbp+0B0h+var_120.ft]
0x180008132  test    rax, rax
0x180008135  jz      short loc_18000816F
0x180008137  lea     rcx, [rsp+1B0h+operation]
0x18000813c  mov     [rsp+1B0h+session], rcx
0x180008141  mov     [rsp+1B0h+completionDetails], r13
0x180008146  mov     rcx, [rsp+1B0h+instance]
0x18000814b  mov     [rsp+1B0h+errorMessage], rcx
0x180008150  lea     r9, ?c_clientConfigProviderNamespace@@3QBGB; "root\\cimv2\\mdm"
0x180008157  xor     r8d, r8d
0x18000815a  xor     edx, edx
0x18000815c  lea     rcx, [rbp+0B0h+var_120]
0x180008160  mov     rax, [rax+10h]
0x180008164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008169  mov     rax, [rbp+0B0h+operation.ft]
0x18000816d  jmp     short loc_18000817D
0x18000816f  xorps   xmm0, xmm0
0x180008172  xor     eax, eax
0x180008174  movups  xmmword ptr [rsp+1B0h+operation.reserved1], xmm0
0x180008179  mov     [rbp+0B0h+operation.ft], rax
0x18000817d  test    rax, rax
0x180008180  jnz     short loc_1800081C0
0x180008182  mov     ebx, 80004005h
0x180008187  lea     rdi, WPP_GLOBAL_Control
0x18000818e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008195  cmp     rcx, rdi
0x180008198  jz      loc_180008370
0x18000819e  test    byte ptr [rcx+1Ch], 4
0x1800081a2  jz      loc_180008370
0x1800081a8  lea     edx, [rax+40h]
0x1800081ab  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x1800081b2  mov     rcx, [rcx+10h]
0x1800081b6  call    WPP_SF_
0x1800081bb  jmp     loc_180008370
0x1800081c0  mov     r15b, sil
0x1800081c3  lea     rax, [rbp+0B0h+var_128]
0x1800081c7  mov     [rsp+1B0h+completionDetails], rax; completionDetails
0x1800081cc  lea     rax, [rsp+1B0h+var_150]
0x1800081d1  mov     [rsp+1B0h+errorMessage], rax; errorMessage
0x1800081d6  lea     r9, [rsp+1B0h+result]; result
0x1800081db  lea     r8, [rsp+1B0h+moreResults]; moreResults
0x1800081e0  lea     rdx, [rsp+1B0h+var_148]; instance
0x1800081e5  lea     rcx, [rsp+1B0h+operation]; operation
0x1800081ea  call    MI_Operation_GetInstance
0x1800081ef  lea     rdi, WPP_GLOBAL_Control
0x1800081f6  mov     eax, [rsp+1B0h+result]
0x1800081fa  test    eax, eax
0x1800081fc  jnz     short loc_180008207
0x1800081fe  cmp     [rsp+1B0h+moreResults], sil
0x180008203  jz      short loc_1800081C3
0x180008205  jmp     short loc_180008255
0x180008207  cmp     eax, 6
0x18000820a  jnz     loc_180008328
0x180008210  mov     rcx, cs:WPP_GLOBAL_Control
0x180008217  cmp     rcx, rdi
0x18000821a  jz      short loc_18000825C
0x18000821c  test    byte ptr [rcx+1Ch], 2
0x180008220  jz      short loc_18000825C
0x180008222  mov     rax, [rsp+1B0h+var_150]
0x180008227  cmp     qword ptr [rbx+18h], 8
0x18000822c  jb      short loc_180008233
0x18000822e  mov     r9, [rbx]
0x180008231  jmp     short loc_180008236
0x180008233  mov     r9, rbx
0x180008236  mov     edx, 41h ; 'A'
0x18000823b  mov     [rsp+1B0h+completionDetails], rax
0x180008240  mov     dword ptr [rsp+1B0h+errorMessage], 6
0x180008248  mov     rcx, [rcx+10h]
0x18000824c  call    WPP_SF_SdS
0x180008251  mov     eax, [rsp+1B0h+result]
0x180008255  mov     rcx, cs:WPP_GLOBAL_Control
0x18000825c  mov     r10, [rsp+1B0h+var_148]
0x180008261  test    r10, r10
0x180008264  jnz     short loc_18000829B
0x180008266  cmp     rcx, rdi
0x180008269  jz      short loc_180008293
0x18000826b  test    [rcx+1Ch], sil
0x18000826f  jz      short loc_180008293
0x180008271  cmp     qword ptr [rbx+18h], 8
0x180008276  jb      short loc_18000827B
0x180008278  mov     rbx, [rbx]
0x18000827b  mov     edx, 43h ; 'C'
0x180008280  mov     r9, rbx
0x180008283  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x18000828a  mov     rcx, [rcx+10h]
0x18000828e  call    WPP_SF_S
0x180008293  mov     ebx, r13d
0x180008296  jmp     loc_180008370
0x18000829b  test    eax, eax
0x18000829d  jnz     loc_180008367
0x1800082a3  xorps   xmm0, xmm0
0x1800082a6  xor     eax, eax
0x1800082a8  movups  [rbp+0B0h+var_C8], xmm0
0x1800082ac  movups  [rbp+0B0h+var_B8], xmm0
0x1800082b0  mov     [rbp+0B0h+var_A8], rax
0x1800082b4  mov     [rsp+1B0h+var_158], r13d
0x1800082b9  mov     [rsp+1B0h+var_15C], r13d
0x1800082be  mov     [rsp+1B0h+var_160], r13d
0x1800082c3  lea     rdx, [rbp+0B0h+var_A0]
0x1800082c7  cmp     [rbp+0B0h+var_88], 8
0x1800082cc  cmovnb  rdx, [rbp+0B0h+var_A0]
0x1800082d1  test    r10, r10
0x1800082d4  jz      short loc_18000831D
0x1800082d6  mov     rax, [r10]
0x1800082d9  test    rax, rax
0x1800082dc  jz      short loc_18000831D
0x1800082de  lea     rcx, [rsp+1B0h+var_160]
0x1800082e3  mov     [rsp+1B0h+completionDetails], rcx
0x1800082e8  lea     rcx, [rsp+1B0h+var_15C]
0x1800082ed  mov     [rsp+1B0h+errorMessage], rcx
0x1800082f2  lea     r9, [rsp+1B0h+var_158]
0x1800082f7  lea     r8, [rbp+0B0h+var_C8]
0x1800082fb  mov     rcx, r10
0x1800082fe  mov     rax, [rax+58h]
0x180008302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008307  mov     [rsp+1B0h+result], eax
0x18000830b  test    eax, eax
0x18000830d  jnz     short loc_180008367
0x18000830f  mov     rdx, qword ptr [rbp+0B0h+var_C8]
0x180008313  mov     rcx, r14
0x180008316  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000831b  jmp     short loc_180008363
0x18000831d  mov     eax, 4
0x180008322  mov     [rsp+1B0h+result], eax
0x180008326  jmp     short loc_180008367
0x180008328  mov     rcx, cs:WPP_GLOBAL_Control
0x18000832f  cmp     rcx, rdi
0x180008332  jz      short loc_180008367
0x180008334  test    byte ptr [rcx+1Ch], 4
0x180008338  jz      short loc_180008367
0x18000833a  mov     r8, [rsp+1B0h+var_150]
0x18000833f  cmp     qword ptr [rbx+18h], 8
0x180008344  jb      short loc_180008349
0x180008346  mov     rbx, [rbx]
0x180008349  mov     edx, 42h ; 'B'
0x18000834e  mov     [rsp+1B0h+completionDetails], r8
0x180008353  mov     dword ptr [rsp+1B0h+errorMessage], eax
0x180008357  mov     r9, rbx
0x18000835a  mov     rcx, [rcx+10h]
0x18000835e  call    WPP_SF_SdS
0x180008363  mov     eax, [rsp+1B0h+result]
0x180008367  mov     ecx, eax; int
0x180008369  call    ?MIResultToHRESULT@@YAJJ@Z; MIResultToHRESULT(long)
0x18000836e  mov     ebx, eax
0x180008370  mov     rcx, [rsp+1B0h+instance]; self
0x180008375  test    rcx, rcx
0x180008378  jz      short loc_18000837F
0x18000837a  call    MI_Instance_Delete
0x18000837f  mov     byte ptr [rsp+1B0h+completionDetails], sil; bool
0x180008384  mov     byte ptr [rsp+1B0h+errorMessage], r12b; bool
0x180008389  mov     r9b, r15b; bool
0x18000838c  lea     r8, [rsp+1B0h+operation]; struct _MI_Operation *
0x180008391  lea     rdx, [rbp+0B0h+var_120]; struct _MI_Session *
0x180008395  lea     rcx, [rbp+0B0h+application]; struct _MI_Application *
  ... truncated ...
```
