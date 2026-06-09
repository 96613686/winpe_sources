# ATL::CComGITPtr<IUnknown>::~CComGITPtr<IUnknown>(void)

- ea: `0x18000cb1c`
- end: `0x18000cbb6`
- name: `??1?$CComGITPtr@UIUnknown@@@ATL@@QEAA@XZ`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f1c5`

## callees

- `0x18000cb1c`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000cb5e`
- `ole32!CoCreateInstance` at `0x18000cb5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ATL::CComGITPtr<IUnknown>::~CComGITPtr<IUnknown>(_DWORD *a1)
{
  HRESULT v2; // eax
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  if ( *a1 )
  {
    ppv = 0;
    if ( ATL::_pAtlModule )
      v2 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, LPVOID *))(*(_QWORD *)ATL::_pAtlModule + 32LL))(
             ATL::_pAtlModule,
             &ppv);
    else
      v2 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
    if ( v2 >= 0 && (*(int (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, (unsigned int)*a1) >= 0 )
      *a1 = 0;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
}

```

## disassembly

```asm
0x18000cb1c  push    rbx
0x18000cb1e  sub     rsp, 30h
0x18000cb22  mov     rbx, rcx
0x18000cb25  cmp     dword ptr [rcx], 0
0x18000cb28  jz      loc_18000CBB0
0x18000cb2e  and     [rsp+38h+arg_0], 0
0x18000cb34  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cb3b  test    rcx, rcx
0x18000cb3e  jnz     short loc_18000CB66
0x18000cb40  lea     rax, [rsp+38h+arg_0]
0x18000cb45  mov     [rsp+38h+ppv], rax; ppv
0x18000cb4a  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000cb51  xor     edx, edx; pUnkOuter
0x18000cb53  lea     r8d, [rcx+1]; dwClsContext
0x18000cb57  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000cb5e  call    cs:__imp_CoCreateInstance
0x18000cb64  jmp     short loc_18000CB78
0x18000cb66  mov     rax, [rcx]
0x18000cb69  lea     rdx, [rsp+38h+arg_0]
0x18000cb6e  mov     rax, [rax+20h]
0x18000cb72  call    cs:__guard_dispatch_icall_fptr
0x18000cb78  test    eax, eax
0x18000cb7a  jns     short loc_18000CB7E
0x18000cb7c  jmp     short loc_18000CB99
0x18000cb7e  mov     rcx, [rsp+38h+arg_0]
0x18000cb83  mov     rax, [rcx]
0x18000cb86  mov     edx, [rbx]
0x18000cb88  mov     rax, [rax+20h]
0x18000cb8c  call    cs:__guard_dispatch_icall_fptr
0x18000cb92  test    eax, eax
0x18000cb94  js      short loc_18000CB99
0x18000cb96  and     dword ptr [rbx], 0
0x18000cb99  mov     rcx, [rsp+38h+arg_0]
0x18000cb9e  test    rcx, rcx
0x18000cba1  jz      short loc_18000CBB0
0x18000cba3  mov     rax, [rcx]
0x18000cba6  mov     rax, [rax+10h]
0x18000cbaa  call    cs:__guard_dispatch_icall_fptr
0x18000cbb0  add     rsp, 30h
0x18000cbb4  pop     rbx
0x18000cbb5  retn
```
