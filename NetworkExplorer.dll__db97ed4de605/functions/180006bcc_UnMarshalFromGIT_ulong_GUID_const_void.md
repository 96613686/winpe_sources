# UnMarshalFromGIT(ulong,_GUID const &,void * *)

- ea: `0x180006bcc`
- end: `0x180006c4e`
- name: `?UnMarshalFromGIT@@YAJKAEBU_GUID@@PEAPEAX@Z`
- size: `130`
- prototype: `__int64 __fastcall(unsigned int, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cc44`
- `0x18000de78`
- `0x18000dee0`
- `0x18000df84`

## callees

- `0x180006bcc`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006c0b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006c0b`

## pseudocode

```c
__int64 __fastcall UnMarshalFromGIT(unsigned int a1, const struct _GUID *a2, void **a3)
{
  HRESULT v6; // ebx
  LPVOID ppv; // [rsp+70h] [rbp+18h] BYREF

  *a3 = 0;
  ppv = 0;
  v6 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const struct _GUID *, void **))(*(_QWORD *)ppv + 40LL))(
           ppv,
           a1,
           a2,
           a3);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006bcc  push    rbx
0x180006bce  push    rbp
0x180006bcf  push    rsi
0x180006bd0  push    rdi
0x180006bd1  sub     rsp, 38h
0x180006bd5  mov     rsi, rdx
0x180006bd8  mov     qword ptr [r8], 0
0x180006bdf  xor     edx, edx; pUnkOuter
0x180006be1  mov     [rsp+58h+arg_10], 0
0x180006bea  mov     rdi, r8
0x180006bed  lea     rax, [rsp+58h+arg_10]
0x180006bf2  mov     ebp, ecx
0x180006bf4  mov     [rsp+58h+ppv], rax; ppv
0x180006bf9  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180006c00  lea     r8d, [rdx+1]; dwClsContext
0x180006c04  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180006c0b  call    cs:__imp_CoCreateInstance
0x180006c11  mov     ebx, eax
0x180006c13  test    eax, eax
0x180006c15  js      short loc_180006C43
0x180006c17  mov     rcx, [rsp+58h+arg_10]
0x180006c1c  mov     r9, rdi
0x180006c1f  mov     r8, rsi
0x180006c22  mov     edx, ebp
0x180006c24  mov     rax, [rcx]
0x180006c27  mov     rax, [rax+28h]
0x180006c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c30  mov     rcx, [rsp+58h+arg_10]
0x180006c35  mov     ebx, eax
0x180006c37  mov     rax, [rcx]
0x180006c3a  mov     rax, [rax+10h]
0x180006c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c43  mov     eax, ebx
0x180006c45  add     rsp, 38h
0x180006c49  pop     rdi
0x180006c4a  pop     rsi
0x180006c4b  pop     rbp
0x180006c4c  pop     rbx
0x180006c4d  retn
```
