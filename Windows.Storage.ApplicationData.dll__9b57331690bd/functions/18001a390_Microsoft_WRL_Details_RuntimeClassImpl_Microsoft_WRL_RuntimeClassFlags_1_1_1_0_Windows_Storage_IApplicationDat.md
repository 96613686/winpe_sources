# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001a390`
- end: `0x18001a412`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIApplicationData@Storage@Windows@@UIApplicationData2@56@UIApplicationData3@56@UIClosable@Foundation@6@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `130`
- prototype: `HRESULT __fastcall(Windows::Storage::RestrictedApplicationDataServer *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e3b0`
- `0x18002e3c0`
- `0x18002e3d0`

## callees

- `0x18001a390`
- `0x18001a4a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a3b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a3b2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::GetIids(
        Windows::Storage::RestrictedApplicationDataServer *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase> *v6; // rcx
  __int64 result; // rax
  _GUID *v8; // r8
  unsigned int index; // [rsp+38h] [rbp+10h] BYREF

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x50u);
  if ( !v5 )
    return 2147942414LL;
  index = 3;
  *v5 = GUID_c3da6fb7_b744_4b45_b0b8_223a0938d0dc;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_9e65cd69_0ba3_4e32_be29_b02de6607638;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &index,
    v5);
  *iidCount = 5;
  result = 0;
  *iids = v8;
  return result;
}

```

## disassembly

```asm
0x18001a390  mov     [rsp+arg_0], rbx
0x18001a395  push    rdi
0x18001a396  sub     rsp, 20h
0x18001a39a  mov     qword ptr [iids], 0
0x18001a3a1  mov     ecx, 50h ; 'P'; cb
0x18001a3a6  mov     dword ptr [iidCount], 0
0x18001a3ac  mov     rbx, iids
0x18001a3af  mov     rdi, iidCount
0x18001a3b2  call    cs:__imp_CoTaskMemAlloc
0x18001a3b8  mov     iids, rax; iids
0x18001a3bb  test    rax, rax
0x18001a3be  jnz     short loc_18001A3C7
0x18001a3c0  mov     eax, 8007000Eh
0x18001a3c5  jmp     short loc_18001A407
0x18001a3c7  movups  xmm0, xmmword ptr cs:_GUID_c3da6fb7_b744_4b45_b0b8_223a0938d0dc.Data1
0x18001a3ce  lea     iidCount, [rsp+28h+index]; index
0x18001a3d3  mov     [rsp+28h+index], 3
0x18001a3db  movdqu  xmmword ptr [rax], xmm0
0x18001a3df  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001a3e6  movdqu  xmmword ptr [rax+10h], xmm1
0x18001a3eb  movups  xmm0, xmmword ptr cs:_GUID_9e65cd69_0ba3_4e32_be29_b02de6607638.Data1
0x18001a3f2  movdqu  xmmword ptr [rax+20h], xmm0
0x18001a3f7  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIApplicationData3@Storage@Windows@@UIClosable@Foundation@6@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z
0x18001a3fc  mov     dword ptr [rdi], 5
0x18001a402  xor     eax, eax
0x18001a404  mov     [rbx], iids
0x18001a407  mov     rbx, [rsp+28h+arg_0]
0x18001a40c  add     rsp, 20h
0x18001a410  pop     rdi
0x18001a411  retn
```
