# CreateSystemObjectServer::_IsRequestApproved(_GUID const &)

- ea: `0x140008ed0`
- end: `0x140008fa3`
- name: `?_IsRequestApproved@CreateSystemObjectServer@@EEAA_NAEBU_GUID@@@Z`
- size: `211`
- prototype: `bool __fastcall(const unsigned __int16 **this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140004340`
- `0x1400079b4`
- `0x140008010`
- `0x140008ed0`
- `0x14000923c`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140008f3d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140008f3d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140008f8a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140008f8a`

## string_xrefs

- `0x140008f00`: `SOFTWARE\Microsoft\Windows\CurrentVersion\CloudExperienceHost\RegisteredClsids`
- `0x140008f4f`: `shellcommon\shell\cloudexperiencehost\onecore\exe\cloudexperiencehostbroker.cpp`

## pseudocode

```c
bool __fastcall CreateSystemObjectServer::_IsRequestApproved(const unsigned __int16 **this, const struct _GUID *a2)
{
  bool result; // al
  GUID *v3; // rbx
  HRESULT v4; // eax
  bool v5; // bl
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v8; // [rsp+40h] [rbp+8h] BYREF
  LPVOID v9; // [rsp+50h] [rbp+18h] BYREF

  result = IsClsidApproved(a2, this[2]);
  if ( result )
  {
    v9 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    v3 = &GUID_4cd0569b_0239_4602_84a3_cfc5a9167c82;
    if ( !IsClsidApproved(
            &GUID_4cd0569b_0239_4602_84a3_cfc5a9167c82,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\RegisteredClsids") )
      v3 = &GUID_baffdff4_240b_4c36_8173_70c8301d7753;
    v4 = CoCreateInstance(v3, 0, 1u, &GUID_06d48c99_bab0_4e6e_ae56_358cec845441, &v9);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"shellcommon\\shell\\cloudexperiencehost\\onecore\\exe\\cloudexperiencehostbroker.cpp",
        (const char *)(unsigned int)v4,
        ppv);
    wil::CoImpersonateClient(&v8);
    v5 = (*(unsigned int (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 24LL))(v9) == 0;
    if ( v8 )
      CoRevertToSelf();
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x140008ed0  push    rbx
0x140008ed2  sub     rsp, 30h
0x140008ed6  mov     rax, rdx
0x140008ed9  mov     rdx, [rcx+10h]; unsigned __int16 *
0x140008edd  mov     rcx, rax; struct _GUID *
0x140008ee0  call    ?IsClsidApproved@@YA_NAEBU_GUID@@PEBG@Z; IsClsidApproved(_GUID const &,ushort const *)
0x140008ee5  test    al, al
0x140008ee7  jz      loc_140008F9D
0x140008eed  mov     [rsp+38h+arg_10], 0
0x140008ef6  lea     rcx, [rsp+38h+arg_10]
0x140008efb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140008f00  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140008f07  lea     rbx, _GUID_4cd0569b_0239_4602_84a3_cfc5a9167c82
0x140008f0e  mov     rcx, rbx; struct _GUID *
0x140008f11  call    ?IsClsidApproved@@YA_NAEBU_GUID@@PEBG@Z; IsClsidApproved(_GUID const &,ushort const *)
0x140008f16  lea     rcx, _GUID_baffdff4_240b_4c36_8173_70c8301d7753
0x140008f1d  test    al, al
0x140008f1f  cmovz   rbx, rcx
0x140008f23  lea     rax, [rsp+38h+arg_10]
0x140008f28  mov     qword ptr [rsp+38h+ppv], rax; int
0x140008f2d  lea     r9, _GUID_06d48c99_bab0_4e6e_ae56_358cec845441; riid
0x140008f34  xor     edx, edx; pUnkOuter
0x140008f36  lea     r8d, [rdx+1]; dwClsContext
0x140008f3a  mov     rcx, rbx; rclsid
0x140008f3d  call    cs:__imp_CoCreateInstance
0x140008f43  mov     rcx, [rsp+38h]; this
0x140008f48  test    eax, eax
0x140008f4a  jns     short loc_140008F61
0x140008f4c  mov     r9d, eax; char *
0x140008f4f  lea     r8, aShellcommonShe; "shellcommon\\shell\\cloudexperiencehost"...
0x140008f56  mov     edx, 23h ; '#'; void *
0x140008f5b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008f61  lea     rcx, [rsp+38h+arg_0]
0x140008f66  call    ?CoImpersonateClient@wil@@YA?AV?$unique_call@P6AJXZ$1?CoRevertToSelf@@YAJXZ$00@1@XZ; wil::CoImpersonateClient(void)
0x140008f6b  nop
0x140008f6c  mov     rcx, [rsp+38h+arg_10]
0x140008f71  mov     rax, [rcx]
0x140008f74  mov     rax, [rax+18h]
0x140008f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f7d  nop
0x140008f7e  test    eax, eax
0x140008f80  setz    bl
0x140008f83  cmp     [rsp+38h+arg_0], 0
0x140008f88  jz      short loc_140008F91
0x140008f8a  call    cs:__imp_CoRevertToSelf
0x140008f90  nop
0x140008f91  lea     rcx, [rsp+38h+arg_10]
0x140008f96  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140008f9b  mov     al, bl
0x140008f9d  add     rsp, 30h
0x140008fa1  pop     rbx
0x140008fa2  retn
```
