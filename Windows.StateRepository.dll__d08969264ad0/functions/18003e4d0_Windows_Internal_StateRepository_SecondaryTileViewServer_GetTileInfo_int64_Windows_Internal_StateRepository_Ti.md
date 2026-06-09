# Windows::Internal::StateRepository::SecondaryTileViewServer::GetTileInfo(__int64 *,Windows::Internal::StateRepository::TileFlags *,Windows::Internal::StateRepository::TileTemplate *,HSTRING__ * *,HSTRING__ * *,Windows::Foundation::Collections::IPropertySet * *,_GUID *,__int64 *)

- ea: `0x18003e4d0`
- end: `0x18003e816`
- name: `?GetTileInfo@SecondaryTileViewServer@StateRepository@Internal@Windows@@UEAAJPEA_JPEAW4TileFlags@234@PEAW4TileTemplate@234@PEAPEAUHSTRING__@@3PEAPEAUIPropertySet@Collections@Foundation@4@PEAU_GUID@@0@Z`
- size: `838`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::SecondaryTileViewServer *this, __int64 *, enum Windows::Internal::StateRepository::TileFlags *, enum Windows::Internal::StateRepository::TileTemplate *, HSTRING *, HSTRING *, struct Windows::Foundation::Collections::IPropertySet **, struct _GUID *, __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180003e54`
- `0x18000a834`
- `0x18000b380`
- `0x18001a9e0`
- `0x18003e4d0`
- `0x18003e880`
- `0x18003ef40`
- `0x1800bab30`
- `0x1801eabf0`
- `0x1801f58b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e5ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e60a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e673`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e6cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e773`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e7d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e7e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e5ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e60a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e673`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e6cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e773`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e7d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e7e7`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18003e6f3`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18003e6f3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::SecondaryTileViewServer::GetTileInfo(
        Windows::Internal::StateRepository::SecondaryTileViewServer *this,
        __int64 *a2,
        enum Windows::Internal::StateRepository::TileFlags *a3,
        enum Windows::Internal::StateRepository::TileTemplate *a4,
        HSTRING *a5,
        HSTRING *a6,
        struct Windows::Foundation::Collections::IPropertySet **a7,
        struct _GUID *a8,
        __int64 *a9)
{
  unsigned int ApplicationUserModelId; // ebx
  bool v14; // zf
  __int64 v15; // rdx
  int TileId; // eax
  int Dictionary; // eax
  __int64 v18; // rdx
  int v19; // eax
  struct _GUID v20; // xmm0
  HSTRING v21; // rcx
  unsigned __int8 *v22; // rax
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  HSTRING v25; // [rsp+28h] [rbp-48h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v26; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v27[4]; // [rsp+38h] [rbp-38h] BYREF
  char v28; // [rsp+3Ch] [rbp-34h]
  unsigned int v29; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int8 *v30; // [rsp+48h] [rbp-28h] BYREF
  int v31; // [rsp+50h] [rbp-20h]
  int v32; // [rsp+54h] [rbp-1Ch]
  __int64 v33; // [rsp+58h] [rbp-18h]
  struct _GUID v34; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  StateRepository::WinRT::Client::RequestInProgress::RequestInProgress(
    (StateRepository::WinRT::Client::RequestInProgress *)v27,
    0);
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        if ( a5 )
        {
          if ( a7 )
          {
            if ( a8 )
            {
              if ( a9 )
              {
                v33 = *((_QWORD *)this + 8);
                v31 = *((_DWORD *)this + 26);
                v32 = *((_DWORD *)this + 28);
                WindowsDeleteString(0);
                string = 0;
                TileId = Windows::Internal::StateRepository::PrimaryTileViewServer::get_TileId(this, &string);
                ApplicationUserModelId = TileId;
                if ( TileId >= 0 )
                {
                  v25 = 0;
                  WindowsDeleteString(0);
                  v25 = 0;
                  ApplicationUserModelId = Windows::Internal::StateRepository::SecondaryTileViewServer::get_ApplicationUserModelId(
                                             this,
                                             &v25);
                  if ( (ApplicationUserModelId & 0x80000000) != 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x30,
                      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.state"
                                    "repository.secondarytileview-custom.cpp",
                      (const char *)ApplicationUserModelId,
                      (int)string);
                    WindowsDeleteString(v25);
                    v25 = 0;
                    WindowsDeleteString(string);
                    v14 = v28 == 0;
                    string = 0;
                    goto LABEL_3;
                  }
                  v26 = 0;
                  v29 = 0;
                  v30 = 0;
                  Dictionary = Windows::Internal::StateRepository::SecondaryTileViewServer::Get_Dictionary(
                                 this,
                                 &v29,
                                 &v30);
                  ApplicationUserModelId = Dictionary;
                  if ( Dictionary >= 0 )
                  {
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
                    Dictionary = SRDictionaryToPropertySet(v29, v30, &v26);
                    ApplicationUserModelId = Dictionary;
                    if ( Dictionary >= 0 )
                    {
                      v34 = 0;
                      Dictionary = Windows::Internal::StateRepository::SecondaryTileViewServer::get_TileUniqueId(
                                     this,
                                     &v34);
                      ApplicationUserModelId = Dictionary;
                      if ( Dictionary >= 0 )
                      {
                        v30 = 0;
                        v19 = Windows::Internal::StateRepository::SecondaryTileViewServer::get_ChangeId(
                                this,
                                (__int64 *)&v30);
                        ApplicationUserModelId = v19;
                        if ( v19 >= 0 )
                        {
                          v20 = v34;
                          *a2 = v33;
                          *(_DWORD *)a3 = v31;
                          v21 = v25;
                          *(_DWORD *)a4 = v32;
                          *a5 = string;
                          string = 0;
                          v25 = 0;
                          *a6 = v21;
                          *a7 = v26;
                          v22 = v30;
                          *a8 = v20;
                          *a9 = (__int64)v22;
                          v26 = 0;
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
                          WindowsDeleteString(v25);
                          v25 = 0;
                          WindowsDeleteString(string);
                          ApplicationUserModelId = 0;
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x39,
                            (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal"
                                          ".staterepository.secondarytileview-custom.cpp",
                            (const char *)(unsigned int)v19,
                            (int)string);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
                          WindowsDeleteString(v25);
                          v25 = 0;
                          WindowsDeleteString(string);
                        }
                        string = 0;
                        goto LABEL_35;
                      }
                      v18 = 55;
                    }
                    else
                    {
                      v18 = 53;
                    }
                  }
                  else
                  {
                    v18 = 52;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v18,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.statere"
                                  "pository.secondarytileview-custom.cpp",
                    (const char *)(unsigned int)Dictionary,
                    (int)string);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
                  WindowsDeleteString(v25);
                  v25 = 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2E,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.statere"
                                  "pository.secondarytileview-custom.cpp",
                    (const char *)(unsigned int)TileId,
                    (int)string);
                }
                WindowsDeleteString(string);
                string = 0;
LABEL_35:
                StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress((StateRepository::WinRT::Client::RequestInProgress *)v27);
                return ApplicationUserModelId;
              }
              v15 = 37;
            }
            else
            {
              v15 = 36;
            }
          }
          else
          {
            v15 = 35;
          }
        }
        else
        {
          v15 = 34;
        }
      }
      else
      {
        v15 = 33;
      }
    }
    else
    {
      v15 = 32;
    }
    ApplicationUserModelId = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.secon"
                    "darytileview-custom.cpp",
      (const char *)0x80004003LL,
      (int)string);
    goto LABEL_35;
  }
  ApplicationUserModelId = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.seconda"
                  "rytileview-custom.cpp",
    (const char *)0x80004003LL,
    (int)string);
  v14 = v28 == 0;
