# HandleRenameDriveRequest(TASK_RENAME_DRIVE_REQUEST const *)

- ea: `0x1400196d8`
- end: `0x1400197fc`
- name: `?HandleRenameDriveRequest@@YAHPEBUTASK_RENAME_DRIVE_REQUEST@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(const struct TASK_RENAME_DRIVE_REQUEST *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x140017d70`

## callees

- `0x140001caf`
- `0x140008190`
- `0x14000e158`
- `0x14000f408`
- `0x14001832c`
- `0x1400196d8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400197c1`
- `KERNEL32!LocalFree` at `0x1400197c1`
- `KERNEL32!SetLastError` at `0x14001972b`
- `KERNEL32!SetLastError` at `0x1400197df`
- `KERNEL32!SetLastError` at `0x14001972b`
- `KERNEL32!SetLastError` at `0x1400197df`
- `KERNEL32!GetLastError` at `0x1400197b1`
- `KERNEL32!GetLastError` at `0x1400197d5`
- `KERNEL32!GetLastError` at `0x1400197b1`
- `KERNEL32!GetLastError` at `0x1400197d5`

## pseudocode

```c
__int64 __fastcall HandleRenameDriveRequest(const struct TASK_RENAME_DRIVE_REQUEST *a1)
{
  struct _SU_DRIVE_OBJECT *v2; // rdi
  unsigned int v3; // ebx
  unsigned int v4; // r8d
  DWORD v5; // ecx
  int DriveFiltered; // eax
  unsigned __int16 *v7; // rcx
  DWORD LastError; // esi
  HLOCAL v9; // rax
  _BYTE v11[40]; // [rsp+20h] [rbp-B58h] BYREF
  __int128 v12; // [rsp+48h] [rbp-B30h]
  struct _SU_DRIVE_OBJECT *v13; // [rsp+B80h] [rbp+8h] BYREF

  memset_0(v11, 0, 0xB48u);
  v2 = 0;
  v13 = 0;
  v3 = IssueProgressStringResult(32900);
  if ( v3 )
  {
    if ( *(_QWORD *)a1 == 560 )
    {
      v12 = *((_OWORD *)a1 + 1);
      DriveFiltered = SuGetDriveFiltered((struct _SU_POOL_OBJECT *)v11, (struct _GUID *)a1 + 2, v4, &v13);
      v2 = v13;
      v3 = DriveFiltered;
      if ( !DriveFiltered )
        goto LABEL_11;
      v7 = (unsigned __int16 *)((char *)v13 + 120);
      *((_WORD *)a1 + 279) = 0;
      v5 = StringCchCopyW(v7, 0x100u, (const unsigned __int16 *)a1 + 24);
      if ( (int)(v5 + 0x80000000) < 0 || v5 == -2147024774 )
      {
        v3 = SuSetDrive(v2);
        goto LABEL_11;
      }
      v3 = 0;
      if ( (v5 & 0x1FFF0000) == 0x70000 )
        v5 = (unsigned __int16)v5;
    }
    else
    {
      v3 = 0;
      v5 = 24;
    }
    SetLastError(v5);
  }
LABEL_11:
  LastError = GetLastError();
  if ( v2 )
  {
    v9 = LocalFree(v2);
    if ( v3 )
    {
      v3 = v9 == 0;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x1400196d8  mov     [rsp+arg_8], rbx
0x1400196dd  mov     [rsp+arg_10], rsi
0x1400196e2  push    rdi
0x1400196e3  sub     rsp, 0B70h
0x1400196ea  mov     rsi, rcx
0x1400196ed  xor     edx, edx; Val
0x1400196ef  lea     rcx, [rsp+0B78h+var_B58]; void *
0x1400196f4  mov     r8d, 0B48h; Size
0x1400196fa  call    memset_0
0x1400196ff  xor     edi, edi
0x140019701  mov     ecx, 8084h
0x140019706  mov     [rsp+0B78h+arg_0], rdi
0x14001970e  call    IssueProgressStringResult
0x140019713  mov     ebx, eax
0x140019715  test    eax, eax
0x140019717  jz      loc_1400197B1
0x14001971d  cmp     qword ptr [rsi], 230h
0x140019724  jz      short loc_140019733
0x140019726  xor     ebx, ebx
0x140019728  lea     ecx, [rdi+18h]; dwErrCode
0x14001972b  call    cs:__imp_SetLastError
0x140019731  jmp     short loc_1400197B1
0x140019733  movups  xmm0, xmmword ptr [rsi+10h]
0x140019737  lea     rdx, [rsi+20h]; struct _GUID *
0x14001973b  lea     r9, [rsp+0B78h+arg_0]; struct _SU_DRIVE_OBJECT **
0x140019743  lea     rcx, [rsp+0B78h+var_B58]; struct _SU_POOL_OBJECT *
0x140019748  movdqu  [rsp+0B78h+var_B30], xmm0
0x14001974e  call    ?SuGetDriveFiltered@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@KPEAPEAU_SU_DRIVE_OBJECT@@@Z; SuGetDriveFiltered(_SU_POOL_OBJECT *,_GUID *,ulong,_SU_DRIVE_OBJECT * *)
0x140019753  mov     rdi, [rsp+0B78h+arg_0]
0x14001975b  mov     ebx, eax
0x14001975d  test    eax, eax
0x14001975f  jz      short loc_1400197B1
0x140019761  lea     r8, [rsi+30h]; unsigned __int16 *
0x140019765  xor     eax, eax
0x140019767  lea     rcx, [rdi+78h]; unsigned __int16 *
0x14001976b  mov     [r8+1FEh], ax
0x140019773  mov     edx, 100h; unsigned __int64
0x140019778  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001977d  mov     edx, 80000000h
0x140019782  mov     ecx, eax
0x140019784  add     eax, edx
0x140019786  test    edx, eax
0x140019788  jnz     short loc_1400197A7
0x14001978a  cmp     ecx, 8007007Ah
0x140019790  jz      short loc_1400197A7
0x140019792  mov     eax, ecx
0x140019794  xor     ebx, ebx
0x140019796  and     eax, 1FFF0000h
0x14001979b  cmp     eax, 70000h
0x1400197a0  jnz     short loc_14001972B
0x1400197a2  movzx   ecx, cx
0x1400197a5  jmp     short loc_14001972B
0x1400197a7  mov     rcx, rdi; struct _SU_DRIVE_OBJECT *
0x1400197aa  call    ?SuSetDrive@@YAHPEAU_SU_DRIVE_OBJECT@@@Z; SuSetDrive(_SU_DRIVE_OBJECT *)
0x1400197af  mov     ebx, eax
0x1400197b1  call    cs:__imp_GetLastError
0x1400197b7  mov     esi, eax
0x1400197b9  test    rdi, rdi
0x1400197bc  jz      short loc_1400197DD
0x1400197be  mov     rcx, rdi; hMem
0x1400197c1  call    cs:__imp_LocalFree
0x1400197c7  xor     ecx, ecx
0x1400197c9  test    rax, rax
0x1400197cc  setz    cl
0x1400197cf  test    ebx, ebx
0x1400197d1  jz      short loc_1400197DD
0x1400197d3  mov     ebx, ecx
0x1400197d5  call    cs:__imp_GetLastError
0x1400197db  mov     esi, eax
0x1400197dd  mov     ecx, esi; dwErrCode
0x1400197df  call    cs:__imp_SetLastError
0x1400197e5  lea     r11, [rsp+0B78h+var_8]
0x1400197ed  mov     eax, ebx
0x1400197ef  mov     rbx, [r11+18h]
0x1400197f3  mov     rsi, [r11+20h]
0x1400197f7  mov     rsp, r11
0x1400197fa  pop     rdi
0x1400197fb  retn
```
