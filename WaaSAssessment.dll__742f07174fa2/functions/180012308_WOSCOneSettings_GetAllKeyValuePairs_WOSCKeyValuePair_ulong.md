# WOSCOneSettings::GetAllKeyValuePairs(WOSCKeyValuePair *,ulong *)

- ea: `0x180012308`
- end: `0x180012a5a`
- name: `?GetAllKeyValuePairs@WOSCOneSettings@@QEAAJPEAUWOSCKeyValuePair@@PEAK@Z`
- size: `1874`
- prototype: `__int64 __fastcall(WOSCOneSettings *__hidden this, struct WOSCKeyValuePair *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d300`

## callees

- `0x180006e28`
- `0x18000efec`
- `0x180012308`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800125d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001260d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001261b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012625`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800125d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001260d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001261b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012510`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012542`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001270f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800127a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800127b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012510`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012542`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001270f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800127a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800127b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012587`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800125a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012587`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800125a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall WOSCOneSettings::GetAllKeyValuePairs(
        WOSCOneSettings *this,
        struct WOSCKeyValuePair *a2,
        unsigned int *a3)
{
  LPVOID v5; // r15
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int v16; // r14d
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING *); // rbx
  int v25; // eax
  HSTRING v26; // rcx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v28; // rax
  void *v29; // rdi
  LPVOID v30; // rbx
  void *v31; // rbx
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // [rsp+20h] [rbp-40h] BYREF
  __int64 v62; // [rsp+28h] [rbp-38h] BYREF
  __int64 v63; // [rsp+30h] [rbp-30h] BYREF
  __int64 v64; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+40h] [rbp-20h] BYREF
  HSTRING v66; // [rsp+48h] [rbp-18h] BYREF
  LPVOID v67; // [rsp+50h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  char v70; // [rsp+B0h] [rbp+50h] BYREF
  int v71; // [rsp+B8h] [rbp+58h] BYREF

  v5 = 0;
  if ( !a3 )
  {
    v6 = -2147467261;
    v7 = 252;
LABEL_102:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
      (const char *)v6,
      v61);
    return v6;
  }
  if ( !*(_QWORD *)this )
  {
    v6 = -2147418113;
    v7 = 253;
    goto LABEL_102;
  }
  v62 = 0;
  *a3 = 0;
  v8 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this)(
         *(_QWORD *)this,
         &GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099,
         &v62);
  v6 = v8;
  if ( v8 >= 0 )
  {
    v61 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v62 + 48LL))(v62, &v61);
    v6 = v10;
    if ( v10 >= 0 )
    {
      v70 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v61 + 56LL))(v61, &v70);
      v6 = v13;
      if ( v13 >= 0 )
      {
        v16 = 0;
        while ( 1 )
        {
          if ( !v70 )
          {
            *a3 = v16;
            v35 = v61;
            if ( v61 )
            {
              v61 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
            }
            v36 = v62;
            if ( v62 )
            {
              v62 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            }
            return 0;
          }
          v63 = 0;
          v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 48LL))(v61, &v63);
          v6 = v17;
          if ( v17 < 0 )
            break;
          v64 = 0;
          v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 56LL))(v63, &v64);
          v6 = v18;
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x114,
              (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
              (const char *)(unsigned int)v18,
              v61);
            v54 = v64;
            if ( v64 )
            {
              v64 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
            }
            v55 = v63;
            if ( v63 )
            {
              v63 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
            }
            v56 = v61;
            if ( v61 )
            {
              v61 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
            }
            v57 = v62;
            if ( v62 )
            {
              v62 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
            }
            return v6;
          }
          v71 = 0;
          v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v64 + 48LL))(v64, &v71);
          v6 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x117,
              (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
              (const char *)(unsigned int)v19,
              v61);
            v50 = v64;
            if ( v64 )
            {
              v64 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
            }
            v51 = v63;
            if ( v63 )
            {
              v63 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
            }
            v52 = v61;
            if ( v61 )
            {
              v61 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
            }
            v53 = v62;
            if ( v62 )
            {
              v62 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
            }
            return v6;
          }
          if ( v71 == 3 )
          {
            v66 = 0;
            string = 0;
            v20 = v64;
            v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v64 + 64LL);
            WindowsDeleteString(0);
            v66 = 0;
            v22 = v21(v20, &v66);
            v6 = v22;
            if ( v22 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x11F,
                (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
                (const char *)(unsigned int)v22,
                v61);
              WindowsDeleteString(string);
              string = 0;
              WindowsDeleteString(v66);
              v66 = 0;
              v42 = v64;
              if ( v64 )
              {
                v64 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
              }
              v43 = v63;
              if ( v63 )
              {
                v63 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
              }
              v44 = v61;
              if ( v61 )
              {
                v61 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
              }
              v45 = v62;
              if ( v62 )
              {
                v62 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
              }
              return v6;
            }
            v23 = v63;
            v24 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v63 + 48LL);
            WindowsDeleteString(string);
            string = 0;
            v25 = v24(v23, &string);
            v6 = v25;
            if ( v25 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x120,
                (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
                (const char *)(unsigned int)v25,
                v61);
              WindowsDeleteString(string);
              string = 0;
              WindowsDeleteString(v66);
              v66 = 0;
              v38 = v64;
              if ( v64 )
              {
                v64 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
              }
              v39 = v63;
              if ( v63 )
              {
                v63 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
              }
              v40 = v61;
              if ( v61 )
              {
                v61 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
              }
              v41 = v62;
              if ( v62 )
              {
                v62 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
              }
              return v6;
            }
            v26 = string;
            if ( v66 && string )
            {
              if ( a2 )
              {
                StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                v67 = 0;
                CSpDynamicString::operator=(&v67, StringRawBuffer);
                v28 = WindowsGetStringRawBuffer(v66, 0);
                pv = 0;
                CSpDynamicString::operator=(&pv, v28);
                v29 = v67;
                if ( v67 )
                {
                  v67 = 0;
                  CSpDynamicString::operator=(&v67, v29);
                  v30 = v67;
                  CoTaskMemFree(0);
                }
                else
                {
                  v30 = 0;
                }
                *((_QWORD *)a2 + 2 * v16) = v30;
                v31 = pv;
                if ( pv )
                {
                  pv = 0;
                  CSpDynamicString::operator=(&pv, v31);
                  v5 = pv;
                  CoTaskMemFree(0);
                }
                *((_QWORD *)a2 + 2 * v16 + 1) = v5;
                CoTaskMemFree(v31);
                CoTaskMemFree(v29);
                v26 = string;
                v5 = 0;
              }
              ++v16;
            }
            WindowsDeleteString(v26);
            string = 0;
            WindowsDeleteString(v66);
          }
          v32 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v61 + 64LL))(v61, &v70);
          v6 = v32;
          if ( v32 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x12F,
              (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
              (const char *)(unsigned int)v32,
              v61);
            v46 = v64;
            if ( v64 )
            {
              v64 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
            }
            v47 = v63;
            if ( v63 )
            {
              v63 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
            }
            v48 = v61;
            if ( v61 )
            {
              v61 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
            }
            v49 = v62;
            if ( v62 )
            {
              v62 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
            }
            return v6;
          }
          v33 = v64;
          if ( v64 )
          {
            v64 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
          }
          v34 = v63;
          if ( v63 )
          {
            v63 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x111,
          (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
          (const char *)(unsigned int)v17,
          v61);
        v58 = v63;
        if ( v63 )
        {
          v63 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        }
        v59 = v61;
        if ( v61 )
        {
          v61 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
        }
        v60 = v62;
        if ( v62 )
        {
          v62 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10B,
          (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
          (const char *)(unsigned int)v13,
          v61);
        v14 = v61;
        if ( v61 )
        {
          v61 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        v15 = v62;
        if ( v62 )
        {
          v62 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
        (const char *)(unsigned int)v10,
        v61);
      v11 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      v12 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecore\\enduser\\waasassessment\\woscsettings\\wosconesettings.cpp",
      (const char *)(unsigned int)v8,
      v61);
    v9 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180012308  mov     [rsp-38h+arg_0], rbx
0x18001230d  push    rbp
0x18001230e  push    rsi
0x18001230f  push    rdi
0x180012310  push    r12
0x180012312  push    r13
0x180012314  push    r14
0x180012316  push    r15
0x180012318  mov     rbp, rsp
0x18001231b  sub     rsp, 60h
0x18001231f  mov     r13, r8
0x180012322  mov     r12, rdx
0x180012325  xor     r15d, r15d
0x180012328  test    r8, r8
0x18001232b  jnz     short loc_18001233C
0x18001232d  mov     ebx, 80004003h
0x180012332  mov     edx, 0FCh
0x180012337  jmp     loc_180012A2D
0x18001233c  cmp     [rcx], r15
0x18001233f  jz      loc_180012A23
0x180012345  mov     [rbp+var_38], r15
0x180012349  mov     [r8], r15d
0x18001234c  mov     rcx, [rcx]
0x18001234f  mov     rax, [rcx]
0x180012352  lea     r8, [rbp+var_38]
0x180012356  lea     rdx, _GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099
0x18001235d  mov     rax, [rax]
0x180012360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012365  mov     ebx, eax
0x180012367  test    eax, eax
0x180012369  jns     short loc_1800123A3
0x18001236b  mov     rcx, [rbp+38h]; this
0x18001236f  mov     r9d, eax; char *
0x180012372  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x180012379  mov     edx, 104h; void *
0x18001237e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012383  nop
0x180012384  mov     rcx, [rbp+var_38]
0x180012388  test    rcx, rcx
0x18001238b  jz      short loc_18001239E
0x18001238d  mov     [rbp+var_38], r15
0x180012391  mov     rax, [rcx]
0x180012394  mov     rax, [rax+10h]
0x180012398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001239d  nop
0x18001239e  jmp     loc_180012A40
0x1800123a3  mov     [rbp+var_40], r15
0x1800123a7  mov     rcx, [rbp+var_38]
0x1800123ab  mov     rax, [rcx]
0x1800123ae  lea     rdx, [rbp+var_40]
0x1800123b2  mov     rax, [rax+30h]
0x1800123b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123bb  mov     ebx, eax
0x1800123bd  test    eax, eax
0x1800123bf  jns     short loc_180012413
0x1800123c1  mov     rcx, [rbp+38h]; this
0x1800123c5  mov     r9d, eax; char *
0x1800123c8  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x1800123cf  mov     edx, 108h; void *
0x1800123d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800123d9  nop
0x1800123da  mov     rcx, [rbp+var_40]
0x1800123de  test    rcx, rcx
0x1800123e1  jz      short loc_1800123F4
0x1800123e3  mov     [rbp+var_40], r15
0x1800123e7  mov     rax, [rcx]
0x1800123ea  mov     rax, [rax+10h]
0x1800123ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123f3  nop
0x1800123f4  mov     rcx, [rbp+var_38]
0x1800123f8  test    rcx, rcx
0x1800123fb  jz      short loc_18001240E
0x1800123fd  mov     [rbp+var_38], r15
0x180012401  mov     rax, [rcx]
0x180012404  mov     rax, [rax+10h]
0x180012408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001240d  nop
0x18001240e  jmp     loc_180012A40
0x180012413  mov     [rbp+arg_10], r15b
0x180012417  mov     rcx, [rbp+var_40]
0x18001241b  mov     rax, [rcx]
0x18001241e  lea     rdx, [rbp+arg_10]
0x180012422  mov     rax, [rax+38h]
0x180012426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001242b  mov     ebx, eax
0x18001242d  test    eax, eax
0x18001242f  jns     short loc_180012483
0x180012431  mov     rcx, [rbp+38h]; this
0x180012435  mov     r9d, eax; char *
0x180012438  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x18001243f  mov     edx, 10Bh; void *
0x180012444  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012449  nop
0x18001244a  mov     rcx, [rbp+var_40]
0x18001244e  test    rcx, rcx
0x180012451  jz      short loc_180012464
0x180012453  mov     [rbp+var_40], r15
0x180012457  mov     rax, [rcx]
0x18001245a  mov     rax, [rax+10h]
0x18001245e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012463  nop
0x180012464  mov     rcx, [rbp+var_38]
0x180012468  test    rcx, rcx
0x18001246b  jz      short loc_18001247E
0x18001246d  mov     [rbp+var_38], r15
0x180012471  mov     rax, [rcx]
0x180012474  mov     rax, [rax+10h]
0x180012478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001247d  nop
0x18001247e  jmp     loc_180012A40
0x180012483  mov     r14d, r15d
0x180012486  jmp     loc_18001269B
0x18001248b  mov     [rbp+var_30], r15
0x18001248f  mov     rcx, [rbp+var_40]
0x180012493  mov     rax, [rcx]
0x180012496  lea     rdx, [rbp+var_30]
0x18001249a  mov     rax, [rax+30h]
0x18001249e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124a3  mov     ebx, eax
0x1800124a5  test    eax, eax
0x1800124a7  js      loc_1800129BA
0x1800124ad  mov     [rbp+var_28], r15
0x1800124b1  mov     rcx, [rbp+var_30]
0x1800124b5  mov     rax, [rcx]
0x1800124b8  lea     rdx, [rbp+var_28]
0x1800124bc  mov     rax, [rax+38h]
0x1800124c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124c5  mov     ebx, eax
0x1800124c7  test    eax, eax
0x1800124c9  js      loc_180012934
0x1800124cf  mov     [rbp+arg_18], r15d
0x1800124d3  mov     rcx, [rbp+var_28]
0x1800124d7  mov     rax, [rcx]
0x1800124da  lea     rdx, [rbp+arg_18]
0x1800124de  mov     rax, [rax+30h]
0x1800124e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124e7  mov     ebx, eax
0x1800124e9  test    eax, eax
0x1800124eb  js      loc_1800128AE
0x1800124f1  cmp     [rbp+arg_18], 3
0x1800124f5  jnz     loc_180012649
0x1800124fb  mov     [rbp+var_18], r15
0x1800124ff  mov     [rbp+string], r15
0x180012503  mov     rdi, [rbp+var_28]
0x180012507  mov     rax, [rdi]
0x18001250a  mov     rbx, [rax+40h]
0x18001250e  xor     ecx, ecx; string
0x180012510  call    cs:__imp_WindowsDeleteString
0x180012516  mov     [rbp+var_18], r15
0x18001251a  lea     rdx, [rbp+var_18]
0x18001251e  mov     rcx, rdi
0x180012521  mov     rax, rbx
0x180012524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012529  mov     ebx, eax
0x18001252b  test    eax, eax
0x18001252d  js      loc_180012786
0x180012533  mov     rdi, [rbp+var_30]
0x180012537  mov     rax, [rdi]
0x18001253a  mov     rbx, [rax+30h]
0x18001253e  mov     rcx, [rbp+string]; string
0x180012542  call    cs:__imp_WindowsDeleteString
0x180012548  mov     [rbp+string], r15
0x18001254c  lea     rdx, [rbp+string]
0x180012550  mov     rcx, rdi
0x180012553  mov     rax, rbx
0x180012556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001255b  mov     ebx, eax
0x18001255d  test    eax, eax
0x18001255f  js      loc_1800126E4
0x180012565  mov     rcx, [rbp+string]; string
0x180012569  cmp     [rbp+var_18], r15
0x18001256d  jz      loc_180012635
0x180012573  test    rcx, rcx
0x180012576  jz      loc_180012635
0x18001257c  test    r12, r12
0x18001257f  jz      loc_180012632
0x180012585  xor     edx, edx; length
0x180012587  call    cs:__imp_WindowsGetStringRawBuffer
0x18001258d  mov     [rbp+var_10], r15
0x180012591  mov     rdx, rax
0x180012594  lea     rcx, [rbp+var_10]
0x180012598  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x18001259d  nop
0x18001259e  xor     edx, edx; length
0x1800125a0  mov     rcx, [rbp+var_18]; string
0x1800125a4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800125aa  mov     [rbp+pv], r15
0x1800125ae  mov     rdx, rax
0x1800125b1  lea     rcx, [rbp+pv]
0x1800125b5  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x1800125ba  mov     rdi, [rbp+var_10]
0x1800125be  test    rdi, rdi
0x1800125c1  jz      short loc_1800125E1
0x1800125c3  mov     [rbp+var_10], r15
0x1800125c7  mov     rdx, rdi
0x1800125ca  lea     rcx, [rbp+var_10]
0x1800125ce  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x1800125d3  mov     rbx, [rbp+var_10]
0x1800125d7  xor     ecx, ecx; pv
0x1800125d9  call    cs:__imp_CoTaskMemFree
0x1800125df  jmp     short loc_1800125E4
0x1800125e1  mov     rbx, r15
0x1800125e4  mov     esi, r14d
0x1800125e7  add     rsi, rsi
0x1800125ea  mov     [r12+rsi*8], rbx
0x1800125ee  mov     rbx, [rbp+pv]
0x1800125f2  test    rbx, rbx
0x1800125f5  jz      short loc_180012613
0x1800125f7  mov     [rbp+pv], r15
0x1800125fb  mov     rdx, rbx
0x1800125fe  lea     rcx, [rbp+pv]
0x180012602  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x180012607  mov     r15, [rbp+pv]
0x18001260b  xor     ecx, ecx; pv
0x18001260d  call    cs:__imp_CoTaskMemFree
0x180012613  mov     [r12+rsi*8+8], r15
0x180012618  mov     rcx, rbx; pv
0x18001261b  call    cs:__imp_CoTaskMemFree
0x180012621  nop
0x180012622  mov     rcx, rdi; pv
0x180012625  call    cs:__imp_CoTaskMemFree
0x18001262b  mov     rcx, [rbp+string]; string
0x18001262f  xor     r15d, r15d
0x180012632  inc     r14d
0x180012635  call    cs:__imp_WindowsDeleteString
0x18001263b  mov     [rbp+string], r15
0x18001263f  mov     rcx, [rbp+var_18]; string
0x180012643  call    cs:__imp_WindowsDeleteString
0x180012649  mov     rcx, [rbp+var_40]
0x18001264d  mov     rax, [rcx]
0x180012650  lea     rdx, [rbp+arg_10]
0x180012654  mov     rax, [rax+40h]
0x180012658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001265d  mov     ebx, eax
0x18001265f  test    eax, eax
0x180012661  js      loc_180012828
0x180012667  mov     rcx, [rbp+var_28]
0x18001266b  test    rcx, rcx
0x18001266e  jz      short loc_180012681
0x180012670  mov     [rbp+var_28], r15
0x180012674  mov     rax, [rcx]
0x180012677  mov     rax, [rax+10h]
0x18001267b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012680  nop
0x180012681  mov     rcx, [rbp+var_30]
0x180012685  test    rcx, rcx
0x180012688  jz      short loc_18001269B
0x18001268a  mov     [rbp+var_30], r15
0x18001268e  mov     rax, [rcx]
0x180012691  mov     rax, [rax+10h]
0x180012695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001269a  nop
0x18001269b  cmp     [rbp+arg_10], r15b
0x18001269f  jnz     loc_18001248B
0x1800126a5  mov     [r13+0], r14d
0x1800126a9  mov     rcx, [rbp+var_40]
0x1800126ad  test    rcx, rcx
0x1800126b0  jz      short loc_1800126C3
0x1800126b2  mov     [rbp+var_40], r15
0x1800126b6  mov     rax, [rcx]
0x1800126b9  mov     rax, [rax+10h]
0x1800126bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126c2  nop
0x1800126c3  mov     rcx, [rbp+var_38]
0x1800126c7  test    rcx, rcx
0x1800126ca  jz      short loc_1800126DD
0x1800126cc  mov     [rbp+var_38], r15
0x1800126d0  mov     rax, [rcx]
0x1800126d3  mov     rax, [rax+10h]
0x1800126d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126dc  nop
0x1800126dd  xor     eax, eax
0x1800126df  jmp     loc_180012A42
0x1800126e4  mov     rcx, [rbp+38h]; this
0x1800126e8  mov     r9d, ebx; char *
0x1800126eb  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasassessment\\woscs"...
0x1800126f2  mov     edx, 120h; void *
0x1800126f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800126fc  nop
0x1800126fd  mov     rcx, [rbp+string]; string
0x180012701  call    cs:__imp_WindowsDeleteString
0x180012707  mov     [rbp+string], r15
0x18001270b  mov     rcx, [rbp+var_18]; string
0x18001270f  call    cs:__imp_WindowsDeleteString
0x180012715  mov     [rbp+var_18], r15
0x180012719  mov     rcx, [rbp+var_28]
0x18001271d  test    rcx, rcx
0x180012720  jz      short loc_180012733
0x180012722  mov     [rbp+var_28], r15
0x180012726  mov     rax, [rcx]
0x180012729  mov     rax, [rax+10h]
0x18001272d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012732  nop
0x180012733  mov     rcx, [rbp+var_30]
0x180012737  test    rcx, rcx
0x18001273a  jz      short loc_18001274D
0x18001273c  mov     [rbp+var_30], r15
0x180012740  mov     rax, [rcx]
0x180012743  mov     rax, [rax+10h]
0x180012747  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
