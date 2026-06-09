# Windows::Service::Task::EnsureTaskFolderExists(wil::com_ptr_t<ITaskService,wil::err_exception_policy> const &)

- ea: `0x18005c718`
- end: `0x18005c8e9`
- name: `?EnsureTaskFolderExists@Task@Service@Windows@@CAXAEBV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `465`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005bbac`
- `0x18005d944`

## callees

- `0x1800209fc`
- `0x180023a34`
- `0x180023ac4`
- `0x18005c718`
- `0x180071010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005c752`
- `OLEAUT32!__imp_SysAllocString` at `0x18005c752`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c86b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c891`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c86b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c891`
- `OLEAUT32!__imp_VariantInit` at `0x18005c734`
- `OLEAUT32!__imp_VariantInit` at `0x18005c734`
- `OLEAUT32!__imp_VariantClear` at `0x18005c89c`
- `OLEAUT32!__imp_VariantClear` at `0x18005c89c`

## string_xrefs

- `0x18005c8c2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18005c8b0`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005c8d7`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
HRESULT __fastcall Windows::Service::Task::EnsureTaskFolderExists(__int64 **a1)
{
  const OLECHAR *v2; // rcx
  OLECHAR *v3; // rax
  const char *v4; // r9
  char v5; // bl
  __int64 *v6; // rdx
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  PCNZWCH *v10; // rdx
  __int64 v11; // rax
  unsigned int v12; // eax
  int v14; // [rsp+20h] [rbp-60h]
  BSTR bstrString; // [rsp+30h] [rbp-50h] BYREF
  BSTR v16[2]; // [rsp+38h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v18; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  __int64 *v20; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+38h] BYREF

  VariantInit(&pvarg);
  v2 = (const OLECHAR *)&Windows::Service::Task::c_securityDescriptor;
  if ( (unsigned __int64)qword_1800976C8 > 7 )
    v2 = Windows::Service::Task::c_securityDescriptor;
  v3 = SysAllocString(v2);
  v16[1] = v3;
  v5 = 1;
  if ( !v3 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v4);
  pvarg.llVal = (LONGLONG)v3;
  pvarg.vt = 8;
  v6 = &Windows::Service::Task::c_rootPath;
  if ( (unsigned __int64)qword_1800976A8 > 7 )
    v6 = (__int64 *)Windows::Service::Task::c_rootPath;
  wil::make_bstr(v16, v6);
  v20 = 0;
  v7 = *a1;
  v8 = **a1;
  v20 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 **))(v8 + 56))(v7, v16[0], &v20);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v9,
      v14);
  v10 = &Windows::Service::Task::c_taskFolder;
  if ( (unsigned __int64)qword_180097688 > 7 )
    v10 = (PCNZWCH *)Windows::Service::Task::c_taskFolder;
  wil::make_bstr(&bstrString, v10);
  v21 = 0;
  v11 = *v20;
  v21 = 0;
  v18 = pvarg;
  v12 = (*(__int64 (__fastcall **)(__int64 *, BSTR, VARIANTARG *, __int64 *))(v11 + 88))(v20, bstrString, &v18, &v21);
  if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147024713 )
    v5 = 0;
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)v12,
      v14);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v20 )
    (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
  if ( v16[0] )
    SysFreeString(v16[0]);
  return VariantClear(&pvarg);
}

```

## disassembly

