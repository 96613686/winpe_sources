# CDlpManager::Deserialize(void)

- ea: `0x1400323e4`
- end: `0x1400332a3`
- name: `?Deserialize@CDlpManager@@AEAAJXZ`
- size: `3775`
- prototype: `__int64 __fastcall(CDlpManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140040e70`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x14002bc70`
- `0x14002bd40`
- `0x14002c158`
- `0x14002c250`
- `0x14002f83c`
- `0x1400323e4`
- `0x140034ab4`
- `0x140040184`
- `0x14004c024`
- `0x140082010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140033210`
- `KERNEL32!HeapFree` at `0x140033210`
- `KERNEL32!GetProcessHeap` at `0x1400331fb`
- `KERNEL32!GetProcessHeap` at `0x1400331fb`
- `KERNEL32!LeaveCriticalSection` at `0x14003322e`
- `KERNEL32!LeaveCriticalSection` at `0x14003322e`
- `KERNEL32!EnterCriticalSection` at `0x140032410`
- `KERNEL32!EnterCriticalSection` at `0x140032410`
- `OLEAUT32!__imp_SysFreeString` at `0x140032747`
- `OLEAUT32!__imp_SysFreeString` at `0x140032789`
- `OLEAUT32!__imp_SysFreeString` at `0x14003285b`
- `OLEAUT32!__imp_SysFreeString` at `0x140032954`
- `OLEAUT32!__imp_SysFreeString` at `0x1400331cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1400331e6`
- `OLEAUT32!__imp_SysFreeString` at `0x140032747`
- `OLEAUT32!__imp_SysFreeString` at `0x140032789`
- `OLEAUT32!__imp_SysFreeString` at `0x14003285b`
- `OLEAUT32!__imp_SysFreeString` at `0x140032954`
- `OLEAUT32!__imp_SysFreeString` at `0x1400331cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1400331e6`

## string_xrefs

- `0x140032506`: `CDlpManager::Deserialize`
- `0x1400330db`: `CDlpManager::Deserialize`
- `0x140032547`: `TaskCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpManager::Deserialize(CDlpManager *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // r15
  unsigned __int16 *v3; // r14
  __int64 v4; // rcx
  int XmlFilePaths; // edi
  __int64 v6; // rcx
  __int64 v7; // rax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // esi
  unsigned int v11; // esi
  unsigned int v12; // esi
  unsigned int v13; // esi
  int v14; // eax
  unsigned __int16 **v15; // r8
  __int64 v16; // rax
  unsigned int v17; // ebx
  int v18; // eax
  int v19; // eax
  HANDLE ProcessHeap; // rax
  int v22; // [rsp+20h] [rbp-59h]
  int v23; // [rsp+28h] [rbp-51h]
  _QWORD *v24; // [rsp+30h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-41h] BYREF
  __int64 v26; // [rsp+40h] [rbp-39h] BYREF
  BSTR v27; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v28; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v29; // [rsp+54h] [rbp-25h] BYREF
  unsigned __int16 *v30; // [rsp+58h] [rbp-21h] BYREF
  struct CDlpTask *v31; // [rsp+60h] [rbp-19h] BYREF
  __int64 v32; // [rsp+68h] [rbp-11h] BYREF
  _QWORD v33[4]; // [rsp+70h] [rbp-9h] BYREF
  int v34; // [rsp+90h] [rbp+17h]
  unsigned int v35; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v36; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v37; // [rsp+F0h] [rbp+77h] BYREF
  unsigned int v38; // [rsp+F8h] [rbp+7Fh] BYREF

  v33[1] = -2;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 312);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  v34 = 1;
  v3 = 0;
  v30 = 0;
  bstrString = 0;
  v27 = 0;
  v32 = 0;
  v26 = 0;
  v24 = 0;
  v31 = 0;
  v38 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v28 = 0;
  v33[0] = 0;
  v29 = 0;
  v4 = *((_QWORD *)this + 83);
  if ( !v4 )
  {
    XmlFilePaths = 0;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
      goto LABEL_147;
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
    v6 = 0;
    goto LABEL_4;
  }
  XmlFilePaths = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, unsigned int *))(v4 + 8))(
                   v4 + 8,
                   L"State",
                   &v29);
  if ( XmlFilePaths >= 0 )
  {
    XmlFilePaths = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, unsigned int *))(*((_QWORD *)this + 83) + 8LL))(
                     *((_QWORD *)this + 83) + 8LL,
                     L"TaskCount",
                     &v38);
    if ( XmlFilePaths < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_147;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v8 = 0;
      if ( !v7 )
        goto LABEL_11;
      v23 = XmlFilePaths;
      v22 = 2376;
      goto LABEL_9;
    }
    XmlFilePaths = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, unsigned int *))(*((_QWORD *)this + 83) + 8LL))(
                     *((_QWORD *)this + 83) + 8LL,
                     L"StringCount",
                     &v35);
    if ( XmlFilePaths < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_147;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v8 = 0;
      if ( !v7 )
        goto LABEL_11;
      v23 = XmlFilePaths;
      v22 = 2379;
      goto LABEL_9;
    }
    XmlFilePaths = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, unsigned int *))(*((_QWORD *)this + 83) + 8LL))(
                     *((_QWORD *)this + 83) + 8LL,
                     L"DwordCount",
                     &v36);
    if ( XmlFilePaths < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_147;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v8 = 0;
      if ( !v7 )
        goto LABEL_11;
      v23 = XmlFilePaths;
      v22 = 2382;
      goto LABEL_9;
    }
    XmlFilePaths = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, unsigned int *))(*((_QWORD *)this + 83) + 8LL))(
                     *((_QWORD *)this + 83) + 8LL,
                     L"QuadwordCount",
                     &v37);
    if ( XmlFilePaths < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_147;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v8 = 0;
      if ( !v7 )
        goto LABEL_11;
      v23 = XmlFilePaths;
      v22 = 2385;
      goto LABEL_9;
    }
    v10 = 0;
    if ( v35 )
    {
      while ( 1 )
      {
        if ( v24 )
        {
          (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
          v24 = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, _QWORD **))(**((_QWORD **)this + 83)
                                                                                             + 32LL))(
                         *((_QWORD *)this + 83),
                         L"StringProperty",
                         v10,
                         &v24);
        if ( XmlFilePaths < 0 )
          break;
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, BSTR *))(v24[1] + 16LL))(
                         v24 + 1,
                         L"Name",
                         &bstrString);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_147;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v8 = 0;
          if ( v7 )
          {
            v23 = XmlFilePaths;
            v22 = 2395;
            goto LABEL_9;
          }
          goto LABEL_11;
        }
        if ( v27 )
        {
          SysFreeString(v27);
          v27 = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, BSTR *))(v24[1] + 16LL))(
                         v24 + 1,
                         L"Value",
                         &v27);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_147;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v8 = 0;
          if ( v7 )
          {
            v23 = XmlFilePaths;
            v22 = 2398;
            goto LABEL_9;
          }
          goto LABEL_11;
        }
        XmlFilePaths = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 544, &bstrString);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_147;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v8 = 0;
          if ( v7 )
          {
            v23 = XmlFilePaths;
            v22 = 2402;
            goto LABEL_9;
          }
          goto LABEL_11;
        }
        XmlFilePaths = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 560, &v27);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_147;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v8 = 0;
          if ( v7 )
          {
            v23 = XmlFilePaths;
            v22 = 2403;
            goto LABEL_9;
          }
          goto LABEL_11;
        }
        if ( ++v10 >= v35 )
          goto LABEL_41;
      }
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_147;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v8 = 0;
      if ( v7 )
      {
        v23 = XmlFilePaths;
        v22 = 2392;
        goto LABEL_9;
      }
      goto LABEL_11;
    }
