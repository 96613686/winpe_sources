# HandleRemoveDriveRequest(TASK_REMOVE_DRIVE_REQUEST const *)

- ea: `0x140019498`
- end: `0x1400196cf`
- name: `?HandleRemoveDriveRequest@@YAHPEBUTASK_REMOVE_DRIVE_REQUEST@@@Z`
- size: `567`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, loader_planting, service_task, installer_update`

## callers

- `0x140017d70`

## callees

- `0x140007de4`
- `0x1400083dc`
- `0x140008454`
- `0x14000a440`
- `0x14000e158`
- `0x14000ee10`
- `0x14000f408`
- `0x140016110`
- `0x140016900`
- `0x14001832c`
- `0x140019498`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400195bb`
- `KERNEL32!LocalFree` at `0x1400195ea`
- `KERNEL32!LocalFree` at `0x1400196a6`
- `KERNEL32!LocalFree` at `0x1400196b7`
- `KERNEL32!LocalFree` at `0x1400195bb`
- `KERNEL32!LocalFree` at `0x1400195ea`
- `KERNEL32!LocalFree` at `0x1400196a6`
- `KERNEL32!LocalFree` at `0x1400196b7`
- `KERNEL32!SleepEx` at `0x140019613`
- `KERNEL32!SleepEx` at `0x140019613`
- `KERNEL32!SetLastError` at `0x1400194f5`
- `KERNEL32!SetLastError` at `0x140019626`
- `KERNEL32!SetLastError` at `0x1400194f5`
- `KERNEL32!SetLastError` at `0x140019626`

## pseudocode

```c
__int64 __fastcall HandleRemoveDriveRequest(struct _GUID *a1)
{
  unsigned int Pool; // ebx
  const struct _GUID *v3; // r14
  unsigned int v4; // r8d
  int DriveFiltered; // eax
  char *v6; // rdi
  struct _SU_DRIVE_OBJECT *v7; // rcx
  int v8; // r15d
  int v9; // r12d
  unsigned int i; // ebx
  int v11; // r13d
  void *First; // r14
  HLOCAL v13; // rcx
  int (__high *v14)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *); // r8
  struct _LIST_ENTRY *Blink; // rax
  struct _SU_POOL_OBJECT *v16; // rcx
  int v17; // eax
  void *v19; // [rsp+20h] [rbp-30h]
  void *v20; // [rsp+28h] [rbp-28h]
  struct _LIST_ENTRY v21; // [rsp+40h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+48h] BYREF
  HLOCAL v23; // [rsp+A0h] [rbp+50h] BYREF
  HLOCAL v24; // [rsp+A8h] [rbp+58h] BYREF

  v24 = 0;
  v21.Blink = &v21;
  v23 = 0;
  v21.Flink = &v21;
  hMem = 0;
  Pool = IssueProgressStringResult(32898);
  if ( !Pool )
    return Pool;
  if ( *(_QWORD *)&a1->Data1 != 48 )
  {
    Pool = 0;
    SetLastError(0x18u);
    return Pool;
  }
  v3 = a1 + 1;
  Pool = SiGetPool(a1 + 1, 0, (struct _SU_POOL_OBJECT **)&v23);
  if ( Pool )
  {
    DriveFiltered = SuGetDriveFiltered((struct _SU_POOL_OBJECT *)v23, a1 + 2, v4, (struct _SU_DRIVE_OBJECT **)&v24);
    v6 = (char *)v24;
    Pool = DriveFiltered;
    if ( DriveFiltered )
    {
      if ( *((_DWORD *)v24 + 716) != 8 )
      {
        v8 = 0;
        goto LABEL_10;
      }
      v7 = (struct _SU_DRIVE_OBJECT *)v24;
      *((_DWORD *)v24 + 714) = 5;
      v8 = 1;
      Pool = SuSetDrive(v7);
      if ( Pool )
      {
LABEL_10:
        v9 = 0;
        SuAutoRepairSpaces(v3);
        for ( i = 0; i < 0xA; ++i )
        {
          v11 = 1;
          First = SiFindFirst(
                    (int (*)(void *, void *, void *, void *, struct _SP_IDS **))SiGetTaskIdsCallback,
                    (int (*)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **))SiGetTaskCallback,
                    v23,
                    &GUID_NULL,
                    v19,
                    v20,
                    (struct _SU_OBJECT **)&hMem);
          if ( First != (void *)-1LL )
          {
            while ( 1 )
            {
              v13 = hMem;
              if ( *((_DWORD *)hMem + 161) == 1 )
                break;
              LocalFree(hMem);
              hMem = 0;
              if ( !(unsigned int)SuFindNext(First, (struct _SU_OBJECT **)&hMem) )
              {
                v13 = hMem;
                goto LABEL_16;
              }
            }
            v9 = 1;
            v11 = 0;
LABEL_16:
            if ( v13 )
            {
              LocalFree(v13);
              hMem = 0;
            }
            SuFindClose(First);
          }
          if ( (v9 != 0 ? v11 : 0) != 0 )
            break;
          SleepEx(0x3E8u, 0);
        }
        SetLastError(0);
        Blink = v21.Blink;
        if ( v21.Blink->Flink != &v21 )
          __fastfail(3u);
        *((_QWORD *)v6 + 1) = v21.Blink;
        *(_QWORD *)v6 = &v21;
        v16 = (struct _SU_POOL_OBJECT *)v23;
        Blink->Flink = (struct _LIST_ENTRY *)v6;
        v21.Blink = (struct _LIST_ENTRY *)v6;
        Pool = SuRemoveDrives(v16, &v21, v14);
        if ( Pool && !v8 && !v6[2835] )
        {
          if ( (v17 = *((_DWORD *)v6 + 676), v17 != 7) && v17 != 4 || (Pool = IssueProgressStringResult(32899)) != 0 )
            Pool = SuNormalizeDrive((const struct _SP_DRIVE_INFO *)(v6 + 72));
        }
      }
    }
    if ( v6 )
      LocalFree(v6);
  }
  if ( v23 )
    LocalFree(v23);
  return Pool;
}

```

