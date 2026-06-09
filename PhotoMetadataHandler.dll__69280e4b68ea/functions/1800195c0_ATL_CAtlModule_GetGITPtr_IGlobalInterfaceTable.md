# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800195c0`
- end: `0x18001963c`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800195c0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019602`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019602`

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
0x1800195c0  mov     [rsp+arg_0], rbx
0x1800195c5  mov     [rsp+arg_8], rsi
0x1800195ca  push    rdi
0x1800195cb  sub     rsp, 30h
0x1800195cf  mov     rsi, rdx
0x1800195d2  test    rdx, rdx
0x1800195d5  jnz     short loc_1800195DE
0x1800195d7  mov     eax, 80004003h
0x1800195dc  jmp     short loc_18001962B
0x1800195de  xor     edi, edi
0x1800195e0  lea     rbx, [rcx+40h]
0x1800195e4  cmp     [rbx], rdi
0x1800195e7  jnz     short loc_180019614
0x1800195e9  mov     [rsp+38h+ppv], rbx; ppv
0x1800195ee  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800195f5  xor     edx, edx; pUnkOuter
0x1800195f7  lea     r8d, [rdi+1]; dwClsContext
0x1800195fb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180019602  call    cs:__imp_CoCreateInstance
0x180019609  nop     dword ptr [rax+rax+00h]
0x18001960e  mov     edi, eax
0x180019610  test    eax, eax
0x180019612  js      short loc_180019629
0x180019614  mov     rcx, [rbx]
0x180019617  mov     [rsi], rcx
0x18001961a  mov     rcx, [rbx]
0x18001961d  mov     rdx, [rcx]
0x180019620  mov     rax, [rdx+8]
0x180019624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019629  mov     eax, edi
0x18001962b  mov     rbx, [rsp+38h+arg_0]
0x180019630  mov     rsi, [rsp+38h+arg_8]
0x180019635  add     rsp, 30h
0x180019639  pop     rdi
0x18001963a  retn
```