LABEL_41:
    v11 = 0;
    if ( v36 )
    {
      while ( 1 )
      {
        if ( v24 )
        {
          (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
          v24 = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, _QWORD **))(**((_QWORD **)this + 83)
                                                                                             + 32LL))(
                         *((_QWORD *)this + 83),
                         L"DwordProperty",
                         v11,
                         &v24);
        if ( XmlFilePaths < 0 )
          break;
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, BSTR *))(v24[1] + 16LL))(
                         v24 + 1,
                         L"Name",
                         &bstrString);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_147;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v8 = 0;
          if ( v7 )
          {
            v23 = XmlFilePaths;
            v22 = 2414;
            goto LABEL_9;
          }
          goto LABEL_11;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, unsigned int *))v24[1])(
                         v24 + 1,
                         L"Value",
                         &v28);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_147;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v8 = 0;
          if ( v7 )
          {
            v23 = XmlFilePaths;
            v22 = 2416;
            goto LABEL_9;
          }
          goto LABEL_11;
        }
        XmlFilePaths = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 576, &bstrString);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_147;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v8 = 0;
          if ( v7 )
          {
            v23 = XmlFilePaths;
            v22 = 2420;
            goto LABEL_9;
          }
          goto LABEL_11;
        }
        XmlFilePaths = CArray<unsigned long,unsigned long,CAdaptorDefault,CPoliciesDefault>::Append(
                         (char *)this + 592,
                         v28);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_147;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v8 = 0;
          if ( v7 )
          {
            v23 = XmlFilePaths;
            v22 = 2421;
            goto LABEL_9;
          }
          goto LABEL_11;
        }
        if ( ++v11 >= v36 )
          goto LABEL_52;
      }
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_147;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v8 = 0;
      if ( v7 )
      {
        v23 = XmlFilePaths;
        v22 = 2411;
        goto LABEL_9;
      }
      goto LABEL_11;
    }
