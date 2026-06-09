# wil::CoCreateInstance<IDeviceBroker,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x18004fb6c`
- end: `0x18004fbd4`
- name: `??$CoCreateInstance@UIDeviceBroker@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIDeviceBroker@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `104`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004fbdc`

## callees

- `0x18000e0c0`
- `0x18004fb6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004fba7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004fba7`

## string_xrefs

- `0x18004fbc2`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<IDeviceBroker,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(&CLSID_DeviceBroker, 0, 1u, &GUID_8604b268_34a6_4b1a_a59f_cdbd8379fd98, a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)Instance,
      v4);
  return a1;
}

```

## disassembly

```asm
0x18004fb6c  mov     rax, rsp
0x18004fb6f  mov     [rax+8], rcx
0x18004fb73  push    rbx
0x18004fb74  sub     rsp, 40h
0x18004fb78  mov     rbx, rcx
0x18004fb7b  mov     dword ptr [rax-18h], 0
0x18004fb82  mov     r8d, 1; dwClsContext
0x18004fb88  mov     [rax-18h], r8d
0x18004fb8c  mov     qword ptr [rcx], 0
0x18004fb93  mov     [rax-28h], rcx
0x18004fb97  lea     r9, _GUID_8604b268_34a6_4b1a_a59f_cdbd8379fd98; riid
0x18004fb9e  xor     edx, edx; pUnkOuter
0x18004fba0  lea     rcx, CLSID_DeviceBroker; rclsid
0x18004fba7  call    cs:__imp_CoCreateInstance
0x18004fbad  test    eax, eax
0x18004fbaf  js      short loc_18004FBBA
0x18004fbb1  mov     rax, rbx
0x18004fbb4  add     rsp, 40h
0x18004fbb8  pop     rbx
0x18004fbb9  retn
0x18004fbba  mov     rcx, [rsp+48h]; this
0x18004fbbf  mov     r9d, eax; char *
0x18004fbc2  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004fbc9  mov     edx, 1CBEh; void *
0x18004fbce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
