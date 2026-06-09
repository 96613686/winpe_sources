# Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<IRegisteredTask> &)

- ea: `0x18001dea4`
- end: `0x18001e448`
- name: `?GetNamedAutopilotTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIRegisteredTask@@@WRL@4@@Z`
- size: `1444`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016ba8`
- `0x18001dcf4`
- `0x18001ddcc`

## callees

- `0x180010764`
- `0x18001dea4`
- `0x18001e83c`
- `0x18001e860`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001df08`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001df08`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e118`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e118`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e164`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e261`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e307`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e38a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e164`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e261`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e307`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e38a`
- `OLEAUT32!__imp_VariantInit` at `0x18001df77`
- `OLEAUT32!__imp_VariantInit` at `0x18001df9c`
- `OLEAUT32!__imp_VariantInit` at `0x18001dfbe`
- `OLEAUT32!__imp_VariantInit` at `0x18001dfdb`
- `OLEAUT32!__imp_VariantInit` at `0x18001df77`
- `OLEAUT32!__imp_VariantInit` at `0x18001df9c`
- `OLEAUT32!__imp_VariantInit` at `0x18001dfbe`
- `OLEAUT32!__imp_VariantInit` at `0x18001dfdb`
- `OLEAUT32!__imp_VariantClear` at `0x18001e072`
- `OLEAUT32!__imp_VariantClear` at `0x18001e084`
- `OLEAUT32!__imp_VariantClear` at `0x18001e096`
- `OLEAUT32!__imp_VariantClear` at `0x18001e0ab`
- `OLEAUT32!__imp_VariantClear` at `0x18001e072`
- `OLEAUT32!__imp_VariantClear` at `0x18001e084`
- `OLEAUT32!__imp_VariantClear` at `0x18001e096`
- `OLEAUT32!__imp_VariantClear` at `0x18001e0ab`

## string_xrefs