LABEL_52:
    v12 = 0;
    if ( v37 )
    {
      while ( 1 )
      {
        if ( v24 )
        {
          (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
          v24 = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, _QWORD **))(**((_QWORD **)this + 83)
                                                                                             + 32LL))(
                         *((_QWORD *)this + 83),
                         L"QuadwordProperty",
                         v12,
                         &v24);
        if ( XmlFilePaths < 0 )
          break;
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, BSTR *))(v24[1] + 16LL))(
                         v24 + 1,
                         L"Name",
                         &bstrString);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_147;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v8 = 0;
          if ( v7 )
          {
            v23 = XmlFilePaths;
            v22 = 2432;
            goto LABEL_9;
          }
          goto LABEL_11;
        }
        XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD *))(v24[1] + 8LL))(
                         v24 + 1,
                         L"Value",
                         v33);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_147;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v8 = 0;
          if ( v7 )
          {
            v23 = XmlFilePaths;
            v22 = 2434;
            goto LABEL_9;
          }
          goto LABEL_11;
        }
        XmlFilePaths = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 608, &bstrString);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_147;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v8 = 0;
          if ( v7 )
          {
            v23 = XmlFilePaths;
            v22 = 2438;
            goto LABEL_9;
          }
          goto LABEL_11;
        }
        XmlFilePaths = CArray<unsigned __int64,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::Append(
                         (char *)this + 624,
                         v33[0]);
        if ( XmlFilePaths < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
            goto LABEL_147;
          v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v8 = 0;
          if ( v7 )
          {
            v23 = XmlFilePaths;
            v22 = 2439;
            goto LABEL_9;
          }
          goto LABEL_11;
        }
        if ( ++v12 >= v37 )
          goto LABEL_63;
      }
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_147;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v8 = 0;
      if ( v7 )
      {
        v23 = XmlFilePaths;
        v22 = 2429;
        goto LABEL_9;
      }
      goto LABEL_11;
    }
LABEL_63:
    if ( (*((_BYTE *)this + 856) & 4) == 0 )
    {
      v13 = 0;
      if ( v38 )
      {
        while ( 1 )
        {
          if ( v26 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
            v26 = 0;
          }
          XmlFilePaths = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, __int64 *))(**((_QWORD **)this + 83)
                                                                                               + 32LL))(
                           *((_QWORD *)this + 83),
                           L"TASK",
                           v13,
                           &v26);
          if ( XmlFilePaths < 0 )
            break;
          XmlFilePaths = CDlpTask::CreateInstance(this, v13, &v31);
          if ( XmlFilePaths < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
              goto LABEL_147;
            v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
            v8 = 0;
            if ( v7 )
            {
              v23 = XmlFilePaths;
              v22 = 2453;
              goto LABEL_9;
            }
            goto LABEL_11;
          }
          XmlFilePaths = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)v31 + 1) + 8LL))((char *)v31 + 8, v26);
          if ( XmlFilePaths < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
              goto LABEL_147;
            v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
            v8 = 0;
            if ( v7 )
            {
              v23 = XmlFilePaths;
              v22 = 2457;
              goto LABEL_9;
            }
            goto LABEL_11;
          }
          XmlFilePaths = CArray<DP_COM<IUnknown>,DP_COM<IUnknown>,CAdaptorDefault,CPoliciesDefault>::Append(
                           (__int64)this + 528,
                           (__int64 *)&v31);
          if ( XmlFilePaths < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
              goto LABEL_147;
            v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
            v8 = 0;
            if ( v7 )
            {
              v23 = XmlFilePaths;
              v22 = 2461;
              goto LABEL_9;
            }
            goto LABEL_11;
          }
          if ( ++v13 >= v38 )
            goto LABEL_72;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
          goto LABEL_147;
        v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
        v8 = 0;
        if ( v7 )
        {
          v23 = XmlFilePaths;
          v22 = 2449;
          goto LABEL_9;
        }
        goto LABEL_11;
      }
    }
