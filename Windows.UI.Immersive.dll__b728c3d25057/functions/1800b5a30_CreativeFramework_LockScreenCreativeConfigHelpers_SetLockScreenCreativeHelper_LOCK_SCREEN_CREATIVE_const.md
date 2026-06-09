# CreativeFramework::LockScreenCreativeConfigHelpers::SetLockScreenCreativeHelper(LOCK_SCREEN_CREATIVE const &)

- ea: `0x1800b5a30`
- end: `0x1800b5b7f`
- name: `?SetLockScreenCreativeHelper@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJAEBULOCK_SCREEN_CREATIVE@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(CreativeFramework::LockScreenCreativeConfigHelpers *__hidden this, const struct LOCK_SCREEN_CREATIVE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b59f4`

## callees

- `0x180009ce4`
- `0x18000bb20`
- `0x18000bd60`
- `0x180034db4`
- `0x180039e34`
- `0x18003aa84`
- `0x1800b5a30`
- `0x1800b862c`
- `0x1800b87b8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b5b20`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b5b20`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b5b12`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b5b12`
- `ntdll!RtlPublishWnfStateData` at `0x1800b5b3f`
- `ntdll!RtlPublishWnfStateData` at `0x1800b5b3f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800b5ad5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800b5ad5`

## string_xrefs

- `0x1800b5a57`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x1800b5aad`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x1800b5af2`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreativeFramework::LockScreenCreativeConfigHelpers::SetLockScreenCreativeHelper(
        CreativeFramework::LockScreenCreativeConfigHelpers *this,
        const struct LOCK_SCREEN_CREATIVE *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  unsigned __int16 **v5; // rdx
  int CurrentUserSidString; // eax
  const unsigned __int16 *v7; // r8
  __int64 v8; // rdx
  int Error; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  DWORD LengthSid; // eax
  int v13; // eax
  int v15; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  PSID Sid; // [rsp+48h] [rbp+18h] BYREF
  LPCWSTR StringSid; // [rsp+50h] [rbp+20h] BYREF

  v3 = CreativeFramework::LockScreenCreativeConfigHelpers::WriteCreativeToRegistry(this, a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    CurrentUserSidString = CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(
                             (CreativeFramework::LockScreenCreativeConfigHelpers *)&StringSid,
                             v5);
    v4 = CurrentUserSidString;
    if ( CurrentUserSidString >= 0 )
    {
      CurrentUserSidString = CreativeFramework::LockScreenCreativeConfigHelpers::WriteCreativeToMachineRegistry(
                               this,
                               (const struct LOCK_SCREEN_CREATIVE *)StringSid,
                               v7);
      v4 = CurrentUserSidString;
      if ( CurrentUserSidString >= 0 )
      {
        Sid = 0;
        if ( ConvertStringSidToSidW(StringSid, &Sid) || (Error = ResultFromKnownLastError(), v4 = Error, Error >= 0) )
        {
          if ( !IsValidSid(Sid)
            || (LengthSid = GetLengthSid(Sid),
                v13 = RtlPublishWnfStateData(WNF_SHEL_LOCKSCREEN_IMAGE_CHANGED, 0, Sid, LengthSid, 0),
                v4 = v13 | 0x10000000,
                v13 >= 0) )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
            v4 = 0;
            goto LABEL_16;
          }
          v10 = v4;
          v11 = 268;
        }
        else
        {
          v10 = (unsigned int)Error;
          v11 = 260;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
          (const char *)v10,
          v15);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
LABEL_16:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
        return v4;
      }
      v8 = 257;
    }
    else
    {
      v8 = 256;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
      (const char *)(unsigned int)CurrentUserSidString,
      v15);
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xFD,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
    (const char *)(unsigned int)v3,
    v15);
  return v4;
}

```

## disassembly

