# Windows::Internal::StateRepository::ApplicationFactoryServer::TryGetActivationInfoByUserAndApplicationUserModelId(Windows::Internal::StateRepository::IUser *,HSTRING__ *,Windows::Internal::StateRepository::ActivationInfoFlags *,HSTRING__ * *,HSTRING__ * *,uchar *)

- ea: `0x180116ff0`
- end: `0x18011741f`
- name: `?TryGetActivationInfoByUserAndApplicationUserModelId@ApplicationFactoryServer@StateRepository@Internal@Windows@@UEAAJPEAUIUser@234@PEAUHSTRING__@@PEAW4ActivationInfoFlags@234@PEAPEAU6@3PEAE@Z`
- size: `1071`
- prototype: `int(Windows::Internal::StateRepository::ApplicationFactoryServer *__hidden this, struct Windows::Internal::StateRepository::IUser *, HSTRING, enum Windows::Internal::StateRepository::ActivationInfoFlags *, HSTRING *, HSTRING *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x18000a834`
- `0x18000ad44`
- `0x18000b380`
- `0x18000b3a0`
- `0x18000c73c`
- `0x18000ca84`
- `0x18000d170`
- `0x18000dc60`
- `0x180016030`
- `0x1800171c0`
- `0x180018574`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180116ff0`
- `0x18018f650`
- `0x1801fd8b8`
- `0x180256878`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117169`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117179`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117293`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801172a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011731a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011732a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801173c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801173d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117169`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117179`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117293`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801172a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011731a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011732a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801173c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801173d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801171f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801171f7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationFactoryServer::TryGetActivationInfoByUserAndApplicationUserModelId(
        Windows::Internal::StateRepository::ApplicationFactoryServer *this,
        struct Windows::Internal::StateRepository::IUser *a2,
        HSTRING a3,
        enum Windows::Internal::StateRepository::ActivationInfoFlags *a4,
        HSTRING *a5,
        HSTRING *a6,
        unsigned __int8 *a7)
{
  unsigned int v9; // ebx
  BlockRequests *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  unsigned int v13; // esi
  unsigned __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // edi
  int UserIdFromUser; // eax
  bool v18; // di
  const unsigned __int16 *StringRawBuffer; // rax
  int ActivationInfoByUserAndApplicationUserModelId; // eax
  struct Microsoft::WRL::Wrappers::HString *v21; // r8
  unsigned int v22; // edi
  int v23; // esi
  struct Microsoft::WRL::Wrappers::HString *v24; // r8
  __int64 v25; // rdx
  HSTRING v26; // rax
  _BYTE *v27; // rcx
  char *v28; // rdx
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  bool v32; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v34; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v35; // [rsp+58h] [rbp-A8h] BYREF
  struct sqlite3 **v36; // [rsp+60h] [rbp-A0h] BYREF
  struct Windows::Internal::StateRepository::IUser *v37[2]; // [rsp+68h] [rbp-98h] BYREF
  int v38[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h]
  __int64 v40; // [rsp+88h] [rbp-78h] BYREF
  char *v41; // [rsp+90h] [rbp-70h]
  unsigned int v42[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 *v43; // [rsp+A0h] [rbp-60h]
  struct sqlite3 *v44[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v45[336]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v37[0] = a2;
  v43 = a7;
  StateRepository::WinRT::Client::RequestInProgress::RequestInProgress(
    (StateRepository::WinRT::Client::RequestInProgress *)v42,
    0);
  v9 = v42[0];
  v41 = "ApplicationStatics::TryGetActivationInfoByUserAndApplicationUserModelId";
  v35 = v42[0];
  StateRepository::Trace::WinRT::API::Method::Start<char const * &,unsigned int>((StateRepository::Trace::WinRT::API::Method *)v45);
  if ( BlockRequests::IsCurrentThreadUnblocked(v10) )
    goto LABEL_9;
  v36 = *(struct sqlite3 ***)&qword_1804E01A0;
  if ( (*(_BYTE *)(&qword_1804E01A0 + 1) & 2) == 0 )
  {
    if ( (BYTE4(v36) & 1) != 0 )
    {
      v11 = -2140733424;
      goto LABEL_8;
    }
    if ( (_DWORD)v36 )
    {
      v11 = -2140733434;
      goto LABEL_8;
    }
LABEL_9:
    if ( !a3 )
    {
      v12 = 1403;
LABEL_11:
      v11 = -2147467261;
      goto LABEL_12;
    }
    if ( !a4 )
    {
      v12 = 1404;
      goto LABEL_11;
    }
    if ( !a5 )
    {
      v12 = 1405;
      goto LABEL_11;
    }
    if ( !a6 )
    {
      v12 = 1406;
      goto LABEL_11;
    }
    if ( !a7 )
    {
      v12 = 1407;
      goto LABEL_11;
    }
    v13 = 0;
    v35 = 0;
    v34 = 0;
    string = 0;
    StateRepository::Database::Database((StateRepository::Database *)v44);
    v15 = StateRepository::Repository::OpenDatabaseFromCache(1, v14, (__int64)v44);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x588,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.app"
                      "licationfactory-custom.cpp",
        (const char *)(unsigned int)v15,
        v30);
LABEL_23:
      StateRepository::Database::~Database((StateRepository::Database *)v44);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v34);
      v34 = 0;
      v11 = v16;
      goto LABEL_38;
    }
    v36 = v44;
    v40 = 0;
    v32 = 0;
    UserIdFromUser = StateRepository::WinRT::DataAccessLayer::User::TryGet_UserIdFromUser(v37[0], v44, &v40, &v32);
    v16 = UserIdFromUser;
    if ( UserIdFromUser < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58D,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.app"
                      "licationfactory-custom.cpp",
        (const char *)(unsigned int)UserIdFromUser,
        v30);
      StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v36);
      goto LABEL_23;
    }
    v18 = v32;
    if ( v32 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
      *(_QWORD *)v38 = 0;
      v39 = 0;
      v37[0] = 0;
      v37[1] = 0;
      ActivationInfoByUserAndApplicationUserModelId = StateRepository::Entity::Application::TryGetActivationInfoByUserAndApplicationUserModelId(
                                                        (struct StateRepository::Database *)v44,
                                                        v40,
                                                        StringRawBuffer,
                                                        (enum StateRepository::ActivationInfoFlags *)&v35,
                                                        (struct StateRepository::Text *)v38,
                                                        (struct StateRepository::Text *)v37,
                                                        &v32);
      v22 = ActivationInfoByUserAndApplicationUserModelId;
      if ( ActivationInfoByUserAndApplicationUserModelId < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x595,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.a"
                        "pplicationfactory-custom.cpp",
          (const char *)(unsigned int)ActivationInfoByUserAndApplicationUserModelId,
          v31);
        StateRepository::TextA::Reset((StateRepository::TextA *)v37);
        StateRepository::TextA::Reset((StateRepository::TextA *)v38);
        StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v36);
        StateRepository::Database::~Database((StateRepository::Database *)v44);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v34);
        v11 = v22;
LABEL_37:
        v34 = 0;
        goto LABEL_38;
      }
      v18 = v32;
      if ( v32 )
      {
        v23 = StateRepository::WinRT::Foundation::ToHString(
                (StateRepository::WinRT::Foundation *)v38,
                (const struct StateRepository::Text *)&v34,
                v21);
        if ( v23 < 0 )
        {
          v25 = 1432;
LABEL_32:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v25,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository"
                          ".applicationfactory-custom.cpp",
            (const char *)(unsigned int)v23,
            v31);
          StateRepository::TextA::Reset((StateRepository::TextA *)v37);
          StateRepository::TextA::Reset((StateRepository::TextA *)v38);
          StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v36);
          StateRepository::Database::~Database((StateRepository::Database *)v44);
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v34);
          v11 = v23;
          goto LABEL_37;
        }
        v23 = StateRepository::WinRT::Foundation::ToHString(
                (StateRepository::WinRT::Foundation *)v37,
                (const struct StateRepository::Text *)&string,
                v24);
        if ( v23 < 0 )
        {
          v25 = 1433;
          goto LABEL_32;
        }
      }
      StateRepository::TextA::Reset((StateRepository::TextA *)v37);
      StateRepository::TextA::Reset((StateRepository::TextA *)v38);
      v13 = v35;
    }
    v26 = v34;
    v27 = v43;
    v28 = v41;
    *(_DWORD *)a4 = v13;
    *a5 = v26;
    *a6 = string;
    *v27 = v18;
    v34 = 0;
    string = 0;
    StateRepository::Trace::WinRT::API::Method::Stop((StateRepository::Trace::WinRT::API::Method *)v45, v28, v9);
    StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v36);
    StateRepository::Database::~Database((StateRepository::Database *)v44);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v34);
    v11 = 0;
    goto LABEL_37;
  }
  v11 = -2147023781;
LABEL_8:
  v12 = 1401;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.applica"
                  "tionfactory-custom.cpp",
    (const char *)v11,
    v30);
LABEL_38:
  StateRepository::Trace::WinRT::API::Method::~Method((StateRepository::Trace::WinRT::API::Method *)v45);
  StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress((StateRepository::WinRT::Client::RequestInProgress *)v42);
  return v11;
}

```

