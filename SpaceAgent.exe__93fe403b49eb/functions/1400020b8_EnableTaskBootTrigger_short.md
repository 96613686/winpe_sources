# EnableTaskBootTrigger(short)

- ea: `0x1400020b8`
- end: `0x1400021d0`
- name: `?EnableTaskBootTrigger@@YAXF@Z`
- size: `280`
- prototype: `void __fastcall(__int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140002868`

## callees

- `0x1400020b8`
- `0x1400021d8`
- `0x14000266c`
- `0x140020010`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x1400021a4`
- `ADVAPI32!FreeSid` at `0x1400021a4`
- `msvcrt!free` at `0x1400021b3`
- `msvcrt!free` at `0x1400021b3`
- `ole32!CoCreateInstance` at `0x140002175`
- `ole32!CoCreateInstance` at `0x140002175`
- `ole32!CoUninitialize` at `0x1400021b9`
- `ole32!CoUninitialize` at `0x1400021b9`
- `ole32!CoInitializeEx` at `0x1400020f0`
- `ole32!CoInitializeEx` at `0x1400020f0`
- `ole32!CoInitializeSecurity` at `0x14000214e`
- `ole32!CoInitializeSecurity` at `0x14000214e`

## pseudocode

```c
void __fastcall EnableTaskBootTrigger(__int16 a1)
{
  unsigned int v2; // ecx
  _OWORD pSecDesc[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v4; // [rsp+70h] [rbp-10h]
  LPVOID ppv; // [rsp+98h] [rbp+18h] BYREF
  PSID pSid; // [rsp+A0h] [rbp+20h] BYREF
  void *Block; // [rsp+A8h] [rbp+28h] BYREF

  ppv = 0;
  v4 = 0;
  Block = 0;
  pSid = 0;
  memset(pSecDesc, 0, sizeof(pSecDesc));
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    if ( (InitializeEveryoneSecurityDescriptor(v2, pSecDesc, (struct _ACL **)&Block, &pSid) & 0x80000000) == 0
      && CoInitializeSecurity(pSecDesc, -1, 0, 0, 6u, 3u, 0, 0, 0) >= 0
      && CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv) >= 0 )
    {
      EnableTaskBootTriggerInternal((struct ITaskService *)ppv, a1);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( pSid )
      FreeSid(pSid);
    if ( Block )
      free(Block);
  }
  CoUninitialize();
}

```

## disassembly

```asm
0x1400020b8  mov     [rsp-8+arg_0], rbx
0x1400020bd  push    rbp
0x1400020be  mov     rbp, rsp
0x1400020c1  sub     rsp, 80h
0x1400020c8  xor     eax, eax
0x1400020ca  mov     [rbp+ppv], 0
0x1400020d2  xorps   xmm0, xmm0
0x1400020d5  mov     [rbp+var_10], rax
0x1400020d9  movzx   ebx, cx
0x1400020dc  mov     [rbp+Block], rax
0x1400020e0  xor     ecx, ecx; pvReserved
0x1400020e2  mov     [rbp+pSid], rax
0x1400020e6  xor     edx, edx; dwCoInit
0x1400020e8  movups  [rbp+pSecDesc], xmm0
0x1400020ec  movups  [rbp+var_20], xmm0
0x1400020f0  call    cs:__imp_CoInitializeEx
0x1400020f6  test    eax, eax
0x1400020f8  js      loc_1400021B9
0x1400020fe  lea     r9, [rbp+pSid]; void **
0x140002102  lea     r8, [rbp+Block]; struct _ACL **
0x140002106  lea     rdx, [rbp+pSecDesc]; void *
0x14000210a  call    ?InitializeEveryoneSecurityDescriptor@@YAKKPEAXPEAPEAU_ACL@@PEAPEAX@Z; InitializeEveryoneSecurityDescriptor(ulong,void *,_ACL * *,void * *)
0x14000210f  test    eax, eax
0x140002111  js      loc_14000219B
0x140002117  mov     [rsp+80h+pReserved3], 0; pReserved3
0x140002120  lea     rcx, [rbp+pSecDesc]; pSecDesc
0x140002124  mov     [rsp+80h+dwCapabilities], 0; dwCapabilities
0x14000212c  xor     r9d, r9d; pReserved1
0x14000212f  mov     [rsp+80h+pAuthList], 0; pAuthList
0x140002138  xor     r8d, r8d; asAuthSvc
0x14000213b  mov     [rsp+80h+dwImpLevel], 3; dwImpLevel
0x140002143  or      edx, 0FFFFFFFFh; cAuthSvc
0x140002146  mov     [rsp+80h+dwAuthnLevel], 6; dwAuthnLevel
0x14000214e  call    cs:__imp_CoInitializeSecurity
0x140002154  test    eax, eax
0x140002156  js      short loc_14000219B
0x140002158  xor     edx, edx; pUnkOuter
0x14000215a  lea     rax, [rbp+ppv]
0x14000215e  lea     r9, IID_ITaskService; riid
0x140002165  mov     qword ptr [rsp+80h+dwAuthnLevel], rax; ppv
0x14000216a  lea     rcx, CLSID_TaskScheduler; rclsid
0x140002171  lea     r8d, [rdx+1]; dwClsContext
0x140002175  call    cs:__imp_CoCreateInstance
0x14000217b  test    eax, eax
0x14000217d  js      short loc_14000219B
0x14000217f  mov     rcx, [rbp+ppv]; struct ITaskService *
0x140002183  movzx   edx, bx; __int16
0x140002186  call    ?EnableTaskBootTriggerInternal@@YAXPEAUITaskService@@F@Z; EnableTaskBootTriggerInternal(ITaskService *,short)
0x14000218b  mov     rcx, [rbp+ppv]
0x14000218f  mov     rax, [rcx]
0x140002192  mov     rax, [rax+10h]
0x140002196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000219b  mov     rcx, [rbp+pSid]; pSid
0x14000219f  test    rcx, rcx
0x1400021a2  jz      short loc_1400021AA
0x1400021a4  call    cs:__imp_FreeSid
0x1400021aa  mov     rcx, [rbp+Block]; Block
0x1400021ae  test    rcx, rcx
0x1400021b1  jz      short loc_1400021B9
0x1400021b3  call    cs:__imp_free
0x1400021b9  call    cs:__imp_CoUninitialize
0x1400021bf  mov     rbx, [rsp+80h+arg_0]
0x1400021c7  add     rsp, 80h
0x1400021ce  pop     rbp
0x1400021cf  retn
```