```asm
0x18005c718  push    rbp
0x18005c71a  push    rbx
0x18005c71b  push    rdi
0x18005c71c  mov     rbp, rsp
0x18005c71f  sub     rsp, 80h
0x18005c726  mov     rdi, rcx
0x18005c729  mov     [rbp+arg_8], 0
0x18005c730  lea     rcx, [rbp+pvarg]; pvarg
0x18005c734  call    cs:__imp_VariantInit
0x18005c73a  nop
0x18005c73b  lea     rcx, ?c_securityDescriptor@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_securityDescriptor
0x18005c742  cmp     cs:qword_1800976C8, 7
0x18005c74a  cmova   rcx, cs:?c_securityDescriptor@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; psz
0x18005c752  call    cs:__imp_SysAllocString
0x18005c758  mov     [rbp+var_40], rax
0x18005c75c  mov     ebx, 1
0x18005c761  mov     [rbp+arg_8], ebx
0x18005c764  mov     rcx, [rbp+18h]; this
0x18005c768  test    rax, rax
0x18005c76b  jz      loc_18005C8C2
0x18005c771  mov     qword ptr [rbp+pvarg+8], rax
0x18005c775  lea     eax, [rbx+7]
0x18005c778  mov     word ptr [rbp+pvarg], ax
0x18005c77c  lea     rdx, ?c_rootPath@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_rootPath
0x18005c783  cmp     cs:qword_1800976A8, 7
0x18005c78b  cmova   rdx, cs:?c_rootPath@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_rootPath
0x18005c793  lea     rcx, [rbp+var_48]
0x18005c797  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005c79c  nop
0x18005c79d  mov     [rbp+arg_10], 0
0x18005c7a5  mov     rcx, [rdi]
0x18005c7a8  mov     rax, [rcx]
0x18005c7ab  mov     [rbp+arg_10], 0
0x18005c7b3  lea     r8, [rbp+arg_10]
0x18005c7b7  mov     rdx, [rbp+var_48]
0x18005c7bb  mov     rax, [rax+38h]
0x18005c7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c7c4  mov     rcx, [rbp+18h]; this
0x18005c7c8  test    eax, eax
0x18005c7ca  js      loc_18005C8D4
0x18005c7d0  lea     rdx, ?c_taskFolder@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_taskFolder
0x18005c7d7  cmp     cs:qword_180097688, 7
0x18005c7df  cmova   rdx, cs:?c_taskFolder@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_taskFolder
0x18005c7e7  lea     rcx, [rbp+bstrString]
0x18005c7eb  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005c7f0  nop
0x18005c7f1  mov     [rbp+arg_18], 0
0x18005c7f9  mov     rcx, [rbp+arg_10]
0x18005c7fd  mov     rax, [rcx]
0x18005c800  mov     [rbp+arg_18], 0
0x18005c808  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18005c80c  movaps  [rbp+var_20], xmm0
0x18005c810  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18005c815  movsd   [rbp+var_10], xmm1
0x18005c81a  lea     r9, [rbp+arg_18]
0x18005c81e  lea     r8, [rbp+var_20]
0x18005c822  mov     rdx, [rbp+bstrString]
0x18005c826  mov     rax, [rax+58h]
0x18005c82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c82f  mov     edx, 80000000h
0x18005c834  lea     ecx, [rax+rdx]
0x18005c837  test    edx, ecx
0x18005c839  jnz     short loc_18005C842
0x18005c83b  cmp     eax, 800700B7h
0x18005c840  jnz     short loc_18005C844
0x18005c842  xor     bl, bl
0x18005c844  mov     rcx, [rbp+18h]; this
0x18005c848  test    bl, bl
0x18005c84a  jnz     short loc_18005C8AD
0x18005c84c  mov     rcx, [rbp+arg_18]
0x18005c850  test    rcx, rcx
0x18005c853  jz      short loc_18005C862
0x18005c855  mov     rax, [rcx]
0x18005c858  mov     rax, [rax+10h]
0x18005c85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c861  nop
0x18005c862  mov     rcx, [rbp+bstrString]; bstrString
0x18005c866  test    rcx, rcx
0x18005c869  jz      short loc_18005C872
0x18005c86b  call    cs:__imp_SysFreeString
0x18005c871  nop
0x18005c872  mov     rcx, [rbp+arg_10]
0x18005c876  test    rcx, rcx
0x18005c879  jz      short loc_18005C888
0x18005c87b  mov     rax, [rcx]
0x18005c87e  mov     rax, [rax+10h]
0x18005c882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c887  nop
0x18005c888  mov     rcx, [rbp+var_48]; bstrString
0x18005c88c  test    rcx, rcx
0x18005c88f  jz      short loc_18005C898
0x18005c891  call    cs:__imp_SysFreeString
0x18005c897  nop
0x18005c898  lea     rcx, [rbp+pvarg]; pvarg
0x18005c89c  call    cs:__imp_VariantClear
0x18005c8a2  add     rsp, 80h
0x18005c8a9  pop     rdi
0x18005c8aa  pop     rbx
0x18005c8ab  pop     rbp
0x18005c8ac  retn
0x18005c8ad  mov     r9d, eax; char *
0x18005c8b0  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005c8b7  mov     edx, 29h ; ')'; void *
0x18005c8bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c8c2  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005c8c9  mov     edx, 15F3h; void *
0x18005c8ce  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18005c8d4  mov     r9d, eax; char *
0x18005c8d7  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005c8de  mov     edx, 23h ; '#'; void *
0x18005c8e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
