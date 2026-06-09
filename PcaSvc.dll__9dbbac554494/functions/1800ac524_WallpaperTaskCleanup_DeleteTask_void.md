# WallpaperTaskCleanup_DeleteTask(void)

- ea: `0x1800ac524`
- end: `0x1800ac7de`
- name: `?WallpaperTaskCleanup_DeleteTask@@YAKXZ`
- size: `698`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800ac7f0`

## callees

- `0x180012920`
- `0x1800ac524`
- `0x1800f7010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800ac645`
- `OLEAUT32!__imp_SysAllocString` at `0x1800ac6a1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800ac645`
- `OLEAUT32!__imp_SysAllocString` at `0x1800ac6a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac75e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac767`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac75e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac767`
- `OLEAUT32!__imp_VariantInit` at `0x1800ac586`
- `OLEAUT32!__imp_VariantInit` at `0x1800ac586`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ac5ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ac5ac`

## string_xrefs

- `0x1800ac653`: `Failed to allocate task folder name`
- `0x1800ac6af`: `Failed to allocate task name`
- `0x1800ac5b8`: `Failed to create a task scheduler [%x]`
- `0x1800ac54f`: `Deleting %ws task...`
- `0x1800ac730`: `Failed to delete task [%x]`
- `0x1800ac748`: `Task deleted.`
- `0x1800ac6e7`: `Task is not registered.`
- `0x1800ac6fb`: `Failed to get task [%x]`
- `0x1800ac53e`: `WallpaperTaskCleanup_DeleteTask`

## pseudocode

```c
__int64 WallpaperTaskCleanup_DeleteTask(void)
{
  OLECHAR *v0; // rsi
  OLECHAR *v1; // rdi
  HRESULT v2; // eax
  int v3; // ebx
  const char *v4; // r9
  int v5; // r8d
  __int64 v6; // rax
  __int64 (__fastcall *v7)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  BSTR v8; // rax
  const char *v9; // r9
  int v10; // r8d
  int v11; // ecx
  BSTR v12; // rax
  int v13; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-79h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-69h] BYREF
  __int128 v17; // [rsp+50h] [rbp-49h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-39h]
  VARIANTARG v19; // [rsp+70h] [rbp-29h] BYREF
  VARIANTARG v20; // [rsp+90h] [rbp-9h] BYREF
  VARIANTARG v21; // [rsp+B0h] [rbp+17h] BYREF
  __int64 v22; // [rsp+100h] [rbp+67h] BYREF
  LPVOID v23; // [rsp+108h] [rbp+6Fh] BYREF
  __int64 v24; // [rsp+110h] [rbp+77h] BYREF

  v0 = 0;
  v23 = 0;
  v22 = 0;
  v24 = 0;
  v1 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  AslLogCallPrintf(
    3,
    (unsigned int)"WallpaperTaskCleanup_DeleteTask",
    62,
    (unsigned int)"Deleting %ws task...",
    L"PcaWallpaperAppDetect");
  VariantInit(&pvarg);
  v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v23);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = "Failed to create a task scheduler [%x]";
    v5 = 73;
