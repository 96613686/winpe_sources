# HandleOfflineDiskRequest(TASK_OFFLINE_DISK_REQUEST const *)

- ea: `0x1400181e0`
- end: `0x140018280`
- name: `?HandleOfflineDiskRequest@@YAHPEBUTASK_OFFLINE_DISK_REQUEST@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(const struct TASK_OFFLINE_DISK_REQUEST *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140017d70`

## callees

- `0x140018110`
- `0x1400181e0`
- `0x14001832c`
- `0x14001bdac`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001825c`
- `KERNEL32!HeapFree` at `0x14001825c`
- `KERNEL32!GetProcessHeap` at `0x1400181ec`
- `KERNEL32!GetProcessHeap` at `0x1400181ec`
- `KERNEL32!SetLastError` at `0x140018217`
- `KERNEL32!SetLastError` at `0x14001826f`
- `KERNEL32!SetLastError` at `0x140018217`
- `KERNEL32!SetLastError` at `0x14001826f`
- `KERNEL32!GetLastError` at `0x140018247`
- `KERNEL32!GetLastError` at `0x140018247`

## pseudocode

```c
__int64 __fastcall HandleOfflineDiskRequest(const struct TASK_OFFLINE_DISK_REQUEST *a1)
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
  v4 = IssueProgressStringResult(32881);
  if ( v4 )
  {
    if ( *(_QWORD *)a1 >= 8u )
    {
      DiskPath = HandleDiskRequest_GetDiskPath(*((_DWORD *)a1 + 4), ProcessHeap, &v9);
      v2 = v9;
      v4 = DiskPath;
      if ( DiskPath )
        v4 = TakeDiskOffline(v9, *((_DWORD *)a1 + 5));
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
0x1400181e0  push    rbx
0x1400181e2  push    rbp
0x1400181e3  push    rsi
0x1400181e4  push    rdi
0x1400181e5  sub     rsp, 28h
0x1400181e9  mov     rsi, rcx
0x1400181ec  call    cs:__imp_GetProcessHeap
0x1400181f2  xor     edi, edi
0x1400181f4  mov     ecx, 8071h
0x1400181f9  mov     rbp, rax
0x1400181fc  mov     [rsp+48h+arg_8], rdi
0x140018201  call    IssueProgressStringResult
0x140018206  mov     ebx, eax
0x140018208  test    eax, eax
0x14001820a  jz      short loc_140018247
0x14001820c  cmp     qword ptr [rsi], 8
0x140018210  jnb     short loc_14001821F
0x140018212  xor     ebx, ebx
0x140018214  lea     ecx, [rdi+18h]; dwErrCode
0x140018217  call    cs:__imp_SetLastError
0x14001821d  jmp     short loc_140018247
0x14001821f  mov     ecx, [rsi+10h]; unsigned int
0x140018222  lea     r8, [rsp+48h+arg_8]; unsigned __int16 **
0x140018227  mov     rdx, rbp; hHeap
0x14001822a  call    ?HandleDiskRequest_GetDiskPath@@YAHKPEAXPEAPEAG@Z; HandleDiskRequest_GetDiskPath(ulong,void *,ushort * *)
0x14001822f  mov     rdi, [rsp+48h+arg_8]
0x140018234  mov     ebx, eax
0x140018236  test    eax, eax
0x140018238  jz      short loc_140018247
0x14001823a  mov     edx, [rsi+14h]; int
0x14001823d  mov     rcx, rdi; unsigned __int16 *
0x140018240  call    ?TakeDiskOffline@@YAHPEBGH@Z; TakeDiskOffline(ushort const *,int)
0x140018245  mov     ebx, eax
0x140018247  call    cs:__imp_GetLastError
0x14001824d  mov     esi, eax
0x14001824f  test    rdi, rdi
0x140018252  jz      short loc_14001826D
0x140018254  mov     r8, rdi; lpMem
0x140018257  xor     edx, edx; dwFlags
0x140018259  mov     rcx, rbp; hHeap
0x14001825c  call    cs:__imp_HeapFree
0x140018262  test    ebx, ebx
0x140018264  jz      short loc_14001826D
0x140018266  mov     ebx, eax
0x140018268  mov     esi, 6
0x14001826d  mov     ecx, esi; dwErrCode
0x14001826f  call    cs:__imp_SetLastError
0x140018275  mov     eax, ebx
0x140018277  add     rsp, 28h
0x14001827b  pop     rdi
0x14001827c  pop     rsi
0x14001827d  pop     rbp
0x14001827e  pop     rbx
0x14001827f  retn
```
