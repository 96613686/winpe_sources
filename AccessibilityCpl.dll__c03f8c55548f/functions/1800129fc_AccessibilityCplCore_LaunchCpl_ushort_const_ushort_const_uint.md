# AccessibilityCplCore::LaunchCpl(ushort const *,ushort const *,uint)

- ea: `0x1800129fc`
- end: `0x180012a80`
- name: `?LaunchCpl@AccessibilityCplCore@@AEAAXPEBG0I@Z`
- size: `132`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x18000466c`
- `0x180005fec`
- `0x1800129fc`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012a38`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012a38`

## pseudocode

```c
void __fastcall AccessibilityCplCore::LaunchCpl(
        AccessibilityCplCore *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  int v8; // eax
  LPVOID ppv[7]; // [rsp+30h] [rbp-38h] BYREF

  ppv[0] = 0;
  if ( CoCreateInstance(&CLSID_OpenControlPanel, 0, 0x17u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, ppv) >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, const unsigned __int16 *, _QWORD))(*(_QWORD *)ppv[0] + 24LL))(
           ppv[0],
           a2,
           a3,
           0);
    if ( v8 < 0 )
      AccessibilityCplCore::ErrorMessage(this, a4, v8);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppv);
}

```

## disassembly

```asm
0x1800129fc  push    rbx
0x1800129fe  push    rbp
0x1800129ff  push    rsi
0x180012a00  push    rdi
0x180012a01  sub     rsp, 48h
0x180012a05  mov     rbp, rdx
0x180012a08  mov     [rsp+68h+var_38], 0
0x180012a11  xor     edx, edx; pUnkOuter
0x180012a13  lea     rax, [rsp+68h+var_38]
0x180012a18  mov     ebx, r9d
0x180012a1b  mov     [rsp+68h+ppv], rax; ppv
0x180012a20  mov     rsi, r8
0x180012a23  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x180012a2a  mov     rdi, rcx
0x180012a2d  lea     rcx, CLSID_OpenControlPanel; rclsid
0x180012a34  lea     r8d, [rdx+17h]; dwClsContext
0x180012a38  call    cs:__imp_CoCreateInstance
0x180012a3e  test    eax, eax
0x180012a40  js      short loc_180012A6D
0x180012a42  mov     rcx, [rsp+68h+var_38]
0x180012a47  xor     r9d, r9d
0x180012a4a  mov     r8, rsi
0x180012a4d  mov     rdx, rbp
0x180012a50  mov     rax, [rcx]
0x180012a53  mov     rax, [rax+18h]
0x180012a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a5c  test    eax, eax
0x180012a5e  jns     short loc_180012A6D
0x180012a60  mov     r8d, eax; int
0x180012a63  mov     edx, ebx; unsigned int
0x180012a65  mov     rcx, rdi; this
0x180012a68  call    ?ErrorMessage@AccessibilityCplCore@@AEAAXIJ@Z; AccessibilityCplCore::ErrorMessage(uint,long)
0x180012a6d  lea     rcx, [rsp+68h+var_38]
0x180012a72  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180012a77  add     rsp, 48h
0x180012a7b  pop     rdi
0x180012a7c  pop     rsi
0x180012a7d  pop     rbp
0x180012a7e  pop     rbx
0x180012a7f  retn
```
