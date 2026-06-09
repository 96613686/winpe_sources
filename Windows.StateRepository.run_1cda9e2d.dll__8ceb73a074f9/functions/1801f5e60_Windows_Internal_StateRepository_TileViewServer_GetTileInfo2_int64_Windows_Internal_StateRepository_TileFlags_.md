# Windows::Internal::StateRepository::TileViewServer::GetTileInfo2(__int64 *,Windows::Internal::StateRepository::TileFlags *,Windows::Internal::StateRepository::TileType *,Windows::Internal::StateRepository::TileTemplate *,HSTRING__ * *,HSTRING__ * *,uint *,uchar * *,_GUID *,__int64 *)

- ea: `0x1801f5e60`
- end: `0x1801f61ae`
- name: `?GetTileInfo2@TileViewServer@StateRepository@Internal@Windows@@UEAAJPEA_JPEAW4TileFlags@234@PEAW4TileType@234@PEAW4TileTemplate@234@PEAPEAUHSTRING__@@4PEAIPEAPEAEPEAU_GUID@@0@Z`
- size: `846`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::TileViewServer *__hidden this, __int64 *, enum Windows::Internal::StateRepository::TileFlags *, enum Windows::Internal::StateRepository::TileType *, enum Windows::Internal::StateRepository::TileTemplate *, HSTRING *, HSTRING *, unsigned int *, unsigned __int8 **, struct _GUID *, __int64 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a834`
- `0x18000b380`
- `0x18001a9e0`
- `0x1800649b0`
- `0x18006e480`
- `0x18006f5f0`
- `0x18006f740`
- `0x18006fd90`
- `0x1800c07c8`
- `0x1801f5904`
- `0x1801f5e60`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5f85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5fc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5fde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f601c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6093`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f60a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f616e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f617c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5f85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5fc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5fde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f601c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6093`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f60a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f616e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f617c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f6089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f6089`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::TileViewServer::GetTileInfo2(
        Windows::Internal::StateRepository::TileViewServer *this,
        __int64 *a2,
        enum Windows::Internal::StateRepository::TileFlags *a3,
        enum Windows::Internal::StateRepository::TileType *a4,
        enum Windows::Internal::StateRepository::TileTemplate *a5,
        HSTRING *a6,
        HSTRING *a7,
        unsigned int *a8,
        unsigned __int8 **a9,
        struct _GUID *a10,
        __int64 *a11)
{
  unsigned int Dictionary; // ebx
  __int64 v16; // rdx
  int v17; // eax
  Windows::Internal::StateRepository::TileViewServer *v18; // rdi
  int TileId; // eax
  int ApplicationUserModelId; // eax
  unsigned __int64 v21; // r9
  __int64 v22; // rdx
  void *v23; // rcx
  int TileUniqueId; // eax
  int v25; // eax
  struct _GUID v26; // xmm0
  HSTRING v27; // rcx
  __int64 v28; // rax
  HSTRING string; // [rsp+20h] [rbp-60h] BYREF
  HSTRING v31; // [rsp+28h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v33; // [rsp+38h] [rbp-48h] BYREF
  int v34; // [rsp+3Ch] [rbp-44h]
  int v35; // [rsp+40h] [rbp-40h]
  int v36; // [rsp+44h] [rbp-3Ch]
  __int64 v37; // [rsp+48h] [rbp-38h] BYREF
  struct _GUID v38; // [rsp+50h] [rbp-30h] BYREF
  char v39; // [rsp+60h] [rbp-20h]
  __int64 v40; // [rsp+68h] [rbp-18h]
  _BYTE v41[16]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  StateRepository::WinRT::Client::RequestInProgress::RequestInProgress(
    (StateRepository::WinRT::Client::RequestInProgress *)v41,
    0);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_TileView_GetMaxChangeIdByUser_QueryOptimization>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_StateRepository_TileView_GetMaxChangeIdByUser_QueryOptimization>::GetImpl'::`2'::impl) )
  {
    if ( !a2 )
    {
      v16 = 92;
LABEL_5:
      Dictionary = -2147467261;
      goto LABEL_6;
    }
    if ( !a3 )
    {
      v16 = 93;
      goto LABEL_5;
    }
    if ( !a4 )
    {
      v16 = 94;
      goto LABEL_5;
    }
    if ( !a5 )
    {
      v16 = 95;
      goto LABEL_5;
    }
    if ( !a6 )
    {
      v16 = 96;
      goto LABEL_5;
    }
    if ( !a8 )
    {
      v16 = 97;
      goto LABEL_5;
    }
    if ( !a9 )
    {
      v16 = 98;
      goto LABEL_5;
    }
    if ( !a10 )
    {
      v16 = 99;
      goto LABEL_5;
    }
    if ( !a11 )
    {
      v16 = 100;
      goto LABEL_5;
    }
    v40 = *((_QWORD *)this + 7);
    v17 = *((_DWORD *)this + 24);
    v18 = (Windows::Internal::StateRepository::TileViewServer *)((char *)this - 16);
    v34 = v17;
    string = 0;
    v35 = *((_DWORD *)v18 + 29);
    v36 = *((_DWORD *)v18 + 30);
    WindowsDeleteString(0);
    string = 0;
    TileId = Windows::Internal::StateRepository::TileViewServer::get_TileId(v18, &string);
    Dictionary = TileId;
    if ( TileId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.til"
                      "eview-custom.cpp",
        (const char *)(unsigned int)TileId,
        (int)string);
LABEL_25:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_40;
    }
    v31 = 0;
    WindowsDeleteString(0);
    v31 = 0;
    ApplicationUserModelId = Windows::Internal::StateRepository::TileViewServer::get_ApplicationUserModelId(v18, &v31);
    Dictionary = ApplicationUserModelId;
    if ( ApplicationUserModelId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.til"
                      "eview-custom.cpp",
        (const char *)(unsigned int)ApplicationUserModelId,
        (int)string);
      WindowsDeleteString(v31);
      v31 = 0;
      goto LABEL_25;
    }
    v33 = 0;
    pv = 0;
    *(_QWORD *)v38.Data4 = 0;
    *(_QWORD *)&v38.Data1 = &pv;
    v39 = 1;
    Dictionary = Windows::Internal::StateRepository::TileViewServer::Get_Dictionary(
                   v18,
                   &v33,
                   (unsigned __int8 **)v38.Data4);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v38);
    if ( (Dictionary & 0x80000000) == 0 )
    {
      v38 = 0;
      TileUniqueId = Windows::Internal::StateRepository::TileViewServer::get_TileUniqueId(v18, &v38);
      Dictionary = TileUniqueId;
      if ( TileUniqueId >= 0 )
      {
        v37 = 0;
        v25 = Windows::Internal::StateRepository::TileViewServer::get_ChangeId(v18, &v37);
        Dictionary = v25;
        if ( v25 >= 0 )
        {
          v26 = v38;
          *a2 = v40;
          *(_DWORD *)a3 = v34;
          *(_DWORD *)a4 = v35;
          v27 = v31;
          *(_DWORD *)a5 = v36;
          *a6 = string;
          string = 0;
          v31 = 0;
          *a7 = v27;
          *a8 = v33;
          *a9 = (unsigned __int8 *)pv;
          v28 = v37;
          *a10 = v26;
          *a11 = v28;
          pv = 0;
          WindowsDeleteString(0);
          v31 = 0;
          WindowsDeleteString(string);
          Dictionary = 0;
LABEL_39:
          string = 0;
          goto LABEL_40;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x78,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.t"
                        "ileview-custom.cpp",
          (const char *)(unsigned int)v25,
          (int)string);
LABEL_31:
        v23 = pv;
        pv = 0;
        if ( v23 )
          CoTaskMemFree(v23);
        WindowsDeleteString(v31);
        v31 = 0;
        WindowsDeleteString(string);
        goto LABEL_39;
      }
      v21 = (unsigned int)TileUniqueId;
      v22 = 118;
    }
    else
    {
      v21 = Dictionary;
      v22 = 116;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.tileview-custom.cpp",
      (const char *)v21,
      (int)string);
    goto LABEL_31;
  }
  Dictionary = -2147467263;
  v16 = 90;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.tileview-custom.cpp",
    (const char *)Dictionary,
    (int)string);
