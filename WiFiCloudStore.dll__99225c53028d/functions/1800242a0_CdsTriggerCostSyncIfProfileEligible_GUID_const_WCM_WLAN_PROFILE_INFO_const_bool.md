# CdsTriggerCostSyncIfProfileEligible(_GUID const *,WCM_WLAN_PROFILE_INFO * const,bool)

- ea: `0x1800242a0`
- end: `0x18002455d`
- name: `?CdsTriggerCostSyncIfProfileEligible@@YAJPEBU_GUID@@QEAUWCM_WLAN_PROFILE_INFO@@_N@Z`
- size: `701`
- prototype: `__int64 __fastcall(const struct _GUID *, struct WCM_WLAN_PROFILE_INFO *const, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18002e580`

## callees

- `0x18001c92c`
- `0x1800242a0`
- `0x18002477c`
- `0x180024c14`
- `0x18003c170`
- `0x18003c954`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024346`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024346`
- `wlanapi!WlanFreeMemory` at `0x1800243df`
- `wlanapi!WlanFreeMemory` at `0x18002442e`
- `wlanapi!WlanFreeMemory` at `0x1800244af`
- `wlanapi!WlanFreeMemory` at `0x1800244fc`
- `wlanapi!WlanFreeMemory` at `0x180024515`
- `wlanapi!WlanFreeMemory` at `0x1800243df`
- `wlanapi!WlanFreeMemory` at `0x18002442e`
- `wlanapi!WlanFreeMemory` at `0x1800244af`
- `wlanapi!WlanFreeMemory` at `0x1800244fc`
- `wlanapi!WlanFreeMemory` at `0x180024515`
- `wlanapi!WlanGetProfileMetadata` at `0x180024398`
- `wlanapi!WlanGetProfileMetadata` at `0x180024398`

## string_xrefs

