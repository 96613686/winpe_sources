# UserAwareCallerIdentity::GetCallingProcessAppId(ushort * *)

- ea: `0x18004e098`
- end: `0x18004e27f`
- name: `?GetCallingProcessAppId@UserAwareCallerIdentity@@YAJPEAPEAG@Z`
- size: `487`
- prototype: `__int64 __fastcall(UserAwareCallerIdentity *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180027d50`
- `0x1800374c8`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180027c60`
- `0x180027ce8`
- `0x18002b520`
- `0x180038c70`
- `0x18004e098`
- `0x18004e288`
- `0x180050f14`
- `0x18005ae90`
- `0x18005ba40`
- `0x18005e96c`
- `0x180074d24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e277`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e277`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18004e1a0`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18004e1a0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18004e180`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18004e180`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UserAwareCallerIdentity::GetCallingProcessAppId(
        UserAwareCallerIdentity *this,
        unsigned __int16 **a2)
{
  int CallingProcessAppId; // ebx
  unsigned int *v4; // rdx
  int CallingProcessId; // eax
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  int ApplicationUserModelIdFromToken; // eax
  int v9; // edx
  int v10; // ecx
  bool v11; // sf
  LPVOID v12; // rax
  int v14; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-C8h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+3Ch] [rbp-C4h] BYREF
  HANDLE token; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID *p_pv; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  char v21; // [rsp+58h] [rbp-A8h]
  WCHAR applicationUserModelId[136]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  *(_QWORD *)this = 0;
  pv = 0;
  p_pv = &pv;
  v20 = 0;
  v21 = 1;
  CallingProcessAppId = CallerIdentity::GetCallingProcessAppId((CallerIdentity *)&v20, a2);
  if ( v21 )
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      p_pv,
      v20);
  if ( CallingProcessAppId == -2147024891 )
  {
    if ( (unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent() )
    {
      v16 = 0;
      token = 0;
      memset_0(applicationUserModelId, 0, 0x106u);
      applicationUserModelIdLength = 131;
      CallingProcessId = UserAwareCallerIdentity::GetCallingProcessId((UserAwareCallerIdentity *)&v16, v4);
      CallingProcessAppId = CallingProcessId;
      if ( CallingProcessId < 0 )
      {
        v6 = (unsigned int)CallingProcessId;
        v7 = 79;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"onecoreuap\\internal\\base\\inc\\UserAwareCallerIdentity.h",
          (const char *)v6,
          v14);
        goto LABEL_15;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &token,
        0);
      ApplicationUserModelIdFromToken = UMgrOpenProcessTokenForQuery(v16, &token);
      if ( ApplicationUserModelIdFromToken < 0 )
        goto LABEL_8;
      ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                          token,
                                          &applicationUserModelIdLength,
                                          applicationUserModelId);
      v11 = ApplicationUserModelIdFromToken < 0;
      if ( ApplicationUserModelIdFromToken > 0 )
      {
        ApplicationUserModelIdFromToken = (unsigned __int16)ApplicationUserModelIdFromToken | 0x80070000;
        v11 = ApplicationUserModelIdFromToken < 0;
      }
      if ( v11 )
      {
LABEL_8:
        CallingProcessAppId = ApplicationUserModelIdFromToken;
LABEL_15:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
LABEL_18:
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
        return (unsigned int)CallingProcessAppId;
      }
      p_pv = &pv;
      v20 = 0;
      v21 = 1;
      CallingProcessAppId = _AllocStringWorker<CTCoAllocPolicy>(
                              v10,
                              v9,
                              (unsigned int)applicationUserModelId,
                              applicationUserModelIdLength);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
      if ( CallingProcessAppId < 0 )
      {
        v6 = (unsigned int)CallingProcessAppId;
        v7 = 82;
        goto LABEL_14;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
LABEL_17:
      v12 = pv;
      pv = 0;
      *(_QWORD *)this = v12;
      CallingProcessAppId = 0;
      goto LABEL_18;
    }
  }
  else if ( CallingProcessAppId >= 0 )
  {
    goto LABEL_17;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)CallingProcessAppId;
}

```

## disassembly

