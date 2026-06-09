# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180001570`
- end: `0x1800015e2`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001570`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800015b2`
- `ole32!CoCreateInstance` at `0x1800015b2`

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
    _mm_lfence();
    *a2 = (struct IGlobalInterfaceTable *)*v5;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180001570  mov     [rsp+arg_0], rbx
0x180001575  mov     [rsp+arg_8], rsi
0x18000157a  push    rdi
0x18000157b  sub     rsp, 30h
0x18000157f  mov     rsi, rdx
0x180001582  test    rdx, rdx
0x180001585  jnz     short loc_18000158E
0x180001587  mov     eax, 80004003h
0x18000158c  jmp     short loc_1800015D2
0x18000158e  xor     edi, edi
0x180001590  lea     rbx, [rcx+40h]
0x180001594  cmp     [rbx], rdi
0x180001597  jnz     short loc_1800015BE
0x180001599  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800015a0  mov     [rsp+38h+ppv], rbx; ppv
0x1800015a5  xor     edx, edx; pUnkOuter
0x1800015a7  lea     r8d, [rdi+1]; dwClsContext
0x1800015ab  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800015b2  call    cs:__imp_CoCreateInstance
0x1800015b8  mov     edi, eax
0x1800015ba  test    eax, eax
0x1800015bc  js      short loc_1800015D0
0x1800015be  lfence
0x1800015c1  mov     rcx, [rbx]
0x1800015c4  mov     [rsi], rcx
0x1800015c7  mov     rcx, [rbx]
0x1800015ca  mov     rdx, [rcx]
0x1800015cd  call    qword ptr [rdx+8]
0x1800015d0  mov     eax, edi
0x1800015d2  mov     rbx, [rsp+38h+arg_0]
0x1800015d7  mov     rsi, [rsp+38h+arg_8]
0x1800015dc  add     rsp, 30h
0x1800015e0  pop     rdi
0x1800015e1  retn
```
