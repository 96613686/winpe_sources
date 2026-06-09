# McpGetAuthorizationHeaderOperation::RuntimeClassInitialize(bool,bool,ushort const *,ushort const *,ushort const *)

- ea: `0x180022e80`
- end: `0x1800230ca`
- name: `?RuntimeClassInitialize@McpGetAuthorizationHeaderOperation@@QEAAJ_N0PEBG11@Z`
- size: `586`
- prototype: `__int64 __fastcall(McpGetAuthorizationHeaderOperation *this, char, char, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800214dc`

## callees

- `0x180003aa0`
- `0x1800067a4`
- `0x18000c4cc`
- `0x18000df30`
- `0x180012c30`
- `0x18001b0e8`
- `0x18001c9a8`
- `0x180022188`
- `0x180022294`
- `0x180022960`
- `0x180022e80`
- `0x180023538`
- `0x180023e98`
- `0x180023f1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022f83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022f83`

## string_xrefs

- `0x18002303c`: `Couldn't get user token`

## pseudocode

```c
__int64 __fastcall McpGetAuthorizationHeaderOperation::RuntimeClassInitialize(
        McpGetAuthorizationHeaderOperation *this,
        char a2,
        char a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  const WCHAR *v10; // rsi
  const WCHAR *v11; // r14
  __int64 v12; // rdi
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 unique_cotaskmem; // rax
  char *v16; // rdi
  void *v17; // rcx
  const char *v18; // r9
  __int64 result; // rax
  void **v20; // rdx
  _DWORD *v21; // rax
  HWND *v22; // rdx
  int UserImpersonationToken; // edi
  int v24; // [rsp+20h] [rbp-88h]
  const char *v25; // [rsp+28h] [rbp-80h]
  char *v26; // [rsp+30h] [rbp-78h] BYREF
  std::_Ref_count_base *v27; // [rsp+38h] [rbp-70h]
  _QWORD v28[8]; // [rsp+40h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  LPVOID pv; // [rsp+B0h] [rbp+8h] BYREF

  v10 = a6;
  v11 = a5;
  McpManagementTelemetry::WriteDbgTraceInfo(
    "McpGetAuthorizationHeaderOperation::RuntimeClassInitialize",
    L"Initializing McpGetAuthorizationHeaderOperation");
  *((_BYTE *)this + 24) = a2;
  *((_BYTE *)this + 25) = a3;
  if ( !a4 )
    a4 = &dword_18002DF04;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( a4[v13] );
  try
  {
    ((void (*)(void))std::wstring::_Assign<unsigned short>)();
    if ( !v11 )
      v11 = &dword_18002DF04;
    v14 = -1;
    do
      ++v14;
    while ( v11[v14] );
    std::wstring::_Assign<unsigned short>((char *)this + 72, v11);
    if ( !v10 )
      v10 = &dword_18002DF04;
    do
      ++v12;
    while ( v10[v12] );
    std::wstring::_Assign<unsigned short>((char *)this + 104, v10);
    unique_cotaskmem = wil::make_unique_cotaskmem_nothrow<McpOperationHandlerThreadParams,>(&pv);
    v16 = (char *)this + 328;
    wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
      (char *)this + 328,
      unique_cotaskmem);
    v17 = pv;
    pv = 0;
    if ( v17 )
      CoTaskMemFree(v17);
    if ( *(_QWORD *)v16 )
    {
      **(_DWORD **)v16 = 2;
      *(_QWORD *)(*(_QWORD *)v16 + 8LL) = this;
      wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
        (char *)this + 232,
        0);
      if ( !*((_QWORD *)this + 29) )
      {
        v21 = operator new(0x18u);
        v21[2] = 1;
        v21[3] = 1;
        *(_QWORD *)v21 = &std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::`vftable';
        *((_QWORD *)v21 + 2) = 0;
        v26 = (char *)(v21 + 4);
        v27 = (std::_Ref_count_base *)v21;
        std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::operator=(
          (char *)this + 232,
          &v26);
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
      }
      UserImpersonationToken = McpManagement::GetUserImpersonationToken(*((PHANDLE *)this + 29), v20);
      if ( UserImpersonationToken >= 0 )
      {
        if ( a2
          || a3
          || (result = McpManagement::GetCallerWindowHandle(
                         (McpGetAuthorizationHeaderOperation *)((char *)this + 32),
                         v22),
              (int)result >= 0) )
        {
          v28[0] = off_18002C9E8;
          v28[1] = this;
          v28[7] = v28;
          result = McpOperationHandler::Initialize((char *)this + 248, v28);
        }
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x22,
          (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetauthorizationheaderoperation.cpp",
          (const char *)(unsigned int)UserImpersonationToken,
          (int)"Couldn't get user token",
          v25);
        result = (unsigned int)UserImpersonationToken;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetauthorizationheaderoperation.cpp",
        (const char *)0x8007000ELL,
        v24);
      result = 2147942414LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x52,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetauthorizationheaderoperation.cpp",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x180022e80  mov     [rsp+arg_10], rbx
