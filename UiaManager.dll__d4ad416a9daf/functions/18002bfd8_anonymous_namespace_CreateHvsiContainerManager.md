# _anonymous_namespace_::CreateHvsiContainerManager

- ea: `0x18002bfd8`
- end: `0x18002c048`
- name: `_anonymous_namespace_::CreateHvsiContainerManager`
- size: `112`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011c04`
- `0x18002be30`
- `0x18002bef0`

## callees

- `0x1800054f8`
- `0x18002bfd8`
- `0x180031540`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c01a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c01a`

## string_xrefs

- `0x18002c02c`: `onecore\windows\accessibletech\common\hvsicontainerapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPVOID *__fastcall anonymous_namespace_::CreateHvsiContainerManager(LPVOID *ppv)
{
  HRESULT Instance; // eax
  int ppva; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppv);
  Instance = CoCreateInstance(
               &GUID_17e24fbc_4d64_459e_8595_fd7154c6d113,
               0,
               4u,
               &GUID_2524d4e0_180b_40f1_99b3_73b65847d0df,
               ppv);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\hvsicontainerapi.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  return ppv;
}

```

## disassembly

```asm
0x18002bfd8  mov     [rsp+arg_0], rcx
0x18002bfdd  push    rbx
0x18002bfde  sub     rsp, 40h
0x18002bfe2  mov     rbx, rcx
0x18002bfe5  mov     [rsp+48h+var_18], 0
0x18002bfed  mov     qword ptr [rcx], 0
0x18002bff4  mov     [rsp+48h+var_18], 1
0x18002bffc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c001  mov     qword ptr [rsp+48h+ppv], rbx; int
0x18002c006  lea     r9, _GUID_2524d4e0_180b_40f1_99b3_73b65847d0df; riid
0x18002c00d  xor     edx, edx; pUnkOuter
0x18002c00f  lea     r8d, [rdx+4]; dwClsContext
0x18002c013  lea     rcx, _GUID_17e24fbc_4d64_459e_8595_fd7154c6d113; rclsid
0x18002c01a  call    cs:__imp_CoCreateInstance
0x18002c020  test    eax, eax
0x18002c022  jns     short loc_18002C03E
0x18002c024  mov     rcx, [rsp+48h]; this
0x18002c029  mov     r9d, eax; char *
0x18002c02c  lea     r8, aOnecoreWindows_23; "onecore\\windows\\accessibletech\\commo"...
0x18002c033  mov     edx, 17h; void *
0x18002c038  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c03e  mov     rax, rbx
0x18002c041  add     rsp, 40h
0x18002c045  pop     rbx
0x18002c046  retn
```
