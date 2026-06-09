# GetDeviceStringListProperty(ushort const *,_DEVPROPKEY const &,tagPROPVARIANT *)

- ea: `0x18000a504`
- end: `0x18000a5c9`
- name: `?GetDeviceStringListProperty@@YAJPEBGAEBU_DEVPROPKEY@@PEAUtagPROPVARIANT@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _DEVPROPKEY *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a5d0`
- `0x180010f48`

## callees

- `0x180005100`
- `0x18000a504`
- `0x18000a700`
- `0x18000a9c0`
- `0x1800112a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a56a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a56a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5b6`

## pseudocode

```c
__int64 __fastcall GetDeviceStringListProperty(
        const unsigned __int16 *a1,
        const struct _DEVPROPKEY *a2,
        struct tagPROPVARIANT *a3)
{
  int DeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222; // eax
  unsigned int v5; // ebx
  int v7; // eax
  int v8; // [rsp+20h] [rbp-28h]
  LPVOID *p_pv; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID pv; // [rsp+68h] [rbp+20h] BYREF

  pv = 0;
  p_pv = &pv;
  DeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222 = GetDeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222_(
                                                                          3,
                                                                          (_DWORD)a1,
                                                                          (_DWORD)a2,
                                                                          8210,
                                                                          (__int64)&p_pv);
  v5 = DeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222;
  if ( DeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
      (const char *)(unsigned int)DeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222,
      v8);
    if ( pv )
      CoTaskMemFree(pv);
    return v5;
  }
  v7 = MultiSzToPropVariant((const unsigned __int16 *)pv, a3);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x223,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
      (const char *)(unsigned int)v7,
      v8);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
    return v5;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x18000a504  mov     r11, rsp
0x18000a507  mov     [r11+8], rbx
0x18000a50b  push    rdi
0x18000a50c  sub     rsp, 40h
0x18000a510  lea     rax, [r11+20h]
0x18000a514  mov     qword ptr [r11+20h], 0
0x18000a51c  mov     rdi, r8
0x18000a51f  mov     [r11-18h], rax
0x18000a523  mov     r8, rdx
0x18000a526  lea     rax, [r11-18h]
0x18000a52a  mov     rdx, rcx
0x18000a52d  mov     [r11-28h], rax
0x18000a531  mov     r9d, 2012h
0x18000a537  mov     ecx, 3
0x18000a53c  call    GetDeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222___; GetDeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222_
0x18000a541  mov     ebx, eax
0x18000a543  test    eax, eax
0x18000a545  jns     short loc_18000A574
0x18000a547  mov     rcx, [rsp+48h]; this
0x18000a54c  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18000a553  mov     r9d, eax; char *
0x18000a556  mov     edx, 221h; void *
0x18000a55b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a560  mov     rcx, [rsp+48h+pv]; pv
0x18000a565  test    rcx, rcx
0x18000a568  jz      short loc_18000A570
0x18000a56a  call    cs:__imp_CoTaskMemFree
0x18000a570  mov     eax, ebx
0x18000a572  jmp     short loc_18000A5BE
0x18000a574  mov     rcx, [rsp+48h+pv]; Src
0x18000a579  mov     rdx, rdi; struct tagPROPVARIANT *
0x18000a57c  call    ?MultiSzToPropVariant@@YAJPEBGPEAUtagPROPVARIANT@@@Z; MultiSzToPropVariant(ushort const *,tagPROPVARIANT *)
0x18000a581  mov     ebx, eax
0x18000a583  test    eax, eax
0x18000a585  jns     short loc_18000A5AC
0x18000a587  mov     rcx, [rsp+48h]; this
0x18000a58c  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18000a593  mov     r9d, eax; char *
0x18000a596  mov     edx, 223h; void *
0x18000a59b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5a0  lea     rcx, [rsp+48h+pv]
0x18000a5a5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000a5aa  jmp     short loc_18000A570
0x18000a5ac  mov     rcx, [rsp+48h+pv]; pv
0x18000a5b1  test    rcx, rcx
0x18000a5b4  jz      short loc_18000A5BC
0x18000a5b6  call    cs:__imp_CoTaskMemFree
0x18000a5bc  xor     eax, eax
0x18000a5be  mov     rbx, [rsp+48h+arg_0]
0x18000a5c3  add     rsp, 40h
0x18000a5c7  pop     rdi
0x18000a5c8  retn
```
