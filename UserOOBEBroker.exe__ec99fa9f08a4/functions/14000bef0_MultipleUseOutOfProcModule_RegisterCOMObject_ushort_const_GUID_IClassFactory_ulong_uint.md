# MultipleUseOutOfProcModule::RegisterCOMObject(ushort const *,_GUID *,IClassFactory * *,ulong *,uint)

- ea: `0x14000bef0`
- end: `0x14000bf89`
- name: `?RegisterCOMObject@MultipleUseOutOfProcModule@@UEAAJPEBGPEAU_GUID@@PEAPEAUIClassFactory@@PEAKI@Z`
- size: `153`
- prototype: `__int64 __fastcall(MultipleUseOutOfProcModule *__hidden this, const unsigned __int16 *, struct _GUID *, struct IClassFactory **, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000bef0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x14000bf50`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x14000bf50`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x14000bf66`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x14000bf66`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000bf3e`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000bf3e`

## pseudocode

```c
__int64 __fastcall MultipleUseOutOfProcModule::RegisterCOMObject(
        MultipleUseOutOfProcModule *this,
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
      v10 = CoRegisterClassObject(&a3[(unsigned int)v7], (LPUNKNOWN)a4[v7], 4u, 5u, &a5[v7]);
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
0x14000bef0  push    rbx
0x14000bef2  push    rbp
0x14000bef3  push    rsi
0x14000bef4  push    rdi
0x14000bef5  push    r14
0x14000bef7  push    r15
0x14000bef9  sub     rsp, 38h
0x14000befd  mov     ebx, [rsp+68h+arg_28]
0x14000bf04  xor     edi, edi
0x14000bf06  mov     r14, [rsp+68h+arg_20]
0x14000bf0e  xor     ebp, ebp
0x14000bf10  mov     rsi, r9
0x14000bf13  mov     r15, r8
0x14000bf16  test    ebx, ebx
0x14000bf18  jz      short loc_14000BF50
0x14000bf1a  test    edi, edi
0x14000bf1c  js      short loc_14000BF5C
0x14000bf1e  mov     rdx, [rsi+rbp*8]; pUnk
0x14000bf22  lea     rax, [r14+rbp*4]
0x14000bf26  mov     r9d, 5; flags
0x14000bf2c  mov     ecx, ebp
0x14000bf2e  shl     rcx, 4
0x14000bf32  add     rcx, r15; rclsid
0x14000bf35  mov     [rsp+68h+lpdwRegister], rax; lpdwRegister
0x14000bf3a  lea     r8d, [r9-1]; dwClsContext
0x14000bf3e  call    cs:__imp_CoRegisterClassObject
0x14000bf44  inc     ebp
0x14000bf46  mov     edi, eax
0x14000bf48  cmp     ebp, ebx
0x14000bf4a  jb      short loc_14000BF1A
0x14000bf4c  test    eax, eax
0x14000bf4e  js      short loc_14000BF5C
0x14000bf50  call    cs:__imp_CoResumeClassObjects
0x14000bf56  mov     edi, eax
0x14000bf58  test    eax, eax
0x14000bf5a  jns     short loc_14000BF7A
0x14000bf5c  xor     esi, esi
0x14000bf5e  test    ebp, ebp
0x14000bf60  jz      short loc_14000BF7A
0x14000bf62  mov     ecx, [r14+rsi*4]; dwRegister
0x14000bf66  call    cs:__imp_CoRevokeClassObject
0x14000bf6c  mov     dword ptr [r14+rsi*4], 0
0x14000bf74  inc     esi
0x14000bf76  cmp     esi, ebp
0x14000bf78  jb      short loc_14000BF62
0x14000bf7a  mov     eax, edi
0x14000bf7c  add     rsp, 38h
0x14000bf80  pop     r15
0x14000bf82  pop     r14
0x14000bf84  pop     rdi
0x14000bf85  pop     rsi
0x14000bf86  pop     rbp
0x14000bf87  pop     rbx
0x14000bf88  retn
```
