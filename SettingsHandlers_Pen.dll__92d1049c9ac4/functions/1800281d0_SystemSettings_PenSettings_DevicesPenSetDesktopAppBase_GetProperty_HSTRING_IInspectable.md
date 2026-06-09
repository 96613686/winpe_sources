# SystemSettings::PenSettings::DevicesPenSetDesktopAppBase::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x1800281d0`
- end: `0x1800284f1`
- name: `?GetProperty@DevicesPenSetDesktopAppBase@PenSettings@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `801`
- prototype: `int(SystemSettings::PenSettings::DevicesPenSetDesktopAppBase *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008128`
- `0x18000a2bc`
- `0x180012868`
- `0x1800168b4`
- `0x180019a40`
- `0x180019b90`
- `0x180027dcc`
- `0x1800281d0`
- `0x18002b2b4`
- `0x18002ee30`
- `0x180052e6c`
- `0x18005d010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18002829b`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18002829b`

## string_xrefs

- `0x18002825e`: `CustomAppPath`
- `0x1800282ef`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x1800283db`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002844d`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::PenSettings::DevicesPenSetDesktopAppBase::GetProperty(
        SystemSettings::PenSettings::DevicesPenSetDesktopAppBase *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  __int64 v5; // r9
  void *v6; // rdi
  __int64 (__fastcall *v7)(void *, _QWORD, __int64 *); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  void *v10; // rdi
  int (__fastcall *v11)(void *, const PROPERTYKEY *, __int64 *); // rbx
  const unsigned __int16 *v12; // rbx
  __int64 v13; // r8
  int v14; // edi
  int String; // eax
  __int64 v16; // rdx
  int v18; // [rsp+20h] [rbp-59h]
  const unsigned __int16 *v19; // [rsp+30h] [rbp-49h] BYREF
  __int64 v20; // [rsp+38h] [rbp-41h]
  __int64 v21; // [rsp+40h] [rbp-39h]
  __int64 v22; // [rsp+48h] [rbp-31h] BYREF
  __int64 v23; // [rsp+50h] [rbp-29h]
  __int64 v24; // [rsp+58h] [rbp-21h]
  __int64 v25; // [rsp+60h] [rbp-19h] BYREF
  __int64 v26; // [rsp+68h] [rbp-11h]
  __int64 v27; // [rsp+70h] [rbp-9h]
  PCWSTR pszPath; // [rsp+78h] [rbp-1h] BYREF
  __int64 v29; // [rsp+80h] [rbp+7h]
  __int64 v30; // [rsp+88h] [rbp+Fh]
  const unsigned __int16 *v31; // [rsp+90h] [rbp+17h] BYREF
  __int64 v32; // [rsp+98h] [rbp+1Fh]
  __int64 v33; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  void *ppv; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180067C70, (const unsigned __int16 *)a3) )
  {
    ppv = 0;
    SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(
      *((_DWORD *)this + 68),
      (unsigned int)&ppv,
      0,
      0,
      0,
      0);
    pszPath = 0;
    v29 = 0;
    v30 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    v29 = -1;
    v30 = -1;
    if ( (int)SHRegAllocData(HKEY_CURRENT_USER, (const unsigned __int16 *)ppv, L"CustomAppPath", v5, (void **)&pszPath) >= 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      if ( SHCreateItemFromParsingName(pszPath, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv) >= 0 )
      {
        v25 = 0;
        v26 = 0;
        v27 = 0;
        v6 = ppv;
        v7 = *(__int64 (__fastcall **)(void *, _QWORD, __int64 *))(*(_QWORD *)ppv + 40LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v25);
        v26 = -1;
        v27 = -1;
        v8 = v7(v6, 0, &v25);
        v9 = v8;
        if ( v8 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9C1,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
            (const char *)(unsigned int)v8,
            v18);
LABEL_25:
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v25);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
          return v9;
        }
        v22 = 0;
        v23 = 0;
        v24 = 0;
        v19 = 0;
        v20 = 0;
        v21 = 0;
        v10 = ppv;
        v11 = *(int (__fastcall **)(void *, const PROPERTYKEY *, __int64 *))(*(_QWORD *)ppv + 136LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v22);
        v23 = -1;
        v24 = -1;
        if ( v11(v10, &PKEY_FileDescription, &v22) >= 0 )
        {
          String = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                     &v19,
                     L"%s (%s)",
                     v22,
                     v25);
          v9 = String;
          if ( String < 0 )
          {
            v16 = 2508;
LABEL_24:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v16,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
              (const char *)(unsigned int)String,
              v18);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v22);
            goto LABEL_25;
          }
          v12 = v19;
        }
        else
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
          v20 = -1;
          v21 = -1;
          v12 = 0;
          v19 = 0;
          if ( !v25 )
          {
            v14 = -2147023728;
LABEL_16:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9C8,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
              (const char *)(unsigned int)v14,
              v18);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v22);
            v9 = v14;
            goto LABEL_25;
          }
          v31 = 0;
          v32 = 0;
          v33 = 0;
          v13 = v26;
          if ( v26 == -1 )
          {
            v13 = -1;
            do
              ++v13;
            while ( *(_WORD *)(v25 + 2 * v13) );
          }
          v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                  &v31,
                  v25,
                  v13);
          if ( v14 >= 0 )
          {
            v12 = v31;
            v31 = 0;
            v33 = 0;
            v32 = 0;
            v19 = v12;
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v31);
          if ( v14 < 0 )
            goto LABEL_16;
        }
        if ( v12 )
        {
          if ( *v12 )
          {
            String = SystemSettings::DataModel::PropValueHelper::CreateString(v12, a3);
            v9 = String;
            if ( String < 0 )
            {
              v16 = 2513;
              goto LABEL_24;
            }
          }
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v22);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v25);
      }
      SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCache(
        *((unsigned int *)this + 68),
        pszPath);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
  }
  return 0;
}