- `0x18001e435`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001df25`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001e0c6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001e17f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001e245`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001e2ed`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

## pseudocode

```c
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
0x18001dea4  mov     rax, rsp
0x18001dea7  mov     [rax+8], rbx
0x18001deab  push    rsi
0x18001deac  push    rdi
0x18001dead  push    r12
0x18001deaf  push    r14
0x18001deb1  push    r15
0x18001deb3  sub     rsp, 190h
0x18001deba  movaps  xmmword ptr [rax-38h], xmm6
0x18001debe  movaps  xmmword ptr [rax-48h], xmm7
0x18001dec2  movaps  xmmword ptr [rax-58h], xmm8
0x18001dec7  movaps  xmmword ptr [rax-68h], xmm9
0x18001decc  movaps  xmmword ptr [rax-78h], xmm10
0x18001ded1  movaps  xmmword ptr [rax-88h], xmm11
0x18001ded9  mov     r14, rdx
0x18001dedc  mov     rsi, rcx
0x18001dedf  xor     r12d, r12d
0x18001dee2  mov     [rax+18h], r12d
0x18001dee6  mov     [rax+20h], r12
0x18001deea  lea     rax, [rax+20h]
0x18001deee  mov     qword ptr [rsp+1B8h+ppv], rax; int
0x18001def3  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18001defa  xor     edx, edx; pUnkOuter
0x18001defc  lea     r8d, [r12+1]; dwClsContext
0x18001df01  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001df08  call    cs:__imp_CoCreateInstance
0x18001df0f  nop     dword ptr [rax+rax+00h]
0x18001df14  mov     ebx, eax
0x18001df16  test    eax, eax
0x18001df18  jns     short loc_18001DF60
0x18001df1a  mov     rcx, [rsp+1B8h]; this
0x18001df22  mov     r9d, eax; char *
0x18001df25  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001df2c  lea     edx, [r12+5Dh]; void *
0x18001df31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df36  nop
0x18001df37  mov     rcx, [rsp+1B8h+arg_18]
0x18001df3f  test    rcx, rcx
0x18001df42  jz      short loc_18001DF59
0x18001df44  mov     [rsp+1B8h+arg_18], r12
0x18001df4c  mov     rax, [rcx]
0x18001df4f  mov     rax, [rax+10h]
0x18001df53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df58  nop
0x18001df59  mov     eax, ebx
0x18001df5b  jmp     loc_18001E3FE
0x18001df60  mov     rdi, [rsp+1B8h+arg_18]
0x18001df68  mov     rax, [rdi]
0x18001df6b  mov     rbx, [rax+50h]
0x18001df6f  lea     rcx, [rsp+1B8h+pvarg]; pvarg
0x18001df77  call    cs:__imp_VariantInit
0x18001df7e  nop     dword ptr [rax+rax+00h]
0x18001df83  nop
0x18001df84  movups  xmm10, xmmword ptr [rsp+1B8h+pvarg]
0x18001df8d  movsd   xmm11, qword ptr [rsp+1B8h+pvarg+10h]
0x18001df97  lea     rcx, [rsp+1B8h+var_140]; pvarg
0x18001df9c  call    cs:__imp_VariantInit
0x18001dfa3  nop     dword ptr [rax+rax+00h]
0x18001dfa8  nop
0x18001dfa9  movups  xmm8, xmmword ptr [rsp+1B8h+var_140]
0x18001dfaf  movsd   xmm9, qword ptr [rsp+1B8h+var_140+10h]
0x18001dfb9  lea     rcx, [rsp+1B8h+var_158]; pvarg
0x18001dfbe  call    cs:__imp_VariantInit
0x18001dfc5  nop     dword ptr [rax+rax+00h]
0x18001dfca  nop
0x18001dfcb  movups  xmm6, xmmword ptr [rsp+1B8h+var_158]
0x18001dfd0  movsd   xmm7, qword ptr [rsp+1B8h+var_158+10h]
0x18001dfd6  lea     rcx, [rsp+1B8h+var_170]; pvarg
0x18001dfdb  call    cs:__imp_VariantInit
0x18001dfe2  nop     dword ptr [rax+rax+00h]
0x18001dfe7  nop
0x18001dfe8  movups  xmm0, xmmword ptr [rsp+1B8h+var_170]
0x18001dfed  movsd   xmm1, qword ptr [rsp+1B8h+var_170+10h]
0x18001dff3  movaps  xmmword ptr [rsp+1B8h+var_108], xmm10
0x18001dffc  movsd   [rsp+1B8h+var_F8], xmm11
0x18001e006  movaps  [rsp+1B8h+var_E8], xmm8
0x18001e00f  movsd   [rsp+1B8h+var_D8], xmm9
0x18001e019  movaps  [rsp+1B8h+var_C8], xmm6
0x18001e021  movsd   [rsp+1B8h+var_B8], xmm7
0x18001e02a  movaps  [rsp+1B8h+var_A8], xmm0
0x18001e032  movsd   [rsp+1B8h+var_98], xmm1
0x18001e03b  lea     rax, [rsp+1B8h+var_108]
0x18001e043  mov     qword ptr [rsp+1B8h+ppv], rax; int
0x18001e048  lea     r9, [rsp+1B8h+var_E8]
0x18001e050  lea     r8, [rsp+1B8h+var_C8]
0x18001e058  lea     rdx, [rsp+1B8h+var_A8]
0x18001e060  mov     rcx, rdi
0x18001e063  mov     rax, rbx
0x18001e066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e06b  mov     ebx, eax
0x18001e06d  lea     rcx, [rsp+1B8h+var_170]; pvarg
0x18001e072  call    cs:__imp_VariantClear
0x18001e079  nop     dword ptr [rax+rax+00h]
0x18001e07e  nop
0x18001e07f  lea     rcx, [rsp+1B8h+var_158]; pvarg
0x18001e084  call    cs:__imp_VariantClear
0x18001e08b  nop     dword ptr [rax+rax+00h]
0x18001e090  nop
0x18001e091  lea     rcx, [rsp+1B8h+var_140]; pvarg
0x18001e096  call    cs:__imp_VariantClear
0x18001e09d  nop     dword ptr [rax+rax+00h]
0x18001e0a2  nop
0x18001e0a3  lea     rcx, [rsp+1B8h+pvarg]; pvarg
0x18001e0ab  call    cs:__imp_VariantClear
0x18001e0b2  nop     dword ptr [rax+rax+00h]
0x18001e0b7  test    ebx, ebx
0x18001e0b9  jns     short loc_18001E101
0x18001e0bb  mov     rcx, [rsp+1B8h]; this
0x18001e0c3  mov     r9d, ebx; char *
0x18001e0c6  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e0cd  mov     edx, 5Eh ; '^'; void *
0x18001e0d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e0d7  nop
0x18001e0d8  mov     rcx, [rsp+1B8h+arg_18]
0x18001e0e0  test    rcx, rcx
0x18001e0e3  jz      short loc_18001E0FA
0x18001e0e5  mov     [rsp+1B8h+arg_18], r12
0x18001e0ed  mov     rax, [rcx]
0x18001e0f0  mov     rax, [rax+10h]
0x18001e0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0f9  nop
0x18001e0fa  mov     eax, ebx
0x18001e0fc  jmp     loc_18001E3FE
0x18001e101  mov     [rsp+1B8h+var_180], r12
0x18001e106  mov     rdi, [rsp+1B8h+arg_18]
0x18001e10e  mov     r15, [rdi]
0x18001e111  lea     rcx, psz; "\\Microsoft\\Windows\\Management\\Autop"...
0x18001e118  call    cs:__imp_SysAllocString
0x18001e11f  nop     dword ptr [rax+rax+00h]
0x18001e124  mov     rbx, rax
0x18001e127  mov     [rsp+1B8h+var_110], rax
0x18001e12f  mov     [rsp+1B8h+arg_10], 1
0x18001e13a  mov     rcx, [rsp+1B8h]; this
0x18001e142  test    rax, rax
0x18001e145  jz      loc_18001E435
0x18001e14b  lea     r8, [rsp+1B8h+var_180]
0x18001e150  mov     rdx, rbx
0x18001e153  mov     rcx, rdi
0x18001e156  mov     rax, [r15+38h]
0x18001e15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e15f  mov     edi, eax
0x18001e161  mov     rcx, rbx; bstrString
0x18001e164  call    cs:__imp_SysFreeString
0x18001e16b  nop     dword ptr [rax+rax+00h]
0x18001e170  test    edi, edi
0x18001e172  jns     short loc_18001E1D6
0x18001e174  mov     rcx, [rsp+1B8h]; this
0x18001e17c  mov     r9d, edi; char *
0x18001e17f  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e186  mov     edx, 61h ; 'a'; void *
0x18001e18b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e190  nop
0x18001e191  mov     rcx, [rsp+1B8h+var_180]
0x18001e196  test    rcx, rcx
0x18001e199  jz      short loc_18001E1AD
0x18001e19b  mov     [rsp+1B8h+var_180], r12
0x18001e1a0  mov     rax, [rcx]
0x18001e1a3  mov     rax, [rax+10h]
0x18001e1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ac  nop
0x18001e1ad  mov     rcx, [rsp+1B8h+arg_18]
0x18001e1b5  test    rcx, rcx
0x18001e1b8  jz      short loc_18001E1CF
0x18001e1ba  mov     [rsp+1B8h+arg_18], r12
0x18001e1c2  mov     rax, [rcx]
0x18001e1c5  mov     rax, [rax+10h]
0x18001e1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ce  nop
0x18001e1cf  mov     eax, edi
0x18001e1d1  jmp     loc_18001E3FE
0x18001e1d6  mov     [rsp+1B8h+var_188], r12
0x18001e1db  cmp     qword ptr [rsi+18h], 7
0x18001e1e0  jbe     short loc_18001E1E5
0x18001e1e2  mov     rsi, [rsi]
0x18001e1e5  mov     rdx, rsi
0x18001e1e8  lea     rcx, [rsp+1B8h+bstrString]
0x18001e1ed  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18001e1f2  nop
0x18001e1f3  mov     rbx, [rsp+1B8h+var_180]
0x18001e1f8  mov     rax, [rbx]
0x18001e1fb  mov     rdi, [rax+68h]
0x18001e1ff  mov     rcx, [rsp+1B8h+var_188]
0x18001e204  test    rcx, rcx
0x18001e207  jz      short loc_18001E21B
0x18001e209  mov     [rsp+1B8h+var_188], r12
0x18001e20e  mov     rdx, [rcx]
0x18001e211  mov     rax, [rdx+10h]
0x18001e215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e21a  nop
0x18001e21b  lea     r8, [rsp+1B8h+var_188]
0x18001e220  mov     rdx, [rsp+1B8h+bstrString]
0x18001e225  mov     rcx, rbx
0x18001e228  mov     rax, rdi
0x18001e22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e230  mov     ebx, eax
0x18001e232  test    eax, eax
0x18001e234  jns     loc_18001E2CF
0x18001e23a  mov     rcx, [rsp+1B8h]; this
0x18001e242  mov     r9d, eax; char *
0x18001e245  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e24c  mov     edx, 65h ; 'e'; void *
0x18001e251  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e256  nop
0x18001e257  mov     rcx, [rsp+1B8h+bstrString]; bstrString
0x18001e25c  test    rcx, rcx
0x18001e25f  jz      short loc_18001E26E
0x18001e261  call    cs:__imp_SysFreeString
0x18001e268  nop     dword ptr [rax+rax+00h]
0x18001e26d  nop
0x18001e26e  mov     rcx, [rsp+1B8h+var_188]
0x18001e273  test    rcx, rcx
0x18001e276  jz      short loc_18001E28A
0x18001e278  mov     [rsp+1B8h+var_188], r12
0x18001e27d  mov     rax, [rcx]
0x18001e280  mov     rax, [rax+10h]
0x18001e284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e289  nop
0x18001e28a  mov     rcx, [rsp+1B8h+var_180]
0x18001e28f  test    rcx, rcx
0x18001e292  jz      short loc_18001E2A6
0x18001e294  mov     [rsp+1B8h+var_180], r12
0x18001e299  mov     rax, [rcx]
0x18001e29c  mov     rax, [rax+10h]
0x18001e2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2a5  nop
0x18001e2a6  mov     rcx, [rsp+1B8h+arg_18]
0x18001e2ae  test    rcx, rcx
0x18001e2b1  jz      short loc_18001E2C8
0x18001e2b3  mov     [rsp+1B8h+arg_18], r12
0x18001e2bb  mov     rax, [rcx]
0x18001e2be  mov     rax, [rax+10h]
0x18001e2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2c7  nop
0x18001e2c8  mov     eax, ebx
0x18001e2ca  jmp     loc_18001E3FE
0x18001e2cf  mov     rax, [rsp+1B8h+var_188]
0x18001e2d4  test    rax, rax
0x18001e2d7  jnz     loc_18001E375
0x18001e2dd  mov     rcx, [rsp+1B8h]; this
0x18001e2e5  mov     ebx, 8000FFFFh
0x18001e2ea  mov     r9d, ebx; char *
0x18001e2ed  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e2f4  lea     edx, [rax+66h]; void *
0x18001e2f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e2fc  nop
0x18001e2fd  mov     rcx, [rsp+1B8h+bstrString]; bstrString
0x18001e302  test    rcx, rcx
0x18001e305  jz      short loc_18001E314
0x18001e307  call    cs:__imp_SysFreeString
0x18001e30e  nop     dword ptr [rax+rax+00h]
0x18001e313  nop
0x18001e314  mov     rcx, [rsp+1B8h+var_188]
0x18001e319  test    rcx, rcx
0x18001e31c  jz      short loc_18001E330
0x18001e31e  mov     [rsp+1B8h+var_188], r12
0x18001e323  mov     rax, [rcx]
0x18001e326  mov     rax, [rax+10h]
0x18001e32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e32f  nop
0x18001e330  mov     rcx, [rsp+1B8h+var_180]
0x18001e335  test    rcx, rcx
0x18001e338  jz      short loc_18001E34C
0x18001e33a  mov     [rsp+1B8h+var_180], r12
0x18001e33f  mov     rax, [rcx]
0x18001e342  mov     rax, [rax+10h]
0x18001e346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e34b  nop
0x18001e34c  mov     rcx, [rsp+1B8h+arg_18]
0x18001e354  test    rcx, rcx
0x18001e357  jz      short loc_18001E36E
0x18001e359  mov     [rsp+1B8h+arg_18], r12
0x18001e361  mov     rdx, [rcx]
0x18001e364  mov     rax, [rdx+10h]
0x18001e368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e36d  nop
0x18001e36e  mov     eax, ebx
0x18001e370  jmp     loc_18001E3FE
0x18001e375  mov     rdx, [r14]
0x18001e378  mov     [r14], rax
0x18001e37b  mov     [rsp+1B8h+var_188], rdx
0x18001e380  mov     rcx, [rsp+1B8h+bstrString]; bstrString
0x18001e385  test    rcx, rcx
0x18001e388  jz      short loc_18001E39B
0x18001e38a  call    cs:__imp_SysFreeString
0x18001e391  nop     dword ptr [rax+rax+00h]
0x18001e396  mov     rdx, [rsp+1B8h+var_188]
0x18001e39b  test    rdx, rdx
0x18001e39e  jz      short loc_18001E3B5
0x18001e3a0  mov     [rsp+1B8h+var_188], r12
0x18001e3a5  mov     rax, [rdx]
0x18001e3a8  mov     rcx, rdx
0x18001e3ab  mov     rax, [rax+10h]
0x18001e3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3b4  nop
0x18001e3b5  mov     rcx, [rsp+1B8h+var_180]
0x18001e3ba  test    rcx, rcx
0x18001e3bd  jz      short loc_18001E3D1
0x18001e3bf  mov     [rsp+1B8h+var_180], r12
0x18001e3c4  mov     rax, [rcx]
0x18001e3c7  mov     rax, [rax+10h]
  ... truncated ...
```
