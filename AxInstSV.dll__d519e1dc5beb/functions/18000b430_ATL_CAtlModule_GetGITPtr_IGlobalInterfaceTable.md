# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000b430`
- end: `0x18000b4a5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b430`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b472`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b472`

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
0x18000b430  mov     [rsp+arg_0], rbx
0x18000b435  mov     [rsp+arg_8], rsi
0x18000b43a  push    rdi
0x18000b43b  sub     rsp, 30h
0x18000b43f  mov     rsi, rdx
0x18000b442  test    rdx, rdx
0x18000b445  jnz     short loc_18000B44E
0x18000b447  mov     eax, 80004003h
0x18000b44c  jmp     short loc_18000B495
0x18000b44e  xor     edi, edi
0x18000b450  lea     rbx, [rcx+40h]
0x18000b454  cmp     [rbx], rdi
0x18000b457  jnz     short loc_18000B47E
0x18000b459  mov     [rsp+38h+ppv], rbx; ppv
0x18000b45e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000b465  xor     edx, edx; pUnkOuter
0x18000b467  lea     r8d, [rdi+1]; dwClsContext
0x18000b46b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000b472  call    cs:__imp_CoCreateInstance
0x18000b478  mov     edi, eax
0x18000b47a  test    eax, eax
0x18000b47c  js      short loc_18000B493
0x18000b47e  mov     rcx, [rbx]
0x18000b481  mov     [rsi], rcx
0x18000b484  mov     rcx, [rbx]
0x18000b487  mov     rdx, [rcx]
0x18000b48a  mov     rax, [rdx+8]
0x18000b48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b493  mov     eax, edi
0x18000b495  mov     rbx, [rsp+38h+arg_0]
0x18000b49a  mov     rsi, [rsp+38h+arg_8]
0x18000b49f  add     rsp, 30h
0x18000b4a3  pop     rdi
0x18000b4a4  retn
```