```

## disassembly

```asm
0x1800281d0  mov     [rsp-8+arg_0], rbx
0x1800281d5  mov     [rsp-8+arg_8], rsi
0x1800281da  push    rbp
0x1800281db  push    rdi
0x1800281dc  push    r12
0x1800281de  push    r14
0x1800281e0  push    r15
0x1800281e2  lea     rbp, [rsp-37h]
0x1800281e7  sub     rsp, 0B0h
0x1800281ee  mov     r14, r8
0x1800281f1  mov     rax, rdx
0x1800281f4  mov     rsi, rcx
0x1800281f7  lea     rdx, stru_180067C70; HSTRING
0x1800281fe  mov     rcx, rax; this
0x180028201  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180028206  xor     r15d, r15d
0x180028209  test    al, al
0x18002820b  jz      loc_1800284D3
0x180028211  mov     [rbp+57h+ppv], r15
0x180028215  mov     [rsp+0D0h+var_A8], r15; unsigned int *
0x18002821a  mov     [rsp+0D0h+var_B0], r15
0x18002821f  xor     r9d, r9d
0x180028222  xor     r8d, r8d
0x180028225  lea     rdx, [rbp+57h+ppv]
0x180028229  mov     ecx, [rsi+110h]
0x18002822f  call    ?GetPrimitiveSpecificParameters@ActionTypeOptionManager@PenSettings@SystemSettings@@SAXW4PenClickType@@PEAPEBG1PEAPEAV?$vector@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@V?$allocator@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@@std@@@std@@11@Z; SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(PenClickType,ushort const * *,ushort const * *,std::vector<SystemSettings::PenSettings::PenActionTypeResourceMapping_> * *,ushort const * *,ushort const * *)
0x180028234  mov     [rbp+57h+pszPath], r15
0x180028238  mov     [rbp+57h+var_50], r15
0x18002823c  mov     [rbp+57h+var_48], r15
0x180028240  lea     rcx, [rbp+57h+pszPath]
0x180028244  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180028249  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002824d  mov     [rbp+57h+var_50], r12
0x180028251  mov     [rbp+57h+var_48], r12
0x180028255  lea     rax, [rbp+57h+pszPath]
0x180028259  mov     [rsp+0D0h+var_B0], rax; int
0x18002825e  lea     r8, aCustomapppath; "CustomAppPath"
0x180028265  mov     rdx, [rbp+57h+ppv]; unsigned __int16 *
0x180028269  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180028270  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180028275  test    eax, eax
0x180028277  js      loc_1800284CA
0x18002827d  mov     [rbp+57h+ppv], r15
0x180028281  lea     rcx, [rbp+57h+ppv]
0x180028285  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002828a  lea     r9, [rbp+57h+ppv]; ppv
0x18002828e  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180028295  xor     edx, edx; pbc
0x180028297  mov     rcx, [rbp+57h+pszPath]; pszPath
0x18002829b  call    cs:__imp_SHCreateItemFromParsingName
0x1800282a1  test    eax, eax
0x1800282a3  js      loc_1800284B0
0x1800282a9  mov     [rbp+57h+var_70], r15
0x1800282ad  mov     [rbp+57h+var_68], r15
0x1800282b1  mov     [rbp+57h+var_60], r15
0x1800282b5  mov     rdi, [rbp+57h+ppv]
0x1800282b9  mov     rax, [rdi]
0x1800282bc  mov     rbx, [rax+28h]
0x1800282c0  lea     rcx, [rbp+57h+var_70]
0x1800282c4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800282c9  mov     [rbp+57h+var_68], r12
0x1800282cd  mov     [rbp+57h+var_60], r12
0x1800282d1  lea     r8, [rbp+57h+var_70]
0x1800282d5  xor     edx, edx
0x1800282d7  mov     rcx, rdi
0x1800282da  mov     rax, rbx
0x1800282dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282e2  mov     ebx, eax
0x1800282e4  test    eax, eax
0x1800282e6  jns     short loc_180028305
0x1800282e8  mov     rcx, [rbp+5Fh]; this
0x1800282ec  mov     r9d, eax; char *
0x1800282ef  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x1800282f6  mov     edx, 9C1h; void *
0x1800282fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028300  jmp     loc_180028472
0x180028305  mov     [rbp+57h+var_88], r15
0x180028309  mov     [rbp+57h+var_80], r15
0x18002830d  mov     [rbp+57h+var_78], r15
0x180028311  mov     [rbp+57h+var_A0], r15
0x180028315  mov     [rbp+57h+var_98], r15
0x180028319  mov     [rbp+57h+var_90], r15
0x18002831d  mov     rdi, [rbp+57h+ppv]
0x180028321  mov     rax, [rdi]
0x180028324  mov     rbx, [rax+88h]
0x18002832b  lea     rcx, [rbp+57h+var_88]
0x18002832f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180028334  mov     [rbp+57h+var_80], r12
0x180028338  mov     [rbp+57h+var_78], r12
0x18002833c  lea     r8, [rbp+57h+var_88]
0x180028340  lea     rdx, PKEY_FileDescription
0x180028347  mov     rcx, rdi
0x18002834a  mov     rax, rbx
0x18002834d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028352  lea     rcx, [rbp+57h+var_A0]
0x180028356  test    eax, eax
0x180028358  jns     loc_180028404
0x18002835e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180028363  mov     [rbp+57h+var_98], r12
0x180028367  mov     [rbp+57h+var_90], r12
0x18002836b  mov     rbx, r15
0x18002836e  mov     [rbp+57h+var_A0], rbx
0x180028372  mov     rdx, [rbp+57h+var_70]
0x180028376  test    rdx, rdx
0x180028379  jz      short loc_1800283CF
0x18002837b  mov     [rbp+57h+var_40], r15
0x18002837f  mov     [rbp+57h+var_38], r15
0x180028383  mov     [rbp+57h+var_30], r15
0x180028387  mov     r8, [rbp+57h+var_68]
0x18002838b  cmp     r8, r12
0x18002838e  jnz     short loc_18002839D
0x180028390  mov     r8, r12
0x180028393  inc     r8
0x180028396  cmp     [rdx+r8*2], r15w
0x18002839b  jnz     short loc_180028393
0x18002839d  lea     rcx, [rbp+57h+var_40]
0x1800283a1  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800283a6  mov     edi, eax
0x1800283a8  test    eax, eax
0x1800283aa  js      short loc_1800283C0
0x1800283ac  mov     rbx, [rbp+57h+var_40]
0x1800283b0  mov     [rbp+57h+var_40], r15
0x1800283b4  mov     [rbp+57h+var_30], r15
0x1800283b8  mov     [rbp+57h+var_38], r15
0x1800283bc  mov     [rbp+57h+var_A0], rbx
0x1800283c0  lea     rcx, [rbp+57h+var_40]
0x1800283c4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800283c9  test    edi, edi
0x1800283cb  jns     short loc_180028429
0x1800283cd  jmp     short loc_1800283D4
0x1800283cf  mov     edi, 80070490h
0x1800283d4  mov     rcx, [rbp+5Fh]; this
0x1800283d8  mov     r9d, edi; char *
0x1800283db  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x1800283e2  mov     edx, 9C8h; void *
0x1800283e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800283ec  nop
0x1800283ed  lea     rcx, [rbp+57h+var_A0]
0x1800283f1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800283f6  nop
0x1800283f7  lea     rcx, [rbp+57h+var_88]
0x1800283fb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180028400  mov     ebx, edi
0x180028402  jmp     short loc_180028472
0x180028404  mov     r9, [rbp+57h+var_70]
0x180028408  mov     r8, [rbp+57h+var_88]
0x18002840c  lea     rdx, aSS; "%s (%s)"
0x180028413  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180028418  mov     ebx, eax
0x18002841a  test    eax, eax
0x18002841c  jns     short loc_180028425
0x18002841e  mov     edx, 9CCh
0x180028423  jmp     short loc_18002844A
0x180028425  mov     rbx, [rbp+57h+var_A0]
0x180028429  test    rbx, rbx
0x18002842c  jz      short loc_180028493
0x18002842e  cmp     [rbx], r15w
0x180028432  jz      short loc_180028493
0x180028434  mov     rdx, r14; struct IInspectable **
0x180028437  mov     rcx, rbx; unsigned __int16 *
0x18002843a  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18002843f  mov     ebx, eax
0x180028441  test    eax, eax
0x180028443  jns     short loc_180028493
0x180028445  mov     edx, 9D1h; void *
0x18002844a  mov     r9d, eax; char *
0x18002844d  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x180028454  mov     rcx, [rbp+5Fh]; this
0x180028458  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002845d  nop
0x18002845e  lea     rcx, [rbp+57h+var_A0]
0x180028462  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180028467  nop
0x180028468  lea     rcx, [rbp+57h+var_88]
0x18002846c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180028471  nop
0x180028472  lea     rcx, [rbp+57h+var_70]
0x180028476  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002847b  nop
0x18002847c  lea     rcx, [rbp+57h+ppv]
0x180028480  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028485  nop
0x180028486  lea     rcx, [rbp+57h+pszPath]
0x18002848a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002848f  mov     eax, ebx
0x180028491  jmp     short loc_1800284D5
0x180028493  lea     rcx, [rbp+57h+var_A0]
0x180028497  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002849c  nop
0x18002849d  lea     rcx, [rbp+57h+var_88]
0x1800284a1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800284a6  nop
0x1800284a7  lea     rcx, [rbp+57h+var_70]
0x1800284ab  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800284b0  mov     rdx, [rbp+57h+pszPath]
0x1800284b4  mov     ecx, [rsi+110h]
0x1800284ba  call    ?UpdateActionValueCache@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@PEBG@Z; SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCache(PenClickType,ushort const *)
0x1800284bf  nop
0x1800284c0  lea     rcx, [rbp+57h+ppv]
0x1800284c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800284c9  nop
0x1800284ca  lea     rcx, [rbp+57h+pszPath]
0x1800284ce  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800284d3  xor     eax, eax
0x1800284d5  lea     r11, [rsp+0D0h+var_20]
0x1800284dd  mov     rbx, [r11+30h]
0x1800284e1  mov     rsi, [r11+38h]
0x1800284e5  mov     rsp, r11
0x1800284e8  pop     r15
0x1800284ea  pop     r14
0x1800284ec  pop     r12
0x1800284ee  pop     rdi
0x1800284ef  pop     rbp
0x1800284f0  retn
```
