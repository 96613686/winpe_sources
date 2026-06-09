# CActiveXInstallBroker::DuplicateProcessInformation(_PROCESS_INFORMATION *,_PROCESS_INFORMATION *)

- ea: `0x4030f5`
- end: `0x4031f7`
- name: `?DuplicateProcessInformation@CActiveXInstallBroker@@AAEJPAU_PROCESS_INFORMATION@@0@Z`
- size: `258`
- prototype: `int __thiscall(CActiveXInstallBroker *__hidden this, struct _PROCESS_INFORMATION *, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x404214`

## callees

- `0x4030f5`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x4031c4`
- `KERNEL32!CloseHandle` at `0x4031d3`
- `KERNEL32!CloseHandle` at `0x4031de`
- `KERNEL32!CloseHandle` at `0x4031c4`
- `KERNEL32!CloseHandle` at `0x4031d3`
- `KERNEL32!CloseHandle` at `0x4031de`
- `KERNEL32!GetCurrentProcess` at `0x403107`
- `KERNEL32!GetCurrentProcess` at `0x403107`
- `KERNEL32!OpenProcess` at `0x40313b`
- `KERNEL32!OpenProcess` at `0x40313b`
- `KERNEL32!DuplicateHandle` at `0x40315d`
- `KERNEL32!DuplicateHandle` at `0x40317e`
- `KERNEL32!DuplicateHandle` at `0x40315d`
- `KERNEL32!DuplicateHandle` at `0x40317e`
- `KERNEL32!GetLastError` at `0x4031a7`
- `KERNEL32!GetLastError` at `0x4031a7`
- `ole32!CoImpersonateClient` at `0x403120`
- `ole32!CoImpersonateClient` at `0x403120`
- `ole32!CoRevertToSelf` at `0x4031e8`
- `ole32!CoRevertToSelf` at `0x4031e8`

## pseudocode

```c
int __thiscall CActiveXInstallBroker::DuplicateProcessInformation(
        CActiveXInstallBroker *this,
        struct _PROCESS_INFORMATION *a2,
        struct _PROCESS_INFORMATION *a3)
{
  int v3; // esi
  int v4; // ebx
  HANDLE v5; // edi
  signed int LastError; // eax
  HANDLE hSourceProcessHandle; // [esp+10h] [ebp-Ch]
  HANDLE TargetHandle; // [esp+14h] [ebp-8h] BYREF
  HANDLE hObject; // [esp+18h] [ebp-4h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = 0;
  hSourceProcessHandle = GetCurrentProcess();
  TargetHandle = 0;
  hObject = 0;
  if ( !g_fRunningAsSystem )
  {
    v3 = CoImpersonateClient();
    if ( v3 < 0 )
      goto LABEL_10;
    v4 = 1;
  }
  v5 = OpenProcess(0x40u, 0, *((_DWORD *)this + 18));
  if ( v5
    && DuplicateHandle(hSourceProcessHandle, a2->hProcess, v5, &TargetHandle, 0x20000100u, 0, 0)
    && DuplicateHandle(hSourceProcessHandle, a2->hThread, v5, &hObject, 0x20000002u, 0, 0) )
  {
    a3->hProcess = TargetHandle;
    a3->hThread = hObject;
    a3->dwProcessId = a2->dwProcessId;
    a3->dwThreadId = a2->dwThreadId;
LABEL_15:
    CloseHandle(v5);
    goto LABEL_16;
  }
  LastError = GetLastError();
  v3 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v3 = LastError;
LABEL_10:
  if ( hObject )
    CloseHandle(hObject);
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  if ( v5 )
    goto LABEL_15;
LABEL_16:
  if ( v4 )
    CoRevertToSelf();
  return v3;
}

