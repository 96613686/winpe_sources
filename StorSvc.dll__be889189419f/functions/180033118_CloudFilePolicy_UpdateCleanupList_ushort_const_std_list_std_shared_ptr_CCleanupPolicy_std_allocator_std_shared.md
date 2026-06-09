# CloudFilePolicy::UpdateCleanupList(ushort const *,std::list<std::shared_ptr<CCleanupPolicy>,std::allocator<std::shared_ptr<CCleanupPolicy>>> &,_STORAGE_TRIGGER_POLICIES_FLAGS,TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> *,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,SYNC_ROOT_INFO,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,SYNC_ROOT_INFO>>> &)

- ea: `0x180033118`
- end: `0x1800334af`
- name: `?UpdateCleanupList@CloudFilePolicy@@SAJPEBGAEAV?$list@V?$shared_ptr@VCCleanupPolicy@@@std@@V?$allocator@V?$shared_ptr@VCCleanupPolicy@@@std@@@2@@std@@W4_STORAGE_TRIGGER_POLICIES_FLAGS@@PEAV?$TraceLoggingActivity@$1?StorageServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@AEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USYNC_ROOT_INFO@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USYNC_ROOT_INFO@@@std@@@2@@3@@Z`
- size: `919`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x18003253c`

## callees

- `0x180001148`
- `0x1800032e4`
- `0x18000d030`
- `0x18000ddb0`
- `0x180012734`
- `0x18001c130`
- `0x18001fcac`
- `0x180024ac4`
- `0x18003037c`
- `0x180031560`
- `0x180033118`
- `0x1800343b4`
- `0x1800393f0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18003316d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18003336b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18003316d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18003336b`
- `RPCRT4!RpcRevertToSelf` at `0x180033428`
- `RPCRT4!RpcRevertToSelf` at `0x180033428`
- `cldapi!CfGetSyncRootInfoByPath` at `0x180033402`
- `cldapi!CfGetSyncRootInfoByPath` at `0x180033402`

## string_xrefs

- `0x18003319b`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CloudFilePolicy::UpdateCleanupList(unsigned __int16 *a1, int a2, char a3, __int64 a4, __int64 a5)
{
  struct _STORAGE_DEVICE_INFO *v8; // rdx
  int DriveNumberW; // r12d
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 **v12; // rdi
  __int64 *i; // rbx
  const WCHAR *v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // r9d
  const WCHAR *v18; // rsi
  int SyncRootInfoByPath; // eax
  bool v20; // zf
  int v22; // [rsp+20h] [rbp-E0h]
  _BYTE v23[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v24; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v25; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v26; // [rsp+4Ch] [rbp-B4h] BYREF
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+54h] [rbp-ACh] BYREF
  int v29; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h]
  const WCHAR *v31; // [rsp+68h] [rbp-98h] BYREF
  __int128 v32; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h]
  _QWORD v34[3]; // [rsp+90h] [rbp-70h] BYREF
  int v35; // [rsp+A8h] [rbp-58h]
  _BYTE v36[512]; // [rsp+ACh] [rbp-54h] BYREF
  _BYTE v37[512]; // [rsp+2ACh] [rbp+1ACh] BYREF
  int v38; // [rsp+4ACh] [rbp+3ACh]
  char v39; // [rsp+4B0h] [rbp+3B0h]
  int v40; // [rsp+4B1h] [rbp+3B1h]
  __int16 v41; // [rsp+4B5h] [rbp+3B5h]
  char v42; // [rsp+4B7h] [rbp+3B7h]
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+408h]

  v30 = a4;
  v28 = 0;
  v24 = 0;
  DriveNumberW = PathGetDriveNumberW(a1);
  v32 = 0;
  v33 = 0;
  if ( DriveNumberW == -1 )
  {
    v10 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FF,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)0x80070057LL,
      v22);
  }
  else
  {
    if ( (a3 & 2) != 0 )
    {
      CloudFilePolicy::DehydrationReason = 4;
    }
    else if ( (a3 & 1) != 0 )
    {
      CloudFilePolicy::DehydrationReason = 1;
    }
    else if ( (a3 & 8) != 0 )
    {
      CloudFilePolicy::DehydrationReason = 3;
      v27 = 0;
      v26 = 2;
      v25 = 31;
      GetStorageDeviceInfoByPathName(a1, v8, (enum _STORAGE_DEVICE_TYPE *)&v26, &v25);
      StorageService::GetStorageDeviceLowDiskState2(v11, v26, v25, 0, &v27, 0, 0);
      if ( v27 == 1 )
        CloudFilePolicy::DehydrationReason = 2;
    }
    else
    {
      CloudFilePolicy::DehydrationReason = 0;
    }
    v12 = *(__int64 ***)(a5 + 8);
    for ( i = *v12; i != (__int64 *)v12; i = (__int64 *)*i )
    {
      v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 6);
      if ( (int)StorageService::GetStoragePolicySettings(v15, 1u, v14, &v28) >= 0
        && v28
        && (int)StorageService::GetStoragePolicySettings(v16, 7u, v14, (int *)&v24) >= 0
        && v24 )
      {
        if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
        {
          v27 = CloudFilePolicy::DehydrationReason;
          v26 = v24;
          v25 = v28 != 0;
          v31 = v14;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800BF000,
            (unsigned int)&dword_1800A7C34,
            v30 + 8,
            v17,
            (__int64)&v31,
            (__int64)&v25,
            (__int64)&v26,
            (__int64)&v27);
        }
        v24 *= 24;
        v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
        if ( PathGetDriveNumberW(v18) == DriveNumberW )
        {
          memset(v34, 0, sizeof(v34));
          v35 = 0;
          memset_0(v36, 0, sizeof(v36));
          memset_0(v37, 0, sizeof(v37));
          v38 = 0;
          v39 = 0;
          v40 = 0;
          v41 = 0;
          v42 = 0;
          v29 = 0;
          AutoRpcImpersonateClient(v23);
          SyncRootInfoByPath = CfGetSyncRootInfoByPath(v18, 1, v34, 1064, &v29);
          if ( ((int)(SyncRootInfoByPath + 0x80000000) < 0 || SyncRootInfoByPath == -2147024662)
            && v35
            && (unsigned int)(v35 + 0x3FFFFFFF) > 1
            && (v35 & 0x40) == 0 )
          {
            *((_BYTE *)i + 80) = 1;
            Util::RecursiveScanRootFolder(1, (_DWORD)v18, v24, a2, (__int64)&v32, a5);
          }
          v20 = v23[0] == 0;
          v23[0] = 0;
          if ( !v20 )
            RpcRevertToSelf();
        }
      }
    }
    v10 = 0;
  }
  std::vector<std::wstring>::_Tidy(&v32);
  return v10;
}

```

