# ConnectedStorage::Contexts::GetAllContexts(void)

- ea: `0x180033414`
- end: `0x1800335f6`
- name: `?GetAllContexts@Contexts@ConnectedStorage@@QEBA?AV?$vector@UXblGameSaveProviderInfo@@V?$allocator@UXblGameSaveProviderInfo@@@std@@@std@@XZ`
- size: `482`
- prototype: `__int64 __fastcall(ConnectedStorage::Contexts *this)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x180014cf8`
- `0x180034734`

## callees

- `0x180003c70`
- `0x180004754`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180011040`
- `0x18001b9c8`
- `0x18001c090`
- `0x1800270e8`
- `0x18002ee50`
- `0x180032674`
- `0x180033394`
- `0x1800333e8`
- `0x180033414`
- `0x18003373c`
- `0x180036534`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800335cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800335cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800335bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800335bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct _RTL_CRITICAL_SECTION *__fastcall ConnectedStorage::Contexts::GetAllContexts(
        ConnectedStorage::Contexts *this,
        struct _RTL_CRITICAL_SECTION *a2,
        char *a3)
{
  const unsigned __int16 *v5; // rax
  int v6; // edx
  int v7; // edx
  const unsigned __int16 *v8; // rax
  signed int Next; // eax
  const unsigned __int16 *v10; // r8
  bool v11; // sf
  __int64 v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+28h] [rbp-D8h]
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v17[3]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h]
  _BYTE v19[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v20[40]; // [rsp+A8h] [rbp-58h] BYREF
  struct _WIN32_FIND_DATAW v21; // [rsp+D0h] [rbp-30h] BYREF

  lpCriticalSection[2] = a2;
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 176),
    a3);
  std::vector<ConnectedStorage::MultiFileWrite::Entry>::vector<ConnectedStorage::MultiFileWrite::Entry>(a2);
  v14 = 1;
  v15 = 0;
  ConnectedStorage::LocalStorage::GetUserContextRoot((__int64)v19, 0, &v15);
  std::operator+<unsigned short>(v20, v19, L"\\*");
  memset_0(&v21, 0, sizeof(v21));
  v13 = -1;
  v5 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
  if ( ConnectedStorage::FindFile::FindFirst((ConnectedStorage::FindFile *)&v13, v5, &v21) - 2 > 1 )
  {
    do
    {
      if ( (v21.dwFileAttributes & 0x10) != 0 )
      {
        v6 = v21.cFileName[0] - 46;
        if ( v21.cFileName[0] == 46 )
          v6 = v21.cFileName[1];
        if ( v6 )
        {
          v7 = v21.cFileName[0] - 46;
          if ( v21.cFileName[0] == 46 )
          {
            v7 = v21.cFileName[1] - 46;
            if ( v21.cFileName[1] == 46 )
              v7 = v21.cFileName[2];
          }
          if ( v7 )
          {
            memset(v17, 0, sizeof(v17));
            v18 = 0;
            v8 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v19);
            if ( ConnectedStorage::Contexts::GetSpaceInfoFromDirectoryName(
                   this,
                   v8,
                   (ConnectedStorage *)v21.cFileName,
                   (struct XblGameSaveProviderInfo *)v17) )
            {
              std::vector<XblGameSaveProviderInfo>::push_back(a2, v17);
            }
          }
        }
      }
      Next = ConnectedStorage::FindFile::FindNext((ConnectedStorage::FindFile *)&v13, &v21);
    }
    while ( !Next );
    if ( Next != 18 )
    {
      v11 = Next < 0;
      if ( Next > 0 )
      {
        Next = (unsigned __int16)Next | 0x80070000;
        v11 = Next < 0;
      }
      if ( v11 )
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)(unsigned int)Next,
          (int)L"Contexts::GetAllContexts",
          v10);
    }
  }
  ConnectedStorage::FindFile::Close((ConnectedStorage::FindFile *)&v13);
  std::wstring::_Tidy_deallocate(v20);
  std::wstring::_Tidy_deallocate(v19);
  WindowsDeleteString(0);
  LeaveCriticalSection(lpCriticalSection[0]);
  return a2;
}

```

## disassembly

