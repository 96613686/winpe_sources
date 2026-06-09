# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180056ba0`
- end: `0x180056c1f`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180056ba0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180056bec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180056bec`

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
0x180056ba0  push    rdi
0x180056ba2  sub     rsp, 40h
0x180056ba6  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x180056baf  mov     [rsp+48h+arg_0], rbx
0x180056bb4  mov     [rsp+48h+arg_8], rsi
0x180056bb9  mov     rsi, rdx
0x180056bbc  test    rdx, rdx
0x180056bbf  jnz     short loc_180056BC8
0x180056bc1  mov     eax, 80004003h
0x180056bc6  jmp     short loc_180056C0F
0x180056bc8  xor     edi, edi
0x180056bca  lea     rbx, [rcx+40h]
0x180056bce  cmp     [rbx], rdi
0x180056bd1  jnz     short loc_180056BF8
0x180056bd3  mov     [rsp+48h+ppv], rbx; ppv
0x180056bd8  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180056bdf  xor     edx, edx; pUnkOuter
0x180056be1  lea     r8d, [rdi+1]; dwClsContext
0x180056be5  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180056bec  call    cs:__imp_CoCreateInstance
0x180056bf2  mov     edi, eax
0x180056bf4  test    eax, eax
0x180056bf6  js      short loc_180056C0D
0x180056bf8  mov     rcx, [rbx]
0x180056bfb  mov     [rsi], rcx
0x180056bfe  mov     rcx, [rbx]
0x180056c01  mov     rdx, [rcx]
0x180056c04  mov     rax, [rdx+8]
0x180056c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c0d  mov     eax, edi
0x180056c0f  mov     rbx, [rsp+48h+arg_0]
0x180056c14  mov     rsi, [rsp+48h+arg_8]
0x180056c19  add     rsp, 40h
0x180056c1d  pop     rdi
0x180056c1e  retn
```
