# UserOOBECreateElevatedObjectHandlerServer::_IsRequestApproved(_GUID const &)

- ea: `0x18002bd20`
- end: `0x18002bea9`
- name: `?_IsRequestApproved@UserOOBECreateElevatedObjectHandlerServer@@EEAA_NAEBU_GUID@@@Z`
- size: `393`
- prototype: `char __fastcall(const unsigned __int16 **this, struct _GUID *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800032b0`
- `0x180004200`
- `0x180007710`
- `0x18000a5c8`
- `0x18000c150`
- `0x18000d738`
- `0x18000e2bc`
- `0x18000e580`
- `0x18002ba90`
- `0x18002bd20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002bd92`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002bd92`

## string_xrefs

- `0x18002bda7`: `shell\oobe\user\dll\useroobeelevatedbroker.cpp`
- `0x18002bdfe`: `shell\oobe\user\dll\useroobeelevatedbroker.cpp`
- `0x18002be5a`: `shell\oobe\user\dll\useroobeelevatedbroker.cpp`

## pseudocode

```c
char __fastcall UserOOBECreateElevatedObjectHandlerServer::_IsRequestApproved(
        const unsigned __int16 **this,
        struct _GUID *a2)
{
  char v4; // bl
  HRESULT v5; // eax
  int v6; // eax
  unsigned int v7; // r9d
  unsigned int BOOLWithREGSAM; // eax
  int v11; // [rsp+20h] [rbp-248h]
  int v12; // [rsp+20h] [rbp-248h]
  int v13; // [rsp+20h] [rbp-248h]
  int v14; // [rsp+30h] [rbp-238h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-230h] BYREF
  unsigned __int16 v16[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v14 = 0;
  if ( !IsClsidApproved(a2, this[2]) )
    return 0;
  v4 = 1;
  if ( !IsUserOOBE() )
  {
    lpsz = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpsz,
      0);
    v5 = StringFromCLSID(a2, &lpsz);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x27,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobeelevatedbroker.cpp",
        (const char *)(unsigned int)v5,
        v11);
    memset_0(v16, 0, 0x208u);
    v12 = (int)lpsz;
    v6 = StringCchPrintfW(v16, 0x104u, L"%s\\%s", this[2]);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x29,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobeelevatedbroker.cpp",
        (const char *)(unsigned int)v6,
        v12);
    BOOLWithREGSAM = SHRegGetBOOLWithREGSAM(HKEY_LOCAL_MACHINE, v16, L"AutoElevationAllowed", v7, &v14);
    if ( (int)(BOOLWithREGSAM + 0x80000000) >= 0 && BOOLWithREGSAM != -2147024894 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobeelevatedbroker.cpp",
        (const char *)BOOLWithREGSAM,
        v13);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
    if ( !v14 )
      return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18002bd20  mov     [rsp+arg_10], rbx
