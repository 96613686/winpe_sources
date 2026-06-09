# HandlerManager::LoadAndInitializeGidsHandler(CtnrHandlerInputs const *,Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits> *,_GUID *,CtnrHandlerCallbacks *)

- ea: `0x18001d898`
- end: `0x18001dcfd`
- name: `?LoadAndInitializeGidsHandler@HandlerManager@@CAJPEBUCtnrHandlerInputs@@PEAV?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@PEAU_GUID@@PEAUCtnrHandlerCallbacks@@@Z`
- size: `1125`
- prototype: `__int64 __fastcall(__int64, __int64, _OWORD *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180038660`

## callees

- `0x180018194`
- `0x18001825c`
- `0x180019b68`
- `0x180019c94`
- `0x18001d898`
- `0x180024c4c`
- `0x18002c640`
- `0x18002d518`
- `0x180037c34`
- `0x180037e2c`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001dbd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001dbd7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001db57`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001db57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbeb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d957`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d9ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d957`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d9ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d905`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d905`

## string_xrefs

- `0x18001d8f7`: `SYSTEM\CurrentControlSet\Services\NgcCtnrSvc\Parameters`
- `0x18001d94c`: `VscHandlerPath`
- `0x18001d9e4`: `VscHandlerPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=96
__int64 __fastcall HandlerManager::LoadAndInitializeGidsHandler(__int64 a1, __int64 a2, _OWORD *a3, __int64 a4)
{
  int LastError; // ebx
  int *v9; // rdx
  LSTATUS v10; // eax
  BYTE *v11; // rbx
  size_t v12; // rdi
  int v13; // eax
  HMODULE Library; // rax
  char *v15; // rdx
  FARPROC ProcAddress; // rbx
  int v17; // eax
  unsigned __int64 v19; // [rsp+30h] [rbp-99h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-91h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-8Dh] BYREF
  LPBYTE lpData; // [rsp+40h] [rbp-89h] BYREF
  void *v23; // [rsp+48h] [rbp-81h]
  __int64 v24; // [rsp+50h] [rbp-79h]
  _QWORD v25[2]; // [rsp+58h] [rbp-71h] BYREF
  void **v26; // [rsp+68h] [rbp-61h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-59h] BYREF
  _OWORD v28[4]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v29; // [rsp+C0h] [rbp-9h]
  __int128 v30; // [rsp+D0h] [rbp+7h] BYREF

  v26 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  hKey = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v26);
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SYSTEM\\CurrentControlSet\\Services\\NgcCtnrSvc\\Parameters",
                0,
                1u,
                &hKey);
  if ( LastError )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_8;
    v9 = &dword_1800A8914;
    goto LABEL_7;
  }
  cbData = 0;
  LastError = RegQueryValueExW(hKey, L"VscHandlerPath", 0, 0, 0, &cbData);
  if ( LastError )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_8;
    v9 = (int *)byte_1800A88E1;
LABEL_7:
    LODWORD(v19) = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BE0B8,
      (_DWORD)v9,
      0,
      0,
      (__int64)&v19);
LABEL_8:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_44;
  }
  Type = 0;
  std::vector<unsigned char>::vector<unsigned char>(&lpData, cbData);
  v10 = RegQueryValueExW(hKey, L"VscHandlerPath", 0, &Type, lpData, &cbData);
  LastError = v10;
  if ( v10 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v19) = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (unsigned int)word_1800A88B2,
        0,
        0,
        (__int64)&v19);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_43;
  }
  v11 = (BYTE *)v23;
  if ( cbData >= (unsigned __int64)((_BYTE *)v23 - lpData) )
  {
    if ( cbData <= (unsigned __int64)((_BYTE *)v23 - lpData) )
      goto LABEL_22;
    if ( cbData > (unsigned __int64)(v24 - (_QWORD)lpData) )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&lpData, cbData);
      v11 = (BYTE *)v23;
      goto LABEL_22;
    }
    v12 = cbData - ((_BYTE *)v23 - lpData);
    memset_0(v23, 0, v12);
    v11 += v12;
  }
  else
  {
    v11 = &lpData[cbData];
  }
  v23 = v11;
