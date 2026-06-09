# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180046c80`
- end: `0x180046cf5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180046c80`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046cc2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046cc2`

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
0x180046c80  mov     [rsp+arg_0], rbx
0x180046c85  mov     [rsp+arg_8], rsi
0x180046c8a  push    rdi
0x180046c8b  sub     rsp, 30h
0x180046c8f  mov     rsi, rdx
0x180046c92  test    rdx, rdx
0x180046c95  jnz     short loc_180046C9E
0x180046c97  mov     eax, 80004003h
0x180046c9c  jmp     short loc_180046CE5
0x180046c9e  xor     edi, edi
0x180046ca0  lea     rbx, [rcx+40h]
0x180046ca4  cmp     [rbx], rdi
0x180046ca7  jnz     short loc_180046CCE
0x180046ca9  mov     [rsp+38h+ppv], rbx; ppv
0x180046cae  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180046cb5  xor     edx, edx; pUnkOuter
0x180046cb7  lea     r8d, [rdi+1]; dwClsContext
0x180046cbb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180046cc2  call    cs:__imp_CoCreateInstance
0x180046cc8  mov     edi, eax
0x180046cca  test    eax, eax
0x180046ccc  js      short loc_180046CE3
0x180046cce  mov     rcx, [rbx]
0x180046cd1  mov     [rsi], rcx
0x180046cd4  mov     rcx, [rbx]
0x180046cd7  mov     rdx, [rcx]
0x180046cda  mov     rax, [rdx+8]
0x180046cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ce3  mov     eax, edi
0x180046ce5  mov     rbx, [rsp+38h+arg_0]
0x180046cea  mov     rsi, [rsp+38h+arg_8]
0x180046cef  add     rsp, 30h
0x180046cf3  pop     rdi
0x180046cf4  retn
```