## disassembly

```asm
0x180116ff0  mov     [rsp-8+arg_0], rbx
0x180116ff5  push    rbp
0x180116ff6  push    rsi
0x180116ff7  push    rdi
0x180116ff8  push    r12
0x180116ffa  push    r13
0x180116ffc  push    r14
0x180116ffe  push    r15
0x180117000  lea     rbp, [rsp-190h]
0x180117008  sub     rsp, 290h
0x18011700f  mov     rax, cs:__security_cookie
0x180117016  xor     rax, rsp
0x180117019  mov     [rbp+1C0h+var_40], rax
0x180117020  mov     rdi, [rbp+1C0h+arg_30]
0x180117027  lea     rcx, [rbp+1C0h+var_228]; this
0x18011702b  mov     r12, [rbp+1C0h+arg_20]
0x180117032  mov     r15, r9
0x180117035  mov     r13, [rbp+1C0h+arg_28]
0x18011703c  mov     r14, r8
0x18011703f  mov     [rsp+2C0h+var_258], rdx
0x180117044  xor     edx, edx; bool
0x180117046  mov     [rbp+1C0h+var_220], rdi
0x18011704a  call    ??0RequestInProgress@Client@WinRT@StateRepository@@QEAA@_N@Z; StateRepository::WinRT::Client::RequestInProgress::RequestInProgress(bool)
0x18011704f  mov     rbx, qword ptr [rbp+1C0h+var_228]
0x180117053  lea     rax, aApplicationsta_3; "ApplicationStatics::TryGetActivationInf"...
0x18011705a  lea     r8, [rsp+2C0h+var_268]
0x18011705f  mov     [rbp+1C0h+var_230], rax
0x180117063  lea     rdx, [rbp+1C0h+var_230]
0x180117067  mov     [rsp+2C0h+var_268], ebx
0x18011706b  lea     rcx, [rbp+1C0h+var_190]; this
0x18011706f  call    ??$Start@AEAPEBDI@Method@API@WinRT@Trace@StateRepository@@SA?AV01234@AEAPEBD$$QEAI@Z; StateRepository::Trace::WinRT::API::Method::Start<char const * &,uint>(char const * &,uint &&)
0x180117074  call    ?IsCurrentThreadUnblocked@BlockRequests@@QEAA_NXZ; BlockRequests::IsCurrentThreadUnblocked(void)
0x180117079  test    al, al
0x18011707b  jnz     short loc_1801170BB
0x18011707d  mov     rax, cs:qword_1804E01A0
0x180117084  mov     [rsp+2C0h+var_260], rax
0x180117089  mov     eax, dword ptr [rsp+2C0h+var_260+4]
0x18011708d  test    al, 2
0x18011708f  jz      short loc_180117098
0x180117091  mov     ebx, 8007045Bh
0x180117096  jmp     short loc_1801170B4
0x180117098  mov     eax, dword ptr [rsp+2C0h+var_260+4]
0x18011709c  test    al, 1
0x18011709e  jz      short loc_1801170A7
0x1801170a0  mov     ebx, 80670010h
0x1801170a5  jmp     short loc_1801170B4
0x1801170a7  mov     eax, dword ptr [rsp+2C0h+var_260]
0x1801170ab  test    eax, eax
0x1801170ad  jz      short loc_1801170BB
0x1801170af  mov     ebx, 80670006h
0x1801170b4  mov     edx, 579h
0x1801170b9  jmp     short loc_1801170CA
0x1801170bb  test    r14, r14
0x1801170be  jnz     short loc_1801170E5
0x1801170c0  mov     edx, 57Bh; void *
0x1801170c5  mov     ebx, 80004003h
0x1801170ca  mov     rcx, [rbp+1C8h]; this
0x1801170d1  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x1801170d8  mov     r9d, ebx; char *
0x1801170db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801170e0  jmp     loc_1801173E1
0x1801170e5  test    r15, r15
0x1801170e8  jnz     short loc_1801170F1
0x1801170ea  mov     edx, 57Ch
0x1801170ef  jmp     short loc_1801170C5
0x1801170f1  test    r12, r12
0x1801170f4  jnz     short loc_1801170FD
0x1801170f6  mov     edx, 57Dh
0x1801170fb  jmp     short loc_1801170C5
0x1801170fd  test    r13, r13
0x180117100  jnz     short loc_180117109
0x180117102  mov     edx, 57Eh
0x180117107  jmp     short loc_1801170C5
0x180117109  test    rdi, rdi
0x18011710c  jnz     short loc_180117115
0x18011710e  mov     edx, 57Fh
0x180117113  jmp     short loc_1801170C5
0x180117115  xor     esi, esi
0x180117117  lea     rcx, [rbp+1C0h+var_210]; this
0x18011711b  mov     [rsp+2C0h+var_268], esi
0x18011711f  mov     [rsp+2C0h+var_270], rsi
0x180117124  mov     [rsp+2C0h+string], rsi
0x180117129  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x18011712e  lea     r8, [rbp+1C0h+var_210]
0x180117132  lea     ecx, [rsi+1]
0x180117135  call    ?OpenDatabaseFromCache@Repository@StateRepository@@SAJW4Partition@2@W4OpenFlags@12@AEAVDatabase@2@@Z; StateRepository::Repository::OpenDatabaseFromCache(StateRepository::Partition,StateRepository::Repository::OpenFlags,StateRepository::Database &)
0x18011713a  mov     edi, eax
0x18011713c  test    eax, eax
0x18011713e  jns     short loc_18011718B
0x180117140  mov     rcx, [rbp+1C8h]; this
0x180117147  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x18011714e  mov     r9d, eax; char *
0x180117151  mov     edx, 588h; void *
0x180117156  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011715b  lea     rcx, [rbp+1C0h+var_210]; this
0x18011715f  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x180117164  mov     rcx, [rsp+2C0h+string]; string
0x180117169  call    cs:__imp_WindowsDeleteString
0x18011716f  mov     rcx, [rsp+2C0h+var_270]; string
0x180117174  mov     [rsp+2C0h+string], rsi
0x180117179  call    cs:__imp_WindowsDeleteString
0x18011717f  mov     [rsp+2C0h+var_270], rsi
0x180117184  mov     ebx, edi
0x180117186  jmp     loc_1801173E1
0x18011718b  mov     rcx, [rsp+2C0h+var_258]; struct Windows::Internal::StateRepository::IUser *
0x180117190  lea     rax, [rbp+1C0h+var_210]
0x180117194  lea     r9, [rsp+2C0h+var_280]; bool *
0x180117199  mov     [rsp+2C0h+var_260], rax
0x18011719e  lea     r8, [rbp+1C0h+var_238]; __int64 *
0x1801171a2  mov     [rbp+1C0h+var_238], rsi
0x1801171a6  lea     rdx, [rbp+1C0h+var_210]; struct StateRepository::Database *
0x1801171aa  mov     [rsp+2C0h+var_280], sil
0x1801171af  call    ?TryGet_UserIdFromUser@User@DataAccessLayer@WinRT@StateRepository@@SAJPEAUIUser@4Internal@Windows@@AEAVDatabase@4@PEA_JPEA_N@Z; StateRepository::WinRT::DataAccessLayer::User::TryGet_UserIdFromUser(Windows::Internal::StateRepository::IUser *,StateRepository::Database &,__int64 *,bool *)
0x1801171b4  mov     edi, eax
0x1801171b6  test    eax, eax
0x1801171b8  jns     short loc_1801171E4
0x1801171ba  mov     rcx, [rbp+1C8h]; this
0x1801171c1  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x1801171c8  mov     r9d, eax; char *
0x1801171cb  mov     edx, 58Dh; void *
0x1801171d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801171d5  lea     rcx, [rsp+2C0h+var_260]; this
0x1801171da  call    ??1AutoAddDatabaseToCache@StateRepository@@QEAA@XZ; StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache(void)
0x1801171df  jmp     loc_18011715B
0x1801171e4  mov     dil, [rsp+2C0h+var_280]
0x1801171e9  test    dil, dil
0x1801171ec  jz      loc_18011736D
0x1801171f2  xor     edx, edx; length
0x1801171f4  mov     rcx, r14; string
0x1801171f7  call    cs:__imp_WindowsGetStringRawBuffer
0x1801171fd  mov     rdx, [rbp+1C0h+var_238]; __int64
0x180117201  lea     rcx, [rsp+2C0h+var_280]
0x180117206  mov     [rsp+2C0h+var_290], rcx; bool *
0x18011720b  lea     r9, [rsp+2C0h+var_268]; enum StateRepository::ActivationInfoFlags *
0x180117210  xor     r14d, r14d
0x180117213  lea     rcx, [rsp+2C0h+var_258]
0x180117218  mov     [rsp+2C0h+var_298], rcx; struct StateRepository::Text *
0x18011721d  mov     r8, rax; unsigned __int16 *
0x180117220  lea     rcx, [rsp+2C0h+var_248]
0x180117225  mov     qword ptr [rsp+2C0h+var_248], r14
0x18011722a  mov     [rsp+2C0h+var_2A0], rcx; int
0x18011722f  lea     rcx, [rbp+1C0h+var_210]; this
0x180117233  mov     [rbp+1C0h+var_240], r14
0x180117237  mov     [rsp+2C0h+var_258], r14
0x18011723c  mov     [rsp+2C0h+var_250], r14
0x180117241  call    ?TryGetActivationInfoByUserAndApplicationUserModelId@Application@Entity@StateRepository@@SAJAEAVDatabase@3@_JPEBGPEAW4ActivationInfoFlags@3@AEAVText@3@4AEA_N@Z; StateRepository::Entity::Application::TryGetActivationInfoByUserAndApplicationUserModelId(StateRepository::Database &,__int64,ushort const *,StateRepository::ActivationInfoFlags *,StateRepository::Text &,StateRepository::Text &,bool &)
0x180117246  mov     edi, eax
0x180117248  test    eax, eax
0x18011724a  jns     short loc_1801172B0
0x18011724c  mov     rcx, [rbp+1C8h]; this
0x180117253  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x18011725a  mov     r9d, eax; char *
0x18011725d  mov     edx, 595h; void *
0x180117262  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117267  lea     rcx, [rsp+2C0h+var_258]; this
0x18011726c  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180117271  lea     rcx, [rsp+2C0h+var_248]; this
0x180117276  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18011727b  lea     rcx, [rsp+2C0h+var_260]; this
0x180117280  call    ??1AutoAddDatabaseToCache@StateRepository@@QEAA@XZ; StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache(void)
0x180117285  lea     rcx, [rbp+1C0h+var_210]; this
0x180117289  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x18011728e  mov     rcx, [rsp+2C0h+string]; string
0x180117293  call    cs:__imp_WindowsDeleteString
0x180117299  mov     rcx, [rsp+2C0h+var_270]; string
0x18011729e  mov     [rsp+2C0h+string], r14
0x1801172a3  call    cs:__imp_WindowsDeleteString
0x1801172a9  mov     ebx, edi
0x1801172ab  jmp     loc_1801173DC
0x1801172b0  mov     dil, [rsp+2C0h+var_280]
0x1801172b5  test    dil, dil
0x1801172b8  jz      loc_180117353
0x1801172be  lea     rdx, [rsp+2C0h+var_270]; struct StateRepository::Text *
0x1801172c3  lea     rcx, [rsp+2C0h+var_248]; this
0x1801172c8  call    ?ToHString@Foundation@WinRT@StateRepository@@YAJAEBVText@3@AEAVHString@Wrappers@WRL@Microsoft@@@Z; StateRepository::WinRT::Foundation::ToHString(StateRepository::Text const &,Microsoft::WRL::Wrappers::HString &)
0x1801172cd  mov     esi, eax
0x1801172cf  test    eax, eax
0x1801172d1  jns     short loc_180117337
0x1801172d3  mov     edx, 598h; void *
0x1801172d8  mov     rcx, [rbp+1C8h]; this
0x1801172df  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x1801172e6  mov     r9d, esi; char *
0x1801172e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801172ee  lea     rcx, [rsp+2C0h+var_258]; this
0x1801172f3  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1801172f8  lea     rcx, [rsp+2C0h+var_248]; this
0x1801172fd  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180117302  lea     rcx, [rsp+2C0h+var_260]; this
0x180117307  call    ??1AutoAddDatabaseToCache@StateRepository@@QEAA@XZ; StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache(void)
0x18011730c  lea     rcx, [rbp+1C0h+var_210]; this
0x180117310  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x180117315  mov     rcx, [rsp+2C0h+string]; string
0x18011731a  call    cs:__imp_WindowsDeleteString
0x180117320  mov     rcx, [rsp+2C0h+var_270]; string
0x180117325  mov     [rsp+2C0h+string], r14
0x18011732a  call    cs:__imp_WindowsDeleteString
0x180117330  mov     ebx, esi
0x180117332  jmp     loc_1801173DC
0x180117337  lea     rdx, [rsp+2C0h+string]; struct StateRepository::Text *
0x18011733c  lea     rcx, [rsp+2C0h+var_258]; this
0x180117341  call    ?ToHString@Foundation@WinRT@StateRepository@@YAJAEBVText@3@AEAVHString@Wrappers@WRL@Microsoft@@@Z; StateRepository::WinRT::Foundation::ToHString(StateRepository::Text const &,Microsoft::WRL::Wrappers::HString &)
0x180117346  mov     esi, eax
0x180117348  test    eax, eax
0x18011734a  jns     short loc_180117353
0x18011734c  mov     edx, 599h
0x180117351  jmp     short loc_1801172D8
0x180117353  lea     rcx, [rsp+2C0h+var_258]; this
0x180117358  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18011735d  lea     rcx, [rsp+2C0h+var_248]; this
0x180117362  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180117367  mov     esi, [rsp+2C0h+var_268]
0x18011736b  jmp     short loc_180117370
0x18011736d  xor     r14d, r14d
0x180117370  mov     rax, [rsp+2C0h+var_270]
0x180117375  test    dil, dil
0x180117378  mov     rcx, [rbp+1C0h+var_220]
0x18011737c  mov     r8d, ebx; unsigned int
0x18011737f  mov     rdx, [rbp+1C0h+var_230]; char *
0x180117383  mov     [r15], esi
0x180117386  mov     [r12], rax
0x18011738a  mov     rax, [rsp+2C0h+string]
0x18011738f  mov     [r13+0], rax
0x180117393  setnz   al
0x180117396  mov     [rcx], al
0x180117398  lea     rcx, [rbp+1C0h+var_190]; this
0x18011739c  mov     [rsp+2C0h+var_270], r14
0x1801173a1  mov     [rsp+2C0h+string], r14
0x1801173a6  call    ?Stop@Method@API@WinRT@Trace@StateRepository@@QEAAXPEBDI@Z; StateRepository::Trace::WinRT::API::Method::Stop(char const *,uint)
0x1801173ab  lea     rcx, [rsp+2C0h+var_260]; this
0x1801173b0  call    ??1AutoAddDatabaseToCache@StateRepository@@QEAA@XZ; StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache(void)
0x1801173b5  lea     rcx, [rbp+1C0h+var_210]; this
0x1801173b9  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x1801173be  mov     rcx, [rsp+2C0h+string]; string
0x1801173c3  call    cs:__imp_WindowsDeleteString
0x1801173c9  mov     rcx, [rsp+2C0h+var_270]; string
0x1801173ce  mov     [rsp+2C0h+string], r14
0x1801173d3  call    cs:__imp_WindowsDeleteString
0x1801173d9  mov     ebx, r14d
0x1801173dc  mov     [rsp+2C0h+var_270], r14
0x1801173e1  lea     rcx, [rbp+1C0h+var_190]; this
0x1801173e5  call    ??1Method@API@WinRT@Trace@StateRepository@@QEAA@XZ; StateRepository::Trace::WinRT::API::Method::~Method(void)
0x1801173ea  lea     rcx, [rbp+1C0h+var_228]; this
0x1801173ee  call    ??1RequestInProgress@Client@WinRT@StateRepository@@QEAA@XZ; StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress(void)
0x1801173f3  mov     eax, ebx
0x1801173f5  mov     rcx, [rbp+1C0h+var_40]
0x1801173fc  xor     rcx, rsp; StackCookie
0x1801173ff  call    __security_check_cookie
0x180117404  mov     rbx, [rsp+2C0h+arg_0]
0x18011740c  add     rsp, 290h
0x180117413  pop     r15
0x180117415  pop     r14
0x180117417  pop     r13
0x180117419  pop     r12
0x18011741b  pop     rdi
0x18011741c  pop     rsi
0x18011741d  pop     rbp
0x18011741e  retn
```
