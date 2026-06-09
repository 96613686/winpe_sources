# ?OpenSharedMemory@@YAJPEB_WPEAV?$unique_ptr@USharedHangRepData@@U?$generic_delete@USharedHangRepData@@U?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@@Z

- ea: `0x140018dbc`
- end: `0x140018f5e`
- name: `?OpenSharedMemory@@YAJPEB_WPEAV?$unique_ptr@USharedHangRepData@@U?$generic_delete@USharedHangRepData@@U?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(LPCWSTR lpName, const void **)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140019374`
- `0x14001f610`
- `0x140023560`
- `0x1400258c0`
- `0x140026a70`

## callees

- `0x140014474`
- `0x140018dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018e03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018e78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018e03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018e78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018eea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018f36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018f36`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140018dd8`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140018dd8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140018e6a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140018ede`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140018e6a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140018ede`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140018df0`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140018f2a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140018f45`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140018df0`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140018f2a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140018f45`

## pseudocode

```c
__int64 __fastcall OpenSharedMemory(LPCWSTR lpName, const void **a2)
{
  HANDLE v3; // rsi
  const void *v4; // rcx
  HANDLE *v5; // rbx
  signed int v6; // eax
  unsigned int v7; // edi
  HANDLE *v8; // rax
  signed int v9; // eax
  CUserModeHangReport *v10; // rcx
  __int64 v11; // rdx
  const void *v12; // rax
  signed int LastError; // eax
  const void *v14; // rcx

  v3 = OpenFileMappingW(4u, 0, lpName);
  v4 = *a2;
  *a2 = 0;
  if ( v4 )
    UnmapViewOfFile(v4);
  if ( (unsigned __int64)v3 + 1 > 1 )
  {
    v8 = (HANDLE *)MapViewOfFile(v3, 4u, 0, 0, 0);
    v5 = v8;
    if ( v8 )
    {
      v12 = MapViewOfFile(*v8, 2u, 0, 0, 0);
      if ( v12 )
      {
        v14 = *a2;
        *a2 = v12;
        if ( v14 )
          UnmapViewOfFile(v14);
        v7 = 0;
        goto LABEL_25;
      }
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_25:
        CloseHandle(v3);
        goto LABEL_26;
      }
      v11 = 17;
    }
    else
    {
      v9 = GetLastError();
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_25;
      }
      v11 = 16;
    }
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids, v7);
    goto LABEL_25;
  }
  v5 = 0;
  v6 = GetLastError();
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids, v7);
  }
LABEL_26:
  if ( v5 )
    UnmapViewOfFile(v5);
  return v7;
}

