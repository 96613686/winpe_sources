# HandleEvacuateDriveRequest(TASK_EVACUATE_DRIVE_REQUEST const *)

- ea: `0x140019310`
- end: `0x14001948f`
- name: `?HandleEvacuateDriveRequest@@YAHPEBUTASK_EVACUATE_DRIVE_REQUEST@@@Z`
- size: `383`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x140017d70`

## callees

- `0x14000a440`
- `0x14000d1e8`
- `0x14000db40`
- `0x14000e158`
- `0x14000f408`
- `0x140016900`
- `0x14001832c`
- `0x140019310`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14001941c`
- `KERNEL32!LocalFree` at `0x140019465`
- `KERNEL32!LocalFree` at `0x14001946e`
- `KERNEL32!LocalFree` at `0x140019476`
- `KERNEL32!LocalFree` at `0x14001941c`
- `KERNEL32!LocalFree` at `0x140019465`
- `KERNEL32!LocalFree` at `0x14001946e`
- `KERNEL32!LocalFree` at `0x140019476`
- `KERNEL32!SleepEx` at `0x14001944d`
- `KERNEL32!SleepEx` at `0x14001944d`
- `KERNEL32!SetLastError` at `0x140019361`
- `KERNEL32!SetLastError` at `0x140019361`

## pseudocode

```c
__int64 __fastcall HandleEvacuateDriveRequest(struct _GUID *a1)
{
  struct _SU_POOL_OBJECT *v2; // rsi
  struct _LIST_ENTRY *v3; // rdi
  unsigned int DriveFiltered; // ebx
  DWORD v5; // ecx
  const struct _GUID *v6; // r15
  unsigned int Pool; // eax
  unsigned int v8; // r8d
  struct _LIST_ENTRY *Blink; // rax
  int v10; // eax
  struct _SU_POOL_OBJECT *v11; // r14
  int v12; // ebx
  struct _LIST_ENTRY v14; // [rsp+20h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+38h] BYREF
  struct _SU_POOL_OBJECT *v16; // [rsp+70h] [rbp+40h] BYREF

  v14.Blink = &v14;
  v2 = 0;
  v16 = 0;
  v3 = 0;
  v14.Flink = &v14;
  hMem = 0;
  DriveFiltered = IssueProgressStringResult(32903);
  if ( DriveFiltered )
  {
    if ( *(_QWORD *)&a1->Data1 != 48 )
    {
      DriveFiltered = 0;
      v5 = 24;
LABEL_4:
      SetLastError(v5);
      goto LABEL_19;
    }
    v6 = a1 + 1;
    Pool = SiGetPool(a1 + 1, 0, &v16);
    v2 = v16;
    DriveFiltered = Pool;
    if ( Pool )
    {
      DriveFiltered = SuGetDriveFiltered(v16, a1 + 2, v8, (struct _SU_DRIVE_OBJECT **)&hMem);
      if ( !DriveFiltered )
      {
        v3 = (struct _LIST_ENTRY *)hMem;
        goto LABEL_19;
      }
      Blink = v14.Blink;
      if ( v14.Blink->Flink != &v14 )
        __fastfail(3u);
      v3 = (struct _LIST_ENTRY *)hMem;
      hMem = 0;
      v3->Flink = &v14;
      v3->Blink = Blink;
      Blink->Flink = v3;
      v14.Blink = v3;
      v10 = SiGetPool((struct _GUID *)((char *)v2 + 40), 0, (struct _SU_POOL_OBJECT **)&hMem);
      v11 = (struct _SU_POOL_OBJECT *)hMem;
      v12 = v10;
      if ( v10 )
      {
        v12 = SiValidateRemoveDrives((struct _SU_POOL_OBJECT *)hMem, &v14);
        if ( v12 )
          v12 = SiRemoveDrives(v11, &v14, 1u);
      }
      if ( v11 )
        LocalFree(v11);
      if ( !v12 )
      {
        DriveFiltered = 0;
        goto LABEL_19;
      }
      LODWORD(v3[178].Blink) = 5;
      DriveFiltered = SuSetDrive((struct _SU_DRIVE_OBJECT *)v3);
      if ( DriveFiltered )
      {
        SuAutoRepairSpaces(v6);
        SleepEx(0x3E8u, 0);
        v5 = 0;
        goto LABEL_4;
      }
    }
  }
LABEL_19:
  LocalFree(v3);
  LocalFree(v2);
  LocalFree(0);
  return DriveFiltered;
}

```

## disassembly