LABEL_22:
  if ( Type == 1 )
  {
    v13 = StringCbLengthW((const unsigned __int16 *)lpData, v11 - lpData, &v19);
    LastError = v13;
    if ( v13 < 0 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        LODWORD(v19) = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800BE0B8,
          (unsigned int)&unk_1800A8848,
          0,
          0,
          (__int64)&v19);
      }
      goto LABEL_43;
    }
    Library = LoadLibraryExW((LPCWSTR)lpData, 0, 0x800u);
    v25[0] = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    v25[1] = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "InitializeHandler");
      if ( ProcAddress )
      {
        v30 = 0;
        memset_0(v28, 0, 0x48u);
        v17 = ((__int64 (__fastcall *)(__int64, __int128 *, _OWORD *))ProcAddress)(a1, &v30, v28);
        LastError = v17;
        if ( v17 >= 0 )
        {
          Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::operator=(a2, v25);
          *a3 = v30;
          *(_OWORD *)a4 = v28[0];
          *(_OWORD *)(a4 + 16) = v28[1];
          *(_OWORD *)(a4 + 32) = v28[2];
          *(_OWORD *)(a4 + 48) = v28[3];
          *(_QWORD *)(a4 + 64) = v29;
        }
        else if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          LODWORD(v19) = v17;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800BE0B8,
            (unsigned int)&unk_1800A87C8,
            0,
            0,
            (__int64)&v19);
        }
        goto LABEL_42;
      }
      LastError = GetLastError();
      if ( (unsigned int)dword_1800BE0B8 <= 2 )
      {
LABEL_33:
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_42:
        v25[0] = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(v25);
LABEL_43:
        std::vector<unsigned char>::_Tidy(&lpData);
        goto LABEL_44;
      }
      v15 = byte_1800A87F5;
    }
    else
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_1800BE0B8 <= 2 )
        goto LABEL_33;
      v15 = byte_1800A8821;
    }
    LODWORD(v19) = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BE0B8,
      (_DWORD)v15,
      0,
      0,
      (__int64)&v19);
    goto LABEL_33;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    LODWORD(v19) = -2147024883;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BE0B8,
      (unsigned int)byte_1800A887B,
      0,
      0,
      (__int64)&v19);
  }
  std::vector<unsigned char>::_Tidy(&lpData);
  LastError = -2147024883;
LABEL_44:
  v26 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v26);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001d898  push    rbp
