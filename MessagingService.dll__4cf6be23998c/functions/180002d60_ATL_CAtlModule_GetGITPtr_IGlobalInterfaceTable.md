# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180002d60`
- end: `0x180002dd5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002d60`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002da2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002da2`

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
0x180002d60  mov     [rsp+arg_0], rbx
0x180002d65  mov     [rsp+arg_8], rsi
0x180002d6a  push    rdi
0x180002d6b  sub     rsp, 30h
0x180002d6f  mov     rsi, rdx
0x180002d72  test    rdx, rdx
0x180002d75  jnz     short loc_180002D7E
0x180002d77  mov     eax, 80004003h
0x180002d7c  jmp     short loc_180002DC5
0x180002d7e  xor     edi, edi
0x180002d80  lea     rbx, [rcx+40h]
0x180002d84  cmp     [rbx], rdi
0x180002d87  jnz     short loc_180002DAE
0x180002d89  mov     [rsp+38h+ppv], rbx; ppv
0x180002d8e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180002d95  xor     edx, edx; pUnkOuter
0x180002d97  lea     r8d, [rdi+1]; dwClsContext
0x180002d9b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180002da2  call    cs:__imp_CoCreateInstance
0x180002da8  mov     edi, eax
0x180002daa  test    eax, eax
0x180002dac  js      short loc_180002DC3
0x180002dae  mov     rcx, [rbx]
0x180002db1  mov     [rsi], rcx
0x180002db4  mov     rcx, [rbx]
0x180002db7  mov     rdx, [rcx]
0x180002dba  mov     rax, [rdx+8]
0x180002dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dc3  mov     eax, edi
0x180002dc5  mov     rbx, [rsp+38h+arg_0]
0x180002dca  mov     rsi, [rsp+38h+arg_8]
0x180002dcf  add     rsp, 30h
0x180002dd3  pop     rdi
0x180002dd4  retn
```
