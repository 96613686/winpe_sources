# StopFaxServiceProviders(void)

- ea: `0x14004be0c`
- end: `0x14004bff2`
- name: `?StopFaxServiceProviders@@YAHXZ`
- size: `486`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140024d80`
- `0x140049678`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140026388`
- `0x14004be0c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004beac`
- `KERNEL32!GetLastError` at `0x14004bf4e`
- `KERNEL32!GetLastError` at `0x14004bf90`
- `KERNEL32!GetLastError` at `0x14004beac`
- `KERNEL32!GetLastError` at `0x14004bf4e`
- `KERNEL32!GetLastError` at `0x14004bf90`
- `KERNEL32!SetLastError` at `0x14004bfc6`
- `KERNEL32!SetLastError` at `0x14004bfc6`
- `KERNEL32!CloseHandle` at `0x14004bfd5`
- `KERNEL32!CloseHandle` at `0x14004bfd5`
- `KERNEL32!WaitForSingleObject` at `0x14004bef0`
- `KERNEL32!WaitForSingleObject` at `0x14004bef0`
- `KERNEL32!GetExitCodeThread` at `0x14004bf69`
- `KERNEL32!GetExitCodeThread` at `0x14004bf69`
- `KERNEL32!CreateThread` at `0x14004be81`
- `KERNEL32!CreateThread` at `0x14004be81`

## pseudocode

