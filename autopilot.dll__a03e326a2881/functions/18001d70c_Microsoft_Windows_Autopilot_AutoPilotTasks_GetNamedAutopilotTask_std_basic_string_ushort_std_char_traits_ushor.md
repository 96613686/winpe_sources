# Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<IRegisteredTask> &)

- ea: `0x18001d70c`
- end: `0x18001dc5b`
- name: `?GetNamedAutopilotTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIRegisteredTask@@@WRL@4@@Z`
- size: `1359`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016700`
- `0x18001d55c`
- `0x18001d634`

## callees

- `0x1800105f4`
- `0x18001d70c`
- `0x18001e00c`
- `0x18001e030`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d770`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d770`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d94a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d94a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d990`
- `OLEAUT32!__imp_SysFreeString` at `0x18001da87`
- `OLEAUT32!__imp_SysFreeString` at `0x18001db27`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dba4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d990`
- `OLEAUT32!__imp_SysFreeString` at `0x18001da87`
- `OLEAUT32!__imp_SysFreeString` at `0x18001db27`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dba4`
- `OLEAUT32!__imp_VariantInit` at `0x18001d7d9`
- `OLEAUT32!__imp_VariantInit` at `0x18001d7f8`
- `OLEAUT32!__imp_VariantInit` at `0x18001d814`
- `OLEAUT32!__imp_VariantInit` at `0x18001d82b`
- `OLEAUT32!__imp_VariantInit` at `0x18001d7d9`
- `OLEAUT32!__imp_VariantInit` at `0x18001d7f8`
- `OLEAUT32!__imp_VariantInit` at `0x18001d814`
- `OLEAUT32!__imp_VariantInit` at `0x18001d82b`
- `OLEAUT32!__imp_VariantClear` at `0x18001d8bc`
- `OLEAUT32!__imp_VariantClear` at `0x18001d8c8`
- `OLEAUT32!__imp_VariantClear` at `0x18001d8d4`
- `OLEAUT32!__imp_VariantClear` at `0x18001d8e3`
- `OLEAUT32!__imp_VariantClear` at `0x18001d8bc`
- `OLEAUT32!__imp_VariantClear` at `0x18001d8c8`
- `OLEAUT32!__imp_VariantClear` at `0x18001d8d4`
- `OLEAUT32!__imp_VariantClear` at `0x18001d8e3`

## string_xrefs