LABEL_72:
    v14 = CDlpState::Set((char *)this + 128, v29);
    XmlFilePaths = v14;
    if ( v14 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)XmlFilePaths);
    if ( XmlFilePaths < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_147;
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v8 = 0;
      if ( !v7 )
        goto LABEL_11;
      v23 = XmlFilePaths;
      v22 = 2465;
      goto LABEL_9;
    }
    if ( *((_DWORD *)this + 215) )
      goto LABEL_147;
    XmlFilePaths = CDlpStateXml::GetXmlFilePaths(*((CDlpStateXml **)this + 83), &v30, v15);
    if ( XmlFilePaths < 0 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
      {
        v16 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
        v17 = 0;
        if ( v16 )
        {
          v18 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v16,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDlpManager::Deserialize",
                  2472,
                  XmlFilePaths);
          v17 = v18;
          if ( v18 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v18);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v17);
      }
      v3 = v30;
      goto LABEL_147;
    }
    v19 = (*(__int64 (__fastcall **)(CDlpManager *, __int64 *))(*(_QWORD *)this + 152LL))(this, &v32);
    v3 = v30;
    if ( v19 >= 0 )
    {
      XmlFilePaths = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v32 + 40LL))(v32, v30);
      if ( XmlFilePaths == -2147467263 )
      {
        XmlFilePaths = 1;
      }
      else if ( XmlFilePaths < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
          goto LABEL_147;
        v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
        v8 = 0;
        if ( !v7 )
          goto LABEL_11;
        v23 = XmlFilePaths;
        v22 = 2475;
LABEL_9:
        v9 = CDlpLogT<CEmptyType>::DlpLogFormat(v7, 4, L"%s(%d): Result = 0x%X", L"CDlpManager::Deserialize", v22, v23);
        v8 = v9;
        if ( v9 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
        goto LABEL_11;
      }
    }
    *((_DWORD *)this + 215) = 1;
    goto LABEL_147;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
  {
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
    v8 = 0;
    if ( v7 )
    {
      v23 = XmlFilePaths;
      v22 = 2373;
      goto LABEL_9;
    }
LABEL_11:
    v6 = v8;
LABEL_4:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  }
LABEL_147:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)XmlFilePaths);
  if ( v31 )
    (*(void (__fastcall **)(struct CDlpTask *))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v24 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v27 )
  {
    SysFreeString(v27);
    v27 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v34 )
  {
    LeaveCriticalSection(v2);
    v34 = 0;
  }
  return (unsigned int)XmlFilePaths;
}