```asm
0x140019310  mov     [rsp-28h+arg_0], rbx
0x140019315  push    rbp
0x140019316  push    rsi
0x140019317  push    rdi
0x140019318  push    r14
0x14001931a  push    r15
0x14001931c  mov     rbp, rsp
0x14001931f  sub     rsp, 30h
0x140019323  lea     rax, [rbp+var_10]
0x140019327  mov     r14, rcx
0x14001932a  mov     [rbp+var_10.Blink], rax
0x14001932e  xor     esi, esi
0x140019330  lea     rax, [rbp+var_10]
0x140019334  mov     [rbp+arg_10], rsi
0x140019338  xor     edi, edi
0x14001933a  mov     [rbp+var_10.Flink], rax
0x14001933e  mov     ecx, 8087h
0x140019343  mov     [rbp+hMem], rdi
0x140019347  call    IssueProgressStringResult
0x14001934c  mov     ebx, eax
0x14001934e  test    eax, eax
0x140019350  jz      loc_140019462
0x140019356  cmp     qword ptr [r14], 30h ; '0'
0x14001935a  jz      short loc_14001936C
0x14001935c  xor     ebx, ebx
0x14001935e  lea     ecx, [rsi+18h]; dwErrCode
0x140019361  call    cs:__imp_SetLastError
0x140019367  jmp     loc_140019462
0x14001936c  lea     r15, [r14+10h]
0x140019370  xor     edx, edx; unsigned int
0x140019372  mov     rcx, r15; struct _GUID *
0x140019375  lea     r8, [rbp+arg_10]; struct _SU_POOL_OBJECT **
0x140019379  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x14001937e  mov     rsi, [rbp+arg_10]
0x140019382  mov     ebx, eax
0x140019384  test    eax, eax
0x140019386  jz      loc_140019462
0x14001938c  lea     rdx, [r14+20h]; struct _GUID *
0x140019390  mov     rcx, rsi; struct _SU_POOL_OBJECT *
0x140019393  lea     r9, [rbp+hMem]; struct _SU_DRIVE_OBJECT **
0x140019397  call    ?SuGetDriveFiltered@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@KPEAPEAU_SU_DRIVE_OBJECT@@@Z; SuGetDriveFiltered(_SU_POOL_OBJECT *,_GUID *,ulong,_SU_DRIVE_OBJECT * *)
0x14001939c  mov     ebx, eax
0x14001939e  test    eax, eax
0x1400193a0  jz      loc_14001945E
0x1400193a6  mov     rax, [rbp+var_10.Blink]
0x1400193aa  lea     rcx, [rbp+var_10]
0x1400193ae  cmp     [rax], rcx
0x1400193b1  jz      short loc_1400193BA
0x1400193b3  mov     ecx, 3
0x1400193b8  int     29h; Win8: RtlFailFast(ecx)
0x1400193ba  mov     rdi, [rbp+hMem]
0x1400193be  lea     rcx, [rbp+var_10]
0x1400193c2  lea     r8, [rbp+hMem]; struct _SU_POOL_OBJECT **
0x1400193c6  mov     [rbp+hMem], 0
0x1400193ce  xor     edx, edx; unsigned int
0x1400193d0  mov     [rdi], rcx
0x1400193d3  lea     rcx, [rsi+28h]; struct _GUID *
0x1400193d7  mov     [rdi+8], rax
0x1400193db  mov     [rax], rdi
0x1400193de  mov     [rbp+var_10.Blink], rdi
0x1400193e2  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x1400193e7  mov     r14, [rbp+hMem]
0x1400193eb  mov     ebx, eax
0x1400193ed  test    eax, eax
0x1400193ef  jz      short loc_140019414
0x1400193f1  lea     rdx, [rbp+var_10]; struct _LIST_ENTRY *
0x1400193f5  mov     rcx, r14; struct _SU_POOL_OBJECT *
0x1400193f8  call    ?SiValidateRemoveDrives@@YAHPEAU_SU_POOL_OBJECT@@PEAU_LIST_ENTRY@@@Z; SiValidateRemoveDrives(_SU_POOL_OBJECT *,_LIST_ENTRY *)
0x1400193fd  mov     ebx, eax
0x1400193ff  test    eax, eax
0x140019401  jz      short loc_140019414
0x140019403  mov     r8b, 1; unsigned __int8
0x140019406  lea     rdx, [rbp+var_10]; struct _LIST_ENTRY *
0x14001940a  mov     rcx, r14; struct _SU_POOL_OBJECT *
0x14001940d  call    ?SiRemoveDrives@@YAHPEAU_SU_POOL_OBJECT@@PEAU_LIST_ENTRY@@E@Z; SiRemoveDrives(_SU_POOL_OBJECT *,_LIST_ENTRY *,uchar)
0x140019412  mov     ebx, eax
0x140019414  test    r14, r14
0x140019417  jz      short loc_140019422
0x140019419  mov     rcx, r14; hMem
0x14001941c  call    cs:__imp_LocalFree
0x140019422  test    ebx, ebx
0x140019424  jz      short loc_14001945A
0x140019426  mov     rcx, rdi; struct _SU_DRIVE_OBJECT *
0x140019429  mov     dword ptr [rdi+0B28h], 5
0x140019433  call    ?SuSetDrive@@YAHPEAU_SU_DRIVE_OBJECT@@@Z; SuSetDrive(_SU_DRIVE_OBJECT *)
0x140019438  mov     ebx, eax
0x14001943a  test    eax, eax
0x14001943c  jz      short loc_140019462
0x14001943e  mov     rcx, r15; struct _GUID *
0x140019441  call    ?SuAutoRepairSpaces@@YAXPEBU_GUID@@@Z; SuAutoRepairSpaces(_GUID const *)
0x140019446  xor     edx, edx; bAlertable
0x140019448  mov     ecx, 3E8h; dwMilliseconds
0x14001944d  call    cs:__imp_SleepEx
0x140019453  xor     ecx, ecx
0x140019455  jmp     loc_140019361
0x14001945a  xor     ebx, ebx
0x14001945c  jmp     short loc_140019462
0x14001945e  mov     rdi, [rbp+hMem]
0x140019462  mov     rcx, rdi; hMem
0x140019465  call    cs:__imp_LocalFree
0x14001946b  mov     rcx, rsi; hMem
0x14001946e  call    cs:__imp_LocalFree
0x140019474  xor     ecx, ecx; hMem
0x140019476  call    cs:__imp_LocalFree
0x14001947c  mov     eax, ebx
0x14001947e  mov     rbx, [rsp+30h+arg_0]
0x140019483  add     rsp, 30h
0x140019487  pop     r15
0x140019489  pop     r14
0x14001948b  pop     rdi
0x14001948c  pop     rsi
0x14001948d  pop     rbp
0x14001948e  retn
```
