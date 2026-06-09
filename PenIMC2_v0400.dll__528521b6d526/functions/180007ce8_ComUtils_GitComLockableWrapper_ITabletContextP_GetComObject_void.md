# ComUtils::GitComLockableWrapper<ITabletContextP>::GetComObject(void)

- ea: `0x180007ce8`
- end: `0x180007e22`
- name: `?GetComObject@?$GitComLockableWrapper@UITabletContextP@@@ComUtils@@QEAA?AV?$CComPtr@UITabletContextP@@@ATL@@XZ`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006f5c`

## callees

- `0x180007ce8`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180007d48`
- `ole32!CoCreateInstance` at `0x180007d48`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
LPVOID *__fastcall ComUtils::GitComLockableWrapper<ITabletContextP>::GetComObject(unsigned int *a1, LPVOID *a2)
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
             &GUID_22f74d0a_694f_4f47_a5ce_ae08a6409ac8,
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
0x180007ce8  mov     [rsp-18h+arg_8], rdx
0x180007ced  push    rbp
0x180007cee  push    rbx
0x180007cef  push    rdi
0x180007cf0  mov     rbp, rsp
0x180007cf3  sub     rsp, 40h
0x180007cf7  mov     rdi, rdx
0x180007cfa  and     [rbp+var_10], 0
0x180007cfe  and     qword ptr [rdx], 0
0x180007d02  mov     r8d, 1; dwClsContext
0x180007d08  mov     [rbp+var_10], r8d
0x180007d0c  mov     ebx, [rcx]
0x180007d0e  test    ebx, ebx
0x180007d10  jz      loc_180007E16
0x180007d16  and     [rbp+arg_18], 0
0x180007d1b  mov     [rbp+arg_0], ebx
0x180007d1e  and     [rbp+arg_10], 0
0x180007d23  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007d2a  test    rcx, rcx
0x180007d2d  jnz     short loc_180007D50
0x180007d2f  lea     rax, [rbp+arg_10]
0x180007d33  mov     [rsp+40h+ppv], rax; ppv
0x180007d38  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180007d3f  xor     edx, edx; pUnkOuter
0x180007d41  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180007d48  call    cs:__imp_CoCreateInstance
0x180007d4e  jmp     short loc_180007D61
0x180007d50  mov     rax, [rcx]
0x180007d53  lea     rdx, [rbp+arg_10]
0x180007d57  mov     rax, [rax+20h]
0x180007d5b  call    cs:__guard_dispatch_icall_fptr
0x180007d61  test    eax, eax
0x180007d63  jns     short loc_180007D84
0x180007d65  mov     rcx, [rbp+arg_10]
0x180007d69  test    rcx, rcx
0x180007d6c  jz      short loc_180007D7B
0x180007d6e  mov     rax, [rcx]
0x180007d71  mov     rax, [rax+10h]
0x180007d75  call    cs:__guard_dispatch_icall_fptr
0x180007d7b  and     [rbp+arg_0], 0
0x180007d7f  jmp     loc_180007E16
0x180007d84  mov     rcx, [rbp+arg_10]
0x180007d88  mov     rax, [rcx]
0x180007d8b  lea     r9, [rbp+arg_18]
0x180007d8f  lea     r8, _GUID_22f74d0a_694f_4f47_a5ce_ae08a6409ac8
0x180007d96  mov     edx, ebx
0x180007d98  mov     rax, [rax+28h]
0x180007d9c  call    cs:__guard_dispatch_icall_fptr
0x180007da2  mov     ebx, eax
0x180007da4  mov     rcx, [rbp+arg_10]
0x180007da8  test    rcx, rcx
0x180007dab  jz      short loc_180007DBA
0x180007dad  mov     rdx, [rcx]
0x180007db0  mov     rax, [rdx+10h]
0x180007db4  call    cs:__guard_dispatch_icall_fptr
0x180007dba  and     [rbp+arg_0], 0
0x180007dbe  test    ebx, ebx
0x180007dc0  js      short loc_180007E16
0x180007dc2  mov     rbx, [rbp+arg_18]
0x180007dc6  cmp     [rdi], rbx
0x180007dc9  jz      short loc_180007E05
0x180007dcb  mov     [rbp+arg_10], rbx
0x180007dcf  test    rbx, rbx
0x180007dd2  jz      short loc_180007DE5
0x180007dd4  mov     rax, [rbx]
0x180007dd7  mov     rcx, rbx
0x180007dda  mov     rax, [rax+8]
0x180007dde  call    cs:__guard_dispatch_icall_fptr
0x180007de4  nop
0x180007de5  mov     rcx, [rdi]
0x180007de8  mov     [rbp+arg_10], rcx
0x180007dec  mov     [rdi], rbx
0x180007def  test    rcx, rcx
0x180007df2  jz      short loc_180007E01
0x180007df4  mov     rax, [rcx]
0x180007df7  mov     rax, [rax+10h]
0x180007dfb  call    cs:__guard_dispatch_icall_fptr
0x180007e01  mov     rbx, [rbp+arg_18]
0x180007e05  mov     rax, [rbx]
0x180007e08  mov     rcx, rbx
0x180007e0b  mov     rax, [rax+10h]
0x180007e0f  call    cs:__guard_dispatch_icall_fptr
0x180007e15  nop
0x180007e16  mov     rax, rdi
0x180007e19  add     rsp, 40h
0x180007e1d  pop     rdi
0x180007e1e  pop     rbx
0x180007e1f  pop     rbp
0x180007e20  retn
```
