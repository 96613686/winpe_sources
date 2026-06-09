# HandleResetDriveRequest(TASK_RESET_DRIVE_REQUEST const *)

- ea: `0x140019804`
- end: `0x14001988c`
- name: `?HandleResetDriveRequest@@YAHPEBUTASK_RESET_DRIVE_REQUEST@@@Z`
- size: `136`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140017d70`

## callees

- `0x14000e158`
- `0x14000f0c4`
- `0x140016900`
- `0x14001832c`
- `0x140019804`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140019879`
- `KERNEL32!LocalFree` at `0x140019879`
- `KERNEL32!SetLastError` at `0x140019835`
- `KERNEL32!SetLastError` at `0x140019835`

## pseudocode

```c
__int64 __fastcall HandleResetDriveRequest(const struct _GUID *a1)
{
  unsigned int DriveFiltered; // ebx
  unsigned int v3; // r8d
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  hMem = 0;
  DriveFiltered = IssueProgressStringResult(32901);
  if ( DriveFiltered )
  {
    if ( *(_QWORD *)&a1->Data1 == 48 )
    {
      DriveFiltered = SuGetDriveFiltered(0, (struct _GUID *)&a1[2], v3, (struct _SU_DRIVE_OBJECT **)&hMem);
      if ( DriveFiltered )
      {
        DriveFiltered = SuResetDrive((struct _SU_DRIVE_OBJECT *)hMem);
        if ( DriveFiltered )
          SuAutoRepairSpaces(a1 + 1);
      }
      if ( hMem )
        LocalFree(hMem);
    }
    else
    {
      DriveFiltered = 0;
      SetLastError(0x18u);
    }
  }
  return DriveFiltered;
}

```

## disassembly

```asm
0x140019804  mov     [rsp+arg_0], rbx
0x140019809  push    rsi
0x14001980a  sub     rsp, 20h
0x14001980e  mov     rsi, rcx
0x140019811  mov     [rsp+28h+hMem], 0
0x14001981a  mov     ecx, 8085h
0x14001981f  call    IssueProgressStringResult
0x140019824  mov     ebx, eax
0x140019826  test    eax, eax
0x140019828  jz      short loc_14001987F
0x14001982a  cmp     qword ptr [rsi], 30h ; '0'
0x14001982e  jz      short loc_14001983D
0x140019830  xor     ebx, ebx
0x140019832  lea     ecx, [rbx+18h]; dwErrCode
0x140019835  call    cs:__imp_SetLastError
0x14001983b  jmp     short loc_14001987F
0x14001983d  lea     rdx, [rsi+20h]; struct _GUID *
0x140019841  xor     ecx, ecx; struct _SU_POOL_OBJECT *
0x140019843  lea     r9, [rsp+28h+hMem]; struct _SU_DRIVE_OBJECT **
0x140019848  call    ?SuGetDriveFiltered@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@KPEAPEAU_SU_DRIVE_OBJECT@@@Z; SuGetDriveFiltered(_SU_POOL_OBJECT *,_GUID *,ulong,_SU_DRIVE_OBJECT * *)
0x14001984d  mov     ebx, eax
0x14001984f  test    eax, eax
0x140019851  jz      short loc_14001986C
0x140019853  mov     rcx, [rsp+28h+hMem]; struct _SU_DRIVE_OBJECT *
0x140019858  call    ?SuResetDrive@@YAHPEAU_SU_DRIVE_OBJECT@@@Z; SuResetDrive(_SU_DRIVE_OBJECT *)
0x14001985d  mov     ebx, eax
0x14001985f  test    eax, eax
0x140019861  jz      short loc_14001986C
0x140019863  lea     rcx, [rsi+10h]; struct _GUID *
0x140019867  call    ?SuAutoRepairSpaces@@YAXPEBU_GUID@@@Z; SuAutoRepairSpaces(_GUID const *)
0x14001986c  cmp     [rsp+28h+hMem], 0
0x140019872  jz      short loc_14001987F
0x140019874  mov     rcx, [rsp+28h+hMem]; hMem
0x140019879  call    cs:__imp_LocalFree
0x14001987f  mov     eax, ebx
0x140019881  mov     rbx, [rsp+28h+arg_0]
0x140019886  add     rsp, 20h
0x14001988a  pop     rsi
0x14001988b  retn
```
