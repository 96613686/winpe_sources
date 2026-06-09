# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180005420`
- end: `0x180005495`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005420`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005462`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005462`

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
0x180005420  mov     [rsp+arg_0], rbx
0x180005425  mov     [rsp+arg_8], rsi
0x18000542a  push    rdi
0x18000542b  sub     rsp, 30h
0x18000542f  mov     rsi, rdx
0x180005432  test    rdx, rdx
0x180005435  jnz     short loc_18000543E
0x180005437  mov     eax, 80004003h
0x18000543c  jmp     short loc_180005485
0x18000543e  xor     edi, edi
0x180005440  lea     rbx, [rcx+40h]
0x180005444  cmp     [rbx], rdi
0x180005447  jnz     short loc_18000546E
0x180005449  mov     [rsp+38h+ppv], rbx; ppv
0x18000544e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180005455  xor     edx, edx; pUnkOuter
0x180005457  lea     r8d, [rdi+1]; dwClsContext
0x18000545b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180005462  call    cs:__imp_CoCreateInstance
0x180005468  mov     edi, eax
0x18000546a  test    eax, eax
0x18000546c  js      short loc_180005483
0x18000546e  mov     rcx, [rbx]
0x180005471  mov     [rsi], rcx
0x180005474  mov     rcx, [rbx]
0x180005477  mov     rdx, [rcx]
0x18000547a  mov     rax, [rdx+8]
0x18000547e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005483  mov     eax, edi
0x180005485  mov     rbx, [rsp+38h+arg_0]
0x18000548a  mov     rsi, [rsp+38h+arg_8]
0x18000548f  add     rsp, 30h
0x180005493  pop     rdi
0x180005494  retn
```
