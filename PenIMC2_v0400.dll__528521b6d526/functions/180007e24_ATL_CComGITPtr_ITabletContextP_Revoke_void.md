# ATL::CComGITPtr<ITabletContextP>::Revoke(void)

- ea: `0x180007e24`
- end: `0x180007ecc`
- name: `?Revoke@?$CComGITPtr@UITabletContextP@@@ATL@@QEAAJXZ`
- size: `168`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001edc`
- `0x1800020a8`
- `0x1800062a0`
- `0x180007ecc`
- `0x180009f28`
- `0x18000bddc`

## callees

- `0x180007e24`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180007e69`
- `ole32!CoCreateInstance` at `0x180007e69`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComGITPtr<ITabletContextP>::Revoke(_DWORD *a1)
{
  int v2; // edi
  HRESULT v3; // eax
  LPVOID v5; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  if ( *a1 )
  {
    v5 = 0;
    if ( ATL::_pAtlModule )
      v3 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, LPVOID *))(*(_QWORD *)ATL::_pAtlModule + 32LL))(
             ATL::_pAtlModule,
             &v5);
    else
      v3 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &v5);
    v2 = v3;
    if ( v3 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v5 + 32LL))(v5, (unsigned int)*a1);
      if ( v2 >= 0 )
        *a1 = 0;
    }
    if ( v5 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180007e24  mov     r11, rsp
0x180007e27  mov     [r11+10h], rbx
0x180007e2b  push    rdi
0x180007e2c  sub     rsp, 30h
0x180007e30  mov     rbx, rcx
0x180007e33  xor     edi, edi
0x180007e35  cmp     [rcx], edi
0x180007e37  jz      loc_180007EBF
0x180007e3d  and     [r11+8], rdi
0x180007e41  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007e48  test    rcx, rcx
0x180007e4b  jnz     short loc_180007E71
0x180007e4d  lea     rax, [r11+8]
0x180007e51  mov     [r11-18h], rax
0x180007e55  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180007e5c  xor     edx, edx; pUnkOuter
0x180007e5e  lea     r8d, [rdi+1]; dwClsContext
0x180007e62  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180007e69  call    cs:__imp_CoCreateInstance
0x180007e6f  jmp     short loc_180007E83
0x180007e71  mov     rax, [rcx]
0x180007e74  lea     rdx, [rsp+38h+arg_0]
0x180007e79  mov     rax, [rax+20h]
0x180007e7d  call    cs:__guard_dispatch_icall_fptr
0x180007e83  mov     edi, eax
0x180007e85  test    eax, eax
0x180007e87  jns     short loc_180007E8B
0x180007e89  jmp     short loc_180007EA8
0x180007e8b  mov     rcx, [rsp+38h+arg_0]
0x180007e90  mov     rax, [rcx]
0x180007e93  mov     edx, [rbx]
0x180007e95  mov     rax, [rax+20h]
0x180007e99  call    cs:__guard_dispatch_icall_fptr
0x180007e9f  mov     edi, eax
0x180007ea1  test    eax, eax
0x180007ea3  js      short loc_180007EA8
0x180007ea5  and     dword ptr [rbx], 0
0x180007ea8  mov     rcx, [rsp+38h+arg_0]
0x180007ead  test    rcx, rcx
0x180007eb0  jz      short loc_180007EBF
0x180007eb2  mov     rax, [rcx]
0x180007eb5  mov     rax, [rax+10h]
0x180007eb9  call    cs:__guard_dispatch_icall_fptr
0x180007ebf  mov     eax, edi
0x180007ec1  mov     rbx, [rsp+38h+arg_8]
0x180007ec6  add     rsp, 30h
0x180007eca  pop     rdi
0x180007ecb  retn
```
