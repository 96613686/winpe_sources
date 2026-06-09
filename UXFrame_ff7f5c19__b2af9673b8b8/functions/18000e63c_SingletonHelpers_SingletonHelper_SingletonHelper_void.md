# SingletonHelpers::SingletonHelper::~SingletonHelper(void)

- ea: `0x18000e63c`
- end: `0x18000e72d`
- name: `??1SingletonHelper@SingletonHelpers@@QEAA@XZ`
- size: `241`
- prototype: `void __fastcall(SingletonHelpers::SingletonHelper *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ef98`

## callees

- `0x180008968`
- `0x18000e360`
- `0x18000e37c`
- `0x18000e510`
- `0x18000e63c`
- `0x18000f838`
- `0x18001049c`
- `0x180017044`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e660`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e660`

## string_xrefs

- `0x18000e71b`: `ShellCommon\Internal\Shell\Inc\SingletonHelpers.h`

## pseudocode

```c
void __fastcall SingletonHelpers::SingletonHelper::~SingletonHelper(SingletonHelpers::SingletonHelper *this)
{
  _QWORD *v2; // rbp
  int v3; // ebx
  const char *v4; // r9
  char **v5; // rbx
  __int64 v6; // rcx
  char *v7; // rax
  char **v8; // rsi
  __int64 v9; // rcx
  char *v10; // rax
  _QWORD v11[2]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v12[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(_QWORD *)this = &SingletonHelpers::SingletonHelper::`vftable';
  v2 = (_QWORD *)((char *)this + 112);
  if ( *((_QWORD *)this + 14) )
  {
    v3 = *((_DWORD *)this + 30);
    if ( v3 != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x136,
        (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\SingletonHelpers.h",
        v4);
    v5 = (char **)((char *)this + 40);
    v6 = *((_QWORD *)this + 7);
    if ( *((_QWORD *)this + 8) <= 7u )
      v7 = (char *)this + 40;
    else
      v7 = *v5;
    v11[0] = v7;
    v11[1] = v6;
    v8 = (char **)((char *)this + 8);
    v9 = *((_QWORD *)this + 3);
    if ( *((_QWORD *)this + 4) <= 7u )
      v10 = (char *)this + 8;
    else
      v10 = *v8;
    v12[0] = v10;
    v12[1] = v9;
    SingletonHelpers::details::ClearDataForSingletonInstance(v2, (__int64)v12, (__int64)v11, v4);
  }
  else
  {
    v5 = (char **)((char *)this + 40);
    v8 = (char **)((char *)this + 8);
  }
  std::_Func_class<void,>::_Tidy((char *)this + 264);
  FlowEndpointBase::~FlowEndpointBase((SingletonHelpers::SingletonHelper *)((char *)this + 128));
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v2);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 104);
  std::wstring::_Tidy_deallocate((char *)this + 72);
  std::wstring::_Tidy_deallocate(v5);
  std::wstring::_Tidy_deallocate(v8);
}

```

## disassembly

```asm
0x18000e63c  push    rbx
0x18000e63e  push    rbp
0x18000e63f  push    rsi
0x18000e640  push    rdi
0x18000e641  sub     rsp, 48h
0x18000e645  mov     rdi, rcx
0x18000e648  lea     rax, ??_7SingletonHelper@SingletonHelpers@@6B@; const SingletonHelpers::SingletonHelper::`vftable'
0x18000e64f  mov     [rcx], rax
0x18000e652  lea     rbp, [rcx+70h]
0x18000e656  cmp     qword ptr [rbp+0], 0
0x18000e65b  jz      short loc_18000E6C4
0x18000e65d  mov     ebx, [rcx+78h]
0x18000e660  call    cs:__imp_GetCurrentThreadId
0x18000e666  cmp     ebx, eax
0x18000e668  jnz     loc_18000E716
0x18000e66e  lea     rbx, [rdi+28h]
0x18000e672  mov     rcx, [rbx+10h]
0x18000e676  cmp     qword ptr [rbx+18h], 7
0x18000e67b  jbe     short loc_18000E682
0x18000e67d  mov     rax, [rbx]
0x18000e680  jmp     short loc_18000E685
0x18000e682  mov     rax, rbx
0x18000e685  mov     [rsp+68h+var_48], rax
0x18000e68a  mov     [rsp+68h+var_40], rcx
0x18000e68f  lea     rsi, [rdi+8]
0x18000e693  mov     rcx, [rsi+10h]
0x18000e697  cmp     qword ptr [rsi+18h], 7
0x18000e69c  jbe     short loc_18000E6A3
0x18000e69e  mov     rax, [rsi]
0x18000e6a1  jmp     short loc_18000E6A6
0x18000e6a3  mov     rax, rsi
0x18000e6a6  mov     [rsp+68h+var_38], rax
0x18000e6ab  mov     [rsp+68h+var_30], rcx
0x18000e6b0  lea     r8, [rsp+68h+var_48]
0x18000e6b5  lea     rdx, [rsp+68h+var_38]
0x18000e6ba  mov     rcx, rbp
0x18000e6bd  call    ?ClearDataForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@1@Z
0x18000e6c2  jmp     short loc_18000E6CC
0x18000e6c4  lea     rbx, [rcx+28h]
0x18000e6c8  lea     rsi, [rcx+8]
0x18000e6cc  lea     rcx, [rdi+108h]
0x18000e6d3  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18000e6d8  lea     rcx, [rdi+80h]; this
0x18000e6df  call    ??1FlowEndpointBase@@UEAA@XZ; FlowEndpointBase::~FlowEndpointBase(void)
0x18000e6e4  mov     rcx, rbp
0x18000e6e7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e6ec  lea     rcx, [rdi+68h]
0x18000e6f0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e6f5  lea     rcx, [rdi+48h]
0x18000e6f9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e6fe  mov     rcx, rbx
0x18000e701  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e706  mov     rcx, rsi
0x18000e709  add     rsp, 48h
0x18000e70d  pop     rdi
0x18000e70e  pop     rsi
0x18000e70f  pop     rbp
0x18000e710  pop     rbx
0x18000e711  jmp     ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e716  mov     rcx, [rsp+68h]; this
0x18000e71b  lea     r8, aShellcommonInt; "ShellCommon\\Internal\\Shell\\Inc\\Sing"...
0x18000e722  mov     edx, 136h; void *
0x18000e727  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
