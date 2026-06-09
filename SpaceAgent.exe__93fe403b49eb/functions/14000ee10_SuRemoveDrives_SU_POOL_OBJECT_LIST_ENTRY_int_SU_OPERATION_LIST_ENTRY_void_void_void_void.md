# SuRemoveDrives(_SU_POOL_OBJECT *,_LIST_ENTRY *,int (*)(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *))

- ea: `0x14000ee10`
- end: `0x14000f0bc`
- name: `?SuRemoveDrives@@YAHPEAU_SU_POOL_OBJECT@@PEAU_LIST_ENTRY@@P6AHW4_SU_OPERATION@@1PEAX333@Z@Z`
- size: `684`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _LIST_ENTRY *, int (__high *)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *))`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140019498`

## callees

- `0x140004114`
- `0x14000c954`
- `0x14000ce60`
- `0x14000d1e8`
- `0x14000db40`
- `0x14000e860`
- `0x14000ee10`
- `0x14000f408`
- `0x14000f8fc`
- `0x14000fa50`
- `0x140012e84`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000f07e`
- `KERNEL32!LocalFree` at `0x14000f08c`
- `KERNEL32!LocalFree` at `0x14000f07e`
- `KERNEL32!LocalFree` at `0x14000f08c`
- `KERNEL32!SetLastError` at `0x14000ee73`
- `KERNEL32!SetLastError` at `0x14000f099`
- `KERNEL32!SetLastError` at `0x14000ee73`
- `KERNEL32!SetLastError` at `0x14000f099`
- `KERNEL32!GetLastError` at `0x14000efc8`
- `KERNEL32!GetLastError` at `0x14000efc8`
- `KERNEL32!QueryPerformanceCounter` at `0x14000ee61`
- `KERNEL32!QueryPerformanceCounter` at `0x14000efdd`
- `KERNEL32!QueryPerformanceCounter` at `0x14000ee61`
- `KERNEL32!QueryPerformanceCounter` at `0x14000efdd`

## string_xrefs

- `0x14000eea5`: `SiValidateRemoveDrives`
- `0x14000ef71`: `SiRemoveDrives`
- `0x14000f024`: `SuRemoveDrives`
- `0x14000f04f`: `SuRemoveDrives`

## pseudocode

```c
__int64 __fastcall SuRemoveDrives(
        struct _SU_POOL_OBJECT *a1,
        struct _LIST_ENTRY *a2,
        int (__high *a3)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *))
{
  DWORD LastError; // r15d
  struct _SP_IDS *v6; // r14
  struct _LIST_ENTRY *Flink; // rax
  unsigned int v8; // ebx
  const char *v9; // rsi
  struct _SP_IDS *v10; // rdx
  struct _LIST_ENTRY *i; // rsi
  struct _GUID *v12; // r12
  __int64 v13; // xmm0_8
  unsigned int SpaceIds; // eax
  struct _SP_IDS *v15; // rdx
  unsigned int v16; // ebx
  struct _LIST_ENTRY *j; // rax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  HLOCAL v21; // rdi
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-19h] BYREF
  LARGE_INTEGER v24; // [rsp+58h] [rbp-11h] BYREF
  __int64 v25; // [rsp+60h] [rbp-9h]
  struct _GUID v26[5]; // [rsp+68h] [rbp-1h] BYREF
  HLOCAL hMem; // [rsp+D0h] [rbp+67h] BYREF
  struct _SP_IDS *v28; // [rsp+E0h] [rbp+77h] BYREF

  LastError = 0;
  hMem = 0;
  memset(v26, 0, 32);
  v28 = 0;
  v6 = 0;
  SI_TIMER::SI_TIMER((SI_TIMER *)&PerformanceCount);
  QueryPerformanceCounter(&PerformanceCount);
  Flink = a2->Flink;
  if ( a2->Flink == a2 )
  {
    SetLastError(0x57u);
    v8 = 0;
    v9 = "Empty DriveListHead invalid";
LABEL_23:
    LastError = GetLastError();
    v12 = (struct _GUID *)((char *)a1 + 40);
    goto LABEL_25;
  }
  do
  {
    Flink[1].Flink = 0;
    Flink = Flink->Flink;
  }
  while ( Flink != a2 );
  v8 = SiValidateRemoveDrives(a1, a2);
  if ( !v8 )
  {
    v9 = "SiValidateRemoveDrives";
    goto LABEL_23;
  }
  for ( i = a2->Flink; i != a2; i = i->Flink )
  {
    if ( LODWORD(i[178].Blink) != 5 )
    {
      LODWORD(i[178].Blink) = 5;
      v8 = SuSetDrive((struct _SU_DRIVE_OBJECT *)i);
      if ( !v8 )
      {
        v9 = "SuSetDrive";
        goto LABEL_23;
      }
    }
  }
  v12 = (struct _GUID *)((char *)a1 + 40);
  v13 = *(_QWORD *)((char *)a1 + 44);
  v26[0].Data1 = *((_DWORD *)a1 + 10);
  *(_DWORD *)&v26[0].Data4[4] = *((_DWORD *)a1 + 13);
  *(_QWORD *)&v26[0].Data2 = v13;
  SuRebalanceMetadata(v26, v10);
  SpaceIds = SuGetSpaceIds((struct _GUID *)((char *)a1 + 40), &v28);
  v6 = v28;
  v8 = SpaceIds;
  if ( !SpaceIds )
  {
    v9 = "SuGetSpaceIds";
    goto LABEL_23;
  }
  v16 = 0;
  if ( *(_DWORD *)v28 )
  {
    do
    {
      v26[1] = *(struct _GUID *)((char *)v6 + 16 * v16 + 4);
      SuRebalanceMetadata(v26, v15);
      ++v16;
    }
    while ( v16 < *(_DWORD *)v6 );
  }
  v8 = SiRemoveDrives(a1, a2, 0);
  if ( !v8 )
  {
    v9 = "SiRemoveDrives";
    goto LABEL_23;
  }
  for ( j = a2->Flink; j != a2; j = j->Flink )
  {
    *(GUID *)&j[2].Blink = GUID_NULL;
    j[5] = (struct _LIST_ENTRY)GUID_NULL;
  }
  v8 = SiPerformParallelOperation(2, a2, 0, 0, 0);
  if ( !v8 )
  {
    v9 = "Callback - SuOperationUnprepareDrives";
    goto LABEL_23;
  }
  v9 = 0;
