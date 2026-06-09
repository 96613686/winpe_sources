# Microsoft::WRL::Module<2,Windows::Internal::SvcHostModule>::RegisterCOMObject(ushort const *,_GUID *,IClassFactory * *,ulong *,uint)

- ea: `0x180006020`
- end: `0x1800060b9`
- name: `?RegisterCOMObject@?$Module@$01VSvcHostModule@Internal@Windows@@@WRL@Microsoft@@UEAAJPEBGPEAU_GUID@@PEAPEAUIClassFactory@@PEAKI@Z`
- size: `153`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180006096`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180006096`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18000606e`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18000606e`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x180006080`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x180006080`

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
0x180006020  push    rbx
0x180006022  push    rbp
0x180006023  push    rsi
0x180006024  push    rdi
0x180006025  push    r14
0x180006027  push    r15
0x180006029  sub     rsp, 38h
0x18000602d  mov     ebx, [rsp+68h+arg_28]
0x180006034  xor     edi, edi
0x180006036  mov     r14, [rsp+68h+arg_20]
0x18000603e  xor     ebp, ebp
0x180006040  mov     rsi, r9
0x180006043  mov     r15, r8
0x180006046  test    ebx, ebx
0x180006048  jz      short loc_180006080
0x18000604a  test    edi, edi
0x18000604c  js      short loc_18000608C
0x18000604e  mov     rdx, [rsi+rbp*8]; pUnk
0x180006052  lea     rax, [r14+rbp*4]
0x180006056  mov     r9d, 5; flags
0x18000605c  mov     ecx, ebp
0x18000605e  shl     rcx, 4
0x180006062  add     rcx, r15; rclsid
0x180006065  mov     [rsp+68h+lpdwRegister], rax; lpdwRegister
0x18000606a  lea     r8d, [r9-1]; dwClsContext
0x18000606e  call    cs:__imp_CoRegisterClassObject
0x180006074  inc     ebp
0x180006076  mov     edi, eax
0x180006078  cmp     ebp, ebx
0x18000607a  jb      short loc_18000604A
0x18000607c  test    eax, eax
0x18000607e  js      short loc_18000608C
0x180006080  call    cs:__imp_CoResumeClassObjects
0x180006086  mov     edi, eax
0x180006088  test    eax, eax
0x18000608a  jns     short loc_1800060AA
0x18000608c  xor     esi, esi
0x18000608e  test    ebp, ebp
0x180006090  jz      short loc_1800060AA
0x180006092  mov     ecx, [r14+rsi*4]; dwRegister
0x180006096  call    cs:__imp_CoRevokeClassObject
0x18000609c  mov     dword ptr [r14+rsi*4], 0
0x1800060a4  inc     esi
0x1800060a6  cmp     esi, ebp
0x1800060a8  jb      short loc_180006092
0x1800060aa  mov     eax, edi
0x1800060ac  add     rsp, 38h
0x1800060b0  pop     r15
0x1800060b2  pop     r14
0x1800060b4  pop     rdi
0x1800060b5  pop     rsi
0x1800060b6  pop     rbp
0x1800060b7  pop     rbx
0x1800060b8  retn
```