- `0x18001dc48`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001d787`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001d8f8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001d9a5`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001da6b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001db0d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(_QWORD *a1, __int64 *a2)
{
  HRESULT Instance; // eax
  unsigned int v5; // ebx
  const char *v6; // r9
  LPVOID v7; // rcx
  __int64 result; // rax
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v11; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v13; // xmm8
  IRecordInfo *v14; // xmm9_8
  __int128 v15; // xmm6
  IRecordInfo *v16; // xmm7_8
  int v17; // ebx
  LPVOID v18; // rcx
  LPVOID v19; // rdi
  __int64 v20; // r15
  BSTR v21; // rax
  const char *v22; // r9
  OLECHAR *v23; // rbx
  int v24; // edi
  __int64 v25; // rcx
  LPVOID v26; // rcx
  int v27; // eax
  unsigned int v28; // ebx
  __int64 v29; // rcx
  __int64 v30; // rcx
  LPVOID v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  LPVOID v37; // rcx
  int ppv; // [rsp+20h] [rbp-198h]
  __int64 v39; // [rsp+30h] [rbp-188h] BYREF
  __int64 v40; // [rsp+38h] [rbp-180h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-178h] BYREF
  VARIANTARG v42; // [rsp+48h] [rbp-170h] BYREF
  VARIANTARG v43; // [rsp+60h] [rbp-158h] BYREF
  VARIANTARG v44; // [rsp+78h] [rbp-140h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-128h] BYREF
  BSTR v46; // [rsp+A8h] [rbp-110h]
  int v47[4]; // [rsp+B0h] [rbp-108h] BYREF
  IRecordInfo *v48; // [rsp+C0h] [rbp-F8h]
  __int128 v49; // [rsp+D0h] [rbp-E8h] BYREF
  IRecordInfo *v50; // [rsp+E0h] [rbp-D8h]
  __int128 v51; // [rsp+F0h] [rbp-C8h] BYREF
  IRecordInfo *v52; // [rsp+100h] [rbp-B8h]
  VARIANTARG v53; // [rsp+110h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]
  __int64 *v55; // [rsp+1D8h] [rbp+20h] BYREF

  v55 = 0;
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)&v55);
  try
  {
    v5 = Instance;
    if ( Instance >= 0 )
    {
      v9 = v55;
      v10 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*v55 + 80);
      VariantInit(&pvarg);
      v11 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v44);
      v13 = *(_OWORD *)&v44.vt;
      v14 = v44.pRecInfo;
      VariantInit(&v43);
      v15 = *(_OWORD *)&v43.vt;
      v16 = v43.pRecInfo;
      VariantInit(&v42);
      *(_OWORD *)v47 = v11;
      v48 = pRecInfo;
      v49 = v13;
      v50 = v14;
      v51 = v15;
      v52 = v16;
      v53 = v42;
      v17 = v10(v9, &v53, &v51, &v49);
      VariantClear(&v42);
      VariantClear(&v43);
      VariantClear(&v44);
      VariantClear(&pvarg);
      if ( v17 >= 0 )
      {
        v40 = 0;
        v19 = v55;
        v20 = *v55;
        v21 = SysAllocString(L"\\Microsoft\\Windows\\Management\\Autopilot");
        v23 = v21;
        v46 = v21;
        if ( !v21 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x15F3,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v22);
        v24 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(v20 + 56))(v19, v21, &v40);
        SysFreeString(v23);
        if ( v24 >= 0 )
        {
          v39 = 0;
          if ( a1[3] > 7u )
            a1 = (_QWORD *)*a1;
          wil::make_bstr(&bstrString, a1);
          v27 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v40 + 104LL))(v40, bstrString, &v39);
          v28 = v27;
          if ( v27 >= 0 )
          {
            if ( v39 )
            {
              v35 = *a2;
              *a2 = v39;
              v39 = v35;
              if ( bstrString )
              {
                SysFreeString(bstrString);
                v35 = v39;
              }
              if ( v35 )
              {
                v39 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
              }
              v36 = v40;
              if ( v40 )
              {
                v40 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              }
              v37 = v55;
              if ( v55 )
              {
                v55 = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v37 + 16LL))(v37);
              }
              result = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x66,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                (const char *)0x8000FFFFLL,
                (int)v47);
              if ( bstrString )
                SysFreeString(bstrString);
              v32 = v39;
              if ( v39 )
              {
                v39 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
              }
              v33 = v40;
              if ( v40 )
              {
                v40 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              }
              v34 = v55;
              if ( v55 )
              {
                v55 = 0;
                (*(void (__fastcall **)(_QWORD *, _QWORD))(*v34 + 16LL))(v34, *v34);
              }
              result = 2147549183LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x65,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
              (const char *)(unsigned int)v27,
              (int)v47);
            if ( bstrString )
              SysFreeString(bstrString);
            v29 = v39;
            if ( v39 )
            {
              v39 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            }
            v30 = v40;
            if ( v40 )
            {
              v40 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            }
            v31 = v55;
            if ( v55 )
            {
              v55 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
            }
            result = v28;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x61,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
            (const char *)(unsigned int)v24,
            (int)v47);
          v25 = v40;
          if ( v40 )
          {
            v40 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          v26 = v55;
          if ( v55 )
          {
            v55 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
          }
          result = (unsigned int)v24;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
          (const char *)(unsigned int)v17,
          (int)v47);
        v18 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
        }
        result = (unsigned int)v17;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
      v7 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
      }
      result = v5;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6C,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18001d70c  mov     rax, rsp
