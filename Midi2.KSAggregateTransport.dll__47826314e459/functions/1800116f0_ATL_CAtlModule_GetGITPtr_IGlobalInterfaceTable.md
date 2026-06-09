# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800116f0`
- end: `0x180011765`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800116f0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011732`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011732`

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
0x1800116f0  mov     [rsp+arg_0], rbx
0x1800116f5  mov     [rsp+arg_8], rsi
0x1800116fa  push    rdi
0x1800116fb  sub     rsp, 30h
0x1800116ff  mov     rsi, rdx
0x180011702  test    rdx, rdx
0x180011705  jnz     short loc_18001170E
0x180011707  mov     eax, 80004003h
0x18001170c  jmp     short loc_180011755
0x18001170e  xor     edi, edi
0x180011710  lea     rbx, [rcx+40h]
0x180011714  cmp     [rbx], rdi
0x180011717  jnz     short loc_18001173E
0x180011719  mov     [rsp+38h+ppv], rbx; ppv
0x18001171e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180011725  xor     edx, edx; pUnkOuter
0x180011727  lea     r8d, [rdi+1]; dwClsContext
0x18001172b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180011732  call    cs:__imp_CoCreateInstance
0x180011738  mov     edi, eax
0x18001173a  test    eax, eax
0x18001173c  js      short loc_180011753
0x18001173e  mov     rcx, [rbx]
0x180011741  mov     [rsi], rcx
0x180011744  mov     rcx, [rbx]
0x180011747  mov     rdx, [rcx]
0x18001174a  mov     rax, [rdx+8]
0x18001174e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011753  mov     eax, edi
0x180011755  mov     rbx, [rsp+38h+arg_0]
0x18001175a  mov     rsi, [rsp+38h+arg_8]
0x18001175f  add     rsp, 30h
0x180011763  pop     rdi
0x180011764  retn
```
