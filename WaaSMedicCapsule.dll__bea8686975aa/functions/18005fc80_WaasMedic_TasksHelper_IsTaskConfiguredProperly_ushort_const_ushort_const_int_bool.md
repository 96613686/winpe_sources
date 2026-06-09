# WaasMedic::TasksHelper::IsTaskConfiguredProperly(ushort const *,ushort const *,int,bool *)

- ea: `0x18005fc80`
- end: `0x18006027e`
- name: `?IsTaskConfiguredProperly@TasksHelper@WaasMedic@@QEAAJPEBG0HPEA_N@Z`
- size: `1534`
- prototype: `int(WaasMedic::TasksHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int, bool *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180054fd0`
- `0x18005acb8`

## callees

- `0x180002150`
- `0x180002738`
- `0x180009a54`
- `0x180016c9c`
- `0x18002543c`
- `0x18005c670`
- `0x18005e218`
- `0x18005e614`
- `0x18005ec54`
- `0x18005fc80`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005fcc4`
- `OLEAUT32!__imp_SysAllocString` at `0x18005fce0`
- `OLEAUT32!__imp_SysAllocString` at `0x18005fcc4`
- `OLEAUT32!__imp_SysAllocString` at `0x18005fce0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fd21`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fd2e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fd38`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fdc2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fdcf`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fdd9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fee9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800601f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180060202`
- `OLEAUT32!__imp_SysFreeString` at `0x18006020c`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fd21`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fd2e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fd38`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fdc2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fdcf`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fdd9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fee9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800601f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180060202`
- `OLEAUT32!__imp_SysFreeString` at `0x18006020c`

## string_xrefs