- `0x180024388`: `CreatorSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CdsTriggerCostSyncIfProfileEligible(
        const struct _GUID *a1,
        struct WCM_WLAN_PROFILE_INFO *const a2,
        unsigned __int8 a3)
{
  int v3; // r14d
  int v6; // r9d
  int v7; // edx
  char *v8; // rdi
  unsigned int ProfileMetadata; // ebx
  unsigned int v10; // ebx
  PVOID v11; // rcx
  PVOID v13; // rcx
  PVOID v14; // rdx
  int v15; // eax
  unsigned int v16; // ebx
  PVOID v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
  PVOID v20; // rcx
  PVOID v21; // rcx
  unsigned int v22; // [rsp+20h] [rbp-68h]
  int v23; // [rsp+20h] [rbp-68h]
  PVOID pMemory; // [rsp+40h] [rbp-48h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-40h] BYREF
  _QWORD v26[2]; // [rsp+50h] [rbp-38h] BYREF
  char v27; // [rsp+60h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  int v29; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v30; // [rsp+A8h] [rbp+20h] BYREF

  v3 = a3;
  if ( *((_QWORD *)a2 + 68) )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3F,
             (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\triggercloudsynconcostchange.cpp",
             (const char *)0x32,
             v22);
  v6 = *((_DWORD *)a2 + 149);
  v7 = *((_DWORD *)a2 + 148);
  if ( ((unsigned int)(v7 - 1) > 1 || v6 != 257 && v6) && ((unsigned int)(v7 - 4) > 1 || ((v6 - 2) & 0xFFFFFFFD) != 0) )
  {
    if ( v7 == 7 )
    {
      if ( ((v6 - 2) & 0xFFFFFFF9) == 0 && v6 != 6 )
        goto LABEL_12;
    }
    else if ( (unsigned int)(v7 - 9) <= 1 )
    {
      goto LABEL_12;
    }
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3F,
             (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\triggercloudsynconcostchange.cpp",
             (const char *)0x32,
             v22);
  }
LABEL_12:
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v30 = 0;
  pMemory = 0;
  v26[0] = &pMemory;
  v26[1] = 0;
  v27 = 1;
  v8 = (char *)a2 + 16;
  ProfileMetadata = WlanGetProfileMetadata(a1, (char *)a2 + 16, 0, L"CreatorSid");
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>(v26);
  if ( (ProfileMetadata & 0xFFFFFFFD) != 0 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4C,
            (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\triggercloudsynconcostchange.cpp",
            (const char *)ProfileMetadata,
            (unsigned int)&v30);
    v11 = pMemory;
    pMemory = 0;
    if ( v11 )
      WlanFreeMemory(v11);
    return v10;
  }
  else if ( !v30 || pMemory )
  {
    v14 = 0;
    if ( ProfileMetadata != 2 )
      v14 = pMemory;
    LOBYTE(v29) = 0;
    v15 = Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry(
            (__int64)a1,
            v14,
            (__int64)v8,
            &SystemTimeAsFileTime,
            4 * v3 + 4,
            0x80000000,
            &v29);
    v16 = v15;
    if ( v15 >= 0 )
    {
      if ( (_BYTE)v29 && (v18 = Windows::Internal::WiFiCloudStore::TriggerTaskWithDelay(), v19 = v18, v18 < 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\triggercloudsynconcostchange.cpp",
          (const char *)(unsigned int)v18,
          v23);
        v20 = pMemory;
        pMemory = 0;
        if ( v20 )
          WlanFreeMemory(v20);
        return v19;
      }
      else
      {
        v21 = pMemory;
        pMemory = 0;
        if ( v21 )
          WlanFreeMemory(v21);
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\triggercloudsynconcostchange.cpp",
        (const char *)(unsigned int)v15,
        v23);
      v17 = pMemory;
      pMemory = 0;
      if ( v17 )
        WlanFreeMemory(v17);
      return v16;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\triggercloudsynconcostchange.cpp",
      (const char *)0x80070057LL,
      (int)&v30);
    v13 = pMemory;
    pMemory = 0;
    if ( v13 )
      WlanFreeMemory(v13);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800242a0  mov     [rsp+arg_0], rbx
0x1800242a5  mov     [rsp+arg_10], rsi
0x1800242aa  push    rdi
0x1800242ab  push    r14
0x1800242ad  push    r15
0x1800242af  sub     rsp, 70h
0x1800242b3  movzx   r14d, r8b
0x1800242b7  mov     rbx, rdx
0x1800242ba  mov     rsi, rcx
0x1800242bd  xor     r15d, r15d
0x1800242c0  cmp     [rdx+224h], r15d
0x1800242c7  jnz     loc_18002451F
0x1800242cd  cmp     [rdx+220h], r15d
0x1800242d4  jnz     loc_18002451F
0x1800242da  mov     r9d, [rdx+254h]
0x1800242e1  mov     edx, [rdx+250h]
0x1800242e7  lea     eax, [rdx-1]
0x1800242ea  cmp     eax, 1
0x1800242ed  ja      short loc_1800242FD
0x1800242ef  cmp     r9d, 101h
0x1800242f6  jz      short loc_18002433C
0x1800242f8  test    r9d, r9d
0x1800242fb  jz      short loc_18002433C
0x1800242fd  lea     eax, [rdx-4]
0x180024300  cmp     eax, 1
0x180024303  ja      short loc_180024310
0x180024305  lea     eax, [r9-2]
0x180024309  test    eax, 0FFFFFFFDh
0x18002430e  jz      short loc_18002433C
0x180024310  cmp     edx, 7
0x180024313  jnz     short loc_180024330
0x180024315  lea     eax, [r9-2]
0x180024319  test    eax, 0FFFFFFF9h
0x18002431e  jnz     loc_18002451F
0x180024324  cmp     r9d, 6
0x180024328  jz      loc_18002451F
0x18002432e  jmp     short loc_18002433C
0x180024330  lea     eax, [rdx-9]
0x180024333  cmp     eax, 1
0x180024336  ja      loc_18002451F
0x18002433c  mov     qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180024341  lea     rcx, [rsp+88h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180024346  call    cs:__imp_GetSystemTimeAsFileTime
0x18002434c  mov     [rsp+88h+arg_18], r15d
0x180024354  mov     [rsp+88h+pMemory], r15
0x180024359  lea     rax, [rsp+88h+pMemory]
0x18002435e  mov     [rsp+88h+var_38], rax
0x180024363  mov     [rsp+88h+var_30], r15
0x180024368  mov     [rsp+88h+var_28], 1
0x18002436d  lea     rdi, [rbx+10h]
0x180024371  lea     rax, [rsp+88h+var_30]
0x180024376  mov     [rsp+88h+var_60], rax
0x18002437b  lea     rax, [rsp+88h+arg_18]
0x180024383  mov     qword ptr [rsp+88h+var_68], rax; int
0x180024388  lea     r9, aCreatorsid; "CreatorSid"
0x18002438f  xor     r8d, r8d
0x180024392  mov     rdx, rdi
0x180024395  mov     rcx, rsi
0x180024398  call    cs:__imp_WlanGetProfileMetadata
0x18002439e  mov     ebx, eax
0x1800243a0  lea     rcx, [rsp+88h+var_38]
0x1800243a5  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x1800243aa  test    ebx, 0FFFFFFFDh
0x1800243b0  jz      short loc_1800243EC
0x1800243b2  mov     rcx, [rsp+88h]; this
0x1800243ba  mov     r9d, ebx; char *
0x1800243bd  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800243c4  mov     edx, 4Ch ; 'L'; void *
0x1800243c9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800243ce  mov     ebx, eax
0x1800243d0  mov     rcx, [rsp+88h+pMemory]; pMemory
0x1800243d5  mov     [rsp+88h+pMemory], r15
0x1800243da  test    rcx, rcx
0x1800243dd  jz      short loc_1800243E5
0x1800243df  call    cs:__imp_WlanFreeMemory
0x1800243e5  mov     eax, ebx
0x1800243e7  jmp     loc_180024546
0x1800243ec  mov     rax, [rsp+88h+pMemory]
0x1800243f1  cmp     [rsp+88h+arg_18], r15d
0x1800243f9  jz      short loc_18002443B
0x1800243fb  test    rax, rax
0x1800243fe  jnz     short loc_18002443B
0x180024400  mov     rcx, [rsp+88h]; this
0x180024408  mov     ebx, 80070057h
0x18002440d  mov     r9d, ebx; char *
0x180024410  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180024417  lea     edx, [rax+51h]; void *
0x18002441a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002441f  mov     rcx, [rsp+88h+pMemory]; pMemory
0x180024424  mov     [rsp+88h+pMemory], r15
0x180024429  test    rcx, rcx
0x18002442c  jz      short loc_180024434
0x18002442e  call    cs:__imp_WlanFreeMemory
0x180024434  mov     eax, ebx
0x180024436  jmp     loc_180024546
0x18002443b  mov     rdx, r15
0x18002443e  cmp     ebx, 2
0x180024441  cmovnz  rdx, rax
0x180024445  mov     byte ptr [rsp+88h+arg_8], r15b
0x18002444d  lea     eax, ds:4[r14*4]
0x180024455  lea     rcx, [rsp+88h+arg_8]
0x18002445d  mov     [rsp+88h+var_58], rcx
0x180024462  mov     dword ptr [rsp+88h+var_60], 80000000h
0x18002446a  mov     [rsp+88h+var_68], eax; int
0x18002446e  lea     r9, [rsp+88h+SystemTimeAsFileTime]
0x180024473  mov     r8, rdi
0x180024476  mov     rcx, rsi
0x180024479  call    ?StoreSyncNeededProfileInRegistry@WiFiCloudStore@Internal@Windows@@YAJAEBU_GUID@@QEAXPEBGAEBU_FILETIME@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEA_N@Z; Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry(_GUID const &,void * const,ushort const *,_FILETIME const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,bool *)
0x18002447e  mov     ebx, eax
0x180024480  test    eax, eax
0x180024482  jns     short loc_1800244BC
0x180024484  mov     rcx, [rsp+88h]; this
0x18002448c  mov     r9d, eax; char *
0x18002448f  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180024496  mov     edx, 62h ; 'b'; void *
0x18002449b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800244a0  mov     rcx, [rsp+88h+pMemory]; pMemory
0x1800244a5  mov     [rsp+88h+pMemory], r15
0x1800244aa  test    rcx, rcx
0x1800244ad  jz      short loc_1800244B5
0x1800244af  call    cs:__imp_WlanFreeMemory
0x1800244b5  mov     eax, ebx
0x1800244b7  jmp     loc_180024546
0x1800244bc  cmp     byte ptr [rsp+88h+arg_8], r15b
0x1800244c4  jz      short loc_180024506
0x1800244c6  call    ?TriggerTaskWithDelay@WiFiCloudStore@Internal@Windows@@YAJW4TaskTrigger@123@@Z; Windows::Internal::WiFiCloudStore::TriggerTaskWithDelay(Windows::Internal::WiFiCloudStore::TaskTrigger)
0x1800244cb  mov     ebx, eax
0x1800244cd  test    eax, eax
0x1800244cf  jns     short loc_180024506
0x1800244d1  mov     rcx, [rsp+88h]; this
0x1800244d9  mov     r9d, eax; char *
0x1800244dc  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800244e3  mov     edx, 66h ; 'f'; void *
0x1800244e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800244ed  mov     rcx, [rsp+88h+pMemory]; pMemory
0x1800244f2  mov     [rsp+88h+pMemory], r15
0x1800244f7  test    rcx, rcx
0x1800244fa  jz      short loc_180024502
0x1800244fc  call    cs:__imp_WlanFreeMemory
0x180024502  mov     eax, ebx
0x180024504  jmp     short loc_180024546
0x180024506  mov     rcx, [rsp+88h+pMemory]; pMemory
0x18002450b  mov     [rsp+88h+pMemory], r15
0x180024510  test    rcx, rcx
0x180024513  jz      short loc_18002451B
0x180024515  call    cs:__imp_WlanFreeMemory
0x18002451b  xor     eax, eax
0x18002451d  jmp     short loc_180024546
0x18002451f  mov     rcx, [rsp+88h]; this
0x180024527  mov     r9d, 32h ; '2'; char *
0x18002452d  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180024534  lea     edx, [r9+0Dh]; void *
0x180024538  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002453d  jmp     short loc_180024546
0x18002453f  mov     eax, [rsp+88h+arg_8]
0x180024546  lea     r11, [rsp+88h+var_18]
0x18002454b  mov     rbx, [r11+20h]
0x18002454f  mov     rsi, [r11+30h]
0x180024553  mov     rsp, r11
0x180024556  pop     r15
0x180024558  pop     r14
0x18002455a  pop     rdi
0x18002455b  retn
```
