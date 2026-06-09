# _lambda_1e4e71d5fefea8a9649a8ab9d35d1697_::operator()

- ea: `0x1800318bc`
- end: `0x180031c0e`
- name: `_lambda_1e4e71d5fefea8a9649a8ab9d35d1697_::operator()`
- size: `850`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `23`
- tags: ``

## callers

- `0x180034734`

## callees

- `0x180003c70`
- `0x18000cb9c`
- `0x1800113bc`
- `0x180011bd0`
- `0x180011c0c`
- `0x1800125ec`
- `0x180012f7c`
- `0x18001c090`
- `0x180020e68`
- `0x180022dec`
- `0x1800270e8`
- `0x18002cf5c`
- `0x180030a00`
- `0x180030e3c`
- `0x180030ea4`
- `0x180031338`
- `0x180031444`
- `0x18003175c`
- `0x1800318bc`
- `0x1800323b4`
- `0x180032f28`
- `0x180036508`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031b87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031b87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031b72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031bad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031bbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031bcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031bdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031b72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031bad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031bbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031bcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031bdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180031a0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180031a0a`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180031a30`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180031a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
HRESULT __fastcall lambda_1e4e71d5fefea8a9649a8ab9d35d1697_::operator()(_QWORD *a1, HSTRING *a2)
{
  __int64 *v4; // rax
  __int64 v5; // rdi
  __int64 i; // rbx
  __int64 v7; // rsi
  void (__fastcall *v8)(__int64, HSTRING *, HSTRING *, HSTRING *, _BYTE *, __int64 *); // rdi
  HSTRING *AddressOf; // rbx
  HSTRING *v10; // rax
  const WCHAR *StringRawBuffer; // rax
  LONG v12; // eax
  bool v13; // sf
  char *v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rdi
  _BYTE v18[8]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v19; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v20; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v21; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING newString; // [rsp+60h] [rbp-A0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+78h] [rbp-88h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h] BYREF
  __int64 v27; // [rsp+88h] [rbp-78h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v29[48]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v30[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v31[40]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v32[96]; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v33[6]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v34[96]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+1F0h] [rbp+F0h] BYREF
  WCHAR packageRelativeApplicationId[72]; // [rsp+280h] [rbp+180h] BYREF

  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, *a2);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v19, a2[1]);
  v4 = (__int64 *)a1[1];
  v5 = v4[1];
  for ( i = *v4; i != v5 && !(unsigned __int8)ConnectedStorage::SimpleHStringWrapper::operator==(i, &newString); i += 8 )
    ;
  if ( i != *(_QWORD *)(a1[1] + 8LL)
    && !(*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)(*a1 + 168LL) + 24LL))(
          *(_QWORD *)(*a1 + 168LL),
          &newString) )
  {
    v21 = 0;
    v20 = 0;
    v18[0] = 0;
    v27 = 0;
    v7 = *(_QWORD *)(*a1 + 168LL);
    v8 = *(void (__fastcall **)(__int64, HSTRING *, HSTRING *, HSTRING *, _BYTE *, __int64 *))(*(_QWORD *)v7 + 16LL);
    AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v20);
    v10 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v21);
    v8(v7, &newString, v10, AddressOf, v18, &v27);
    if ( !ConnectedStorage::SimpleHStringWrapper::IsEmpty((ConnectedStorage::SimpleHStringWrapper *)&v21)
      && !ConnectedStorage::SimpleHStringWrapper::IsEmpty((ConnectedStorage::SimpleHStringWrapper *)&v20) )
    {
      packageFamilyNameLength = 65;
      packageRelativeApplicationIdLength = 66;
      StringRawBuffer = WindowsGetStringRawBuffer(a2[3], 0);
      v12 = ParseApplicationUserModelId(
              StringRawBuffer,
              &packageFamilyNameLength,
              packageFamilyName,
              &packageRelativeApplicationIdLength,
              packageRelativeApplicationId);
      v13 = v12 < 0;
      if ( v12 > 0 )
        v13 = 1;
      if ( !v13 )
      {
        ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, packageFamilyName);
        ConnectedStorage::ContextDesc::ContextDesc(
          (ConnectedStorage::ContextDesc *)v29,
          (const struct ConnectedStorage::SimpleHStringWrapper *)&v21,
          (const struct ConnectedStorage::SimpleHStringWrapper *)&v20,
          (const struct ConnectedStorage::SimpleHStringWrapper *)&newString,
          (const struct ConnectedStorage::SimpleHStringWrapper *)&v19,
          (const struct ConnectedStorage::SimpleHStringWrapper *)&string,
          0,
          0);
        ConnectedStorage::Mutex::Lock::Lock(
          (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
          (struct _RTL_CRITICAL_SECTION *)(*a1 + 176LL),
          v14);
        std::_Tree<std::_Tmap_traits<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry,std::less<ConnectedStorage::ContextDesc>,std::allocator<std::pair<ConnectedStorage::ContextDesc const,ConnectedStorage::Contexts::ContextEntry>>,0>>::lower_bound(
          *a1 + 224LL,
          &v26,
          v29);
        v15 = v26;
        if ( v26 == *(_QWORD *)(*a1 + 224LL)
          || !(unsigned __int8)ConnectedStorage::operator==(v26 + 32, v29)
          || ConnectedStorage::Contexts::ContextEntry::Empty((ConnectedStorage::Contexts::ContextEntry *)(v15 + 80)) )
        {
          ConnectedStorage::Contexts::ContextEntry::ContextEntry((ConnectedStorage::Contexts::ContextEntry *)v32);
          v26 = 0;
          ConnectedStorage::LocalStorage::GetUserContextRoot((__int64)v31, 0, &v26);
          ConnectedStorage::Contexts::AddNewUploadingContextToEntry(*a1, v32, v29, v31);
          v16 = *a1;
          ConnectedStorage::ContextDesc::ContextDesc(v33, (const struct ConnectedStorage::ContextDesc *)v29);
          ConnectedStorage::Contexts::ContextEntry::ContextEntry(
            (ConnectedStorage::Contexts::ContextEntry *)v34,
            (const struct ConnectedStorage::Contexts::ContextEntry *)v32);
          std::map<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry>::insert<std::pair<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry>,0>(
            v16 + 224,
            v30,
            v15,
            v33);
          std::pair<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry>::~pair<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry>((ConnectedStorage::ContextDesc *)v33);
          std::wstring::_Tidy_deallocate(v31);
          WindowsDeleteString(0);
          ConnectedStorage::Contexts::ContextEntry::~ContextEntry((ConnectedStorage::Contexts::ContextEntry *)v32);
        }
        LeaveCriticalSection(lpCriticalSection[0]);
        ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v29);
        WindowsDeleteString(string);
        string = 0;
      }
    }
    WindowsDeleteString(v20);
    v20 = 0;
    WindowsDeleteString(v21);
    v21 = 0;
  }
  WindowsDeleteString(v19);
  v19 = 0;
  return WindowsDeleteString(newString);
}

