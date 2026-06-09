# UiaEndpointNotifier::GetUiaManagerEndpointRegistration(void)

- ea: `0x18003187c`
- end: `0x1800318e6`
- name: `?GetUiaManagerEndpointRegistration@UiaEndpointNotifier@@CA?AV?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `106`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180031560`
- `0x180031640`
- `0x180031780`

## callees

- `0x180031540`
- `0x18003187c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800318b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800318b8`

## string_xrefs

- `0x1800318ca`: `onecore\windows\accessibletech\uiamanager\dll\uiaendpointnotifier.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID *__fastcall UiaEndpointNotifier::GetUiaManagerEndpointRegistration(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(&CLSID_UiaManager, 0, 4u, &GUID_05286245_d789_4e02_97c9_f27f01db10ca, a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiaendpointnotifier.cpp",
      (const char *)(unsigned int)Instance,
      v4);
  return a1;
}

```

## disassembly

```asm
0x18003187c  mov     rax, rsp
0x18003187f  mov     [rax+8], rcx
0x180031883  push    rbx
0x180031884  sub     rsp, 40h
0x180031888  mov     rbx, rcx
0x18003188b  mov     dword ptr [rax-18h], 0
0x180031892  mov     dword ptr [rax-18h], 1
0x180031899  mov     qword ptr [rcx], 0
0x1800318a0  mov     [rax-28h], rcx
0x1800318a4  lea     r9, _GUID_05286245_d789_4e02_97c9_f27f01db10ca; riid
0x1800318ab  xor     edx, edx; pUnkOuter
0x1800318ad  lea     r8d, [rdx+4]; dwClsContext
0x1800318b1  lea     rcx, CLSID_UiaManager; rclsid
0x1800318b8  call    cs:__imp_CoCreateInstance
0x1800318be  test    eax, eax
0x1800318c0  jns     short loc_1800318DC
0x1800318c2  mov     rcx, [rsp+48h]; this
0x1800318c7  mov     r9d, eax; char *
0x1800318ca  lea     r8, aOnecoreWindows_8; "onecore\\windows\\accessibletech\\uiama"...
0x1800318d1  mov     edx, 9Ch; void *
0x1800318d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800318dc  mov     rax, rbx
0x1800318df  add     rsp, 40h
0x1800318e3  pop     rbx
0x1800318e4  retn
```
