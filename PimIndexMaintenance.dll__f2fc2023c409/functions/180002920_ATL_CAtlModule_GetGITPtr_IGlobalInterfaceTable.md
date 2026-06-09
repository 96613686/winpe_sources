# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180002920`
- end: `0x180002995`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002920`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002962`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002962`

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
0x180002920  mov     [rsp+arg_0], rbx
0x180002925  mov     [rsp+arg_8], rsi
0x18000292a  push    rdi
0x18000292b  sub     rsp, 30h
0x18000292f  mov     rsi, rdx
0x180002932  test    rdx, rdx
0x180002935  jnz     short loc_18000293E
0x180002937  mov     eax, 80004003h
0x18000293c  jmp     short loc_180002985
0x18000293e  xor     edi, edi
0x180002940  lea     rbx, [rcx+40h]
0x180002944  cmp     [rbx], rdi
0x180002947  jnz     short loc_18000296E
0x180002949  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180002950  mov     [rsp+38h+ppv], rbx; ppv
0x180002955  xor     edx, edx; pUnkOuter
0x180002957  lea     r8d, [rdi+1]; dwClsContext
0x18000295b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180002962  call    cs:__imp_CoCreateInstance
0x180002968  mov     edi, eax
0x18000296a  test    eax, eax
0x18000296c  js      short loc_180002983
0x18000296e  mov     rcx, [rbx]
0x180002971  mov     [rsi], rcx
0x180002974  mov     rcx, [rbx]
0x180002977  mov     rdx, [rcx]
0x18000297a  mov     rax, [rdx+8]
0x18000297e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002983  mov     eax, edi
0x180002985  mov     rbx, [rsp+38h+arg_0]
0x18000298a  mov     rsi, [rsp+38h+arg_8]
0x18000298f  add     rsp, 30h
0x180002993  pop     rdi
0x180002994  retn
```