```

## disassembly

```asm
0x1800318bc  mov     [rsp-8+arg_10], rbx
0x1800318c1  mov     [rsp-8+arg_18], rsi
0x1800318c6  push    rbp
0x1800318c7  push    rdi
0x1800318c8  push    r12
0x1800318ca  push    r14
0x1800318cc  push    r15
0x1800318ce  lea     rbp, [rsp-220h]
0x1800318d6  sub     rsp, 320h
0x1800318dd  mov     rax, cs:__security_cookie
0x1800318e4  xor     rax, rsp
0x1800318e7  mov     [rbp+240h+var_30], rax
0x1800318ee  mov     r15, rdx
0x1800318f1  mov     r14, rcx
0x1800318f4  xor     r12d, r12d
0x1800318f7  mov     rdx, [rdx]; string
0x1800318fa  lea     rcx, [rsp+340h+newString]; newString
0x1800318ff  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180031904  nop
0x180031905  mov     rdx, [r15+8]; string
0x180031909  lea     rcx, [rsp+340h+var_2F8]; newString
0x18003190e  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180031913  nop
0x180031914  mov     rax, [r14+8]
0x180031918  mov     rdi, [rax+8]
0x18003191c  mov     rbx, [rax]
0x18003191f  jmp     short loc_180031936
0x180031921  lea     rdx, [rsp+340h+newString]
0x180031926  mov     rcx, rbx
0x180031929  call    ??8SimpleHStringWrapper@ConnectedStorage@@QEBA_NAEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator==(ConnectedStorage::SimpleHStringWrapper const &)
0x18003192e  test    al, al
0x180031930  jnz     short loc_18003193B
0x180031932  add     rbx, 8
0x180031936  cmp     rbx, rdi
0x180031939  jnz     short loc_180031921
0x18003193b  mov     rax, [r14+8]
0x18003193f  cmp     rbx, [rax+8]
0x180031943  jz      loc_180031BC8
0x180031949  mov     rax, [r14]
0x18003194c  mov     rcx, [rax+0A8h]
0x180031953  mov     rax, [rcx]
0x180031956  lea     rdx, [rsp+340h+newString]
0x18003195b  mov     rax, [rax+18h]
0x18003195f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031964  test    al, al
0x180031966  jnz     loc_180031BC8
0x18003196c  mov     [rsp+340h+var_2E8], r12
0x180031971  mov     [rsp+340h+var_2F0], r12
0x180031976  mov     [rsp+340h+var_300], r12b
0x18003197b  mov     [rbp+240h+var_2B8], r12
0x18003197f  mov     rax, [r14]
0x180031982  mov     rsi, [rax+0A8h]
0x180031989  mov     rax, [rsi]
0x18003198c  mov     rdi, [rax+10h]
0x180031990  lea     rcx, [rsp+340h+var_2F0]; this
0x180031995  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18003199a  mov     rbx, rax
0x18003199d  lea     rcx, [rsp+340h+var_2E8]; this
0x1800319a2  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x1800319a7  lea     rcx, [rbp+240h+var_2B8]
0x1800319ab  mov     [rsp+340h+var_318], rcx
0x1800319b0  lea     rcx, [rsp+340h+var_300]
0x1800319b5  mov     [rsp+340h+packageRelativeApplicationId], rcx
0x1800319ba  mov     r9, rbx
0x1800319bd  mov     r8, rax
0x1800319c0  lea     rdx, [rsp+340h+newString]
0x1800319c5  mov     rcx, rsi
0x1800319c8  mov     rax, rdi
0x1800319cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319d0  lea     rcx, [rsp+340h+var_2E8]; this
0x1800319d5  call    ?IsEmpty@SimpleHStringWrapper@ConnectedStorage@@QEBA_NXZ; ConnectedStorage::SimpleHStringWrapper::IsEmpty(void)
0x1800319da  test    al, al
0x1800319dc  jnz     loc_180031BA8
0x1800319e2  lea     rcx, [rsp+340h+var_2F0]; this
0x1800319e7  call    ?IsEmpty@SimpleHStringWrapper@ConnectedStorage@@QEBA_NXZ; ConnectedStorage::SimpleHStringWrapper::IsEmpty(void)
0x1800319ec  test    al, al
0x1800319ee  jnz     loc_180031BA8
0x1800319f4  mov     [rsp+340h+packageFamilyNameLength], 41h ; 'A'
0x1800319fc  mov     [rsp+340h+packageRelativeApplicationIdLength], 42h ; 'B'
0x180031a04  xor     edx, edx; length
0x180031a06  mov     rcx, [r15+18h]; string
0x180031a0a  call    cs:__imp_WindowsGetStringRawBuffer
0x180031a10  mov     rcx, rax; applicationUserModelId
0x180031a13  lea     rax, [rbp+240h+var_C0]
0x180031a1a  mov     [rsp+340h+packageRelativeApplicationId], rax; packageRelativeApplicationId
0x180031a1f  lea     r9, [rsp+340h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x180031a24  lea     r8, [rbp+240h+packageFamilyName]; packageFamilyName
0x180031a2b  lea     rdx, [rsp+340h+packageFamilyNameLength]; packageFamilyNameLength
0x180031a30  call    cs:__imp_ParseApplicationUserModelId
0x180031a36  test    eax, eax
0x180031a38  jle     short loc_180031A44
0x180031a3a  movzx   eax, ax
0x180031a3d  or      eax, 80070000h
0x180031a42  test    eax, eax
0x180031a44  js      loc_180031BA8
0x180031a4a  lea     rdx, [rbp+240h+packageFamilyName]; sourceString
0x180031a51  lea     rcx, [rsp+340h+string]; string
0x180031a56  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180031a5b  nop
0x180031a5c  mov     [rsp+340h+var_308], r12b; bool
0x180031a61  mov     [rsp+340h+var_310], r12d; unsigned int
0x180031a66  lea     rax, [rsp+340h+string]
0x180031a6b  mov     [rsp+340h+var_318], rax; struct ConnectedStorage::SimpleHStringWrapper *
0x180031a70  lea     rax, [rsp+340h+var_2F8]
0x180031a75  mov     [rsp+340h+packageRelativeApplicationId], rax; struct ConnectedStorage::SimpleHStringWrapper *
0x180031a7a  lea     r9, [rsp+340h+newString]; struct ConnectedStorage::SimpleHStringWrapper *
0x180031a7f  lea     r8, [rsp+340h+var_2F0]; struct ConnectedStorage::SimpleHStringWrapper *
0x180031a84  lea     rdx, [rsp+340h+var_2E8]; struct ConnectedStorage::SimpleHStringWrapper *
0x180031a89  lea     rcx, [rbp+240h+var_2A0]; this
0x180031a8d  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBVSimpleHStringWrapper@1@0000K_N@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ulong,bool)
0x180031a92  nop
0x180031a93  mov     rdx, [r14]
0x180031a96  add     rdx, 0B0h; struct ConnectedStorage::Mutex *
0x180031a9d  lea     rcx, [rbp+240h+lpCriticalSection]; this
0x180031aa1  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180031aa6  nop
0x180031aa7  mov     rcx, [r14]
0x180031aaa  add     rcx, 0E0h
0x180031ab1  lea     r8, [rbp+240h+var_2A0]
0x180031ab5  lea     rdx, [rbp+240h+var_2C0]
0x180031ab9  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@VContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@U?$less@VContextDesc@ConnectedStorage@@@std@@V?$allocator@U?$pair@$$CBVContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@@std@@@6@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@@std@@@std@@@std@@@2@AEBVContextDesc@ConnectedStorage@@@Z; std::_Tree<std::_Tmap_traits<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry,std::less<ConnectedStorage::ContextDesc>,std::allocator<std::pair<ConnectedStorage::ContextDesc const,ConnectedStorage::Contexts::ContextEntry>>,0>>::lower_bound(ConnectedStorage::ContextDesc const &)
0x180031abe  mov     rax, [r14]
0x180031ac1  mov     rbx, [rbp+240h+var_2C0]
0x180031ac5  cmp     rbx, [rax+0E0h]
0x180031acc  jz      short loc_180031AF0
0x180031ace  lea     rdx, [rbp+240h+var_2A0]
0x180031ad2  lea     rcx, [rbx+20h]
0x180031ad6  call    ??8ConnectedStorage@@YA_NAEBVContextDesc@0@0@Z; ConnectedStorage::operator==(ConnectedStorage::ContextDesc const &,ConnectedStorage::ContextDesc const &)
0x180031adb  test    al, al
0x180031add  jz      short loc_180031AF0
0x180031adf  lea     rcx, [rbx+50h]; this
0x180031ae3  call    ?Empty@ContextEntry@Contexts@ConnectedStorage@@QEBA_NXZ; ConnectedStorage::Contexts::ContextEntry::Empty(void)
0x180031ae8  test    al, al
0x180031aea  jz      loc_180031B83
0x180031af0  lea     rcx, [rbp+240h+var_240]; this
0x180031af4  call    ??0ContextEntry@Contexts@ConnectedStorage@@QEAA@XZ; ConnectedStorage::Contexts::ContextEntry::ContextEntry(void)
0x180031af9  nop
0x180031afa  mov     [rbp+240h+var_2C0], r12
0x180031afe  lea     r8, [rbp+240h+var_2C0]
0x180031b02  xor     edx, edx
0x180031b04  lea     rcx, [rbp+240h+var_268]
0x180031b08  call    ?GetUserContextRoot@LocalStorage@ConnectedStorage@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KAEBVSimpleHStringWrapper@2@@Z; ConnectedStorage::LocalStorage::GetUserContextRoot(unsigned __int64,ConnectedStorage::SimpleHStringWrapper const &)
0x180031b0d  nop
0x180031b0e  lea     r9, [rbp+240h+var_268]
0x180031b12  lea     r8, [rbp+240h+var_2A0]
0x180031b16  lea     rdx, [rbp+240h+var_240]
0x180031b1a  mov     rcx, [r14]
0x180031b1d  call    ?AddNewUploadingContextToEntry@Contexts@ConnectedStorage@@AEBAJAEAUContextEntry@12@AEBVContextDesc@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::Contexts::AddNewUploadingContextToEntry(ConnectedStorage::Contexts::ContextEntry &,ConnectedStorage::ContextDesc const &,std::wstring const &)
0x180031b22  mov     rdi, [r14]
0x180031b25  lea     rdx, [rbp+240h+var_2A0]; struct ConnectedStorage::ContextDesc *
0x180031b29  lea     rcx, [rbp+240h+var_1E0]; this
0x180031b2d  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x180031b32  nop
0x180031b33  lea     rdx, [rbp+240h+var_240]; struct ConnectedStorage::Contexts::ContextEntry *
0x180031b37  lea     rcx, [rbp+240h+var_1B0]; this
0x180031b3e  call    ??0ContextEntry@Contexts@ConnectedStorage@@QEAA@AEBU012@@Z; ConnectedStorage::Contexts::ContextEntry::ContextEntry(ConnectedStorage::Contexts::ContextEntry const &)
0x180031b43  nop
0x180031b44  lea     r9, [rbp+240h+var_1E0]
0x180031b48  mov     r8, rbx
0x180031b4b  lea     rdx, [rbp+240h+var_270]
0x180031b4f  lea     rcx, [rdi+0E0h]
0x180031b56  call    ??$insert@U?$pair@VContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@@std@@$0A@@?$map@VContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@U?$less@VContextDesc@ConnectedStorage@@@std@@V?$allocator@U?$pair@$$CBVContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@@std@@@6@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@@std@@@std@@@std@@@1@$$QEAU?$pair@VContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@@1@@Z; std::map<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry>::insert<std::pair<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry>,0>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ConnectedStorage::ContextDesc const,ConnectedStorage::Contexts::ContextEntry>>>>,std::pair<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry> &&)
0x180031b5b  nop
0x180031b5c  lea     rcx, [rbp+240h+var_1E0]; this
0x180031b60  call    ??1?$pair@VContextDesc@ConnectedStorage@@UContextEntry@Contexts@2@@std@@QEAA@XZ; std::pair<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry>::~pair<ConnectedStorage::ContextDesc,ConnectedStorage::Contexts::ContextEntry>(void)
0x180031b65  nop
0x180031b66  lea     rcx, [rbp+240h+var_268]
0x180031b6a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031b6f  nop
0x180031b70  xor     ecx, ecx; string
0x180031b72  call    cs:__imp_WindowsDeleteString
0x180031b78  nop
0x180031b79  lea     rcx, [rbp+240h+var_240]; this
0x180031b7d  call    ??1ContextEntry@Contexts@ConnectedStorage@@QEAA@XZ; ConnectedStorage::Contexts::ContextEntry::~ContextEntry(void)
0x180031b82  nop
0x180031b83  mov     rcx, [rbp+240h+lpCriticalSection]; lpCriticalSection
0x180031b87  call    cs:__imp_LeaveCriticalSection
0x180031b8d  nop
0x180031b8e  lea     rcx, [rbp+240h+var_2A0]; this
0x180031b92  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180031b97  nop
0x180031b98  mov     rcx, [rsp+340h+string]; string
0x180031b9d  call    cs:__imp_WindowsDeleteString
0x180031ba3  mov     [rsp+340h+string], r12
0x180031ba8  mov     rcx, [rsp+340h+var_2F0]; string
0x180031bad  call    cs:__imp_WindowsDeleteString
0x180031bb3  mov     [rsp+340h+var_2F0], r12
0x180031bb8  mov     rcx, [rsp+340h+var_2E8]; string
0x180031bbd  call    cs:__imp_WindowsDeleteString
0x180031bc3  mov     [rsp+340h+var_2E8], r12
0x180031bc8  mov     rcx, [rsp+340h+var_2F8]; string
0x180031bcd  call    cs:__imp_WindowsDeleteString
0x180031bd3  mov     [rsp+340h+var_2F8], r12
0x180031bd8  mov     rcx, [rsp+340h+newString]; string
0x180031bdd  call    cs:__imp_WindowsDeleteString
0x180031be3  mov     rcx, [rbp+240h+var_30]
0x180031bea  xor     rcx, rsp; StackCookie
0x180031bed  call    __security_check_cookie
0x180031bf2  lea     r11, [rsp+340h+var_20]
0x180031bfa  mov     rbx, [r11+40h]
0x180031bfe  mov     rsi, [r11+48h]
0x180031c02  mov     rsp, r11
0x180031c05  pop     r15
0x180031c07  pop     r14
0x180031c09  pop     r12
0x180031c0b  pop     rdi
0x180031c0c  pop     rbp
0x180031c0d  retn
```
