# GetDiskPath(ulong,int,unsigned __int64 *,ushort *)

- ea: `0x14001a900`
- end: `0x14001ab5f`
- name: `?GetDiskPath@@YAHKHPEA_KPEAG@Z`
- size: `607`
- prototype: `__int64 __fastcall(int, int, unsigned __int64 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14001480c`
- `0x140018110`

## callees

- `0x14001a900`
- `0x14001bd28`
- `0x14001c1d8`
- `0x14001c238`
- `0x14001c3b0`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001aa47`
- `KERNEL32!CloseHandle` at `0x14001aada`
- `KERNEL32!CloseHandle` at `0x14001aa47`
- `KERNEL32!CloseHandle` at `0x14001aada`
- `KERNEL32!HeapAlloc` at `0x14001a962`
- `KERNEL32!HeapAlloc` at `0x14001a962`
- `KERNEL32!HeapFree` at `0x14001ab17`
- `KERNEL32!HeapFree` at `0x14001ab17`
- `KERNEL32!GetProcessHeap` at `0x14001a92e`
- `KERNEL32!GetProcessHeap` at `0x14001a92e`
- `KERNEL32!SetLastError` at `0x14001aab2`
- `KERNEL32!SetLastError` at `0x14001ab32`
- `KERNEL32!SetLastError` at `0x14001aab2`
- `KERNEL32!SetLastError` at `0x14001ab32`
- `KERNEL32!GetLastError` at `0x14001aab8`
- `KERNEL32!GetLastError` at `0x14001aac0`
- `KERNEL32!GetLastError` at `0x14001aae6`
- `KERNEL32!GetLastError` at `0x14001ab02`
- `KERNEL32!GetLastError` at `0x14001aab8`
- `KERNEL32!GetLastError` at `0x14001aac0`
- `KERNEL32!GetLastError` at `0x14001aae6`
- `KERNEL32!GetLastError` at `0x14001ab02`
- `KERNEL32!DeviceIoControl` at `0x14001aa31`
- `KERNEL32!DeviceIoControl` at `0x14001aa31`
- `KERNEL32!CreateFileW` at `0x14001a9f4`
- `KERNEL32!CreateFileW` at `0x14001a9f4`

## pseudocode

```c
__int64 __fastcall GetDiskPath(int a1, int a2, unsigned __int64 *a3, unsigned __int16 *a4)
{
  HANDLE ProcessHeap; // rax
  __int64 FirstDevice; // r14
  void *v10; // r13
  __int64 FileW; // rbp
  unsigned __int16 *v12; // rsi
  unsigned int NextDevice; // ebx
  DWORD v14; // ecx
  GUID *v15; // rcx
  BOOL v16; // eax
  int v17; // eax
  DWORD LastError; // edi
  BOOL v19; // eax
  unsigned int DeviceClose; // eax
  BOOL v21; // eax
  unsigned __int64 v23; // [rsp+40h] [rbp-58h] BYREF
  __int64 OutBuffer; // [rsp+48h] [rbp-50h] BYREF
  int v25; // [rsp+50h] [rbp-48h]

  ProcessHeap = GetProcessHeap();
  FirstDevice = -1;
  v23 = 0;
  v10 = ProcessHeap;
  FileW = -1;
  if ( *a3 && a4 )
    *a4 = 0;
  v12 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x10000u);
  if ( v12 )
  {
    v23 = 0x8000;
    v15 = &GUID_DEVINTERFACE_DISK;
    if ( a2 )
      v15 = &GUID_DEVINTERFACE_HIDDEN_DISK;
    FirstDevice = (__int64)FindFirstDevice(
                             v15,
                             0,
                             0,
                             (int (*)(void *, unsigned __int64 *, unsigned __int16 *))FindNextDevice,
                             &v23,
                             v12);
    if ( FirstDevice == -1 )
    {
      NextDevice = 0;
    }
    else
    {
      while ( 1 )
      {
        NextDevice = 0;
        OutBuffer = 0;
        v25 = 0;
        FileW = (__int64)CreateFileW(v12, 0x20000u, 3u, 0, 3u, 0, 0);
        if ( FileW == -1 )
          break;
        NextDevice = DeviceIoControl((HANDLE)FileW, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, 0, 0);
        if ( !NextDevice )
          break;
        if ( HIDWORD(OutBuffer) == a1 )
        {
          if ( !a4 )
          {
            NextDevice = 0;
            v14 = 122;
            goto LABEL_21;
          }
          v17 = StringCchCopyNW(a4, *a3, v12, v23);
          v14 = v17;
          if ( v17 < 0 )
          {
            NextDevice = 0;
            if ( (v17 & 0x1FFF0000) == 0x70000 )
              v14 = (unsigned __int16)v17;
            goto LABEL_21;
          }
          break;
        }
        v16 = CloseHandle((HANDLE)FileW);
        FileW = -1;
        NextDevice = v16;
        if ( v16 )
        {
          v23 = 0x8000;
          NextDevice = FindNextDevice((GUID *)FirstDevice, &v23, v12);
          if ( NextDevice )
            continue;
        }
        break;
      }
    }
  }
  else
  {
    NextDevice = 0;
    v14 = 8;
LABEL_21:
    SetLastError(v14);
  }
  LastError = GetLastError();
  if ( GetLastError() == 18 )
    LastError = 2;
  if ( FileW != -1 )
  {
    v19 = CloseHandle((HANDLE)FileW);
    if ( NextDevice )
    {
      NextDevice = v19;
      LastError = GetLastError();
    }
  }
  if ( FirstDevice != -1 )
  {
    DeviceClose = FindDeviceClose((void *)FirstDevice);
    if ( NextDevice )
    {
      NextDevice = DeviceClose;
      LastError = GetLastError();
    }
  }
  if ( v12 )
  {
    v21 = HeapFree(v10, 0, v12);
    if ( NextDevice )
    {
      NextDevice = v21;
      LastError = 6;
    }
  }
  *a3 = v23;
  SetLastError(LastError);
  return NextDevice;
}