```asm
0x18004e098  mov     [rsp-8+arg_8], rbx
0x18004e09d  mov     [rsp-8+arg_10], rdi
0x18004e0a2  push    rbp
0x18004e0a3  lea     rbp, [rsp-80h]
0x18004e0a8  sub     rsp, 180h
0x18004e0af  mov     rax, cs:__security_cookie
0x18004e0b6  xor     rax, rsp
0x18004e0b9  mov     [rbp+80h+var_10], rax
0x18004e0bd  mov     rdi, rcx
0x18004e0c0  mov     qword ptr [rcx], 0
0x18004e0c7  mov     [rsp+180h+pv], 0
0x18004e0d0  lea     rax, [rsp+180h+pv]
0x18004e0d5  mov     [rsp+180h+var_138], rax
0x18004e0da  mov     [rsp+180h+var_130], 0
0x18004e0e3  mov     [rsp+180h+var_128], 1
0x18004e0e8  lea     rcx, [rsp+180h+var_130]; this
0x18004e0ed  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x18004e0f2  mov     ebx, eax
0x18004e0f4  cmp     [rsp+180h+var_128], 0
0x18004e0f9  jz      short loc_18004E10A
0x18004e0fb  mov     rdx, [rsp+180h+var_130]
0x18004e100  mov     rcx, [rsp+180h+var_138]
0x18004e105  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004e10a  cmp     ebx, 80070005h
0x18004e110  jnz     loc_18004E269
0x18004e116  call    IsUMgrOpenProcessHandleForAccessPresent
0x18004e11b  test    al, al
0x18004e11d  jz      loc_18004E26D
0x18004e123  mov     [rsp+180h+var_148], 0
0x18004e12b  mov     [rsp+180h+token], 0
0x18004e134  xor     edx, edx; Val
0x18004e136  mov     r8d, 106h; Size
0x18004e13c  lea     rcx, [rsp+180h+applicationUserModelId]; void *
0x18004e141  call    memset_0
0x18004e146  mov     [rsp+180h+applicationUserModelIdLength], 83h
0x18004e14e  lea     rcx, [rsp+180h+var_148]; this
0x18004e153  call    ?GetCallingProcessId@UserAwareCallerIdentity@@YAJPEAK@Z; UserAwareCallerIdentity::GetCallingProcessId(ulong *)
0x18004e158  mov     ebx, eax
0x18004e15a  test    eax, eax
0x18004e15c  jns     short loc_18004E16B
0x18004e15e  mov     r9d, eax
0x18004e161  mov     edx, 4Fh ; 'O'
0x18004e166  jmp     loc_18004E1FF
0x18004e16b  xor     edx, edx
0x18004e16d  lea     rcx, [rsp+180h+token]
0x18004e172  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004e177  lea     rdx, [rsp+180h+token]
0x18004e17c  mov     ecx, [rsp+180h+var_148]
0x18004e180  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x18004e186  test    eax, eax
0x18004e188  jns     short loc_18004E191
0x18004e18a  mov     ebx, eax
0x18004e18c  jmp     loc_18004E213
0x18004e191  lea     r8, [rsp+180h+applicationUserModelId]; applicationUserModelId
0x18004e196  lea     rdx, [rsp+180h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18004e19b  mov     rcx, [rsp+180h+token]; token
0x18004e1a0  call    cs:__imp_GetApplicationUserModelIdFromToken
0x18004e1a6  test    eax, eax
0x18004e1a8  jle     short loc_18004E1B4
0x18004e1aa  movzx   eax, ax
0x18004e1ad  or      eax, 80070000h
0x18004e1b2  test    eax, eax
0x18004e1b4  js      short loc_18004E18A
0x18004e1b6  lea     rax, [rsp+180h+pv]
0x18004e1bb  mov     [rsp+180h+var_138], rax
0x18004e1c0  mov     [rsp+180h+var_130], 0
0x18004e1c9  mov     [rsp+180h+var_128], 1
0x18004e1ce  mov     r9d, [rsp+180h+applicationUserModelIdLength]
0x18004e1d3  lea     rax, [rsp+180h+var_130]
0x18004e1d8  mov     [rsp+180h+var_158], rax
0x18004e1dd  lea     r8, [rsp+180h+applicationUserModelId]
0x18004e1e2  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18004e1e7  mov     ebx, eax
0x18004e1e9  lea     rcx, [rsp+180h+var_138]
0x18004e1ee  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18004e1f3  test    ebx, ebx
0x18004e1f5  jns     short loc_18004E21F
0x18004e1f7  mov     r9d, ebx; char *
0x18004e1fa  mov     edx, 52h ; 'R'; void *
0x18004e1ff  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\base\\inc\\UserAw"...
0x18004e206  mov     rcx, [rbp+88h]; this
0x18004e20d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e212  nop
0x18004e213  lea     rcx, [rsp+180h+token]
0x18004e218  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004e21d  jmp     short loc_18004E23C
0x18004e21f  lea     rcx, [rsp+180h+token]
0x18004e224  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004e229  mov     rax, [rsp+180h+pv]
0x18004e22e  mov     [rsp+180h+pv], 0
0x18004e237  mov     [rdi], rax
0x18004e23a  xor     ebx, ebx
0x18004e23c  lea     rcx, [rsp+180h+pv]
0x18004e241  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004e246  mov     eax, ebx
0x18004e248  mov     rcx, [rbp+80h+var_10]
0x18004e24c  xor     rcx, rsp; StackCookie
0x18004e24f  call    __security_check_cookie
0x18004e254  lea     r11, [rsp+180h+var_s0]
0x18004e25c  mov     rbx, [r11+18h]
0x18004e260  mov     rdi, [r11+20h]
0x18004e264  mov     rsp, r11
0x18004e267  pop     rbp
0x18004e268  retn
0x18004e269  test    ebx, ebx
0x18004e26b  jns     short loc_18004E229
0x18004e26d  mov     rcx, [rsp+180h+pv]; pv
0x18004e272  test    rcx, rcx
0x18004e275  jz      short loc_18004E246
0x18004e277  call    cs:__imp_CoTaskMemFree
0x18004e27d  jmp     short loc_18004E246
```
