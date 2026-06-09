# AccessibilityCplCore::GetAdminObject(IAccessibilityCplAdmin * *)

- ea: `0x1800068f8`
- end: `0x180006999`
- name: `?GetAdminObject@AccessibilityCplCore@@AEAAJPEAPEAUIAccessibilityCplAdmin@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this, struct IAccessibilityCplAdmin **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015fa0`

## callees

- `0x18000466c`
- `0x1800068f8`
- `0x18002e010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180006925`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180006925`
- `PROPSYS!PSPropertyBag_ReadType` at `0x180006955`
- `PROPSYS!PSPropertyBag_ReadType` at `0x180006955`

## string_xrefs

- `0x18000693d`: `AccessibilityAdminObject`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::GetAdminObject(AccessibilityCplCore *this, struct IAccessibilityCplAdmin **a2)
{
  IUnknown *v2; // rcx
  HRESULT v4; // ebx
  VARIANT var; // [rsp+20h] [rbp-28h] BYREF
  void *ppvOut; // [rsp+50h] [rbp+8h] BYREF

  v2 = (IUnknown *)*((_QWORD *)this + 2);
  ppvOut = 0;
  v4 = IUnknown_QueryService(
         v2,
         &GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &ppvOut);
  if ( v4 >= 0 )
  {
    memset(&var, 0, sizeof(var));
    v4 = PSPropertyBag_ReadType((IPropertyBag *)ppvOut, L"AccessibilityAdminObject", &var, 0xDu);
    if ( v4 >= 0 )
    {
      if ( var.llVal )
        v4 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, struct IAccessibilityCplAdmin **))var.llVal)(
               var.llVal,
               &GUID_97b9f488_b188_4b03_9b27_d74b25755464,
               a2);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppvOut);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800068f8  mov     [rsp+arg_8], rbx
0x1800068fd  push    rdi
0x1800068fe  sub     rsp, 40h
0x180006902  mov     rcx, [rcx+10h]; punk
0x180006906  lea     r9, [rsp+48h+ppvOut]; ppvOut
0x18000690b  mov     rdi, rdx
0x18000690e  mov     [rsp+48h+ppvOut], 0
0x180006917  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1; guidService
0x18000691e  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180006925  call    cs:__imp_IUnknown_QueryService
0x18000692b  mov     ebx, eax
0x18000692d  test    eax, eax
0x18000692f  js      short loc_180006982
0x180006931  mov     rcx, [rsp+48h+ppvOut]; propBag
0x180006936  lea     r8, [rsp+48h+var]; var
0x18000693b  xor     eax, eax
0x18000693d  lea     rdx, propName; "AccessibilityAdminObject"
0x180006944  xorps   xmm0, xmm0
0x180006947  mov     qword ptr [rsp+48h+var+10h], rax
0x18000694c  movups  xmmword ptr [rsp+48h+var], xmm0
0x180006951  lea     r9d, [rax+0Dh]; type
0x180006955  call    cs:__imp_PSPropertyBag_ReadType
0x18000695b  mov     ebx, eax
0x18000695d  test    eax, eax
0x18000695f  js      short loc_180006982
0x180006961  mov     rcx, qword ptr [rsp+48h+var+8]
0x180006966  test    rcx, rcx
0x180006969  jz      short loc_180006982
0x18000696b  mov     rax, [rcx]
0x18000696e  lea     rdx, _GUID_97b9f488_b188_4b03_9b27_d74b25755464
0x180006975  mov     r8, rdi
0x180006978  mov     rax, [rax]
0x18000697b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006980  mov     ebx, eax
0x180006982  lea     rcx, [rsp+48h+ppvOut]
0x180006987  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000698c  mov     eax, ebx
0x18000698e  mov     rbx, [rsp+48h+arg_8]
0x180006993  add     rsp, 40h
0x180006997  pop     rdi
0x180006998  retn
```
