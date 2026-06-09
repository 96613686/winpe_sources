# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180009b10`
- end: `0x180009b85`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009b10`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009b52`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009b52`

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
0x180009b10  mov     [rsp+arg_0], rbx
0x180009b15  mov     [rsp+arg_8], rsi
0x180009b1a  push    rdi
0x180009b1b  sub     rsp, 30h
0x180009b1f  mov     rsi, rdx
0x180009b22  test    rdx, rdx
0x180009b25  jnz     short loc_180009B2E
0x180009b27  mov     eax, 80004003h
0x180009b2c  jmp     short loc_180009B75
0x180009b2e  xor     edi, edi
0x180009b30  lea     rbx, [rcx+40h]
0x180009b34  cmp     [rbx], rdi
0x180009b37  jnz     short loc_180009B5E
0x180009b39  mov     [rsp+38h+ppv], rbx; ppv
0x180009b3e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180009b45  xor     edx, edx; pUnkOuter
0x180009b47  lea     r8d, [rdi+1]; dwClsContext
0x180009b4b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180009b52  call    cs:__imp_CoCreateInstance
0x180009b58  mov     edi, eax
0x180009b5a  test    eax, eax
0x180009b5c  js      short loc_180009B73
0x180009b5e  mov     rcx, [rbx]
0x180009b61  mov     [rsi], rcx
0x180009b64  mov     rcx, [rbx]
0x180009b67  mov     rdx, [rcx]
0x180009b6a  mov     rax, [rdx+8]
0x180009b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b73  mov     eax, edi
0x180009b75  mov     rbx, [rsp+38h+arg_0]
0x180009b7a  mov     rsi, [rsp+38h+arg_8]
0x180009b7f  add     rsp, 30h
0x180009b83  pop     rdi
0x180009b84  retn
```