```

## disassembly

```asm
0x1400323e4  push    rbp
0x1400323e6  push    rbx
0x1400323e7  push    rsi
0x1400323e8  push    rdi
0x1400323e9  push    r12
0x1400323eb  push    r14
0x1400323ed  push    r15
0x1400323ef  lea     rbp, [rsp-27h]
0x1400323f4  sub     rsp, 0A0h
0x1400323fb  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x140032403  mov     rbx, rcx
0x140032406  lea     r15, [rcx+138h]
0x14003240d  mov     rcx, r15; lpCriticalSection
0x140032410  call    cs:__imp_EnterCriticalSection
0x140032417  nop     dword ptr [rax+rax+00h]
0x14003241c  mov     [rbp+57h+var_40], 1
0x140032423  xor     r12d, r12d
0x140032426  mov     r14d, r12d
0x140032429  mov     [rbp+57h+var_78], r12
0x14003242d  mov     [rbp+57h+bstrString], r12
0x140032431  mov     [rbp+57h+var_88], r12
0x140032435  mov     [rbp+57h+var_68], r12
0x140032439  mov     [rbp+57h+var_90], r12
0x14003243d  mov     [rbp+57h+var_A0], r12
0x140032441  mov     [rbp+57h+var_70], r12
0x140032445  mov     [rbp+57h+arg_18], r12d
0x140032449  mov     [rbp+57h+arg_0], r12d
0x14003244d  mov     [rbp+57h+arg_8], r12d
0x140032451  mov     [rbp+57h+arg_10], r12d
0x140032455  mov     [rbp+57h+var_80], r12d
0x140032459  mov     [rbp+57h+var_60], r12
0x14003245d  mov     [rbp+57h+var_7C], r12d
0x140032461  mov     rcx, [rbx+298h]
0x140032468  test    rcx, rcx
0x14003246b  jnz     short loc_1400324A7
0x14003246d  mov     edi, r12d
0x140032470  mov     rax, [rbx+50h]
0x140032474  lea     rcx, [rbx+50h]
0x140032478  mov     rax, [rax+10h]
0x14003247c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032481  test    rax, rax
0x140032484  jz      loc_14003315D
0x14003248a  mov     rax, [rbx+50h]
0x14003248e  lea     rcx, [rbx+50h]
0x140032492  mov     rax, [rax+10h]
0x140032496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003249b  xor     ecx, ecx
0x14003249d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400324a2  jmp     loc_14003315D
0x1400324a7  add     rcx, 8
0x1400324ab  mov     rax, [rcx]
0x1400324ae  lea     r8, [rbp+57h+var_7C]
0x1400324b2  lea     rdx, aState; "State"
0x1400324b9  mov     rax, [rax]
0x1400324bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400324c1  mov     edi, eax
0x1400324c3  test    eax, eax
0x1400324c5  jns     short loc_140032535
0x1400324c7  mov     rdx, [rbx+50h]
0x1400324cb  lea     rcx, [rbx+50h]
0x1400324cf  mov     rax, [rdx+10h]
0x1400324d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400324d8  test    rax, rax
0x1400324db  jz      loc_14003315D
0x1400324e1  mov     rax, [rbx+50h]
0x1400324e5  lea     rcx, [rbx+50h]
0x1400324e9  mov     rax, [rax+10h]
0x1400324ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400324f2  mov     ebx, r12d
0x1400324f5  test    rax, rax
0x1400324f8  jz      short loc_14003252E
0x1400324fa  mov     [rsp+0D0h+var_A8], edi
0x1400324fe  mov     [rsp+0D0h+var_B0], 945h
0x140032506  lea     r9, aCdlpmanagerDes; "CDlpManager::Deserialize"
0x14003250d  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x140032514  mov     edx, 4
0x140032519  mov     rcx, rax
0x14003251c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x140032521  mov     ebx, eax
0x140032523  test    eax, eax
0x140032525  jns     short loc_14003252E
0x140032527  mov     ecx, eax
0x140032529  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14003252e  mov     ecx, ebx
0x140032530  jmp     loc_14003249D
0x140032535  mov     rcx, [rbx+298h]
0x14003253c  add     rcx, 8
0x140032540  mov     rax, [rcx]
0x140032543  lea     r8, [rbp+57h+arg_18]
0x140032547  lea     rdx, aTaskcount; "TaskCount"
0x14003254e  mov     rax, [rax]
0x140032551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032556  mov     edi, eax
0x140032558  test    eax, eax
0x14003255a  jns     short loc_1400325A0
0x14003255c  mov     rax, [rbx+50h]
0x140032560  lea     rcx, [rbx+50h]
0x140032564  mov     rax, [rax+10h]
0x140032568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003256d  test    rax, rax
0x140032570  jz      loc_14003315D
0x140032576  mov     rax, [rbx+50h]
0x14003257a  lea     rcx, [rbx+50h]
0x14003257e  mov     rax, [rax+10h]
0x140032582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032587  mov     ebx, r12d
0x14003258a  test    rax, rax
0x14003258d  jz      short loc_14003252E
0x14003258f  mov     [rsp+0D0h+var_A8], edi
0x140032593  mov     [rsp+0D0h+var_B0], 948h
0x14003259b  jmp     loc_140032506
0x1400325a0  mov     rcx, [rbx+298h]
0x1400325a7  add     rcx, 8
0x1400325ab  mov     rax, [rcx]
0x1400325ae  lea     r8, [rbp+57h+arg_0]
0x1400325b2  lea     rdx, aStringcount; "StringCount"
0x1400325b9  mov     rax, [rax]
0x1400325bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400325c1  mov     edi, eax
0x1400325c3  test    eax, eax
0x1400325c5  jns     short loc_14003260F
0x1400325c7  mov     rax, [rbx+50h]
0x1400325cb  lea     rcx, [rbx+50h]
0x1400325cf  mov     rax, [rax+10h]
0x1400325d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400325d8  test    rax, rax
0x1400325db  jz      loc_14003315D
0x1400325e1  mov     rax, [rbx+50h]
0x1400325e5  lea     rcx, [rbx+50h]
0x1400325e9  mov     rax, [rax+10h]
0x1400325ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400325f2  mov     ebx, r12d
0x1400325f5  test    rax, rax
0x1400325f8  jz      loc_14003252E
0x1400325fe  mov     [rsp+0D0h+var_A8], edi
0x140032602  mov     [rsp+0D0h+var_B0], 94Bh
0x14003260a  jmp     loc_140032506
0x14003260f  mov     rcx, [rbx+298h]
0x140032616  add     rcx, 8
0x14003261a  mov     rax, [rcx]
0x14003261d  lea     r8, [rbp+57h+arg_8]
0x140032621  lea     rdx, aDwordcount; "DwordCount"
0x140032628  mov     rax, [rax]
0x14003262b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032630  mov     edi, eax
0x140032632  test    eax, eax
0x140032634  jns     short loc_14003267E
0x140032636  mov     rax, [rbx+50h]
0x14003263a  lea     rcx, [rbx+50h]
0x14003263e  mov     rax, [rax+10h]
0x140032642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032647  test    rax, rax
0x14003264a  jz      loc_14003315D
0x140032650  mov     rax, [rbx+50h]
0x140032654  lea     rcx, [rbx+50h]
0x140032658  mov     rax, [rax+10h]
0x14003265c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032661  mov     ebx, r12d
0x140032664  test    rax, rax
0x140032667  jz      loc_14003252E
0x14003266d  mov     [rsp+0D0h+var_A8], edi
0x140032671  mov     [rsp+0D0h+var_B0], 94Eh
0x140032679  jmp     loc_140032506
0x14003267e  mov     rcx, [rbx+298h]
0x140032685  add     rcx, 8
0x140032689  mov     rax, [rcx]
0x14003268c  lea     r8, [rbp+57h+arg_10]
0x140032690  lea     rdx, aQuadwordcount; "QuadwordCount"
0x140032697  mov     rax, [rax]
0x14003269a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003269f  mov     edi, eax
0x1400326a1  test    eax, eax
0x1400326a3  jns     short loc_1400326ED
0x1400326a5  mov     rax, [rbx+50h]
0x1400326a9  lea     rcx, [rbx+50h]
0x1400326ad  mov     rax, [rax+10h]
0x1400326b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400326b6  test    rax, rax
0x1400326b9  jz      loc_14003315D
0x1400326bf  mov     rax, [rbx+50h]
0x1400326c3  lea     rcx, [rbx+50h]
0x1400326c7  mov     rax, [rax+10h]
0x1400326cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400326d0  mov     ebx, r12d
0x1400326d3  test    rax, rax
0x1400326d6  jz      loc_14003252E
0x1400326dc  mov     [rsp+0D0h+var_A8], edi
0x1400326e0  mov     [rsp+0D0h+var_B0], 951h
0x1400326e8  jmp     loc_140032506
0x1400326ed  mov     esi, r12d
0x1400326f0  cmp     [rbp+57h+arg_0], r12d
0x1400326f4  jbe     loc_140032801
0x1400326fa  mov     rcx, [rbp+57h+var_A0]
0x1400326fe  test    rcx, rcx
0x140032701  jz      short loc_140032713
0x140032703  mov     rax, [rcx]
0x140032706  mov     rax, [rax+10h]
0x14003270a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003270f  mov     [rbp+57h+var_A0], r12
0x140032713  mov     rcx, [rbx+298h]
0x14003271a  mov     rax, [rcx]
0x14003271d  lea     r9, [rbp+57h+var_A0]
0x140032721  mov     r8d, esi
0x140032724  lea     rdx, aStringproperty; "StringProperty"
0x14003272b  mov     rax, [rax+20h]
0x14003272f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032734  mov     edi, eax
0x140032736  test    eax, eax
0x140032738  js      loc_140032C45
0x14003273e  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140032742  test    rcx, rcx
0x140032745  jz      short loc_140032757
0x140032747  call    cs:__imp_SysFreeString
0x14003274e  nop     dword ptr [rax+rax+00h]
0x140032753  mov     [rbp+57h+bstrString], r12
0x140032757  mov     rcx, [rbp+57h+var_A0]
0x14003275b  add     rcx, 8
0x14003275f  mov     rax, [rcx]
0x140032762  lea     r8, [rbp+57h+bstrString]
0x140032766  lea     rdx, aName; "Name"
0x14003276d  mov     rax, [rax+10h]
0x140032771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032776  mov     edi, eax
0x140032778  test    eax, eax
0x14003277a  js      loc_140032BFD
0x140032780  mov     rcx, [rbp+57h+var_88]; bstrString
0x140032784  test    rcx, rcx
0x140032787  jz      short loc_140032799
0x140032789  call    cs:__imp_SysFreeString
0x140032790  nop     dword ptr [rax+rax+00h]
0x140032795  mov     [rbp+57h+var_88], r12
0x140032799  mov     rcx, [rbp+57h+var_A0]
0x14003279d  add     rcx, 8
0x1400327a1  mov     rax, [rcx]
0x1400327a4  lea     r8, [rbp+57h+var_88]
0x1400327a8  lea     rdx, aValue; "Value"
0x1400327af  mov     rax, [rax+10h]
0x1400327b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400327b8  mov     edi, eax
0x1400327ba  test    eax, eax
0x1400327bc  js      loc_140032BB5
0x1400327c2  lea     rcx, [rbx+220h]
0x1400327c9  lea     rdx, [rbp+57h+bstrString]
0x1400327cd  call    ?Append@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_BSTR@@@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(DH_BSTR const &)
0x1400327d2  mov     edi, eax
0x1400327d4  test    eax, eax
0x1400327d6  js      loc_140032B6D
0x1400327dc  lea     rcx, [rbx+230h]
0x1400327e3  lea     rdx, [rbp+57h+var_88]
0x1400327e7  call    ?Append@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_BSTR@@@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(DH_BSTR const &)
0x1400327ec  mov     edi, eax
0x1400327ee  test    eax, eax
0x1400327f0  js      loc_140032B25
0x1400327f6  inc     esi
0x1400327f8  cmp     esi, [rbp+57h+arg_0]
0x1400327fb  jb      loc_1400326FA
0x140032801  mov     esi, r12d
0x140032804  cmp     [rbp+57h+arg_8], r12d
0x140032808  jbe     loc_1400328FA
0x14003280e  mov     rcx, [rbp+57h+var_A0]
0x140032812  test    rcx, rcx
0x140032815  jz      short loc_140032827
0x140032817  mov     rax, [rcx]
0x14003281a  mov     rax, [rax+10h]
0x14003281e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032823  mov     [rbp+57h+var_A0], r12
0x140032827  mov     rcx, [rbx+298h]
0x14003282e  mov     rax, [rcx]
0x140032831  lea     r9, [rbp+57h+var_A0]
0x140032835  mov     r8d, esi
0x140032838  lea     rdx, aDwordproperty; "DwordProperty"
0x14003283f  mov     rax, [rax+20h]
0x140032843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032848  mov     edi, eax
0x14003284a  test    eax, eax
0x14003284c  js      loc_140032DAD
0x140032852  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140032856  test    rcx, rcx
0x140032859  jz      short loc_14003286B
0x14003285b  call    cs:__imp_SysFreeString
0x140032862  nop     dword ptr [rax+rax+00h]
0x140032867  mov     [rbp+57h+bstrString], r12
0x14003286b  mov     rcx, [rbp+57h+var_A0]
0x14003286f  add     rcx, 8
0x140032873  mov     rax, [rcx]
0x140032876  lea     r8, [rbp+57h+bstrString]
0x14003287a  lea     rdx, aName; "Name"
0x140032881  mov     rax, [rax+10h]
0x140032885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003288a  mov     edi, eax
0x14003288c  test    eax, eax
0x14003288e  js      loc_140032D65
0x140032894  mov     rcx, [rbp+57h+var_A0]
0x140032898  add     rcx, 8
0x14003289c  mov     rax, [rcx]
0x14003289f  lea     r8, [rbp+57h+var_80]
0x1400328a3  lea     rdx, aValue; "Value"
0x1400328aa  mov     rax, [rax]
0x1400328ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400328b2  mov     edi, eax
  ... truncated ...
```
