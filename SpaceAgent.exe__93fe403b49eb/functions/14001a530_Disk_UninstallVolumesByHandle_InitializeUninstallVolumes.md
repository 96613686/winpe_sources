# Disk_UninstallVolumesByHandle_InitializeUninstallVolumes

- ea: `0x14001a530`
- end: `0x14001a70b`
- name: `Disk_UninstallVolumesByHandle_InitializeUninstallVolumes`
- size: `475`
- prototype: `__int64 __fastcall(int, int, int, _DWORD *, void ***)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14001a2dc`

## callees

- `0x14001a530`
- `0x14001c1d8`
- `0x14001c238`
- `0x14001d640`
- `0x14001db30`
- `0x14001e464`

## import_xrefs

- `KERNEL32!HeapReAlloc` at `0x14001a64f`
- `KERNEL32!HeapReAlloc` at `0x14001a64f`
- `KERNEL32!HeapAlloc` at `0x14001a564`
- `KERNEL32!HeapAlloc` at `0x14001a5fa`
- `KERNEL32!HeapAlloc` at `0x14001a564`
- `KERNEL32!HeapAlloc` at `0x14001a5fa`
- `KERNEL32!HeapFree` at `0x14001a6a4`
- `KERNEL32!HeapFree` at `0x14001a6d7`
- `KERNEL32!HeapFree` at `0x14001a6a4`
- `KERNEL32!HeapFree` at `0x14001a6d7`
- `KERNEL32!GetProcessHeap` at `0x14001a54c`
- `KERNEL32!GetProcessHeap` at `0x14001a54c`
- `KERNEL32!SetLastError` at `0x14001a57b`
- `KERNEL32!SetLastError` at `0x14001a6f2`
- `KERNEL32!SetLastError` at `0x14001a57b`
- `KERNEL32!SetLastError` at `0x14001a6f2`
- `KERNEL32!GetLastError` at `0x14001a5db`
- `KERNEL32!GetLastError` at `0x14001a663`
- `KERNEL32!GetLastError` at `0x14001a673`
- `KERNEL32!GetLastError` at `0x14001a68f`
- `KERNEL32!GetLastError` at `0x14001a5db`
- `KERNEL32!GetLastError` at `0x14001a663`
- `KERNEL32!GetLastError` at `0x14001a673`
- `KERNEL32!GetLastError` at `0x14001a68f`

## pseudocode

```c
__int64 __fastcall Disk_UninstallVolumesByHandle_InitializeUninstallVolumes(
        int a1,
        int a2,
        int a3,
        _DWORD *a4,
        void ***a5)
{
  HANDLE ProcessHeap; // r12
  __int64 v9; // rdi
  void **v10; // rsi
  unsigned __int16 *v11; // r14
  __int64 FirstDevice; // r15
  unsigned int NextVolumePath; // ebx
  GUID *v14; // rcx
  __int64 v15; // rdx
  void **v16; // rax
  DWORD LastError; // ebp
  unsigned int DeviceClose; // eax
  BOOL v19; // eax
  void ***v20; // rax
  unsigned __int64 v22[11]; // [rsp+30h] [rbp-58h] BYREF
  int v23; // [rsp+A0h] [rbp+18h] BYREF

  v23 = a3;
  ProcessHeap = GetProcessHeap();
  v9 = 0;
  v10 = 0;
  v11 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x10000u);
  if ( !v11 )
  {
    FirstDevice = -1;
LABEL_3:
    NextVolumePath = 0;
    SetLastError(8u);
    goto LABEL_16;
  }
  v22[0] = 0x8000;
  v14 = &GUID_DEVINTERFACE_VOLUME;
  v23 = a1;
  if ( a2 )
    v14 = &GUID_DEVINTERFACE_HIDDEN_VOLUME;
  FirstDevice = (__int64)FindFirstDevice(
                           v14,
                           4u,
                           &v23,
                           (int (*)(void *, unsigned __int64 *, unsigned __int16 *))FindNextVolumePath,
                           v22,
                           v11);
  if ( FirstDevice == -1 )
  {
    if ( GetLastError() == 18 )
LABEL_15:
      NextVolumePath = 1;
    else
      NextVolumePath = 0;
  }
  else
  {
    v10 = (void **)HeapAlloc(ProcessHeap, 0, 8u);
    if ( !v10 )
      goto LABEL_3;
    while ( 1 )
    {
      NextVolumePath = InitializeUninstallVolume(v11, v15, &v10[v9]);
      if ( !NextVolumePath )
        break;
      v22[0] = 0x8000;
      v9 = (unsigned int)(v9 + 1);
      NextVolumePath = FindNextVolumePath((GUID *)FirstDevice, v22, v11);
      if ( !NextVolumePath )
      {
        if ( GetLastError() != 18 )
          break;
        goto LABEL_15;
      }
      v16 = (void **)HeapReAlloc(ProcessHeap, 0, v10, 8LL * (unsigned int)v9 + 8);
      if ( !v16 )
        goto LABEL_3;
      v10 = v16;
    }
  }
LABEL_16:
  LastError = GetLastError();
  if ( FirstDevice != -1 )
  {
    DeviceClose = FindDeviceClose((void *)FirstDevice);
    if ( NextVolumePath )
    {
      NextVolumePath = DeviceClose;
      LastError = GetLastError();
    }
  }
  if ( !v11 )
  {
LABEL_22:
    if ( NextVolumePath )
      goto LABEL_29;
    goto LABEL_25;
  }
  v19 = HeapFree(ProcessHeap, 0, v11);
  if ( NextVolumePath )
  {
    NextVolumePath = v19;
    LastError = 6;
    goto LABEL_22;
  }
LABEL_25:
  while ( (_DWORD)v9 )
  {
    LODWORD(v9) = v9 - 1;
    AbortUninstallVolume((LPVOID *)v10[(unsigned int)v9]);
  }
  if ( v10 )
    HeapFree(ProcessHeap, 0, v10);
  v10 = 0;
  LODWORD(v9) = 0;
LABEL_29:
  v20 = a5;
  *a4 = v9;
  *v20 = v10;
  SetLastError(LastError);
  return NextVolumePath;
}

```

