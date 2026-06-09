# FwService::CreateInstance(NET_FW_SERVICE_TYPE_,_tag_FW_PROFILE_TYPE,FwService * *)

- ea: `0x180046630`
- end: `0x180046721`
- name: `?CreateInstance@FwService@@SAJW4NET_FW_SERVICE_TYPE_@@W4_tag_FW_PROFILE_TYPE@@PEAPEAV1@@Z`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180045980`
- `0x180047410`

## callees

- `0x18004657c`
- `0x180046630`
- `0x18005e010`

## import_xrefs

- `fwbase!FwResolveIndirectString` at `0x1800466a3`
- `fwbase!FwResolveIndirectString` at `0x1800466a3`
- `fwbase!FwReportReturnError` at `0x1800466b8`
- `fwbase!FwReportReturnError` at `0x1800466c7`
- `fwbase!FwReportReturnError` at `0x1800466dc`
- `fwbase!FwReportReturnError` at `0x1800466ff`
- `fwbase!FwReportReturnError` at `0x1800466b8`
- `fwbase!FwReportReturnError` at `0x1800466c7`
- `fwbase!FwReportReturnError` at `0x1800466dc`
- `fwbase!FwReportReturnError` at `0x1800466ff`
- `fwbase!FwStringCopy` at `0x180046693`
- `fwbase!FwStringCopy` at `0x180046693`

## string_xrefs

- `0x1800466d5`: `FwService::CreateInstance`
- `0x1800466f8`: `FwService::CreateInstance`
- `0x1800466b1`: `FwService::Initialize`
- `0x1800466c0`: `FwService::Initialize`

## pseudocode

```c
__int64 __fastcall FwService::CreateInstance(int a1, int a2, _QWORD *a3)
{
  __int64 v3; // r14
  int v6; // eax
  _DWORD *v7; // rdi
  int v8; // ebx
  const unsigned __int16 * near *v9; // rcx
  _DWORD *v11; // [rsp+50h] [rbp+18h] BYREF

  v3 = a1;
  v11 = 0;
  *a3 = 0;
  v6 = ATL::CComObject<FwService>::CreateInstance(&v11);
  v7 = v11;
  v8 = v6;
  if ( v6 < 0 )
    goto LABEL_5;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v11 + 8LL))(v11);
  v7[6] = v3;
  v9 = (&g_arrEmbeddedContextStrings)[v3];
  v7[12] = a2;
  v8 = FwStringCopy(v9, v7 + 8);
  if ( v8 >= 0 )
  {
    v8 = FwResolveIndirectString(v7 + 8);
    if ( v8 >= 0 )
      goto LABEL_8;
  }
  FwReportReturnError("FwService::Initialize", (unsigned int)v8);
  v6 = FwReportReturnError("FwService::Initialize", (unsigned int)v8);
  v8 = v6;
  if ( v6 >= 0 )
  {
LABEL_8:
    *a3 = v7;
  }
  else
  {
LABEL_5:
    FwReportReturnError("FwService::CreateInstance", (unsigned int)v6);
    if ( v7 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
    return (unsigned int)FwReportReturnError("FwService::CreateInstance", (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180046630  mov     rax, rsp
0x180046633  mov     [rax+8], rbx
0x180046637  mov     [rax+10h], rbp
0x18004663b  push    rsi
0x18004663c  push    rdi
0x18004663d  push    r14
0x18004663f  sub     rsp, 20h
0x180046643  movsxd  r14, ecx
0x180046646  mov     rsi, r8
0x180046649  lea     rcx, [rax+18h]
0x18004664d  mov     qword ptr [rax+18h], 0
0x180046655  mov     ebp, edx
0x180046657  mov     qword ptr [r8], 0
0x18004665e  call    ?CreateInstance@?$CComObject@VFwService@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<FwService>::CreateInstance(ATL::CComObject<FwService> * *)
0x180046663  mov     rdi, [rsp+38h+arg_10]
0x180046668  mov     ebx, eax
0x18004666a  test    eax, eax
0x18004666c  js      short loc_1800466D3
0x18004666e  mov     rax, [rdi]
0x180046671  mov     rcx, rdi
0x180046674  mov     rax, [rax+8]
0x180046678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004667d  lea     rax, ?g_arrEmbeddedContextStrings@@3PAPEBGA; ushort const * near * g_arrEmbeddedContextStrings
0x180046684  mov     [rdi+18h], r14d
0x180046688  mov     rcx, [rax+r14*8]
0x18004668c  lea     rdx, [rdi+20h]
0x180046690  mov     [rdi+30h], ebp
0x180046693  call    cs:__imp_FwStringCopy
0x180046699  mov     ebx, eax
0x18004669b  test    eax, eax
0x18004669d  js      short loc_1800466AF
0x18004669f  lea     rcx, [rdi+20h]
0x1800466a3  call    cs:__imp_FwResolveIndirectString
0x1800466a9  mov     ebx, eax
0x1800466ab  test    eax, eax
0x1800466ad  jns     short loc_180046709
0x1800466af  mov     edx, ebx
0x1800466b1  lea     rcx, aFwserviceIniti; "FwService::Initialize"
0x1800466b8  call    cs:__imp_FwReportReturnError
0x1800466be  mov     edx, ebx
0x1800466c0  lea     rcx, aFwserviceIniti; "FwService::Initialize"
0x1800466c7  call    cs:__imp_FwReportReturnError
0x1800466cd  mov     ebx, eax
0x1800466cf  test    eax, eax
0x1800466d1  jns     short loc_180046709
0x1800466d3  mov     edx, eax
0x1800466d5  lea     rcx, aFwserviceCreat; "FwService::CreateInstance"
0x1800466dc  call    cs:__imp_FwReportReturnError
0x1800466e2  test    rdi, rdi
0x1800466e5  jz      short loc_1800466F6
0x1800466e7  mov     rax, [rdi]
0x1800466ea  mov     rcx, rdi
0x1800466ed  mov     rax, [rax+10h]
0x1800466f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466f6  mov     edx, ebx
0x1800466f8  lea     rcx, aFwserviceCreat; "FwService::CreateInstance"
0x1800466ff  call    cs:__imp_FwReportReturnError
0x180046705  mov     ebx, eax
0x180046707  jmp     short loc_18004670C
0x180046709  mov     [rsi], rdi
0x18004670c  mov     rbp, [rsp+38h+arg_8]
0x180046711  mov     eax, ebx
0x180046713  mov     rbx, [rsp+38h+arg_0]
0x180046718  add     rsp, 20h
0x18004671c  pop     r14
0x18004671e  pop     rdi
0x18004671f  pop     rsi
0x180046720  retn
```
