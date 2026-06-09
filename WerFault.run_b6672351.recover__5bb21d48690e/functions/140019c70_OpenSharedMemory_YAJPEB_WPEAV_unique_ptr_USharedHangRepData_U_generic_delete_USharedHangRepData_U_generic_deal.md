# ?OpenSharedMemory@@YAJPEB_WPEAV?$unique_ptr@USharedHangRepData@@U?$generic_delete@USharedHangRepData@@U?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@@Z

- ea: `0x140019c70`
- end: `0x140019e4f`
- name: `?OpenSharedMemory@@YAJPEB_WPEAV?$unique_ptr@USharedHangRepData@@U?$generic_delete@USharedHangRepData@@U?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a274`
- `0x140020bf0`
- `0x140024c90`
- `0x1400271e0`
- `0x14002840c`

## callees

- `0x140014f14`
- `0x140019c70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019d44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019dc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019d44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019dc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019e1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019e1a`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140019c8c`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140019c8c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140019d30`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140019db0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140019d30`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140019db0`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140019caa`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140019e08`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140019e2f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140019caa`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140019e08`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140019e2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140019c70  mov     [rsp+arg_0], rbx
0x140019c75  mov     [rsp+arg_8], rsi
0x140019c7a  push    rdi
0x140019c7b  sub     rsp, 30h
0x140019c7f  mov     rdi, rdx
0x140019c82  mov     r8, rcx; lpName
0x140019c85  xor     edx, edx; bInheritHandle
0x140019c87  lea     ebx, [rdx+4]
0x140019c8a  mov     ecx, ebx; dwDesiredAccess
0x140019c8c  call    cs:__imp_OpenFileMappingW
0x140019c93  nop     dword ptr [rax+rax+00h]
0x140019c98  mov     rsi, rax
0x140019c9b  mov     rcx, [rdi]; lpBaseAddress
0x140019c9e  mov     qword ptr [rdi], 0
0x140019ca5  test    rcx, rcx
0x140019ca8  jz      short loc_140019CB7
0x140019caa  call    cs:__imp_UnmapViewOfFile
0x140019cb1  nop     dword ptr [rax+rax+00h]
0x140019cb6  nop
0x140019cb7  lea     rcx, [rsi+1]
0x140019cbb  cmp     rcx, 1
0x140019cbf  ja      short loc_140019D1C
0x140019cc1  xor     ebx, ebx
0x140019cc3  call    cs:__imp_GetLastError
0x140019cca  nop     dword ptr [rax+rax+00h]
0x140019ccf  mov     edi, eax
0x140019cd1  test    eax, eax
0x140019cd3  jle     short loc_140019CDE
0x140019cd5  movzx   edi, ax
0x140019cd8  or      edi, 80070000h
0x140019cde  lea     rax, WPP_GLOBAL_Control
0x140019ce5  mov     rcx, cs:WPP_GLOBAL_Control
0x140019cec  cmp     rcx, rax
0x140019cef  jz      loc_140019E27
0x140019cf5  test    byte ptr [rcx+1Ch], 1
0x140019cf9  jz      loc_140019E27
0x140019cff  mov     edx, 0Fh
0x140019d04  mov     r9d, edi
0x140019d07  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x140019d0e  mov     rcx, [rcx+10h]
0x140019d12  call    WPP_SF_d
0x140019d17  jmp     loc_140019E27
0x140019d1c  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x140019d25  xor     r9d, r9d; dwFileOffsetLow
0x140019d28  xor     r8d, r8d; dwFileOffsetHigh
0x140019d2b  mov     edx, ebx; dwDesiredAccess
0x140019d2d  mov     rcx, rsi; hFileMappingObject
0x140019d30  call    cs:__imp_MapViewOfFile
0x140019d37  nop     dword ptr [rax+rax+00h]
0x140019d3c  mov     rbx, rax
0x140019d3f  test    rax, rax
0x140019d42  jnz     short loc_140019D9A
0x140019d44  call    cs:__imp_GetLastError
0x140019d4b  nop     dword ptr [rax+rax+00h]
0x140019d50  mov     edi, eax
0x140019d52  test    eax, eax
0x140019d54  jle     short loc_140019D5F
0x140019d56  movzx   edi, ax
0x140019d59  or      edi, 80070000h
0x140019d5f  lea     rax, WPP_GLOBAL_Control
0x140019d66  mov     rcx, cs:WPP_GLOBAL_Control
0x140019d6d  cmp     rcx, rax
0x140019d70  jz      loc_140019E17
0x140019d76  test    byte ptr [rcx+1Ch], 1
0x140019d7a  jz      loc_140019E17
0x140019d80  mov     edx, 10h
0x140019d85  mov     r9d, edi
0x140019d88  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x140019d8f  mov     rcx, [rcx+10h]
0x140019d93  call    WPP_SF_d
0x140019d98  jmp     short loc_140019E17
0x140019d9a  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x140019da3  xor     r9d, r9d; dwFileOffsetLow
0x140019da6  xor     r8d, r8d; dwFileOffsetHigh
0x140019da9  lea     edx, [r9+2]; dwDesiredAccess
0x140019dad  mov     rcx, [rax]; hFileMappingObject
0x140019db0  call    cs:__imp_MapViewOfFile
0x140019db7  nop     dword ptr [rax+rax+00h]
0x140019dbc  nop
0x140019dbd  test    rax, rax
0x140019dc0  jnz     short loc_140019DFD
0x140019dc2  call    cs:__imp_GetLastError
0x140019dc9  nop     dword ptr [rax+rax+00h]
0x140019dce  mov     edi, eax
0x140019dd0  test    eax, eax
0x140019dd2  jle     short loc_140019DDD
0x140019dd4  movzx   edi, ax
0x140019dd7  or      edi, 80070000h
0x140019ddd  lea     rax, WPP_GLOBAL_Control
0x140019de4  mov     rcx, cs:WPP_GLOBAL_Control
0x140019deb  cmp     rcx, rax
0x140019dee  jz      short loc_140019E17
0x140019df0  test    byte ptr [rcx+1Ch], 1
0x140019df4  jz      short loc_140019E17
0x140019df6  mov     edx, 11h
0x140019dfb  jmp     short loc_140019D85
0x140019dfd  mov     rcx, [rdi]; lpBaseAddress
0x140019e00  mov     [rdi], rax
0x140019e03  test    rcx, rcx
0x140019e06  jz      short loc_140019E15
0x140019e08  call    cs:__imp_UnmapViewOfFile
0x140019e0f  nop     dword ptr [rax+rax+00h]
0x140019e14  nop
0x140019e15  xor     edi, edi
0x140019e17  mov     rcx, rsi; hObject
0x140019e1a  call    cs:__imp_CloseHandle
0x140019e21  nop     dword ptr [rax+rax+00h]
0x140019e26  nop
0x140019e27  test    rbx, rbx
0x140019e2a  jz      short loc_140019E3C
0x140019e2c  mov     rcx, rbx; lpBaseAddress
0x140019e2f  call    cs:__imp_UnmapViewOfFile
0x140019e36  nop     dword ptr [rax+rax+00h]
0x140019e3b  nop
0x140019e3c  mov     eax, edi
0x140019e3e  mov     rbx, [rsp+38h+arg_0]
0x140019e43  mov     rsi, [rsp+38h+arg_8]
0x140019e48  add     rsp, 30h
0x140019e4c  pop     rdi
0x140019e4d  retn
```