LABEL_3:
    LODWORD(ppv) = v2;
    AslLogCallPrintf(1, (unsigned int)"WallpaperTaskCleanup_DeleteTask", v5, (_DWORD)v4, ppv);
    goto LABEL_21;
  }
  v17 = *(_OWORD *)&pvarg.vt;
  v6 = *(_QWORD *)v23;
  pRecInfo = pvarg.pRecInfo;
  v19 = pvarg;
  v7 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v6 + 80);
  v20 = pvarg;
  v21 = pvarg;
  v2 = v7(v23, &v21, &v20, &v19, &v17);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = "Failed to connect to scheduler [%x]";
    v5 = 80;
    goto LABEL_3;
  }
  v8 = SysAllocString(L"Microsoft\\Windows\\Application Experience");
  v0 = v8;
  if ( !v8 )
  {
    v9 = "Failed to allocate task folder name";
    v10 = 88;
LABEL_8:
    v3 = -2147024888;
    v11 = 1;
    goto LABEL_20;
  }
  v2 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v23 + 56LL))(v23, v8, &v22);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = "Failed to get scheduler folder [%x]";
    v5 = 95;
    goto LABEL_3;
  }
  v12 = SysAllocString(L"PcaWallpaperAppDetect");
  v1 = v12;
  if ( !v12 )
  {
    v9 = "Failed to allocate task name";
    v10 = 103;
    goto LABEL_8;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v22 + 104LL))(v22, v12, &v24);
  if ( v13 < 0 )
  {
    if ( v13 == -2147024894 )
    {
      AslLogCallPrintf(3, (unsigned int)"WallpaperTaskCleanup_DeleteTask", 112, (unsigned int)"Task is not registered.");
      v3 = 0;
      goto LABEL_21;
    }
    LODWORD(ppv) = v13;
    AslLogCallPrintf(
      1,
      (unsigned int)"WallpaperTaskCleanup_DeleteTask",
      118,
      (unsigned int)"Failed to get task [%x]",
      ppv);
  }
  v2 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD))(*(_QWORD *)v22 + 120LL))(v22, v1, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = "Failed to delete task [%x]";
    v5 = 125;
    goto LABEL_3;
  }
  v10 = 129;
  v9 = "Task deleted.";
  v11 = 3;
LABEL_20:
  AslLogCallPrintf(v11, (unsigned int)"WallpaperTaskCleanup_DeleteTask", v10, (_DWORD)v9);
