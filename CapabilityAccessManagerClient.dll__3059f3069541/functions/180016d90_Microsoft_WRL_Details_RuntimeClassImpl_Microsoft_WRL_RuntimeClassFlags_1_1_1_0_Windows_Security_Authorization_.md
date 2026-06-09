# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,Windows::Security::Authorization::AppCapabilityAccess::IAppCapability2,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180016d90`
- end: `0x180016dfa`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAppCapability@AppCapabilityAccess@Authorization@Security@Windows@@UIAppCapability2@5678@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016e00`

## callees

- `0x180015de0`
- `0x180016d90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016db2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016db2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,Windows::Security::Authorization::AppCapabilityAccess::IAppCapability2,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_4c49d915_8a2a_4295_9437_2df7c396aff4;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Security::Authorization::AppCapabilityAccess::IAppCapability2,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180016d90  mov     [rsp+arg_0], rbx
0x180016d95  push    rdi
0x180016d96  sub     rsp, 20h
0x180016d9a  mov     qword ptr [r8], 0
0x180016da1  mov     ecx, 30h ; '0'; cb
0x180016da6  mov     dword ptr [rdx], 0
0x180016dac  mov     rbx, r8
0x180016daf  mov     rdi, rdx
0x180016db2  call    cs:__imp_CoTaskMemAlloc
0x180016db8  mov     r8, rax
0x180016dbb  test    rax, rax
0x180016dbe  jnz     short loc_180016DC7
0x180016dc0  mov     eax, 8007000Eh
0x180016dc5  jmp     short loc_180016DEF
0x180016dc7  movups  xmm0, xmmword ptr cs:_GUID_4c49d915_8a2a_4295_9437_2df7c396aff4.Data1
0x180016dce  lea     rdx, [rsp+28h+arg_8]
0x180016dd3  mov     [rsp+28h+arg_8], 1
0x180016ddb  movdqu  xmmword ptr [rax], xmm0
0x180016ddf  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIAppCapability2@AppCapabilityAccess@Authorization@Security@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Security::Authorization::AppCapabilityAccess::IAppCapability2,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180016de4  mov     dword ptr [rdi], 3
0x180016dea  xor     eax, eax
0x180016dec  mov     [rbx], r8
0x180016def  mov     rbx, [rsp+28h+arg_0]
0x180016df4  add     rsp, 20h
0x180016df8  pop     rdi
0x180016df9  retn
```
