# DynamoRaiseToast(ushort const *,ushort const *)

- ea: `0x1400390d8`
- end: `0x140039492`
- name: `?DynamoRaiseToast@@YAJPEBG0@Z`
- size: `954`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140039730`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x140009594`
- `0x1400095b4`
- `0x14000bb88`
- `0x140036bd0`
- `0x140036d50`
- `0x1400388b8`
- `0x1400390d8`
- `0x140039f28`
- `0x140039fe8`
- `0x14003bad8`
- `0x14003bdac`
- `0x14005d010`

## import_xrefs

- `DMCmnUtils!DmRaiseToastNotification` at `0x14003938b`
- `DMCmnUtils!DmRaiseToastNotification` at `0x14003938b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400391d6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400391d6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140039261`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140039261`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140039289`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140039316`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400393c1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140039421`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140039289`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140039316`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400393c1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140039421`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400393b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140039417`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400393b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140039417`

## string_xrefs

- `0x1400391cf`: `DMAppsRes.dll`
- `0x14003936f`: `protocol`

## pseudocode

```c
__int64 __fastcall DynamoRaiseToast(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  HMODULE Library; // rax
  const char *v6; // r9
  HMODULE v7; // rbx
  unsigned int v8; // ebx
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  int StringW; // eax
  const char *v12; // r9
  unsigned int LastError; // edi
  void (__fastcall ***v14)(_QWORD, __int64); // rcx
  HLOCAL v15; // rdi
  void (__fastcall ***v16)(_QWORD, __int64); // rcx
  int v17; // eax
  unsigned int v18; // esi
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  int v21; // [rsp+20h] [rbp-238h]
  int v22; // [rsp+20h] [rbp-238h]
  void (__fastcall ***v23)(_QWORD, __int64); // [rsp+30h] [rbp-228h] BYREF
  WCHAR Buffer[4]; // [rsp+38h] [rbp-220h] BYREF
  HLOCAL hMem[2]; // [rsp+40h] [rbp-218h] BYREF
  _QWORD v26[42]; // [rsp+50h] [rbp-208h] BYREF
  char v27[144]; // [rsp+1A0h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  memset_0(v27, 0, 0x81u);
  anonymous_namespace_::GetCorrelationVector(v27);
  wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v26,
    "RaiseToastActivity");
  v26[0] = &DynamicManagementProvider::RaiseToastActivity::`vftable';
  DynamicManagementProvider::RaiseToastActivity::StartActivityWithCorrelationVector(
    (DynamicManagementProvider::RaiseToastActivity *)v26,
    v27);
  Dynamo::DataStoreFactory_t<Dynamo::details::DataStore>::GetStore(&v23, a1, a2);
  if ( !((unsigned __int8 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v23)[9])(v23) )
  {
    wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v26);
    v4 = v23;
    v23 = 0;
    if ( v4 )
      (**v4)(v4, 1);
LABEL_23:
    v26[0] = &DynamicManagementProvider::RaiseToastActivity::`vftable';
    wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v26);
    wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v26);
    return 0;
  }
  Library = LoadLibraryExW(L"DMAppsRes.dll", 0, 0x800u);
  v7 = Library;
  hMem[1] = Library;
  if ( Library )
  {
    *(_QWORD *)Buffer = 0;
    StringW = LoadStringW(Library, 0x65EFu, Buffer, 0);
    if ( StringW )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        hMem,
        *(char **)Buffer,
        StringW,
        v12);
      v15 = hMem[0];
      if ( hMem[0] )
      {
        v17 = DmRaiseToastNotification(
                L"Windows.SystemToast.DeviceManagement",
                L"DynamicManagement",
                L"ms-settings:workplace",
                L"protocol",
                0,
                (const unsigned __int16 *)hMem[0]);
        v18 = v17;
        if ( v17 >= 0 )
        {
          wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v26);
          LocalFree(v15);
          FreeLibrary(v7);
          v20 = v23;
          v23 = 0;
          if ( v20 )
            (**v20)(v20, 1);
          goto LABEL_23;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x237,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
          (const char *)(unsigned int)v17,
          v22);
        LocalFree(v15);
        FreeLibrary(v7);
        v19 = v23;
        v23 = 0;
        if ( v19 )
          (**v19)(v19, 1);
        v26[0] = &DynamicManagementProvider::RaiseToastActivity::`vftable';
        wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v26);
        wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v26);
        return v18;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x22F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
          (const char *)0x8007000ELL,
          v21);
        FreeLibrary(v7);
        v16 = v23;
        v23 = 0;
        if ( v16 )
          (**v16)(v16, 1);
        v26[0] = &DynamicManagementProvider::RaiseToastActivity::`vftable';
        wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v26);
        wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v26);
        return 2147942414LL;
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x22C,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
                    v12);
      FreeLibrary(v7);
      v14 = v23;
      v23 = 0;
      if ( v14 )
        (**v14)(v14, 1);
      v26[0] = &DynamicManagementProvider::RaiseToastActivity::`vftable';
      wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v26);
      wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v26);
      return LastError;
    }
  }
  else
  {
    v8 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x227,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
           v6);
    v9 = v23;
    v23 = 0;
    if ( v9 )
      (**v9)(v9, 1);
    v26[0] = &DynamicManagementProvider::RaiseToastActivity::`vftable';
    wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v26);
    wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v26);
    return v8;
  }
}

