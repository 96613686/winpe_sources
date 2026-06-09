# _PROG_RESOURCES::RegisterLogin(void)

- ea: `0x180009ba4`
- end: `0x180009c22`
- name: `?RegisterLogin@_PROG_RESOURCES@@QEAAHXZ`
- size: `126`
- prototype: `__int64 __fastcall(_PROG_RESOURCES *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800098a0`
- `0x180012604`

## callees

- `0x180009ba4`
- `0x180020010`

## import_xrefs

- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009c03`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009c03`
- `wbemcomn!GetMemLogObject` at `0x180009bf8`
- `wbemcomn!GetMemLogObject` at `0x180009bf8`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180009bec`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180009bec`

## pseudocode

```c
__int64 __fastcall _PROG_RESOURCES::RegisterLogin(_PROG_RESOURCES *this)
{
  HRESULT v1; // ebx
  CMemoryLog *MemLogObject; // rax

  pUnk = (LPUNKNOWN)&g_FactoryLogin;
  (*(void (**)(void))(g_FactoryLogin + 8LL))();
  v1 = CoRegisterClassObject(&CLSID_WbemLevel1Login, pUnk, 0x15u, 1u, &dwRegister);
  if ( v1 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v1);
    return 0;
  }
  else
  {
    *(&g_ProgRes + 1) = 1;
    return 1;
  }
}

```

## disassembly

```asm
0x180009ba4  push    rbx
0x180009ba6  sub     rsp, 30h
0x180009baa  mov     rax, cs:?g_FactoryLogin@@3VCForwardFactory@@A; CForwardFactory g_FactoryLogin
0x180009bb1  lea     rcx, ?g_FactoryLogin@@3VCForwardFactory@@A; CForwardFactory g_FactoryLogin
0x180009bb8  mov     qword ptr cs:pUnk, rcx
0x180009bbf  mov     rax, [rax+8]
0x180009bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bc8  mov     rdx, qword ptr cs:pUnk; pUnk
0x180009bcf  lea     rax, dwRegister
0x180009bd6  mov     r9d, 1; flags
0x180009bdc  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x180009be1  lea     rcx, CLSID_WbemLevel1Login; rclsid
0x180009be8  lea     r8d, [r9+14h]; dwClsContext
0x180009bec  call    cs:__imp_CoRegisterClassObject
0x180009bf2  mov     ebx, eax
0x180009bf4  test    eax, eax
0x180009bf6  jz      short loc_180009C0D
0x180009bf8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009bfe  mov     rcx, rax
0x180009c01  mov     edx, ebx
0x180009c03  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009c09  xor     eax, eax
0x180009c0b  jmp     short loc_180009C1C
0x180009c0d  mov     dword ptr cs:?g_ProgRes@@3U_PROG_RESOURCES@@A+4, 1; _PROG_RESOURCES g_ProgRes
0x180009c17  mov     eax, 1
0x180009c1c  add     rsp, 30h
0x180009c20  pop     rbx
0x180009c21  retn
```
