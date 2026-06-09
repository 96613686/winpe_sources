# ComUtils::GitComLockableWrapper<IUnknown>::GetComObject(void)

- ea: `0x18000c9e0`
- end: `0x18000cb1a`
- name: `?GetComObject@?$GitComLockableWrapper@UIUnknown@@@ComUtils@@QEAA?AV?$CComPtr@UIUnknown@@@ATL@@XZ`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c8c0`
- `0x18000c950`

## callees

- `0x18000c9e0`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000ca40`
- `ole32!CoCreateInstance` at `0x18000ca40`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
LPVOID *__fastcall ComUtils::GitComLockableWrapper<IUnknown>::GetComObject(unsigned int *a1, LPVOID *a2)
{
  unsigned int v3; // ebx
  HRESULT v4; // eax
  int v5; // ebx
  void *v6; // rbx
  LPVOID v7; // rcx
  LPVOID ppv; // [rsp+70h] [rbp+30h] BYREF
  void *v10; // [rsp+78h] [rbp+38h] BYREF

  *a2 = 0;
  v3 = *a1;
  if ( *a1 )
  {
    v10 = 0;
    ppv = 0;
    if ( ATL::_pAtlModule )
      v4 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, LPVOID *))(*(_QWORD *)ATL::_pAtlModule + 32LL))(
             ATL::_pAtlModule,
             &ppv);
    else
      v4 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
    if ( v4 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, void **))(*(_QWORD *)ppv + 40LL))(
             ppv,
             v3,
             &GUID_00000000_0000_0000_c000_000000000046,
             &v10);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v5 >= 0 )
      {
        v6 = v10;
        if ( *a2 != v10 )
        {
          ppv = v10;
          if ( v10 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 8LL))(v10);
          ppv = *a2;
          v7 = ppv;
          *a2 = v6;
          if ( v7 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
          v6 = v10;
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
      }
    }
    else if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18000c9e0  mov     [rsp-18h+arg_8], rdx
0x18000c9e5  push    rbp
0x18000c9e6  push    rbx
0x18000c9e7  push    rdi
0x18000c9e8  mov     rbp, rsp
0x18000c9eb  sub     rsp, 40h
0x18000c9ef  mov     rdi, rdx
0x18000c9f2  and     [rbp+var_10], 0
0x18000c9f6  and     qword ptr [rdx], 0
0x18000c9fa  mov     r8d, 1; dwClsContext
0x18000ca00  mov     [rbp+var_10], r8d
0x18000ca04  mov     ebx, [rcx]
0x18000ca06  test    ebx, ebx
0x18000ca08  jz      loc_18000CB0E
0x18000ca0e  and     [rbp+arg_18], 0
0x18000ca13  mov     [rbp+arg_0], ebx
0x18000ca16  and     [rbp+arg_10], 0
0x18000ca1b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ca22  test    rcx, rcx
0x18000ca25  jnz     short loc_18000CA48
0x18000ca27  lea     rax, [rbp+arg_10]
0x18000ca2b  mov     [rsp+40h+ppv], rax; ppv
0x18000ca30  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000ca37  xor     edx, edx; pUnkOuter
0x18000ca39  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000ca40  call    cs:__imp_CoCreateInstance
0x18000ca46  jmp     short loc_18000CA59
0x18000ca48  mov     rax, [rcx]
0x18000ca4b  lea     rdx, [rbp+arg_10]
0x18000ca4f  mov     rax, [rax+20h]
0x18000ca53  call    cs:__guard_dispatch_icall_fptr
0x18000ca59  test    eax, eax
0x18000ca5b  jns     short loc_18000CA7C
0x18000ca5d  mov     rcx, [rbp+arg_10]
0x18000ca61  test    rcx, rcx
0x18000ca64  jz      short loc_18000CA73
0x18000ca66  mov     rax, [rcx]
0x18000ca69  mov     rax, [rax+10h]
0x18000ca6d  call    cs:__guard_dispatch_icall_fptr
0x18000ca73  and     [rbp+arg_0], 0
0x18000ca77  jmp     loc_18000CB0E
0x18000ca7c  mov     rcx, [rbp+arg_10]
0x18000ca80  mov     rax, [rcx]
0x18000ca83  lea     r9, [rbp+arg_18]
0x18000ca87  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x18000ca8e  mov     edx, ebx
0x18000ca90  mov     rax, [rax+28h]
0x18000ca94  call    cs:__guard_dispatch_icall_fptr
0x18000ca9a  mov     ebx, eax
0x18000ca9c  mov     rcx, [rbp+arg_10]
0x18000caa0  test    rcx, rcx
0x18000caa3  jz      short loc_18000CAB2
0x18000caa5  mov     rdx, [rcx]
0x18000caa8  mov     rax, [rdx+10h]
0x18000caac  call    cs:__guard_dispatch_icall_fptr
0x18000cab2  and     [rbp+arg_0], 0
0x18000cab6  test    ebx, ebx
0x18000cab8  js      short loc_18000CB0E
0x18000caba  mov     rbx, [rbp+arg_18]
0x18000cabe  cmp     [rdi], rbx
0x18000cac1  jz      short loc_18000CAFD
0x18000cac3  mov     [rbp+arg_10], rbx
0x18000cac7  test    rbx, rbx
0x18000caca  jz      short loc_18000CADD
0x18000cacc  mov     rax, [rbx]
0x18000cacf  mov     rcx, rbx
0x18000cad2  mov     rax, [rax+8]
0x18000cad6  call    cs:__guard_dispatch_icall_fptr
0x18000cadc  nop
0x18000cadd  mov     rcx, [rdi]
0x18000cae0  mov     [rbp+arg_10], rcx
0x18000cae4  mov     [rdi], rbx
0x18000cae7  test    rcx, rcx
0x18000caea  jz      short loc_18000CAF9
0x18000caec  mov     rax, [rcx]
0x18000caef  mov     rax, [rax+10h]
0x18000caf3  call    cs:__guard_dispatch_icall_fptr
0x18000caf9  mov     rbx, [rbp+arg_18]
0x18000cafd  mov     rax, [rbx]
0x18000cb00  mov     rcx, rbx
0x18000cb03  mov     rax, [rax+10h]
0x18000cb07  call    cs:__guard_dispatch_icall_fptr
0x18000cb0d  nop
0x18000cb0e  mov     rax, rdi
0x18000cb11  add     rsp, 40h
0x18000cb15  pop     rdi
0x18000cb16  pop     rbx
0x18000cb17  pop     rbp
0x18000cb18  retn
```
