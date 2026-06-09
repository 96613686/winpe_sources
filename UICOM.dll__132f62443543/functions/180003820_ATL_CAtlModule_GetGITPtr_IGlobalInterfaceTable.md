# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180003820`
- end: `0x180003895`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003820`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003862`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003862`

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
0x180003820  mov     [rsp+arg_0], rbx
0x180003825  mov     [rsp+arg_8], rsi
0x18000382a  push    rdi
0x18000382b  sub     rsp, 30h
0x18000382f  mov     rsi, rdx
0x180003832  test    rdx, rdx
0x180003835  jnz     short loc_18000383E
0x180003837  mov     eax, 80004003h
0x18000383c  jmp     short loc_180003885
0x18000383e  xor     edi, edi
0x180003840  lea     rbx, [rcx+40h]
0x180003844  cmp     [rbx], rdi
0x180003847  jnz     short loc_18000386E
0x180003849  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180003850  mov     [rsp+38h+ppv], rbx; ppv
0x180003855  xor     edx, edx; pUnkOuter
0x180003857  lea     r8d, [rdi+1]; dwClsContext
0x18000385b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180003862  call    cs:__imp_CoCreateInstance
0x180003868  mov     edi, eax
0x18000386a  test    eax, eax
0x18000386c  js      short loc_180003883
0x18000386e  mov     rcx, [rbx]
0x180003871  mov     [rsi], rcx
0x180003874  mov     rcx, [rbx]
0x180003877  mov     rdx, [rcx]
0x18000387a  mov     rax, [rdx+8]
0x18000387e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003883  mov     eax, edi
0x180003885  mov     rbx, [rsp+38h+arg_0]
0x18000388a  mov     rsi, [rsp+38h+arg_8]
0x18000388f  add     rsp, 30h
0x180003893  pop     rdi
0x180003894  retn
```