```c
_BOOL8 StopFaxServiceProviders(void)
{
  unsigned int v0; // edx
  HANDLE v1; // rdi
  DWORD v2; // eax
  BOOL v3; // ebx
  unsigned int i; // r8d
  DWORD v5; // eax
  DWORD LastError; // eax
  __int64 v7; // rdx
  DWORD ExitCode; // [rsp+50h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+58h] [rbp+10h] BYREF

  ThreadId = 0;
  ExitCode = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
  }
  v1 = CreateThread(0, 0, ShutdownDeviceProviders, 0, 0, &ThreadId);
  if ( v1 )
  {
    for ( i = 20000; ; i = 30000 )
    {
      ReportServiceStatus(3u, v0, i);
      v5 = WaitForSingleObject(v1, 0x2710u);
      if ( !v5 )
        break;
      if ( v5 != 258 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          v7 = 56;
          goto LABEL_28;
        }
        goto LABEL_29;
      }
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
      }
    }
    if ( !GetExitCodeThread(v1, &ExitCode) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v7 = 54;
LABEL_28:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, LastError);
      }
LABEL_29:
      v3 = 0;
      goto LABEL_31;
    }
    v3 = ExitCode == 0;
    SetLastError(ExitCode);
LABEL_31:
    CloseHandle(v1);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v2);
    }
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x14004be0c  mov     [rsp+arg_10], rbx
0x14004be11  push    rbp
0x14004be12  push    rdi
0x14004be13  push    r14
0x14004be15  sub     rsp, 30h
0x14004be19  mov     [rsp+48h+ThreadId], 0
0x14004be21  mov     [rsp+48h+ExitCode], 0
0x14004be29  mov     rcx, cs:WPP_GLOBAL_Control
0x14004be30  lea     rbp, WPP_GLOBAL_Control
0x14004be37  lea     r14, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x14004be3e  mov     bl, 4
0x14004be40  cmp     rcx, rbp
0x14004be43  jz      short loc_14004BE61
0x14004be45  test    [rcx+1Ch], bl
0x14004be48  jz      short loc_14004BE61
0x14004be4a  cmp     byte ptr [rcx+19h], 5
0x14004be4e  jb      short loc_14004BE61
0x14004be50  mov     rcx, [rcx+10h]
0x14004be54  mov     edx, 34h ; '4'
0x14004be59  mov     r8, r14
0x14004be5c  call    WPP_SF_
0x14004be61  lea     rax, [rsp+48h+ThreadId]
0x14004be66  xor     r9d, r9d; lpParameter
0x14004be69  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x14004be6e  lea     r8, ?ShutdownDeviceProviders@@YAKPEAX@Z; lpStartAddress
0x14004be75  xor     edx, edx; dwStackSize
0x14004be77  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x14004be7f  xor     ecx, ecx; lpThreadAttributes
0x14004be81  call    cs:__imp_CreateThread
0x14004be88  nop     dword ptr [rax+rax+00h]
0x14004be8d  mov     rdi, rax
0x14004be90  test    rax, rax
0x14004be93  jnz     short loc_14004BED8
0x14004be95  mov     rax, cs:WPP_GLOBAL_Control
0x14004be9c  cmp     rax, rbp
0x14004be9f  jz      short loc_14004BED1
0x14004bea1  test    [rax+1Ch], bl
0x14004bea4  jz      short loc_14004BED1
0x14004bea6  cmp     byte ptr [rax+19h], 2
0x14004beaa  jb      short loc_14004BED1
0x14004beac  call    cs:__imp_GetLastError
0x14004beb3  nop     dword ptr [rax+rax+00h]
0x14004beb8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bebf  lea     edx, [rdi+35h]
0x14004bec2  mov     r9d, eax
0x14004bec5  mov     r8, r14
0x14004bec8  mov     rcx, [rcx+10h]
0x14004becc  call    WPP_SF_d
0x14004bed1  xor     ebx, ebx
0x14004bed3  jmp     loc_14004BFE1
0x14004bed8  mov     r8d, 4E20h; unsigned int
0x14004bede  mov     ecx, 3; unsigned int
0x14004bee3  call    ?ReportServiceStatus@@YAHKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x14004bee8  mov     edx, 2710h; dwMilliseconds
0x14004beed  mov     rcx, rdi; hHandle
0x14004bef0  call    cs:__imp_WaitForSingleObject
0x14004bef7  nop     dword ptr [rax+rax+00h]
0x14004befc  test    eax, eax
0x14004befe  jz      short loc_14004BF61
0x14004bf00  cmp     eax, 102h
0x14004bf05  jnz     short loc_14004BF37
0x14004bf07  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bf0e  cmp     rcx, rbp
0x14004bf11  jz      short loc_14004BF2F
0x14004bf13  test    [rcx+1Ch], bl
0x14004bf16  jz      short loc_14004BF2F
0x14004bf18  cmp     byte ptr [rcx+19h], 5
0x14004bf1c  jb      short loc_14004BF2F
0x14004bf1e  mov     rcx, [rcx+10h]
0x14004bf22  mov     edx, 37h ; '7'
0x14004bf27  mov     r8, r14
0x14004bf2a  call    WPP_SF_
0x14004bf2f  mov     r8d, 7530h
0x14004bf35  jmp     short loc_14004BEDE
0x14004bf37  mov     rax, cs:WPP_GLOBAL_Control
0x14004bf3e  cmp     rax, rbp
0x14004bf41  jz      short loc_14004BFB7
0x14004bf43  test    [rax+1Ch], bl
0x14004bf46  jz      short loc_14004BFB7
0x14004bf48  cmp     byte ptr [rax+19h], 2
0x14004bf4c  jb      short loc_14004BFB7
0x14004bf4e  call    cs:__imp_GetLastError
0x14004bf55  nop     dword ptr [rax+rax+00h]
0x14004bf5a  mov     edx, 38h ; '8'
0x14004bf5f  jmp     short loc_14004BFA1
0x14004bf61  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x14004bf66  mov     rcx, rdi; hThread
0x14004bf69  call    cs:__imp_GetExitCodeThread
0x14004bf70  nop     dword ptr [rax+rax+00h]
0x14004bf75  test    eax, eax
0x14004bf77  jnz     short loc_14004BFBB
0x14004bf79  mov     rax, cs:WPP_GLOBAL_Control
0x14004bf80  cmp     rax, rbp
0x14004bf83  jz      short loc_14004BFB7
0x14004bf85  test    [rax+1Ch], bl
0x14004bf88  jz      short loc_14004BFB7
0x14004bf8a  cmp     byte ptr [rax+19h], 2
0x14004bf8e  jb      short loc_14004BFB7
0x14004bf90  call    cs:__imp_GetLastError
0x14004bf97  nop     dword ptr [rax+rax+00h]
0x14004bf9c  mov     edx, 36h ; '6'
0x14004bfa1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bfa8  mov     r9d, eax
0x14004bfab  mov     r8, r14
0x14004bfae  mov     rcx, [rcx+10h]
0x14004bfb2  call    WPP_SF_d
0x14004bfb7  xor     ebx, ebx
0x14004bfb9  jmp     short loc_14004BFD2
0x14004bfbb  mov     ecx, [rsp+48h+ExitCode]; dwErrCode
0x14004bfbf  xor     ebx, ebx
0x14004bfc1  test    ecx, ecx
0x14004bfc3  setz    bl
0x14004bfc6  call    cs:__imp_SetLastError
0x14004bfcd  nop     dword ptr [rax+rax+00h]
0x14004bfd2  mov     rcx, rdi; hObject
0x14004bfd5  call    cs:__imp_CloseHandle
0x14004bfdc  nop     dword ptr [rax+rax+00h]
0x14004bfe1  mov     eax, ebx
0x14004bfe3  mov     rbx, [rsp+48h+arg_10]
0x14004bfe8  add     rsp, 30h
0x14004bfec  pop     r14
0x14004bfee  pop     rdi
0x14004bfef  pop     rbp
0x14004bff0  retn
```
