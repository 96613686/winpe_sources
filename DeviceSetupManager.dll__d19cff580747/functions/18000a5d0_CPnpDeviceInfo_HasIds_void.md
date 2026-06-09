# CPnpDeviceInfo::HasIds(void)

- ea: `0x18000a5d0`
- end: `0x18000a6f7`
- name: `?HasIds@CPnpDeviceInfo@@QEAAHXZ`
- size: `295`
- prototype: `__int64 __fastcall(CPnpDeviceInfo *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003493c`

## callees

- `0x180005100`
- `0x18000a504`
- `0x18000a5d0`
- `0x18000a700`
- `0x18000a9c0`
- `0x1800112a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a6d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a6dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a6d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a6dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a647`

## pseudocode

```c
_BOOL8 __fastcall CPnpDeviceInfo::HasIds(CPnpDeviceInfo *this)
{
  __int64 v1; // rdx
  int DeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222; // eax
  BOOL v4; // ebx
  int v5; // eax
  const unsigned __int16 *v6; // rcx
  int v8; // [rsp+20h] [rbp-40h]
  struct tagPROPVARIANT pvar; // [rsp+30h] [rbp-30h] BYREF
  struct tagPROPVARIANT v10; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  LPVOID pv; // [rsp+70h] [rbp+10h] BYREF
  LPVOID *p_pv; // [rsp+78h] [rbp+18h] BYREF

  v1 = *((_QWORD *)this + 1);
  pv = 0;
  p_pv = &pv;
  memset(&v10, 0, sizeof(v10));
  DeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222 = GetDeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222_(
                                                                          3,
                                                                          v1,
                                                                          (unsigned int)&DEVPKEY_Device_HardwareIds,
                                                                          8210,
                                                                          (__int64)&p_pv);
  if ( DeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222 >= 0 )
  {
    v5 = MultiSzToPropVariant((const unsigned __int16 *)pv, &v10);
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x223,
        (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
        (const char *)(unsigned int)v5,
        v8);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
      goto LABEL_5;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
      (const char *)(unsigned int)DeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222,
      v8);
  }
  if ( pv )
    CoTaskMemFree(pv);
LABEL_5:
  if ( v10.lVal && v10.vt == 4127 )
  {
    v4 = 1;
  }
  else
  {
    v6 = (const unsigned __int16 *)*((_QWORD *)this + 1);
    memset(&pvar, 0, sizeof(pvar));
    GetDeviceStringListProperty(v6, &DEVPKEY_Device_CompatibleIds, &pvar);
    v4 = pvar.vt == 4127 && pvar.lVal;
    PropVariantClear((PROPVARIANT *)&pvar);
  }
  PropVariantClear((PROPVARIANT *)&v10);
  return v4;
}

```

## disassembly

```asm
0x18000a5d0  mov     [rsp-8+arg_10], rbx
0x18000a5d5  mov     [rsp-8+arg_18], rsi
0x18000a5da  push    rbp
0x18000a5db  mov     rbp, rsp
0x18000a5de  sub     rsp, 60h
0x18000a5e2  mov     rdx, [rcx+8]
0x18000a5e6  lea     r8, DEVPKEY_Device_HardwareIds
0x18000a5ed  xor     eax, eax
0x18000a5ef  mov     rbx, rcx
0x18000a5f2  mov     [rbp+var_8], rax
0x18000a5f6  xorps   xmm0, xmm0
0x18000a5f9  mov     [rbp+pv], rax
0x18000a5fd  mov     r9d, 2012h
0x18000a603  lea     rax, [rbp+pv]
0x18000a607  mov     ecx, 3
0x18000a60c  mov     [rbp+arg_8], rax
0x18000a610  lea     rax, [rbp+arg_8]
0x18000a614  mov     qword ptr [rsp+60h+var_40], rax; int
0x18000a619  movups  xmmword ptr [rbp+var_18], xmm0
0x18000a61d  call    GetDeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222___; GetDeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222_
0x18000a622  test    eax, eax
0x18000a624  jns     short loc_18000A665
0x18000a626  mov     rcx, [rbp+8]; this
0x18000a62a  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18000a631  mov     r9d, eax; char *
0x18000a634  mov     edx, 221h; void *
0x18000a639  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a63e  mov     rcx, [rbp+pv]; pv
0x18000a642  test    rcx, rcx
0x18000a645  jz      short loc_18000A64D
0x18000a647  call    cs:__imp_CoTaskMemFree
0x18000a64d  cmp     dword ptr [rbp+var_18+8], 0
0x18000a651  mov     esi, 101Fh
0x18000a656  jbe     short loc_18000A699
0x18000a658  cmp     word ptr [rbp+var_18], si
0x18000a65c  jnz     short loc_18000A699
0x18000a65e  mov     ebx, 1
0x18000a663  jmp     short loc_18000A6D9
0x18000a665  mov     rcx, [rbp+pv]; Src
0x18000a669  lea     rdx, [rbp+var_18]; struct tagPROPVARIANT *
0x18000a66d  call    ?MultiSzToPropVariant@@YAJPEBGPEAUtagPROPVARIANT@@@Z; MultiSzToPropVariant(ushort const *,tagPROPVARIANT *)
0x18000a672  test    eax, eax
0x18000a674  jns     short loc_18000A63E
0x18000a676  mov     rcx, [rbp+8]; this
0x18000a67a  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18000a681  mov     r9d, eax; char *
0x18000a684  mov     edx, 223h; void *
0x18000a689  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a68e  lea     rcx, [rbp+pv]
0x18000a692  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000a697  jmp     short loc_18000A64D
0x18000a699  mov     rcx, [rbx+8]; unsigned __int16 *
0x18000a69d  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x18000a6a1  xorps   xmm0, xmm0
0x18000a6a4  lea     rdx, DEVPKEY_Device_CompatibleIds; struct _DEVPROPKEY *
0x18000a6ab  xor     eax, eax
0x18000a6ad  movups  xmmword ptr [rbp+pvar], xmm0
0x18000a6b1  mov     [rbp+var_20], rax
0x18000a6b5  call    ?GetDeviceStringListProperty@@YAJPEBGAEBU_DEVPROPKEY@@PEAUtagPROPVARIANT@@@Z; GetDeviceStringListProperty(ushort const *,_DEVPROPKEY const &,tagPROPVARIANT *)
0x18000a6ba  cmp     word ptr [rbp+pvar], si
0x18000a6be  jnz     short loc_18000A6CD
0x18000a6c0  cmp     dword ptr [rbp+pvar+8], 0
0x18000a6c4  jbe     short loc_18000A6CD
0x18000a6c6  mov     ebx, 1
0x18000a6cb  jmp     short loc_18000A6CF
0x18000a6cd  xor     ebx, ebx
0x18000a6cf  lea     rcx, [rbp+pvar]; pvar
0x18000a6d3  call    cs:__imp_PropVariantClear
0x18000a6d9  lea     rcx, [rbp+var_18]; pvar
0x18000a6dd  call    cs:__imp_PropVariantClear
0x18000a6e3  lea     r11, [rsp+60h+var_s0]
0x18000a6e8  mov     eax, ebx
0x18000a6ea  mov     rbx, [r11+20h]
0x18000a6ee  mov     rsi, [r11+28h]
0x18000a6f2  mov     rsp, r11
0x18000a6f5  pop     rbp
0x18000a6f6  retn
```
