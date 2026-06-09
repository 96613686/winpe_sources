# CBrowserBrokerInstance::MonitorApplicationFrameHost(HWND__ *)

- ea: `0x18000b0f0`
- end: `0x18000b1ee`
- name: `?MonitorApplicationFrameHost@CBrowserBrokerInstance@@UEAAJPEAUHWND__@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(PVOID Context, HWND hWnd)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b0f0`
- `0x18000e428`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000b194`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000b194`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b1b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b1b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b19e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b19e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1c7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b164`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b164`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x18000b130`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x18000b130`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000b14d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000b14d`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::MonitorApplicationFrameHost(HANDLE *Context, HWND hWnd)
{
  int PIC; // eax
  unsigned int v5; // ebx
  HWND Parent; // rax
  HANDLE v7; // rax
  signed int LastError; // eax
  signed int v9; // eax
  DWORD dwProcessId; // [rsp+50h] [rbp+18h] BYREF
  unsigned int v12; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &v12);
  dwProcessId = 0;
  v5 = PIC;
  if ( PIC >= 0 )
  {
    Parent = GetParent(hWnd);
    if ( Parent )
    {
      GetWindowThreadProcessId(Parent, &dwProcessId);
      if ( dwProcessId && (v7 = OpenProcess(0x100000u, 0, dwProcessId), (Context[9] = v7) != 0) )
      {
        if ( !RegisterWaitForSingleObject(
                Context + 10,
                v7,
                s_WaitOnApplicationFrameHost_Callback,
                Context,
                0xFFFFFFFF,
                8u) )
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
          CloseHandle(Context[9]);
          Context[9] = 0;
        }
      }
      else
      {
        v9 = GetLastError();
        v5 = v9;
        if ( v9 > 0 )
          return (unsigned __int16)v9 | 0x80070000;
      }
    }
    else
    {
      return (unsigned int)-2147467263;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000b0f0  mov     rax, rsp
0x18000b0f3  mov     [rax+8], rbx
0x18000b0f7  mov     [rax+10h], rsi
0x18000b0fb  push    rdi
0x18000b0fc  sub     rsp, 30h
0x18000b100  mov     rsi, rdx
0x18000b103  mov     dword ptr [rax+20h], 0
0x18000b10a  mov     rdi, rcx
0x18000b10d  lea     rdx, [rax+20h]; unsigned int *
0x18000b111  mov     ecx, 1; unsigned int
0x18000b116  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18000b11b  mov     [rsp+38h+dwProcessId], 0
0x18000b123  mov     ebx, eax
0x18000b125  test    eax, eax
0x18000b127  js      loc_18000B1DC
0x18000b12d  mov     rcx, rsi; hWnd
0x18000b130  call    cs:__imp_GetParent
0x18000b136  test    rax, rax
0x18000b139  jnz     short loc_18000B145
0x18000b13b  mov     ebx, 80004001h
0x18000b140  jmp     loc_18000B1DC
0x18000b145  lea     rdx, [rsp+38h+dwProcessId]; lpdwProcessId
0x18000b14a  mov     rcx, rax; hWnd
0x18000b14d  call    cs:__imp_GetWindowThreadProcessId
0x18000b153  mov     r8d, [rsp+38h+dwProcessId]; dwProcessId
0x18000b158  test    r8d, r8d
0x18000b15b  jz      short loc_18000B1C7
0x18000b15d  xor     edx, edx; bInheritHandle
0x18000b15f  mov     ecx, 100000h; dwDesiredAccess
0x18000b164  call    cs:__imp_OpenProcess
0x18000b16a  mov     [rdi+48h], rax
0x18000b16e  test    rax, rax
0x18000b171  jz      short loc_18000B1C7
0x18000b173  lea     rcx, [rdi+50h]; phNewWaitObject
0x18000b177  mov     [rsp+38h+dwFlags], 8; dwFlags
0x18000b17f  mov     r9, rdi; Context
0x18000b182  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18000b18a  lea     r8, s_WaitOnApplicationFrameHost_Callback; Callback
0x18000b191  mov     rdx, rax; hObject
0x18000b194  call    cs:__imp_RegisterWaitForSingleObject
0x18000b19a  test    eax, eax
0x18000b19c  jnz     short loc_18000B1DC
0x18000b19e  call    cs:__imp_GetLastError
0x18000b1a4  mov     ebx, eax
0x18000b1a6  test    eax, eax
0x18000b1a8  jle     short loc_18000B1B3
0x18000b1aa  movzx   ebx, ax
0x18000b1ad  or      ebx, 80070000h
0x18000b1b3  mov     rcx, [rdi+48h]; hObject
0x18000b1b7  call    cs:__imp_CloseHandle
0x18000b1bd  mov     qword ptr [rdi+48h], 0
0x18000b1c5  jmp     short loc_18000B1DC
0x18000b1c7  call    cs:__imp_GetLastError
0x18000b1cd  mov     ebx, eax
0x18000b1cf  test    eax, eax
0x18000b1d1  jle     short loc_18000B1DC
0x18000b1d3  movzx   ebx, ax
0x18000b1d6  or      ebx, 80070000h
0x18000b1dc  mov     rsi, [rsp+38h+arg_8]
0x18000b1e1  mov     eax, ebx
0x18000b1e3  mov     rbx, [rsp+38h+arg_0]
0x18000b1e8  add     rsp, 30h
0x18000b1ec  pop     rdi
0x18000b1ed  retn
```
