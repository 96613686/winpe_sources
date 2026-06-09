# ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>(void)

- ea: `0x18001eed0`
- end: `0x18001ef3e`
- name: `??1?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001ef40`

## callees

- `0x18001eed0`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>(
        __int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable';
  *(_DWORD *)(a1 + 24) = -1073741823;
  result = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v3 = *(_QWORD *)(a1 + 16);
  if ( v3 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *(_QWORD *)(a1 + 8);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return result;
}

```

## disassembly

```asm
0x18001eed0  mov     [rsp+arg_0], rcx
0x18001eed5  push    rbx
0x18001eed6  sub     rsp, 30h
0x18001eeda  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001eee3  mov     rbx, rcx
0x18001eee6  lea     rax, ??_7?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable'
0x18001eeed  mov     [rcx], rax
0x18001eef0  mov     dword ptr [rcx+18h], 0C0000001h
0x18001eef7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001eefe  mov     rax, [rcx]
0x18001ef01  mov     rax, [rax+10h]
0x18001ef05  call    cs:__guard_dispatch_icall_fptr
0x18001ef0b  nop
0x18001ef0c  mov     rcx, [rbx+10h]
0x18001ef10  test    rcx, rcx
0x18001ef13  jz      short loc_18001EF22
0x18001ef15  mov     rax, [rcx]
0x18001ef18  mov     rax, [rax+10h]
0x18001ef1c  call    cs:__guard_dispatch_icall_fptr
0x18001ef22  mov     rcx, [rbx+8]
0x18001ef26  test    rcx, rcx
0x18001ef29  jz      short loc_18001EF38
0x18001ef2b  mov     rax, [rcx]
0x18001ef2e  mov     rax, [rax+10h]
0x18001ef32  call    cs:__guard_dispatch_icall_fptr
0x18001ef38  add     rsp, 30h
0x18001ef3c  pop     rbx
0x18001ef3d  retn
```