0x180022e85  mov     [rsp+arg_18], rsi
0x180022e8a  push    rdi
0x180022e8b  push    r12
0x180022e8d  push    r13
0x180022e8f  push    r14
0x180022e91  push    r15
0x180022e93  sub     rsp, 80h
0x180022e9a  mov     r15, r9
0x180022e9d  mov     r12b, r8b
0x180022ea0  mov     r13b, dl
0x180022ea3  mov     rbx, rcx
0x180022ea6  mov     rsi, [rsp+0A8h+arg_28]
0x180022eae  mov     r14, [rsp+0A8h+arg_20]
0x180022eb6  lea     rdx, aInitializingMc_1; "Initializing McpGetAuthorizationHeaderO"...
0x180022ebd  lea     rcx, aMcpgetauthoriz_0; "McpGetAuthorizationHeaderOperation::Run"...
0x180022ec4  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180022ec9  mov     [rbx+18h], r13b
0x180022ecd  mov     [rbx+19h], r12b
0x180022ed1  lea     rax, dword_18002DF04
0x180022ed8  test    r15, r15
0x180022edb  cmovz   r15, rax
0x180022edf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180022ee3  mov     r8, rdi
0x180022ee6  xor     eax, eax
0x180022ee8  inc     r8
0x180022eeb  cmp     [r15+r8*2], ax
0x180022ef0  jnz     short loc_180022EE8
0x180022ef2  lea     rcx, [rbx+28h]
0x180022ef6  mov     rdx, r15
0x180022ef9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180022efe  xor     r15d, r15d
0x180022f01  test    r14, r14
0x180022f04  lea     rax, dword_18002DF04
0x180022f0b  cmovz   r14, rax
0x180022f0f  mov     r8, rdi
0x180022f12  inc     r8
0x180022f15  cmp     [r14+r8*2], r15w
0x180022f1a  jnz     short loc_180022F12
0x180022f1c  lea     rcx, [rbx+48h]
0x180022f20  mov     rdx, r14
0x180022f23  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180022f28  test    rsi, rsi
0x180022f2b  lea     rax, dword_18002DF04
0x180022f32  cmovz   rsi, rax
0x180022f36  inc     rdi
0x180022f39  cmp     [rsi+rdi*2], r15w
0x180022f3e  jnz     short loc_180022F36
0x180022f40  lea     rcx, [rbx+68h]
0x180022f44  mov     r8, rdi
0x180022f47  mov     rdx, rsi
0x180022f4a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180022f4f  lea     rcx, [rsp+0A8h+pv]
0x180022f57  call    ??$make_unique_cotaskmem_nothrow@UMcpOperationHandlerThreadParams@@$$V@wil@@YA?AV?$unique_ptr@UMcpOperationHandlerThreadParams@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ; wil::make_unique_cotaskmem_nothrow<McpOperationHandlerThreadParams,>(void)
0x180022f5c  lea     rdi, [rbx+148h]
0x180022f63  mov     rdx, rax
0x180022f66  mov     rcx, rdi
0x180022f69  call    ??4?$unique_ptr@UMcpOperationHandlerThreadParams@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180022f6e  mov     rcx, [rsp+0A8h+pv]; pv
0x180022f76  mov     [rsp+0A8h+pv], r15
0x180022f7e  test    rcx, rcx
0x180022f81  jz      short loc_180022F89
0x180022f83  call    cs:__imp_CoTaskMemFree
0x180022f89  mov     rax, [rdi]
0x180022f8c  test    rax, rax
0x180022f8f  jnz     short loc_180022FB7
0x180022f91  mov     rcx, [rsp+0A8h]; this
0x180022f99  mov     ebx, 8007000Eh
0x180022f9e  mov     r9d, ebx; char *
0x180022fa1  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180022fa8  lea     edx, [rax+1Ch]; void *
0x180022fab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022fb0  mov     eax, ebx
0x180022fb2  jmp     loc_1800230AC
0x180022fb7  mov     dword ptr [rax], 2
0x180022fbd  mov     rax, [rdi]
0x180022fc0  mov     [rax+8], rbx
0x180022fc4  lea     rdi, [rbx+0E8h]
0x180022fcb  xor     edx, edx
0x180022fcd  mov     rcx, rdi
0x180022fd0  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x180022fd5  cmp     [rdi], r15
0x180022fd8  jnz     short loc_180023026
0x180022fda  mov     ecx, 18h; Size
0x180022fdf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022fe4  mov     ecx, 1
0x180022fe9  mov     [rax+8], ecx
0x180022fec  mov     [rax+0Ch], ecx
0x180022fef  lea     rcx, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::`vftable'
0x180022ff6  mov     [rax], rcx
0x180022ff9  lea     rdx, [rax+10h]
0x180022ffd  mov     [rdx], r15
0x180023000  mov     [rsp+0A8h+var_78], rdx
0x180023005  mov     [rsp+0A8h+var_70], rax
0x18002300a  lea     rdx, [rsp+0A8h+var_78]
0x18002300f  mov     rcx, rdi
0x180023012  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x180023017  mov     rcx, [rsp+0A8h+var_70]; this
0x18002301c  test    rcx, rcx
0x18002301f  jz      short loc_180023026
0x180023021  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180023026  mov     rcx, [rdi]; phNewToken
0x180023029  call    ?GetUserImpersonationToken@McpManagement@@YAJPEAPEAX@Z; McpManagement::GetUserImpersonationToken(void * *)
0x18002302e  mov     edi, eax
0x180023030  test    eax, eax
0x180023032  jns     short loc_180023060
0x180023034  mov     rcx, [rsp+0A8h]; this
0x18002303c  lea     rax, aCouldnTGetUser; "Couldn't get user token"
0x180023043  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x180023048  mov     r9d, edi; char *
0x18002304b  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180023052  mov     edx, 22h ; '"'; void *
0x180023057  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002305c  mov     eax, edi
0x18002305e  jmp     short loc_1800230AC
0x180023060  test    r13b, r13b
0x180023063  jnz     short loc_180023077
0x180023065  test    r12b, r12b
0x180023068  jnz     short loc_180023077
0x18002306a  lea     rcx, [rbx+20h]; this
0x18002306e  call    ?GetCallerWindowHandle@McpManagement@@YAJPEAPEAUHWND__@@@Z; McpManagement::GetCallerWindowHandle(HWND__ * *)
0x180023073  test    eax, eax
0x180023075  js      short loc_1800230AC
0x180023077  lea     rax, off_18002C9E8
0x18002307e  mov     [rsp+0A8h+var_68], rax
0x180023083  mov     [rsp+0A8h+var_60], rbx
0x180023088  lea     rax, [rsp+0A8h+var_68]
0x18002308d  mov     [rsp+0A8h+var_30], rax
0x180023092  lea     rcx, [rbx+0F8h]
0x180023099  lea     rdx, [rsp+0A8h+var_68]
0x18002309e  call    ?Initialize@McpOperationHandler@@QEAAJV?$function@$$A6AJXZ@std@@@Z; McpOperationHandler::Initialize(std::function<long (void)>)
0x1800230a3  jmp     short loc_1800230AC
0x1800230a5  mov     eax, [rsp+0A8h+arg_8]
0x1800230ac  lea     r11, [rsp+0A8h+var_28]
0x1800230b4  mov     rbx, [r11+40h]
0x1800230b8  mov     rsi, [r11+48h]
0x1800230bc  mov     rsp, r11
0x1800230bf  pop     r15
0x1800230c1  pop     r14
0x1800230c3  pop     r13
0x1800230c5  pop     r12
0x1800230c7  pop     rdi
0x1800230c8  retn
```