- `0x18005fd0b`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x18005fdac`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x18005fe53`: `m_taskFolder->GetTask`
- `0x18005fecb`: `pExpectedTaskDefinition->put_XmlText`
- `0x18005ff0f`: `pCurrentTaskDefinition->get_XmlText`
- `0x18005fe7c`: `pCurrentTask->get_Definition`
- `0x18005fea3`: `m_taskService->NewTask`
- `0x18006009a`: `CompareActions`
- `0x180060091`: `CompareTriggers`
- `0x18005ff1f`: `pCurrentTaskXml:: %s`
- `0x1800600a3`: `ComparePrincipals`
- `0x180060088`: `CompareSettings`
- `0x1800600b5`: `Error encountered when comparing current task settings with expected task settings. hr=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall WaasMedic::TasksHelper::IsTaskConfiguredProperly(
        WaasMedic::TasksHelper *this,
        OLECHAR *a2,
        OLECHAR *a3,
        int a4,
        bool *a5)
{
  OLECHAR *v8; // rdi
  OLECHAR *v9; // rbx
  bool *v10; // r15
  unsigned int v11; // r14d
  const unsigned __int16 *v12; // rcx
  const unsigned __int16 *v14; // rcx
  int v15; // esi
  const wchar_t *v16; // r14
  bool *v17; // r14
  __int64 (__fastcall *v18)(bool *, BSTR *); // rsi
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  const struct _tlgProvider_t *v22; // rax
  int v23; // r9d
  const struct _tlgProvider_t *v24; // r8
  __int64 v25; // rax
  const struct _tlgProvider_t *v26; // rax
  int v27; // r9d
  const unsigned __int16 *v28; // rcx
  bool *v29; // rcx
  __int64 v30; // rcx
  int v31; // [rsp+20h] [rbp-60h]
  bool *v32; // [rsp+50h] [rbp-30h] BYREF
  __int64 v33; // [rsp+58h] [rbp-28h] BYREF
  const unsigned __int16 *v34; // [rsp+60h] [rbp-20h] BYREF
  __int64 v35; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int16 *v36; // [rsp+70h] [rbp-10h] BYREF
  unsigned __int16 *v37; // [rsp+78h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  BSTR bstrString; // [rsp+C8h] [rbp+48h] BYREF
  const unsigned __int16 *v40; // [rsp+D0h] [rbp+50h] BYREF
  int v41; // [rsp+D8h] [rbp+58h] BYREF

  v41 = a4;
  v33 = 0;
  v32 = 0;
  v40 = 0;
  v8 = 0;
  v35 = 0;
  if ( a2 )
  {
    v8 = SysAllocString(a2);
    v35 = (__int64)v8;
  }
  v9 = 0;
  v36 = 0;
  if ( a3 )
  {
    v9 = SysAllocString(a3);
    v36 = v9;
  }
  bstrString = 0;
  v10 = a5;
  if ( !a5 )
  {
    v11 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\taskshelper.cpp",
      (const char *)0x80004003LL,
      v31);
    SysFreeString(bstrString);
    bstrString = 0;
    SysFreeString(v9);
    SysFreeString(v8);
    v12 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v11;
  }
  if ( !*((_BYTE *)this + 17) )
  {
    v11 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x209,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\taskshelper.cpp",
      (const char *)0x8007139FLL,
      v31);
    SysFreeString(bstrString);
    bstrString = 0;
    SysFreeString(v9);
    SysFreeString(v8);
    v14 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return v11;
  }
  *a5 = 0;
  v15 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(**((_QWORD **)this + 1) + 104LL))(
          *((_QWORD *)this + 1),
          v8,
          &v33);
  if ( v15 < 0 )
  {
    v16 = L"m_taskFolder->GetTask";
    goto LABEL_53;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, bool **))(*(_QWORD *)v33 + 152LL))(v33, &v32);
  if ( v15 < 0 )
  {
    v16 = L"pCurrentTask->get_Definition";
    goto LABEL_53;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 **))(**(_QWORD **)this + 72LL))(
          *(_QWORD *)this,
          0,
          &v40);
  if ( v15 < 0 )
  {
    v16 = L"m_taskService->NewTask";
    goto LABEL_53;
  }
  v15 = (*(__int64 (__fastcall **)(const unsigned __int16 *, OLECHAR *))(*(_QWORD *)v40 + 160LL))(v40, v9);
  if ( v15 < 0 )
  {
    v16 = L"pExpectedTaskDefinition->put_XmlText";
    goto LABEL_53;
  }
  v17 = v32;
  v18 = *(__int64 (__fastcall **)(bool *, BSTR *))(*(_QWORD *)v32 + 152LL);
  SysFreeString(bstrString);
  bstrString = 0;
  v15 = v18(v17, &bstrString);
  if ( v15 < 0 )
  {
    v16 = L"pCurrentTaskDefinition->get_XmlText";
    goto LABEL_53;
  }
  LogLevelW(4u, L"pCurrentTaskXml:: %s", bstrString);
  a5 = v32;
  if ( v32 )
    (*(void (__fastcall **)(bool *))(*(_QWORD *)v32 + 8LL))(v32);
  v34 = v40;
  if ( v40 )
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v40 + 8LL))(v40);
  v15 = WaasMedic::TasksHelper::ComparePrincipals(&v34, &a5, v19, v10);
  if ( v15 >= 0 && *v10 )
  {
    a5 = v32;
    if ( v32 )
      (*(void (__fastcall **)(bool *))(*(_QWORD *)v32 + 8LL))(v32);
    v34 = v40;
    if ( v40 )
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v40 + 8LL))(v40);
    v15 = WaasMedic::TasksHelper::CompareActions(&v34, &a5, 0, v10);
    if ( v15 >= 0 && *v10 )
    {
      a5 = v32;
      if ( v32 )
        (*(void (__fastcall **)(bool *))(*(_QWORD *)v32 + 8LL))(v32);
      v34 = v40;
      if ( v40 )
        (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v40 + 8LL))(v40);
      v15 = WaasMedic::TasksHelper::CompareTriggers(&v34, &a5, v20, v10);
      if ( v15 >= 0 && *v10 )
      {
        a5 = v32;
        if ( v32 )
          (*(void (__fastcall **)(bool *))(*(_QWORD *)v32 + 8LL))(v32);
        v34 = v40;
        if ( v40 )
          (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v40 + 8LL))(v40);
        v15 = WaasMedic::TasksHelper::CompareSettings(&v34, &a5, v21, v10);
        if ( v15 >= 0 && *v10 )
        {
          *v10 = 1;
          goto LABEL_62;
        }
        v16 = L"CompareSettings";
      }
      else
      {
        v16 = L"CompareTriggers";
      }
    }
    else
    {
      v16 = L"CompareActions";
    }
  }
  else
  {
    v16 = L"ComparePrincipals";
  }
  if ( v15 < 0 )
  {
LABEL_53:
    LogLevelW(
      2u,
      L"Error encountered when comparing current task settings with expected task settings. hr=0x%08x",
      (unsigned int)v15);
    if ( bstrString )
    {
      v22 = WaasMedic::TelemetryProvider::Provider();
      v24 = v22;
      if ( *(_DWORD *)v22 > 5u )
      {
        v25 = *((_QWORD *)v22 + 3);
        if ( (*((_QWORD *)v24 + 2) & 0x200000000000LL) != 0 && (v25 & 0x200000000000LL) == v25 )
        {
          v41 = v15;
          a5 = (bool *)v16;
          v36 = a3;
          v35 = (__int64)bstrString;
          v34 = a2;
          v37 = &gc_pszVersionString;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (_DWORD)v24,
            (unsigned int)&byte_18008A4BF,
            (_DWORD)v24,
            v23,
            (__int64)&v37,
            (__int64)&v34,
            (__int64)&v35,
            (__int64)&v36,
            (__int64)&a5,
            (__int64)&v41);
        }
      }
    }
    v26 = WaasMedic::TelemetryProvider::Provider();
    if ( *(_DWORD *)v26 > 5u
      && (*((_QWORD *)v26 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v26 + 3) & 0x400000000000LL) == *((_QWORD *)v26 + 3) )
    {
      v41 = v15;
      a5 = (bool *)v16;
      v37 = a2;
      v36 = &gc_pszVersionString;
      v35 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v26,
        (unsigned int)byte_18008A44B,
        0,
        v27,
        (__int64)&v35,
        (__int64)&v36,
        (__int64)&v37,
        (__int64)&a5,
        (__int64)&v41);
    }
  }
LABEL_62:
  SysFreeString(bstrString);
  bstrString = 0;
  SysFreeString(v9);
  SysFreeString(v8);
  v28 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(bool *))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18005fc80  mov     [rsp-38h+arg_0], rbx
0x18005fc85  mov     [rsp-38h+arg_18], r9d
0x18005fc8a  push    rbp
0x18005fc8b  push    rsi
0x18005fc8c  push    rdi
0x18005fc8d  push    r12
0x18005fc8f  push    r13
0x18005fc91  push    r14
0x18005fc93  push    r15
0x18005fc95  mov     rbp, rsp
0x18005fc98  sub     rsp, 80h
0x18005fc9f  mov     r12, r8
0x18005fca2  mov     r13, rdx
0x18005fca5  mov     r14, rcx
0x18005fca8  xor     esi, esi
0x18005fcaa  mov     [rbp+var_28], rsi
0x18005fcae  mov     [rbp+var_30], rsi
0x18005fcb2  mov     [rbp+arg_10], rsi
0x18005fcb6  mov     edi, esi
0x18005fcb8  mov     [rbp+var_18], rsi
0x18005fcbc  test    rdx, rdx
0x18005fcbf  jz      short loc_18005FCD1
0x18005fcc1  mov     rcx, rdx; psz
0x18005fcc4  call    cs:__imp_SysAllocString
0x18005fcca  mov     rdi, rax
0x18005fccd  mov     [rbp+var_18], rax
0x18005fcd1  mov     rbx, rsi
0x18005fcd4  mov     [rbp+var_10], rbx
0x18005fcd8  test    r12, r12
0x18005fcdb  jz      short loc_18005FCED
0x18005fcdd  mov     rcx, r12; psz
0x18005fce0  call    cs:__imp_SysAllocString
0x18005fce6  mov     rbx, rax
0x18005fce9  mov     [rbp+var_10], rax
0x18005fced  mov     [rbp+bstrString], rsi
0x18005fcf1  mov     r15, [rbp+arg_20]
0x18005fcf5  test    r15, r15
0x18005fcf8  jnz     loc_18005FD95
0x18005fcfe  mov     rcx, [rbp+38h]; this
0x18005fd02  mov     r14d, 80004003h
0x18005fd08  mov     r9d, r14d; char *
0x18005fd0b  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005fd12  mov     edx, 208h; void *
0x18005fd17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005fd1c  nop
0x18005fd1d  mov     rcx, [rbp+bstrString]; bstrString
0x18005fd21  call    cs:__imp_SysFreeString
0x18005fd27  mov     [rbp+bstrString], rsi
0x18005fd2b  mov     rcx, rbx; bstrString
0x18005fd2e  call    cs:__imp_SysFreeString
0x18005fd34  nop
0x18005fd35  mov     rcx, rdi; bstrString
0x18005fd38  call    cs:__imp_SysFreeString
0x18005fd3e  nop
0x18005fd3f  mov     rcx, [rbp+arg_10]
0x18005fd43  test    rcx, rcx
0x18005fd46  jz      short loc_18005FD59
0x18005fd48  mov     [rbp+arg_10], rsi
0x18005fd4c  mov     rax, [rcx]
0x18005fd4f  mov     rax, [rax+10h]
0x18005fd53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd58  nop
0x18005fd59  mov     rcx, [rbp+var_30]
0x18005fd5d  test    rcx, rcx
0x18005fd60  jz      short loc_18005FD73
0x18005fd62  mov     [rbp+var_30], rsi
0x18005fd66  mov     rax, [rcx]
0x18005fd69  mov     rax, [rax+10h]
0x18005fd6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd72  nop
0x18005fd73  mov     rcx, [rbp+var_28]
0x18005fd77  test    rcx, rcx
0x18005fd7a  jz      short loc_18005FD8D
0x18005fd7c  mov     [rbp+var_28], rsi
0x18005fd80  mov     rdx, [rcx]
0x18005fd83  mov     rax, [rdx+10h]
0x18005fd87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd8c  nop
0x18005fd8d  mov     eax, r14d
0x18005fd90  jmp     loc_180060263
0x18005fd95  cmp     [r14+11h], sil
0x18005fd99  jnz     loc_18005FE33
0x18005fd9f  mov     rcx, [rbp+38h]; this
0x18005fda3  mov     r14d, 8007139Fh
0x18005fda9  mov     r9d, r14d; char *
0x18005fdac  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005fdb3  mov     edx, 209h; void *
0x18005fdb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005fdbd  nop
0x18005fdbe  mov     rcx, [rbp+bstrString]; bstrString
0x18005fdc2  call    cs:__imp_SysFreeString
0x18005fdc8  mov     [rbp+bstrString], rsi
0x18005fdcc  mov     rcx, rbx; bstrString
0x18005fdcf  call    cs:__imp_SysFreeString
0x18005fdd5  nop
0x18005fdd6  mov     rcx, rdi; bstrString
0x18005fdd9  call    cs:__imp_SysFreeString
0x18005fddf  nop
0x18005fde0  mov     rcx, [rbp+arg_10]
0x18005fde4  test    rcx, rcx
0x18005fde7  jz      short loc_18005FDFA
0x18005fde9  mov     [rbp+arg_10], rsi
0x18005fded  mov     rax, [rcx]
0x18005fdf0  mov     rax, [rax+10h]
0x18005fdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fdf9  nop
0x18005fdfa  mov     rcx, [rbp+var_30]
0x18005fdfe  test    rcx, rcx
0x18005fe01  jz      short loc_18005FE14
0x18005fe03  mov     [rbp+var_30], rsi
0x18005fe07  mov     rax, [rcx]
0x18005fe0a  mov     rax, [rax+10h]
0x18005fe0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe13  nop
0x18005fe14  mov     rcx, [rbp+var_28]
0x18005fe18  test    rcx, rcx
0x18005fe1b  jz      short loc_18005FE2E
0x18005fe1d  mov     [rbp+var_28], rsi
0x18005fe21  mov     rdx, [rcx]
0x18005fe24  mov     rax, [rdx+10h]
0x18005fe28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe2d  nop
0x18005fe2e  jmp     loc_18005FD8D
0x18005fe33  mov     [r15], sil
0x18005fe36  mov     rcx, [r14+8]
0x18005fe3a  mov     rax, [rcx]
0x18005fe3d  lea     r8, [rbp+var_28]
0x18005fe41  mov     rdx, rdi
0x18005fe44  mov     rax, [rax+68h]
0x18005fe48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe4d  mov     esi, eax
0x18005fe4f  test    eax, eax
0x18005fe51  jns     short loc_18005FE5F
0x18005fe53  lea     r14, aMTaskfolderGet; "m_taskFolder->GetTask"
0x18005fe5a  jmp     loc_1800600B2
0x18005fe5f  mov     rcx, [rbp+var_28]
0x18005fe63  mov     rax, [rcx]
0x18005fe66  lea     rdx, [rbp+var_30]
0x18005fe6a  mov     rax, [rax+98h]
0x18005fe71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe76  mov     esi, eax
0x18005fe78  test    eax, eax
0x18005fe7a  jns     short loc_18005FE88
0x18005fe7c  lea     r14, aPcurrenttaskGe; "pCurrentTask->get_Definition"
0x18005fe83  jmp     loc_1800600B2
0x18005fe88  mov     rcx, [r14]
0x18005fe8b  mov     rax, [rcx]
0x18005fe8e  lea     r8, [rbp+arg_10]
0x18005fe92  xor     edx, edx
0x18005fe94  mov     rax, [rax+48h]
0x18005fe98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe9d  mov     esi, eax
0x18005fe9f  test    eax, eax
0x18005fea1  jns     short loc_18005FEAF
0x18005fea3  lea     r14, aMTaskserviceNe; "m_taskService->NewTask"
0x18005feaa  jmp     loc_1800600B2
0x18005feaf  mov     rcx, [rbp+arg_10]
0x18005feb3  mov     rax, [rcx]
0x18005feb6  mov     rdx, rbx
0x18005feb9  mov     rax, [rax+0A0h]
0x18005fec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fec5  mov     esi, eax
0x18005fec7  test    eax, eax
0x18005fec9  jns     short loc_18005FED7
0x18005fecb  lea     r14, aPexpectedtaskd; "pExpectedTaskDefinition->put_XmlText"
0x18005fed2  jmp     loc_1800600B2
0x18005fed7  mov     r14, [rbp+var_30]
0x18005fedb  mov     rax, [r14]
0x18005fede  mov     rsi, [rax+98h]
0x18005fee5  mov     rcx, [rbp+bstrString]; bstrString
0x18005fee9  call    cs:__imp_SysFreeString
0x18005feef  mov     [rbp+bstrString], 0
0x18005fef7  lea     rdx, [rbp+bstrString]
0x18005fefb  mov     rcx, r14
0x18005fefe  mov     rax, rsi
0x18005ff01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ff06  mov     esi, eax
0x18005ff08  xor     r14d, r14d
0x18005ff0b  test    eax, eax
0x18005ff0d  jns     short loc_18005FF1B
0x18005ff0f  lea     r14, aPcurrenttaskde; "pCurrentTaskDefinition->get_XmlText"
0x18005ff16  jmp     loc_1800600B2
0x18005ff1b  mov     r8, [rbp+bstrString]
0x18005ff1f  lea     rdx, aPcurrenttaskxm; "pCurrentTaskXml:: %s"
0x18005ff26  mov     ecx, 4; unsigned __int8
0x18005ff2b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005ff30  mov     rcx, [rbp+var_30]
0x18005ff34  mov     [rbp+arg_20], rcx
0x18005ff38  test    rcx, rcx
0x18005ff3b  jz      short loc_18005FF4A
0x18005ff3d  mov     rax, [rcx]
0x18005ff40  mov     rax, [rax+8]
0x18005ff44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ff49  nop
0x18005ff4a  mov     rcx, [rbp+arg_10]
0x18005ff4e  mov     [rbp+var_20], rcx
0x18005ff52  test    rcx, rcx
0x18005ff55  jz      short loc_18005FF64
0x18005ff57  mov     rax, [rcx]
0x18005ff5a  mov     rax, [rax+8]
0x18005ff5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ff63  nop
0x18005ff64  mov     r9, r15
0x18005ff67  lea     rdx, [rbp+arg_20]
0x18005ff6b  lea     rcx, [rbp+var_20]
0x18005ff6f  call    ?ComparePrincipals@TasksHelper@WaasMedic@@CAJV?$ComPtr@UITaskDefinition@@@WRL@Microsoft@@0HPEA_N@Z; WaasMedic::TasksHelper::ComparePrincipals(Microsoft::WRL::ComPtr<ITaskDefinition>,Microsoft::WRL::ComPtr<ITaskDefinition>,int,bool *)
0x18005ff74  mov     esi, eax
0x18005ff76  test    eax, eax
0x18005ff78  js      loc_1800600A3
0x18005ff7e  cmp     [r15], r14b
0x18005ff81  jz      loc_1800600A3
0x18005ff87  mov     rcx, [rbp+var_30]
0x18005ff8b  mov     [rbp+arg_20], rcx
0x18005ff8f  test    rcx, rcx
0x18005ff92  jz      short loc_18005FFA1
0x18005ff94  mov     rax, [rcx]
0x18005ff97  mov     rax, [rax+8]
0x18005ff9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ffa0  nop
0x18005ffa1  mov     rcx, [rbp+arg_10]
0x18005ffa5  mov     [rbp+var_20], rcx
0x18005ffa9  test    rcx, rcx
0x18005ffac  jz      short loc_18005FFBB
0x18005ffae  mov     rax, [rcx]
0x18005ffb1  mov     rax, [rax+8]
0x18005ffb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ffba  nop
0x18005ffbb  mov     r9, r15
0x18005ffbe  xor     r8d, r8d
0x18005ffc1  lea     rdx, [rbp+arg_20]
0x18005ffc5  lea     rcx, [rbp+var_20]
0x18005ffc9  call    ?CompareActions@TasksHelper@WaasMedic@@CAJV?$ComPtr@UITaskDefinition@@@WRL@Microsoft@@0HPEA_N@Z; WaasMedic::TasksHelper::CompareActions(Microsoft::WRL::ComPtr<ITaskDefinition>,Microsoft::WRL::ComPtr<ITaskDefinition>,int,bool *)
0x18005ffce  mov     esi, eax
0x18005ffd0  test    eax, eax
0x18005ffd2  js      loc_18006009A
0x18005ffd8  cmp     [r15], r14b
0x18005ffdb  jz      loc_18006009A
0x18005ffe1  mov     rcx, [rbp+var_30]
0x18005ffe5  mov     [rbp+arg_20], rcx
0x18005ffe9  test    rcx, rcx
0x18005ffec  jz      short loc_18005FFFB
0x18005ffee  mov     rax, [rcx]
0x18005fff1  mov     rax, [rax+8]
0x18005fff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fffa  nop
0x18005fffb  mov     rcx, [rbp+arg_10]
0x18005ffff  mov     [rbp+var_20], rcx
0x180060003  test    rcx, rcx
0x180060006  jz      short loc_180060015
0x180060008  mov     rax, [rcx]
0x18006000b  mov     rax, [rax+8]
0x18006000f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060014  nop
0x180060015  mov     r9, r15
0x180060018  lea     rdx, [rbp+arg_20]
0x18006001c  lea     rcx, [rbp+var_20]
0x180060020  call    ?CompareTriggers@TasksHelper@WaasMedic@@CAJV?$ComPtr@UITaskDefinition@@@WRL@Microsoft@@0HPEA_N@Z; WaasMedic::TasksHelper::CompareTriggers(Microsoft::WRL::ComPtr<ITaskDefinition>,Microsoft::WRL::ComPtr<ITaskDefinition>,int,bool *)
0x180060025  mov     esi, eax
0x180060027  test    eax, eax
0x180060029  js      short loc_180060091
0x18006002b  cmp     [r15], r14b
0x18006002e  jz      short loc_180060091
0x180060030  mov     rcx, [rbp+var_30]
0x180060034  mov     [rbp+arg_20], rcx
0x180060038  test    rcx, rcx
0x18006003b  jz      short loc_18006004A
0x18006003d  mov     rax, [rcx]
0x180060040  mov     rax, [rax+8]
0x180060044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060049  nop
0x18006004a  mov     rcx, [rbp+arg_10]
0x18006004e  mov     [rbp+var_20], rcx
0x180060052  test    rcx, rcx
0x180060055  jz      short loc_180060064
0x180060057  mov     rax, [rcx]
0x18006005a  mov     rax, [rax+8]
0x18006005e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060063  nop
0x180060064  mov     r9, r15
0x180060067  lea     rdx, [rbp+arg_20]
0x18006006b  lea     rcx, [rbp+var_20]
0x18006006f  call    ?CompareSettings@TasksHelper@WaasMedic@@CAJV?$ComPtr@UITaskDefinition@@@WRL@Microsoft@@0HPEA_N@Z; WaasMedic::TasksHelper::CompareSettings(Microsoft::WRL::ComPtr<ITaskDefinition>,Microsoft::WRL::ComPtr<ITaskDefinition>,int,bool *)
0x180060074  mov     esi, eax
0x180060076  test    eax, eax
0x180060078  js      short loc_180060088
0x18006007a  cmp     [r15], r14b
0x18006007d  jz      short loc_180060088
0x18006007f  mov     byte ptr [r15], 1
0x180060083  jmp     loc_1800601F1
0x180060088  lea     r14, aComparesetting; "CompareSettings"
0x18006008f  jmp     short loc_1800600AA
0x180060091  lea     r14, aComparetrigger; "CompareTriggers"
0x180060098  jmp     short loc_1800600AA
0x18006009a  lea     r14, aCompareactions; "CompareActions"
0x1800600a1  jmp     short loc_1800600AA
0x1800600a3  lea     r14, aCompareprincip; "ComparePrincipals"
0x1800600aa  test    esi, esi
0x1800600ac  jns     loc_1800601EE
0x1800600b2  mov     r8d, esi
0x1800600b5  lea     rdx, aErrorEncounter_0; "Error encountered when comparing curren"...
  ... truncated ...
```
