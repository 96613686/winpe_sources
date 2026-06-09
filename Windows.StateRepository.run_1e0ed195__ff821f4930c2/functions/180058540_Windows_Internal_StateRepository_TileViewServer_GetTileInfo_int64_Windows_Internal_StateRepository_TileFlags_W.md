# Windows::Internal::StateRepository::TileViewServer::GetTileInfo(__int64 *,Windows::Internal::StateRepository::TileFlags *,Windows::Internal::StateRepository::TileType *,Windows::Internal::StateRepository::TileTemplate *,HSTRING__ * *,HSTRING__ * *,Windows::Foundation::Collections::IPropertySet * *,_GUID *,__int64 *)

- ea: `0x180058540`
- end: `0x180058a83`
- name: `?GetTileInfo@TileViewServer@StateRepository@Internal@Windows@@UEAAJPEA_JPEAW4TileFlags@234@PEAW4TileType@234@PEAW4TileTemplate@234@PEAPEAUHSTRING__@@4PEAPEAUIPropertySet@Collections@Foundation@4@PEAU_GUID@@0@Z`
- size: `1347`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::TileViewServer *__hidden this, __int64 *, enum Windows::Internal::StateRepository::TileFlags *, enum Windows::Internal::StateRepository::TileType *, enum Windows::Internal::StateRepository::TileTemplate *, HSTRING *, HSTRING *, struct Windows::Foundation::Collections::IPropertySet **, struct _GUID *, __int64 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003e54`
- `0x18000b380`
- `0x180017a58`
- `0x18001a9e0`
- `0x180058540`
- `0x18019914d`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800586ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180058712`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005876b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800586ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180058712`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005876b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800586f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180058756`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800588dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800586f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180058756`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800588dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005890a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005890a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800585c7`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800585c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058988`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058699`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005886b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058879`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800588c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800588d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058a12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058a20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058699`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005886b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058879`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800588c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800588d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058a12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058a20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800586d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005873e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800586d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005873e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005878a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005878a`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18005858e`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18005858e`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x1800587d6`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x1800587d6`

## string_xrefs

