# Microsoft::WRL::Details::RegisterCOMObject<1>(ushort const *,_GUID *,IClassFactory * *,ulong *,uint)

- ea: `0x140006960`
- end: `0x1400069f4`
- name: `??$RegisterCOMObject@$00@Details@WRL@Microsoft@@YAJPEBGPEAU_GUID@@PEAPEAUIClassFactory@@PEAKI@Z`
- size: `148`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008420`

## callees

- `0x140006960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x1400069bb`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x1400069bb`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400069d1`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400069d1`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1400069a9`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1400069a9`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RegisterCOMObject<1>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  HRESULT v5; // edi
  __int64 v6; // rbp
  HRESULT v10; // eax
  __int64 i; // rsi

  v5 = 0;
  v6 = 0;
  if ( a5 )
  {
    while ( v5 >= 0 )
    {
      v10 = CoRegisterClassObject(
              (const IID *const)(a2 + 16LL * (unsigned int)v6),
              *(LPUNKNOWN *)(a3 + 8 * v6),
              4u,
              5u,
              (LPDWORD)(a4 + 4 * v6));
      v6 = (unsigned int)(v6 + 1);
      v5 = v10;
      if ( (unsigned int)v6 >= a5 )
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
    v5 = CoResumeClassObjects();
    if ( v5 >= 0 )
      return (unsigned int)v5;
  }
  for ( i = 0; (unsigned int)i < (unsigned int)v6; i = (unsigned int)(i + 1) )
  {
    CoRevokeClassObject(*(_DWORD *)(a4 + 4 * i));
    *(_DWORD *)(a4 + 4 * i) = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140006960  push    rbx
0x140006962  push    rbp
0x140006963  push    rsi
0x140006964  push    rdi
0x140006965  push    r14
0x140006967  push    r15
0x140006969  sub     rsp, 38h
0x14000696d  mov     ebx, [rsp+68h+arg_20]
0x140006974  xor     edi, edi
0x140006976  xor     ebp, ebp
0x140006978  mov     r14, r9
0x14000697b  mov     rsi, r8
0x14000697e  mov     r15, rdx
0x140006981  test    ebx, ebx
0x140006983  jz      short loc_1400069BB
0x140006985  test    edi, edi
0x140006987  js      short loc_1400069C7
0x140006989  mov     rdx, [rsi+rbp*8]; pUnk
0x14000698d  lea     rax, [r14+rbp*4]
0x140006991  mov     r9d, 5; flags
0x140006997  mov     ecx, ebp
0x140006999  shl     rcx, 4
0x14000699d  add     rcx, r15; rclsid
0x1400069a0  mov     [rsp+68h+lpdwRegister], rax; lpdwRegister
0x1400069a5  lea     r8d, [r9-1]; dwClsContext
0x1400069a9  call    cs:__imp_CoRegisterClassObject
0x1400069af  inc     ebp
0x1400069b1  mov     edi, eax
0x1400069b3  cmp     ebp, ebx
0x1400069b5  jb      short loc_140006985
0x1400069b7  test    eax, eax
0x1400069b9  js      short loc_1400069C7
0x1400069bb  call    cs:__imp_CoResumeClassObjects
0x1400069c1  mov     edi, eax
0x1400069c3  test    eax, eax
0x1400069c5  jns     short loc_1400069E5
0x1400069c7  xor     esi, esi
0x1400069c9  test    ebp, ebp
0x1400069cb  jz      short loc_1400069E5
0x1400069cd  mov     ecx, [r14+rsi*4]; dwRegister
0x1400069d1  call    cs:__imp_CoRevokeClassObject
0x1400069d7  mov     dword ptr [r14+rsi*4], 0
0x1400069df  inc     esi
0x1400069e1  cmp     esi, ebp
0x1400069e3  jb      short loc_1400069CD
0x1400069e5  mov     eax, edi
0x1400069e7  add     rsp, 38h
0x1400069eb  pop     r15
0x1400069ed  pop     r14
0x1400069ef  pop     rdi
0x1400069f0  pop     rsi
0x1400069f1  pop     rbp
0x1400069f2  pop     rbx
0x1400069f3  retn
```
