# CModelDownloadComponent::GenerateXMLModelFilesNode(void)

- ea: `0x14000f280`
- end: `0x14000f4cc`
- name: `?GenerateXMLModelFilesNode@CModelDownloadComponent@@AEAAJXZ`
- size: `588`
- prototype: `__int64 __fastcall(CModelDownloadComponent *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000d5a4`

## callees

- `0x14000985c`
- `0x14000c3ac`
- `0x14000f280`
- `0x14001d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14000f408`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14000f408`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000f304`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000f304`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f2bd`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f2bd`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f46b`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f46b`
- `OLEAUT32!__imp_VariantClear` at `0x14000f2ac`
- `OLEAUT32!__imp_VariantClear` at `0x14000f476`
- `OLEAUT32!__imp_VariantClear` at `0x14000f2ac`
- `OLEAUT32!__imp_VariantClear` at `0x14000f476`

## string_xrefs

- `0x14000f314`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(853)`
- `0x14000f320`: `CModelDownloadComponent::GenerateXMLModelFilesNode`
- `0x14000f37b`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(854)`
- `0x14000f394`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(858)`
- `0x14000f3c1`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(861)`
- `0x14000f3eb`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(862)`
- `0x14000f41b`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(867)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::GenerateXMLModelFilesNode(CModelDownloadComponent *this)
{
  const OLECHAR *v2; // rbx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdi
  __int64 v9; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG v12; // [rsp+50h] [rbp-20h] BYREF
  __int16 v13; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v14; // [rsp+A8h] [rbp+38h] BYREF
  LPVOID ppv; // [rsp+B0h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+B8h] [rbp+48h] BYREF

  ppv = 0;
  v14 = 0;
  v2 = (const OLECHAR *)((char *)this + 3736);
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(v2);
  if ( !pvarg.llVal && v2 )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(pvarg.cyVal.Hi);
  }
  v13 = 0;
  bstrString = 0;
  v3 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, &ppv);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v12 = pvarg;
    v5 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(*(_QWORD *)ppv + 464LL))(ppv, &v12, &v13);
    v4 = v5;
    if ( v5 >= 0 )
    {
      if ( v13 )
      {
        v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 360LL))(ppv, &v14);
        v4 = v6;
        if ( v6 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v14 + 56LL))(v14, &bstrString);
          v4 = v7;
          if ( v7 >= 0 )
          {
            if ( (unsigned int)_o__wcsnicmp(bstrString, L"ModelFiles") )
            {
              v4 = -2147200958;
              DoTraceMessage(
                2,
                "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                &NLInternal::s_tracingPrefix,
                L"CModelDownloadComponent::GenerateXMLModelFilesNode",
                L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(867)",
                -2147200958);
            }
            else
            {
              v8 = v14;
              if ( *((_QWORD *)this + 3073) != v14 )
              {
                if ( v14 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
                v9 = *((_QWORD *)this + 3073);
                if ( v9 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
                *((_QWORD *)this + 3073) = v8;
              }
            }
          }
          else
          {
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              &NLInternal::s_tracingPrefix,
              L"CModelDownloadComponent::GenerateXMLModelFilesNode",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(862)",
              v7);
          }
        }
        else
        {
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            &NLInternal::s_tracingPrefix,
            L"CModelDownloadComponent::GenerateXMLModelFilesNode",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(861)",
            v6);
        }
      }
      else
      {
        v4 = -2147418113;
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::GenerateXMLModelFilesNode",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(858)",
          -2147418113);
      }
    }
    else
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::GenerateXMLModelFilesNode",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(854)",
        v5);
    }
  }
  else
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::GenerateXMLModelFilesNode",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(853)",
      v3);
  }
  SysFreeString(bstrString);
  VariantClear(&pvarg);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v4;
}

