# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800095f0`
- end: `0x180009665`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800095f0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009632`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009632`

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
0x1800095f0  mov     [rsp+arg_0], rbx
0x1800095f5  mov     [rsp+arg_8], rsi
0x1800095fa  push    rdi
0x1800095fb  sub     rsp, 30h
0x1800095ff  mov     rsi, rdx
0x180009602  test    rdx, rdx
0x180009605  jnz     short loc_18000960E
0x180009607  mov     eax, 80004003h
0x18000960c  jmp     short loc_180009655
0x18000960e  xor     edi, edi
0x180009610  lea     rbx, [rcx+40h]
0x180009614  cmp     [rbx], rdi
0x180009617  jnz     short loc_18000963E
0x180009619  mov     [rsp+38h+ppv], rbx; ppv
0x18000961e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180009625  xor     edx, edx; pUnkOuter
0x180009627  lea     r8d, [rdi+1]; dwClsContext
0x18000962b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180009632  call    cs:__imp_CoCreateInstance
0x180009638  mov     edi, eax
0x18000963a  test    eax, eax
0x18000963c  js      short loc_180009653
0x18000963e  mov     rcx, [rbx]
0x180009641  mov     [rsi], rcx
0x180009644  mov     rcx, [rbx]
0x180009647  mov     rdx, [rcx]
0x18000964a  mov     rax, [rdx+8]
0x18000964e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009653  mov     eax, edi
0x180009655  mov     rbx, [rsp+38h+arg_0]
0x18000965a  mov     rsi, [rsp+38h+arg_8]
0x18000965f  add     rsp, 30h
0x180009663  pop     rdi
0x180009664  retn
```
