# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180009440`
- end: `0x1800094b5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009440`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009482`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009482`

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
0x180009440  mov     [rsp+arg_0], rbx
0x180009445  mov     [rsp+arg_8], rsi
0x18000944a  push    rdi
0x18000944b  sub     rsp, 30h
0x18000944f  mov     rsi, rdx
0x180009452  test    rdx, rdx
0x180009455  jnz     short loc_18000945E
0x180009457  mov     eax, 80004003h
0x18000945c  jmp     short loc_1800094A5
0x18000945e  xor     edi, edi
0x180009460  lea     rbx, [rcx+40h]
0x180009464  cmp     [rbx], rdi
0x180009467  jnz     short loc_18000948E
0x180009469  mov     [rsp+38h+ppv], rbx; ppv
0x18000946e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180009475  xor     edx, edx; pUnkOuter
0x180009477  lea     r8d, [rdi+1]; dwClsContext
0x18000947b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180009482  call    cs:__imp_CoCreateInstance
0x180009488  mov     edi, eax
0x18000948a  test    eax, eax
0x18000948c  js      short loc_1800094A3
0x18000948e  mov     rcx, [rbx]
0x180009491  mov     [rsi], rcx
0x180009494  mov     rcx, [rbx]
0x180009497  mov     rdx, [rcx]
0x18000949a  mov     rax, [rdx+8]
0x18000949e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094a3  mov     eax, edi
0x1800094a5  mov     rbx, [rsp+38h+arg_0]
0x1800094aa  mov     rsi, [rsp+38h+arg_8]
0x1800094af  add     rsp, 30h
0x1800094b3  pop     rdi
0x1800094b4  retn
```
