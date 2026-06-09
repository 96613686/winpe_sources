# ServerConnector::CompleteConnect(void)

- ea: `0x180035790`
- end: `0x180035834`
- name: `?CompleteConnect@ServerConnector@@UEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002a514`
- `0x180031540`
- `0x180035790`
- `0x18003583c`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800357d9`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800357d9`

## string_xrefs

- `0x1800357e8`: `onecore\windows\accessibletech\uiamanager\dll\namedpipechannel.cpp`
- `0x18003581c`: `onecore\windows\accessibletech\uiamanager\dll\namedpipechannel.cpp`

## pseudocode

```c
_QWORD *__fastcall ServerConnector::CompleteConnect(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  void *v5; // rcx
  const char *v6; // r9
  _QWORD *result; // rax
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD NumberOfBytesTransferred; // [rsp+40h] [rbp+8h] BYREF

  v4 = *(_QWORD **)(a1 + 8);
  if ( !v4 || !*v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F5,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\namedpipechannel.cpp",
      (const char *)0x8000FFFFLL,
      v8);
  __4__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01___T_Z();
  v5 = *(void **)(a1 + 24);
  NumberOfBytesTransferred = 0;
  *(_OWORD *)(a1 + 40) = 0;
  *(_OWORD *)(a1 + 56) = 0;
  if ( !GetOverlappedResult(v5, (LPOVERLAPPED)(a1 + 40), &NumberOfBytesTransferred, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2FB,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\namedpipechannel.cpp",
      v6);
  *a2 = *(_QWORD *)(a1 + 24);
  result = a2;
  *(_QWORD *)(a1 + 24) = 0;
  return result;
}

```

## disassembly

```asm
0x180035790  mov     [rsp+arg_8], rbx
0x180035795  push    rdi
0x180035796  sub     rsp, 30h
0x18003579a  mov     rbx, rcx
0x18003579d  mov     rdi, rdx
0x1800357a0  add     rcx, 8
0x1800357a4  mov     rax, [rcx]
0x1800357a7  test    rax, rax
0x1800357aa  jz      short loc_180035817
0x1800357ac  cmp     qword ptr [rax], 0
0x1800357b0  jz      short loc_180035817
0x1800357b2  call    ??4?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@$$T@Z
0x1800357b7  mov     rcx, [rbx+18h]; hFile
0x1800357bb  lea     rdx, [rbx+28h]; lpOverlapped
0x1800357bf  xorps   xmm0, xmm0
0x1800357c2  mov     [rsp+38h+NumberOfBytesTransferred], 0
0x1800357ca  movups  xmmword ptr [rdx], xmm0
0x1800357cd  xor     r9d, r9d; bWait
0x1800357d0  lea     r8, [rsp+38h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800357d5  movups  xmmword ptr [rdx+10h], xmm0
0x1800357d9  call    cs:__imp_GetOverlappedResult
0x1800357df  test    eax, eax
0x1800357e1  jnz     short loc_1800357FA
0x1800357e3  mov     rcx, [rsp+38h]; this
0x1800357e8  lea     r8, aOnecoreWindows_29; "onecore\\windows\\accessibletech\\uiama"...
0x1800357ef  mov     edx, 2FBh; void *
0x1800357f4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800357fa  mov     rax, [rbx+18h]
0x1800357fe  mov     [rdi], rax
0x180035801  mov     rax, rdi
0x180035804  mov     qword ptr [rbx+18h], 0
0x18003580c  mov     rbx, [rsp+38h+arg_8]
0x180035811  add     rsp, 30h
0x180035815  pop     rdi
0x180035816  retn
0x180035817  mov     rcx, [rsp+38h]; this
0x18003581c  lea     r8, aOnecoreWindows_29; "onecore\\windows\\accessibletech\\uiama"...
0x180035823  mov     r9d, 8000FFFFh; char *
0x180035829  mov     edx, 2F5h; void *
0x18003582e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
