# ConnectedStorage::ProviderEnumerator::DeleteLocalAndCloudData(HSTRING__ *,HSTRING__ *)

- ea: `0x1800200d0`
- end: `0x18002032d`
- name: `?DeleteLocalAndCloudData@ProviderEnumerator@ConnectedStorage@@MEAAJPEAUHSTRING__@@0@Z`
- size: `605`
- prototype: `__int64 __fastcall(ConnectedStorage::ProviderEnumerator *__hidden this, HSTRING string, HSTRING)`
- caller_count: `0`
- callee_count: `17`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180011bd0`
- `0x180011c0c`
- `0x180013e1c`
- `0x1800145d8`
- `0x1800160c8`
- `0x1800170d4`
- `0x18001c63c`
- `0x18001fd80`
- `0x18001ff28`
- `0x18001ff8c`
- `0x1800200d0`
- `0x1800204a8`
- `0x180020898`
- `0x1800235c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002016c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002016c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800201ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800202bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800202d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800202e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800201ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800202bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800202d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800202e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020241`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180020269`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180020269`

## string_xrefs

- `0x18002013c`: `The service has shutdown.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ConnectedStorage::ProviderEnumerator::DeleteLocalAndCloudData(
        ConnectedStorage::ProviderEnumerator *this,
        HSTRING string,
        HSTRING a3)
{
  char *v6; // r8
  const unsigned __int16 *v7; // r8
  ConnectedStorage::Service *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // r8
  __int64 v13; // rax
  const unsigned __int16 *v14; // r8
  const WCHAR *StringRawBuffer; // rax
  int v16; // eax
  const unsigned __int16 *v17; // r8
  bool v18; // sf
  unsigned int v20; // [rsp+30h] [rbp-1E8h]
  HSTRING v21; // [rsp+38h] [rbp-1E0h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+40h] [rbp-1D8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+44h] [rbp-1D4h] BYREF
  HSTRING v24; // [rsp+48h] [rbp-1D0h] BYREF
  HSTRING newString; // [rsp+50h] [rbp-1C8h] BYREF
  HSTRING stringa; // [rsp+58h] [rbp-1C0h] BYREF
  __int64 v27; // [rsp+60h] [rbp-1B8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+68h] [rbp-1B0h] BYREF
  _BYTE v29[16]; // [rsp+80h] [rbp-198h] BYREF
  _DWORD v30[16]; // [rsp+90h] [rbp-188h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+D0h] [rbp-148h] BYREF
  WCHAR packageRelativeApplicationId[72]; // [rsp+160h] [rbp-B8h] BYREF

  v20 = 0;
  try
  {
    ConnectedStorage::ProviderEnumerator::CheckCaller(this);
    if ( !ConnectedStorage::gShutdown )
    {
      ConnectedStorage::Event::Wait((ConnectedStorage::Event *)&qword_1800C0998, 0xFFFFFFFF);
      ConnectedStorage::Mutex::Lock::Lock((ConnectedStorage::Mutex::Lock *)lpCriticalSection, &CriticalSection, v6);
      if ( !ConnectedStorage::gServiceRef )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80004005LL, (int)L"The service has shutdown.", v7);
      ++ConnectedStorage::gServiceRef;
      ConnectedStorage::Service::AddServiceActivity(qword_1800C0858, 2);
      LeaveCriticalSection(lpCriticalSection[0]);
    }
    v8 = qword_1800C0858;
    lpCriticalSection[2] = (LPCRITICAL_SECTION)qword_1800C0858;
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, string);
    v9 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&stringa, a3);
    ConnectedStorage::NormalizeScid(&v21, v9);
    WindowsDeleteString(stringa);
    stringa = 0;
    ConnectedStorage::ProviderEnumerator::Enumerate(this);
    std::vector<ConnectedStorage::BlobRecord>::end((char *)this + 72, v29);
    v11 = (_QWORD *)std::vector<ConnectedStorage::ContextDesc>::begin(v10, lpCriticalSection);
    std::find_if_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_XblGameSaveProviderInfo_______lambda_8a8d4905eb495ac4f392b248442728df___(
      &v27,
      *v11,
      v12,
      &v21);
    v13 = std::vector<ConnectedStorage::BlobRecord>::end((char *)this + 72, lpCriticalSection);
    if ( (unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<ConnectedStorage::Container>>>>>::operator==(
                            &v27,
                            v13) )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80070490LL, (int)L"SCID lookup failed", v14);
    packageFamilyNameLength = 65;
    packageRelativeApplicationIdLength = 66;
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(v27 + 24), 0);
    v16 = ParseApplicationUserModelId(
            StringRawBuffer,
            &packageFamilyNameLength,
            packageFamilyName,
            &packageRelativeApplicationIdLength,
            packageRelativeApplicationId);
    v18 = v16 < 0;
    if ( v16 > 0 )
    {
      v16 = (unsigned __int16)v16 | 0x80070000;
      v18 = v16 < 0;
    }
    if ( v18 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v16,
        (int)L"HRESULT_FROM_WIN32(ParseApplicationUserModelId( WindowsGetStringRawBuffer(find->Aumid, nullptr), &packageFa"
              "milyNameBufferLength, packageFamilyNameBuffer, &appIdLength, appId))",
        v17);
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v24, packageFamilyName);
    ConnectedStorage::Service::DeleteLocalAndCloudStorageForContext(
      v8,
      (struct ConnectedStorage::SimpleHStringWrapper *)&newString,
      (struct ConnectedStorage::SimpleHStringWrapper *)&v21,
      (struct ConnectedStorage::SimpleHStringWrapper *)&v24);
    WindowsDeleteString(v24);
    v24 = 0;
    WindowsDeleteString(v21);
    v21 = 0;
    WindowsDeleteString(newString);
    newString = 0;
    if ( v8 )
      ConnectedStorage::Service::ReturnInstance();
  }
  catch ( ConnectedStorage::ComError v30 )
  {
    v20 = v30[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v30);
    return v20;
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( ... )
  {
    return (unsigned int)-2147467259;
  }
  return v20;
}