## disassembly

```asm
0x14001a530  mov     [rsp+arg_10], r8d
0x14001a535  push    rbx
0x14001a536  push    rbp
0x14001a537  push    rsi
0x14001a538  push    rdi
0x14001a539  push    r12
0x14001a53b  push    r13
0x14001a53d  push    r14
0x14001a53f  push    r15
0x14001a541  sub     rsp, 48h
0x14001a545  mov     r13, r9
0x14001a548  mov     ebx, edx
0x14001a54a  mov     ebp, ecx
0x14001a54c  call    cs:__imp_GetProcessHeap
0x14001a552  xor     edx, edx; dwFlags
0x14001a554  mov     r8d, 10000h; dwBytes
0x14001a55a  mov     rcx, rax; hHeap
0x14001a55d  mov     r12, rax
0x14001a560  xor     edi, edi
0x14001a562  xor     esi, esi
0x14001a564  call    cs:__imp_HeapAlloc
0x14001a56a  mov     r14, rax
0x14001a56d  test    rax, rax
0x14001a570  jnz     short loc_14001A586
0x14001a572  or      r15, 0FFFFFFFFFFFFFFFFh
0x14001a576  xor     ebx, ebx
0x14001a578  lea     ecx, [rbx+8]; dwErrCode
0x14001a57b  call    cs:__imp_SetLastError
0x14001a581  jmp     loc_14001A673
0x14001a586  lea     rax, GUID_DEVINTERFACE_HIDDEN_VOLUME
0x14001a58d  mov     [rsp+88h+var_60], r14; unsigned __int16 *
0x14001a592  test    ebx, ebx
0x14001a594  mov     [rsp+88h+var_58], 8000h
0x14001a59d  lea     rcx, GUID_DEVINTERFACE_VOLUME
0x14001a5a4  mov     [rsp+88h+arg_10], ebp
0x14001a5ab  cmovnz  rcx, rax; ClassGuid
0x14001a5af  lea     r9, ?FindNextVolumePath@@YAHPEAXPEA_KPEAG@Z; int (*)(void *, unsigned __int64 *, unsigned __int16 *)
0x14001a5b6  lea     rax, [rsp+88h+var_58]
0x14001a5bb  mov     edx, 4; Size
0x14001a5c0  lea     r8, [rsp+88h+arg_10]; void *
0x14001a5c8  mov     [rsp+88h+var_68], rax; unsigned __int64 *
0x14001a5cd  call    ?FindFirstDevice@@YAPEAXPEBU_GUID@@_KPEAXP6AH2PEA_KPEAG@Z34@Z; FindFirstDevice(_GUID const *,unsigned __int64,void *,int (*)(void *,unsigned __int64 *,ushort *),unsigned __int64 *,ushort *)
0x14001a5d2  mov     r15, rax
0x14001a5d5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001a5d9  jnz     short loc_14001A5F1
0x14001a5db  call    cs:__imp_GetLastError
0x14001a5e1  cmp     eax, 12h
0x14001a5e4  jz      loc_14001A66E
0x14001a5ea  xor     ebx, ebx
0x14001a5ec  jmp     loc_14001A673
0x14001a5f1  xor     edx, edx; dwFlags
0x14001a5f3  mov     rcx, r12; hHeap
0x14001a5f6  lea     r8d, [rdx+8]; dwBytes
0x14001a5fa  call    cs:__imp_HeapAlloc
0x14001a600  mov     rsi, rax
0x14001a603  test    rax, rax
0x14001a606  jz      loc_14001A576
0x14001a60c  lea     r8, [rsi+rdi*8]; void **
0x14001a610  mov     rcx, r14; unsigned __int16 *
0x14001a613  call    ?InitializeUninstallVolume@@YAHPEBGHPEAPEAX@Z; InitializeUninstallVolume(ushort const *,int,void * *)
0x14001a618  mov     ebx, eax
0x14001a61a  test    eax, eax
0x14001a61c  jz      short loc_14001A673
0x14001a61e  mov     r8, r14; unsigned __int16 *
0x14001a621  mov     [rsp+88h+var_58], 8000h
0x14001a62a  lea     rdx, [rsp+88h+var_58]; unsigned __int64 *
0x14001a62f  mov     rcx, r15; InterfaceClassGuid
0x14001a632  inc     edi
0x14001a634  call    ?FindNextVolumePath@@YAHPEAXPEA_KPEAG@Z; FindNextVolumePath(void *,unsigned __int64 *,ushort *)
0x14001a639  mov     ebx, eax
0x14001a63b  test    eax, eax
0x14001a63d  jz      short loc_14001A663
0x14001a63f  lea     r9, ds:8[rdi*8]; dwBytes
0x14001a647  mov     r8, rsi; lpMem
0x14001a64a  xor     edx, edx; dwFlags
0x14001a64c  mov     rcx, r12; hHeap
0x14001a64f  call    cs:__imp_HeapReAlloc
0x14001a655  test    rax, rax
0x14001a658  jz      loc_14001A576
0x14001a65e  mov     rsi, rax
0x14001a661  jmp     short loc_14001A60C
0x14001a663  call    cs:__imp_GetLastError
0x14001a669  cmp     eax, 12h
0x14001a66c  jnz     short loc_14001A673
0x14001a66e  mov     ebx, 1
0x14001a673  call    cs:__imp_GetLastError
0x14001a679  mov     ebp, eax
0x14001a67b  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x14001a67f  jz      short loc_14001A697
0x14001a681  mov     rcx, r15; lpMem
0x14001a684  call    ?FindDeviceClose@@YAHPEAX@Z; FindDeviceClose(void *)
0x14001a689  test    ebx, ebx
0x14001a68b  jz      short loc_14001A697
0x14001a68d  mov     ebx, eax
0x14001a68f  call    cs:__imp_GetLastError
0x14001a695  mov     ebp, eax
0x14001a697  test    r14, r14
0x14001a69a  jz      short loc_14001A6B5
0x14001a69c  mov     r8, r14; lpMem
0x14001a69f  xor     edx, edx; dwFlags
0x14001a6a1  mov     rcx, r12; hHeap
0x14001a6a4  call    cs:__imp_HeapFree
0x14001a6aa  test    ebx, ebx
0x14001a6ac  jz      short loc_14001A6C6
0x14001a6ae  mov     ebx, eax
0x14001a6b0  mov     ebp, 6
0x14001a6b5  test    ebx, ebx
0x14001a6b7  jnz     short loc_14001A6E1
0x14001a6b9  jmp     short loc_14001A6C6
0x14001a6bb  dec     edi
0x14001a6bd  mov     rcx, [rsi+rdi*8]; lpMem
0x14001a6c1  call    ?AbortUninstallVolume@@YAHPEAX@Z; AbortUninstallVolume(void *)
0x14001a6c6  test    edi, edi
0x14001a6c8  jnz     short loc_14001A6BB
0x14001a6ca  test    rsi, rsi
0x14001a6cd  jz      short loc_14001A6DD
0x14001a6cf  mov     r8, rsi; lpMem
0x14001a6d2  xor     edx, edx; dwFlags
0x14001a6d4  mov     rcx, r12; hHeap
0x14001a6d7  call    cs:__imp_HeapFree
0x14001a6dd  xor     esi, esi
0x14001a6df  xor     edi, edi
0x14001a6e1  mov     rax, [rsp+88h+arg_20]
0x14001a6e9  mov     ecx, ebp; dwErrCode
0x14001a6eb  mov     [r13+0], edi
0x14001a6ef  mov     [rax], rsi
0x14001a6f2  call    cs:__imp_SetLastError
0x14001a6f8  mov     eax, ebx
0x14001a6fa  add     rsp, 48h
0x14001a6fe  pop     r15
0x14001a700  pop     r14
0x14001a702  pop     r13
0x14001a704  pop     r12
0x14001a706  pop     rdi
0x14001a707  pop     rsi
0x14001a708  pop     rbp
0x14001a709  pop     rbx
0x14001a70a  retn
```
