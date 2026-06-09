# HandleOnlineDiskRequest(TASK_ONLINE_DISK_REQUEST const *)

- ea: `0x140018288`
- end: `0x140018325`
- name: `?HandleOnlineDiskRequest@@YAHPEBUTASK_ONLINE_DISK_REQUEST@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(const struct TASK_ONLINE_DISK_REQUEST *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140017d70`

## callees

- `0x140018110`
- `0x140018288`
- `0x14001832c`
- `0x140019c40`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140018301`
- `KERNEL32!HeapFree` at `0x140018301`
- `KERNEL32!GetProcessHeap` at `0x140018294`
- `KERNEL32!GetProcessHeap` at `0x140018294`
- `KERNEL32!SetLastError` at `0x1400182bf`
- `KERNEL32!SetLastError` at `0x140018314`
- `KERNEL32!SetLastError` at `0x1400182bf`
- `KERNEL32!SetLastError` at `0x140018314`
- `KERNEL32!GetLastError` at `0x1400182ec`
- `KERNEL32!GetLastError` at `0x1400182ec`

## pseudocode

```c
__int64 __fastcall HandleOnlineDiskRequest(const struct TASK_ONLINE_DISK_REQUEST *a1)
{
  unsigned __int16 *v2; // rdi
  HANDLE ProcessHeap; // rbp
  unsigned int v4; // ebx
  unsigned int DiskPath; // eax
  DWORD LastError; // esi
  BOOL v7; // eax
  unsigned __int16 *v9; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v9 = 0;
  v4 = IssueProgressStringResult(32882);
  if ( v4 )
  {
    if ( *(_QWORD *)a1 >= 8u )
    {
      DiskPath = HandleDiskRequest_GetDiskPath(*((_DWORD *)a1 + 4), ProcessHeap, &v9);
      v2 = v9;
      v4 = DiskPath;
      if ( DiskPath )
        v4 = BringDiskOnline(v9);
    }
    else
    {
      v4 = 0;
      SetLastError(0x18u);
    }
  }
  LastError = GetLastError();
  if ( v2 )
  {
    v7 = HeapFree(ProcessHeap, 0, v2);
    if ( v4 )
    {
      v4 = v7;
      LastError = 6;
    }
  }
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x140018288  push    rbx
0x14001828a  push    rbp
0x14001828b  push    rsi
0x14001828c  push    rdi
0x14001828d  sub     rsp, 28h
0x140018291  mov     rsi, rcx
0x140018294  call    cs:__imp_GetProcessHeap
0x14001829a  xor     edi, edi
0x14001829c  mov     ecx, 8072h
0x1400182a1  mov     rbp, rax
0x1400182a4  mov     [rsp+48h+arg_8], rdi
0x1400182a9  call    IssueProgressStringResult
0x1400182ae  mov     ebx, eax
0x1400182b0  test    eax, eax
0x1400182b2  jz      short loc_1400182EC
0x1400182b4  cmp     qword ptr [rsi], 8
0x1400182b8  jnb     short loc_1400182C7
0x1400182ba  xor     ebx, ebx
0x1400182bc  lea     ecx, [rdi+18h]; dwErrCode
0x1400182bf  call    cs:__imp_SetLastError
0x1400182c5  jmp     short loc_1400182EC
0x1400182c7  mov     ecx, [rsi+10h]; unsigned int
0x1400182ca  lea     r8, [rsp+48h+arg_8]; unsigned __int16 **
0x1400182cf  mov     rdx, rbp; hHeap
0x1400182d2  call    ?HandleDiskRequest_GetDiskPath@@YAHKPEAXPEAPEAG@Z; HandleDiskRequest_GetDiskPath(ulong,void *,ushort * *)
0x1400182d7  mov     rdi, [rsp+48h+arg_8]
0x1400182dc  mov     ebx, eax
0x1400182de  test    eax, eax
0x1400182e0  jz      short loc_1400182EC
0x1400182e2  mov     rcx, rdi; unsigned __int16 *
0x1400182e5  call    ?BringDiskOnline@@YAHPEBG@Z; BringDiskOnline(ushort const *)
0x1400182ea  mov     ebx, eax
0x1400182ec  call    cs:__imp_GetLastError
0x1400182f2  mov     esi, eax
0x1400182f4  test    rdi, rdi
0x1400182f7  jz      short loc_140018312
0x1400182f9  mov     r8, rdi; lpMem
0x1400182fc  xor     edx, edx; dwFlags
0x1400182fe  mov     rcx, rbp; hHeap
0x140018301  call    cs:__imp_HeapFree
0x140018307  test    ebx, ebx
0x140018309  jz      short loc_140018312
0x14001830b  mov     ebx, eax
0x14001830d  mov     esi, 6
0x140018312  mov     ecx, esi; dwErrCode
0x140018314  call    cs:__imp_SetLastError
0x14001831a  mov     eax, ebx
0x14001831c  add     rsp, 28h
0x140018320  pop     rdi
0x140018321  pop     rsi
0x140018322  pop     rbp
0x140018323  pop     rbx
0x140018324  retn
```
