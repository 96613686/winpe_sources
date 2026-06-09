# CConnectedUser::InitializeConnectedAADUser(void *)

- ea: `0x180018ac4`
- end: `0x180018b95`
- name: `?InitializeConnectedAADUser@CConnectedUser@@QEAAJPEAX@Z`
- size: `209`
- prototype: `__int64 __fastcall(CConnectedUser *this, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016400`
- `0x180016718`

## callees

- `0x18000e530`
- `0x18000f034`
- `0x180015900`
- `0x180018ac4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b46`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018ae2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018ae2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018b3c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018b3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018b1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018b1d`

## pseudocode

```c
__int64 __fastcall CConnectedUser::InitializeConnectedAADUser(CConnectedUser *this, void *a2)
{
  DWORD LengthSid; // ebp
  __int64 *unique_hlocal; // rax
  __int64 v6; // rdx
  HLOCAL v7; // rcx
  PSID v8; // rdi
  unsigned int v9; // ebx
  signed int LastError; // eax
  PSID pDestinationSid; // [rsp+50h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp+20h] BYREF

  pDestinationSid = 0;
  LengthSid = GetLengthSid(a2);
  unique_hlocal = wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, LengthSid);
  v6 = *unique_hlocal;
  *unique_hlocal = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pDestinationSid,
    v6);
  v7 = hMem;
  hMem = 0;
  if ( v7 )
    LocalFree(v7);
  v8 = pDestinationSid;
  if ( pDestinationSid )
  {
    if ( CopySid(LengthSid, pDestinationSid, a2) )
    {
      v9 = 0;
      pDestinationSid = 0;
      *(_OWORD *)((char *)this + 68) = xmmword_18001E7E0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        (char *)this + 96,
        v8);
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v9 = -2147024882;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pDestinationSid);
  return v9;
}

```

## disassembly

```asm
0x180018ac4  mov     [rsp+arg_0], rbx
0x180018ac9  push    rbp
0x180018aca  push    rsi
0x180018acb  push    rdi
0x180018acc  sub     rsp, 20h
0x180018ad0  mov     rsi, rcx
0x180018ad3  mov     [rsp+38h+pDestinationSid], 0
0x180018adc  mov     rcx, rdx; pSid
0x180018adf  mov     rbx, rdx
0x180018ae2  call    cs:__imp_GetLengthSid
0x180018ae8  mov     edx, eax
0x180018aea  lea     rcx, [rsp+38h+hMem]
0x180018aef  mov     ebp, eax
0x180018af1  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180018af6  lea     rcx, [rsp+38h+pDestinationSid]
0x180018afb  mov     rdx, [rax]
0x180018afe  mov     qword ptr [rax], 0
0x180018b05  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180018b0a  mov     rcx, [rsp+38h+hMem]; hMem
0x180018b0f  mov     [rsp+38h+hMem], 0
0x180018b18  test    rcx, rcx
0x180018b1b  jz      short loc_180018B23
0x180018b1d  call    cs:__imp_LocalFree
0x180018b23  mov     rdi, [rsp+38h+pDestinationSid]
0x180018b28  test    rdi, rdi
0x180018b2b  jnz     short loc_180018B34
0x180018b2d  mov     ebx, 8007000Eh
0x180018b32  jmp     short loc_180018B7C
0x180018b34  mov     r8, rbx; pSourceSid
0x180018b37  mov     rdx, rdi; pDestinationSid
0x180018b3a  mov     ecx, ebp; nDestinationSidLength
0x180018b3c  call    cs:__imp_CopySid
0x180018b42  test    eax, eax
0x180018b44  jnz     short loc_180018B5D
0x180018b46  call    cs:__imp_GetLastError
0x180018b4c  mov     ebx, eax
0x180018b4e  test    eax, eax
0x180018b50  jle     short loc_180018B7C
0x180018b52  movzx   ebx, ax
0x180018b55  or      ebx, 80070000h
0x180018b5b  jmp     short loc_180018B7C
0x180018b5d  movups  xmm0, cs:xmmword_18001E7E0
0x180018b64  xor     ebx, ebx
0x180018b66  lea     rcx, [rsi+60h]
0x180018b6a  mov     rdx, rdi
0x180018b6d  mov     [rsp+38h+pDestinationSid], rbx
0x180018b72  movdqu  xmmword ptr [rsi+44h], xmm0
0x180018b77  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180018b7c  lea     rcx, [rsp+38h+pDestinationSid]
0x180018b81  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180018b86  mov     eax, ebx
0x180018b88  mov     rbx, [rsp+38h+arg_0]
0x180018b8d  add     rsp, 20h
0x180018b91  pop     rdi
0x180018b92  pop     rsi
0x180018b93  pop     rbp
0x180018b94  retn
```
