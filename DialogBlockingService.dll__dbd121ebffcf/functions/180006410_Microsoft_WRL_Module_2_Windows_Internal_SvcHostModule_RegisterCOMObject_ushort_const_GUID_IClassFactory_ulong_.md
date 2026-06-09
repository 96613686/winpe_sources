# Microsoft::WRL::Module<2,Windows::Internal::SvcHostModule>::RegisterCOMObject(ushort const *,_GUID *,IClassFactory * *,ulong *,uint)

- ea: `0x180006410`
- end: `0x1800064a9`
- name: `?RegisterCOMObject@?$Module@$01VSvcHostModule@Internal@Windows@@@WRL@Microsoft@@UEAAJPEBGPEAU_GUID@@PEAPEAUIClassFactory@@PEAKI@Z`
- size: `153`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006410`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180006486`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180006486`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18000645e`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18000645e`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x180006470`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x180006470`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Module<2,Windows::Internal::SvcHostModule>::RegisterCOMObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6)
{
  HRESULT v6; // edi
  __int64 v7; // rbp
  HRESULT v10; // eax
  __int64 i; // rsi

  v6 = 0;
  v7 = 0;
  if ( a6 )
  {
    while ( v6 >= 0 )
    {
      v10 = CoRegisterClassObject(
              (const IID *const)(a3 + 16LL * (unsigned int)v7),
              *(LPUNKNOWN *)(a4 + 8 * v7),
              4u,
              5u,
              (LPDWORD)(a5 + 4 * v7));
      v7 = (unsigned int)(v7 + 1);
      v6 = v10;
      if ( (unsigned int)v7 >= a6 )
      {
        if ( v10 < 0 )
          break;
        goto LABEL_5;
      }
    }
  }
  else
  {
LABEL_5:
    v6 = CoResumeClassObjects();
    if ( v6 >= 0 )
      return (unsigned int)v6;
  }
  for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
  {
    CoRevokeClassObject(*(_DWORD *)(a5 + 4 * i));
    *(_DWORD *)(a5 + 4 * i) = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006410  push    rbx
0x180006412  push    rbp
0x180006413  push    rsi
0x180006414  push    rdi
0x180006415  push    r14
0x180006417  push    r15
0x180006419  sub     rsp, 38h
0x18000641d  mov     ebx, [rsp+68h+arg_28]
0x180006424  xor     edi, edi
0x180006426  mov     r14, [rsp+68h+arg_20]
0x18000642e  xor     ebp, ebp
0x180006430  mov     rsi, r9
0x180006433  mov     r15, r8
0x180006436  test    ebx, ebx
0x180006438  jz      short loc_180006470
0x18000643a  test    edi, edi
0x18000643c  js      short loc_18000647C
0x18000643e  mov     rdx, [rsi+rbp*8]; pUnk
0x180006442  lea     rax, [r14+rbp*4]
0x180006446  mov     r9d, 5; flags
0x18000644c  mov     ecx, ebp
0x18000644e  shl     rcx, 4
0x180006452  add     rcx, r15; rclsid
0x180006455  mov     [rsp+68h+lpdwRegister], rax; lpdwRegister
0x18000645a  lea     r8d, [r9-1]; dwClsContext
0x18000645e  call    cs:__imp_CoRegisterClassObject
0x180006464  inc     ebp
0x180006466  mov     edi, eax
0x180006468  cmp     ebp, ebx
0x18000646a  jb      short loc_18000643A
0x18000646c  test    eax, eax
0x18000646e  js      short loc_18000647C
0x180006470  call    cs:__imp_CoResumeClassObjects
0x180006476  mov     edi, eax
0x180006478  test    eax, eax
0x18000647a  jns     short loc_18000649A
0x18000647c  xor     esi, esi
0x18000647e  test    ebp, ebp
0x180006480  jz      short loc_18000649A
0x180006482  mov     ecx, [r14+rsi*4]; dwRegister
0x180006486  call    cs:__imp_CoRevokeClassObject
0x18000648c  mov     dword ptr [r14+rsi*4], 0
0x180006494  inc     esi
0x180006496  cmp     esi, ebp
0x180006498  jb      short loc_180006482
0x18000649a  mov     eax, edi
0x18000649c  add     rsp, 38h
0x1800064a0  pop     r15
0x1800064a2  pop     r14
0x1800064a4  pop     rdi
0x1800064a5  pop     rsi
0x1800064a6  pop     rbp
0x1800064a7  pop     rbx
0x1800064a8  retn
```
