# Windows::Storage::ApplicationDataServer::GetIids(ulong *,_GUID * *)

- ea: `0x18001a420`
- end: `0x18001a4a2`
- name: `?GetIids@ApplicationDataServer@Storage@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `130`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataServer *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037b10`
- `0x180037b20`
- `0x180037b30`

## callees

- `0x18001a420`
- `0x18001a4a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a442`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a442`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataServer::GetIids(
        Windows::Storage::ApplicationDataServer *this,
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
0x18001a420  mov     [rsp+arg_0], rbx
0x18001a425  push    rdi
0x18001a426  sub     rsp, 20h
0x18001a42a  mov     qword ptr [iids], 0
0x18001a431  mov     ecx, 50h ; 'P'; cb
0x18001a436  mov     dword ptr [iidCount], 0
0x18001a43c  mov     rbx, iids
0x18001a43f  mov     rdi, iidCount
0x18001a442  call    cs:__imp_CoTaskMemAlloc
0x18001a448  mov     iids, rax; iids
0x18001a44b  test    rax, rax
0x18001a44e  jz      short loc_18001A49B
0x18001a450  movups  xmm0, xmmword ptr cs:_GUID_c3da6fb7_b744_4b45_b0b8_223a0938d0dc.Data1
0x18001a457  lea     iidCount, [rsp+28h+index]; index
0x18001a45c  mov     [rsp+28h+index], 3
0x18001a464  movdqu  xmmword ptr [rax], xmm0
0x18001a468  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001a46f  movdqu  xmmword ptr [rax+10h], xmm1
0x18001a474  movups  xmm0, xmmword ptr cs:_GUID_9e65cd69_0ba3_4e32_be29_b02de6607638.Data1
0x18001a47b  movdqu  xmmword ptr [rax+20h], xmm0
0x18001a480  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIApplicationData3@Storage@Windows@@UIClosable@Foundation@6@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001a485  mov     dword ptr [rdi], 5
0x18001a48b  xor     eax, eax
0x18001a48d  mov     [rbx], iids
0x18001a490  mov     rbx, [rsp+28h+arg_0]
0x18001a495  add     rsp, 20h
0x18001a499  pop     rdi
0x18001a49a  retn
0x18001a49b  mov     eax, 8007000Eh
0x18001a4a0  jmp     short loc_18001A490
```
