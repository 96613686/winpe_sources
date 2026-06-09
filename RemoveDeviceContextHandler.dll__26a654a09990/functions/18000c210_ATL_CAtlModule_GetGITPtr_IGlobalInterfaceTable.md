# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000c210`
- end: `0x18000c285`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000c210`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c252`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c252`

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
0x18000c210  mov     [rsp+arg_0], rbx
0x18000c215  mov     [rsp+arg_8], rsi
0x18000c21a  push    rdi
0x18000c21b  sub     rsp, 30h
0x18000c21f  mov     rsi, rdx
0x18000c222  test    rdx, rdx
0x18000c225  jnz     short loc_18000C22E
0x18000c227  mov     eax, 80004003h
0x18000c22c  jmp     short loc_18000C275
0x18000c22e  xor     edi, edi
0x18000c230  lea     rbx, [rcx+40h]
0x18000c234  cmp     [rbx], rdi
0x18000c237  jnz     short loc_18000C25E
0x18000c239  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000c240  mov     [rsp+38h+ppv], rbx; ppv
0x18000c245  xor     edx, edx; pUnkOuter
0x18000c247  lea     r8d, [rdi+1]; dwClsContext
0x18000c24b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000c252  call    cs:__imp_CoCreateInstance
0x18000c258  mov     edi, eax
0x18000c25a  test    eax, eax
0x18000c25c  js      short loc_18000C273
0x18000c25e  mov     rcx, [rbx]
0x18000c261  mov     [rsi], rcx
0x18000c264  mov     rcx, [rbx]
0x18000c267  mov     rdx, [rcx]
0x18000c26a  mov     rax, [rdx+8]
0x18000c26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c273  mov     eax, edi
0x18000c275  mov     rbx, [rsp+38h+arg_0]
0x18000c27a  mov     rsi, [rsp+38h+arg_8]
0x18000c27f  add     rsp, 30h
0x18000c283  pop     rdi
0x18000c284  retn
```
