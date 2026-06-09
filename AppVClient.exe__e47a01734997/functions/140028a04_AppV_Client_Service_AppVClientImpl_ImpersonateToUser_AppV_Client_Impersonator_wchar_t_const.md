# AppV::Client::Service::AppVClientImpl::ImpersonateToUser(AppV::Client::Impersonator &,wchar_t * const)

- ea: `0x140028a04`
- end: `0x140028df7`
- name: `?ImpersonateToUser@AppVClientImpl@Service@Client@AppV@@CA_KAEAVImpersonator@34@QEA_W@Z`
- size: `1011`
- prototype: `unsigned __int64 __fastcall(struct AppV::Client::Impersonator *, wchar_t *const)`
- caller_count: `5`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14002b080`
- `0x14002b460`
- `0x14002be30`
- `0x140037b00`
- `0x140037eb0`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140004558`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x1400147fc`
- `0x140018bec`
- `0x14001de78`
- `0x140028a04`
- `0x14003c034`
- `0x14003c258`
- `0x14006a010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140028b89`
- `KERNEL32!CloseHandle` at `0x140028b89`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140028af0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140028af0`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140028be4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140028c18`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140028cbb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140028d9c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140028be4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140028c18`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140028cbb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140028d9c`

## string_xrefs

- `0x140028d22`: `A public API call was rejected because the Client service is in the process of shutting down.`
- `0x140028bcb`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140028d92`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140028cf6`: `AppV::Client::Service::AppVClientImpl::ImpersonateToUser`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
unsigned __int64 __fastcall AppV::Client::Service::AppVClientImpl::ImpersonateToUser(
        struct AppV::Client::Impersonator *a1,
        wchar_t *const a2)
{
  __int64 v4; // rbx
  _QWORD *v5; // rax
  __int64 *v6; // rbx
  __int128 *v7; // rdx
  __int64 **v8; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  unsigned __int64 v11; // rbx
  char *v13; // rax
  const char *v14; // rax
  char *v15; // rax
  const char *v16; // rax
  __int64 v17; // r8
  __int64 v18; // rax
  int v19; // eax
  char *v20; // rax
  const char *v21; // rax
  char *v22; // rax
  const char *v23; // rax
  HANDLE hObject; // [rsp+30h] [rbp-79h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-71h] BYREF
  unsigned int v26; // [rsp+48h] [rbp-61h] BYREF
  __int128 v27; // [rsp+50h] [rbp-59h] BYREF
  __int64 v28; // [rsp+60h] [rbp-49h]
  unsigned __int64 v29; // [rsp+68h] [rbp-41h]
  __int128 v30; // [rsp+70h] [rbp-39h] BYREF
  __int64 v31; // [rsp+80h] [rbp-29h]
  __int64 v32; // [rsp+88h] [rbp-21h]
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+90h] [rbp-19h] BYREF
  wchar_t *v34; // [rsp+A0h] [rbp-9h]
  int v35; // [rsp+A8h] [rbp-1h]
  int v36; // [rsp+ACh] [rbp+3h]
  unsigned int *v37; // [rsp+B0h] [rbp+7h]
  __int64 v38; // [rsp+B8h] [rbp+Fh]
  HANDLE *p_hObject; // [rsp+C0h] [rbp+17h]
  __int64 v40; // [rsp+C8h] [rbp+1Fh]

  if ( AppV::Client::Service::AppVClientImpl::st_allowCalls
    && AppV::Client::Service::AppVClientImpl::st_controllerRequests )
  {
    v4 = (*(__int64 (**)(void))(*(_QWORD *)AppV::Client::Service::AppVClientImpl::st_controllerRequests + 24LL))();
    Block[1] = 0;
    v5 = operator new(0x50u);
    *v5 = v5;
    v5[1] = v5;
    v5[2] = v5;
    *((_WORD *)v5 + 12) = 257;
    Block[0] = v5;
    (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v4 + 56LL))(v4, Block);
    v6 = *(__int64 **)Block[0];
    while ( v6 != Block[0] )
    {
      v27 = 0;
      v28 = 0;
      v29 = 7;
      LOWORD(v27) = 0;
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v6[8] + 24LL))(v6[8], &v27);
      v7 = &v27;
      if ( v29 > 7 )
        v7 = (__int128 *)v27;
      if ( !(unsigned int)_o__wcsicmp(a2, v7) )
      {
        hObject = 0;
        (*(void (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v6[8] + 32LL))(v6[8], &hObject);
        v11 = (*(__int64 (__fastcall **)(struct AppV::Client::Impersonator *, HANDLE))(*(_QWORD *)a1 + 8LL))(
                a1,
                hObject);
        if ( hObject )
        {
          CloseHandle(hObject);
          hObject = 0;
        }
        std::wstring::~wstring((char **)&v27);
        goto LABEL_20;
      }
      std::wstring::~wstring((char **)&v27);
      v8 = (__int64 **)v6[2];
      if ( *((_BYTE *)v8 + 25) )
      {
        for ( i = (__int64 *)v6[1]; !*((_BYTE *)i + 25) && v6 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v6 = i;
        v6 = i;
      }
      else
      {
        v6 = (__int64 *)v6[2];
        for ( j = *v8; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v6 = j;
      }
    }
    if ( (byte_1400B0B81 & 0x40) != 0 )
    {
      v13 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
      if ( v13 )
        v14 = v13 + 1;
      else
        v14 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
      AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v14);
      v15 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
      if ( v15 )
        v16 = v15 + 1;
      else
        v16 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
      v26 = ((unsigned int)AppV::FileLookUp::getFileId(
                             (AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_,
                             v16) << 20)
          | 0x2703;
      LODWORD(hObject) = 259;
      if ( a2 )
      {
        v18 = -1;
        do
          ++v18;
        while ( a2[v18] );
        v19 = 2 * v18 + 2;
      }
      else
      {
        a2 = L"NULL";
        v19 = 10;
      }
      v34 = a2;
      v35 = v19;
      v36 = 0;
      v37 = &v26;
      v38 = 4;
      p_hObject = &hObject;
      v40 = 4;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)PROVIDER_MICROSOFT_APPV_CLIENT_Context,
        (const EVENT_DESCRIPTOR *)APPV_CLIENT_Evt_UserSIDImpersonationFailed,
        v17,
        4u,
        &v33);
    }
    v20 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    if ( v20 )
      v21 = v20 + 1;
    else
      v21 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    v11 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v21) << 52)
        | 0x270300000103LL;
LABEL_20:
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>>,void *>>>(
      (__int64)Block,
      (__int64)Block,
      *((__int64 **)Block[0] + 1));
    operator delete(Block[0]);
    return v11;
  }
  else
  {
    std::string::string(&v33, "AppV::Client::Service::AppVClientImpl::ImpersonateToUser");
    LODWORD(v37) = 296;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v30,
      L"A public API call was rejected because the Client service is in the process of shutting down.",
      0x5Du);
    v27 = 0;
    v28 = 0;
    v29 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v27, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)&v33, 8, (int)&v27, (__int64)&v30);
    std::wstring::~wstring((char **)&v27);
    std::wstring::~wstring((char **)&v30);
    std::string::~string((char **)&v33);
    v22 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    if ( v22 )
      v23 = v22 + 1;
    else
      v23 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    return (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v23) << 52)
         | 0x250300000101LL;
  }
}

```