```asm
0x180033414  mov     [rsp-8+arg_10], rbx
0x180033419  push    rbp
0x18003341a  push    rsi
0x18003341b  push    rdi
0x18003341c  lea     rbp, [rsp-230h]
0x180033424  sub     rsp, 330h
0x18003342b  mov     rax, cs:__security_cookie
0x180033432  xor     rax, rsp
0x180033435  mov     [rbp+240h+var_20], rax
0x18003343c  mov     rbx, rdx
0x18003343f  mov     rdi, rcx
0x180033442  mov     [rsp+340h+var_2F8], rdx
0x180033447  mov     esi, 1
0x18003344c  mov     [rsp+340h+var_318], esi
0x180033450  lea     rdx, [rcx+0B0h]; struct ConnectedStorage::Mutex *
0x180033457  lea     rcx, [rsp+340h+lpCriticalSection]; this
0x18003345c  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180033461  nop
0x180033462  mov     rcx, rbx
0x180033465  call    ??0?$vector@UEntry@MultiFileWrite@ConnectedStorage@@V?$allocator@UEntry@MultiFileWrite@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::MultiFileWrite::Entry>::vector<ConnectedStorage::MultiFileWrite::Entry>(void)
0x18003346a  nop
0x18003346b  mov     [rsp+340h+var_318], esi
0x18003346f  mov     [rsp+340h+var_310], 0
0x180033478  lea     r8, [rsp+340h+var_310]
0x18003347d  xor     edx, edx
0x18003347f  lea     rcx, [rbp+240h+var_2B8]
0x180033483  call    ?GetUserContextRoot@LocalStorage@ConnectedStorage@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KAEBVSimpleHStringWrapper@2@@Z; ConnectedStorage::LocalStorage::GetUserContextRoot(unsigned __int64,ConnectedStorage::SimpleHStringWrapper const &)
0x180033488  nop
0x180033489  lea     r8, asc_18009B7C4; "\\*"
0x180033490  lea     rdx, [rbp+240h+var_2B8]
0x180033494  lea     rcx, [rbp+240h+var_298]
0x180033498  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003349d  nop
0x18003349e  xor     edx, edx; Val
0x1800334a0  mov     r8d, 250h; Size
0x1800334a6  lea     rcx, [rbp+240h+var_270]; void *
0x1800334aa  call    memset_0
0x1800334af  mov     [rsp+340h+var_320], 0FFFFFFFFFFFFFFFFh
0x1800334b8  lea     rcx, [rbp+240h+var_298]
0x1800334bc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800334c1  mov     rdx, rax; unsigned __int16 *
0x1800334c4  lea     r8, [rbp+240h+var_270]; struct _WIN32_FIND_DATAW *
0x1800334c8  lea     rcx, [rsp+340h+var_320]; this
0x1800334cd  call    ?FindFirst@FindFile@ConnectedStorage@@QEAAKPEBGPEAU_WIN32_FIND_DATAW@@@Z; ConnectedStorage::FindFile::FindFirst(ushort const *,_WIN32_FIND_DATAW *)
0x1800334d2  add     eax, 0FFFFFFFEh
0x1800334d5  cmp     eax, esi
0x1800334d7  jbe     loc_18003359E
0x1800334dd  mov     esi, 2Eh ; '.'
0x1800334e2  test    byte ptr [rbp+240h+var_270.dwFileAttributes], 10h
0x1800334e6  jz      short loc_180033564
0x1800334e8  movzx   edx, [rbp+240h+var_270.cFileName]
0x1800334ec  sub     edx, esi
0x1800334ee  jnz     short loc_1800334FB
0x1800334f0  movzx   edx, [rbp+240h+var_270.cFileName+2]
0x1800334f4  xor     eax, eax
0x1800334f6  movzx   ecx, ax
0x1800334f9  sub     edx, ecx
0x1800334fb  test    edx, edx
0x1800334fd  jz      short loc_180033564
0x1800334ff  movzx   edx, [rbp+240h+var_270.cFileName]
0x180033503  sub     edx, esi
0x180033505  jnz     short loc_18003351A
0x180033507  movzx   edx, [rbp+240h+var_270.cFileName+2]
0x18003350b  sub     edx, esi
0x18003350d  jnz     short loc_18003351A
0x18003350f  movzx   edx, [rbp+240h+var_270.cFileName+4]
0x180033513  xor     eax, eax
0x180033515  movzx   ecx, ax
0x180033518  sub     edx, ecx
0x18003351a  test    edx, edx
0x18003351c  jz      short loc_180033564
0x18003351e  xorps   xmm0, xmm0
0x180033521  xor     eax, eax
0x180033523  movups  [rsp+340h+var_2F0], xmm0
0x180033528  movups  [rsp+340h+var_2E0], xmm0
0x18003352d  movups  [rsp+340h+var_2D0], xmm0
0x180033532  mov     [rbp+240h+var_2C0], rax
0x180033536  lea     rcx, [rbp+240h+var_2B8]
0x18003353a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003353f  mov     rdx, rax; unsigned __int16 *
0x180033542  lea     r9, [rsp+340h+var_2F0]; struct XblGameSaveProviderInfo *
0x180033547  lea     r8, [rbp+240h+var_270.cFileName]; unsigned __int16 *
0x18003354b  mov     rcx, rdi; this
0x18003354e  call    ?GetSpaceInfoFromDirectoryName@Contexts@ConnectedStorage@@AEBA_NPEBGPEAGPEAUXblGameSaveProviderInfo@@@Z; ConnectedStorage::Contexts::GetSpaceInfoFromDirectoryName(ushort const *,ushort *,XblGameSaveProviderInfo *)
0x180033553  test    al, al
0x180033555  jz      short loc_180033564
0x180033557  lea     rdx, [rsp+340h+var_2F0]
0x18003355c  mov     rcx, rbx
0x18003355f  call    ?push_back@?$vector@UXblGameSaveProviderInfo@@V?$allocator@UXblGameSaveProviderInfo@@@std@@@std@@QEAAXAEBUXblGameSaveProviderInfo@@@Z; std::vector<XblGameSaveProviderInfo>::push_back(XblGameSaveProviderInfo const &)
0x180033564  lea     rdx, [rbp+240h+var_270]; struct _WIN32_FIND_DATAW *
0x180033568  lea     rcx, [rsp+340h+var_320]; this
0x18003356d  call    ?FindNext@FindFile@ConnectedStorage@@QEAAKPEAU_WIN32_FIND_DATAW@@@Z; ConnectedStorage::FindFile::FindNext(_WIN32_FIND_DATAW *)
0x180033572  test    eax, eax
0x180033574  jz      loc_1800334E2
0x18003357a  cmp     eax, 12h
0x18003357d  jz      short loc_18003359E
0x18003357f  test    eax, eax
0x180033581  jle     short loc_18003358D
0x180033583  movzx   eax, ax
0x180033586  or      eax, 80070000h
0x18003358b  test    eax, eax
0x18003358d  jns     short loc_18003359E
0x18003358f  lea     rdx, aContextsGetall; "Contexts::GetAllContexts"
0x180033596  mov     ecx, eax; this
0x180033598  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18003359e  lea     rcx, [rsp+340h+var_320]; this
0x1800335a3  call    ?Close@FindFile@ConnectedStorage@@QEAAXXZ; ConnectedStorage::FindFile::Close(void)
0x1800335a8  nop
0x1800335a9  lea     rcx, [rbp+240h+var_298]
0x1800335ad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800335b2  nop
0x1800335b3  lea     rcx, [rbp+240h+var_2B8]
0x1800335b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800335bc  nop
0x1800335bd  xor     ecx, ecx; string
0x1800335bf  call    cs:__imp_WindowsDeleteString
0x1800335c5  nop
0x1800335c6  mov     rcx, [rsp+340h+lpCriticalSection]; lpCriticalSection
0x1800335cb  call    cs:__imp_LeaveCriticalSection
0x1800335d1  mov     rax, rbx
0x1800335d4  mov     rcx, [rbp+240h+var_20]
0x1800335db  xor     rcx, rsp; StackCookie
0x1800335de  call    __security_check_cookie
0x1800335e3  mov     rbx, [rsp+340h+arg_10]
0x1800335eb  add     rsp, 330h
0x1800335f2  pop     rdi
0x1800335f3  pop     rsi
0x1800335f4  pop     rbp
0x1800335f5  retn
```
