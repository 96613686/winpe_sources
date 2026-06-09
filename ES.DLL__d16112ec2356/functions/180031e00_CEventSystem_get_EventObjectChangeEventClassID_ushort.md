# CEventSystem::get_EventObjectChangeEventClassID(ushort * *)

- ea: `0x180031e00`
- end: `0x180031e73`
- name: `?get_EventObjectChangeEventClassID@CEventSystem@@UEAAJPEAPEAG@Z`
- size: `115`
- prototype: `int(CEventSystem *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800164f0`
- `0x180031e00`
- `0x18003ecb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180031e39`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180031e39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031e61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031e61`

## pseudocode

```c
__int64 __fastcall CEventSystem::get_EventObjectChangeEventClassID(CEventSystem *this, unsigned __int16 **a2)
{
  HRESULT v4; // [rsp+20h] [rbp-18h]
  LPOLESTR lpsz; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  lpsz = 0;
  v4 = StringFromCLSID(&CLSID_EventObjectChange, &lpsz);
  if ( v4 >= 0 )
    v4 = SetBSTR(a2, lpsz);
  CoTaskMemFree(lpsz);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180031e00  push    rbx
0x180031e02  sub     rsp, 30h
0x180031e06  mov     rbx, rdx
0x180031e09  mov     [rsp+38h+var_18], 0
0x180031e11  test    rdx, rdx
0x180031e14  jnz     short loc_180031E1D
0x180031e16  mov     eax, 80004003h
0x180031e1b  jmp     short loc_180031E6D
0x180031e1d  mov     qword ptr [rdx], 0
0x180031e24  mov     [rsp+38h+lpsz], 0
0x180031e2d  lea     rdx, [rsp+38h+lpsz]; lplpsz
0x180031e32  lea     rcx, CLSID_EventObjectChange; rclsid
0x180031e39  call    cs:__imp_StringFromCLSID
0x180031e3f  mov     [rsp+38h+var_18], eax
0x180031e43  mov     eax, [rsp+38h+var_18]
0x180031e47  test    eax, eax
0x180031e49  js      short loc_180031E5C
0x180031e4b  mov     rdx, [rsp+38h+lpsz]; unsigned __int16 *
0x180031e50  mov     rcx, rbx; unsigned __int16 **
0x180031e53  call    ?SetBSTR@@YAJAEAPEAGPEBG@Z; SetBSTR(ushort * &,ushort const *)
0x180031e58  mov     [rsp+38h+var_18], eax
0x180031e5c  mov     rcx, [rsp+38h+lpsz]; pv
0x180031e61  call    cs:__imp_CoTaskMemFree
0x180031e67  jmp     short $+2
0x180031e69  mov     eax, [rsp+38h+var_18]
0x180031e6d  add     rsp, 30h
0x180031e71  pop     rbx
0x180031e72  retn
0x18004572a  push    rbp
0x18004572c  sub     rsp, 20h
0x180045730  mov     rbp, rdx
0x180045733  lea     rdx, [rbp+20h]; int *
0x180045737  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z
0x18004573c  nop
0x18004573d  add     rsp, 20h
0x180045741  pop     rbp
0x180045742  retn
```