- `0x180058609`: `onecore\base\appmodel\staterepository\winrt\common\src\winrt.cpp`
- `0x1800589a8`: `onecore\base\appmodel\staterepository\winrt\common\src\winrt.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::StateRepository::TileViewServer::GetTileInfo(
        Windows::Internal::StateRepository::TileViewServer *this,
        __int64 *a2,
        enum Windows::Internal::StateRepository::TileFlags *a3,
        enum Windows::Internal::StateRepository::TileType *a4,
        enum Windows::Internal::StateRepository::TileTemplate *a5,
        HSTRING *a6,
        HSTRING *a7,
        struct Windows::Foundation::Collections::IPropertySet **a8,
        struct _GUID *a9,
        __int64 *a10)
{
  HRESULT v14; // eax
  int v15; // ebx
  DWORD CurrentProcessId; // edi
  void *v17; // rcx
  const WCHAR *v18; // rcx
  __int64 v19; // rdx
  HRESULT v20; // ebx
  const WCHAR *v21; // rcx
  __int64 v22; // rdx
  size_t v23; // rsi
  void *v24; // r12
  const void *v25; // r15
  void *v26; // rax
  void *v27; // rbx
  int v28; // eax
  struct _GUID v29; // xmm0
  __int64 v30; // r8
  __int64 v31; // rdx
  HSTRING v32; // rax
  HSTRING v33; // rcx
  struct Windows::Foundation::Collections::IPropertySet *v34; // rax
  __int64 v36; // rdx
  struct Windows::Foundation::Collections::IPropertySet *v37; // rcx
  __int64 v38; // rdx
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  HSTRING v40; // [rsp+28h] [rbp-38h] BYREF
  DWORD v41; // [rsp+30h] [rbp-30h] BYREF
  char v42; // [rsp+34h] [rbp-2Ch]
  void *ppInterface; // [rsp+38h] [rbp-28h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v44; // [rsp+40h] [rbp-20h] BYREF
  HANDLE Process; // [rsp+48h] [rbp-18h] BYREF
  int v46; // [rsp+50h] [rbp-10h]
  __int64 v47; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v42 = 0;
  _InterlockedIncrement(&StateRepository::WinRT::Client::RequestInProgress::s_count);
  ppInterface = 0;
  v14 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( v14 != -2147417833 && v14 != -2147467262 )
    {
      CurrentProcessId = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\common\\src\\winrt.cpp",
        (const char *)(unsigned int)v14,
        (int)string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppInterface);
      goto LABEL_9;
    }
    CurrentProcessId = GetCurrentProcessId();
  }
  else
  {
    Process = 0;
    if ( (*(int (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL))(ppInterface, 4096, &Process) < 0 )
      CurrentProcessId = 0;
    else
      CurrentProcessId = GetProcessId(Process);
    if ( (char *)Process - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(Process);
  }
  v17 = ppInterface;
  if ( ppInterface )
  {
    ppInterface = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v15 = 0;
LABEL_9:
  if ( v15 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\common\\src\\winrt.cpp",
      (const char *)(unsigned int)v15,
      (int)string);
  v41 = CurrentProcessId;
  if ( !a2 )
  {
    v36 = 32;
LABEL_58:
    v20 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.tileview-custom.cpp",
      (const char *)0x80004003LL,
      (int)string);
    goto LABEL_47;
  }
  if ( !a3 )
  {
    v38 = 33;
LABEL_67:
    v20 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.tileview-custom.cpp",
      (const char *)0x80004003LL,
      (int)string);
LABEL_70:
    StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress((StateRepository::WinRT::Client::RequestInProgress *)&v41);
    return (unsigned int)v20;
  }
  if ( !a4 )
  {
    v38 = 34;
    goto LABEL_67;
  }
  if ( !a5 )
  {
    v38 = 35;
    goto LABEL_67;
  }
  if ( !a6 )
  {
    v38 = 36;
    goto LABEL_67;
  }
  if ( !a8 )
  {
    v38 = 37;
    goto LABEL_67;
  }
  if ( !a9 )
  {
    v38 = 38;
    goto LABEL_67;
  }
  if ( !a10 )
  {
    v36 = 39;
    goto LABEL_58;
  }
  v47 = *((_QWORD *)this + 9);
  v46 = *((_DWORD *)this + 28);
  LODWORD(Process) = *((_DWORD *)this + 29);
  LODWORD(ppInterface) = *((_DWORD *)this + 30);
  WindowsDeleteString(0);
  AcquireSRWLockShared((PSRWLOCK)this + 36);
  string = 0;
  v18 = (const WCHAR *)*((_QWORD *)this + 16);
  if ( v18 )
  {
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
  }
  else
  {
    LODWORD(v19) = 0;
  }
  v20 = WindowsCreateString(v18, v19, &string);
  if ( v20 < 0 )
    string = 0;
  if ( this != (Windows::Internal::StateRepository::TileViewServer *)-288LL )
    ReleaseSRWLockShared((PSRWLOCK)this + 36);
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.tileview-custom.cpp",
      (const char *)(unsigned int)v20,
      (int)string);
LABEL_69:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_70;
  }
  v40 = 0;
  WindowsDeleteString(0);
  v40 = 0;
  AcquireSRWLockShared((PSRWLOCK)this + 36);
  v40 = 0;
  v21 = (const WCHAR *)*((_QWORD *)this + 34);
  if ( v21 )
  {
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
  }
  else
  {
    LODWORD(v22) = 0;
  }
  v20 = WindowsCreateString(v21, v22, &v40);
  if ( v20 < 0 )
    v40 = 0;
  if ( this != (Windows::Internal::StateRepository::TileViewServer *)-288LL )
    ReleaseSRWLockShared((PSRWLOCK)this + 36);
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.tileview-custom.cpp",
      (const char *)(unsigned int)v20,
      (int)string);
    goto LABEL_50;
  }
  v44 = 0;
  AcquireSRWLockShared((PSRWLOCK)this + 36);
  v23 = *((_QWORD *)this + 23);
  v24 = 0;
  if ( v23 )
  {
    v25 = (const void *)*((_QWORD *)this + 22);
    v26 = CoTaskMemAlloc(*((_QWORD *)this + 23));
    v27 = v26;
    if ( !v26 )
    {
      v20 = -2147024882;
      LODWORD(v23) = 0;
      goto LABEL_39;
    }
    memcpy_0(v26, v25, v23);
    v24 = v27;
  }
  v20 = 0;
LABEL_39:
  if ( this != (Windows::Internal::StateRepository::TileViewServer *)-288LL )
    ReleaseSRWLockShared((PSRWLOCK)this + 36);
  if ( v20 >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    v28 = SRDictionaryToPropertySet((unsigned int)v23, v24, &v44);
    v20 = v28;
    if ( v28 >= 0 )
    {
      v29 = *(struct _GUID *)((char *)this + 252);
      v30 = *((_QWORD *)this + 28);
      v31 = *((_QWORD *)this + 27);
      *a2 = v47;
      *(_DWORD *)a3 = v46;
      *(_DWORD *)a4 = (_DWORD)Process;
      *(_DWORD *)a5 = (_DWORD)ppInterface;
      v32 = string;
      string = 0;
      *a6 = v32;
      v33 = v40;
      v40 = 0;
      *a7 = v33;
      v34 = v44;
      v44 = 0;
      *a8 = v34;
      *a9 = v29;
      if ( v31 <= v30 )
        v31 = v30;
      *a10 = v31;
      WindowsDeleteString(0);
      v40 = 0;
      WindowsDeleteString(string);
      v20 = 0;
      goto LABEL_46;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.tileview-custom.cpp",
      (const char *)(unsigned int)v28,
      (int)string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    WindowsDeleteString(v40);
    v40 = 0;
    goto LABEL_69;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x38,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.tileview-custom.cpp",
    (const char *)(unsigned int)v20,
    (int)string);
  v37 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v37 + 16LL))(v37);
  }
LABEL_50:
  WindowsDeleteString(v40);
  v40 = 0;
  WindowsDeleteString(string);
LABEL_46:
  string = 0;
LABEL_47:
  _InterlockedDecrement(&StateRepository::WinRT::Client::RequestInProgress::s_count);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180058540  mov     rax, rsp
0x180058543  mov     [rax+8], rbx
0x180058547  mov     [rax+20h], r9
0x18005854b  mov     [rax+18h], r8
0x18005854f  mov     [rax+10h], rdx
0x180058553  push    rbp
0x180058554  push    rsi
0x180058555  push    rdi
0x180058556  push    r12
0x180058558  push    r13
0x18005855a  push    r14
0x18005855c  push    r15
0x18005855e  mov     rbp, rsp
0x180058561  sub     rsp, 60h
0x180058565  mov     rsi, r9
0x180058568  mov     r15, r8
0x18005856b  mov     r12, rdx
0x18005856e  mov     r14, rcx
0x180058571  xor     r13d, r13d
0x180058574  mov     [rbp+var_2C], r13b
0x180058578  lock inc cs:?s_count@RequestInProgress@Client@WinRT@StateRepository@@0JC; long volatile StateRepository::WinRT::Client::RequestInProgress::s_count
0x18005857f  mov     [rbp+ppInterface], r13
0x180058583  lea     rdx, [rbp+ppInterface]; ppInterface
0x180058587  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x18005858e  call    cs:__imp_CoGetCallContext
0x180058594  mov     ebx, eax
0x180058596  test    eax, eax
0x180058598  js      loc_1800588FF
0x18005859e  mov     [rbp+Process], r13
0x1800585a2  mov     rcx, [rbp+ppInterface]
0x1800585a6  mov     rax, [rcx]
0x1800585a9  lea     r8, [rbp+Process]
0x1800585ad  mov     edx, 1000h
0x1800585b2  mov     rax, [rax+18h]
0x1800585b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800585bb  test    eax, eax
0x1800585bd  js      loc_1800588E7
0x1800585c3  mov     rcx, [rbp+Process]; Process
0x1800585c7  call    cs:__imp_GetProcessId
0x1800585cd  mov     edi, eax
0x1800585cf  mov     rcx, [rbp+Process]; hObject
0x1800585d3  lea     rax, [rcx-1]
0x1800585d7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800585db  jbe     loc_180058988
0x1800585e1  mov     rcx, [rbp+ppInterface]
0x1800585e5  test    rcx, rcx
0x1800585e8  jz      short loc_1800585FB
0x1800585ea  mov     [rbp+ppInterface], r13
0x1800585ee  mov     rax, [rcx]
0x1800585f1  mov     rax, [rax+10h]
0x1800585f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800585fa  nop
0x1800585fb  mov     ebx, r13d
0x1800585fe  mov     rcx, [rbp+38h]; this
0x180058602  test    ebx, ebx
0x180058604  jns     short loc_18005861A
0x180058606  mov     r9d, ebx; char *
0x180058609  lea     r8, aOnecoreBaseApp_355; "onecore\\base\\appmodel\\staterepositor"...
0x180058610  mov     edx, 3Bh ; ';'; void *
0x180058615  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005861a  mov     [rbp+var_30], edi
0x18005861d  test    r12, r12
0x180058620  jz      loc_180058927
0x180058626  test    r15, r15
0x180058629  jz      loc_1800589C7
0x18005862f  xor     r15d, r15d
0x180058632  test    rsi, rsi
0x180058635  jz      loc_180058A38
0x18005863b  mov     r13, [rbp+arg_20]
0x18005863f  test    r13, r13
0x180058642  jz      loc_180058A3F
0x180058648  cmp     [rbp+arg_28], r15
0x18005864c  jz      loc_180058A46
0x180058652  cmp     [rbp+arg_38], r15
0x180058656  jz      loc_180058A4D
0x18005865c  cmp     [rbp+arg_40], r15
0x180058663  jz      loc_1800589CE
0x180058669  cmp     [rbp+arg_48], r15
0x180058670  jz      loc_180058981
0x180058676  mov     rax, [r14+48h]
0x18005867a  mov     [rbp+var_8], rax
0x18005867e  mov     eax, [r14+70h]
0x180058682  mov     [rbp+var_10], eax
0x180058685  mov     eax, [r14+74h]
0x180058689  mov     dword ptr [rbp+Process], eax
0x18005868c  mov     eax, [r14+78h]
0x180058690  mov     dword ptr [rbp+ppInterface], eax
0x180058693  mov     [rbp+string], r15
0x180058697  xor     ecx, ecx; string
0x180058699  call    cs:__imp_WindowsDeleteString
0x18005869f  mov     [rbp+string], r15
0x1800586a3  lea     rdi, [r14+120h]
0x1800586aa  mov     rcx, rdi; SRWLock
0x1800586ad  call    cs:__imp_AcquireSRWLockShared
0x1800586b3  mov     [rbp+string], r15
0x1800586b7  mov     rcx, [r14+80h]; sourceString
0x1800586be  test    rcx, rcx
0x1800586c1  jz      loc_180058917
0x1800586c7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800586cb  inc     rdx; length
0x1800586ce  cmp     [rcx+rdx*2], r15w
0x1800586d3  jnz     short loc_1800586CB
0x1800586d5  lea     r8, [rbp+string]; string
0x1800586d9  call    cs:__imp_WindowsCreateString
0x1800586df  mov     ebx, eax
0x1800586e1  test    eax, eax
0x1800586e3  js      loc_180058A57
0x1800586e9  test    rdi, rdi
0x1800586ec  jz      short loc_1800586F7
0x1800586ee  mov     rcx, rdi; SRWLock
0x1800586f1  call    cs:__imp_ReleaseSRWLockShared
0x1800586f7  test    ebx, ebx
0x1800586f9  js      loc_180058A60
0x1800586ff  mov     [rbp+var_38], r15
0x180058703  xor     ecx, ecx; string
0x180058705  call    cs:__imp_WindowsDeleteString
0x18005870b  mov     [rbp+var_38], r15
0x18005870f  mov     rcx, rdi; SRWLock
0x180058712  call    cs:__imp_AcquireSRWLockShared
0x180058718  mov     [rbp+var_38], r15
0x18005871c  mov     rcx, [r14+110h]; sourceString
0x180058723  test    rcx, rcx
0x180058726  jz      loc_18005891F
0x18005872c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180058730  inc     rdx; length
0x180058733  cmp     [rcx+rdx*2], r15w
0x180058738  jnz     short loc_180058730
0x18005873a  lea     r8, [rbp+var_38]; string
0x18005873e  call    cs:__imp_WindowsCreateString
0x180058744  mov     ebx, eax
0x180058746  test    eax, eax
0x180058748  js      loc_180058A7A
0x18005874e  test    rdi, rdi
0x180058751  jz      short loc_18005875C
0x180058753  mov     rcx, rdi; SRWLock
0x180058756  call    cs:__imp_ReleaseSRWLockShared
0x18005875c  test    ebx, ebx
0x18005875e  js      loc_1800588A7
0x180058764  mov     [rbp+var_20], r15
0x180058768  mov     rcx, rdi; SRWLock
0x18005876b  call    cs:__imp_AcquireSRWLockShared
0x180058771  mov     rsi, [r14+0B8h]
0x180058778  mov     r12, r15
0x18005877b  test    rsi, rsi
0x18005877e  jz      short loc_1800587B0
0x180058780  mov     r15, [r14+0B0h]
0x180058787  mov     rcx, rsi; cb
0x18005878a  call    cs:__imp_CoTaskMemAlloc
0x180058790  mov     rbx, rax
0x180058793  test    rax, rax
0x180058796  jz      loc_1800588EF
0x18005879c  mov     r8, rsi; Size
0x18005879f  mov     rdx, r15; Src
0x1800587a2  mov     rcx, rax; void *
0x1800587a5  call    memcpy_0
0x1800587aa  mov     r12, rbx
0x1800587ad  xor     r15d, r15d
0x1800587b0  mov     ebx, r15d
0x1800587b3  test    rdi, rdi
0x1800587b6  jnz     loc_1800588D9
0x1800587bc  test    ebx, ebx
0x1800587be  js      loc_180058949
0x1800587c4  lea     rcx, [rbp+var_20]
0x1800587c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800587cd  lea     r8, [rbp+var_20]
0x1800587d1  mov     rdx, r12
0x1800587d4  mov     ecx, esi
0x1800587d6  call    cs:__imp_SRDictionaryToPropertySet
0x1800587dc  mov     ebx, eax
0x1800587de  test    eax, eax
0x1800587e0  js      loc_1800589ED
0x1800587e6  movups  xmm0, xmmword ptr [r14+0FCh]
0x1800587ee  mov     r8, [r14+0E0h]
0x1800587f5  mov     rdx, [r14+0D8h]
0x1800587fc  mov     rax, [rbp+arg_8]
0x180058800  mov     rcx, [rbp+var_8]
0x180058804  mov     [rax], rcx
0x180058807  mov     rax, [rbp+arg_10]
0x18005880b  mov     ecx, [rbp+var_10]
0x18005880e  mov     [rax], ecx
0x180058810  mov     rax, [rbp+arg_18]
0x180058814  mov     ecx, dword ptr [rbp+Process]
0x180058817  mov     [rax], ecx
0x180058819  mov     eax, dword ptr [rbp+ppInterface]
0x18005881c  mov     [r13+0], eax
0x180058820  mov     rax, [rbp+string]
0x180058824  mov     [rbp+string], r15
0x180058828  mov     rcx, [rbp+arg_28]
0x18005882c  mov     [rcx], rax
0x18005882f  mov     rcx, [rbp+var_38]
0x180058833  mov     [rbp+var_38], r15
0x180058837  mov     rax, [rbp+arg_30]
0x18005883b  mov     [rax], rcx
0x18005883e  mov     rax, [rbp+var_20]
0x180058842  mov     [rbp+var_20], r15
0x180058846  mov     rcx, [rbp+arg_38]
0x18005884a  mov     [rcx], rax
0x18005884d  mov     rax, [rbp+arg_40]
0x180058854  movdqu  xmmword ptr [rax], xmm0
0x180058858  cmp     rdx, r8
0x18005885b  cmovle  rdx, r8
0x18005885f  mov     rax, [rbp+arg_48]
0x180058866  mov     [rax], rdx
0x180058869  xor     ecx, ecx; string
0x18005886b  call    cs:__imp_WindowsDeleteString
0x180058871  mov     [rbp+var_38], r15
0x180058875  mov     rcx, [rbp+string]; string
0x180058879  call    cs:__imp_WindowsDeleteString
0x18005887f  mov     ebx, r15d
0x180058882  mov     [rbp+string], r15
0x180058886  lock dec cs:?s_count@RequestInProgress@Client@WinRT@StateRepository@@0JC; long volatile StateRepository::WinRT::Client::RequestInProgress::s_count
0x18005888d  mov     eax, ebx
0x18005888f  mov     rbx, [rsp+60h+arg_0]
0x180058897  add     rsp, 60h
0x18005889b  pop     r15
0x18005889d  pop     r14
0x18005889f  pop     r13
0x1800588a1  pop     r12
0x1800588a3  pop     rdi
0x1800588a4  pop     rsi
0x1800588a5  pop     rbp
0x1800588a6  retn
0x1800588a7  mov     rcx, [rbp+38h]; this
0x1800588ab  mov     r9d, ebx; char *
0x1800588ae  lea     r8, aOnecoreBaseApp_258; "onecore\\base\\appmodel\\staterepositor"...
0x1800588b5  mov     edx, 34h ; '4'; void *
0x1800588ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800588bf  mov     rcx, [rbp+var_38]; string
0x1800588c3  call    cs:__imp_WindowsDeleteString
0x1800588c9  mov     [rbp+var_38], r15
0x1800588cd  mov     rcx, [rbp+string]; string
0x1800588d1  call    cs:__imp_WindowsDeleteString
0x1800588d7  jmp     short loc_180058882
0x1800588d9  mov     rcx, rdi; SRWLock
0x1800588dc  call    cs:__imp_ReleaseSRWLockShared
0x1800588e2  jmp     loc_1800587BC
0x1800588e7  mov     edi, r13d
0x1800588ea  jmp     loc_1800585CF
0x1800588ef  mov     ebx, 8007000Eh
0x1800588f4  xor     r15d, r15d
0x1800588f7  mov     esi, r15d
0x1800588fa  jmp     loc_1800587B3
0x1800588ff  cmp     eax, 80010117h
0x180058904  jnz     loc_180058993
0x18005890a  call    cs:__imp_GetCurrentProcessId
0x180058910  mov     edi, eax
0x180058912  jmp     loc_1800585E1
0x180058917  mov     edx, r15d
0x18005891a  jmp     loc_1800586D5
0x18005891f  mov     edx, r15d
0x180058922  jmp     loc_18005873A
0x180058927  mov     edx, 20h ; ' '; void *
0x18005892c  mov     ebx, 80004003h
0x180058931  lea     r8, aOnecoreBaseApp_258; "onecore\\base\\appmodel\\staterepositor"...
0x180058938  mov     r9d, ebx; char *
0x18005893b  mov     rcx, [rbp+38h]; this
0x18005893f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058944  jmp     loc_180058886
0x180058949  mov     rcx, [rbp+38h]; this
0x18005894d  mov     r9d, ebx; char *
0x180058950  lea     r8, aOnecoreBaseApp_258; "onecore\\base\\appmodel\\staterepositor"...
0x180058957  mov     edx, 38h ; '8'; void *
0x18005895c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058961  nop
0x180058962  mov     rcx, [rbp+var_20]
0x180058966  test    rcx, rcx
0x180058969  jz      short loc_18005897C
0x18005896b  mov     [rbp+var_20], r15
0x18005896f  mov     rax, [rcx]
0x180058972  mov     rax, [rax+10h]
0x180058976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005897b  nop
0x18005897c  jmp     loc_1800588BF
0x180058981  mov     edx, 27h ; '''
0x180058986  jmp     short loc_18005892C
0x180058988  call    cs:__imp_CloseHandle
0x18005898e  jmp     loc_1800585E1
0x180058993  cmp     eax, 80004002h
0x180058998  jz      loc_18005890A
0x18005899e  mov     edi, r13d
0x1800589a1  mov     rcx, [rbp+38h]; this
0x1800589a5  mov     r9d, eax; char *
0x1800589a8  lea     r8, aOnecoreBaseApp_355; "onecore\\base\\appmodel\\staterepositor"...
0x1800589af  mov     edx, 33h ; '3'; void *
0x1800589b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800589b9  lea     rcx, [rbp+ppInterface]
0x1800589bd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800589c2  jmp     loc_1800585FE
0x1800589c7  mov     edx, 21h ; '!'
0x1800589cc  jmp     short loc_1800589D3
0x1800589ce  mov     edx, 26h ; '&'; void *
0x1800589d3  mov     ebx, 80004003h
0x1800589d8  lea     r8, aOnecoreBaseApp_258; "onecore\\base\\appmodel\\staterepositor"...
0x1800589df  mov     r9d, ebx; char *
0x1800589e2  mov     rcx, [rbp+38h]; this
0x1800589e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800589eb  jmp     short loc_180058A2A
0x1800589ed  mov     rcx, [rbp+38h]; this
0x1800589f1  mov     r9d, eax; char *
0x1800589f4  lea     r8, aOnecoreBaseApp_258; "onecore\\base\\appmodel\\staterepositor"...
  ... truncated ...
```