```

## disassembly

```asm
0x14000f280  push    rbp
0x14000f282  push    rbx
0x14000f283  push    rsi
0x14000f284  push    rdi
0x14000f285  push    r14
0x14000f287  mov     rbp, rsp
0x14000f28a  sub     rsp, 70h
0x14000f28e  mov     rsi, rcx
0x14000f291  xor     r14d, r14d
0x14000f294  mov     [rbp+arg_10], r14
0x14000f298  mov     [rbp+arg_8], r14
0x14000f29c  lea     rbx, [rcx+0E98h]
0x14000f2a3  mov     word ptr [rbp+pvarg], r14w
0x14000f2a8  lea     rcx, [rbp+pvarg]; pvarg
0x14000f2ac  call    cs:__imp_VariantClear
0x14000f2b2  lea     eax, [r14+8]
0x14000f2b6  mov     word ptr [rbp+pvarg], ax
0x14000f2ba  mov     rcx, rbx; psz
0x14000f2bd  call    cs:__imp_SysAllocString
0x14000f2c3  mov     dword ptr [rbp+pvarg+8], eax
0x14000f2c6  mov     rcx, rax
0x14000f2c9  sar     rcx, 20h; int
0x14000f2cd  mov     dword ptr [rbp+pvarg+0Ch], ecx
0x14000f2d0  test    rax, rax
0x14000f2d3  jnz     short loc_14000F2DE
0x14000f2d5  test    rbx, rbx
0x14000f2d8  jnz     loc_14000F4B6
0x14000f2de  mov     [rbp+arg_0], r14w
0x14000f2e3  mov     [rbp+bstrString], r14
0x14000f2e7  lea     rax, [rbp+arg_10]
0x14000f2eb  mov     [rsp+70h+ppv], rax; ppv
0x14000f2f0  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x14000f2f7  xor     edx, edx; pUnkOuter
0x14000f2f9  lea     r8d, [rdx+17h]; dwClsContext
0x14000f2fd  lea     rcx, CLSID_DOMDocument60; rclsid
0x14000f304  call    cs:__imp_CoCreateInstance
0x14000f30a  mov     ebx, eax
0x14000f30c  test    eax, eax
0x14000f30e  jns     short loc_14000F344
0x14000f310  mov     [rsp+70h+var_48], eax
0x14000f314  lea     rax, aOnecoreuapEndu_48; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f31b  mov     [rsp+70h+ppv], rax
0x14000f320  lea     r9, aCmodeldownload_33; "CModelDownloadComponent::GenerateXMLMod"...
0x14000f327  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000f32e  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000f335  mov     ecx, 2; int
0x14000f33a  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000f33f  jmp     loc_14000F467
0x14000f344  mov     rcx, [rbp+arg_10]
0x14000f348  movups  xmm0, xmmword ptr [rbp+pvarg]
0x14000f34c  movaps  [rbp+var_20], xmm0
0x14000f350  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x14000f355  movsd   [rbp+var_10], xmm1
0x14000f35a  mov     rax, [rcx]
0x14000f35d  lea     r8, [rbp+arg_0]
0x14000f361  lea     rdx, [rbp+var_20]
0x14000f365  mov     rax, [rax+1D0h]
0x14000f36c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f371  mov     ebx, eax
0x14000f373  test    eax, eax
0x14000f375  jns     short loc_14000F384
0x14000f377  mov     [rsp+70h+var_48], eax
0x14000f37b  lea     rax, aOnecoreuapEndu_61; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f382  jmp     short loc_14000F31B
0x14000f384  cmp     [rbp+arg_0], r14w
0x14000f389  jnz     short loc_14000F3A0
0x14000f38b  mov     ebx, 8000FFFFh
0x14000f390  mov     [rsp+70h+var_48], ebx
0x14000f394  lea     rax, aOnecoreuapEndu_78; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f39b  jmp     loc_14000F31B
0x14000f3a0  mov     rcx, [rbp+arg_10]
0x14000f3a4  mov     rax, [rcx]
0x14000f3a7  lea     rdx, [rbp+arg_8]
0x14000f3ab  mov     rax, [rax+168h]
0x14000f3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f3b7  mov     ebx, eax
0x14000f3b9  test    eax, eax
0x14000f3bb  jns     short loc_14000F3CD
0x14000f3bd  mov     [rsp+70h+var_48], eax
0x14000f3c1  lea     rax, aOnecoreuapEndu_74; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f3c8  jmp     loc_14000F31B
0x14000f3cd  mov     rcx, [rbp+arg_8]
0x14000f3d1  mov     rax, [rcx]
0x14000f3d4  lea     rdx, [rbp+bstrString]
0x14000f3d8  mov     rax, [rax+38h]
0x14000f3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f3e1  mov     ebx, eax
0x14000f3e3  test    eax, eax
0x14000f3e5  jns     short loc_14000F3F7
0x14000f3e7  mov     [rsp+70h+var_48], eax
0x14000f3eb  lea     rax, aOnecoreuapEndu_55; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f3f2  jmp     loc_14000F31B
0x14000f3f7  mov     r8d, 104h
0x14000f3fd  lea     rdx, aModelfiles; "ModelFiles"
0x14000f404  mov     rcx, [rbp+bstrString]
0x14000f408  call    cs:__imp__o__wcsnicmp
0x14000f40e  test    eax, eax
0x14000f410  jz      short loc_14000F427
0x14000f412  mov     ebx, 80045042h
0x14000f417  mov     [rsp+70h+var_48], ebx
0x14000f41b  lea     rax, aOnecoreuapEndu_100; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f422  jmp     loc_14000F31B
0x14000f427  mov     rdi, [rbp+arg_8]
0x14000f42b  cmp     [rsi+6008h], rdi
0x14000f432  jz      short loc_14000F467
0x14000f434  test    rdi, rdi
0x14000f437  jz      short loc_14000F448
0x14000f439  mov     rax, [rdi]
0x14000f43c  mov     rcx, rdi
0x14000f43f  mov     rax, [rax+8]
0x14000f443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f448  mov     rcx, [rsi+6008h]
0x14000f44f  test    rcx, rcx
0x14000f452  jz      short loc_14000F460
0x14000f454  mov     rax, [rcx]
0x14000f457  mov     rax, [rax+10h]
0x14000f45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f460  mov     [rsi+6008h], rdi
0x14000f467  mov     rcx, [rbp+bstrString]; bstrString
0x14000f46b  call    cs:__imp_SysFreeString
0x14000f471  nop
0x14000f472  lea     rcx, [rbp+pvarg]; pvarg
0x14000f476  call    cs:__imp_VariantClear
0x14000f47c  nop
0x14000f47d  mov     rcx, [rbp+arg_8]
0x14000f481  test    rcx, rcx
0x14000f484  jz      short loc_14000F493
0x14000f486  mov     rax, [rcx]
0x14000f489  mov     rax, [rax+10h]
0x14000f48d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f492  nop
0x14000f493  mov     rcx, [rbp+arg_10]
0x14000f497  test    rcx, rcx
0x14000f49a  jz      short loc_14000F4A9
0x14000f49c  mov     rax, [rcx]
0x14000f49f  mov     rax, [rax+10h]
0x14000f4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f4a8  nop
0x14000f4a9  mov     eax, ebx
0x14000f4ab  add     rsp, 70h
0x14000f4af  pop     r14
0x14000f4b1  pop     rdi
0x14000f4b2  pop     rsi
0x14000f4b3  pop     rbx
0x14000f4b4  pop     rbp
0x14000f4b5  retn
0x14000f4b6  mov     eax, 0Ah
0x14000f4bb  mov     word ptr [rbp+pvarg], ax
0x14000f4bf  mov     dword ptr [rbp+pvarg+8], 8007000Eh
0x14000f4c6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
