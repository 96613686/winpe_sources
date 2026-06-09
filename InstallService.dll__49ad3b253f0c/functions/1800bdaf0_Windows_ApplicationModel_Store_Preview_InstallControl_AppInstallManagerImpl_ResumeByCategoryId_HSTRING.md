# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::ResumeByCategoryId(HSTRING__ *)

- ea: `0x1800bdaf0`
- end: `0x1800bdd7e`
- name: `?ResumeByCategoryId@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `654`
- prototype: `int(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x18001c844`
- `0x180037200`
- `0x18003b08c`
- `0x1800453bc`
- `0x180045588`
- `0x18006cc00`
- `0x18008fc28`
- `0x1800bdaf0`
- `0x1800c893c`
- `0x1800cd008`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800bdd10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800bdd10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800bdce3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800bdce3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bdb26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bdb79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bdcc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bdb26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bdb79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bdcc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bdb93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bdb93`

## string_xrefs

- `0x1800bdb5f`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800bdbd6`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800bdd4c`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800bdb40`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::ResumeByCategoryId`
- `0x1800bdbc9`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::ResumeByCategoryId`
- `0x1800bdd40`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::ResumeByCategoryId`
- `0x1800bdd39`: `spAgent->ResumeByCategoryId(categoryId)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::ResumeByCategoryId(
        RTL_SRWLOCK *this,
        HSTRING a2)
{
  int CallingProcessAndFunction; // eax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  HSTRING v8; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 *InstallControl2; // rsi
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rcx
  unsigned int v14; // eax
  HSTRING Ptr; // rbx
  unsigned int v16; // edi
  int v17; // eax
  int v18; // [rsp+20h] [rbp-A8h]
  int v19; // [rsp+28h] [rbp-A0h]
  _BYTE v20[8]; // [rsp+50h] [rbp-78h] BYREF
  _BYTE v21[8]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE v22[8]; // [rsp+60h] [rbp-68h] BYREF
  const winrt::hresult_error *v23; // [rsp+68h] [rbp-60h] BYREF
  int v24; // [rsp+70h] [rbp-58h] BYREF
  __int128 v25; // [rsp+78h] [rbp-50h]
  _QWORD v26[8]; // [rsp+88h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  HSTRING v28; // [rsp+D8h] [rbp+10h] BYREF
  HSTRING v29; // [rsp+E0h] [rbp+18h] BYREF
  HSTRING string; // [rsp+E8h] [rbp+20h] BYREF

  v28 = a2;
  if ( Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2((Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *)this) )
  {
    string = 0;
    WindowsDeleteString(0);
    try
    {
      string = 0;
      CallingProcessAndFunction = GetCallingProcessAndFunction(
                                    0,
                                    L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::Re"
                                     "sumeByCategoryId",
                                    &string);
      v5 = CallingProcessAndFunction;
      if ( CallingProcessAndFunction >= 0 )
      {
        v8 = string;
        StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          0x1810u,
          "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::ResumeByCategoryId",
          -1,
          L"ResumeByCategoryId request: categoryId = %s, clientAppId = %s",
          0,
          0,
          StringRawBuffer,
          v8);
        InstallControl2 = (__int64 *)Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(
                                       &this[-11],
                                       v22);
        v29 = string;
        v11 = *(_QWORD *)ToWinRTType<HSTRING__ *>(v21, &v29);
        v12 = *(_QWORD *)ToWinRTType<HSTRING__ *>(v20, &v28);
        winrt::param::hstring::hstring((winrt::param::hstring *)v26, L"WuCategoryId");
        v13 = *InstallControl2;
        v24 = 0;
        v25 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, _QWORD))(*(_QWORD *)v13 + 136LL))(
                v13,
                v26[0],
                v12,
                v11,
                0);
        winrt::check_hresult(&v29, v14, &v24);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v20);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v21);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v22);
        WindowsDeleteString(string);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x180F,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)CallingProcessAndFunction,
          v18);
        WindowsDeleteString(string);
        result = v5;
      }
    }
    catch ( const winrt::hresult_error *v23 )
    {
      LODWORD(v29) = *((_DWORD *)v23 + 3);
      return (unsigned int)v29;
    }
    catch ( ... )
    {
      LODWORD(v29) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x1813,
                       (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
                       v6);
      return (unsigned int)v29;
    }
  }
  else
  {
    AcquireSRWLockShared(this + 19);
    Ptr = (HSTRING)this[22].Ptr;
    v29 = Ptr;
    if ( Ptr )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)Ptr + 8LL))(Ptr);
    ReleaseSRWLockShared(this + 19);
    v16 = -2147418113;
    if ( Ptr )
    {
      v17 = (*(__int64 (__fastcall **)(HSTRING, HSTRING))(*(_QWORD *)Ptr + 144LL))(Ptr, a2);
      v16 = TraceHR(
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
              0x181Eu,
              "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::ResumeByCategoryId",
              "spAgent->ResumeByCategoryId(categoryId)",
              v17,
              v19);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v29);
    return v16;
  }
  return result;
}

```

## disassembly

```asm
0x1800bdaf0  mov     [rsp+arg_0], rbx
0x1800bdaf5  mov     [rsp+arg_8], rdx
0x1800bdafa  push    rsi
0x1800bdafb  push    rdi
0x1800bdafc  push    r14
0x1800bdafe  sub     rsp, 0B0h
0x1800bdb05  mov     r14, rdx
0x1800bdb08  mov     rdi, rcx
0x1800bdb0b  call    ?_ShouldUseInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA_NXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2(void)
0x1800bdb10  test    al, al
0x1800bdb12  jz      loc_1800BDCD9
0x1800bdb18  mov     [rsp+0C8h+string], 0
0x1800bdb24  xor     ecx, ecx; string
0x1800bdb26  call    cs:__imp_WindowsDeleteString
0x1800bdb2c  mov     [rsp+0C8h+string], 0
0x1800bdb38  lea     r8, [rsp+0C8h+string]; HSTRING *
0x1800bdb40  lea     rdx, aWindowsApplica_91; "Windows::ApplicationModel::Store::Previ"...
0x1800bdb47  xor     ecx, ecx; HSTRING
0x1800bdb49  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800bdb4e  mov     ebx, eax
0x1800bdb50  test    eax, eax
0x1800bdb52  jns     short loc_1800BDB86
0x1800bdb54  mov     rcx, [rsp+0C8h]; this
0x1800bdb5c  mov     r9d, eax; char *
0x1800bdb5f  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800bdb66  mov     edx, 180Fh; void *
0x1800bdb6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdb70  nop
0x1800bdb71  mov     rcx, [rsp+0C8h+string]; string
0x1800bdb79  call    cs:__imp_WindowsDeleteString
0x1800bdb7f  mov     eax, ebx
0x1800bdb81  jmp     loc_1800BDD69
0x1800bdb86  mov     rbx, [rsp+0C8h+string]
0x1800bdb8e  xor     edx, edx; length
0x1800bdb90  mov     rcx, r14; string
0x1800bdb93  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bdb99  mov     [rsp+0C8h+var_80], rbx
0x1800bdb9e  mov     [rsp+0C8h+var_88], rax
0x1800bdba3  mov     [rsp+0C8h+var_90], 0; unsigned __int16 *
0x1800bdbac  mov     [rsp+0C8h+var_98], 0; char *
0x1800bdbb5  lea     rax, aResumebycatego; "ResumeByCategoryId request: categoryId "...
0x1800bdbbc  mov     [rsp+0C8h+var_A0], rax; unsigned __int16 *
0x1800bdbc1  mov     [rsp+0C8h+var_A8], 0FFFFFFFFh; int
0x1800bdbc9  lea     r9, aWindowsApplica_134; "Windows::ApplicationModel::Store::Previ"...
0x1800bdbd0  mov     r8d, 1810h; unsigned int
0x1800bdbd6  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800bdbdd  mov     ecx, 3; unsigned int
0x1800bdbe2  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800bdbe7  lea     rcx, [rdi-58h]
0x1800bdbeb  lea     rdx, [rsp+0C8h+var_68]
0x1800bdbf0  call    ?_GetInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA?AUInstallServiceControl@Control@InstallService@Internal@6winrt@@XZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(void)
0x1800bdbf5  mov     rsi, rax
0x1800bdbf8  mov     rcx, [rsp+0C8h+string]
0x1800bdc00  mov     [rsp+0C8h+arg_10], rcx
0x1800bdc08  lea     rdx, [rsp+0C8h+arg_10]
0x1800bdc10  lea     rcx, [rsp+0C8h+var_70]
0x1800bdc15  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800bdc1a  nop
0x1800bdc1b  mov     rdi, [rax]
0x1800bdc1e  lea     rdx, [rsp+0C8h+arg_8]
0x1800bdc26  lea     rcx, [rsp+0C8h+var_78]
0x1800bdc2b  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800bdc30  nop
0x1800bdc31  mov     rbx, [rax]
0x1800bdc34  lea     rdx, aWucategoryid_0; "WuCategoryId"
0x1800bdc3b  lea     rcx, [rsp+0C8h+var_40]; this
0x1800bdc43  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800bdc48  mov     rcx, [rsi]
0x1800bdc4b  mov     [rsp+0C8h+var_58], 0
0x1800bdc53  xorps   xmm0, xmm0
0x1800bdc56  movdqu  [rsp+0C8h+var_50], xmm0
0x1800bdc5c  mov     rax, [rcx]
0x1800bdc5f  mov     qword ptr [rsp+0C8h+var_A8], 0
0x1800bdc68  mov     r9, rdi
0x1800bdc6b  mov     r8, rbx
0x1800bdc6e  mov     rdx, [rsp+0C8h+var_40]
0x1800bdc76  mov     rax, [rax+88h]
0x1800bdc7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdc82  lea     r8, [rsp+0C8h+var_58]
0x1800bdc87  mov     edx, eax
0x1800bdc89  lea     rcx, [rsp+0C8h+arg_10]
0x1800bdc91  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800bdc96  nop
0x1800bdc97  lea     rcx, [rsp+0C8h+var_78]
0x1800bdc9c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800bdca1  nop
0x1800bdca2  lea     rcx, [rsp+0C8h+var_70]
0x1800bdca7  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800bdcac  nop
0x1800bdcad  lea     rcx, [rsp+0C8h+var_68]; void *
0x1800bdcb2  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800bdcb7  nop
0x1800bdcb8  mov     rcx, [rsp+0C8h+string]; string
0x1800bdcc0  call    cs:__imp_WindowsDeleteString
0x1800bdcc6  xor     eax, eax
0x1800bdcc8  jmp     loc_1800BDD69
0x1800bdccd  mov     eax, dword ptr [rsp+0C8h+arg_10]
0x1800bdcd4  jmp     loc_1800BDD69
0x1800bdcd9  lea     rsi, [rdi+98h]
0x1800bdce0  mov     rcx, rsi; SRWLock
0x1800bdce3  call    cs:__imp_AcquireSRWLockShared
0x1800bdce9  mov     rbx, [rdi+0B0h]
0x1800bdcf0  mov     [rsp+0C8h+arg_10], rbx
0x1800bdcf8  test    rbx, rbx
0x1800bdcfb  jz      short loc_1800BDD0D
0x1800bdcfd  mov     rax, [rbx]
0x1800bdd00  mov     rcx, rbx
0x1800bdd03  mov     rax, [rax+8]
0x1800bdd07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdd0c  nop
0x1800bdd0d  mov     rcx, rsi; SRWLock
0x1800bdd10  call    cs:__imp_ReleaseSRWLockShared
0x1800bdd16  mov     edi, 8000FFFFh
0x1800bdd1b  test    rbx, rbx
0x1800bdd1e  jz      short loc_1800BDD5A
0x1800bdd20  mov     rax, [rbx]
0x1800bdd23  mov     rdx, r14
0x1800bdd26  mov     rcx, rbx
0x1800bdd29  mov     rax, [rax+90h]
0x1800bdd30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdd35  mov     [rsp+0C8h+var_A8], eax; int
0x1800bdd39  lea     r9, aSpagentResumeb; "spAgent->ResumeByCategoryId(categoryId)"
0x1800bdd40  lea     r8, aWindowsApplica_134; "Windows::ApplicationModel::Store::Previ"...
0x1800bdd47  mov     edx, 181Eh; unsigned int
0x1800bdd4c  lea     rcx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800bdd53  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800bdd58  mov     edi, eax
0x1800bdd5a  lea     rcx, [rsp+0C8h+arg_10]
0x1800bdd62  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800bdd67  mov     eax, edi
0x1800bdd69  mov     rbx, [rsp+0C8h+arg_0]
0x1800bdd71  add     rsp, 0B0h
0x1800bdd78  pop     r14
0x1800bdd7a  pop     rdi
0x1800bdd7b  pop     rsi
0x1800bdd7c  retn
```
