# FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18002ed08`
- end: `0x18002ee16`
- name: `?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180030f00`
- `0x1800378a0`
- `0x180038790`
- `0x180038c20`

## callees

- `0x180009608`
- `0x180017a3c`
- `0x180017a64`
- `0x18002ed08`
- `0x18002ee1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edba`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002edb0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002edb0`

## pseudocode

```c
__int64 __fastcall FSGetUserSidString(__int64 a1, LPWSTR *a2)
{
  int v3; // eax
  signed int v4; // ebx
  __int64 v5; // rdx
  signed int LastError; // eax
  DWORD v8; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+44h] [rbp+Ch]
  PSID *v10; // [rsp+50h] [rbp+18h] BYREF

  v9 = HIDWORD(a1);
  v10 = 0;
  v8 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    a2,
    0);
  v3 = FSGetUserToken_Internal((HANDLE)0xFFFFFFFFFFFFFFFBLL, (void **)&v10, &v8);
  v4 = v3;
  if ( v3 != -2147023888 )
  {
    if ( v3 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_15;
      v5 = 37;
      goto LABEL_5;
    }
    goto LABEL_9;
  }
  v3 = FSGetUserToken_Internal((HANDLE)0xFFFFFFFFFFFFFFFCLL, (void **)&v10, &v8);
  v4 = v3;
  if ( v3 >= 0 )
  {
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a2,
      0);
    if ( !ConvertSidToStringSidW(*v10, a2) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 < 0 && g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v4);
    }
    goto LABEL_15;
  }
  if ( g_wppLevels )
  {
    v5 = 36;
LABEL_5:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v3);
  }
LABEL_15:
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002ed08  mov     rax, rsp
0x18002ed0b  mov     [rax+10h], rbx
0x18002ed0f  mov     [rax+8], rcx
0x18002ed13  push    rdi
0x18002ed14  sub     rsp, 30h
0x18002ed18  mov     rdi, rdx
0x18002ed1b  mov     qword ptr [rax+18h], 0
0x18002ed23  mov     rcx, rdi
0x18002ed26  mov     dword ptr [rax+8], 0
0x18002ed2d  xor     edx, edx
0x18002ed2f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002ed34  lea     r8, [rsp+38h+arg_0]
0x18002ed39  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18002ed40  lea     rdx, [rsp+38h+arg_10]
0x18002ed45  call    ?FSGetUserToken_Internal@@YAJPEAXAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@AEAK@Z; FSGetUserToken_Internal(void *,wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &,ulong &)
0x18002ed4a  mov     ebx, eax
0x18002ed4c  cmp     eax, 800703F0h
0x18002ed51  jnz     short loc_18002ED87
0x18002ed53  lea     r8, [rsp+38h+arg_0]
0x18002ed58  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x18002ed5f  lea     rdx, [rsp+38h+arg_10]
0x18002ed64  call    ?FSGetUserToken_Internal@@YAJPEAXAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@AEAK@Z; FSGetUserToken_Internal(void *,wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &,ulong &)
0x18002ed69  mov     ebx, eax
0x18002ed6b  test    eax, eax
0x18002ed6d  jns     short loc_18002ED9B
0x18002ed6f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002ed76  jb      loc_18002EDFF
0x18002ed7c  mov     edx, 24h ; '$'
0x18002ed81  mov     [rsp+38h+var_18], eax
0x18002ed85  jmp     short loc_18002EDE5
0x18002ed87  test    eax, eax
0x18002ed89  jns     short loc_18002ED9B
0x18002ed8b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002ed92  jb      short loc_18002EDFF
0x18002ed94  mov     edx, 25h ; '%'
0x18002ed99  jmp     short loc_18002ED81
0x18002ed9b  xor     edx, edx
0x18002ed9d  mov     rcx, rdi
0x18002eda0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002eda5  mov     rcx, [rsp+38h+arg_10]
0x18002edaa  mov     rdx, rdi; StringSid
0x18002edad  mov     rcx, [rcx]; Sid
0x18002edb0  call    cs:__imp_ConvertSidToStringSidW
0x18002edb6  test    eax, eax
0x18002edb8  jnz     short loc_18002EDFF
0x18002edba  call    cs:__imp_GetLastError
0x18002edc0  mov     ebx, eax
0x18002edc2  test    eax, eax
0x18002edc4  jle     short loc_18002EDCF
0x18002edc6  movzx   ebx, ax
0x18002edc9  or      ebx, 80070000h
0x18002edcf  test    ebx, ebx
0x18002edd1  jns     short loc_18002EDFF
0x18002edd3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002edda  jb      short loc_18002EDFF
0x18002eddc  mov     edx, 27h ; '''
0x18002ede1  mov     [rsp+38h+var_18], ebx
0x18002ede5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002edec  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18002edf3  xor     r9d, r9d
0x18002edf6  mov     rcx, [rcx+10h]
0x18002edfa  call    WPP_SF_qD
0x18002edff  lea     rcx, [rsp+38h+arg_10]
0x18002ee04  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18002ee09  mov     eax, ebx
0x18002ee0b  mov     rbx, [rsp+38h+arg_8]
0x18002ee10  add     rsp, 30h
0x18002ee14  pop     rdi
0x18002ee15  retn
```
