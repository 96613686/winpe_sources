# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000acf0`
- end: `0x18000ad65`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000acf0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ad32`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ad32`

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
0x18000acf0  mov     [rsp+arg_0], rbx
0x18000acf5  mov     [rsp+arg_8], rsi
0x18000acfa  push    rdi
0x18000acfb  sub     rsp, 30h
0x18000acff  mov     rsi, rdx
0x18000ad02  test    rdx, rdx
0x18000ad05  jnz     short loc_18000AD0E
0x18000ad07  mov     eax, 80004003h
0x18000ad0c  jmp     short loc_18000AD55
0x18000ad0e  xor     edi, edi
0x18000ad10  lea     rbx, [rcx+40h]
0x18000ad14  cmp     [rbx], rdi
0x18000ad17  jnz     short loc_18000AD3E
0x18000ad19  mov     [rsp+38h+ppv], rbx; ppv
0x18000ad1e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000ad25  xor     edx, edx; pUnkOuter
0x18000ad27  lea     r8d, [rdi+1]; dwClsContext
0x18000ad2b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000ad32  call    cs:__imp_CoCreateInstance
0x18000ad38  mov     edi, eax
0x18000ad3a  test    eax, eax
0x18000ad3c  js      short loc_18000AD53
0x18000ad3e  mov     rcx, [rbx]
0x18000ad41  mov     [rsi], rcx
0x18000ad44  mov     rcx, [rbx]
0x18000ad47  mov     rdx, [rcx]
0x18000ad4a  mov     rax, [rdx+8]
0x18000ad4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad53  mov     eax, edi
0x18000ad55  mov     rbx, [rsp+38h+arg_0]
0x18000ad5a  mov     rsi, [rsp+38h+arg_8]
0x18000ad5f  add     rsp, 30h
0x18000ad63  pop     rdi
0x18000ad64  retn
```