0x18001d70f  mov     [rax+8], rbx
0x18001d713  push    rsi
0x18001d714  push    rdi
0x18001d715  push    r12
0x18001d717  push    r14
0x18001d719  push    r15
0x18001d71b  sub     rsp, 190h
0x18001d722  movaps  xmmword ptr [rax-38h], xmm6
0x18001d726  movaps  xmmword ptr [rax-48h], xmm7
0x18001d72a  movaps  xmmword ptr [rax-58h], xmm8
0x18001d72f  movaps  xmmword ptr [rax-68h], xmm9
0x18001d734  movaps  xmmword ptr [rax-78h], xmm10
0x18001d739  movaps  xmmword ptr [rax-88h], xmm11
0x18001d741  mov     r14, rdx
0x18001d744  mov     rsi, rcx
0x18001d747  xor     r12d, r12d
0x18001d74a  mov     [rax+18h], r12d
0x18001d74e  mov     [rax+20h], r12
0x18001d752  lea     rax, [rax+20h]
0x18001d756  mov     qword ptr [rsp+1B8h+ppv], rax; int
0x18001d75b  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18001d762  xor     edx, edx; pUnkOuter
0x18001d764  lea     r8d, [r12+1]; dwClsContext
0x18001d769  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001d770  call    cs:__imp_CoCreateInstance
0x18001d776  mov     ebx, eax
0x18001d778  test    eax, eax
0x18001d77a  jns     short loc_18001D7C2
0x18001d77c  mov     rcx, [rsp+1B8h]; this
0x18001d784  mov     r9d, eax; char *
0x18001d787  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001d78e  lea     edx, [r12+5Dh]; void *
0x18001d793  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d798  nop
0x18001d799  mov     rcx, [rsp+1B8h+arg_18]
0x18001d7a1  test    rcx, rcx
0x18001d7a4  jz      short loc_18001D7BB
0x18001d7a6  mov     [rsp+1B8h+arg_18], r12
0x18001d7ae  mov     rax, [rcx]
0x18001d7b1  mov     rax, [rax+10h]
0x18001d7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7ba  nop
0x18001d7bb  mov     eax, ebx
0x18001d7bd  jmp     loc_18001DC12
0x18001d7c2  mov     rdi, [rsp+1B8h+arg_18]
0x18001d7ca  mov     rax, [rdi]
0x18001d7cd  mov     rbx, [rax+50h]
0x18001d7d1  lea     rcx, [rsp+1B8h+pvarg]; pvarg
0x18001d7d9  call    cs:__imp_VariantInit
0x18001d7df  nop
0x18001d7e0  movups  xmm10, xmmword ptr [rsp+1B8h+pvarg]
0x18001d7e9  movsd   xmm11, qword ptr [rsp+1B8h+pvarg+10h]
0x18001d7f3  lea     rcx, [rsp+1B8h+var_140]; pvarg
0x18001d7f8  call    cs:__imp_VariantInit
0x18001d7fe  nop
0x18001d7ff  movups  xmm8, xmmword ptr [rsp+1B8h+var_140]
0x18001d805  movsd   xmm9, qword ptr [rsp+1B8h+var_140+10h]
0x18001d80f  lea     rcx, [rsp+1B8h+var_158]; pvarg
0x18001d814  call    cs:__imp_VariantInit
0x18001d81a  nop
0x18001d81b  movups  xmm6, xmmword ptr [rsp+1B8h+var_158]
0x18001d820  movsd   xmm7, qword ptr [rsp+1B8h+var_158+10h]
0x18001d826  lea     rcx, [rsp+1B8h+var_170]; pvarg
0x18001d82b  call    cs:__imp_VariantInit
0x18001d831  nop
0x18001d832  movups  xmm0, xmmword ptr [rsp+1B8h+var_170]
0x18001d837  movsd   xmm1, qword ptr [rsp+1B8h+var_170+10h]
0x18001d83d  movaps  xmmword ptr [rsp+1B8h+var_108], xmm10
0x18001d846  movsd   [rsp+1B8h+var_F8], xmm11
0x18001d850  movaps  [rsp+1B8h+var_E8], xmm8
0x18001d859  movsd   [rsp+1B8h+var_D8], xmm9
0x18001d863  movaps  [rsp+1B8h+var_C8], xmm6
0x18001d86b  movsd   [rsp+1B8h+var_B8], xmm7
0x18001d874  movaps  [rsp+1B8h+var_A8], xmm0
0x18001d87c  movsd   [rsp+1B8h+var_98], xmm1
0x18001d885  lea     rax, [rsp+1B8h+var_108]
0x18001d88d  mov     qword ptr [rsp+1B8h+ppv], rax; int
0x18001d892  lea     r9, [rsp+1B8h+var_E8]
0x18001d89a  lea     r8, [rsp+1B8h+var_C8]
0x18001d8a2  lea     rdx, [rsp+1B8h+var_A8]
0x18001d8aa  mov     rcx, rdi
0x18001d8ad  mov     rax, rbx
0x18001d8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8b5  mov     ebx, eax
0x18001d8b7  lea     rcx, [rsp+1B8h+var_170]; pvarg
0x18001d8bc  call    cs:__imp_VariantClear
0x18001d8c2  nop
0x18001d8c3  lea     rcx, [rsp+1B8h+var_158]; pvarg
0x18001d8c8  call    cs:__imp_VariantClear
0x18001d8ce  nop
0x18001d8cf  lea     rcx, [rsp+1B8h+var_140]; pvarg
0x18001d8d4  call    cs:__imp_VariantClear
0x18001d8da  nop
0x18001d8db  lea     rcx, [rsp+1B8h+pvarg]; pvarg
0x18001d8e3  call    cs:__imp_VariantClear
0x18001d8e9  test    ebx, ebx
0x18001d8eb  jns     short loc_18001D933
0x18001d8ed  mov     rcx, [rsp+1B8h]; this
0x18001d8f5  mov     r9d, ebx; char *
0x18001d8f8  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001d8ff  mov     edx, 5Eh ; '^'; void *
0x18001d904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d909  nop
0x18001d90a  mov     rcx, [rsp+1B8h+arg_18]
0x18001d912  test    rcx, rcx
0x18001d915  jz      short loc_18001D92C
0x18001d917  mov     [rsp+1B8h+arg_18], r12
0x18001d91f  mov     rax, [rcx]
0x18001d922  mov     rax, [rax+10h]
0x18001d926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d92b  nop
0x18001d92c  mov     eax, ebx
0x18001d92e  jmp     loc_18001DC12
0x18001d933  mov     [rsp+1B8h+var_180], r12
0x18001d938  mov     rdi, [rsp+1B8h+arg_18]
0x18001d940  mov     r15, [rdi]
0x18001d943  lea     rcx, psz; "\\Microsoft\\Windows\\Management\\Autop"...
0x18001d94a  call    cs:__imp_SysAllocString
0x18001d950  mov     rbx, rax
0x18001d953  mov     [rsp+1B8h+var_110], rax
0x18001d95b  mov     [rsp+1B8h+arg_10], 1
0x18001d966  mov     rcx, [rsp+1B8h]; this
0x18001d96e  test    rax, rax
0x18001d971  jz      loc_18001DC48
0x18001d977  lea     r8, [rsp+1B8h+var_180]
0x18001d97c  mov     rdx, rbx
0x18001d97f  mov     rcx, rdi
0x18001d982  mov     rax, [r15+38h]
0x18001d986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d98b  mov     edi, eax
0x18001d98d  mov     rcx, rbx; bstrString
0x18001d990  call    cs:__imp_SysFreeString
0x18001d996  test    edi, edi
0x18001d998  jns     short loc_18001D9FC
0x18001d99a  mov     rcx, [rsp+1B8h]; this
0x18001d9a2  mov     r9d, edi; char *
0x18001d9a5  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001d9ac  mov     edx, 61h ; 'a'; void *
0x18001d9b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d9b6  nop
0x18001d9b7  mov     rcx, [rsp+1B8h+var_180]
0x18001d9bc  test    rcx, rcx
0x18001d9bf  jz      short loc_18001D9D3
0x18001d9c1  mov     [rsp+1B8h+var_180], r12
0x18001d9c6  mov     rax, [rcx]
0x18001d9c9  mov     rax, [rax+10h]
0x18001d9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9d2  nop
0x18001d9d3  mov     rcx, [rsp+1B8h+arg_18]
0x18001d9db  test    rcx, rcx
0x18001d9de  jz      short loc_18001D9F5
0x18001d9e0  mov     [rsp+1B8h+arg_18], r12
0x18001d9e8  mov     rax, [rcx]
0x18001d9eb  mov     rax, [rax+10h]
0x18001d9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9f4  nop
0x18001d9f5  mov     eax, edi
0x18001d9f7  jmp     loc_18001DC12
0x18001d9fc  mov     [rsp+1B8h+var_188], r12
0x18001da01  cmp     qword ptr [rsi+18h], 7
0x18001da06  jbe     short loc_18001DA0B
0x18001da08  mov     rsi, [rsi]
0x18001da0b  mov     rdx, rsi
0x18001da0e  lea     rcx, [rsp+1B8h+bstrString]
0x18001da13  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18001da18  nop
0x18001da19  mov     rbx, [rsp+1B8h+var_180]
0x18001da1e  mov     rax, [rbx]
0x18001da21  mov     rdi, [rax+68h]
0x18001da25  mov     rcx, [rsp+1B8h+var_188]
0x18001da2a  test    rcx, rcx
0x18001da2d  jz      short loc_18001DA41
0x18001da2f  mov     [rsp+1B8h+var_188], r12
0x18001da34  mov     rdx, [rcx]
0x18001da37  mov     rax, [rdx+10h]
0x18001da3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da40  nop
0x18001da41  lea     r8, [rsp+1B8h+var_188]
0x18001da46  mov     rdx, [rsp+1B8h+bstrString]
0x18001da4b  mov     rcx, rbx
0x18001da4e  mov     rax, rdi
0x18001da51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da56  mov     ebx, eax
0x18001da58  test    eax, eax
0x18001da5a  jns     loc_18001DAEF
0x18001da60  mov     rcx, [rsp+1B8h]; this
0x18001da68  mov     r9d, eax; char *
0x18001da6b  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001da72  mov     edx, 65h ; 'e'; void *
0x18001da77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da7c  nop
0x18001da7d  mov     rcx, [rsp+1B8h+bstrString]; bstrString
0x18001da82  test    rcx, rcx
0x18001da85  jz      short loc_18001DA8E
0x18001da87  call    cs:__imp_SysFreeString
0x18001da8d  nop
0x18001da8e  mov     rcx, [rsp+1B8h+var_188]
0x18001da93  test    rcx, rcx
0x18001da96  jz      short loc_18001DAAA
0x18001da98  mov     [rsp+1B8h+var_188], r12
0x18001da9d  mov     rax, [rcx]
0x18001daa0  mov     rax, [rax+10h]
0x18001daa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daa9  nop
0x18001daaa  mov     rcx, [rsp+1B8h+var_180]
0x18001daaf  test    rcx, rcx
0x18001dab2  jz      short loc_18001DAC6
0x18001dab4  mov     [rsp+1B8h+var_180], r12
0x18001dab9  mov     rax, [rcx]
0x18001dabc  mov     rax, [rax+10h]
0x18001dac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dac5  nop
0x18001dac6  mov     rcx, [rsp+1B8h+arg_18]
0x18001dace  test    rcx, rcx
0x18001dad1  jz      short loc_18001DAE8
0x18001dad3  mov     [rsp+1B8h+arg_18], r12
0x18001dadb  mov     rax, [rcx]
0x18001dade  mov     rax, [rax+10h]
0x18001dae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dae7  nop
0x18001dae8  mov     eax, ebx
0x18001daea  jmp     loc_18001DC12
0x18001daef  mov     rax, [rsp+1B8h+var_188]
0x18001daf4  test    rax, rax
0x18001daf7  jnz     loc_18001DB8F
0x18001dafd  mov     rcx, [rsp+1B8h]; this
0x18001db05  mov     ebx, 8000FFFFh
0x18001db0a  mov     r9d, ebx; char *
0x18001db0d  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001db14  lea     edx, [rax+66h]; void *
0x18001db17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db1c  nop
0x18001db1d  mov     rcx, [rsp+1B8h+bstrString]; bstrString
0x18001db22  test    rcx, rcx
0x18001db25  jz      short loc_18001DB2E
0x18001db27  call    cs:__imp_SysFreeString
0x18001db2d  nop
0x18001db2e  mov     rcx, [rsp+1B8h+var_188]
0x18001db33  test    rcx, rcx
0x18001db36  jz      short loc_18001DB4A
0x18001db38  mov     [rsp+1B8h+var_188], r12
0x18001db3d  mov     rax, [rcx]
0x18001db40  mov     rax, [rax+10h]
0x18001db44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db49  nop
0x18001db4a  mov     rcx, [rsp+1B8h+var_180]
0x18001db4f  test    rcx, rcx
0x18001db52  jz      short loc_18001DB66
0x18001db54  mov     [rsp+1B8h+var_180], r12
0x18001db59  mov     rax, [rcx]
0x18001db5c  mov     rax, [rax+10h]
0x18001db60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db65  nop
0x18001db66  mov     rcx, [rsp+1B8h+arg_18]
0x18001db6e  test    rcx, rcx
0x18001db71  jz      short loc_18001DB88
0x18001db73  mov     [rsp+1B8h+arg_18], r12
0x18001db7b  mov     rdx, [rcx]
0x18001db7e  mov     rax, [rdx+10h]
0x18001db82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db87  nop
0x18001db88  mov     eax, ebx
0x18001db8a  jmp     loc_18001DC12
0x18001db8f  mov     rdx, [r14]
0x18001db92  mov     [r14], rax
0x18001db95  mov     [rsp+1B8h+var_188], rdx
0x18001db9a  mov     rcx, [rsp+1B8h+bstrString]; bstrString
0x18001db9f  test    rcx, rcx
0x18001dba2  jz      short loc_18001DBAF
0x18001dba4  call    cs:__imp_SysFreeString
0x18001dbaa  mov     rdx, [rsp+1B8h+var_188]
0x18001dbaf  test    rdx, rdx
0x18001dbb2  jz      short loc_18001DBC9
0x18001dbb4  mov     [rsp+1B8h+var_188], r12
0x18001dbb9  mov     rax, [rdx]
0x18001dbbc  mov     rcx, rdx
0x18001dbbf  mov     rax, [rax+10h]
0x18001dbc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbc8  nop
0x18001dbc9  mov     rcx, [rsp+1B8h+var_180]
0x18001dbce  test    rcx, rcx
0x18001dbd1  jz      short loc_18001DBE5
0x18001dbd3  mov     [rsp+1B8h+var_180], r12
0x18001dbd8  mov     rax, [rcx]
0x18001dbdb  mov     rax, [rax+10h]
0x18001dbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbe4  nop
0x18001dbe5  mov     rcx, [rsp+1B8h+arg_18]
0x18001dbed  test    rcx, rcx
0x18001dbf0  jz      short loc_18001DC07
0x18001dbf2  mov     [rsp+1B8h+arg_18], r12
0x18001dbfa  mov     rax, [rcx]
0x18001dbfd  mov     rax, [rax+10h]
0x18001dc01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc06  nop
0x18001dc07  xor     eax, eax
0x18001dc09  jmp     short loc_18001DC12
0x18001dc0b  mov     eax, [rsp+1B8h+arg_10]
0x18001dc12  lea     r11, [rsp+1B8h+var_28]
  ... truncated ...
```