LABEL_25:
  QueryPerformanceCounter(&v24);
  SiIdsStringFromList(v12, a2, (unsigned __int16 **)&hMem);
  v21 = hMem;
  if ( v8 )
  {
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 2) != 0 )
      McTemplateK0zsjzx_EventWriteTransfer(
        v18,
        (unsigned int)RemoveDrivesSucceeded,
        v19,
        v20,
        (__int64)"SuRemoveDrives",
        (__int64)v12,
        (__int64)hMem,
        1000000 * (v24.QuadPart - PerformanceCount.QuadPart) / v25);
  }
  else if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    McTemplateK0zsjzsq_EventWriteTransfer(
      v18,
      (unsigned int)RemoveDrivesFailed,
      v19,
      v20,
      (__int64)"SuRemoveDrives",
      (__int64)v12,
      (__int64)hMem,
      (__int64)v9,
      LastError);
  }
  if ( v21 )
    LocalFree(v21);
  if ( v6 )
    LocalFree(v6);
  if ( !v8 )
    SetLastError(LastError);
  return v8;
}

```

## disassembly

```asm
0x14000ee10  mov     [rsp-8+arg_8], rbx
0x14000ee15  mov     [rsp-8+arg_10], r8
0x14000ee1a  push    rbp
0x14000ee1b  push    rsi
0x14000ee1c  push    rdi
0x14000ee1d  push    r12
0x14000ee1f  push    r13
0x14000ee21  push    r14
0x14000ee23  push    r15
0x14000ee25  lea     rbp, [rsp-27h]
0x14000ee2a  sub     rsp, 90h
0x14000ee31  xor     r15d, r15d
0x14000ee34  xorps   xmm0, xmm0
0x14000ee37  mov     r13, rcx
0x14000ee3a  mov     [rbp+57h+hMem], r15
0x14000ee3e  movups  xmmword ptr [rbp+57h+var_54], xmm0
0x14000ee42  lea     rcx, [rbp+57h+PerformanceCount]; this
0x14000ee46  mov     [rbp+57h+var_58], r15d
0x14000ee4a  movups  xmmword ptr [rbp+57h+var_54+0Ch], xmm0
0x14000ee4e  mov     rdi, rdx
0x14000ee51  mov     [rbp+57h+arg_10], r15
0x14000ee55  mov     r14d, r15d
0x14000ee58  call    ??0SI_TIMER@@QEAA@XZ; SI_TIMER::SI_TIMER(void)
0x14000ee5d  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x14000ee61  call    cs:__imp_QueryPerformanceCounter
0x14000ee67  mov     rax, [rdi]
0x14000ee6a  cmp     rax, rdi
0x14000ee6d  jnz     short loc_14000EE88
0x14000ee6f  lea     ecx, [r15+57h]; dwErrCode
0x14000ee73  call    cs:__imp_SetLastError
0x14000ee79  mov     ebx, r15d
0x14000ee7c  lea     rsi, aEmptyDrivelist; "Empty DriveListHead invalid"
0x14000ee83  jmp     loc_14000EFC8
0x14000ee88  mov     [rax+10h], r15
0x14000ee8c  mov     rax, [rax]
0x14000ee8f  cmp     rax, rdi
0x14000ee92  jnz     short loc_14000EE88
0x14000ee94  mov     rdx, rdi; struct _LIST_ENTRY *
0x14000ee97  mov     rcx, r13; struct _SU_POOL_OBJECT *
0x14000ee9a  call    ?SiValidateRemoveDrives@@YAHPEAU_SU_POOL_OBJECT@@PEAU_LIST_ENTRY@@@Z; SiValidateRemoveDrives(_SU_POOL_OBJECT *,_LIST_ENTRY *)
0x14000ee9f  mov     ebx, eax
0x14000eea1  test    eax, eax
0x14000eea3  jnz     short loc_14000EEB1
0x14000eea5  lea     rsi, aSivalidateremo; "SiValidateRemoveDrives"
0x14000eeac  jmp     loc_14000EFC8
0x14000eeb1  mov     rsi, [rdi]
0x14000eeb4  cmp     rsi, rdi
0x14000eeb7  jz      short loc_14000EEEB
0x14000eeb9  cmp     dword ptr [rsi+0B28h], 5
0x14000eec0  jz      short loc_14000EEDA
0x14000eec2  mov     rcx, rsi; struct _SU_DRIVE_OBJECT *
0x14000eec5  mov     dword ptr [rsi+0B28h], 5
0x14000eecf  call    ?SuSetDrive@@YAHPEAU_SU_DRIVE_OBJECT@@@Z; SuSetDrive(_SU_DRIVE_OBJECT *)
0x14000eed4  mov     ebx, eax
0x14000eed6  test    eax, eax
0x14000eed8  jz      short loc_14000EEDF
0x14000eeda  mov     rsi, [rsi]
0x14000eedd  jmp     short loc_14000EEB4
0x14000eedf  lea     rsi, aSusetdrive; "SuSetDrive"
0x14000eee6  jmp     loc_14000EFC8
0x14000eeeb  lea     r12, [r13+28h]
0x14000eeef  mov     eax, [r12]
0x14000eef3  lea     rcx, [rbp+57h+var_58]; struct _SP_ID *
0x14000eef7  movsd   xmm0, qword ptr [r12+4]
0x14000eefe  mov     [rbp+57h+var_58], eax
0x14000ef01  mov     eax, [r12+0Ch]
0x14000ef06  mov     dword ptr [rbp+57h+var_54+8], eax
0x14000ef09  movsd   qword ptr [rbp+57h+var_54], xmm0
0x14000ef0e  call    ?SuRebalanceMetadata@@YAHPEAU_SP_ID@@PEAU_SP_IDS@@@Z; SuRebalanceMetadata(_SP_ID *,_SP_IDS *)
0x14000ef13  lea     rdx, [rbp+57h+arg_10]; struct _SP_IDS **
0x14000ef17  mov     rcx, r12; struct _GUID *
0x14000ef1a  call    ?SuGetSpaceIds@@YAHPEAU_GUID@@PEAPEAU_SP_IDS@@@Z; SuGetSpaceIds(_GUID *,_SP_IDS * *)
0x14000ef1f  mov     r14, [rbp+57h+arg_10]
0x14000ef23  mov     ebx, eax
0x14000ef25  test    eax, eax
0x14000ef27  jnz     short loc_14000EF35
0x14000ef29  lea     rsi, aSugetspaceids; "SuGetSpaceIds"
0x14000ef30  jmp     loc_14000EFC8
0x14000ef35  mov     ebx, r15d
0x14000ef38  cmp     [r14], r15d
0x14000ef3b  jbe     short loc_14000EF5D
0x14000ef3d  mov     eax, ebx
0x14000ef3f  lea     rcx, [rbp+57h+var_58]; struct _SP_ID *
0x14000ef43  add     rax, rax
0x14000ef46  movups  xmm0, xmmword ptr [r14+rax*8+4]
0x14000ef4c  movdqu  xmmword ptr [rbp+57h+var_54+0Ch], xmm0
0x14000ef51  call    ?SuRebalanceMetadata@@YAHPEAU_SP_ID@@PEAU_SP_IDS@@@Z; SuRebalanceMetadata(_SP_ID *,_SP_IDS *)
0x14000ef56  inc     ebx
0x14000ef58  cmp     ebx, [r14]
0x14000ef5b  jb      short loc_14000EF3D
0x14000ef5d  xor     r8d, r8d; unsigned __int8
0x14000ef60  mov     rdx, rdi; struct _LIST_ENTRY *
0x14000ef63  mov     rcx, r13; struct _SU_POOL_OBJECT *
0x14000ef66  call    ?SiRemoveDrives@@YAHPEAU_SU_POOL_OBJECT@@PEAU_LIST_ENTRY@@E@Z; SiRemoveDrives(_SU_POOL_OBJECT *,_LIST_ENTRY *,uchar)
0x14000ef6b  mov     ebx, eax
0x14000ef6d  test    eax, eax
0x14000ef6f  jnz     short loc_14000EF7A
0x14000ef71  lea     rsi, aSiremovedrives; "SiRemoveDrives"
0x14000ef78  jmp     short loc_14000EFC8
0x14000ef7a  mov     rax, [rdi]
0x14000ef7d  jmp     short loc_14000EF9A
0x14000ef7f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000ef86  movdqu  xmmword ptr [rax+28h], xmm0
0x14000ef8b  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x14000ef92  movdqu  xmmword ptr [rax+50h], xmm1
0x14000ef97  mov     rax, [rax]
0x14000ef9a  cmp     rax, rdi
0x14000ef9d  jnz     short loc_14000EF7F
0x14000ef9f  xor     r9d, r9d
0x14000efa2  mov     [rsp+0C0h+var_98], r15
0x14000efa7  xor     r8d, r8d
0x14000efaa  mov     [rsp+0C0h+var_A0], r15
0x14000efaf  mov     rdx, rdi
0x14000efb2  lea     ecx, [r9+2]
0x14000efb6  call    ?SiPerformParallelOperation@@YAHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX222@Z; SiPerformParallelOperation(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *)
0x14000efbb  mov     ebx, eax
0x14000efbd  test    eax, eax
0x14000efbf  jnz     short loc_14000EFD7
0x14000efc1  lea     rsi, aCallbackSuoper_0; "Callback - SuOperationUnprepareDrives"
0x14000efc8  call    cs:__imp_GetLastError
0x14000efce  mov     r15d, eax
0x14000efd1  lea     r12, [r13+28h]
0x14000efd5  jmp     short loc_14000EFD9
0x14000efd7  xor     esi, esi
0x14000efd9  lea     rcx, [rbp+57h+var_68]; lpPerformanceCount
0x14000efdd  call    cs:__imp_QueryPerformanceCounter
0x14000efe3  lea     r8, [rbp+57h+hMem]; unsigned __int16 **
0x14000efe7  mov     rdx, rdi; struct _LIST_ENTRY *
0x14000efea  mov     rcx, r12; struct _GUID *
0x14000efed  call    ?SiIdsStringFromList@@YAHPEAU_GUID@@PEAU_LIST_ENTRY@@PEAPEAG@Z; SiIdsStringFromList(_GUID *,_LIST_ENTRY *,ushort * *)
0x14000eff2  mov     rdi, [rbp+57h+hMem]
0x14000eff6  test    ebx, ebx
0x14000eff8  jz      short loc_14000F041
0x14000effa  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 2
0x14000f001  jz      short loc_14000F076
0x14000f003  mov     rax, qword ptr [rbp+57h+var_68]
0x14000f007  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x14000f00b  imul    rax, 0F4240h
0x14000f012  cqo
0x14000f014  idiv    [rbp+57h+var_60]
0x14000f018  lea     rdx, RemoveDrivesSucceeded
0x14000f01f  mov     [rsp+0C0h+var_88], rax
0x14000f024  lea     rax, aSuremovedrives; "SuRemoveDrives"
0x14000f02b  mov     [rsp+0C0h+var_90], rdi
0x14000f030  mov     [rsp+0C0h+var_98], r12
0x14000f035  mov     [rsp+0C0h+var_A0], rax
0x14000f03a  call    McTemplateK0zsjzx_EventWriteTransfer
0x14000f03f  jmp     short loc_14000F076
0x14000f041  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x14000f048  jz      short loc_14000F076
0x14000f04a  mov     [rsp+0C0h+var_80], r15d
0x14000f04f  lea     rax, aSuremovedrives; "SuRemoveDrives"
0x14000f056  mov     [rsp+0C0h+var_88], rsi
0x14000f05b  lea     rdx, RemoveDrivesFailed
0x14000f062  mov     [rsp+0C0h+var_90], rdi
0x14000f067  mov     [rsp+0C0h+var_98], r12
0x14000f06c  mov     [rsp+0C0h+var_A0], rax
0x14000f071  call    McTemplateK0zsjzsq_EventWriteTransfer
0x14000f076  test    rdi, rdi
0x14000f079  jz      short loc_14000F084
0x14000f07b  mov     rcx, rdi; hMem
0x14000f07e  call    cs:__imp_LocalFree
0x14000f084  test    r14, r14
0x14000f087  jz      short loc_14000F092
0x14000f089  mov     rcx, r14; hMem
0x14000f08c  call    cs:__imp_LocalFree
0x14000f092  test    ebx, ebx
0x14000f094  jnz     short loc_14000F09F
0x14000f096  mov     ecx, r15d; dwErrCode
0x14000f099  call    cs:__imp_SetLastError
0x14000f09f  mov     eax, ebx
0x14000f0a1  mov     rbx, [rsp+0C0h+arg_8]
0x14000f0a9  add     rsp, 90h
0x14000f0b0  pop     r15
0x14000f0b2  pop     r14
0x14000f0b4  pop     r13
0x14000f0b6  pop     r12
0x14000f0b8  pop     rdi
0x14000f0b9  pop     rsi
0x14000f0ba  pop     rbp
0x14000f0bb  retn
```