```asm
0x1800b5a30  mov     [rsp-8+arg_0], rbx
0x1800b5a35  mov     [rsp-8+arg_18], rdi
0x1800b5a3a  push    rbp
0x1800b5a3b  mov     rbp, rsp
0x1800b5a3e  sub     rsp, 30h
0x1800b5a42  mov     rdi, rcx
0x1800b5a45  call    ?WriteCreativeToRegistry@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBULOCK_SCREEN_CREATIVE@@@Z; CreativeFramework::LockScreenCreativeConfigHelpers::WriteCreativeToRegistry(LOCK_SCREEN_CREATIVE const *)
0x1800b5a4a  mov     ebx, eax
0x1800b5a4c  test    eax, eax
0x1800b5a4e  jns     short loc_1800B5A6D
0x1800b5a50  mov     rcx, [rbp+8]; this
0x1800b5a54  mov     r9d, eax; char *
0x1800b5a57  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x1800b5a5e  mov     edx, 0FDh; void *
0x1800b5a63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5a68  jmp     loc_1800B5B6D
0x1800b5a6d  mov     [rbp+StringSid], 0
0x1800b5a75  xor     edx, edx
0x1800b5a77  lea     rcx, [rbp+StringSid]
0x1800b5a7b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800b5a80  lea     rcx, [rbp+StringSid]; this
0x1800b5a84  call    ?GetCurrentUserSidString@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEAPEAG@Z; CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(ushort * *)
0x1800b5a89  mov     ebx, eax
0x1800b5a8b  test    eax, eax
0x1800b5a8d  jns     short loc_1800B5A96
0x1800b5a8f  mov     edx, 100h
0x1800b5a94  jmp     short loc_1800B5AAD
0x1800b5a96  mov     rdx, [rbp+StringSid]; struct LOCK_SCREEN_CREATIVE *
0x1800b5a9a  mov     rcx, rdi; this
0x1800b5a9d  call    ?WriteCreativeToMachineRegistry@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBULOCK_SCREEN_CREATIVE@@PEBG@Z; CreativeFramework::LockScreenCreativeConfigHelpers::WriteCreativeToMachineRegistry(LOCK_SCREEN_CREATIVE const *,ushort const *)
0x1800b5aa2  mov     ebx, eax
0x1800b5aa4  test    eax, eax
0x1800b5aa6  jns     short loc_1800B5AC5
0x1800b5aa8  mov     edx, 101h; void *
0x1800b5aad  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x1800b5ab4  mov     r9d, eax; char *
0x1800b5ab7  mov     rcx, [rbp+8]; this
0x1800b5abb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5ac0  jmp     loc_1800B5B64
0x1800b5ac5  mov     [rbp+Sid], 0
0x1800b5acd  lea     rdx, [rbp+Sid]; Sid
0x1800b5ad1  mov     rcx, [rbp+StringSid]; StringSid
0x1800b5ad5  call    cs:__imp_ConvertStringSidToSidW
0x1800b5adb  test    eax, eax
0x1800b5add  jnz     short loc_1800B5B0E
0x1800b5adf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b5ae4  mov     ebx, eax
0x1800b5ae6  test    eax, eax
0x1800b5ae8  jns     short loc_1800B5B0E
0x1800b5aea  mov     r9d, eax; char *
0x1800b5aed  mov     edx, 104h; void *
0x1800b5af2  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x1800b5af9  mov     rcx, [rbp+8]; this
0x1800b5afd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5b02  nop
0x1800b5b03  lea     rcx, [rbp+Sid]
0x1800b5b07  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b5b0c  jmp     short loc_1800B5B64
0x1800b5b0e  mov     rcx, [rbp+Sid]; pSid
0x1800b5b12  call    cs:__imp_IsValidSid
0x1800b5b18  test    eax, eax
0x1800b5b1a  jz      short loc_1800B5B59
0x1800b5b1c  mov     rcx, [rbp+Sid]; pSid
0x1800b5b20  call    cs:__imp_GetLengthSid
0x1800b5b26  mov     qword ptr [rsp+30h+var_10], 0
0x1800b5b2f  mov     r9d, eax
0x1800b5b32  mov     r8, [rbp+Sid]
0x1800b5b36  xor     edx, edx
0x1800b5b38  mov     rcx, cs:WNF_SHEL_LOCKSCREEN_IMAGE_CHANGED
0x1800b5b3f  call    cs:__imp_RtlPublishWnfStateData
0x1800b5b45  mov     ebx, eax
0x1800b5b47  or      ebx, 10000000h
0x1800b5b4d  jge     short loc_1800B5B59
0x1800b5b4f  mov     r9d, ebx
0x1800b5b52  mov     edx, 10Ch
0x1800b5b57  jmp     short loc_1800B5AF2
0x1800b5b59  lea     rcx, [rbp+Sid]
0x1800b5b5d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b5b62  xor     ebx, ebx
0x1800b5b64  lea     rcx, [rbp+StringSid]
0x1800b5b68  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800b5b6d  mov     eax, ebx
0x1800b5b6f  mov     rbx, [rsp+30h+arg_0]
0x1800b5b74  mov     rdi, [rsp+30h+arg_18]
0x1800b5b79  add     rsp, 30h
0x1800b5b7d  pop     rbp
0x1800b5b7e  retn
```