```

## disassembly

```asm
0x14001a900  mov     [rsp+arg_0], rbx
0x14001a905  push    rbp
0x14001a906  push    rsi
0x14001a907  push    rdi
0x14001a908  push    r12
0x14001a90a  push    r13
0x14001a90c  push    r14
0x14001a90e  push    r15
0x14001a910  sub     rsp, 60h
0x14001a914  mov     rax, cs:__security_cookie
0x14001a91b  xor     rax, rsp
0x14001a91e  mov     [rsp+98h+var_40], rax
0x14001a923  mov     rdi, r9
0x14001a926  mov     r15, r8
0x14001a929  mov     ebx, edx
0x14001a92b  mov     r12d, ecx
0x14001a92e  call    cs:__imp_GetProcessHeap
0x14001a934  or      r14, 0FFFFFFFFFFFFFFFFh
0x14001a938  mov     [rsp+98h+var_58], 0
0x14001a941  cmp     qword ptr [r15], 0
0x14001a945  mov     r13, rax
0x14001a948  mov     rbp, r14
0x14001a94b  jbe     short loc_14001A957
0x14001a94d  test    rdi, rdi
0x14001a950  jz      short loc_14001A957
0x14001a952  xor     ecx, ecx
0x14001a954  mov     [rdi], cx
0x14001a957  xor     edx, edx; dwFlags
0x14001a959  mov     r8d, 10000h; dwBytes
0x14001a95f  mov     rcx, r13; hHeap
0x14001a962  call    cs:__imp_HeapAlloc
0x14001a968  mov     rsi, rax
0x14001a96b  test    rax, rax
0x14001a96e  jnz     short loc_14001A97A
0x14001a970  xor     ebx, ebx
0x14001a972  lea     ecx, [rax+8]
0x14001a975  jmp     loc_14001AAB2
0x14001a97a  lea     rax, GUID_DEVINTERFACE_HIDDEN_DISK
0x14001a981  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rsi; unsigned __int16 *
0x14001a986  test    ebx, ebx
0x14001a988  mov     [rsp+98h+var_58], 8000h
0x14001a991  lea     rcx, GUID_DEVINTERFACE_DISK
0x14001a998  cmovnz  rcx, rax; ClassGuid
0x14001a99c  lea     r9, ?FindNextDevice@@YAHPEAXPEA_KPEAG@Z; int (*)(void *, unsigned __int64 *, unsigned __int16 *)
0x14001a9a3  lea     rax, [rsp+98h+var_58]
0x14001a9a8  xor     r8d, r8d; void *
0x14001a9ab  xor     edx, edx; Size
0x14001a9ad  mov     qword ptr [rsp+98h+dwCreationDisposition], rax; unsigned __int64 *
0x14001a9b2  call    ?FindFirstDevice@@YAPEAXPEBU_GUID@@_KPEAXP6AH2PEA_KPEAG@Z34@Z; FindFirstDevice(_GUID const *,unsigned __int64,void *,int (*)(void *,unsigned __int64 *,ushort *),unsigned __int64 *,ushort *)
0x14001a9b7  mov     r14, rax
0x14001a9ba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001a9be  jnz     short loc_14001A9C7
0x14001a9c0  xor     ebx, ebx
0x14001a9c2  jmp     loc_14001AAB8
0x14001a9c7  xor     eax, eax
0x14001a9c9  xor     ebx, ebx
0x14001a9cb  mov     [rsp+98h+hTemplateFile], rbx; hTemplateFile
0x14001a9d0  xor     r9d, r9d; lpSecurityAttributes
0x14001a9d3  mov     [rsp+98h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x14001a9d7  mov     edx, 20000h; dwDesiredAccess
0x14001a9dc  mov     rcx, rsi; lpFileName
0x14001a9df  mov     [rsp+98h+OutBuffer], rax
0x14001a9e4  lea     r8d, [rax+3]; dwShareMode
0x14001a9e8  mov     [rsp+98h+var_48], eax
0x14001a9ec  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x14001a9f4  call    cs:__imp_CreateFileW
0x14001a9fa  mov     rbp, rax
0x14001a9fd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001aa01  jz      loc_14001AAB8
0x14001aa07  mov     [rsp+98h+lpOverlapped], rbx; lpOverlapped
0x14001aa0c  lea     rax, [rsp+98h+OutBuffer]
0x14001aa11  mov     [rsp+98h+hTemplateFile], rbx; lpBytesReturned
0x14001aa16  xor     r9d, r9d; nInBufferSize
0x14001aa19  mov     [rsp+98h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x14001aa21  xor     r8d, r8d; lpInBuffer
0x14001aa24  mov     edx, 2D1080h; dwIoControlCode
0x14001aa29  mov     qword ptr [rsp+98h+dwCreationDisposition], rax; lpOutBuffer
0x14001aa2e  mov     rcx, rbp; hDevice
0x14001aa31  call    cs:__imp_DeviceIoControl
0x14001aa37  mov     ebx, eax
0x14001aa39  test    eax, eax
0x14001aa3b  jz      short loc_14001AAB8
0x14001aa3d  cmp     dword ptr [rsp+98h+OutBuffer+4], r12d
0x14001aa42  jz      short loc_14001AA7C
0x14001aa44  mov     rcx, rbp; hObject
0x14001aa47  call    cs:__imp_CloseHandle
0x14001aa4d  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14001aa51  mov     ebx, eax
0x14001aa53  test    eax, eax
0x14001aa55  jz      short loc_14001AAB8
0x14001aa57  mov     r8, rsi; unsigned __int16 *
0x14001aa5a  mov     [rsp+98h+var_58], 8000h
0x14001aa63  lea     rdx, [rsp+98h+var_58]; unsigned __int64 *
0x14001aa68  mov     rcx, r14; InterfaceClassGuid
0x14001aa6b  call    ?FindNextDevice@@YAHPEAXPEA_KPEAG@Z; FindNextDevice(void *,unsigned __int64 *,ushort *)
0x14001aa70  mov     ebx, eax
0x14001aa72  test    eax, eax
0x14001aa74  jnz     loc_14001A9C7
0x14001aa7a  jmp     short loc_14001AAB8
0x14001aa7c  test    rdi, rdi
0x14001aa7f  jnz     short loc_14001AA88
0x14001aa81  xor     ebx, ebx
0x14001aa83  lea     ecx, [rdi+7Ah]
0x14001aa86  jmp     short loc_14001AAB2
0x14001aa88  mov     r9, [rsp+98h+var_58]; unsigned __int64
0x14001aa8d  mov     r8, rsi; unsigned __int16 *
0x14001aa90  mov     rdx, [r15]; unsigned __int64
0x14001aa93  mov     rcx, rdi; unsigned __int16 *
0x14001aa96  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14001aa9b  mov     ecx, eax
0x14001aa9d  test    eax, eax
0x14001aa9f  jns     short loc_14001AAB8
0x14001aaa1  xor     ebx, ebx
0x14001aaa3  and     eax, 1FFF0000h
0x14001aaa8  cmp     eax, 70000h
0x14001aaad  jnz     short loc_14001AAB2
0x14001aaaf  movzx   ecx, cx; dwErrCode
0x14001aab2  call    cs:__imp_SetLastError
0x14001aab8  call    cs:__imp_GetLastError
0x14001aabe  mov     edi, eax
0x14001aac0  call    cs:__imp_GetLastError
0x14001aac6  cmp     eax, 12h
0x14001aac9  mov     ecx, 2
0x14001aace  cmovz   edi, ecx
0x14001aad1  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14001aad5  jz      short loc_14001AAEE
0x14001aad7  mov     rcx, rbp; hObject
0x14001aada  call    cs:__imp_CloseHandle
0x14001aae0  test    ebx, ebx
0x14001aae2  jz      short loc_14001AAEE
0x14001aae4  mov     ebx, eax
0x14001aae6  call    cs:__imp_GetLastError
0x14001aaec  mov     edi, eax
0x14001aaee  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14001aaf2  jz      short loc_14001AB0A
0x14001aaf4  mov     rcx, r14; lpMem
0x14001aaf7  call    ?FindDeviceClose@@YAHPEAX@Z; FindDeviceClose(void *)
0x14001aafc  test    ebx, ebx
0x14001aafe  jz      short loc_14001AB0A
0x14001ab00  mov     ebx, eax
0x14001ab02  call    cs:__imp_GetLastError
0x14001ab08  mov     edi, eax
0x14001ab0a  test    rsi, rsi
0x14001ab0d  jz      short loc_14001AB28
0x14001ab0f  mov     r8, rsi; lpMem
0x14001ab12  xor     edx, edx; dwFlags
0x14001ab14  mov     rcx, r13; hHeap
0x14001ab17  call    cs:__imp_HeapFree
0x14001ab1d  test    ebx, ebx
0x14001ab1f  jz      short loc_14001AB28
0x14001ab21  mov     ebx, eax
0x14001ab23  mov     edi, 6
0x14001ab28  mov     rax, [rsp+98h+var_58]
0x14001ab2d  mov     ecx, edi; dwErrCode
0x14001ab2f  mov     [r15], rax
0x14001ab32  call    cs:__imp_SetLastError
0x14001ab38  mov     eax, ebx
0x14001ab3a  mov     rcx, [rsp+98h+var_40]
0x14001ab3f  xor     rcx, rsp; StackCookie
0x14001ab42  call    __security_check_cookie
0x14001ab47  mov     rbx, [rsp+98h+arg_0]
0x14001ab4f  add     rsp, 60h
0x14001ab53  pop     r15
0x14001ab55  pop     r14
0x14001ab57  pop     r13
0x14001ab59  pop     r12
0x14001ab5b  pop     rdi
0x14001ab5c  pop     rsi
0x14001ab5d  pop     rbp
0x14001ab5e  retn
```
