# McpGetCloudPrintServiceOperation::RuntimeClassInitialize(bool,bool,bool)

- ea: `0x180022580`
- end: `0x180022785`
- name: `?RuntimeClassInitialize@McpGetCloudPrintServiceOperation@@QEAAJ_N00@Z`
- size: `517`
- prototype: `__int64 __fastcall(McpGetCloudPrintServiceOperation *this, char, char, char)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800215d8`

## callees

- `0x180003aa0`
- `0x18000c4cc`
- `0x18000df30`
- `0x180011f80`
- `0x180012c30`
- `0x1800194dc`
- `0x18001b0e8`
- `0x18001c9a8`
- `0x180022188`
- `0x180022294`
- `0x180022580`
- `0x180022960`
- `0x180023538`
- `0x180023e98`
- `0x180023f1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002263d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002263d`

## string_xrefs

- `0x1800225a0`: `Initializing McpGetCloudPrintServiceOperation`
- `0x1800225a7`: `McpGetCloudPrintServiceOperation::RuntimeClassInitialize`
- `0x18002265b`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpgetcloudprintserviceoperation.cpp`
- `0x18002270e`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpgetcloudprintserviceoperation.cpp`
- `0x1800226ff`: `Couldn't get user token`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall McpGetCloudPrintServiceOperation::RuntimeClassInitialize(
        McpGetCloudPrintServiceOperation *this,
        char a2,
        char a3,
        char a4)
{
  _DWORD *v8; // rsi
  std::_Ref_count_base *v9; // rcx
  __int64 unique_cotaskmem; // rax
  char *v11; // rbx
  void *v12; // rcx
  const char *v13; // r9
  __int64 result; // rax
  void **v15; // rdx
  _DWORD *v16; // rax
  HWND *v17; // rdx
  int UserImpersonationToken; // ebx
  int v19; // [rsp+20h] [rbp-88h]
  const char *v20; // [rsp+28h] [rbp-80h]
  char *v21; // [rsp+30h] [rbp-78h] BYREF
  std::_Ref_count_base *v22; // [rsp+38h] [rbp-70h]
  _QWORD v23[13]; // [rsp+40h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  LPVOID pv; // [rsp+B0h] [rbp+8h] BYREF

  McpManagementTelemetry::WriteDbgTraceInfo(
    "McpGetCloudPrintServiceOperation::RuntimeClassInitialize",
    L"Initializing McpGetCloudPrintServiceOperation");
  *((_BYTE *)this + 24) = a2;
  *((_BYTE *)this + 25) = a3;
  *((_BYTE *)this + 26) = a4;
  try
  {
    v8 = operator new(0x1E8u);
    v8[2] = 1;
    v8[3] = 1;
    *(_QWORD *)v8 = &std::_Ref_count_obj2<CloudPrint::CloudPrintHelper>::`vftable';
    CloudPrint::CloudPrintHelper::CloudPrintHelper((CloudPrint::CloudPrintHelper *)(v8 + 4));
    *((_QWORD *)this + 5) = v8 + 4;
    v9 = (std::_Ref_count_base *)*((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = v8;
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    unique_cotaskmem = wil::make_unique_cotaskmem_nothrow<McpOperationHandlerThreadParams,>(&pv);
    v11 = (char *)this + 152;
    wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
      (char *)this + 152,
      unique_cotaskmem);
    v12 = pv;
    pv = 0;
    if ( v12 )
      CoTaskMemFree(v12);
    if ( !*(_QWORD *)v11 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19,
        (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceoperation.cpp",
        (const char *)0x8007000ELL,
        v19);
      return 2147942414LL;
    }
    **(_DWORD **)v11 = 1;
    *(_QWORD *)(*(_QWORD *)v11 + 8LL) = this;
    if ( CloudPrint::CloudPrintHelper::IsMockEnabled() )
      goto LABEL_17;
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
      (char *)this + 56,
      0);
    if ( !*((_QWORD *)this + 7) )
    {
      v16 = operator new(0x18u);
      v16[2] = 1;
      v16[3] = 1;
      *(_QWORD *)v16 = &std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::`vftable';
      *((_QWORD *)v16 + 2) = 0;
      v21 = (char *)(v16 + 4);
      v22 = (std::_Ref_count_base *)v16;
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::operator=(
        (char *)this + 56,
        &v21);
      if ( v22 )
        std::_Ref_count_base::_Decref(v22);
    }
    UserImpersonationToken = McpManagement::GetUserImpersonationToken(*((PHANDLE *)this + 7), v15);
    if ( UserImpersonationToken < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x23,
        (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceoperation.cpp",
        (const char *)(unsigned int)UserImpersonationToken,
        (int)"Couldn't get user token",
        v20);
      return (unsigned int)UserImpersonationToken;
    }
    if ( a2
      || a4
      || (result = McpManagement::GetCallerWindowHandle((McpGetCloudPrintServiceOperation *)((char *)this + 32), v17),
          (int)result >= 0) )
    {
LABEL_17:
      v23[0] = off_18002C880;
      v23[1] = this;
      v23[7] = v23;
      result = McpOperationHandler::Initialize((char *)this + 72, v23);
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4D,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceoperation.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180022580  mov     [rsp+arg_10], rbx
0x180022585  push    rsi
0x180022586  push    rdi
0x180022587  push    r13
0x180022589  push    r14
0x18002258b  push    r15
0x18002258d  sub     rsp, 80h
0x180022594  mov     r14b, r9b
0x180022597  mov     bl, r8b
0x18002259a  mov     r15b, dl
0x18002259d  mov     rdi, rcx
0x1800225a0  lea     rdx, aInitializingMc; "Initializing McpGetCloudPrintServiceOpe"...
0x1800225a7  lea     rcx, aMcpgetcloudpri_3; "McpGetCloudPrintServiceOperation::Runti"...
0x1800225ae  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800225b3  mov     [rdi+18h], r15b
0x1800225b7  mov     [rdi+19h], bl
0x1800225ba  mov     [rdi+1Ah], r14b
0x1800225be  mov     ecx, 1E8h; Size
0x1800225c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800225c8  mov     rsi, rax
0x1800225cb  mov     r13d, 1
0x1800225d1  mov     [rax+8], r13d
0x1800225d5  mov     [rax+0Ch], r13d
0x1800225d9  lea     rax, ??_7?$_Ref_count_obj2@VCloudPrintHelper@CloudPrint@@@std@@6B@; const std::_Ref_count_obj2<CloudPrint::CloudPrintHelper>::`vftable'
0x1800225e0  mov     [rsi], rax
0x1800225e3  lea     rbx, [rsi+10h]
0x1800225e7  mov     rcx, rbx; this
0x1800225ea  call    ??0CloudPrintHelper@CloudPrint@@QEAA@XZ; CloudPrint::CloudPrintHelper::CloudPrintHelper(void)
0x1800225ef  mov     [rdi+28h], rbx
0x1800225f3  mov     rcx, [rdi+30h]; this
0x1800225f7  mov     [rdi+30h], rsi
0x1800225fb  test    rcx, rcx
0x1800225fe  jz      short loc_180022605
0x180022600  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022605  lea     rcx, [rsp+0A8h+pv]
0x18002260d  call    ??$make_unique_cotaskmem_nothrow@UMcpOperationHandlerThreadParams@@$$V@wil@@YA?AV?$unique_ptr@UMcpOperationHandlerThreadParams@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ; wil::make_unique_cotaskmem_nothrow<McpOperationHandlerThreadParams,>(void)
0x180022612  lea     rbx, [rdi+98h]
0x180022619  mov     rdx, rax
0x18002261c  mov     rcx, rbx
0x18002261f  call    ??4?$unique_ptr@UMcpOperationHandlerThreadParams@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180022624  mov     rcx, [rsp+0A8h+pv]; pv
0x18002262c  mov     [rsp+0A8h+pv], 0
0x180022638  test    rcx, rcx
0x18002263b  jz      short loc_180022643
0x18002263d  call    cs:__imp_CoTaskMemFree
0x180022643  mov     rax, [rbx]
0x180022646  test    rax, rax
0x180022649  jnz     short loc_180022671
0x18002264b  mov     rcx, [rsp+0A8h]; this
0x180022653  mov     ebx, 8007000Eh
0x180022658  mov     r9d, ebx; char *
0x18002265b  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180022662  lea     edx, [rax+19h]; void *
0x180022665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002266a  mov     eax, ebx
0x18002266c  jmp     loc_18002276C
0x180022671  mov     [rax], r13d
0x180022674  mov     rax, [rbx]
0x180022677  mov     [rax+8], rdi
0x18002267b  call    ?IsMockEnabled@CloudPrintHelper@CloudPrint@@SA_NXZ; CloudPrint::CloudPrintHelper::IsMockEnabled(void)
0x180022680  test    al, al
0x180022682  jnz     loc_18002273A
0x180022688  lea     rbx, [rdi+38h]
0x18002268c  xor     edx, edx
0x18002268e  mov     rcx, rbx
0x180022691  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x180022696  cmp     qword ptr [rbx], 0
0x18002269a  jnz     short loc_1800226E9
0x18002269c  mov     ecx, 18h; Size
0x1800226a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800226a6  mov     [rax+8], r13d
0x1800226aa  mov     [rax+0Ch], r13d
0x1800226ae  lea     rcx, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::`vftable'
0x1800226b5  mov     [rax], rcx
0x1800226b8  lea     rdx, [rax+10h]
0x1800226bc  mov     qword ptr [rdx], 0
0x1800226c3  mov     [rsp+0A8h+var_78], rdx
0x1800226c8  mov     [rsp+0A8h+var_70], rax
0x1800226cd  lea     rdx, [rsp+0A8h+var_78]
0x1800226d2  mov     rcx, rbx
0x1800226d5  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x1800226da  mov     rcx, [rsp+0A8h+var_70]; this
0x1800226df  test    rcx, rcx
0x1800226e2  jz      short loc_1800226E9
0x1800226e4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800226e9  mov     rcx, [rbx]; phNewToken
0x1800226ec  call    ?GetUserImpersonationToken@McpManagement@@YAJPEAPEAX@Z; McpManagement::GetUserImpersonationToken(void * *)
0x1800226f1  mov     ebx, eax
0x1800226f3  test    eax, eax
0x1800226f5  jns     short loc_180022723
0x1800226f7  mov     rcx, [rsp+0A8h]; this
0x1800226ff  lea     rax, aCouldnTGetUser; "Couldn't get user token"
0x180022706  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18002270b  mov     r9d, ebx; char *
0x18002270e  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180022715  mov     edx, 23h ; '#'; void *
0x18002271a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002271f  mov     eax, ebx
0x180022721  jmp     short loc_18002276C
0x180022723  test    r15b, r15b
0x180022726  jnz     short loc_18002273A
0x180022728  test    r14b, r14b
0x18002272b  jnz     short loc_18002273A
0x18002272d  lea     rcx, [rdi+20h]; this
0x180022731  call    ?GetCallerWindowHandle@McpManagement@@YAJPEAPEAUHWND__@@@Z; McpManagement::GetCallerWindowHandle(HWND__ * *)
0x180022736  test    eax, eax
0x180022738  js      short loc_18002276C
0x18002273a  lea     rax, off_18002C880
0x180022741  mov     [rsp+0A8h+var_68], rax
0x180022746  mov     [rsp+0A8h+var_60], rdi
0x18002274b  lea     rax, [rsp+0A8h+var_68]
0x180022750  mov     [rsp+0A8h+var_30], rax
0x180022755  lea     rcx, [rdi+48h]
0x180022759  lea     rdx, [rsp+0A8h+var_68]
0x18002275e  call    ?Initialize@McpOperationHandler@@QEAAJV?$function@$$A6AJXZ@std@@@Z; McpOperationHandler::Initialize(std::function<long (void)>)
0x180022763  jmp     short loc_18002276C
0x180022765  mov     eax, [rsp+0A8h+arg_8]
0x18002276c  mov     rbx, [rsp+0A8h+arg_10]
0x180022774  add     rsp, 80h
0x18002277b  pop     r15
0x18002277d  pop     r14
0x18002277f  pop     r13
0x180022781  pop     rdi
0x180022782  pop     rsi
0x180022783  retn
```
