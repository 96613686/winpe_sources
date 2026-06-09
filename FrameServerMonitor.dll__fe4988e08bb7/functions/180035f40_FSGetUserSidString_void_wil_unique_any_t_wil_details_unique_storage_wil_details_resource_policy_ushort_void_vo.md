# FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180035f40`
- end: `0x180036046`
- name: `?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(__int64, LPWSTR *)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180036cb8`
- `0x18003ce10`
- `0x18003dd10`
- `0x18003e1a0`

## callees

- `0x1800060f8`
- `0x180006a98`
- `0x18000d1e0`
- `0x18000d240`
- `0x180035f40`
- `0x18003604c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035fea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035fea`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180035fe0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180035fe0`

## pseudocode

```c
__int64 __fastcall FSGetUserSidString(__int64 a1, LPWSTR *a2)
{
  signed int v3; // ebx
  __int64 v4; // rdx
  signed int LastError; // eax
  PSID *v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    a2,
    0);
  v3 = FSGetUserToken_Internal((HANDLE)0xFFFFFFFFFFFFFFFBLL);
  if ( v3 == -2147023888 )
  {
    v3 = FSGetUserToken_Internal((HANDLE)0xFFFFFFFFFFFFFFFCLL);
    if ( v3 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v4 = 36;
LABEL_14:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v3);
        goto LABEL_15;
      }
      goto LABEL_15;
    }
LABEL_8:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a2,
      0);
    if ( !ConvertSidToStringSidW(*v7, a2) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v4 = 39;
        goto LABEL_14;
      }
    }
    goto LABEL_15;
  }
  if ( v3 >= 0 )
    goto LABEL_8;
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v4 = 37;
    goto LABEL_14;
  }
LABEL_15:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180035f40  mov     rax, rsp
0x180035f43  mov     [rax+10h], rbx
0x180035f47  mov     [rax+8], rcx
0x180035f4b  push    rdi
0x180035f4c  sub     rsp, 30h
0x180035f50  mov     rdi, rdx
0x180035f53  mov     qword ptr [rax+18h], 0
0x180035f5b  mov     rcx, rdi
0x180035f5e  mov     dword ptr [rax+8], 0
0x180035f65  xor     edx, edx
0x180035f67  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180035f6c  lea     r8, [rsp+38h+arg_0]
0x180035f71  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x180035f78  lea     rdx, [rsp+38h+arg_10]
0x180035f7d  call    ?FSGetUserToken_Internal@@YAJPEAXAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@AEAK@Z; FSGetUserToken_Internal(void *,wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &,ulong &)
0x180035f82  mov     ebx, eax
0x180035f84  cmp     eax, 800703F0h
0x180035f89  jnz     short loc_180035FB7
0x180035f8b  lea     r8, [rsp+38h+arg_0]
0x180035f90  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x180035f97  lea     rdx, [rsp+38h+arg_10]
0x180035f9c  call    ?FSGetUserToken_Internal@@YAJPEAXAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@AEAK@Z; FSGetUserToken_Internal(void *,wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &,ulong &)
0x180035fa1  mov     ebx, eax
0x180035fa3  test    eax, eax
0x180035fa5  jns     short loc_180035FCB
0x180035fa7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180035fac  cmp     al, 1
0x180035fae  jb      short loc_18003602F
0x180035fb0  mov     edx, 24h ; '$'
0x180035fb5  jmp     short loc_180036011
0x180035fb7  test    ebx, ebx
0x180035fb9  jns     short loc_180035FCB
0x180035fbb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180035fc0  cmp     al, 1
0x180035fc2  jb      short loc_18003602F
0x180035fc4  mov     edx, 25h ; '%'
0x180035fc9  jmp     short loc_180036011
0x180035fcb  xor     edx, edx
0x180035fcd  mov     rcx, rdi
0x180035fd0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180035fd5  mov     rcx, [rsp+38h+arg_10]
0x180035fda  mov     rdx, rdi; StringSid
0x180035fdd  mov     rcx, [rcx]; Sid
0x180035fe0  call    cs:__imp_ConvertSidToStringSidW
0x180035fe6  test    eax, eax
0x180035fe8  jnz     short loc_18003602F
0x180035fea  call    cs:__imp_GetLastError
0x180035ff0  mov     ebx, eax
0x180035ff2  test    eax, eax
0x180035ff4  jle     short loc_180035FFF
0x180035ff6  movzx   ebx, ax
0x180035ff9  or      ebx, 80070000h
0x180035fff  test    ebx, ebx
0x180036001  jns     short loc_18003602F
0x180036003  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180036008  cmp     al, 1
0x18003600a  jb      short loc_18003602F
0x18003600c  mov     edx, 27h ; '''
0x180036011  mov     rcx, cs:WPP_GLOBAL_Control
0x180036018  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003601f  xor     r9d, r9d
0x180036022  mov     [rsp+38h+var_18], ebx
0x180036026  mov     rcx, [rcx+10h]
0x18003602a  call    WPP_SF_qD
0x18003602f  lea     rcx, [rsp+38h+arg_10]
0x180036034  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180036039  mov     eax, ebx
0x18003603b  mov     rbx, [rsp+38h+arg_8]
0x180036040  add     rsp, 30h
0x180036044  pop     rdi
0x180036045  retn
```
