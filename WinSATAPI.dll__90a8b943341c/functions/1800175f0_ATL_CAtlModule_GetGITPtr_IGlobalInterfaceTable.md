# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800175f0`
- end: `0x180017676`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800175f0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001763c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001763c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::GetGITPtr(ATL::CAtlModule *this, struct IGlobalInterfaceTable **a2)
{
  HRESULT Instance; // edi
  _QWORD **v5; // rbx

  if ( !a2 )
    return 2147500035LL;
  Instance = 0;
  v5 = (_QWORD **)((char *)this + 64);
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
    (*(void (__fastcall **)(_QWORD, _QWORD))(**v5 + 8LL))(*v5, **v5);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800175f0  push    rdi
0x1800175f2  sub     rsp, 40h
0x1800175f6  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800175ff  mov     [rsp+48h+arg_0], rbx
0x180017604  mov     [rsp+48h+arg_8], rsi
0x180017609  mov     rsi, rdx
0x18001760c  test    rdx, rdx
0x18001760f  jnz     short loc_180017618
0x180017611  mov     eax, 80004003h
0x180017616  jmp     short loc_180017665
0x180017618  xor     edi, edi
0x18001761a  lea     rbx, [rcx+40h]
0x18001761e  cmp     [rbx], rdi
0x180017621  jnz     short loc_18001764E
0x180017623  mov     [rsp+48h+ppv], rbx; ppv
0x180017628  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18001762f  xor     edx, edx; pUnkOuter
0x180017631  lea     r8d, [rdi+1]; dwClsContext
0x180017635  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001763c  call    cs:__imp_CoCreateInstance
0x180017643  nop     dword ptr [rax+rax+00h]
0x180017648  mov     edi, eax
0x18001764a  test    eax, eax
0x18001764c  js      short loc_180017663
0x18001764e  mov     rcx, [rbx]
0x180017651  mov     [rsi], rcx
0x180017654  mov     rcx, [rbx]
0x180017657  mov     rdx, [rcx]
0x18001765a  mov     rax, [rdx+8]
0x18001765e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017663  mov     eax, edi
0x180017665  mov     rbx, [rsp+48h+arg_0]
0x18001766a  mov     rsi, [rsp+48h+arg_8]
0x18001766f  add     rsp, 40h
0x180017673  pop     rdi
0x180017674  retn
```