## disassembly

```asm
0x140019498  push    rbp
0x14001949a  push    rbx
0x14001949b  push    rdi
0x14001949c  push    r12
0x14001949e  push    r13
0x1400194a0  push    r14
0x1400194a2  push    r15
0x1400194a4  mov     rbp, rsp
0x1400194a7  sub     rsp, 50h
0x1400194ab  lea     rax, [rbp+var_10]
0x1400194af  mov     [rbp+arg_18], 0
0x1400194b7  mov     [rbp+var_10.Blink], rax
0x1400194bb  mov     rdi, rcx
0x1400194be  lea     rax, [rbp+var_10]
0x1400194c2  mov     [rbp+arg_10], 0
0x1400194ca  mov     ecx, 8082h
0x1400194cf  mov     [rbp+var_10.Flink], rax
0x1400194d3  mov     [rbp+hMem], 0
0x1400194db  call    IssueProgressStringResult
0x1400194e0  mov     ebx, eax
0x1400194e2  test    eax, eax
0x1400194e4  jz      loc_1400196BD
0x1400194ea  cmp     qword ptr [rdi], 30h ; '0'
0x1400194ee  jz      short loc_140019500
0x1400194f0  xor     ebx, ebx
0x1400194f2  lea     ecx, [rbx+18h]; dwErrCode
0x1400194f5  call    cs:__imp_SetLastError
0x1400194fb  jmp     loc_1400196BD
0x140019500  lea     r14, [rdi+10h]
0x140019504  xor     edx, edx; unsigned int
0x140019506  mov     rcx, r14; struct _GUID *
0x140019509  lea     r8, [rbp+arg_10]; struct _SU_POOL_OBJECT **
0x14001950d  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x140019512  mov     ebx, eax
0x140019514  test    eax, eax
0x140019516  jz      loc_1400196AC
0x14001951c  mov     rcx, [rbp+arg_10]; struct _SU_POOL_OBJECT *
0x140019520  lea     rdx, [rdi+20h]; struct _GUID *
0x140019524  lea     r9, [rbp+arg_18]; struct _SU_DRIVE_OBJECT **
0x140019528  call    ?SuGetDriveFiltered@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@KPEAPEAU_SU_DRIVE_OBJECT@@@Z; SuGetDriveFiltered(_SU_POOL_OBJECT *,_GUID *,ulong,_SU_DRIVE_OBJECT * *)
0x14001952d  mov     rdi, [rbp+arg_18]
0x140019531  mov     ebx, eax
0x140019533  test    eax, eax
0x140019535  jz      loc_14001969E
0x14001953b  cmp     dword ptr [rdi+0B30h], 8
0x140019542  jnz     short loc_140019568
0x140019544  mov     rcx, rdi; struct _SU_DRIVE_OBJECT *
0x140019547  mov     dword ptr [rdi+0B28h], 5
0x140019551  mov     r15d, 1
0x140019557  call    ?SuSetDrive@@YAHPEAU_SU_DRIVE_OBJECT@@@Z; SuSetDrive(_SU_DRIVE_OBJECT *)
0x14001955c  mov     ebx, eax
0x14001955e  test    eax, eax
0x140019560  jz      loc_14001969E
0x140019566  jmp     short loc_14001956B
0x140019568  xor     r15d, r15d
0x14001956b  mov     rcx, r14; struct _GUID *
0x14001956e  xor     r12d, r12d
0x140019571  call    ?SuAutoRepairSpaces@@YAXPEBU_GUID@@@Z; SuAutoRepairSpaces(_GUID const *)
0x140019576  xor     ebx, ebx
0x140019578  mov     r8, [rbp+arg_10]; void *
0x14001957c  lea     rax, [rbp+hMem]
0x140019580  lea     r9, GUID_NULL; void *
0x140019587  mov     [rsp+50h+var_20], rax; struct _SU_OBJECT **
0x14001958c  lea     rdx, ?SiGetTaskCallback@@YAHPEAX000PEAU_GUID@@PEAPEAU_SU_OBJECT@@@Z; int (*)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **)
0x140019593  mov     r13d, 1
0x140019599  lea     rcx, ?SiGetTaskIdsCallback@@YAHPEAX000PEAPEAU_SP_IDS@@@Z; int (*)(void *, void *, void *, void *, struct _SP_IDS **)
0x1400195a0  call    ?SiFindFirst@@YAPEAXP6AHPEAX000PEAPEAU_SP_IDS@@@ZP6AH0000PEAU_GUID@@PEAPEAU_SU_OBJECT@@@Z00004@Z; SiFindFirst(int (*)(void *,void *,void *,void *,_SP_IDS * *),int (*)(void *,void *,void *,void *,_GUID *,_SU_OBJECT * *),void *,void *,void *,void *,_SU_OBJECT * *)
0x1400195a5  mov     r14, rax
0x1400195a8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400195ac  jz      short loc_140019600
0x1400195ae  mov     rcx, [rbp+hMem]; hMem
0x1400195b2  cmp     [rcx+284h], r13d
0x1400195b9  jz      short loc_1400195DF
0x1400195bb  call    cs:__imp_LocalFree
0x1400195c1  lea     rdx, [rbp+hMem]; struct _SU_OBJECT **
0x1400195c5  mov     [rbp+hMem], 0
0x1400195cd  mov     rcx, r14; void *
0x1400195d0  call    ?SuFindNext@@YAHPEAXPEAPEAU_SU_OBJECT@@@Z; SuFindNext(void *,_SU_OBJECT * *)
0x1400195d5  test    eax, eax
0x1400195d7  jnz     short loc_1400195AE
0x1400195d9  mov     rcx, [rbp+hMem]
0x1400195dd  jmp     short loc_1400195E5
0x1400195df  mov     r12d, r13d
0x1400195e2  xor     r13d, r13d
0x1400195e5  test    rcx, rcx
0x1400195e8  jz      short loc_1400195F8
0x1400195ea  call    cs:__imp_LocalFree
0x1400195f0  mov     [rbp+hMem], 0
0x1400195f8  mov     rcx, r14; hMem
0x1400195fb  call    ?SuFindClose@@YAHPEAX@Z; SuFindClose(void *)
0x140019600  mov     eax, r12d
0x140019603  neg     eax
0x140019605  sbb     eax, eax
0x140019607  test    r13d, eax
0x14001960a  jnz     short loc_140019624
0x14001960c  xor     edx, edx; bAlertable
0x14001960e  mov     ecx, 3E8h; dwMilliseconds
0x140019613  call    cs:__imp_SleepEx
0x140019619  inc     ebx
0x14001961b  cmp     ebx, 0Ah
0x14001961e  jb      loc_140019578
0x140019624  xor     ecx, ecx; dwErrCode
0x140019626  call    cs:__imp_SetLastError
0x14001962c  mov     rax, [rbp+var_10.Blink]
0x140019630  lea     rcx, [rbp+var_10]
0x140019634  cmp     [rax], rcx
0x140019637  jz      short loc_140019640
0x140019639  mov     ecx, 3
0x14001963e  int     29h; Win8: RtlFailFast(ecx)
0x140019640  mov     [rdi+8], rax
0x140019644  lea     rcx, [rbp+var_10]
0x140019648  mov     [rdi], rcx
0x14001964b  lea     rdx, [rbp+var_10]; struct _LIST_ENTRY *
0x14001964f  mov     rcx, [rbp+arg_10]; struct _SU_POOL_OBJECT *
0x140019653  mov     [rax], rdi
0x140019656  mov     [rbp+var_10.Blink], rdi
0x14001965a  call    ?SuRemoveDrives@@YAHPEAU_SU_POOL_OBJECT@@PEAU_LIST_ENTRY@@P6AHW4_SU_OPERATION@@1PEAX333@Z@Z; SuRemoveDrives(_SU_POOL_OBJECT *,_LIST_ENTRY *,int (*)(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *))
0x14001965f  mov     ebx, eax
0x140019661  test    eax, eax
0x140019663  jz      short loc_14001969E
0x140019665  test    r15d, r15d
0x140019668  jnz     short loc_14001969E
0x14001966a  cmp     [rdi+0B13h], r15b
0x140019671  jnz     short loc_14001969E
0x140019673  mov     eax, [rdi+0A90h]
0x140019679  cmp     eax, 7
0x14001967c  jz      short loc_140019683
0x14001967e  cmp     eax, 4
0x140019681  jnz     short loc_140019693
0x140019683  mov     ecx, 8083h
0x140019688  call    IssueProgressStringResult
0x14001968d  mov     ebx, eax
0x14001968f  test    eax, eax
0x140019691  jz      short loc_14001969E
0x140019693  lea     rcx, [rdi+48h]; struct _SP_DRIVE_INFO *
0x140019697  call    ?SuNormalizeDrive@@YAHPEBU_SP_DRIVE_INFO@@@Z; SuNormalizeDrive(_SP_DRIVE_INFO const *)
0x14001969c  mov     ebx, eax
0x14001969e  test    rdi, rdi
0x1400196a1  jz      short loc_1400196AC
0x1400196a3  mov     rcx, rdi; hMem
0x1400196a6  call    cs:__imp_LocalFree
0x1400196ac  cmp     [rbp+arg_10], 0
0x1400196b1  jz      short loc_1400196BD
0x1400196b3  mov     rcx, [rbp+arg_10]; hMem
0x1400196b7  call    cs:__imp_LocalFree
0x1400196bd  mov     eax, ebx
0x1400196bf  add     rsp, 50h
0x1400196c3  pop     r15
0x1400196c5  pop     r14
0x1400196c7  pop     r13
0x1400196c9  pop     r12
0x1400196cb  pop     rdi
0x1400196cc  pop     rbx
0x1400196cd  pop     rbp
0x1400196ce  retn
```
