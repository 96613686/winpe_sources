# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IClosable,Windows::Foundation::IMemoryBufferReference,Microsoft::WRL::CloakedIid<Windows::Foundation::IMemoryBufferByteAccess>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18003e0b0`
- end: `0x18003e11a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIClosable@Foundation@Windows@@UIMemoryBufferReference@56@U?$CloakedIid@UIMemoryBufferByteAccess@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003e120`

## callees

- `0x18003e080`
- `0x18003e0b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e0d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e0d2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IClosable,Windows::Foundation::IMemoryBufferReference,Microsoft::WRL::CloakedIid<Windows::Foundation::IMemoryBufferByteAccess>,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IMemoryBufferReference,Microsoft::WRL::CloakedIid<Windows::Foundation::IMemoryBufferByteAccess>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18003e0b0  mov     [rsp+arg_0], rbx
0x18003e0b5  push    rdi
0x18003e0b6  sub     rsp, 20h
0x18003e0ba  mov     qword ptr [r8], 0
0x18003e0c1  mov     ecx, 30h ; '0'; cb
0x18003e0c6  mov     dword ptr [rdx], 0
0x18003e0cc  mov     rbx, r8
0x18003e0cf  mov     rdi, rdx
0x18003e0d2  call    cs:__imp_CoTaskMemAlloc
0x18003e0d8  mov     r8, rax
0x18003e0db  test    rax, rax
0x18003e0de  jnz     short loc_18003E0E7
0x18003e0e0  mov     eax, 8007000Eh
0x18003e0e5  jmp     short loc_18003E10F
0x18003e0e7  movups  xmm0, xmmword ptr cs:_GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e.Data1
0x18003e0ee  lea     rdx, [rsp+28h+arg_8]
0x18003e0f3  mov     [rsp+28h+arg_8], 1
0x18003e0fb  movdqu  xmmword ptr [rax], xmm0
0x18003e0ff  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIMemoryBufferReference@Foundation@Windows@@U?$CloakedIid@UIMemoryBufferByteAccess@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IMemoryBufferReference,Microsoft::WRL::CloakedIid<Windows::Foundation::IMemoryBufferByteAccess>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003e104  mov     dword ptr [rdi], 3
0x18003e10a  xor     eax, eax
0x18003e10c  mov     [rbx], r8
0x18003e10f  mov     rbx, [rsp+28h+arg_0]
0x18003e114  add     rsp, 20h
0x18003e118  pop     rdi
0x18003e119  retn
```
