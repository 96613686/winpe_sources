# DavrGetTheLockOwnerOfTheFile

- ea: `0x18000a010`
- end: `0x18000a366`
- name: `DavrGetTheLockOwnerOfTheFile`
- size: `854`
- prototype: `__int64 __fastcall(__int64, _WORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002ca0`
- `0x18000a010`
- `0x18000b7dc`
- `0x18000b93c`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000a128`
- `ntdll!NtOpenFile` at `0x18000a128`
- `ntdll!RtlNtStatusToDosError` at `0x18000a13c`
- `ntdll!RtlNtStatusToDosError` at `0x18000a13c`
- `ntdll!NtClose` at `0x18000a330`
- `ntdll!NtClose` at `0x18000a330`
- `ntdll!RtlInitUnicodeString` at `0x18000a0cd`
- `ntdll!RtlInitUnicodeString` at `0x18000a0cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a295`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000a28b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000a28b`
- `KERNEL32!LocalFree` at `0x18000a346`
- `KERNEL32!LocalFree` at `0x18000a346`
- `KERNEL32!LocalAlloc` at `0x18000a208`
- `KERNEL32!LocalAlloc` at `0x18000a208`

## pseudocode

```c
__int64 __fastcall DavrGetTheLockOwnerOfTheFile(__int64 a1, _WORD *a2, _QWORD *a3)
{
  _WORD *v4; // rbx
  void *v5; // r15
  unsigned __int64 v6; // rax
  NTSTATUS v7; // eax
  ULONG v8; // eax
  DWORD LastError; // ebx
  DWORD v10; // eax
  _WORD *v11; // rbx
  __int64 v12; // rax
  DWORD v13; // r12d
  HLOCAL v14; // rax
  _WORD *v16; // [rsp+48h] [rbp-90h] BYREF
  _WORD *v17; // [rsp+50h] [rbp-88h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-50h] BYREF
  __int64 v20; // [rsp+98h] [rbp-40h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-38h] BYREF
  DWORD BytesReturned; // [rsp+E8h] [rbp+10h] BYREF
  void *FileHandle; // [rsp+F8h] [rbp+20h] BYREF

  v4 = a2;
  FileHandle = (void *)-1LL;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  v16 = 0;
  BytesReturned = 0;
  v5 = 0;
  v17 = 0;
  if ( !a2 )
    goto LABEL_33;
  if ( !a3 )
    goto LABEL_33;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( v6 < 2 )
  {
LABEL_33:
    LastError = 87;
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 308, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, a2);
  RtlInitUnicodeString(&DestinationString, L"\\Device\\WebDavRedirector");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x10u);
  if ( v7 )
  {
    FileHandle = (void *)-1LL;
    v8 = RtlNtStatusToDosError(v7);
    LastError = v8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 309, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v8);
    goto LABEL_34;
  }
  if ( *v4 != 92 )
  {
    v10 = DavConvertDriveLetterPathToUncPath(v4, &v16);
    LastError = v10;
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 310, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v10);
      goto LABEL_34;
    }
    v4 = v16;
    v5 = v16;
    v17 = v16;
  }
  v11 = v4 + 1;
  v16 = v11;
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  v13 = 2 * v12 + 2;
  v20 = 1026;
  v14 = LocalAlloc(0x40u, 0x402u);
  *a3 = v14;
  if ( v14 )
  {
    if ( DeviceIoControl(FileHandle, 0x140388u, v11, v13, v14, 0x402u, &BytesReturned, 0) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 312, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 311, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
  }
LABEL_34:
  if ( FileHandle != (void *)-1LL )
  {
    NtClose(FileHandle);
    FileHandle = (void *)-1LL;
  }
  if ( v5 )
    LocalFree(v5);
  return LastError;
}

```

## disassembly

