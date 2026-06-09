# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000c500`
- end: `0x18000c575`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000c500`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c542`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c542`

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
0x18000c500  mov     [rsp+arg_0], rbx
0x18000c505  mov     [rsp+arg_8], rsi
0x18000c50a  push    rdi
0x18000c50b  sub     rsp, 30h
0x18000c50f  mov     rsi, rdx
0x18000c512  test    rdx, rdx
0x18000c515  jnz     short loc_18000C51E
0x18000c517  mov     eax, 80004003h
0x18000c51c  jmp     short loc_18000C565
0x18000c51e  xor     edi, edi
0x18000c520  lea     rbx, [rcx+40h]
0x18000c524  cmp     [rbx], rdi
0x18000c527  jnz     short loc_18000C54E
0x18000c529  mov     [rsp+38h+ppv], rbx; ppv
0x18000c52e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000c535  xor     edx, edx; pUnkOuter
0x18000c537  lea     r8d, [rdi+1]; dwClsContext
0x18000c53b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000c542  call    cs:__imp_CoCreateInstance
0x18000c548  mov     edi, eax
0x18000c54a  test    eax, eax
0x18000c54c  js      short loc_18000C563
0x18000c54e  mov     rcx, [rbx]
0x18000c551  mov     [rsi], rcx
0x18000c554  mov     rcx, [rbx]
0x18000c557  mov     rdx, [rcx]
0x18000c55a  mov     rax, [rdx+8]
0x18000c55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c563  mov     eax, edi
0x18000c565  mov     rbx, [rsp+38h+arg_0]
0x18000c56a  mov     rsi, [rsp+38h+arg_8]
0x18000c56f  add     rsp, 30h
0x18000c573  pop     rdi
0x18000c574  retn
```
