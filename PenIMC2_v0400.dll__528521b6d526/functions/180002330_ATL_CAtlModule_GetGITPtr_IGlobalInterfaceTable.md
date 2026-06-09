# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180002330`
- end: `0x1800023a6`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `118`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002330`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180002372`
- `ole32!CoCreateInstance` at `0x180002372`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::GetGITPtr(ATL::CAtlModule *this, struct IGlobalInterfaceTable **a2)
{
  HRESULT Instance; // edi
  _QWORD *v5; // rbx

  if ( !a2 )
    return 2147500035LL;
  Instance = 0;
  v5 = (_QWORD *)((char *)this + 64);
  if ( *((_QWORD *)this + 8)
    || (Instance = CoCreateInstance(
                     &CLSID_StdGlobalInterfaceTable,
                     0,
                     1u,
                     &GUID_00000146_0000_0000_c000_000000000046,
                     (LPVOID *)this + 8),
        Instance >= 0) )
  {
    *a2 = (struct IGlobalInterfaceTable *)*v5;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180002330  mov     [rsp+arg_0], rbx
0x180002335  mov     [rsp+arg_8], rsi
0x18000233a  push    rdi
0x18000233b  sub     rsp, 30h
0x18000233f  mov     rsi, rdx
0x180002342  test    rdx, rdx
0x180002345  jnz     short loc_18000234E
0x180002347  mov     eax, 80004003h
0x18000234c  jmp     short loc_180002396
0x18000234e  xor     edi, edi
0x180002350  lea     rbx, [rcx+40h]
0x180002354  cmp     [rbx], rdi
0x180002357  jnz     short loc_18000237E
0x180002359  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180002360  mov     [rsp+38h+ppv], rbx; ppv
0x180002365  xor     edx, edx; pUnkOuter
0x180002367  lea     r8d, [rdi+1]; dwClsContext
0x18000236b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180002372  call    cs:__imp_CoCreateInstance
0x180002378  mov     edi, eax
0x18000237a  test    eax, eax
0x18000237c  js      short loc_180002394
0x18000237e  mov     rcx, [rbx]
0x180002381  mov     [rsi], rcx
0x180002384  mov     rcx, [rbx]
0x180002387  mov     rdx, [rcx]
0x18000238a  mov     rax, [rdx+8]
0x18000238e  call    cs:__guard_dispatch_icall_fptr
0x180002394  mov     eax, edi
0x180002396  mov     rbx, [rsp+38h+arg_0]
0x18000239b  mov     rsi, [rsp+38h+arg_8]
0x1800023a0  add     rsp, 30h
0x1800023a4  pop     rdi
0x1800023a5  retn
```