```

## disassembly

```asm
0x4030f5  mov     edi, edi
0x4030f7  push    ebp
0x4030f8  mov     ebp, esp
0x4030fa  sub     esp, 10h
0x4030fd  push    ebx
0x4030fe  push    esi
0x4030ff  push    edi
0x403100  mov     [ebp+var_10], ecx
0x403103  xor     esi, esi
0x403105  xor     ebx, ebx
0x403107  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x40310d  xor     edi, edi
0x40310f  mov     [ebp+hSourceProcessHandle], eax
0x403112  mov     [ebp+TargetHandle], ebx
0x403115  mov     [ebp+hObject], ebx
0x403118  cmp     ?g_fRunningAsSystem@@3HA, ebx; int g_fRunningAsSystem
0x40311e  jnz     short loc_403131
0x403120  call    ds:__imp__CoImpersonateClient@0; CoImpersonateClient()
0x403126  mov     esi, eax
0x403128  test    esi, esi
0x40312a  js      loc_4031BB
0x403130  inc     ebx
0x403131  mov     eax, [ebp+var_10]
0x403134  push    dword ptr [eax+48h]; dwProcessId
0x403137  push    0; bInheritHandle
0x403139  push    40h ; '@'; dwDesiredAccess
0x40313b  call    ds:__imp__OpenProcess@12; OpenProcess(x,x,x)
0x403141  mov     edi, eax
0x403143  test    edi, edi
0x403145  jz      short loc_4031A7
0x403147  push    0; dwOptions
0x403149  push    0; bInheritHandle
0x40314b  push    20000100h; dwDesiredAccess
0x403150  lea     eax, [ebp+TargetHandle]
0x403153  push    eax; lpTargetHandle
0x403154  mov     eax, [ebp+arg_0]
0x403157  push    edi; hTargetProcessHandle
0x403158  push    dword ptr [eax]; hSourceHandle
0x40315a  push    [ebp+hSourceProcessHandle]; hSourceProcessHandle
0x40315d  call    ds:__imp__DuplicateHandle@28; DuplicateHandle(x,x,x,x,x,x,x)
0x403163  test    eax, eax
0x403165  jz      short loc_4031A7
0x403167  push    0; dwOptions
0x403169  push    0; bInheritHandle
0x40316b  push    20000002h; dwDesiredAccess
0x403170  lea     eax, [ebp+hObject]
0x403173  push    eax; lpTargetHandle
0x403174  mov     eax, [ebp+arg_0]
0x403177  push    edi; hTargetProcessHandle
0x403178  push    dword ptr [eax+4]; hSourceHandle
0x40317b  push    [ebp+hSourceProcessHandle]; hSourceProcessHandle
0x40317e  call    ds:__imp__DuplicateHandle@28; DuplicateHandle(x,x,x,x,x,x,x)
0x403184  test    eax, eax
0x403186  jz      short loc_4031A7
0x403188  mov     ecx, [ebp+arg_4]
0x40318b  mov     edx, [ebp+arg_0]
0x40318e  mov     eax, [ebp+TargetHandle]
0x403191  mov     [ecx], eax
0x403193  mov     eax, [ebp+hObject]
0x403196  mov     [ecx+4], eax
0x403199  mov     eax, [edx+8]
0x40319c  mov     [ecx+8], eax
0x40319f  mov     eax, [edx+0Ch]
0x4031a2  mov     [ecx+0Ch], eax
0x4031a5  jmp     short loc_4031DD
0x4031a7  call    ds:__imp__GetLastError@0; GetLastError()
0x4031ad  movzx   esi, ax
0x4031b0  or      esi, 80070000h
0x4031b6  test    eax, eax
0x4031b8  cmovle  esi, eax
0x4031bb  cmp     [ebp+hObject], 0
0x4031bf  jz      short loc_4031CA
0x4031c1  push    [ebp+hObject]; hObject
0x4031c4  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x4031ca  cmp     [ebp+TargetHandle], 0
0x4031ce  jz      short loc_4031D9
0x4031d0  push    [ebp+TargetHandle]; hObject
0x4031d3  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x4031d9  test    edi, edi
0x4031db  jz      short loc_4031E4
0x4031dd  push    edi; hObject
0x4031de  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x4031e4  test    ebx, ebx
0x4031e6  jz      short loc_4031EE
0x4031e8  call    ds:__imp__CoRevertToSelf@0; CoRevertToSelf()
0x4031ee  pop     edi
0x4031ef  mov     eax, esi
0x4031f1  pop     esi
0x4031f2  pop     ebx
0x4031f3  leave
0x4031f4  retn    8
```
