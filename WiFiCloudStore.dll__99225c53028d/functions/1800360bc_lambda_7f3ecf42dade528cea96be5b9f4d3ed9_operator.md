# _lambda_7f3ecf42dade528cea96be5b9f4d3ed9_::operator()

- ea: `0x1800360bc`
- end: `0x180036237`
- name: `_lambda_7f3ecf42dade528cea96be5b9f4d3ed9_::operator()`
- size: `379`
- prototype: `__int64 __fastcall(wil::filetime *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180035984`

## callees

- `0x180006420`
- `0x180007f90`
- `0x180013ef0`
- `0x18002a030`
- `0x18002e2d0`
- `0x180032c10`
- `0x1800360bc`
- `0x18003c170`
- `0x18003d4d8`

## string_xrefs

- `0x180036225`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`

## pseudocode

```c
__int64 __fastcall lambda_7f3ecf42dade528cea96be5b9f4d3ed9_::operator()(wil::filetime *a1)
{
  _QWORD *v2; // rax
  int v3; // edi
  int v4; // esi
  __int64 v5; // rbx
  int v6; // eax
  int v8; // [rsp+20h] [rbp-49h]
  _BYTE v9[4]; // [rsp+50h] [rbp-19h] BYREF
  int v10; // [rsp+54h] [rbp-15h] BYREF
  int v11; // [rsp+58h] [rbp-11h] BYREF
  int v12; // [rsp+5Ch] [rbp-Dh] BYREF
  int v13; // [rsp+60h] [rbp-9h] BYREF
  int v14; // [rsp+64h] [rbp-5h] BYREF
  int v15; // [rsp+68h] [rbp-1h] BYREF
  BYTE v16[4]; // [rsp+70h] [rbp+7h] BYREF
  struct _FILETIME system_time; // [rsp+74h] [rbp+Bh]
  int v18[8]; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v9[0] = 0;
  *(_DWORD *)v16 = 1;
  system_time = wil::filetime::get_system_time(a1);
  v2 = (_QWORD *)*((_QWORD *)a1 + 3);
  v3 = *((_DWORD *)v2 + 11);
  v4 = *((_DWORD *)v2 + 10);
  v5 = **((_QWORD **)a1 + 1) + 532LL * **((unsigned int **)a1 + 2);
  std::wstring::wstring(v18, **(_QWORD **)a1);
  Windows::Internal::WiFiCloudStore::SetRetryCountForProfile((int)v18, v5 + 8, v4, v3, v16);
  std::wstring::~wstring(v18);
  v6 = Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry(
         *((_QWORD *)a1 + 4),
         ***((void ****)a1 + 5),
         **(_QWORD **)a1,
         (_DWORD *)(*((_QWORD *)a1 + 3) + 32LL),
         *(_DWORD *)(*((_QWORD *)a1 + 3) + 40LL),
         *(_DWORD *)(*((_QWORD *)a1 + 3) + 44LL),
         v9);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x211,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
      (const char *)(unsigned int)v6,
      v8);
  v10 = 16;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  return WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const * &,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int,int,int,int,int,enum WiFiSyncAction>(
           *((_QWORD *)a1 + 6),
           *(_QWORD *)a1,
           *((_QWORD *)a1 + 7),
           (unsigned int)&v15,
           (__int64)&v14,
           (__int64)&v13,
           (__int64)&v12,
           (__int64)&v11,
           (__int64)&v10);
}