0x18002bd25  mov     [rsp+arg_18], rsi
0x18002bd2a  push    rdi
0x18002bd2b  sub     rsp, 260h
0x18002bd32  mov     rax, cs:__security_cookie
0x18002bd39  xor     rax, rsp
0x18002bd3c  mov     [rsp+268h+var_18], rax
0x18002bd44  mov     rdi, rdx
0x18002bd47  mov     rsi, rcx
0x18002bd4a  mov     [rsp+268h+var_238], 0
0x18002bd52  mov     rdx, [rcx+10h]; unsigned __int16 *
0x18002bd56  mov     rcx, rdi; rclsid
0x18002bd59  call    ?IsClsidApproved@@YA_NAEBU_GUID@@PEBG@Z; IsClsidApproved(_GUID const &,ushort const *)
0x18002bd5e  test    al, al
0x18002bd60  jz      loc_18002BE80
0x18002bd66  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x18002bd6b  mov     bl, 1
0x18002bd6d  test    al, al
0x18002bd6f  jnz     loc_18002BE82
0x18002bd75  mov     [rsp+268h+lpsz], 0
0x18002bd7e  xor     edx, edx
0x18002bd80  lea     rcx, [rsp+268h+lpsz]
0x18002bd85  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002bd8a  lea     rdx, [rsp+268h+lpsz]; lplpsz
0x18002bd8f  mov     rcx, rdi; rclsid
0x18002bd92  call    cs:__imp_StringFromCLSID
0x18002bd98  mov     rcx, [rsp+268h]; this
0x18002bda0  test    eax, eax
0x18002bda2  jns     short loc_18002BDB9
0x18002bda4  mov     r9d, eax; char *
0x18002bda7  lea     r8, aShellOobeUserD_2; "shell\\oobe\\user\\dll\\useroobeelevate"...
0x18002bdae  mov     edx, 27h ; '''; void *
0x18002bdb3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002bdb9  xor     edx, edx; Val
0x18002bdbb  mov     r8d, 208h; Size
0x18002bdc1  lea     rcx, [rsp+268h+var_228]; void *
0x18002bdc6  call    memset_0
0x18002bdcb  mov     rax, [rsp+268h+lpsz]
0x18002bdd0  mov     qword ptr [rsp+268h+var_248], rax; int
0x18002bdd5  mov     r9, [rsi+10h]
0x18002bdd9  lea     r8, aSS_0; "%s\\%s"
0x18002bde0  mov     edx, 104h; unsigned __int64
0x18002bde5  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18002bdea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bdef  mov     rcx, [rsp+268h]; this
0x18002bdf7  test    eax, eax
0x18002bdf9  jns     short loc_18002BE10
0x18002bdfb  mov     r9d, eax; char *
0x18002bdfe  lea     r8, aShellOobeUserD_2; "shell\\oobe\\user\\dll\\useroobeelevate"...
0x18002be05  mov     edx, 29h ; ')'; void *
0x18002be0a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002be10  lea     rax, [rsp+268h+var_238]
0x18002be15  mov     qword ptr [rsp+268h+var_248], rax; int
0x18002be1a  lea     r8, aAutoelevationa; "AutoElevationAllowed"
0x18002be21  lea     rdx, [rsp+268h+var_228]; unsigned __int16 *
0x18002be26  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18002be2d  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18002be32  mov     edx, 80000000h
0x18002be37  lea     ecx, [rax+rdx]
0x18002be3a  test    edx, ecx
0x18002be3c  jnz     short loc_18002BE49
0x18002be3e  cmp     eax, 80070002h
0x18002be43  jz      short loc_18002BE49
0x18002be45  mov     cl, bl
0x18002be47  jmp     short loc_18002BE4B
0x18002be49  xor     cl, cl
0x18002be4b  mov     r10, [rsp+268h]
0x18002be53  test    cl, cl
0x18002be55  jz      short loc_18002BE6F
0x18002be57  mov     r9d, eax; char *
0x18002be5a  lea     r8, aShellOobeUserD_2; "shell\\oobe\\user\\dll\\useroobeelevate"...
0x18002be61  mov     edx, 2Bh ; '+'; void *
0x18002be66  mov     rcx, r10; this
0x18002be69  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002be6f  lea     rcx, [rsp+268h+lpsz]
0x18002be74  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002be79  cmp     [rsp+268h+var_238], 0
0x18002be7e  jnz     short loc_18002BE82
0x18002be80  xor     bl, bl
0x18002be82  mov     al, bl
0x18002be84  mov     rcx, [rsp+268h+var_18]
0x18002be8c  xor     rcx, rsp; StackCookie
0x18002be8f  call    __security_check_cookie
0x18002be94  lea     r11, [rsp+268h+var_8]
0x18002be9c  mov     rbx, [r11+20h]
0x18002bea0  mov     rsi, [r11+28h]
0x18002bea4  mov     rsp, r11
0x18002bea7  pop     rdi
0x18002bea8  retn
```
