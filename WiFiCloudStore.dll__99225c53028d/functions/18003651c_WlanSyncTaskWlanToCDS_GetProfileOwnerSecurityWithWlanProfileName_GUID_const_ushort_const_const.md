# WlanSyncTaskWlanToCDS::GetProfileOwnerSecurityWithWlanProfileName(_GUID const &,ushort const * const)

- ea: `0x18003651c`
- end: `0x1800365cf`
- name: `?GetProfileOwnerSecurityWithWlanProfileName@WlanSyncTaskWlanToCDS@@CA?AW4ProfileOwnerSecurity@WiFiCloudStore@Internal@Windows@@AEBU_GUID@@QEBG@Z`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800365d8`

## callees

- `0x180016118`
- `0x18001c92c`
- `0x180031ce4`
- `0x18003651c`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x1800365bc`
- `wlanapi!WlanFreeMemory` at `0x1800365bc`
- `wlanapi!WlanGetProfileMetadata` at `0x180036568`
- `wlanapi!WlanGetProfileMetadata` at `0x180036568`

## string_xrefs

- `0x18003655e`: `CreatorSid`
- `0x180036588`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WlanSyncTaskWlanToCDS::GetProfileOwnerSecurityWithWlanProfileName(__int64 a1, __int64 a2)
{
  unsigned int ProfileMetadata; // ebx
  PVOID v3; // rcx
  unsigned int OwnerSecurityOfSid; // ebx
  PVOID v5; // rcx
  _QWORD v7[2]; // [rsp+30h] [rbp-20h] BYREF
  char v8; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  unsigned int v10; // [rsp+70h] [rbp+20h] BYREF
  PVOID pMemory; // [rsp+78h] [rbp+28h] BYREF

  pMemory = 0;
  v10 = 0;
  v7[0] = &pMemory;
  v7[1] = 0;
  v8 = 1;
  ProfileMetadata = WlanGetProfileMetadata(a1, a2, 0, L"CreatorSid");
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)v7);
  if ( (ProfileMetadata & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x295,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
      (const char *)ProfileMetadata,
      (unsigned int)&v10);
  v3 = 0;
  if ( ProfileMetadata != 2 )
    v3 = pMemory;
  OwnerSecurityOfSid = Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(v3);
  v5 = pMemory;
  pMemory = 0;
  if ( v5 )
    WlanFreeMemory(v5);
  return OwnerSecurityOfSid;
}

```

## disassembly

```asm
0x18003651c  mov     [rsp-8+arg_0], rbx
0x180036521  push    rbp
0x180036522  mov     rbp, rsp
0x180036525  sub     rsp, 50h
0x180036529  mov     [rbp+pMemory], 0
0x180036531  mov     [rbp+arg_10], 0
0x180036538  lea     rax, [rbp+pMemory]
0x18003653c  mov     [rbp+var_20], rax
0x180036540  mov     [rbp+var_18], 0
0x180036548  mov     [rbp+var_10], 1
0x18003654c  lea     rax, [rbp+var_18]
0x180036550  mov     [rsp+50h+var_28], rax
0x180036555  lea     rax, [rbp+arg_10]
0x180036559  mov     qword ptr [rsp+50h+var_30], rax; unsigned int
0x18003655e  lea     r9, aCreatorsid; "CreatorSid"
0x180036565  xor     r8d, r8d
0x180036568  call    cs:__imp_WlanGetProfileMetadata
0x18003656e  mov     ebx, eax
0x180036570  lea     rcx, [rbp+var_20]
0x180036574  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x180036579  test    ebx, 0FFFFFFFDh
0x18003657f  jz      short loc_18003659A
0x180036581  mov     rcx, [rbp+8]; this
0x180036585  mov     r9d, ebx; char *
0x180036588  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18003658f  mov     edx, 295h; void *
0x180036594  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003659a  xor     ecx, ecx
0x18003659c  cmp     ebx, 2
0x18003659f  cmovnz  rcx, [rbp+pMemory]
0x1800365a4  call    ?GetOwnerSecurityOfSid@WiFiCloudStore@Internal@Windows@@YA?AW4ProfileOwnerSecurity@123@QEAX@Z; Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(void * const)
0x1800365a9  mov     ebx, eax
0x1800365ab  mov     rcx, [rbp+pMemory]; pMemory
0x1800365af  mov     [rbp+pMemory], 0
0x1800365b7  test    rcx, rcx
0x1800365ba  jz      short loc_1800365C2
0x1800365bc  call    cs:__imp_WlanFreeMemory
0x1800365c2  mov     eax, ebx
0x1800365c4  mov     rbx, [rsp+50h+arg_0]
0x1800365c9  add     rsp, 50h
0x1800365cd  pop     rbp
0x1800365ce  retn
```