```

## disassembly

```asm
0x140018dbc  mov     [rsp+arg_0], rbx
0x140018dc1  mov     [rsp+arg_8], rsi
0x140018dc6  push    rdi
0x140018dc7  sub     rsp, 30h
0x140018dcb  mov     rdi, rdx
0x140018dce  mov     r8, rcx; lpName
0x140018dd1  xor     edx, edx; bInheritHandle
0x140018dd3  lea     ebx, [rdx+4]
0x140018dd6  mov     ecx, ebx; dwDesiredAccess
0x140018dd8  call    cs:__imp_OpenFileMappingW
0x140018dde  mov     rsi, rax
0x140018de1  mov     rcx, [rdi]; lpBaseAddress
0x140018de4  mov     qword ptr [rdi], 0
0x140018deb  test    rcx, rcx
0x140018dee  jz      short loc_140018DF7
0x140018df0  call    cs:__imp_UnmapViewOfFile
0x140018df6  nop
0x140018df7  lea     rcx, [rsi+1]
0x140018dfb  cmp     rcx, 1
0x140018dff  ja      short loc_140018E56
0x140018e01  xor     ebx, ebx
0x140018e03  call    cs:__imp_GetLastError
0x140018e09  mov     edi, eax
0x140018e0b  test    eax, eax
0x140018e0d  jle     short loc_140018E18
0x140018e0f  movzx   edi, ax
0x140018e12  or      edi, 80070000h
0x140018e18  lea     rax, WPP_GLOBAL_Control
0x140018e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e26  cmp     rcx, rax
0x140018e29  jz      loc_140018F3D
0x140018e2f  test    byte ptr [rcx+1Ch], 1
0x140018e33  jz      loc_140018F3D
0x140018e39  mov     edx, 0Fh
0x140018e3e  mov     r9d, edi
0x140018e41  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x140018e48  mov     rcx, [rcx+10h]
0x140018e4c  call    WPP_SF_d
0x140018e51  jmp     loc_140018F3D
0x140018e56  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x140018e5f  xor     r9d, r9d; dwFileOffsetLow
0x140018e62  xor     r8d, r8d; dwFileOffsetHigh
0x140018e65  mov     edx, ebx; dwDesiredAccess
0x140018e67  mov     rcx, rsi; hFileMappingObject
0x140018e6a  call    cs:__imp_MapViewOfFile
0x140018e70  mov     rbx, rax
0x140018e73  test    rax, rax
0x140018e76  jnz     short loc_140018EC8
0x140018e78  call    cs:__imp_GetLastError
0x140018e7e  mov     edi, eax
0x140018e80  test    eax, eax
0x140018e82  jle     short loc_140018E8D
0x140018e84  movzx   edi, ax
0x140018e87  or      edi, 80070000h
0x140018e8d  lea     rax, WPP_GLOBAL_Control
0x140018e94  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e9b  cmp     rcx, rax
0x140018e9e  jz      loc_140018F33
0x140018ea4  test    byte ptr [rcx+1Ch], 1
0x140018ea8  jz      loc_140018F33
0x140018eae  mov     edx, 10h
0x140018eb3  mov     r9d, edi
0x140018eb6  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x140018ebd  mov     rcx, [rcx+10h]
0x140018ec1  call    WPP_SF_d
0x140018ec6  jmp     short loc_140018F33
0x140018ec8  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x140018ed1  xor     r9d, r9d; dwFileOffsetLow
0x140018ed4  xor     r8d, r8d; dwFileOffsetHigh
0x140018ed7  lea     edx, [r9+2]; dwDesiredAccess
0x140018edb  mov     rcx, [rax]; hFileMappingObject
0x140018ede  call    cs:__imp_MapViewOfFile
0x140018ee4  nop
0x140018ee5  test    rax, rax
0x140018ee8  jnz     short loc_140018F1F
0x140018eea  call    cs:__imp_GetLastError
0x140018ef0  mov     edi, eax
0x140018ef2  test    eax, eax
0x140018ef4  jle     short loc_140018EFF
0x140018ef6  movzx   edi, ax
0x140018ef9  or      edi, 80070000h
0x140018eff  lea     rax, WPP_GLOBAL_Control
0x140018f06  mov     rcx, cs:WPP_GLOBAL_Control
0x140018f0d  cmp     rcx, rax
0x140018f10  jz      short loc_140018F33
0x140018f12  test    byte ptr [rcx+1Ch], 1
0x140018f16  jz      short loc_140018F33
0x140018f18  mov     edx, 11h
0x140018f1d  jmp     short loc_140018EB3
0x140018f1f  mov     rcx, [rdi]; lpBaseAddress
0x140018f22  mov     [rdi], rax
0x140018f25  test    rcx, rcx
0x140018f28  jz      short loc_140018F31
0x140018f2a  call    cs:__imp_UnmapViewOfFile
0x140018f30  nop
0x140018f31  xor     edi, edi
0x140018f33  mov     rcx, rsi; hObject
0x140018f36  call    cs:__imp_CloseHandle
0x140018f3c  nop
0x140018f3d  test    rbx, rbx
0x140018f40  jz      short loc_140018F4C
0x140018f42  mov     rcx, rbx; lpBaseAddress
0x140018f45  call    cs:__imp_UnmapViewOfFile
0x140018f4b  nop
0x140018f4c  mov     eax, edi
0x140018f4e  mov     rbx, [rsp+38h+arg_0]
0x140018f53  mov     rsi, [rsp+38h+arg_8]
0x140018f58  add     rsp, 30h
0x140018f5c  pop     rdi
0x140018f5d  retn
```