## disassembly

```asm
0x180033118  mov     [rsp-8+arg_10], rbx
0x18003311d  push    rbp
0x18003311e  push    rsi
0x18003311f  push    rdi
0x180033120  push    r12
0x180033122  push    r13
0x180033124  push    r14
0x180033126  push    r15
0x180033128  lea     rbp, [rsp-3D0h]
0x180033130  sub     rsp, 4D0h
0x180033137  mov     rax, cs:__security_cookie
0x18003313e  xor     rax, rsp
0x180033141  mov     [rbp+400h+var_40], rax
0x180033148  mov     [rsp+500h+var_4A0], r9
0x18003314d  mov     ebx, r8d
0x180033150  mov     r13, rdx
0x180033153  mov     rdi, rcx
0x180033156  mov     r15, [rbp+400h+arg_20]
0x18003315d  mov     [rsp+500h+var_4AC], 0
0x180033165  mov     [rsp+500h+var_4BC], 0
0x18003316d  call    cs:__imp_PathGetDriveNumberW
0x180033173  mov     r12d, eax
0x180033176  xorps   xmm0, xmm0
0x180033179  movdqu  [rsp+500h+var_490], xmm0
0x18003317f  mov     [rbp+400h+var_480], 0
0x180033187  cmp     eax, 0FFFFFFFFh
0x18003318a  jnz     short loc_1800331B1
0x18003318c  mov     rcx, [rbp+408h]; this
0x180033193  mov     ebx, 80070057h
0x180033198  mov     r9d, ebx; char *
0x18003319b  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x1800331a2  mov     edx, 2FFh; void *
0x1800331a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800331ac  jmp     loc_180033479
0x1800331b1  mov     esi, 2
0x1800331b6  test    sil, bl
0x1800331b9  jz      short loc_1800331CA
0x1800331bb  mov     cs:?DehydrationReason@CloudFilePolicy@@2W4CF_DEHYDRATE_REASON@@A, 4; CF_DEHYDRATE_REASON CloudFilePolicy::DehydrationReason
0x1800331c5  jmp     loc_180033256
0x1800331ca  test    bl, 1
0x1800331cd  jz      short loc_1800331DB
0x1800331cf  mov     cs:?DehydrationReason@CloudFilePolicy@@2W4CF_DEHYDRATE_REASON@@A, 1; CF_DEHYDRATE_REASON CloudFilePolicy::DehydrationReason
0x1800331d9  jmp     short loc_180033256
0x1800331db  test    bl, 8
0x1800331de  jz      short loc_18003324C
0x1800331e0  mov     cs:?DehydrationReason@CloudFilePolicy@@2W4CF_DEHYDRATE_REASON@@A, 3; CF_DEHYDRATE_REASON CloudFilePolicy::DehydrationReason
0x1800331ea  mov     [rsp+500h+var_4B0], 0
0x1800331f2  mov     [rsp+500h+var_4B4], esi
0x1800331f6  mov     [rsp+500h+var_4B8], 1Fh
0x1800331fe  lea     r9, [rsp+500h+var_4B8]; unsigned int *
0x180033203  lea     r8, [rsp+500h+var_4B4]; enum _STORAGE_DEVICE_TYPE *
0x180033208  mov     rcx, rdi; unsigned __int16 *
0x18003320b  call    ?GetStorageDeviceInfoByPathName@@YAJPEBGPEAU_STORAGE_DEVICE_INFO@@PEAW4_STORAGE_DEVICE_TYPE@@PEAK@Z; GetStorageDeviceInfoByPathName(ushort const *,_STORAGE_DEVICE_INFO *,_STORAGE_DEVICE_TYPE *,ulong *)
0x180033210  mov     [rsp+500h+var_4D0], 0
0x180033219  mov     [rsp+500h+var_4D8], 0
0x180033222  lea     rax, [rsp+500h+var_4B0]
0x180033227  mov     [rsp+500h+var_4E0], rax
0x18003322c  xor     r9d, r9d
0x18003322f  mov     r8d, [rsp+500h+var_4B8]
0x180033234  mov     edx, [rsp+500h+var_4B4]
0x180033238  call    ?GetStorageDeviceLowDiskState2@StorageService@@QEAAJW4_STORAGE_DEVICE_TYPE@@KHPEAHPEA_K2@Z; StorageService::GetStorageDeviceLowDiskState2(_STORAGE_DEVICE_TYPE,ulong,int,int *,unsigned __int64 *,unsigned __int64 *)
0x18003323d  cmp     [rsp+500h+var_4B0], 1
0x180033242  jnz     short loc_180033256
0x180033244  mov     cs:?DehydrationReason@CloudFilePolicy@@2W4CF_DEHYDRATE_REASON@@A, esi; CF_DEHYDRATE_REASON CloudFilePolicy::DehydrationReason
0x18003324a  jmp     short loc_180033256
0x18003324c  mov     cs:?DehydrationReason@CloudFilePolicy@@2W4CF_DEHYDRATE_REASON@@A, 0; CF_DEHYDRATE_REASON CloudFilePolicy::DehydrationReason
0x180033256  mov     rdi, [r15+8]
0x18003325a  mov     rbx, [rdi]
0x18003325d  cmp     rbx, rdi
0x180033260  jz      loc_180033477
0x180033266  lea     rcx, [rbx+30h]
0x18003326a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003326f  mov     rsi, rax
0x180033272  lea     r9, [rsp+500h+var_4AC]
0x180033277  mov     r8, rax
0x18003327a  mov     edx, 1
0x18003327f  call    ?GetStoragePolicySettings@StorageService@@QEAAJW4_STORAGE_POLICY@@PEBGPEAK@Z; StorageService::GetStoragePolicySettings(_STORAGE_POLICY,ushort const *,ulong *)
0x180033284  test    eax, eax
0x180033286  js      loc_18003342E
0x18003328c  cmp     [rsp+500h+var_4AC], 0
0x180033291  jz      loc_18003342E
0x180033297  lea     r9, [rsp+500h+var_4BC]
0x18003329c  mov     r8, rsi
0x18003329f  mov     edx, 7
0x1800332a4  call    ?GetStoragePolicySettings@StorageService@@QEAAJW4_STORAGE_POLICY@@PEBGPEAK@Z; StorageService::GetStoragePolicySettings(_STORAGE_POLICY,ushort const *,ulong *)
0x1800332a9  test    eax, eax
0x1800332ab  js      loc_18003342E
0x1800332b1  cmp     [rsp+500h+var_4BC], 0
0x1800332b6  jz      loc_18003342E
0x1800332bc  mov     eax, cs:dword_1800BF000
0x1800332c2  cmp     eax, 5
0x1800332c5  jbe     loc_18003334E
0x1800332cb  mov     rdx, 400000000000h
0x1800332d5  lea     rcx, dword_1800BF000
0x1800332dc  call    _tlgKeywordOn
0x1800332e1  test    al, al
0x1800332e3  jz      short loc_18003334E
0x1800332e5  mov     eax, cs:?DehydrationReason@CloudFilePolicy@@2W4CF_DEHYDRATE_REASON@@A; CF_DEHYDRATE_REASON CloudFilePolicy::DehydrationReason
0x1800332eb  mov     [rsp+500h+var_4B0], eax
0x1800332ef  mov     eax, [rsp+500h+var_4BC]
0x1800332f3  mov     [rsp+500h+var_4B4], eax
0x1800332f7  xor     eax, eax
0x1800332f9  cmp     [rsp+500h+var_4AC], 1
0x1800332fe  setnb   al
0x180033301  mov     [rsp+500h+var_4B8], eax
0x180033305  mov     [rsp+500h+var_498], rsi
0x18003330a  mov     r8, [rsp+500h+var_4A0]
0x18003330f  add     r8, 8
0x180033313  lea     rax, [rsp+500h+var_4B0]
0x180033318  mov     [rsp+500h+var_4C8], rax
0x18003331d  lea     rax, [rsp+500h+var_4B4]
0x180033322  mov     [rsp+500h+var_4D0], rax
0x180033327  lea     rax, [rsp+500h+var_4B8]
0x18003332c  mov     [rsp+500h+var_4D8], rax
0x180033331  lea     rax, [rsp+500h+var_498]
0x180033336  mov     [rsp+500h+var_4E0], rax
0x18003333b  lea     rdx, dword_1800A7C34
0x180033342  lea     rcx, dword_1800BF000
0x180033349  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003334e  mov     eax, [rsp+500h+var_4BC]
0x180033352  lea     ecx, [rax+rax*2]
0x180033355  shl     ecx, 3
0x180033358  mov     [rsp+500h+var_4BC], ecx
0x18003335c  lea     rcx, [rbx+10h]
0x180033360  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180033365  mov     rsi, rax
0x180033368  mov     rcx, rax; pszPath
0x18003336b  call    cs:__imp_PathGetDriveNumberW
0x180033371  cmp     eax, r12d
0x180033374  jnz     loc_18003342E
0x18003337a  mov     [rbp+400h+var_470], 0
0x180033382  xor     ecx, ecx
0x180033384  mov     [rbp+400h+var_468], rcx
0x180033388  xor     eax, eax
0x18003338a  mov     [rbp+400h+var_460], rax
0x18003338e  mov     [rbp+400h+var_458], eax
0x180033391  xor     edx, edx; Val
0x180033393  mov     r8d, 200h; Size
0x180033399  lea     rcx, [rbp+400h+var_454]; void *
0x18003339d  call    memset_0
0x1800333a2  xor     edx, edx; Val
0x1800333a4  mov     r8d, 200h; Size
0x1800333aa  lea     rcx, [rbp+400h+var_254]; void *
0x1800333b1  call    memset_0
0x1800333b6  xor     eax, eax
0x1800333b8  mov     [rbp+400h+var_54], eax
0x1800333be  mov     [rbp+400h+var_50], al
0x1800333c4  mov     [rbp+400h+var_4F], eax
0x1800333ca  mov     [rbp+400h+var_4B], ax
0x1800333d1  mov     [rbp+400h+var_49], al
0x1800333d7  mov     [rsp+500h+var_4A8], eax
0x1800333db  lea     rcx, [rsp+500h+var_4C0]
0x1800333e0  call    ?AutoRpcImpersonateClient@@YA?AV?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@XZ; AutoRpcImpersonateClient(void)
0x1800333e5  nop
0x1800333e6  lea     rax, [rsp+500h+var_4A8]
0x1800333eb  mov     [rsp+500h+var_4E0], rax
0x1800333f0  mov     r9d, 428h
0x1800333f6  lea     r8, [rbp+400h+var_470]
0x1800333fa  mov     edx, 1
0x1800333ff  mov     rcx, rsi
0x180033402  call    cs:__imp_CfGetSyncRootInfoByPath
0x180033408  mov     edx, 80000000h
0x18003340d  lea     ecx, [rax+rdx]
0x180033410  test    edx, ecx
0x180033412  jnz     short loc_180033436
0x180033414  cmp     eax, 800700EAh
0x180033419  jz      short loc_180033436
0x18003341b  mov     al, [rsp+500h+var_4C0]
0x18003341f  test    al, al
0x180033421  mov     [rsp+500h+var_4C0], 0
0x180033426  jz      short loc_18003342E
0x180033428  call    cs:__imp_RpcRevertToSelf
0x18003342e  mov     rbx, [rbx]
0x180033431  jmp     loc_18003325D
0x180033436  mov     ecx, [rbp+400h+var_458]
0x180033439  test    ecx, ecx
0x18003343b  jz      short loc_18003341B
0x18003343d  lea     eax, [rcx+3FFFFFFFh]
0x180033443  cmp     eax, 1
0x180033446  jbe     short loc_18003341B
0x180033448  test    cl, 40h
0x18003344b  jnz     short loc_18003341B
0x18003344d  mov     byte ptr [rbx+50h], 1
0x180033451  mov     [rsp+500h+var_4D8], r15
0x180033456  lea     rax, [rsp+500h+var_490]
0x18003345b  mov     [rsp+500h+var_4E0], rax
0x180033460  mov     r9, r13
0x180033463  mov     r8d, [rsp+500h+var_4BC]
0x180033468  mov     rdx, rsi
0x18003346b  mov     ecx, 1
0x180033470  call    Util__RecursiveScanRootFolder
0x180033475  jmp     short loc_18003341B
0x180033477  xor     ebx, ebx
0x180033479  lea     rcx, [rsp+500h+var_490]
0x18003347e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180033483  mov     eax, ebx
0x180033485  mov     rcx, [rbp+400h+var_40]
0x18003348c  xor     rcx, rsp; StackCookie
0x18003348f  call    __security_check_cookie
0x180033494  mov     rbx, [rsp+500h+arg_10]
0x18003349c  add     rsp, 4D0h
0x1800334a3  pop     r15
0x1800334a5  pop     r14
0x1800334a7  pop     r13
0x1800334a9  pop     r12
0x1800334ab  pop     rdi
0x1800334ac  pop     rsi
0x1800334ad  pop     rbp
0x1800334ae  retn
```
