# FlowEndpointBase::Uninitialize(void)

- ea: `0x18002c4c0`
- end: `0x18002c53b`
- name: `?Uninitialize@FlowEndpointBase@@QEAAXXZ`
- size: `123`
- prototype: `void __fastcall(FlowEndpointBase *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180021dbc`
- `0x18002bf60`
- `0x18004cda8`
- `0x18004d0b8`
- `0x18004d4d0`

## callees

- `0x18001049c`
- `0x18001a798`
- `0x18002c4c0`
- `0x18002d484`

## import_xrefs

- `USER32!DestroyWindow` at `0x18002c52a`
- `USER32!DestroyWindow` at `0x18002c52a`
- `USER32!GetWindowThreadProcessId` at `0x18002c4fd`
- `USER32!GetWindowThreadProcessId` at `0x18002c4fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c505`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c505`

## string_xrefs

- `0x18002c514`: `ShellCommon\Internal\Shell\Inc\ValueSetChannel.h`

## pseudocode

```c
void __fastcall FlowEndpointBase::Uninitialize(FlowEndpointBase *this)
{
  HWND v2; // rcx
  DWORD WindowThreadProcessId; // ebx
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    (char *)this + 64,
    0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 56,
    0);
  v2 = (HWND)*((_QWORD *)this + 1);
  *((_DWORD *)this + 28) = 3;
  *((_QWORD *)this + 10) = 0;
  if ( v2 )
  {
    WindowThreadProcessId = GetWindowThreadProcessId(v2, 0);
    if ( WindowThreadProcessId != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x73,
        (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\ValueSetChannel.h",
        v4);
    DestroyWindow(*((HWND *)this + 1));
  }
}

```

## disassembly

```asm
0x18002c4c0  mov     [rsp+arg_0], rbx
0x18002c4c5  push    rdi
0x18002c4c6  sub     rsp, 20h
0x18002c4ca  mov     rdi, rcx
0x18002c4cd  xor     edx, edx
0x18002c4cf  add     rcx, 40h ; '@'
0x18002c4d3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18002c4d8  lea     rcx, [rdi+38h]
0x18002c4dc  xor     edx, edx
0x18002c4de  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002c4e3  mov     rcx, [rdi+8]; hWnd
0x18002c4e7  mov     dword ptr [rdi+70h], 3
0x18002c4ee  mov     qword ptr [rdi+50h], 0
0x18002c4f6  test    rcx, rcx
0x18002c4f9  jz      short loc_18002C530
0x18002c4fb  xor     edx, edx; lpdwProcessId
0x18002c4fd  call    cs:__imp_GetWindowThreadProcessId
0x18002c503  mov     ebx, eax
0x18002c505  call    cs:__imp_GetCurrentThreadId
0x18002c50b  cmp     ebx, eax
0x18002c50d  jz      short loc_18002C526
0x18002c50f  mov     rcx, [rsp+28h]; this
0x18002c514  lea     r8, aShellcommonInt_0; "ShellCommon\\Internal\\Shell\\Inc\\Valu"...
0x18002c51b  mov     edx, 73h ; 's'; void *
0x18002c520  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002c526  mov     rcx, [rdi+8]; hWnd
0x18002c52a  call    cs:__imp_DestroyWindow
0x18002c530  mov     rbx, [rsp+28h+arg_0]
0x18002c535  add     rsp, 20h
0x18002c539  pop     rdi
0x18002c53a  retn
```