```

## disassembly

```asm
0x1800360bc  mov     [rsp-8+arg_8], rbx
0x1800360c1  mov     [rsp-8+arg_10], rsi
0x1800360c6  push    rbp
0x1800360c7  push    rdi
0x1800360c8  push    r14
0x1800360ca  lea     rbp, [rsp-47h]
0x1800360cf  sub     rsp, 0B0h
0x1800360d6  mov     rax, cs:__security_cookie
0x1800360dd  xor     rax, rsp
0x1800360e0  mov     [rbp+57h+var_20], rax
0x1800360e4  mov     r14, rcx
0x1800360e7  mov     [rbp+57h+var_70], 0
0x1800360eb  mov     dword ptr [rbp+57h+var_50], 1
0x1800360f2  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x1800360f7  mov     [rbp+57h+var_4C], rax
0x1800360fb  mov     rax, [r14+18h]
0x1800360ff  mov     edi, [rax+2Ch]
0x180036102  mov     esi, [rax+28h]
0x180036105  mov     rax, [r14+10h]
0x180036109  mov     ecx, [rax]
0x18003610b  imul    rbx, rcx, 214h
0x180036112  mov     rax, [r14+8]
0x180036116  add     rbx, [rax]
0x180036119  mov     rdx, [r14]
0x18003611c  mov     rdx, [rdx]
0x18003611f  lea     rcx, [rbp+57h+var_40]
0x180036123  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180036128  nop
0x180036129  lea     rax, [rbp+57h+var_50]
0x18003612d  mov     [rsp+0C0h+var_A0], rax; BYTE *
0x180036132  mov     r9d, edi; int
0x180036135  mov     r8d, esi; int
0x180036138  lea     rdx, [rbx+8]; int
0x18003613c  lea     rcx, [rbp+57h+var_40]; int
0x180036140  call    ?SetRetryCountForProfile@WiFiCloudStore@Internal@Windows@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@AEBURetryStatistics@123@@Z; Windows::Internal::WiFiCloudStore::SetRetryCountForProfile(std::wstring const &,_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,Windows::Internal::WiFiCloudStore::RetryStatistics const &)
0x180036145  nop
0x180036146  lea     rcx, [rbp+57h+var_40]
0x18003614a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003614f  mov     rcx, [r14+18h]
0x180036153  lea     r9, [rcx+20h]
0x180036157  mov     r8, [r14]
0x18003615a  mov     rax, [r14+28h]
0x18003615e  mov     rdx, [rax]
0x180036161  lea     rax, [rbp+57h+var_70]
0x180036165  mov     [rsp+0C0h+var_90], rax
0x18003616a  mov     eax, [rcx+2Ch]
0x18003616d  mov     dword ptr [rsp+0C0h+var_98], eax
0x180036171  mov     eax, [rcx+28h]
0x180036174  mov     dword ptr [rsp+0C0h+var_A0], eax; int
0x180036178  mov     r8, [r8]
0x18003617b  mov     rdx, [rdx]
0x18003617e  mov     rcx, [r14+20h]
0x180036182  call    ?StoreSyncNeededProfileInRegistry@WiFiCloudStore@Internal@Windows@@YAJAEBU_GUID@@QEAXPEBGAEBU_FILETIME@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEA_N@Z; Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry(_GUID const &,void * const,ushort const *,_FILETIME const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,bool *)
0x180036187  test    eax, eax
0x180036189  js      loc_18003621E
0x18003618f  mov     [rbp+57h+var_6C], 10h
0x180036196  mov     [rbp+57h+var_68], 0
0x18003619d  mov     [rbp+57h+var_64], 0
0x1800361a4  mov     [rbp+57h+var_60], 0
0x1800361ab  mov     [rbp+57h+var_5C], 0
0x1800361b2  mov     [rbp+57h+var_58], 0
0x1800361b9  lea     rax, [rbp+57h+var_6C]
0x1800361bd  mov     [rsp+0C0h+var_80], rax
0x1800361c2  lea     rax, [rbp+57h+var_68]
0x1800361c6  mov     [rsp+0C0h+var_88], rax
0x1800361cb  lea     rax, [rbp+57h+var_64]
0x1800361cf  mov     [rsp+0C0h+var_90], rax
0x1800361d4  lea     rax, [rbp+57h+var_60]
0x1800361d8  mov     [rsp+0C0h+var_98], rax
0x1800361dd  lea     rax, [rbp+57h+var_5C]
0x1800361e1  mov     [rsp+0C0h+var_A0], rax
0x1800361e6  lea     r9, [rbp+57h+var_58]
0x1800361ea  mov     r8, [r14+38h]
0x1800361ee  mov     rdx, [r14]
0x1800361f1  mov     rcx, [r14+30h]
0x1800361f5  call    ??$ActionTakenOnWiFiProfile@AEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@HHHHHW4WiFiSyncAction@@@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAXAEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@$$QEAH2222$$QEAW4WiFiSyncAction@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<ushort const * &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int,int,int,int,int,WiFiSyncAction>(ushort const * &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int &&,int &&,int &&,int &&,int &&,WiFiSyncAction &&)
0x1800361fa  mov     rcx, [rbp+57h+var_20]
0x1800361fe  xor     rcx, rsp; StackCookie
0x180036201  call    __security_check_cookie
0x180036206  lea     r11, [rsp+0C0h+var_10]
0x18003620e  mov     rbx, [r11+28h]
0x180036212  mov     rsi, [r11+30h]
0x180036216  mov     rsp, r11
0x180036219  pop     r14
0x18003621b  pop     rdi
0x18003621c  pop     rbp
0x18003621d  retn
0x18003621e  mov     rcx, [rbp+5Fh]; this
0x180036222  mov     r9d, eax; char *
0x180036225  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18003622c  mov     edx, 211h; void *
0x180036231  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
