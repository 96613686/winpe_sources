# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180009ab0`
- end: `0x180009b25`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009ab0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009af2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009af2`

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
0x180009ab0  mov     [rsp+arg_0], rbx
0x180009ab5  mov     [rsp+arg_8], rsi
0x180009aba  push    rdi
0x180009abb  sub     rsp, 30h
0x180009abf  mov     rsi, rdx
0x180009ac2  test    rdx, rdx
0x180009ac5  jnz     short loc_180009ACE
0x180009ac7  mov     eax, 80004003h
0x180009acc  jmp     short loc_180009B15
0x180009ace  xor     edi, edi
0x180009ad0  lea     rbx, [rcx+40h]
0x180009ad4  cmp     [rbx], rdi
0x180009ad7  jnz     short loc_180009AFE
0x180009ad9  mov     [rsp+38h+ppv], rbx; ppv
0x180009ade  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180009ae5  xor     edx, edx; pUnkOuter
0x180009ae7  lea     r8d, [rdi+1]; dwClsContext
0x180009aeb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180009af2  call    cs:__imp_CoCreateInstance
0x180009af8  mov     edi, eax
0x180009afa  test    eax, eax
0x180009afc  js      short loc_180009B13
0x180009afe  mov     rcx, [rbx]
0x180009b01  mov     [rsi], rcx
0x180009b04  mov     rcx, [rbx]
0x180009b07  mov     rdx, [rcx]
0x180009b0a  mov     rax, [rdx+8]
0x180009b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b13  mov     eax, edi
0x180009b15  mov     rbx, [rsp+38h+arg_0]
0x180009b1a  mov     rsi, [rsp+38h+arg_8]
0x180009b1f  add     rsp, 30h
0x180009b23  pop     rdi
0x180009b24  retn
```
