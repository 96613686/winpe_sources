# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180012cc0`
- end: `0x180012d35`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180012cc0`
- `0x180014010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180012d02`
- `ole32!CoCreateInstance` at `0x180012d02`

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
0x180012cc0  mov     [rsp+arg_0], rbx
0x180012cc5  mov     [rsp+arg_8], rsi
0x180012cca  push    rdi
0x180012ccb  sub     rsp, 30h
0x180012ccf  mov     rsi, rdx
0x180012cd2  test    rdx, rdx
0x180012cd5  jnz     short loc_180012CDE
0x180012cd7  mov     eax, 80004003h
0x180012cdc  jmp     short loc_180012D25
0x180012cde  xor     edi, edi
0x180012ce0  lea     rbx, [rcx+40h]
0x180012ce4  cmp     [rbx], rdi
0x180012ce7  jnz     short loc_180012D0E
0x180012ce9  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180012cf0  mov     [rsp+38h+ppv], rbx; ppv
0x180012cf5  xor     edx, edx; pUnkOuter
0x180012cf7  lea     r8d, [rdi+1]; dwClsContext
0x180012cfb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180012d02  call    cs:__imp_CoCreateInstance
0x180012d08  mov     edi, eax
0x180012d0a  test    eax, eax
0x180012d0c  js      short loc_180012D23
0x180012d0e  mov     rcx, [rbx]
0x180012d11  mov     [rsi], rcx
0x180012d14  mov     rcx, [rbx]
0x180012d17  mov     rdx, [rcx]
0x180012d1a  mov     rax, [rdx+8]
0x180012d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d23  mov     eax, edi
0x180012d25  mov     rbx, [rsp+38h+arg_0]
0x180012d2a  mov     rsi, [rsp+38h+arg_8]
0x180012d2f  add     rsp, 30h
0x180012d33  pop     rdi
0x180012d34  retn
```
