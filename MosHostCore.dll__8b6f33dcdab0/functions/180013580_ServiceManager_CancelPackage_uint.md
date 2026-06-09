# ServiceManager::CancelPackage(uint)

- ea: `0x180013580`
- end: `0x18001367c`
- name: `?CancelPackage@ServiceManager@@UEAAJI@Z`
- size: `252`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800101bc`
- `0x180013400`
- `0x180013580`
- `0x180014c00`
- `0x18001aea4`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001360e`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001360e`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800135c4`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800135c4`

## string_xrefs

- `0x1800135b8`: `ServiceManager::CancelPackage`
- `0x180013605`: `ServiceManager::CancelPackage`

## pseudocode

```c
__int64 __fastcall ServiceManager::CancelPackage(ServiceManager *this, unsigned int a2)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  PackageManager *v6; // rcx
  int v7; // eax
  int v8; // r8d
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v10);
  if ( *((_DWORD *)this + 882) == 5 )
  {
    v5 = 0;
    v6 = (ServiceManager *)((char *)this + 3568);
    if ( a2 != *((_DWORD *)this + 952) )
    {
      PackageManager::OnPackageCanceled(v6, a2);
      goto LABEL_15;
    }
    if ( *((_DWORD *)this + 881) == 1 )
    {
      v7 = ServiceManager::OnOperationComplete(this, -2147023673);
      if ( v7 >= 0 )
      {
        v7 = ServiceManager::DetachClient((__int64)this, 2u, 0);
        if ( v7 >= 0 )
        {
          *((_DWORD *)this + 881) = 2;
          goto LABEL_15;
        }
        v8 = 944;
      }
      else
      {
        v8 = 943;
      }
    }
    else
    {
      PackageManager::OnPackageCanceled(v6, a2);
      v7 = ServiceManager::CancelOperation(this, 0);
      if ( v7 >= 0 )
        goto LABEL_15;
      v8 = 956;
    }
    v4 = ZTraceReportPropagation(v7, "ServiceManager::CancelPackage", v8, this);
  }
  else
  {
    v4 = ZTraceReportOrigination(-2147024875, "ServiceManager::CancelPackage", 935, this);
  }
  v5 = v4;
LABEL_15:
  RelockableGate::~RelockableGate((RelockableGate *)v10);
  return v5;
}

```

## disassembly

```asm
0x180013580  mov     [rsp+arg_0], rbx
0x180013585  mov     [rsp+arg_8], rsi
0x18001358a  push    rdi
0x18001358b  sub     rsp, 30h
0x18001358f  mov     esi, edx
0x180013591  mov     rbx, rcx
0x180013594  add     rcx, 0D48h
0x18001359b  lea     rdx, [rsp+38h+var_18]
0x1800135a0  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x1800135a5  nop
0x1800135a6  cmp     dword ptr [rbx+0DC8h], 5
0x1800135ad  jz      short loc_1800135D1
0x1800135af  mov     r9, rbx
0x1800135b2  mov     r8d, 3A7h
0x1800135b8  lea     rdx, aServicemanager_61; "ServiceManager::CancelPackage"
0x1800135bf  mov     ecx, 80070015h
0x1800135c4  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x1800135ca  mov     edi, eax
0x1800135cc  jmp     loc_180013660
0x1800135d1  xor     edi, edi
0x1800135d3  lea     rcx, [rbx+0DF0h]; this
0x1800135da  cmp     esi, [rcx+0F0h]
0x1800135e0  jnz     short loc_180013658
0x1800135e2  cmp     dword ptr [rbx+0DC4h], 1
0x1800135e9  jnz     short loc_18001363B
0x1800135eb  mov     edx, 800704C7h; int
0x1800135f0  mov     rcx, rbx; this
0x1800135f3  call    ?OnOperationComplete@ServiceManager@@AEAAJJ@Z; ServiceManager::OnOperationComplete(long)
0x1800135f8  test    eax, eax
0x1800135fa  jns     short loc_180013616
0x1800135fc  mov     r8d, 3AFh
0x180013602  mov     r9, rbx
0x180013605  lea     rdx, aServicemanager_61; "ServiceManager::CancelPackage"
0x18001360c  mov     ecx, eax
0x18001360e  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180013614  jmp     short loc_1800135CA
0x180013616  xor     r8d, r8d
0x180013619  lea     esi, [r8+2]
0x18001361d  mov     edx, esi
0x18001361f  mov     rcx, rbx
0x180013622  call    ?DetachClient@ServiceManager@@UEAAJW4MapsClientType@@K@Z; ServiceManager::DetachClient(MapsClientType,ulong)
0x180013627  test    eax, eax
0x180013629  jns     short loc_180013633
0x18001362b  mov     r8d, 3B0h
0x180013631  jmp     short loc_180013602
0x180013633  mov     [rbx+0DC4h], esi
0x180013639  jmp     short loc_180013660
0x18001363b  mov     edx, esi; unsigned int
0x18001363d  call    ?OnPackageCanceled@PackageManager@@QEAAJI@Z; PackageManager::OnPackageCanceled(uint)
0x180013642  xor     edx, edx
0x180013644  mov     rcx, rbx
0x180013647  call    ?CancelOperation@ServiceManager@@AEAAJW4CANCELLATION_TYPE@1@@Z; ServiceManager::CancelOperation(ServiceManager::CANCELLATION_TYPE)
0x18001364c  test    eax, eax
0x18001364e  jns     short loc_180013660
0x180013650  mov     r8d, 3BCh
0x180013656  jmp     short loc_180013602
0x180013658  mov     edx, esi; unsigned int
0x18001365a  call    ?OnPackageCanceled@PackageManager@@QEAAJI@Z; PackageManager::OnPackageCanceled(uint)
0x18001365f  nop
0x180013660  lea     rcx, [rsp+38h+var_18]; this
0x180013665  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001366a  mov     eax, edi
0x18001366c  mov     rbx, [rsp+38h+arg_0]
0x180013671  mov     rsi, [rsp+38h+arg_8]
0x180013676  add     rsp, 30h
0x18001367a  pop     rdi
0x18001367b  retn
```
