# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Core::ILowLightControlInternal,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800b2e10`
- end: `0x1800b2e6f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UILowLightControlInternal@Core@Media@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800b2d7c`
- `0x1800b2e10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b2e32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b2e32`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Core::ILowLightControlInternal,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Media::Core::ILowLightControlInternal,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800b2e10  mov     [rsp+arg_0], rbx
0x1800b2e15  push    rdi
0x1800b2e16  sub     rsp, 20h
0x1800b2e1a  mov     qword ptr [r8], 0
0x1800b2e21  mov     ecx, 20h ; ' '; cb
0x1800b2e26  mov     dword ptr [rdx], 0
0x1800b2e2c  mov     rbx, r8
0x1800b2e2f  mov     rdi, rdx
0x1800b2e32  call    cs:__imp_CoTaskMemAlloc
0x1800b2e38  mov     r8, rax
0x1800b2e3b  test    rax, rax
0x1800b2e3e  jnz     short loc_1800B2E47
0x1800b2e40  mov     eax, 8007000Eh
0x1800b2e45  jmp     short loc_1800B2E64
0x1800b2e47  lea     rdx, [rsp+28h+arg_8]
0x1800b2e4c  mov     [rsp+28h+arg_8], 0
0x1800b2e54  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UILowLightControlInternal@Core@Media@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Media::Core::ILowLightControlInternal,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800b2e59  mov     dword ptr [rdi], 2
0x1800b2e5f  xor     eax, eax
0x1800b2e61  mov     [rbx], r8
0x1800b2e64  mov     rbx, [rsp+28h+arg_0]
0x1800b2e69  add     rsp, 20h
0x1800b2e6d  pop     rdi
0x1800b2e6e  retn
```
