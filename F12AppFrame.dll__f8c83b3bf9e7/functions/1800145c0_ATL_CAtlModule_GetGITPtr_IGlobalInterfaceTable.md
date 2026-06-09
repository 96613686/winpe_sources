# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800145c0`
- end: `0x180014635`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800145c0`
- `0x180035010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180014602`
- `ole32!CoCreateInstance` at `0x180014602`

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
0x1800145c0  mov     [rsp+arg_0], rbx
0x1800145c5  mov     [rsp+arg_8], rsi
0x1800145ca  push    rdi
0x1800145cb  sub     rsp, 30h
0x1800145cf  mov     rsi, rdx
0x1800145d2  test    rdx, rdx
0x1800145d5  jnz     short loc_1800145DE
0x1800145d7  mov     eax, 80004003h
0x1800145dc  jmp     short loc_180014625
0x1800145de  xor     edi, edi
0x1800145e0  lea     rbx, [rcx+40h]
0x1800145e4  cmp     [rbx], rdi
0x1800145e7  jnz     short loc_18001460E
0x1800145e9  mov     [rsp+38h+ppv], rbx; ppv
0x1800145ee  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800145f5  xor     edx, edx; pUnkOuter
0x1800145f7  lea     r8d, [rdi+1]; dwClsContext
0x1800145fb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180014602  call    cs:__imp_CoCreateInstance
0x180014608  mov     edi, eax
0x18001460a  test    eax, eax
0x18001460c  js      short loc_180014623
0x18001460e  mov     rcx, [rbx]
0x180014611  mov     [rsi], rcx
0x180014614  mov     rcx, [rbx]
0x180014617  mov     rdx, [rcx]
0x18001461a  mov     rax, [rdx+8]
0x18001461e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014623  mov     eax, edi
0x180014625  mov     rbx, [rsp+38h+arg_0]
0x18001462a  mov     rsi, [rsp+38h+arg_8]
0x18001462f  add     rsp, 30h
0x180014633  pop     rdi
0x180014634  retn
```
