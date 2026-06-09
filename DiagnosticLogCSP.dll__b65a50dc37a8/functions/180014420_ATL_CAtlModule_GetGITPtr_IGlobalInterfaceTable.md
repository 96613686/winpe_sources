# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180014420`
- end: `0x18001449c`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180014420`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014462`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014462`

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
0x180014420  mov     [rsp+arg_0], rbx
0x180014425  mov     [rsp+arg_8], rsi
0x18001442a  push    rdi
0x18001442b  sub     rsp, 30h
0x18001442f  mov     rsi, rdx
0x180014432  test    rdx, rdx
0x180014435  jnz     short loc_18001443E
0x180014437  mov     eax, 80004003h
0x18001443c  jmp     short loc_18001448B
0x18001443e  xor     edi, edi
0x180014440  lea     rbx, [rcx+40h]
0x180014444  cmp     [rbx], rdi
0x180014447  jnz     short loc_180014474
0x180014449  mov     [rsp+38h+ppv], rbx; ppv
0x18001444e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180014455  xor     edx, edx; pUnkOuter
0x180014457  lea     r8d, [rdi+1]; dwClsContext
0x18001445b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180014462  call    cs:__imp_CoCreateInstance
0x180014469  nop     dword ptr [rax+rax+00h]
0x18001446e  mov     edi, eax
0x180014470  test    eax, eax
0x180014472  js      short loc_180014489
0x180014474  mov     rcx, [rbx]
0x180014477  mov     [rsi], rcx
0x18001447a  mov     rcx, [rbx]
0x18001447d  mov     rdx, [rcx]
0x180014480  mov     rax, [rdx+8]
0x180014484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014489  mov     eax, edi
0x18001448b  mov     rbx, [rsp+38h+arg_0]
0x180014490  mov     rsi, [rsp+38h+arg_8]
0x180014495  add     rsp, 30h
0x180014499  pop     rdi
0x18001449a  retn
```