LABEL_3:
  if ( !v14 )
    _InterlockedDecrement((volatile signed __int32 *)&StateRepository::WinRT::Client::RequestInProgress::s_countNonBlocking);
  _InterlockedDecrement(&StateRepository::WinRT::Client::RequestInProgress::s_count);
  return ApplicationUserModelId;
}

```

## disassembly

```asm
0x18003e4d0  mov     [rsp-38h+arg_0], rbx
0x18003e4d5  mov     [rsp-38h+arg_10], r8
0x18003e4da  mov     [rsp-38h+arg_8], rdx
0x18003e4df  push    rbp
0x18003e4e0  push    rsi
0x18003e4e1  push    rdi
0x18003e4e2  push    r12
0x18003e4e4  push    r13
0x18003e4e6  push    r14
0x18003e4e8  push    r15
0x18003e4ea  mov     rbp, rsp
0x18003e4ed  sub     rsp, 70h
0x18003e4f1  mov     rsi, rdx
0x18003e4f4  mov     rdi, rcx
0x18003e4f7  xor     edx, edx; bool
0x18003e4f9  lea     rcx, [rbp+var_38]; this
0x18003e4fd  mov     r13, r9
0x18003e500  mov     rbx, r8
0x18003e503  call    ??0RequestInProgress@Client@WinRT@StateRepository@@QEAA@_N@Z; StateRepository::WinRT::Client::RequestInProgress::RequestInProgress(bool)
0x18003e508  test    rsi, rsi
0x18003e50b  jnz     short loc_18003E541
0x18003e50d  mov     rcx, [rbp+38h]; this
0x18003e511  lea     r8, aOnecoreBaseApp_144; "onecore\\base\\appmodel\\staterepositor"...
0x18003e518  mov     ebx, 80004003h
0x18003e51d  lea     edx, [rsi+1Fh]; void *
0x18003e520  mov     r9d, ebx; char *
0x18003e523  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e528  cmp     [rbp+var_34], sil
0x18003e52c  jz      short loc_18003E535
0x18003e52e  lock dec cs:?s_countNonBlocking@RequestInProgress@Client@WinRT@StateRepository@@0JC; long volatile StateRepository::WinRT::Client::RequestInProgress::s_countNonBlocking
0x18003e535  lock dec cs:?s_count@RequestInProgress@Client@WinRT@StateRepository@@0JC; long volatile StateRepository::WinRT::Client::RequestInProgress::s_count
0x18003e53c  jmp     loc_18003E7FC
0x18003e541  test    rbx, rbx
0x18003e544  jnz     short loc_18003E54B
0x18003e546  lea     edx, [rbx+20h]
0x18003e549  jmp     short loc_18003E593
0x18003e54b  test    r13, r13
0x18003e54e  jnz     short loc_18003E556
0x18003e550  lea     edx, [r13+21h]
0x18003e554  jmp     short loc_18003E593
0x18003e556  mov     rsi, [rbp+arg_20]
0x18003e55a  test    rsi, rsi
0x18003e55d  jnz     short loc_18003E564
0x18003e55f  lea     edx, [rsi+22h]
0x18003e562  jmp     short loc_18003E593
0x18003e564  mov     r14, [rbp+arg_30]
0x18003e568  test    r14, r14
0x18003e56b  jnz     short loc_18003E573
0x18003e56d  lea     edx, [r14+23h]
0x18003e571  jmp     short loc_18003E593
0x18003e573  mov     r15, [rbp+arg_38]
0x18003e577  test    r15, r15
0x18003e57a  jnz     short loc_18003E582
0x18003e57c  lea     edx, [r15+24h]
0x18003e580  jmp     short loc_18003E593
0x18003e582  mov     r12, [rbp+arg_40]
0x18003e589  test    r12, r12
0x18003e58c  jnz     short loc_18003E5B0
0x18003e58e  lea     edx, [r12+25h]; void *
0x18003e593  mov     rcx, [rbp+38h]; this
0x18003e597  lea     r8, aOnecoreBaseApp_144; "onecore\\base\\appmodel\\staterepositor"...
0x18003e59e  mov     ebx, 80004003h
0x18003e5a3  mov     r9d, ebx; char *
0x18003e5a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e5ab  jmp     loc_18003E7F3
0x18003e5b0  mov     rax, [rdi+40h]
0x18003e5b4  xor     ecx, ecx; string
0x18003e5b6  mov     [rbp+var_18], rax
0x18003e5ba  mov     eax, [rdi+68h]
0x18003e5bd  mov     [rbp+var_20], eax
0x18003e5c0  mov     eax, [rdi+70h]
0x18003e5c3  mov     [rbp+var_1C], eax
0x18003e5c6  mov     [rbp+string], 0
0x18003e5ce  call    cs:__imp_WindowsDeleteString
0x18003e5d4  lea     rdx, [rbp+string]; HSTRING *
0x18003e5d8  mov     [rbp+string], 0
0x18003e5e0  mov     rcx, rdi; this
0x18003e5e3  call    ?get_TileId@PrimaryTileViewServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z; Windows::Internal::StateRepository::PrimaryTileViewServer::get_TileId(HSTRING__ * *)
0x18003e5e8  mov     ebx, eax
0x18003e5ea  test    eax, eax
0x18003e5ec  jns     short loc_18003E61D
0x18003e5ee  mov     rcx, [rbp+38h]; this
0x18003e5f2  lea     r8, aOnecoreBaseApp_144; "onecore\\base\\appmodel\\staterepositor"...
0x18003e5f9  mov     r9d, eax; char *
0x18003e5fc  mov     edx, 2Eh ; '.'; void *
0x18003e601  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e606  mov     rcx, [rbp+string]; string
0x18003e60a  call    cs:__imp_WindowsDeleteString
0x18003e610  mov     [rbp+string], 0
0x18003e618  jmp     loc_18003E7F3
0x18003e61d  xor     ecx, ecx; string
0x18003e61f  mov     [rbp+var_48], 0
0x18003e627  call    cs:__imp_WindowsDeleteString
0x18003e62d  lea     rdx, [rbp+var_48]; HSTRING *
0x18003e631  mov     [rbp+var_48], 0
0x18003e639  mov     rcx, rdi; this
0x18003e63c  call    ?get_ApplicationUserModelId@SecondaryTileViewServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z; Windows::Internal::StateRepository::SecondaryTileViewServer::get_ApplicationUserModelId(HSTRING__ * *)
0x18003e641  mov     ebx, eax
0x18003e643  xor     eax, eax
0x18003e645  test    ebx, ebx
0x18003e647  jns     short loc_18003E686
0x18003e649  mov     rcx, [rbp+38h]; this
0x18003e64d  lea     r8, aOnecoreBaseApp_144; "onecore\\base\\appmodel\\staterepositor"...
0x18003e654  mov     r9d, ebx; char *
0x18003e657  lea     edx, [rax+30h]; void *
0x18003e65a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e65f  mov     rcx, [rbp+var_48]; string
0x18003e663  call    cs:__imp_WindowsDeleteString
0x18003e669  mov     rcx, [rbp+string]; string
0x18003e66d  xor     edi, edi
0x18003e66f  mov     [rbp+var_48], rdi
0x18003e673  call    cs:__imp_WindowsDeleteString
0x18003e679  cmp     [rbp+var_34], dil
0x18003e67d  mov     [rbp+string], rdi
0x18003e681  jmp     loc_18003E52C
0x18003e686  lea     r8, [rbp+var_28]; unsigned __int8 **
0x18003e68a  mov     [rbp+var_40], rax
0x18003e68e  lea     rdx, [rbp+var_30]; unsigned int *
0x18003e692  mov     [rbp+var_30], eax
0x18003e695  mov     rcx, rdi; this
0x18003e698  mov     [rbp+var_28], rax
0x18003e69c  call    ?Get_Dictionary@SecondaryTileViewServer@StateRepository@Internal@Windows@@UEAAJPEAIPEAPEAE@Z; Windows::Internal::StateRepository::SecondaryTileViewServer::Get_Dictionary(uint *,uchar * *)
0x18003e6a1  mov     ebx, eax
0x18003e6a3  test    eax, eax
0x18003e6a5  jns     short loc_18003E6DF
0x18003e6a7  mov     edx, 34h ; '4'; void *
0x18003e6ac  mov     rcx, [rbp+38h]; this
0x18003e6b0  lea     r8, aOnecoreBaseApp_144; "onecore\\base\\appmodel\\staterepositor"...
0x18003e6b7  mov     r9d, eax; char *
0x18003e6ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e6bf  lea     rcx, [rbp+var_40]
0x18003e6c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e6c8  mov     rcx, [rbp+var_48]; string
0x18003e6cc  call    cs:__imp_WindowsDeleteString
0x18003e6d2  mov     [rbp+var_48], 0
0x18003e6da  jmp     loc_18003E606
0x18003e6df  lea     rcx, [rbp+var_40]
0x18003e6e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e6e8  mov     rdx, [rbp+var_28]
0x18003e6ec  lea     r8, [rbp+var_40]
0x18003e6f0  mov     ecx, [rbp+var_30]
0x18003e6f3  call    cs:__imp_SRDictionaryToPropertySet
0x18003e6f9  mov     ebx, eax
0x18003e6fb  test    eax, eax
0x18003e6fd  jns     short loc_18003E706
0x18003e6ff  mov     edx, 35h ; '5'
0x18003e704  jmp     short loc_18003E6AC
0x18003e706  xorps   xmm0, xmm0
0x18003e709  lea     rdx, [rbp+var_10]; struct _GUID *
0x18003e70d  mov     rcx, rdi; this
0x18003e710  movups  xmmword ptr [rbp+var_10.Data1], xmm0
0x18003e714  call    ?get_TileUniqueId@SecondaryTileViewServer@StateRepository@Internal@Windows@@UEAAJPEAU_GUID@@@Z; Windows::Internal::StateRepository::SecondaryTileViewServer::get_TileUniqueId(_GUID *)
0x18003e719  mov     ebx, eax
0x18003e71b  test    eax, eax
0x18003e71d  jns     short loc_18003E726
0x18003e71f  mov     edx, 37h ; '7'
0x18003e724  jmp     short loc_18003E6AC
0x18003e726  lea     rdx, [rbp+var_28]; __int64 *
0x18003e72a  mov     [rbp+var_28], 0
0x18003e732  mov     rcx, rdi; this
0x18003e735  call    ?get_ChangeId@SecondaryTileViewServer@StateRepository@Internal@Windows@@UEAAJPEA_J@Z; Windows::Internal::StateRepository::SecondaryTileViewServer::get_ChangeId(__int64 *)
0x18003e73a  xor     edi, edi
0x18003e73c  mov     ebx, eax
0x18003e73e  test    eax, eax
0x18003e740  jns     short loc_18003E77B
0x18003e742  mov     rcx, [rbp+38h]; this
0x18003e746  lea     r8, aOnecoreBaseApp_144; "onecore\\base\\appmodel\\staterepositor"...
0x18003e74d  mov     r9d, eax; char *
0x18003e750  lea     edx, [rdi+39h]; void *
0x18003e753  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e758  lea     rcx, [rbp+var_40]
0x18003e75c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e761  mov     rcx, [rbp+var_48]; string
0x18003e765  call    cs:__imp_WindowsDeleteString
0x18003e76b  mov     rcx, [rbp+string]; string
0x18003e76f  mov     [rbp+var_48], rdi
0x18003e773  call    cs:__imp_WindowsDeleteString
0x18003e779  jmp     short loc_18003E7EF
0x18003e77b  mov     rcx, [rbp+var_18]
0x18003e77f  mov     rax, [rbp+arg_8]
0x18003e783  movups  xmm0, xmmword ptr [rbp+var_10.Data1]
0x18003e787  mov     [rax], rcx
0x18003e78a  mov     rax, [rbp+arg_10]
0x18003e78e  mov     ecx, [rbp+var_20]
0x18003e791  mov     [rax], ecx
0x18003e793  mov     rcx, [rbp+var_48]
0x18003e797  mov     eax, [rbp+var_1C]
0x18003e79a  mov     [r13+0], eax
0x18003e79e  mov     rax, [rbp+string]
0x18003e7a2  mov     [rsi], rax
0x18003e7a5  mov     rax, [rbp+arg_28]
0x18003e7a9  mov     [rbp+string], rdi
0x18003e7ad  mov     [rbp+var_48], rdi
0x18003e7b1  mov     [rax], rcx
0x18003e7b4  lea     rcx, [rbp+var_40]
0x18003e7b8  mov     rax, [rbp+var_40]
0x18003e7bc  mov     [r14], rax
0x18003e7bf  mov     rax, [rbp+var_28]
0x18003e7c3  movdqu  xmmword ptr [r15], xmm0
0x18003e7c8  mov     [r12], rax
0x18003e7cc  mov     [rbp+var_40], rdi
0x18003e7d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e7d5  mov     rcx, [rbp+var_48]; string
0x18003e7d9  call    cs:__imp_WindowsDeleteString
0x18003e7df  mov     rcx, [rbp+string]; string
0x18003e7e3  mov     [rbp+var_48], rdi
0x18003e7e7  call    cs:__imp_WindowsDeleteString
0x18003e7ed  mov     ebx, edi
0x18003e7ef  mov     [rbp+string], rdi
0x18003e7f3  lea     rcx, [rbp+var_38]; this
0x18003e7f7  call    ??1RequestInProgress@Client@WinRT@StateRepository@@QEAA@XZ; StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress(void)
0x18003e7fc  mov     eax, ebx
0x18003e7fe  mov     rbx, [rsp+70h+arg_0]
0x18003e806  add     rsp, 70h
0x18003e80a  pop     r15
0x18003e80c  pop     r14
0x18003e80e  pop     r13
0x18003e810  pop     r12
0x18003e812  pop     rdi
0x18003e813  pop     rsi
0x18003e814  pop     rbp
0x18003e815  retn
```