LABEL_21:
  SysFreeString(v0);
  SysFreeString(v1);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v23 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v3 < 0 )
  {
    if ( (v3 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v3;
  }
  else
  {
    return 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800ac524  mov     [rsp-8+arg_18], rbx
0x1800ac529  push    rbp
0x1800ac52a  push    rsi
0x1800ac52b  push    rdi
0x1800ac52c  push    r12
0x1800ac52e  push    r15
0x1800ac530  lea     rbp, [rsp-37h]
0x1800ac535  sub     rsp, 0D0h
0x1800ac53c  xor     esi, esi
0x1800ac53e  lea     r15, aWallpapertaskc_0; "WallpaperTaskCleanup_DeleteTask"
0x1800ac545  xor     eax, eax
0x1800ac547  mov     [rbp+57h+arg_8], rsi
0x1800ac54b  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800ac54f  lea     r9, aDeletingWsTask; "Deleting %ws task..."
0x1800ac556  xorps   xmm0, xmm0
0x1800ac559  mov     [rbp+57h+arg_0], rsi
0x1800ac55d  lea     rax, aPcawallpaperap_0; "PcaWallpaperAppDetect"
0x1800ac564  mov     [rbp+57h+arg_10], rsi
0x1800ac568  lea     r8d, [rsi+3Eh]
0x1800ac56c  mov     [rsp+0F0h+ppv], rax
0x1800ac571  lea     ecx, [rsi+3]
0x1800ac574  mov     rdx, r15
0x1800ac577  xor     edi, edi
0x1800ac579  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800ac57d  call    AslLogCallPrintf
0x1800ac582  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800ac586  call    cs:__imp_VariantInit
0x1800ac58c  lea     rax, [rbp+57h+arg_8]
0x1800ac590  xor     edx, edx; pUnkOuter
0x1800ac592  lea     r12d, [rsi+1]
0x1800ac596  mov     [rsp+0F0h+ppv], rax; ppv
0x1800ac59b  mov     r8d, r12d; dwClsContext
0x1800ac59e  lea     r9, IID_ITaskService; riid
0x1800ac5a5  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800ac5ac  call    cs:__imp_CoCreateInstance
0x1800ac5b2  mov     ebx, eax
0x1800ac5b4  test    eax, eax
0x1800ac5b6  jns     short loc_1800AC5D7
0x1800ac5b8  lea     r9, aFailedToCreate_6; "Failed to create a task scheduler [%x]"
0x1800ac5bf  lea     r8d, [rsi+49h]
0x1800ac5c3  mov     rdx, r15
0x1800ac5c6  mov     dword ptr [rsp+0F0h+ppv], eax
0x1800ac5ca  mov     ecx, r12d
0x1800ac5cd  call    AslLogCallPrintf
0x1800ac5d2  jmp     loc_1800AC75B
0x1800ac5d7  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x1800ac5db  lea     rdx, [rbp+57h+var_A0]
0x1800ac5df  mov     rcx, [rbp+57h+arg_8]
0x1800ac5e3  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x1800ac5e8  lea     r9, [rbp+57h+var_80]
0x1800ac5ec  mov     [rsp+0F0h+ppv], rdx
0x1800ac5f1  lea     r8, [rbp+57h+var_60]
0x1800ac5f5  lea     rdx, [rbp+57h+var_40]
0x1800ac5f9  movaps  [rbp+57h+var_A0], xmm1
0x1800ac5fd  mov     rax, [rcx]
0x1800ac600  movsd   [rbp+57h+var_90], xmm0
0x1800ac605  movaps  [rbp+57h+var_80], xmm1
0x1800ac609  movsd   [rbp+57h+var_70], xmm0
0x1800ac60e  mov     rax, [rax+50h]
0x1800ac612  movaps  [rbp+57h+var_60], xmm1
0x1800ac616  movsd   [rbp+57h+var_50], xmm0
0x1800ac61b  movaps  [rbp+57h+var_40], xmm1
0x1800ac61f  movsd   [rbp+57h+var_30], xmm0
0x1800ac624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac629  mov     ebx, eax
0x1800ac62b  test    eax, eax
0x1800ac62d  jns     short loc_1800AC63E
0x1800ac62f  lea     r9, aFailedToConnec; "Failed to connect to scheduler [%x]"
0x1800ac636  mov     r8d, 50h ; 'P'
0x1800ac63c  jmp     short loc_1800AC5C3
0x1800ac63e  lea     rcx, psz; "Microsoft\\Windows\\Application Experie"...
0x1800ac645  call    cs:__imp_SysAllocString
0x1800ac64b  mov     rsi, rax
0x1800ac64e  test    rax, rax
0x1800ac651  jnz     short loc_1800AC66B
0x1800ac653  lea     r9, aFailedToAlloca_6; "Failed to allocate task folder name"
0x1800ac65a  lea     r8d, [rax+58h]
0x1800ac65e  mov     ebx, 80070008h
0x1800ac663  mov     ecx, r12d
0x1800ac666  jmp     loc_1800AC753
0x1800ac66b  mov     rcx, [rbp+57h+arg_8]
0x1800ac66f  lea     r8, [rbp+57h+arg_0]
0x1800ac673  mov     rdx, rsi
0x1800ac676  mov     rax, [rcx]
0x1800ac679  mov     rax, [rax+38h]
0x1800ac67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac682  mov     ebx, eax
0x1800ac684  test    eax, eax
0x1800ac686  jns     short loc_1800AC69A
0x1800ac688  lea     r9, aFailedToGetSch; "Failed to get scheduler folder [%x]"
0x1800ac68f  mov     r8d, 5Fh ; '_'
0x1800ac695  jmp     loc_1800AC5C3
0x1800ac69a  lea     rcx, aPcawallpaperap_0; "PcaWallpaperAppDetect"
0x1800ac6a1  call    cs:__imp_SysAllocString
0x1800ac6a7  mov     rdi, rax
0x1800ac6aa  test    rax, rax
0x1800ac6ad  jnz     short loc_1800AC6BC
0x1800ac6af  lea     r9, aFailedToAlloca_17; "Failed to allocate task name"
0x1800ac6b6  lea     r8d, [rax+67h]
0x1800ac6ba  jmp     short loc_1800AC65E
0x1800ac6bc  mov     rcx, [rbp+57h+arg_0]
0x1800ac6c0  lea     r8, [rbp+57h+arg_10]
0x1800ac6c4  mov     rdx, rdi
0x1800ac6c7  mov     rax, [rcx]
0x1800ac6ca  mov     rax, [rax+68h]
0x1800ac6ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac6d3  test    eax, eax
0x1800ac6d5  jns     short loc_1800AC714
0x1800ac6d7  mov     rdx, r15
0x1800ac6da  cmp     eax, 80070002h
0x1800ac6df  jnz     short loc_1800AC6FB
0x1800ac6e1  mov     r8d, 70h ; 'p'
0x1800ac6e7  lea     r9, aTaskIsNotRegis; "Task is not registered."
0x1800ac6ee  lea     ecx, [r8-6Dh]
0x1800ac6f2  call    AslLogCallPrintf
0x1800ac6f7  xor     ebx, ebx
0x1800ac6f9  jmp     short loc_1800AC75B
0x1800ac6fb  lea     r9, aFailedToGetTas; "Failed to get task [%x]"
0x1800ac702  mov     dword ptr [rsp+0F0h+ppv], eax
0x1800ac706  mov     r8d, 76h ; 'v'
0x1800ac70c  mov     ecx, r12d
0x1800ac70f  call    AslLogCallPrintf
0x1800ac714  mov     rcx, [rbp+57h+arg_0]
0x1800ac718  xor     r8d, r8d
0x1800ac71b  mov     rdx, rdi
0x1800ac71e  mov     rax, [rcx]
0x1800ac721  mov     rax, [rax+78h]
0x1800ac725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac72a  mov     ebx, eax
0x1800ac72c  test    eax, eax
0x1800ac72e  jns     short loc_1800AC742
0x1800ac730  lea     r9, aFailedToDelete_7; "Failed to delete task [%x]"
0x1800ac737  mov     r8d, 7Dh ; '}'
0x1800ac73d  jmp     loc_1800AC5C3
0x1800ac742  mov     r8d, 81h
0x1800ac748  lea     r9, aTaskDeleted; "Task deleted."
0x1800ac74f  lea     ecx, [r8-7Eh]
0x1800ac753  mov     rdx, r15
0x1800ac756  call    AslLogCallPrintf
0x1800ac75b  mov     rcx, rsi; bstrString
0x1800ac75e  call    cs:__imp_SysFreeString
0x1800ac764  mov     rcx, rdi; bstrString
0x1800ac767  call    cs:__imp_SysFreeString
0x1800ac76d  mov     rcx, [rbp+57h+arg_10]
0x1800ac771  test    rcx, rcx
0x1800ac774  jz      short loc_1800AC782
0x1800ac776  mov     rax, [rcx]
0x1800ac779  mov     rax, [rax+10h]
0x1800ac77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac782  mov     rcx, [rbp+57h+arg_0]
0x1800ac786  test    rcx, rcx
0x1800ac789  jz      short loc_1800AC797
0x1800ac78b  mov     rax, [rcx]
0x1800ac78e  mov     rax, [rax+10h]
0x1800ac792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac797  mov     rcx, [rbp+57h+arg_8]
0x1800ac79b  test    rcx, rcx
0x1800ac79e  jz      short loc_1800AC7AC
0x1800ac7a0  mov     rax, [rcx]
0x1800ac7a3  mov     rax, [rax+10h]
0x1800ac7a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac7ac  test    ebx, ebx
0x1800ac7ae  js      short loc_1800AC7B4
0x1800ac7b0  xor     ebx, ebx
0x1800ac7b2  jmp     short loc_1800AC7C5
0x1800ac7b4  mov     eax, ebx
0x1800ac7b6  and     eax, 1FFF0000h
0x1800ac7bb  cmp     eax, 70000h
0x1800ac7c0  jnz     short loc_1800AC7C5
0x1800ac7c2  movzx   ebx, bx
0x1800ac7c5  mov     eax, ebx
0x1800ac7c7  mov     rbx, [rsp+0F0h+arg_18]
0x1800ac7cf  add     rsp, 0D0h
0x1800ac7d6  pop     r15
0x1800ac7d8  pop     r12
0x1800ac7da  pop     rdi
0x1800ac7db  pop     rsi
0x1800ac7dc  pop     rbp
0x1800ac7dd  retn
```