```

## disassembly

```asm
0x1800200d0  mov     [rsp+arg_18], rbx
0x1800200d5  push    rsi
0x1800200d6  push    rdi
0x1800200d7  push    r14
0x1800200d9  sub     rsp, 200h
0x1800200e0  mov     rax, cs:__security_cookie
0x1800200e7  xor     rax, rsp
0x1800200ea  mov     [rsp+218h+var_28], rax
0x1800200f2  mov     r14, r8
0x1800200f5  mov     rdi, rdx
0x1800200f8  mov     rsi, rcx
0x1800200fb  mov     [rsp+218h+var_1E8], 0
0x180020103  call    ?CheckCaller@ProviderEnumerator@ConnectedStorage@@AEAAXXZ; ConnectedStorage::ProviderEnumerator::CheckCaller(void)
0x180020108  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, 0; bool ConnectedStorage::gShutdown
0x18002010f  jnz     short loc_180020172
0x180020111  or      edx, 0FFFFFFFFh; unsigned int
0x180020114  lea     rcx, qword_1800C0998; this
0x18002011b  call    ?Wait@Event@ConnectedStorage@@QEAA_NK@Z; ConnectedStorage::Event::Wait(ulong)
0x180020120  lea     rdx, CriticalSection; struct ConnectedStorage::Mutex *
0x180020127  lea     rcx, [rsp+218h+lpCriticalSection]; this
0x18002012c  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180020131  nop
0x180020132  mov     eax, cs:?gServiceRef@ConnectedStorage@@3IA; uint ConnectedStorage::gServiceRef
0x180020138  test    eax, eax
0x18002013a  jnz     short loc_18002014D
0x18002013c  lea     rdx, aTheServiceHasS; "The service has shutdown."
0x180020143  mov     ecx, 80004005h; this
0x180020148  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002014d  inc     eax
0x18002014f  mov     cs:?gServiceRef@ConnectedStorage@@3IA, eax; uint ConnectedStorage::gServiceRef
0x180020155  mov     edx, 2
0x18002015a  mov     rcx, cs:qword_1800C0858
0x180020161  call    ?AddServiceActivity@Service@ConnectedStorage@@AEAAXW4ServiceActivity@12@@Z; ConnectedStorage::Service::AddServiceActivity(ConnectedStorage::Service::ServiceActivity)
0x180020166  nop
0x180020167  mov     rcx, [rsp+218h+lpCriticalSection]; lpCriticalSection
0x18002016c  call    cs:__imp_LeaveCriticalSection
0x180020172  mov     rbx, cs:qword_1800C0858
0x180020179  mov     [rsp+218h+var_1A0], rbx
0x18002017e  mov     rdx, rdi; string
0x180020181  lea     rcx, [rsp+218h+newString]; newString
0x180020186  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x18002018b  nop
0x18002018c  mov     rdx, r14; string
0x18002018f  lea     rcx, [rsp+218h+string]; newString
0x180020194  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180020199  nop
0x18002019a  mov     rdx, rax
0x18002019d  lea     rcx, [rsp+218h+var_1E0]
0x1800201a2  call    ?NormalizeScid@ConnectedStorage@@YA?AVSimpleHStringWrapper@1@AEBV21@@Z; ConnectedStorage::NormalizeScid(ConnectedStorage::SimpleHStringWrapper const &)
0x1800201a7  nop
0x1800201a8  mov     rcx, [rsp+218h+string]; string
0x1800201ad  call    cs:__imp_WindowsDeleteString
0x1800201b3  mov     [rsp+218h+string], 0
0x1800201bc  mov     rcx, rsi; this
0x1800201bf  call    ?Enumerate@ProviderEnumerator@ConnectedStorage@@AEAAXXZ; ConnectedStorage::ProviderEnumerator::Enumerate(void)
0x1800201c4  lea     rdi, [rsi+48h]
0x1800201c8  lea     rdx, [rsp+218h+var_198]
0x1800201d0  mov     rcx, rdi
0x1800201d3  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x1800201d8  mov     r8, [rax]
0x1800201db  lea     rdx, [rsp+218h+lpCriticalSection]
0x1800201e0  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x1800201e5  lea     r9, [rsp+218h+var_1E0]
0x1800201ea  mov     rdx, [rax]
0x1800201ed  lea     rcx, [rsp+218h+var_1B8]
0x1800201f2  call    std__find_if_std___Vector_const_iterator_std___Vector_val_std___Simple_types_XblGameSaveProviderInfo_______lambda_8a8d4905eb495ac4f392b248442728df___
0x1800201f7  lea     rdx, [rsp+218h+lpCriticalSection]
0x1800201fc  mov     rcx, rdi
0x1800201ff  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x180020204  mov     rdx, rax
0x180020207  lea     rcx, [rsp+218h+var_1B8]
0x18002020c  call    ??8?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VContainer@ConnectedStorage@@@std@@@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<ConnectedStorage::Container>>>>>::operator==(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<ConnectedStorage::Container>>>>> const &)
0x180020211  test    al, al
0x180020213  jz      short loc_180020226
0x180020215  lea     rdx, aScidLookupFail; "SCID lookup failed"
0x18002021c  mov     ecx, 80070490h; this
0x180020221  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180020226  mov     [rsp+218h+packageFamilyNameLength], 41h ; 'A'
0x18002022e  mov     [rsp+218h+packageRelativeApplicationIdLength], 42h ; 'B'
0x180020236  xor     edx, edx; length
0x180020238  mov     rcx, [rsp+218h+var_1B8]
0x18002023d  mov     rcx, [rcx+18h]; string
0x180020241  call    cs:__imp_WindowsGetStringRawBuffer
0x180020247  mov     rcx, rax; applicationUserModelId
0x18002024a  lea     rax, [rsp+218h+var_B8]
0x180020252  mov     [rsp+218h+packageRelativeApplicationId], rax; packageRelativeApplicationId
0x180020257  lea     r9, [rsp+218h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18002025c  lea     r8, [rsp+218h+packageFamilyName]; packageFamilyName
0x180020264  lea     rdx, [rsp+218h+packageFamilyNameLength]; packageFamilyNameLength
0x180020269  call    cs:__imp_ParseApplicationUserModelId
0x18002026f  test    eax, eax
0x180020271  jle     short loc_18002027D
0x180020273  movzx   eax, ax
0x180020276  or      eax, 80070000h
0x18002027b  test    eax, eax
0x18002027d  jns     short loc_18002028D
0x18002027f  lea     rdx, aHresultFromWin_1; "HRESULT_FROM_WIN32(ParseApplicationUser"...
0x180020286  mov     ecx, eax; this
0x180020288  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002028d  lea     rdx, [rsp+218h+packageFamilyName]; sourceString
0x180020295  lea     rcx, [rsp+218h+var_1D0]; string
0x18002029a  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18002029f  nop
0x1800202a0  lea     r9, [rsp+218h+var_1D0]; struct ConnectedStorage::SimpleHStringWrapper *
0x1800202a5  lea     r8, [rsp+218h+var_1E0]; struct ConnectedStorage::SimpleHStringWrapper *
0x1800202aa  lea     rdx, [rsp+218h+newString]; struct ConnectedStorage::SimpleHStringWrapper *
0x1800202af  mov     rcx, rbx; this
0x1800202b2  call    ?DeleteLocalAndCloudStorageForContext@Service@ConnectedStorage@@QEAAXAEAVSimpleHStringWrapper@2@00@Z; ConnectedStorage::Service::DeleteLocalAndCloudStorageForContext(ConnectedStorage::SimpleHStringWrapper &,ConnectedStorage::SimpleHStringWrapper &,ConnectedStorage::SimpleHStringWrapper &)
0x1800202b7  nop
0x1800202b8  mov     rcx, [rsp+218h+var_1D0]; string
0x1800202bd  call    cs:__imp_WindowsDeleteString
0x1800202c3  mov     [rsp+218h+var_1D0], 0
0x1800202cc  mov     rcx, [rsp+218h+var_1E0]; string
0x1800202d1  call    cs:__imp_WindowsDeleteString
0x1800202d7  mov     [rsp+218h+var_1E0], 0
0x1800202e0  mov     rcx, [rsp+218h+newString]; string
0x1800202e5  call    cs:__imp_WindowsDeleteString
0x1800202eb  mov     [rsp+218h+newString], 0
0x1800202f4  test    rbx, rbx
0x1800202f7  jz      short loc_1800202FF
0x1800202f9  call    ?ReturnInstance@Service@ConnectedStorage@@CAXXZ; ConnectedStorage::Service::ReturnInstance(void)
0x1800202fe  nop
0x1800202ff  jmp     short loc_180020305
0x180020301  jmp     short loc_180020305
0x180020303  jmp     short $+2
0x180020305  mov     eax, [rsp+218h+var_1E8]
0x180020309  mov     rcx, [rsp+218h+var_28]
0x180020311  xor     rcx, rsp; StackCookie
0x180020314  call    __security_check_cookie
0x180020319  mov     rbx, [rsp+218h+arg_18]
0x180020321  add     rsp, 200h
0x180020328  pop     r14
0x18002032a  pop     rdi
0x18002032b  pop     rsi
0x18002032c  retn
```