```

## disassembly

```asm
0x1400390d8  mov     [rsp+arg_10], rbx
0x1400390dd  push    rsi
0x1400390de  push    rdi
0x1400390df  push    r15
0x1400390e1  sub     rsp, 240h
0x1400390e8  mov     rax, cs:__security_cookie
0x1400390ef  xor     rax, rsp
0x1400390f2  mov     [rsp+258h+var_28], rax
0x1400390fa  mov     rdi, rdx
0x1400390fd  mov     rbx, rcx
0x140039100  xor     edx, edx; Val
0x140039102  mov     r8d, 81h; Size
0x140039108  lea     rcx, [rsp+258h+var_B8]; void *
0x140039110  call    memset_0
0x140039115  lea     rcx, [rsp+258h+var_B8]; char *
0x14003911d  call    _anonymous_namespace___GetCorrelationVector
0x140039122  lea     rdx, aRaisetoastacti; "RaiseToastActivity"
0x140039129  lea     rcx, [rsp+258h+var_208]
0x14003912e  call    ??0?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140039133  lea     r15, ??_7RaiseToastActivity@DynamicManagementProvider@@6B@; const DynamicManagementProvider::RaiseToastActivity::`vftable'
0x14003913a  mov     [rsp+258h+var_208], r15
0x14003913f  lea     rdx, [rsp+258h+var_B8]; char *
0x140039147  lea     rcx, [rsp+258h+var_208]; this
0x14003914c  call    ?StartActivityWithCorrelationVector@RaiseToastActivity@DynamicManagementProvider@@QEAAXPEBD@Z; DynamicManagementProvider::RaiseToastActivity::StartActivityWithCorrelationVector(char const *)
0x140039151  nop
0x140039152  mov     r8, rdi
0x140039155  mov     rdx, rbx
0x140039158  lea     rcx, [rsp+258h+var_228]
0x14003915d  call    ?GetStore@?$DataStoreFactory_t@VDataStore@details@Dynamo@@@Dynamo@@SA?AV?$unique_ptr@VIDataStore@Dynamo@@U?$default_delete@VIDataStore@Dynamo@@@wistd@@@wistd@@PEBG0@Z; Dynamo::DataStoreFactory_t<Dynamo::details::DataStore>::GetStore(ushort const *,ushort const *)
0x140039162  nop
0x140039163  mov     rcx, [rsp+258h+var_228]
0x140039168  mov     rax, [rcx]
0x14003916b  mov     rax, [rax+48h]
0x14003916f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039174  test    al, al
0x140039176  jnz     short loc_1400391C7
0x140039178  lea     rcx, [rsp+258h+var_208]
0x14003917d  call    ?Stop@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140039182  nop
0x140039183  mov     rcx, [rsp+258h+var_228]
0x140039188  mov     [rsp+258h+var_228], 0
0x140039191  test    rcx, rcx
0x140039194  jz      short loc_1400391A7
0x140039196  mov     rax, [rcx]
0x140039199  mov     edx, 1
0x14003919e  mov     rax, [rax]
0x1400391a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400391a6  nop
0x1400391a7  mov     [rsp+258h+var_208], r15
0x1400391ac  lea     rcx, [rsp+258h+var_208]
0x1400391b1  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400391b6  lea     rcx, [rsp+258h+var_208]
0x1400391bb  call    ??1?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400391c0  xor     eax, eax
0x1400391c2  jmp     loc_14003946D
0x1400391c7  xor     edx, edx; hFile
0x1400391c9  mov     r8d, 800h; dwFlags
0x1400391cf  lea     rcx, aDmappsresDll; "DMAppsRes.dll"
0x1400391d6  call    cs:__imp_LoadLibraryExW
0x1400391dc  mov     rbx, rax
0x1400391df  mov     [rsp+258h+var_210], rax
0x1400391e4  test    rax, rax
0x1400391e7  jnz     short loc_140039248
0x1400391e9  mov     rcx, [rsp+258h]; this
0x1400391f1  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400391f8  mov     edx, 227h; void *
0x1400391fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140039202  mov     ebx, eax
0x140039204  mov     rcx, [rsp+258h+var_228]
0x140039209  mov     [rsp+258h+var_228], 0
0x140039212  test    rcx, rcx
0x140039215  jz      short loc_140039228
0x140039217  mov     rdx, [rcx]
0x14003921a  mov     rax, [rdx]
0x14003921d  mov     edx, 1
0x140039222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039227  nop
0x140039228  mov     [rsp+258h+var_208], r15
0x14003922d  lea     rcx, [rsp+258h+var_208]
0x140039232  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140039237  lea     rcx, [rsp+258h+var_208]
0x14003923c  call    ??1?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140039241  mov     eax, ebx
0x140039243  jmp     loc_14003946D
0x140039248  mov     qword ptr [rsp+258h+Buffer], 0
0x140039251  xor     r9d, r9d; cchBufferMax
0x140039254  lea     r8, [rsp+258h+Buffer]; lpBuffer
0x140039259  mov     edx, 65EFh; uID
0x14003925e  mov     rcx, rbx; hInstance
0x140039261  call    cs:__imp_LoadStringW
0x140039267  test    eax, eax
0x140039269  jnz     short loc_1400392D4
0x14003926b  mov     rcx, [rsp+258h]; this
0x140039273  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14003927a  mov     edx, 22Ch; void *
0x14003927f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140039284  mov     edi, eax
0x140039286  mov     rcx, rbx; hLibModule
0x140039289  call    cs:__imp_FreeLibrary
0x14003928f  nop
0x140039290  mov     rcx, [rsp+258h+var_228]
0x140039295  mov     [rsp+258h+var_228], 0
0x14003929e  test    rcx, rcx
0x1400392a1  jz      short loc_1400392B4
0x1400392a3  mov     rdx, [rcx]
0x1400392a6  mov     rax, [rdx]
0x1400392a9  mov     edx, 1
0x1400392ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400392b3  nop
0x1400392b4  mov     [rsp+258h+var_208], r15
0x1400392b9  lea     rcx, [rsp+258h+var_208]
0x1400392be  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400392c3  lea     rcx, [rsp+258h+var_208]
0x1400392c8  call    ??1?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400392cd  mov     eax, edi
0x1400392cf  jmp     loc_14003946D
0x1400392d4  movsxd  r8, eax
0x1400392d7  mov     rdx, qword ptr [rsp+258h+Buffer]
0x1400392dc  lea     rcx, [rsp+258h+hMem]
0x1400392e1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1400392e6  nop
0x1400392e7  mov     rdi, [rsp+258h+hMem]
0x1400392ec  test    rdi, rdi
0x1400392ef  jnz     short loc_140039361
0x1400392f1  mov     rcx, [rsp+258h]; this
0x1400392f9  mov     edi, 8007000Eh
0x1400392fe  mov     r9d, edi; char *
0x140039301  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140039308  mov     edx, 22Fh; void *
0x14003930d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140039312  nop
0x140039313  mov     rcx, rbx; hLibModule
0x140039316  call    cs:__imp_FreeLibrary
0x14003931c  nop
0x14003931d  mov     rcx, [rsp+258h+var_228]
0x140039322  mov     [rsp+258h+var_228], 0
0x14003932b  test    rcx, rcx
0x14003932e  jz      short loc_140039341
0x140039330  mov     rax, [rcx]
0x140039333  mov     edx, 1
0x140039338  mov     rax, [rax]
0x14003933b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039340  nop
0x140039341  mov     [rsp+258h+var_208], r15
0x140039346  lea     rcx, [rsp+258h+var_208]
0x14003934b  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140039350  lea     rcx, [rsp+258h+var_208]
0x140039355  call    ??1?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x14003935a  mov     eax, edi
0x14003935c  jmp     loc_14003946D
0x140039361  mov     [rsp+258h+var_230], rdi
0x140039366  mov     qword ptr [rsp+258h+var_238], 0; int
0x14003936f  lea     r9, aProtocol; "protocol"
0x140039376  lea     r8, aMsSettingsWork; "ms-settings:workplace"
0x14003937d  lea     rdx, aDynamicmanagem; "DynamicManagement"
0x140039384  lea     rcx, aWindowsSystemt; "Windows.SystemToast.DeviceManagement"
0x14003938b  call    cs:__imp_?DmRaiseToastNotification@@YAJPEBG00000@Z; DmRaiseToastNotification(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140039391  mov     esi, eax
0x140039393  test    eax, eax
0x140039395  jns     short loc_140039409
0x140039397  mov     rcx, [rsp+258h]; this
0x14003939f  mov     r9d, eax; char *
0x1400393a2  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400393a9  mov     edx, 237h; void *
0x1400393ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400393b3  nop
0x1400393b4  mov     rcx, rdi; hMem
0x1400393b7  call    cs:__imp_LocalFree
0x1400393bd  nop
0x1400393be  mov     rcx, rbx; hLibModule
0x1400393c1  call    cs:__imp_FreeLibrary
0x1400393c7  nop
0x1400393c8  mov     rcx, [rsp+258h+var_228]
0x1400393cd  mov     [rsp+258h+var_228], 0
0x1400393d6  test    rcx, rcx
0x1400393d9  jz      short loc_1400393EC
0x1400393db  mov     rax, [rcx]
0x1400393de  mov     edx, 1
0x1400393e3  mov     rax, [rax]
0x1400393e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400393eb  nop
0x1400393ec  mov     [rsp+258h+var_208], r15
0x1400393f1  lea     rcx, [rsp+258h+var_208]
0x1400393f6  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400393fb  lea     rcx, [rsp+258h+var_208]
0x140039400  call    ??1?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140039405  mov     eax, esi
0x140039407  jmp     short loc_14003946D
0x140039409  lea     rcx, [rsp+258h+var_208]
0x14003940e  call    ?Stop@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140039413  nop
0x140039414  mov     rcx, rdi; hMem
0x140039417  call    cs:__imp_LocalFree
0x14003941d  nop
0x14003941e  mov     rcx, rbx; hLibModule
0x140039421  call    cs:__imp_FreeLibrary
0x140039427  nop
0x140039428  mov     rcx, [rsp+258h+var_228]
0x14003942d  mov     [rsp+258h+var_228], 0
0x140039436  test    rcx, rcx
0x140039439  jz      short loc_14003944C
0x14003943b  mov     rax, [rcx]
0x14003943e  mov     edx, 1
0x140039443  mov     rax, [rax]
0x140039446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003944b  nop
0x14003944c  mov     [rsp+258h+var_208], r15
0x140039451  lea     rcx, [rsp+258h+var_208]
0x140039456  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14003945b  lea     rcx, [rsp+258h+var_208]
0x140039460  call    ??1?$ActivityBase@VDynamoProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140039465  xor     eax, eax
0x140039467  jmp     short loc_14003946D
0x140039469  mov     eax, dword ptr [rsp+258h+var_228]
0x14003946d  mov     rcx, [rsp+258h+var_28]
0x140039475  xor     rcx, rsp; StackCookie
0x140039478  call    __security_check_cookie
0x14003947d  mov     rbx, [rsp+258h+arg_10]
0x140039485  add     rsp, 240h
0x14003948c  pop     r15
0x14003948e  pop     rdi
0x14003948f  pop     rsi
0x140039490  retn
```