0x18001d89a  push    rbx
0x18001d89b  push    rsi
0x18001d89c  push    rdi
0x18001d89d  push    r12
0x18001d89f  push    r14
0x18001d8a1  push    r15
0x18001d8a3  lea     rbp, [rsp-27h]
0x18001d8a8  sub     rsp, 0F0h
0x18001d8af  mov     rax, cs:__security_cookie
0x18001d8b6  xor     rax, rsp
0x18001d8b9  mov     [rbp+57h+var_40], rax
0x18001d8bd  mov     rsi, r9
0x18001d8c0  mov     r12, r8
0x18001d8c3  mov     r15, rdx
0x18001d8c6  mov     r14, rcx
0x18001d8c9  lea     rax, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18001d8d0  mov     [rbp+57h+var_B8], rax
0x18001d8d4  mov     [rbp+57h+hKey], 0
0x18001d8dc  lea     rcx, [rbp+57h+var_B8]
0x18001d8e0  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001d8e5  lea     rax, [rbp+57h+hKey]
0x18001d8e9  mov     [rsp+120h+phkResult], rax; phkResult
0x18001d8ee  mov     r9d, 1; samDesired
0x18001d8f4  xor     r8d, r8d; ulOptions
0x18001d8f7  lea     rdx, aSystemCurrentc_8; "SYSTEM\\CurrentControlSet\\Services\\Ng"...
0x18001d8fe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d905  call    cs:__imp_RegOpenKeyExW
0x18001d90c  nop     dword ptr [rax+rax+00h]
0x18001d911  mov     ebx, eax
0x18001d913  test    eax, eax
0x18001d915  jz      short loc_18001D92B
0x18001d917  mov     ecx, cs:dword_1800BE0B8
0x18001d91d  cmp     ecx, 2
0x18001d920  jbe     short loc_18001D99B
0x18001d922  lea     rdx, dword_1800A8914
0x18001d929  jmp     short loc_18001D97B
0x18001d92b  mov     [rsp+120h+cbData], 0
0x18001d933  lea     rax, [rsp+120h+cbData]
0x18001d938  mov     [rsp+120h+lpcbData], rax; lpcbData
0x18001d93d  mov     [rsp+120h+phkResult], 0; lpData
0x18001d946  xor     r9d, r9d; lpType
0x18001d949  xor     r8d, r8d; lpReserved
0x18001d94c  lea     rdx, aVschandlerpath; "VscHandlerPath"
0x18001d953  mov     rcx, [rbp+57h+hKey]; hKey
0x18001d957  call    cs:__imp_RegQueryValueExW
0x18001d95e  nop     dword ptr [rax+rax+00h]
0x18001d963  mov     ebx, eax
0x18001d965  test    eax, eax
0x18001d967  jz      short loc_18001D9B1
0x18001d969  mov     ecx, cs:dword_1800BE0B8
0x18001d96f  cmp     ecx, 2
0x18001d972  jbe     short loc_18001D99B
0x18001d974  lea     rdx, byte_1800A88E1
0x18001d97b  xor     r9d, r9d
0x18001d97e  lea     rax, [rsp+120h+var_F0]
0x18001d983  xor     r8d, r8d
0x18001d986  mov     [rsp+120h+phkResult], rax
0x18001d98b  mov     dword ptr [rsp+120h+var_F0], ebx
0x18001d98f  lea     rcx, dword_1800BE0B8
0x18001d996  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001d99b  test    ebx, ebx
0x18001d99d  jle     loc_18001DCC8
0x18001d9a3  movzx   ebx, bx
0x18001d9a6  or      ebx, 80070000h
0x18001d9ac  jmp     loc_18001DCC8
0x18001d9b1  mov     [rsp+120h+Type], 0
0x18001d9b9  mov     edx, [rsp+120h+cbData]
0x18001d9bd  lea     rcx, [rsp+120h+lpData]
0x18001d9c2  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18001d9c7  nop
0x18001d9c8  mov     rax, [rsp+120h+lpData]
0x18001d9cd  lea     rcx, [rsp+120h+cbData]
0x18001d9d2  mov     [rsp+120h+lpcbData], rcx; lpcbData
0x18001d9d7  mov     [rsp+120h+phkResult], rax; lpData
0x18001d9dc  lea     r9, [rsp+120h+Type]; lpType
0x18001d9e1  xor     r8d, r8d; lpReserved
0x18001d9e4  lea     rdx, aVschandlerpath; "VscHandlerPath"
0x18001d9eb  mov     rcx, [rbp+57h+hKey]; hKey
0x18001d9ef  call    cs:__imp_RegQueryValueExW
0x18001d9f6  nop     dword ptr [rax+rax+00h]
0x18001d9fb  mov     ebx, eax
0x18001d9fd  test    eax, eax
0x18001d9ff  jz      short loc_18001DA49
0x18001da01  mov     ecx, cs:dword_1800BE0B8
0x18001da07  cmp     ecx, 2
0x18001da0a  jbe     short loc_18001DA33
0x18001da0c  mov     dword ptr [rsp+120h+var_F0], eax
0x18001da10  lea     rax, [rsp+120h+var_F0]
0x18001da15  mov     [rsp+120h+phkResult], rax
0x18001da1a  xor     r9d, r9d
0x18001da1d  xor     r8d, r8d
0x18001da20  lea     rdx, word_1800A88B2
0x18001da27  lea     rcx, dword_1800BE0B8
0x18001da2e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001da33  test    ebx, ebx
0x18001da35  jle     loc_18001DCBD
0x18001da3b  movzx   ebx, bx
0x18001da3e  or      ebx, 80070000h
0x18001da44  jmp     loc_18001DCBD
0x18001da49  mov     edi, [rsp+120h+cbData]
0x18001da4d  mov     rdx, [rsp+120h+lpData]
0x18001da52  mov     rbx, [rsp+120h+var_D8]
0x18001da57  mov     rcx, rbx
0x18001da5a  sub     rcx, rdx
0x18001da5d  cmp     rdi, rcx
0x18001da60  jnb     short loc_18001DA68
0x18001da62  lea     rbx, [rdi+rdx]
0x18001da66  jmp     short loc_18001DA9D
0x18001da68  jbe     short loc_18001DAA2
0x18001da6a  mov     rax, [rbp+57h+var_D0]
0x18001da6e  sub     rax, rdx
0x18001da71  cmp     rdi, rax
0x18001da74  jbe     short loc_18001DA8A
0x18001da76  mov     rdx, rdi
0x18001da79  lea     rcx, [rsp+120h+lpData]
0x18001da7e  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001da83  mov     rbx, [rsp+120h+var_D8]
0x18001da88  jmp     short loc_18001DAA2
0x18001da8a  sub     rdi, rcx
0x18001da8d  mov     r8, rdi; Size
0x18001da90  xor     edx, edx; Val
0x18001da92  mov     rcx, rbx; void *
0x18001da95  call    memset_0
0x18001da9a  add     rbx, rdi
0x18001da9d  mov     [rsp+120h+var_D8], rbx
0x18001daa2  cmp     [rsp+120h+Type], 1
0x18001daa7  jz      short loc_18001DAF4
0x18001daa9  mov     eax, cs:dword_1800BE0B8
0x18001daaf  cmp     eax, 2
0x18001dab2  jbe     short loc_18001DAE0
0x18001dab4  mov     dword ptr [rsp+120h+var_F0], 8007000Dh
0x18001dabc  lea     rax, [rsp+120h+var_F0]
0x18001dac1  mov     [rsp+120h+phkResult], rax
0x18001dac6  xor     r9d, r9d
0x18001dac9  xor     r8d, r8d
0x18001dacc  lea     rdx, byte_1800A887B
0x18001dad3  lea     rcx, dword_1800BE0B8
0x18001dada  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001dadf  nop
0x18001dae0  lea     rcx, [rsp+120h+lpData]
0x18001dae5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001daea  mov     ebx, 8007000Dh
0x18001daef  jmp     loc_18001DCC8
0x18001daf4  mov     rcx, [rsp+120h+lpData]; unsigned __int16 *
0x18001daf9  sub     rbx, rcx
0x18001dafc  lea     r8, [rsp+120h+var_F0]; unsigned __int64 *
0x18001db01  mov     rdx, rbx; unsigned __int64
0x18001db04  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001db09  mov     ebx, eax
0x18001db0b  test    eax, eax
0x18001db0d  jns     short loc_18001DB4A
0x18001db0f  mov     ecx, cs:dword_1800BE0B8
0x18001db15  cmp     ecx, 2
0x18001db18  jbe     loc_18001DCBD
0x18001db1e  mov     dword ptr [rsp+120h+var_F0], eax
0x18001db22  lea     rax, [rsp+120h+var_F0]
0x18001db27  mov     [rsp+120h+phkResult], rax
0x18001db2c  xor     r9d, r9d
0x18001db2f  xor     r8d, r8d
0x18001db32  lea     rdx, unk_1800A8848
0x18001db39  lea     rcx, dword_1800BE0B8
0x18001db40  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001db45  jmp     loc_18001DCBD
0x18001db4a  xor     edx, edx; hFile
0x18001db4c  mov     r8d, 800h; dwFlags
0x18001db52  mov     rcx, [rsp+120h+lpData]; lpLibFileName
0x18001db57  call    cs:__imp_LoadLibraryExW
0x18001db5e  nop     dword ptr [rax+rax+00h]
0x18001db63  lea     rdi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18001db6a  mov     [rbp+57h+var_C8], rdi
0x18001db6e  mov     [rbp+57h+var_C0], rax
0x18001db72  test    rax, rax
0x18001db75  jnz     short loc_18001DBCD
0x18001db77  call    cs:__imp_GetLastError
0x18001db7e  nop     dword ptr [rax+rax+00h]
0x18001db83  mov     ebx, eax
0x18001db85  mov     ecx, cs:dword_1800BE0B8
0x18001db8b  cmp     ecx, 2
0x18001db8e  jbe     short loc_18001DBB7
0x18001db90  lea     rdx, byte_1800A8821
0x18001db97  xor     r9d, r9d
0x18001db9a  lea     rax, [rsp+120h+var_F0]
0x18001db9f  xor     r8d, r8d
0x18001dba2  mov     [rsp+120h+phkResult], rax
0x18001dba7  mov     dword ptr [rsp+120h+var_F0], ebx
0x18001dbab  lea     rcx, dword_1800BE0B8
0x18001dbb2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001dbb7  test    ebx, ebx
0x18001dbb9  jle     loc_18001DCAF
0x18001dbbf  movzx   ebx, bx
0x18001dbc2  or      ebx, 80070000h
0x18001dbc8  jmp     loc_18001DCAF
0x18001dbcd  lea     rdx, ProcName; "InitializeHandler"
0x18001dbd4  mov     rcx, rax; hModule
0x18001dbd7  call    cs:__imp_GetProcAddress
0x18001dbde  nop     dword ptr [rax+rax+00h]
0x18001dbe3  mov     rbx, rax
0x18001dbe6  test    rax, rax
0x18001dbe9  jnz     short loc_18001DC0D
0x18001dbeb  call    cs:__imp_GetLastError
0x18001dbf2  nop     dword ptr [rax+rax+00h]
0x18001dbf7  mov     ebx, eax
0x18001dbf9  mov     ecx, cs:dword_1800BE0B8
0x18001dbff  cmp     ecx, 2
0x18001dc02  jbe     short loc_18001DBB7
0x18001dc04  lea     rdx, byte_1800A87F5
0x18001dc0b  jmp     short loc_18001DB97
0x18001dc0d  xorps   xmm0, xmm0
0x18001dc10  movups  [rbp+57h+var_50], xmm0
0x18001dc14  xor     edx, edx; Val
0x18001dc16  lea     r8d, [rdx+48h]; Size
0x18001dc1a  lea     rcx, [rbp+57h+var_A0]; void *
0x18001dc1e  call    memset_0
0x18001dc23  lea     r8, [rbp+57h+var_A0]
0x18001dc27  lea     rdx, [rbp+57h+var_50]
0x18001dc2b  mov     rcx, r14
0x18001dc2e  mov     rax, rbx
0x18001dc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc36  mov     ebx, eax
0x18001dc38  test    eax, eax
0x18001dc3a  jns     short loc_18001DC70
0x18001dc3c  mov     ecx, cs:dword_1800BE0B8
0x18001dc42  cmp     ecx, 2
0x18001dc45  jbe     short loc_18001DCAF
0x18001dc47  mov     dword ptr [rsp+120h+var_F0], eax
0x18001dc4b  lea     rax, [rsp+120h+var_F0]
0x18001dc50  mov     [rsp+120h+phkResult], rax
0x18001dc55  xor     r9d, r9d
0x18001dc58  xor     r8d, r8d
0x18001dc5b  lea     rdx, unk_1800A87C8
0x18001dc62  lea     rcx, dword_1800BE0B8
0x18001dc69  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001dc6e  jmp     short loc_18001DCAF
0x18001dc70  lea     rdx, [rbp+57h+var_C8]
0x18001dc74  mov     rcx, r15
0x18001dc77  call    ??4?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAAEAV0123@$$QEAV0123@@Z; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::operator=(Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits> &&)
0x18001dc7c  movups  xmm0, [rbp+57h+var_50]
0x18001dc80  movdqu  xmmword ptr [r12], xmm0
0x18001dc86  movaps  xmm1, [rbp+57h+var_A0]
0x18001dc8a  movups  xmmword ptr [rsi], xmm1
0x18001dc8d  movaps  xmm0, [rbp+57h+var_90]
0x18001dc91  movups  xmmword ptr [rsi+10h], xmm0
0x18001dc95  movaps  xmm1, [rbp+57h+var_80]
0x18001dc99  movups  xmmword ptr [rsi+20h], xmm1
0x18001dc9d  movaps  xmm0, [rbp+57h+var_70]
0x18001dca1  movups  xmmword ptr [rsi+30h], xmm0
0x18001dca5  movsd   xmm1, [rbp+57h+var_60]
0x18001dcaa  movsd   qword ptr [rsi+40h], xmm1
0x18001dcaf  mov     [rbp+57h+var_C8], rdi
0x18001dcb3  lea     rcx, [rbp+57h+var_C8]
0x18001dcb7  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001dcbc  nop
0x18001dcbd  lea     rcx, [rsp+120h+lpData]
0x18001dcc2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001dcc7  nop
0x18001dcc8  lea     rax, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18001dccf  mov     [rbp+57h+var_B8], rax
0x18001dcd3  lea     rcx, [rbp+57h+var_B8]
0x18001dcd7  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001dcdc  mov     eax, ebx
0x18001dcde  mov     rcx, [rbp+57h+var_40]
0x18001dce2  xor     rcx, rsp; StackCookie
0x18001dce5  call    __security_check_cookie
0x18001dcea  add     rsp, 0F0h
0x18001dcf1  pop     r15
0x18001dcf3  pop     r14
0x18001dcf5  pop     r12
0x18001dcf7  pop     rdi
0x18001dcf8  pop     rsi
0x18001dcf9  pop     rbx
0x18001dcfa  pop     rbp
0x18001dcfb  retn
```
