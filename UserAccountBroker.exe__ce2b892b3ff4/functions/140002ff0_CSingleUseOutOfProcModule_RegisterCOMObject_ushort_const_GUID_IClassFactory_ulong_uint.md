# CSingleUseOutOfProcModule::RegisterCOMObject(ushort const *,_GUID *,IClassFactory * *,ulong *,uint)

- ea: `0x140002ff0`
- end: `0x140003088`
- name: `?RegisterCOMObject@CSingleUseOutOfProcModule@@UEAAJPEBGPEAU_GUID@@PEAPEAUIClassFactory@@PEAKI@Z`
- size: `152`
- prototype: `__int64 __fastcall(CSingleUseOutOfProcModule *__hidden this, const unsigned __int16 *, struct _GUID *, struct IClassFactory **, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002ff0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140003065`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140003065`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x14000304f`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x14000304f`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000303d`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000303d`

## pseudocode

```c
__int64 __fastcall CSingleUseOutOfProcModule::RegisterCOMObject(
        CSingleUseOutOfProcModule *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct IClassFactory **a4,
        unsigned int *a5,
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
      v10 = CoRegisterClassObject(&a3[(unsigned int)v7], (LPUNKNOWN)a4[v7], 4u, 4u, &a5[v7]);
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
    CoRevokeClassObject(a5[i]);
    a5[i] = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140002ff0  push    rbx
0x140002ff2  push    rbp
0x140002ff3  push    rsi
0x140002ff4  push    rdi
0x140002ff5  push    r14
0x140002ff7  push    r15
0x140002ff9  sub     rsp, 38h
0x140002ffd  mov     ebx, [rsp+68h+arg_28]
0x140003004  xor     edi, edi
0x140003006  mov     r14, [rsp+68h+arg_20]
0x14000300e  xor     ebp, ebp
0x140003010  mov     rsi, r9
0x140003013  mov     r15, r8
0x140003016  test    ebx, ebx
0x140003018  jz      short loc_14000304F
0x14000301a  test    edi, edi
0x14000301c  js      short loc_14000305B
0x14000301e  mov     rdx, [rsi+rbp*8]; pUnk
0x140003022  lea     rax, [r14+rbp*4]
0x140003026  mov     r9d, 4; flags
0x14000302c  mov     ecx, ebp
0x14000302e  shl     rcx, 4
0x140003032  mov     r8d, r9d; dwClsContext
0x140003035  add     rcx, r15; rclsid
0x140003038  mov     [rsp+68h+lpdwRegister], rax; lpdwRegister
0x14000303d  call    cs:__imp_CoRegisterClassObject
0x140003043  inc     ebp
0x140003045  mov     edi, eax
0x140003047  cmp     ebp, ebx
0x140003049  jb      short loc_14000301A
0x14000304b  test    eax, eax
0x14000304d  js      short loc_14000305B
0x14000304f  call    cs:__imp_CoResumeClassObjects
0x140003055  mov     edi, eax
0x140003057  test    eax, eax
0x140003059  jns     short loc_140003079
0x14000305b  xor     esi, esi
0x14000305d  test    ebp, ebp
0x14000305f  jz      short loc_140003079
0x140003061  mov     ecx, [r14+rsi*4]; dwRegister
0x140003065  call    cs:__imp_CoRevokeClassObject
0x14000306b  mov     dword ptr [r14+rsi*4], 0
0x140003073  inc     esi
0x140003075  cmp     esi, ebp
0x140003077  jb      short loc_140003061
0x140003079  mov     eax, edi
0x14000307b  add     rsp, 38h
0x14000307f  pop     r15
0x140003081  pop     r14
0x140003083  pop     rdi
0x140003084  pop     rsi
0x140003085  pop     rbp
0x140003086  pop     rbx
0x140003087  retn
```
