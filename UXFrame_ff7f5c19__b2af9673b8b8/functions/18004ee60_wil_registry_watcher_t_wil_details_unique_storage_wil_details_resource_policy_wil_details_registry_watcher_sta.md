# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,ulong)

- ea: `0x18004ee60`
- end: `0x18004ef0f`
- name: `?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z`
- size: `175`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18001047c`
- `0x18003f970`
- `0x180049268`
- `0x18004ee60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004eea1`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004eea1`

## string_xrefs

- `0x18004eecf`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\registry.h`

## pseudocode

```c
void __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback(
        PTP_CALLBACK_INSTANCE Instance,
        unsigned __int8 *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  int v5; // eax
  char v6; // dl
  BOOL fAsynchronous; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( _InterlockedIncrement((volatile signed __int32 *)Context + 37) > 1 )
  {
    v5 = RegNotifyChangeKeyValue(*((HKEY *)Context + 15), Context[144], 0x10000005u, *((HANDLE *)Context + 16), 1);
    if ( !v5 || v5 == 5 )
    {
      wistd::function<void (enum wil::RegistryChangeKind)>::operator()(Context, 0);
      v6 = 1;
    }
    else
    {
      if ( v5 != 811 )
      {
        if ( v5 != 1018 )
        {
          if ( v5 > 0 )
            v5 = (unsigned __int16)v5 | 0x80070000;
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0xCB1,
            (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\registry.h",
            (const char *)(unsigned int)v5,
            fAsynchronous);
        }
        wistd::function<void (enum wil::RegistryChangeKind)>::operator()(Context, 1);
      }
      v6 = 0;
    }
    wil::details::registry_watcher_state::ReleaseFromCallback((wil::details::registry_watcher_state *)Context, v6);
  }
}

```

## disassembly

```asm
0x18004ee60  push    rbx
0x18004ee62  sub     rsp, 30h
0x18004ee66  mov     rbx, rdx
0x18004ee69  mov     eax, 1
0x18004ee6e  lock xadd [rdx+94h], eax
0x18004ee76  inc     eax
0x18004ee78  cmp     eax, 1
0x18004ee7b  jle     loc_18004EF09
0x18004ee81  movzx   edx, byte ptr [rdx+90h]; bWatchSubtree
0x18004ee88  mov     r8d, 10000005h; dwNotifyFilter
0x18004ee8e  mov     r9, [rbx+80h]; hEvent
0x18004ee95  mov     rcx, [rbx+78h]; hKey
0x18004ee99  mov     [rsp+38h+fAsynchronous], 1; int
0x18004eea1  call    cs:__imp_RegNotifyChangeKeyValue
0x18004eea7  test    eax, eax
0x18004eea9  jz      short loc_18004EEF5
0x18004eeab  cmp     eax, 5
0x18004eeae  jz      short loc_18004EEF5
0x18004eeb0  cmp     eax, 32Bh
0x18004eeb5  jz      short loc_18004EEF1
0x18004eeb7  cmp     eax, 3FAh
0x18004eebc  jz      short loc_18004EEE4
0x18004eebe  test    eax, eax
0x18004eec0  jle     short loc_18004EECA
0x18004eec2  movzx   eax, ax
0x18004eec5  or      eax, 80070000h
0x18004eeca  mov     rcx, [rsp+38h]; this
0x18004eecf  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18004eed6  mov     r9d, eax; char *
0x18004eed9  mov     edx, 0CB1h; void *
0x18004eede  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18004eee4  mov     edx, 1
0x18004eee9  mov     rcx, rbx
0x18004eeec  call    ??R?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@QEBAXW4RegistryChangeKind@wil@@@Z; wistd::function<void (wil::RegistryChangeKind)>::operator()(wil::RegistryChangeKind)
0x18004eef1  xor     edx, edx
0x18004eef3  jmp     short loc_18004EF01
0x18004eef5  xor     edx, edx
0x18004eef7  mov     rcx, rbx
0x18004eefa  call    ??R?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@QEBAXW4RegistryChangeKind@wil@@@Z; wistd::function<void (wil::RegistryChangeKind)>::operator()(wil::RegistryChangeKind)
0x18004eeff  mov     dl, 1; bool
0x18004ef01  mov     rcx, rbx; this
0x18004ef04  call    ?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z; wil::details::registry_watcher_state::ReleaseFromCallback(bool)
0x18004ef09  add     rsp, 30h
0x18004ef0d  pop     rbx
0x18004ef0e  retn
```
