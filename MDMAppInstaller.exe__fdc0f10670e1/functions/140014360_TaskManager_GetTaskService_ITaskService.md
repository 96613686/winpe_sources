# TaskManager::GetTaskService(ITaskService * *)

- ea: `0x140014360`
- end: `0x140014480`
- name: `?GetTaskService@TaskManager@@CAJPEAPEAUITaskService@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(LPVOID *)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140013c90`
- `0x140013e20`
- `0x140013f34`
- `0x140014038`
- `0x140014664`
- `0x140015108`

## callees

- `0x14000740c`
- `0x140014360`
- `0x14001c010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1400143bd`
- `ole32!CoCreateInstance` at `0x1400143bd`
- `OLEAUT32!__imp_VariantInit` at `0x140014393`
- `OLEAUT32!__imp_VariantInit` at `0x140014393`
- `OLEAUT32!__imp_VariantClear` at `0x140014451`
- `OLEAUT32!__imp_VariantClear` at `0x140014451`

## string_xrefs

- `0x14001445d`: `GetTaskService() failed.  Error = 0x%1!x!.`

## pseudocode

```c
__int64 __fastcall TaskManager::GetTaskService(LPVOID *a1)
{
  HRESULT v2; // ebx
  __int64 v3; // rax
  __int64 (__fastcall *v4)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  LPVOID v5; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-49h] BYREF
  __int128 v8; // [rsp+50h] [rbp-29h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-19h]
  VARIANTARG v10; // [rsp+70h] [rbp-9h] BYREF
  VARIANTARG v11; // [rsp+90h] [rbp+17h] BYREF
  VARIANTARG v12; // [rsp+B0h] [rbp+37h] BYREF
  LPVOID ppv; // [rsp+E0h] [rbp+67h] BYREF

  ppv = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  *a1 = 0;
  v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v2 < 0 )
    goto LABEL_4;
  v8 = *(_OWORD *)&pvarg.vt;
  v3 = *(_QWORD *)ppv;
  pRecInfo = pvarg.pRecInfo;
  v10 = pvarg;
  v4 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v3 + 80);
  v11 = pvarg;
  v12 = pvarg;
  v2 = v4(ppv, &v12, &v11, &v10, &v8);
  if ( v2 < 0 )
  {
LABEL_4:
    v5 = ppv;
  }
  else
  {
    v5 = 0;
    *a1 = ppv;
    ppv = 0;
  }
  if ( v5 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
    ppv = 0;
  }
  VariantClear(&pvarg);
  if ( v2 < 0 )
    LogError(L"GetTaskService() failed.  Error = 0x%1!x!.", (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140014360  mov     [rsp-8+arg_8], rbx
0x140014365  mov     [rsp-8+arg_10], rdi
0x14001436a  push    rbp
0x14001436b  lea     rbp, [rsp-57h]
0x140014370  sub     rsp, 0D0h
0x140014377  mov     rdi, rcx
0x14001437a  mov     [rbp+57h+arg_0], 0
0x140014382  xorps   xmm0, xmm0
0x140014385  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140014389  xor     eax, eax
0x14001438b  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x14001438f  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x140014393  call    cs:__imp_VariantInit
0x140014399  xor     edx, edx; pUnkOuter
0x14001439b  mov     qword ptr [rdi], 0
0x1400143a2  lea     rax, [rbp+57h+arg_0]
0x1400143a6  lea     r9, IID_ITaskService; riid
0x1400143ad  mov     [rsp+0D0h+ppv], rax; ppv
0x1400143b2  lea     rcx, CLSID_TaskScheduler; rclsid
0x1400143b9  lea     r8d, [rdx+1]; dwClsContext
0x1400143bd  call    cs:__imp_CoCreateInstance
0x1400143c3  mov     ebx, eax
0x1400143c5  test    eax, eax
0x1400143c7  js      short loc_140014430
0x1400143c9  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x1400143cd  lea     rdx, [rbp+57h+var_80]
0x1400143d1  mov     rcx, [rbp+57h+arg_0]
0x1400143d5  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x1400143da  lea     r9, [rbp+57h+var_60]
0x1400143de  mov     [rsp+0D0h+ppv], rdx
0x1400143e3  lea     r8, [rbp+57h+var_40]
0x1400143e7  lea     rdx, [rbp+57h+var_20]
0x1400143eb  movaps  [rbp+57h+var_80], xmm1
0x1400143ef  mov     rax, [rcx]
0x1400143f2  movsd   [rbp+57h+var_70], xmm0
0x1400143f7  movaps  [rbp+57h+var_60], xmm1
0x1400143fb  movsd   [rbp+57h+var_50], xmm0
0x140014400  mov     rax, [rax+50h]
0x140014404  movaps  [rbp+57h+var_40], xmm1
0x140014408  movsd   [rbp+57h+var_30], xmm0
0x14001440d  movaps  [rbp+57h+var_20], xmm1
0x140014411  movsd   [rbp+57h+var_10], xmm0
0x140014416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001441b  mov     ebx, eax
0x14001441d  test    eax, eax
0x14001441f  js      short loc_140014430
0x140014421  mov     rax, [rbp+57h+arg_0]
0x140014425  xor     ecx, ecx
0x140014427  mov     [rdi], rax
0x14001442a  mov     [rbp+57h+arg_0], rcx
0x14001442e  jmp     short loc_140014434
0x140014430  mov     rcx, [rbp+57h+arg_0]
0x140014434  test    rcx, rcx
0x140014437  jz      short loc_14001444D
0x140014439  mov     rax, [rcx]
0x14001443c  mov     rax, [rax+10h]
0x140014440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014445  mov     [rbp+57h+arg_0], 0
0x14001444d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140014451  call    cs:__imp_VariantClear
0x140014457  test    ebx, ebx
0x140014459  jns     short loc_140014469
0x14001445b  mov     edx, ebx
0x14001445d  lea     rcx, aGettaskservice; "GetTaskService() failed.  Error = 0x%1!"...
0x140014464  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140014469  lea     r11, [rsp+0D0h+var_s0]
0x140014471  mov     eax, ebx
0x140014473  mov     rbx, [r11+18h]
0x140014477  mov     rdi, [r11+20h]
0x14001447b  mov     rsp, r11
0x14001447e  pop     rbp
0x14001447f  retn
```