## disassembly

```asm
0x140028a04  mov     [rsp-8+arg_10], rbx
0x140028a09  mov     [rsp-8+arg_18], rsi
0x140028a0e  push    rbp
0x140028a0f  push    rdi
0x140028a10  push    r12
0x140028a12  push    r14
0x140028a14  push    r15
0x140028a16  lea     rbp, [rsp-37h]
0x140028a1b  sub     rsp, 0E0h
0x140028a22  mov     rax, cs:__security_cookie
0x140028a29  xor     rax, rsp
0x140028a2c  mov     [rbp+57h+var_30], rax
0x140028a30  mov     r14, rdx
0x140028a33  mov     rdi, rcx
0x140028a36  mov     rcx, cs:?st_controllerRequests@AppVClientImpl@Service@Client@AppV@@0REAVControllerRequests@34@EA; AppV::Client::ControllerRequests * AppV::Client::Service::AppVClientImpl::st_controllerRequests
0x140028a3d  mov     al, cs:?st_allowCalls@AppVClientImpl@Service@Client@AppV@@0_NC; bool volatile AppV::Client::Service::AppVClientImpl::st_allowCalls
0x140028a43  xor     r15d, r15d
0x140028a46  test    al, al
0x140028a48  jz      loc_140028CF6
0x140028a4e  test    rcx, rcx
0x140028a51  jz      loc_140028CF6
0x140028a57  mov     rax, [rcx]
0x140028a5a  mov     rax, [rax+18h]
0x140028a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028a63  mov     rbx, rax
0x140028a66  mov     [rbp+57h+Block], r15
0x140028a6a  mov     [rbp+57h+var_C0], r15
0x140028a6e  lea     r12d, [r15+50h]
0x140028a72  mov     ecx, r12d; Size
0x140028a75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140028a7a  mov     [rax], rax
0x140028a7d  mov     [rax+8], rax
0x140028a81  mov     [rax+10h], rax
0x140028a85  mov     word ptr [rax+18h], 101h
0x140028a8b  mov     [rbp+57h+Block], rax
0x140028a8f  mov     rax, [rbx]
0x140028a92  lea     rdx, [rbp+57h+Block]
0x140028a96  mov     rcx, rbx
0x140028a99  mov     rax, [rax+38h]
0x140028a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028aa2  mov     rbx, [rbp+57h+Block]
0x140028aa6  mov     rbx, [rbx]
0x140028aa9  cmp     rbx, [rbp+57h+Block]
0x140028aad  jz      loc_140028BC6
0x140028ab3  xorps   xmm0, xmm0
0x140028ab6  movups  [rbp+57h+var_B0], xmm0
0x140028aba  mov     [rbp+57h+var_A0], r15
0x140028abe  mov     [rbp+57h+var_98], 7
0x140028ac6  mov     word ptr [rbp+57h+var_B0], r15w
0x140028acb  mov     rcx, [rbx+40h]
0x140028acf  mov     rax, [rcx]
0x140028ad2  lea     rdx, [rbp+57h+var_B0]
0x140028ad6  mov     rax, [rax+18h]
0x140028ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028adf  lea     rdx, [rbp+57h+var_B0]
0x140028ae3  cmp     [rbp+57h+var_98], 7
0x140028ae8  cmova   rdx, qword ptr [rbp+57h+var_B0]
0x140028aed  mov     rcx, r14
0x140028af0  call    cs:__imp__o__wcsicmp
0x140028af6  test    eax, eax
0x140028af8  jz      short loc_140028B52
0x140028afa  lea     rcx, [rbp+57h+var_B0]
0x140028afe  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140028b03  mov     rcx, [rbx+10h]
0x140028b07  cmp     [rcx+19h], r15b
0x140028b0b  jz      short loc_140028B2E
0x140028b0d  mov     rax, [rbx+8]
0x140028b11  jmp     short loc_140028B20
0x140028b13  cmp     rbx, [rax+10h]
0x140028b17  jnz     short loc_140028B26
0x140028b19  mov     rbx, rax
0x140028b1c  mov     rax, [rax+8]
0x140028b20  cmp     [rax+19h], r15b
0x140028b24  jz      short loc_140028B13
0x140028b26  mov     rbx, rax
0x140028b29  jmp     loc_140028AA9
0x140028b2e  mov     rbx, rcx
0x140028b31  mov     rcx, [rcx]
0x140028b34  cmp     [rcx+19h], r15b
0x140028b38  jnz     loc_140028AA9
0x140028b3e  mov     rbx, rcx
0x140028b41  mov     rax, [rcx]
0x140028b44  mov     rcx, rax
0x140028b47  cmp     [rax+19h], r15b
0x140028b4b  jz      short loc_140028B3E
0x140028b4d  jmp     loc_140028AA9
0x140028b52  mov     [rbp+57h+hObject], r15
0x140028b56  mov     rcx, [rbx+40h]
0x140028b5a  mov     rax, [rcx]
0x140028b5d  lea     rdx, [rbp+57h+hObject]
0x140028b61  mov     rax, [rax+20h]
0x140028b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028b6a  mov     rax, [rdi]
0x140028b6d  mov     rdx, [rbp+57h+hObject]
0x140028b71  mov     rcx, rdi
0x140028b74  mov     rax, [rax+8]
0x140028b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028b7d  mov     rbx, rax
0x140028b80  mov     rcx, [rbp+57h+hObject]; hObject
0x140028b84  test    rcx, rcx
0x140028b87  jz      short loc_140028B93
0x140028b89  call    cs:__imp_CloseHandle
0x140028b8f  mov     [rbp+57h+hObject], r15
0x140028b93  lea     rcx, [rbp+57h+var_B0]
0x140028b97  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140028b9c  nop
0x140028b9d  mov     r8, [rbp+57h+Block]
0x140028ba1  mov     r8, [r8+8]
0x140028ba5  lea     rdx, [rbp+57h+Block]
0x140028ba9  lea     rcx, [rbp+57h+Block]
0x140028bad  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>>,void *> *)
0x140028bb2  mov     rdx, r12
0x140028bb5  mov     rcx, [rbp+57h+Block]; Block
0x140028bb9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140028bbe  mov     rax, rbx
0x140028bc1  jmp     loc_140028DCF
0x140028bc6  mov     edi, 5Ch ; '\'
0x140028bcb  lea     rbx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140028bd2  test    cs:byte_1400B0B81, 40h
0x140028bd9  jz      loc_140028CB6
0x140028bdf  mov     edx, edi; Ch
0x140028be1  mov     rcx, rbx; Str
0x140028be4  call    cs:__imp_strrchr
0x140028bea  test    rax, rax
0x140028bed  jz      short loc_140028BF4
0x140028bef  inc     rax
0x140028bf2  jmp     short loc_140028BF7
0x140028bf4  mov     rax, rbx
0x140028bf7  mov     rdx, rax; char *
0x140028bfa  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140028c01  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140028c06  mov     rsi, rax
0x140028c09  shl     rsi, 34h
0x140028c0d  or      esi, 103h
0x140028c13  mov     edx, edi; Ch
0x140028c15  mov     rcx, rbx; Str
0x140028c18  call    cs:__imp_strrchr
0x140028c1e  test    rax, rax
0x140028c21  jz      short loc_140028C28
0x140028c23  inc     rax
0x140028c26  jmp     short loc_140028C2B
0x140028c28  mov     rax, rbx
0x140028c2b  mov     rdx, rax; char *
0x140028c2e  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140028c35  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140028c3a  shl     rax, 14h
0x140028c3e  or      eax, 2703h
0x140028c43  mov     [rbp+57h+var_B8], eax
0x140028c46  mov     dword ptr [rbp+57h+hObject], esi
0x140028c49  test    r14, r14
0x140028c4c  jz      short loc_140028C65
0x140028c4e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140028c52  inc     rax
0x140028c55  cmp     [r14+rax*2], r15w
0x140028c5a  jnz     short loc_140028C52
0x140028c5c  lea     eax, ds:2[rax*2]
0x140028c63  jmp     short loc_140028C71
0x140028c65  lea     r14, aNull; "NULL"
0x140028c6c  mov     eax, 0Ah
0x140028c71  mov     [rbp+57h+var_60], r14
0x140028c75  mov     [rbp+57h+var_58], eax
0x140028c78  mov     [rbp+57h+var_54], r15d
0x140028c7c  lea     rax, [rbp+57h+var_B8]
0x140028c80  mov     [rbp+57h+var_50], rax
0x140028c84  mov     r9d, 4
0x140028c8a  mov     [rbp+57h+var_48], r9
0x140028c8e  lea     rax, [rbp+57h+hObject]
0x140028c92  mov     [rbp+57h+var_40], rax
0x140028c96  mov     [rbp+57h+var_38], r9
0x140028c9a  lea     rax, [rbp+57h+var_70]
0x140028c9e  mov     [rsp+100h+var_E0], rax
0x140028ca3  lea     rdx, APPV_CLIENT_Evt_UserSIDImpersonationFailed
0x140028caa  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x140028cb1  call    McGenEventWrite_EventWriteTransfer
0x140028cb6  mov     edx, edi; Ch
0x140028cb8  mov     rcx, rbx; Str
0x140028cbb  call    cs:__imp_strrchr
0x140028cc1  test    rax, rax
0x140028cc4  jz      short loc_140028CCB
0x140028cc6  inc     rax
0x140028cc9  jmp     short loc_140028CCE
0x140028ccb  mov     rax, rbx
0x140028cce  mov     rdx, rax; char *
0x140028cd1  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140028cd8  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140028cdd  mov     rbx, rax
0x140028ce0  shl     rbx, 34h
0x140028ce4  mov     rax, 270300000103h
0x140028cee  or      rbx, rax
0x140028cf1  jmp     loc_140028B9D
0x140028cf6  lea     rdx, aAppvClientServ_23; "AppV::Client::Service::AppVClientImpl::"...
0x140028cfd  lea     rcx, [rbp+57h+var_70]
0x140028d01  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028d06  mov     dword ptr [rbp+57h+var_50], 128h
0x140028d0d  xorps   xmm0, xmm0
0x140028d10  movups  [rbp+57h+var_90], xmm0
0x140028d14  mov     [rbp+57h+var_80], r15
0x140028d18  mov     [rbp+57h+var_78], r15
0x140028d1c  mov     r8d, 5Dh ; ']'
0x140028d22  lea     rdx, aAPublicApiCall; "A public API call was rejected because "...
0x140028d29  lea     rcx, [rbp+57h+var_90]
0x140028d2d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140028d32  nop
0x140028d33  xorps   xmm0, xmm0
0x140028d36  movups  [rbp+57h+var_B0], xmm0
0x140028d3a  mov     [rbp+57h+var_A0], r15
0x140028d3e  mov     [rbp+57h+var_98], r15
0x140028d42  mov     r8d, 6
0x140028d48  lea     rdx, aClient; "Client"
0x140028d4f  lea     rcx, [rbp+57h+var_B0]
0x140028d53  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140028d58  nop
0x140028d59  lea     r9, [rbp+57h+var_90]
0x140028d5d  lea     r8, [rbp+57h+var_B0]
0x140028d61  mov     edx, 8
0x140028d66  lea     rcx, [rbp+57h+var_70]
0x140028d6a  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140028d6f  nop
0x140028d70  lea     rcx, [rbp+57h+var_B0]
0x140028d74  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140028d79  nop
0x140028d7a  lea     rcx, [rbp+57h+var_90]
0x140028d7e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140028d83  nop
0x140028d84  lea     rcx, [rbp+57h+var_70]
0x140028d88  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140028d8d  mov     edx, 5Ch ; '\'; Ch
0x140028d92  lea     rbx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140028d99  mov     rcx, rbx; Str
0x140028d9c  call    cs:__imp_strrchr
0x140028da2  test    rax, rax
0x140028da5  jz      short loc_140028DAC
0x140028da7  inc     rax
0x140028daa  jmp     short loc_140028DAF
0x140028dac  mov     rax, rbx
0x140028daf  mov     rdx, rax; char *
0x140028db2  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140028db9  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140028dbe  shl     rax, 34h
0x140028dc2  mov     rcx, 250300000101h
0x140028dcc  or      rax, rcx
0x140028dcf  mov     rcx, [rbp+57h+var_30]
0x140028dd3  xor     rcx, rsp; StackCookie
0x140028dd6  call    __security_check_cookie
0x140028ddb  lea     r11, [rsp+100h+var_20]
0x140028de3  mov     rbx, [r11+40h]
0x140028de7  mov     rsi, [r11+48h]
0x140028deb  mov     rsp, r11
0x140028dee  pop     r15
0x140028df0  pop     r14
0x140028df2  pop     r12
0x140028df4  pop     rdi
0x140028df5  pop     rbp
0x140028df6  retn
```