LABEL_40:
  StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress((StateRepository::WinRT::Client::RequestInProgress *)v41);
  return Dictionary;
}

```

## disassembly

```asm
0x1801f5e60  mov     rax, rsp
0x1801f5e63  mov     [rax+8], rbx
0x1801f5e67  mov     [rax+20h], r9
0x1801f5e6b  mov     [rax+18h], r8
0x1801f5e6f  mov     [rax+10h], rdx
0x1801f5e73  push    rbp
0x1801f5e74  push    rsi
0x1801f5e75  push    rdi
0x1801f5e76  push    r12
0x1801f5e78  push    r13
0x1801f5e7a  push    r14
0x1801f5e7c  push    r15
0x1801f5e7e  mov     rbp, rsp
0x1801f5e81  sub     rsp, 80h
0x1801f5e88  mov     r14, rdx
0x1801f5e8b  mov     rdi, rcx
0x1801f5e8e  xor     edx, edx; bool
0x1801f5e90  lea     rcx, [rbp+var_10]; this
0x1801f5e94  mov     rbx, r9
0x1801f5e97  mov     rsi, r8
0x1801f5e9a  call    ??0RequestInProgress@Client@WinRT@StateRepository@@QEAA@_N@Z; StateRepository::WinRT::Client::RequestInProgress::RequestInProgress(bool)
0x1801f5e9f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StateRepository_TileView_GetMaxChangeIdByUser_QueryOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_TileView_GetMaxChangeIdByUser_QueryOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_TileView_GetMaxChangeIdByUser_QueryOptimization> `wil::Feature<__WilFeatureTraits_Feature_StateRepository_TileView_GetMaxChangeIdByUser_QueryOptimization>::GetImpl(void)'::`2'::impl
0x1801f5ea6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_TileView_GetMaxChangeIdByUser_QueryOptimization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_TileView_GetMaxChangeIdByUser_QueryOptimization>::__private_IsEnabled(void)
0x1801f5eab  test    al, al
0x1801f5ead  jnz     short loc_1801F5EBB
0x1801f5eaf  mov     ebx, 80004001h
0x1801f5eb4  mov     edx, 5Ah ; 'Z'
0x1801f5eb9  jmp     short loc_1801F5EC9
0x1801f5ebb  test    r14, r14
0x1801f5ebe  jnz     short loc_1801F5EE1
0x1801f5ec0  lea     edx, [r14+5Ch]; void *
0x1801f5ec4  mov     ebx, 80004003h
0x1801f5ec9  mov     rcx, [rbp+38h]; this
0x1801f5ecd  lea     r8, aOnecoreBaseApp_258; "onecore\\base\\appmodel\\staterepositor"...
0x1801f5ed4  mov     r9d, ebx; char *
0x1801f5ed7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f5edc  jmp     loc_1801F6188
0x1801f5ee1  test    rsi, rsi
0x1801f5ee4  jnz     short loc_1801F5EEB
0x1801f5ee6  lea     edx, [rsi+5Dh]
0x1801f5ee9  jmp     short loc_1801F5EC4
0x1801f5eeb  test    rbx, rbx
0x1801f5eee  jnz     short loc_1801F5EF5
0x1801f5ef0  lea     edx, [rbx+5Eh]
0x1801f5ef3  jmp     short loc_1801F5EC4
0x1801f5ef5  mov     rsi, [rbp+arg_20]
0x1801f5ef9  test    rsi, rsi
0x1801f5efc  jnz     short loc_1801F5F03
0x1801f5efe  lea     edx, [rsi+5Fh]
0x1801f5f01  jmp     short loc_1801F5EC4
0x1801f5f03  mov     r14, [rbp+arg_28]
0x1801f5f07  test    r14, r14
0x1801f5f0a  jnz     short loc_1801F5F12
0x1801f5f0c  lea     edx, [r14+60h]
0x1801f5f10  jmp     short loc_1801F5EC4
0x1801f5f12  mov     r15, [rbp+arg_38]
0x1801f5f16  test    r15, r15
0x1801f5f19  jnz     short loc_1801F5F21
0x1801f5f1b  lea     edx, [r15+61h]
0x1801f5f1f  jmp     short loc_1801F5EC4
0x1801f5f21  mov     r12, [rbp+arg_40]
0x1801f5f28  test    r12, r12
0x1801f5f2b  jnz     short loc_1801F5F34
0x1801f5f2d  lea     edx, [r12+62h]
0x1801f5f32  jmp     short loc_1801F5EC4
0x1801f5f34  mov     r13, [rbp+arg_48]
0x1801f5f3b  test    r13, r13
0x1801f5f3e  jnz     short loc_1801F5F49
0x1801f5f40  lea     edx, [r13+63h]
0x1801f5f44  jmp     loc_1801F5EC4
0x1801f5f49  cmp     [rbp+arg_50], 0
0x1801f5f51  jnz     short loc_1801F5F5D
0x1801f5f53  mov     edx, 64h ; 'd'
0x1801f5f58  jmp     loc_1801F5EC4
0x1801f5f5d  mov     rax, [rdi+38h]
0x1801f5f61  xor     ecx, ecx; string
0x1801f5f63  mov     [rbp+var_18], rax
0x1801f5f67  mov     eax, [rdi+60h]
0x1801f5f6a  add     rdi, 0FFFFFFFFFFFFFFF0h
0x1801f5f6e  mov     [rbp+var_44], eax
0x1801f5f71  mov     [rbp+string], 0
0x1801f5f79  mov     eax, [rdi+74h]
0x1801f5f7c  mov     [rbp+var_40], eax
0x1801f5f7f  mov     eax, [rdi+78h]
0x1801f5f82  mov     [rbp+var_3C], eax
0x1801f5f85  call    cs:__imp_WindowsDeleteString
0x1801f5f8b  lea     rdx, [rbp+string]; HSTRING *
0x1801f5f8f  mov     [rbp+string], 0
0x1801f5f97  mov     rcx, rdi; this
0x1801f5f9a  call    ?get_TileId@TileViewServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z; Windows::Internal::StateRepository::TileViewServer::get_TileId(HSTRING__ * *)
0x1801f5f9f  mov     ebx, eax
0x1801f5fa1  test    eax, eax
0x1801f5fa3  jns     short loc_1801F5FD4
0x1801f5fa5  mov     rcx, [rbp+38h]; this
0x1801f5fa9  lea     r8, aOnecoreBaseApp_258; "onecore\\base\\appmodel\\staterepositor"...
0x1801f5fb0  mov     r9d, eax; char *
0x1801f5fb3  mov     edx, 6Fh ; 'o'; void *
0x1801f5fb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f5fbd  mov     rcx, [rbp+string]; string
0x1801f5fc1  call    cs:__imp_WindowsDeleteString
0x1801f5fc7  mov     [rbp+string], 0
0x1801f5fcf  jmp     loc_1801F6188
0x1801f5fd4  xor     ecx, ecx; string
0x1801f5fd6  mov     [rbp+var_58], 0
0x1801f5fde  call    cs:__imp_WindowsDeleteString
0x1801f5fe4  lea     rdx, [rbp+var_58]; HSTRING *
0x1801f5fe8  mov     [rbp+var_58], 0
0x1801f5ff0  mov     rcx, rdi; this
0x1801f5ff3  call    ?get_ApplicationUserModelId@TileViewServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z; Windows::Internal::StateRepository::TileViewServer::get_ApplicationUserModelId(HSTRING__ * *)
0x1801f5ff8  xor     ecx, ecx
0x1801f5ffa  mov     ebx, eax
0x1801f5ffc  test    eax, eax
0x1801f5ffe  jns     short loc_1801F602C
0x1801f6000  mov     rcx, [rbp+38h]; this
0x1801f6004  lea     r8, aOnecoreBaseApp_258; "onecore\\base\\appmodel\\staterepositor"...
0x1801f600b  mov     r9d, eax; char *
0x1801f600e  mov     edx, 71h ; 'q'; void *
0x1801f6013  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f6018  mov     rcx, [rbp+var_58]; string
0x1801f601c  call    cs:__imp_WindowsDeleteString
0x1801f6022  mov     [rbp+var_58], 0
0x1801f602a  jmp     short loc_1801F5FBD
0x1801f602c  mov     [rbp+var_48], ecx
0x1801f602f  lea     rax, [rbp+pv]
0x1801f6033  mov     [rbp+pv], rcx
0x1801f6037  lea     r8, [rbp+var_30.Data4]; unsigned __int8 **
0x1801f603b  mov     qword ptr [rbp+var_30.Data4], rcx
0x1801f603f  lea     rdx, [rbp+var_48]; unsigned int *
0x1801f6043  mov     rcx, rdi; this
0x1801f6046  mov     qword ptr [rbp+var_30.Data1], rax
0x1801f604a  mov     [rbp+var_20], 1
0x1801f604e  call    ?Get_Dictionary@TileViewServer@StateRepository@Internal@Windows@@UEAAJPEAIPEAPEAE@Z; Windows::Internal::StateRepository::TileViewServer::Get_Dictionary(uint *,uchar * *)
0x1801f6053  lea     rcx, [rbp+var_30]
0x1801f6057  mov     ebx, eax
0x1801f6059  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1801f605e  test    ebx, ebx
0x1801f6060  jns     short loc_1801F60AC
0x1801f6062  mov     r9d, ebx; char *
0x1801f6065  mov     edx, 74h ; 't'; void *
0x1801f606a  mov     rcx, [rbp+38h]; this
0x1801f606e  lea     r8, aOnecoreBaseApp_258; "onecore\\base\\appmodel\\staterepositor"...
0x1801f6075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f607a  xor     edi, edi
0x1801f607c  mov     rcx, [rbp+pv]; pv
0x1801f6080  mov     [rbp+pv], rdi
0x1801f6084  test    rcx, rcx
0x1801f6087  jz      short loc_1801F608F
0x1801f6089  call    cs:__imp_CoTaskMemFree
0x1801f608f  mov     rcx, [rbp+var_58]; string
0x1801f6093  call    cs:__imp_WindowsDeleteString
0x1801f6099  mov     rcx, [rbp+string]; string
0x1801f609d  mov     [rbp+var_58], rdi
0x1801f60a1  call    cs:__imp_WindowsDeleteString
0x1801f60a7  jmp     loc_1801F6184
0x1801f60ac  xorps   xmm0, xmm0
0x1801f60af  lea     rdx, [rbp+var_30]; struct _GUID *
0x1801f60b3  mov     rcx, rdi; this
0x1801f60b6  movups  xmmword ptr [rbp+var_30.Data1], xmm0
0x1801f60ba  call    ?get_TileUniqueId@TileViewServer@StateRepository@Internal@Windows@@UEAAJPEAU_GUID@@@Z; Windows::Internal::StateRepository::TileViewServer::get_TileUniqueId(_GUID *)
0x1801f60bf  mov     ebx, eax
0x1801f60c1  test    eax, eax
0x1801f60c3  jns     short loc_1801F60CF
0x1801f60c5  mov     r9d, eax
0x1801f60c8  mov     edx, 76h ; 'v'
0x1801f60cd  jmp     short loc_1801F606A
0x1801f60cf  lea     rdx, [rbp+var_38]; __int64 *
0x1801f60d3  mov     [rbp+var_38], 0
0x1801f60db  mov     rcx, rdi; this
0x1801f60de  call    ?get_ChangeId@TileViewServer@StateRepository@Internal@Windows@@UEAAJPEA_J@Z; Windows::Internal::StateRepository::TileViewServer::get_ChangeId(__int64 *)
0x1801f60e3  xor     edi, edi
0x1801f60e5  mov     ebx, eax
0x1801f60e7  test    eax, eax
0x1801f60e9  jns     short loc_1801F6106
0x1801f60eb  mov     rcx, [rbp+38h]; this
0x1801f60ef  lea     r8, aOnecoreBaseApp_258; "onecore\\base\\appmodel\\staterepositor"...
0x1801f60f6  mov     r9d, eax; char *
0x1801f60f9  lea     edx, [rdi+78h]; void *
0x1801f60fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f6101  jmp     loc_1801F607C
0x1801f6106  mov     rcx, [rbp+var_18]
0x1801f610a  mov     rax, [rbp+arg_8]
0x1801f610e  movups  xmm0, xmmword ptr [rbp+var_30.Data1]
0x1801f6112  mov     [rax], rcx
0x1801f6115  mov     ecx, [rbp+var_44]
0x1801f6118  mov     rax, [rbp+arg_10]
0x1801f611c  mov     [rax], ecx
0x1801f611e  mov     rax, [rbp+arg_18]
0x1801f6122  mov     ecx, [rbp+var_40]
0x1801f6125  mov     [rax], ecx
0x1801f6127  mov     rcx, [rbp+var_58]
0x1801f612b  mov     eax, [rbp+var_3C]
0x1801f612e  mov     [rsi], eax
0x1801f6130  mov     rax, [rbp+string]
0x1801f6134  mov     [r14], rax
0x1801f6137  mov     rax, [rbp+arg_30]
0x1801f613b  mov     [rbp+string], rdi
0x1801f613f  mov     [rbp+var_58], rdi
0x1801f6143  mov     [rax], rcx
0x1801f6146  mov     eax, [rbp+var_48]
0x1801f6149  mov     rcx, [rbp+arg_50]
0x1801f6150  mov     [r15], eax
0x1801f6153  mov     rax, [rbp+pv]
0x1801f6157  mov     [r12], rax
0x1801f615b  mov     rax, [rbp+var_38]
0x1801f615f  movdqu  xmmword ptr [r13+0], xmm0
0x1801f6165  mov     [rcx], rax
0x1801f6168  xor     ecx, ecx; string
0x1801f616a  mov     [rbp+pv], rdi
0x1801f616e  call    cs:__imp_WindowsDeleteString
0x1801f6174  mov     rcx, [rbp+string]; string
0x1801f6178  mov     [rbp+var_58], rdi
0x1801f617c  call    cs:__imp_WindowsDeleteString
0x1801f6182  mov     ebx, edi
0x1801f6184  mov     [rbp+string], rdi
0x1801f6188  lea     rcx, [rbp+var_10]; this
0x1801f618c  call    ??1RequestInProgress@Client@WinRT@StateRepository@@QEAA@XZ; StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress(void)
0x1801f6191  mov     eax, ebx
0x1801f6193  mov     rbx, [rsp+80h+arg_0]
0x1801f619b  add     rsp, 80h
0x1801f61a2  pop     r15
0x1801f61a4  pop     r14
0x1801f61a6  pop     r13
0x1801f61a8  pop     r12
0x1801f61aa  pop     rdi
0x1801f61ab  pop     rsi
0x1801f61ac  pop     rbp
0x1801f61ad  retn
```
