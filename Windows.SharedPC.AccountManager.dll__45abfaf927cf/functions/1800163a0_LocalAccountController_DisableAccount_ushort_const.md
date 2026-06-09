# LocalAccountController::DisableAccount(ushort const *)

- ea: `0x1800163a0`
- end: `0x180016458`
- name: `?DisableAccount@LocalAccountController@@UEAAJPEBG@Z`
- size: `184`
- prototype: `__int64 __fastcall(LocalAccountController *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800154ec`
- `0x1800163a0`
- `0x1800198d4`
- `0x1800237f0`

## import_xrefs

- `samcli!NetUserGetInfo` at `0x1800163bd`
- `samcli!NetUserGetInfo` at `0x1800163bd`
- `samcli!NetUserSetInfo` at `0x180016414`
- `samcli!NetUserSetInfo` at `0x180016414`

## string_xrefs

- `0x1800163d6`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`
- `0x18001642d`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LocalAccountController::DisableAccount(LocalAccountController *this, const unsigned __int16 *a2)
{
  DWORD Info; // eax
  int v4; // eax
  int v5; // ecx
  DWORD v6; // eax
  int v7; // eax
  const char *v8; // r9
  __int64 result; // rax
  int parm_err; // [rsp+20h] [rbp-18h]
  int parm_erra; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int buf; // [rsp+50h] [rbp+18h] BYREF
  LPBYTE bufptr; // [rsp+58h] [rbp+20h] BYREF

  bufptr = 0;
  Info = NetUserGetInfo(0, a2, 0x17u, &bufptr);
  v4 = NetpApiStatusToNtStatus(Info);
  try
  {
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0xA4,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
        (const char *)(unsigned int)v4,
        parm_err);
    v5 = *((_DWORD *)bufptr + 6);
    if ( (v5 & 2) == 0 )
    {
      buf = v5 | 2;
      v6 = NetUserSetInfo(0, a2, 0x3F0u, (LPBYTE)&buf, 0);
      v7 = NetpApiStatusToNtStatus(v6);
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0xAB,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
          (const char *)(unsigned int)v7,
          parm_erra);
    }
    wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_23 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_23 *,_USER_INFO_23 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_INFO_23 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_23 *,_USER_INFO_23 *,0,std::nullptr_t>>(&bufptr);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAF,
                           (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x1800163a0  push    rbx
0x1800163a2  sub     rsp, 30h
0x1800163a6  mov     rbx, rdx
0x1800163a9  mov     [rsp+38h+bufptr], 0
0x1800163b2  lea     r9, [rsp+38h+bufptr]; bufptr
0x1800163b7  xor     ecx, ecx; servername
0x1800163b9  lea     r8d, [rcx+17h]; level
0x1800163bd  call    cs:__imp_NetUserGetInfo
0x1800163c3  mov     ecx, eax
0x1800163c5  call    NetpApiStatusToNtStatus
0x1800163ca  mov     rcx, [rsp+38h]; this
0x1800163cf  test    eax, eax
0x1800163d1  jns     short loc_1800163E7
0x1800163d3  mov     r9d, eax; char *
0x1800163d6  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800163dd  mov     edx, 0A4h; void *
0x1800163e2  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800163e7  mov     rax, [rsp+38h+bufptr]
0x1800163ec  mov     ecx, [rax+18h]
0x1800163ef  test    cl, 2
0x1800163f2  jnz     short loc_18001643F
0x1800163f4  or      ecx, 2
0x1800163f7  mov     [rsp+38h+buf], ecx
0x1800163fb  mov     qword ptr [rsp+38h+parm_err], 0; int
0x180016404  lea     r9, [rsp+38h+buf]; buf
0x180016409  mov     r8d, 3F0h; level
0x18001640f  mov     rdx, rbx; username
0x180016412  xor     ecx, ecx; servername
0x180016414  call    cs:__imp_NetUserSetInfo
0x18001641a  mov     ecx, eax
0x18001641c  call    NetpApiStatusToNtStatus
0x180016421  mov     rcx, [rsp+38h]; this
0x180016426  test    eax, eax
0x180016428  jns     short loc_18001643F
0x18001642a  mov     r9d, eax; char *
0x18001642d  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180016434  mov     edx, 0ABh; void *
0x180016439  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18001643f  lea     rcx, [rsp+38h+bufptr]
0x180016444  call    ??1?$unique_storage@U?$resource_policy@PEAU_USER_INFO_23@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_23 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_23 *,_USER_INFO_23 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_INFO_23 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_23 *,_USER_INFO_23 *,0,std::nullptr_t>>(void)
0x180016449  xor     eax, eax
0x18001644b  jmp     short loc_180016451
0x18001644d  mov     eax, [rsp+38h+buf]
0x180016451  add     rsp, 30h
0x180016455  pop     rbx
0x180016456  retn
```