```asm
0x18000a010  mov     r11, rsp
0x18000a013  mov     [r11+8], rbx
0x18000a017  push    rsi
0x18000a018  push    rdi
0x18000a019  push    r12
0x18000a01b  push    r13
0x18000a01d  push    r15
0x18000a01f  sub     rsp, 0B0h
0x18000a026  mov     r13, r8
0x18000a029  mov     rbx, rdx
0x18000a02c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a030  mov     [r11+20h], rsi
0x18000a034  xorps   xmm0, xmm0
0x18000a037  movups  xmmword ptr [r11-38h], xmm0
0x18000a03c  xor     eax, eax
0x18000a03e  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.Length], xmm0
0x18000a043  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.ObjectName], xmm0
0x18000a048  movups  xmmword ptr [rsp+0D8h+ObjectAttributes+1Ch], xmm0
0x18000a04d  movups  xmmword ptr [r11-50h], xmm0
0x18000a052  xor     edi, edi
0x18000a054  mov     [rsp+0D8h+var_90], rdi
0x18000a059  mov     [r11+10h], edi
0x18000a05d  mov     r15d, edi
0x18000a060  mov     [rsp+0D8h+var_88], rdi
0x18000a065  test    rdx, rdx
0x18000a068  jz      loc_18000A31E
0x18000a06e  test    r8, r8
0x18000a071  jz      loc_18000A31E
0x18000a077  mov     rax, rsi
0x18000a07a  inc     rax
0x18000a07d  cmp     [rdx+rax*2], di
0x18000a081  jnz     short loc_18000A07A
0x18000a083  cmp     rax, 2
0x18000a087  jb      loc_18000A31E
0x18000a08d  lea     r12, WPP_GLOBAL_Control
0x18000a094  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a09b  cmp     rcx, r12
0x18000a09e  jz      short loc_18000A0BE
0x18000a0a0  test    byte ptr [rcx+1Ch], 2
0x18000a0a4  jz      short loc_18000A0BE
0x18000a0a6  mov     edx, 134h
0x18000a0ab  mov     r9, rbx
0x18000a0ae  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000a0b5  mov     rcx, [rcx+10h]
0x18000a0b9  call    WPP_SF_S
0x18000a0be  lea     rdx, aDeviceWebdavre_1; "\\Device\\WebDavRedirector"
0x18000a0c5  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x18000a0cd  call    cs:__imp_RtlInitUnicodeString
0x18000a0d3  mov     [rsp+0D8h+ObjectAttributes.Length], 30h ; '0'
0x18000a0db  mov     [rsp+0D8h+ObjectAttributes.RootDirectory], rdi
0x18000a0e0  mov     [rsp+0D8h+ObjectAttributes.Attributes], 40h ; '@'
0x18000a0e8  lea     rax, [rsp+0D8h+DestinationString]
0x18000a0f0  mov     [rsp+0D8h+ObjectAttributes.ObjectName], rax
0x18000a0f5  xorps   xmm0, xmm0
0x18000a0f8  movdqu  xmmword ptr [rsp+0D8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a0fe  mov     [rsp+0D8h+OpenOptions], 10h; OpenOptions
0x18000a106  mov     [rsp+0D8h+ShareAccess], 7; ShareAccess
0x18000a10e  lea     r9, [rsp+0D8h+IoStatusBlock]; IoStatusBlock
0x18000a116  lea     r8, [rsp+0D8h+ObjectAttributes]; ObjectAttributes
0x18000a11b  mov     edx, 100000h; DesiredAccess
0x18000a120  lea     rcx, [rsp+0D8h+FileHandle]; FileHandle
0x18000a128  call    cs:__imp_NtOpenFile
0x18000a12e  test    eax, eax
0x18000a130  jz      short loc_18000A17B
0x18000a132  mov     [rsp+0D8h+FileHandle], rsi
0x18000a13a  mov     ecx, eax; Status
0x18000a13c  call    cs:__imp_RtlNtStatusToDosError
0x18000a142  mov     ebx, eax
0x18000a144  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a14b  cmp     rcx, r12
0x18000a14e  jz      loc_18000A323
0x18000a154  test    byte ptr [rcx+1Ch], 1
0x18000a158  jz      loc_18000A323
0x18000a15e  mov     edx, 135h
0x18000a163  mov     r9d, eax
0x18000a166  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000a16d  mov     rcx, [rcx+10h]
0x18000a171  call    WPP_SF_d
0x18000a176  jmp     loc_18000A323
0x18000a17b  cmp     word ptr [rbx], 5Ch ; '\'
0x18000a17f  jz      short loc_18000A1D4
0x18000a181  lea     rdx, [rsp+0D8h+var_90]
0x18000a186  mov     rcx, rbx
0x18000a189  call    DavConvertDriveLetterPathToUncPath
0x18000a18e  mov     ebx, eax
0x18000a190  mov     [rsp+0D8h+var_98], eax
0x18000a194  test    eax, eax
0x18000a196  jz      short loc_18000A1C7
0x18000a198  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a19f  cmp     rcx, r12
0x18000a1a2  jz      short loc_18000A1C2
0x18000a1a4  test    byte ptr [rcx+1Ch], 1
0x18000a1a8  jz      short loc_18000A1C2
0x18000a1aa  mov     edx, 136h
0x18000a1af  mov     r9d, eax
0x18000a1b2  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000a1b9  mov     rcx, [rcx+10h]
0x18000a1bd  call    WPP_SF_d
0x18000a1c2  jmp     loc_18000A323
0x18000a1c7  mov     rbx, [rsp+0D8h+var_90]
0x18000a1cc  mov     r15, rbx
0x18000a1cf  mov     [rsp+0D8h+var_88], rbx
0x18000a1d4  add     rbx, 2
0x18000a1d8  mov     rcx, rbx
0x18000a1db  mov     [rsp+0D8h+var_90], rbx
0x18000a1e0  mov     rax, rsi
0x18000a1e3  inc     rax
0x18000a1e6  cmp     [rcx+rax*2], di
0x18000a1ea  jnz     short loc_18000A1E3
0x18000a1ec  lea     r12d, ds:2[rax*2]
0x18000a1f4  mov     eax, 402h
0x18000a1f9  mov     [rsp+0D8h+var_40], rax
0x18000a201  mov     edx, eax; uBytes
0x18000a203  mov     ecx, 40h ; '@'; uFlags
0x18000a208  call    cs:__imp_LocalAlloc
0x18000a20e  mov     [r13+0], rax
0x18000a212  test    rax, rax
0x18000a215  jnz     short loc_18000A259
0x18000a217  call    cs:__imp_GetLastError
0x18000a21d  mov     ebx, eax
0x18000a21f  mov     [rsp+0D8h+var_98], eax
0x18000a223  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a22a  lea     rax, WPP_GLOBAL_Control
0x18000a231  cmp     rcx, rax
0x18000a234  jz      short loc_18000A254
0x18000a236  test    byte ptr [rcx+1Ch], 1
0x18000a23a  jz      short loc_18000A254
0x18000a23c  mov     edx, 137h
0x18000a241  mov     r9d, ebx
0x18000a244  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000a24b  mov     rcx, [rcx+10h]
0x18000a24f  call    WPP_SF_d
0x18000a254  jmp     loc_18000A323
0x18000a259  mov     [rsp+0D8h+lpOverlapped], rdi; lpOverlapped
0x18000a25e  lea     rcx, [rsp+0D8h+BytesReturned]
0x18000a266  mov     [rsp+0D8h+lpBytesReturned], rcx; lpBytesReturned
0x18000a26b  mov     [rsp+0D8h+OpenOptions], 402h; nOutBufferSize
0x18000a273  mov     qword ptr [rsp+0D8h+ShareAccess], rax; lpOutBuffer
0x18000a278  mov     r9d, r12d; nInBufferSize
0x18000a27b  mov     r8, rbx; lpInBuffer
0x18000a27e  mov     edx, 140388h; dwIoControlCode
0x18000a283  mov     rcx, [rsp+0D8h+FileHandle]; hDevice
0x18000a28b  call    cs:__imp_DeviceIoControl
0x18000a291  test    eax, eax
0x18000a293  jnz     short loc_18000A2D4
0x18000a295  call    cs:__imp_GetLastError
0x18000a29b  mov     ebx, eax
0x18000a29d  mov     [rsp+0D8h+var_98], eax
0x18000a2a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2a8  lea     rax, WPP_GLOBAL_Control
0x18000a2af  cmp     rcx, rax
0x18000a2b2  jz      short loc_18000A2D2
0x18000a2b4  test    byte ptr [rcx+1Ch], 1
0x18000a2b8  jz      short loc_18000A2D2
0x18000a2ba  mov     edx, 138h
0x18000a2bf  mov     r9d, ebx
0x18000a2c2  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000a2c9  mov     rcx, [rcx+10h]
0x18000a2cd  call    WPP_SF_d
0x18000a2d2  jmp     short loc_18000A323
0x18000a2d4  mov     ebx, edi
0x18000a2d6  mov     [rsp+0D8h+var_98], ebx
0x18000a2da  jmp     short loc_18000A323
0x18000a2dc  mov     ebx, eax
0x18000a2de  mov     [rsp+0D8h+var_98], eax
0x18000a2e2  lea     rax, WPP_GLOBAL_Control
0x18000a2e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2f0  cmp     rcx, rax
0x18000a2f3  jz      short loc_18000A313
0x18000a2f5  test    byte ptr [rcx+1Ch], 1
0x18000a2f9  jz      short loc_18000A313
0x18000a2fb  mov     edx, 139h
0x18000a300  mov     r9d, ebx
0x18000a303  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000a30a  mov     rcx, [rcx+10h]
0x18000a30e  call    WPP_SF_d
0x18000a313  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a317  mov     r15, [rsp+0D8h+var_88]
0x18000a31c  jmp     short loc_18000A323
0x18000a31e  mov     ebx, 57h ; 'W'
0x18000a323  mov     rcx, [rsp+0D8h+FileHandle]; Handle
0x18000a32b  cmp     rcx, rsi
0x18000a32e  jz      short loc_18000A33E
0x18000a330  call    cs:__imp_NtClose
0x18000a336  mov     [rsp+0D8h+FileHandle], rsi
0x18000a33e  test    r15, r15
0x18000a341  jz      short loc_18000A34C
0x18000a343  mov     rcx, r15; hMem
0x18000a346  call    cs:__imp_LocalFree
0x18000a34c  mov     eax, ebx
0x18000a34e  mov     rbx, [rsp+0D8h+arg_0]
0x18000a356  add     rsp, 0B0h
0x18000a35d  pop     r15
0x18000a35f  pop     r13
0x18000a361  pop     r12
0x18000a363  pop     rdi
0x18000a364  pop     rsi
0x18000a365  retn
```
