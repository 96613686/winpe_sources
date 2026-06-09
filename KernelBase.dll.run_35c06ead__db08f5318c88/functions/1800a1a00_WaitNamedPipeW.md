# WaitNamedPipeW

- ea: `0x1800a1a00`
- end: `0x1800a1e0e`
- name: `WaitNamedPipeW`
- size: `1038`
- prototype: `BOOL __stdcall(LPCWSTR lpNamedPipeName, DWORD nTimeOut)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a15d0`

## callees

- `0x1800134a0`
- `0x1800a1a00`
- `0x180188eb9`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800a1bfb`
- `ntdll!RtlFreeUnicodeString` at `0x1800a1c90`
- `ntdll!RtlFreeUnicodeString` at `0x1800a1ce1`
- `ntdll!RtlFreeUnicodeString` at `0x1800a1cff`
- `ntdll!RtlFreeUnicodeString` at `0x1800a1d84`
- `ntdll!RtlFreeUnicodeString` at `0x1800a1d9d`
- `ntdll!RtlFreeUnicodeString` at `0x1800a1bfb`
- `ntdll!RtlFreeUnicodeString` at `0x1800a1c90`
- `ntdll!RtlFreeUnicodeString` at `0x1800a1ce1`
- `ntdll!RtlFreeUnicodeString` at `0x1800a1cff`
- `ntdll!RtlFreeUnicodeString` at `0x1800a1d84`
- `ntdll!RtlFreeUnicodeString` at `0x1800a1d9d`
- `ntdll!RtlInitUnicodeString` at `0x1800a1ae1`
- `ntdll!RtlInitUnicodeString` at `0x1800a1b1c`
- `ntdll!RtlInitUnicodeString` at `0x1800a1ae1`
- `ntdll!RtlInitUnicodeString` at `0x1800a1b1c`
- `ntdll!NtOpenFile` at `0x1800a1b62`
- `ntdll!NtOpenFile` at `0x1800a1b62`
- `ntdll!NtFsControlFile` at `0x1800a1c31`
- `ntdll!NtFsControlFile` at `0x1800a1c31`
- `ntdll!_wcsnicmp` at `0x1800a1d1b`
- `ntdll!_wcsnicmp` at `0x1800a1d1b`
- `ntdll!RtlSetLastWin32Error` at `0x1800a1ca5`
- `ntdll!RtlSetLastWin32Error` at `0x1800a1d7a`
- `ntdll!RtlSetLastWin32Error` at `0x1800a1e01`
- `ntdll!RtlSetLastWin32Error` at `0x1800a1ca5`
- `ntdll!RtlSetLastWin32Error` at `0x1800a1d7a`
- `ntdll!RtlSetLastWin32Error` at `0x1800a1e01`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x1800a1ab8`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x1800a1ab8`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800a1dca`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800a1dca`
- `ntdll!NtClose` at `0x1800a1c55`
- `ntdll!NtClose` at `0x1800a1c9a`
- `ntdll!NtClose` at `0x1800a1c55`
- `ntdll!NtClose` at `0x1800a1c9a`
- `ntdll!RtlCreateUnicodeString` at `0x1800a1a54`
- `ntdll!RtlCreateUnicodeString` at `0x1800a1a54`
- `ntdll!RtlFreeHeap` at `0x1800a1b81`
- `ntdll!RtlFreeHeap` at `0x1800a1c4b`
- `ntdll!RtlFreeHeap` at `0x1800a1b81`
- `ntdll!RtlFreeHeap` at `0x1800a1c4b`
- `ntdll!RtlPrefixString` at `0x1800a1af2`
- `ntdll!RtlPrefixString` at `0x1800a1af2`
- `ntdll!RtlAllocateHeap` at `0x1800a1bac`
- `ntdll!RtlAllocateHeap` at `0x1800a1d63`
- `ntdll!RtlAllocateHeap` at `0x1800a1bac`
- `ntdll!RtlAllocateHeap` at `0x1800a1d63`

## pseudocode

```c
BOOL __stdcall WaitNamedPipeW(LPCWSTR lpNamedPipeName, DWORD nTimeOut)
{
  __int64 v2; // rsi
  USHORT Length; // r8
  unsigned int v5; // eax
  __int32 v6; // eax
  const WCHAR *v7; // rdx
  struct _UNICODE_STRING *p_String2; // rcx
  WCHAR *v9; // rbx
  NTSTATUS v10; // edi
  ULONG InputBufferLength; // edi
  _DWORD *v12; // rax
  _DWORD *InputBuffer; // rbx
  char v14; // al
  __int64 v15; // rcx
  PCHAR v17; // rbx
  __int16 i; // ax
  PCHAR v19; // rdi
  USHORT v20; // cx
  WCHAR *Heap; // rax
  STRING String2; // [rsp+50h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-39h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+70h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-19h] BYREF
  struct _UNICODE_STRING v26; // [rsp+B0h] [rbp+17h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp+27h] BYREF
  struct _IO_STATUS_BLOCK v28; // [rsp+D0h] [rbp+37h] BYREF
  HANDLE FileHandle; // [rsp+110h] [rbp+77h] BYREF

  v2 = nTimeOut;
  FileHandle = 0;
  v28 = 0;
  memset(&ObjectAttributes, 0, 44);
  Destination = 0;
  String2 = 0;
  DestinationString = 0;
  v26 = 0;
  IoStatusBlock = 0;
  if ( !RtlCreateUnicodeString(&DestinationString, lpNamedPipeName) )
  {
    RtlSetLastWin32Error(8u);
    return 0;
  }
  Length = DestinationString.Length;
  v5 = 0;
  if ( (DestinationString.Length & 0xFFFE) != 0 )
  {
    do
    {
      if ( DestinationString.Buffer[v5] == 47 )
      {
        DestinationString.Buffer[v5] = 92;
        Length = DestinationString.Length;
      }
      ++v5;
    }
    while ( v5 < Length >> 1 );
  }
  String2 = (STRING)DestinationString;
  v6 = RtlDetermineDosPathNameType_U(lpNamedPipeName) - 1;
  if ( !v6 )
  {
    v17 = String2.Buffer + 4;
    for ( i = *((_WORD *)String2.Buffer + 2); i; v17 += 2 )
    {
      if ( i == 92 )
        break;
      i = *((_WORD *)v17 + 1);
    }
    if ( *(_WORD *)v17 && !_wcsnicmp((const wchar_t *)v17 + 1, L"pipe\\", 5u) )
    {
      v19 = v17 + 10;
      v20 = (_WORD)v17 + 10 - (LOWORD(String2.Buffer) + 4);
      String2.Buffer += 4;
      String2.Length = v20;
      String2.MaximumLength = v20;
      Destination.MaximumLength = v20 + 34;
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, (unsigned __int16)(v20 + 34));
      Destination.Buffer = Heap;
      v9 = Heap;
      if ( !Heap )
      {
        RtlSetLastWin32Error(8u);
        RtlFreeUnicodeString(&DestinationString);
        return 0;
      }
      *(_OWORD *)Heap = *(_OWORD *)L"\\DosDevices\\UNC\\";
      *((_OWORD *)Heap + 1) = *(_OWORD *)L"ces\\UNC\\";
      Destination.Length = 32;
      RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)&String2);
      v7 = (const WCHAR *)(v19 + 2);
      p_String2 = (struct _UNICODE_STRING *)&String2;
      goto LABEL_10;
    }
LABEL_27:
    RtlFreeUnicodeString(&DestinationString);
    v15 = 3221225531LL;
    goto LABEL_20;
  }
  if ( v6 != 5 )
  {
    BaseSetLastNTError(3221225531LL);
    RtlFreeUnicodeString(&DestinationString);
    return 0;
  }
  RtlInitUnicodeString(&v26, L"\\\\.\\pipe\\");
  if ( !RtlPrefixString((const STRING *)&v26, &String2, 1u) )
    goto LABEL_27;
  String2.Buffer += 18;
  v7 = L"\\DosDevices\\pipe\\";
  p_String2 = &Destination;
  String2.Length -= 18;
  v9 = 0;
LABEL_10:
  RtlInitUnicodeString(p_String2, v7);
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  if ( v10 < 0 )
  {
    RtlFreeUnicodeString(&DestinationString);
LABEL_19:
    v15 = (unsigned int)v10;
LABEL_20:
    BaseSetLastNTError(v15);
    return 0;
  }
  InputBufferLength = String2.Length + 14;
  v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, InputBufferLength);
  InputBuffer = v12;
  if ( !v12 )
  {
    RtlFreeUnicodeString(&DestinationString);
    NtClose(FileHandle);
    RtlSetLastWin32Error(8u);
    return 0;
  }
  if ( (_DWORD)v2 )
  {
    if ( (_DWORD)v2 == -1 )
    {
      *v12 = 0;
      v12[1] = 0x80000000;
    }
    else
    {
      *(_QWORD *)v12 = -10000 * v2;
    }
    v14 = 1;
  }
  else
  {
    *(_QWORD *)v12 = 0;
    v14 = 0;
  }
  *((_BYTE *)InputBuffer + 12) = v14;
  InputBuffer[2] = String2.Length;
  memcpy_0((char *)InputBuffer + 14, String2.Buffer, String2.Length);
  RtlFreeUnicodeString(&DestinationString);
  v10 = NtFsControlFile(FileHandle, 0, 0, 0, &v28, 0x110018u, InputBuffer, InputBufferLength, 0, 0);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, InputBuffer);
  NtClose(FileHandle);
  if ( v10 < 0 )
    goto LABEL_19;
  return 1;
}

```

## disassembly

```asm
0x1800a1a00  mov     [rsp-8+arg_18], rbx
0x1800a1a05  push    rbp
0x1800a1a06  push    rsi
0x1800a1a07  push    r15
0x1800a1a09  lea     rbp, [rsp-47h]
0x1800a1a0e  sub     rsp, 0E0h
0x1800a1a15  xorps   xmm0, xmm0
0x1800a1a18  mov     esi, edx
0x1800a1a1a  xorps   xmm1, xmm1
0x1800a1a1d  mov     rdx, rcx; SourceString
0x1800a1a20  mov     rbx, rcx
0x1800a1a23  xor     r15d, r15d
0x1800a1a26  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800a1a2a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800a1a2e  mov     [rbp+57h+FileHandle], r15
0x1800a1a32  xor     eax, eax
0x1800a1a34  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800a1a38  movups  xmmword ptr [rbp+57h+var_20], xmm0
0x1800a1a3c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800a1a40  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x1800a1a44  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x1800a1a48  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800a1a4c  movups  xmmword ptr [rbp+57h+var_40.Length], xmm1
0x1800a1a50  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800a1a54  call    cs:__imp_RtlCreateUnicodeString
0x1800a1a5a  test    al, al
0x1800a1a5c  jz      loc_1800A1DFC
0x1800a1a62  movzx   r8d, [rbp+57h+DestinationString.Length]
0x1800a1a67  mov     eax, r15d
0x1800a1a6a  mov     [rsp+0F0h+arg_8], r14
0x1800a1a72  test    r8d, 0FFFFFFFEh
0x1800a1a79  jbe     short loc_1800A1AA4
0x1800a1a7b  nop     dword ptr [rax+rax+00h]
0x1800a1a80  mov     rcx, [rbp+57h+DestinationString.Buffer]
0x1800a1a84  mov     edx, eax
0x1800a1a86  cmp     word ptr [rcx+rdx*2], 2Fh ; '/'
0x1800a1a8b  jnz     short loc_1800A1A98
0x1800a1a8d  mov     word ptr [rcx+rdx*2], 5Ch ; '\'
0x1800a1a93  movzx   r8d, [rbp+57h+DestinationString.Length]
0x1800a1a98  movzx   ecx, r8w
0x1800a1a9c  inc     eax
0x1800a1a9e  shr     ecx, 1
0x1800a1aa0  cmp     eax, ecx
0x1800a1aa2  jb      short loc_1800A1A80
0x1800a1aa4  movaps  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x1800a1aa8  mov     rcx, rbx; Path
0x1800a1aab  movdqa  xmmword ptr [rbp+57h+String2.Length], xmm0
0x1800a1ab0  mov     [rsp+0F0h+arg_0], rdi
0x1800a1ab8  call    cs:__imp_RtlDetermineDosPathNameType_U
0x1800a1abe  mov     r14d, 20h ; ' '
0x1800a1ac4  sub     eax, 1
0x1800a1ac7  jz      loc_1800A1CC3
0x1800a1acd  cmp     eax, 5
0x1800a1ad0  jnz     loc_1800A1CF1
0x1800a1ad6  lea     rdx, aPipe; "\\\\.\\pipe\\"
0x1800a1add  lea     rcx, [rbp+57h+var_40]; DestinationString
0x1800a1ae1  call    cs:__imp_RtlInitUnicodeString
0x1800a1ae7  mov     r8b, 1; CaseInsensitive
0x1800a1aea  lea     rdx, [rbp+57h+String2]; String2
0x1800a1aee  lea     rcx, [rbp+57h+var_40]; String1
0x1800a1af2  call    cs:__imp_RtlPrefixString
0x1800a1af8  test    al, al
0x1800a1afa  jz      loc_1800A1CDD
0x1800a1b00  add     [rbp+57h+String2.Buffer], 12h
0x1800a1b05  lea     rdx, aDosdevicesPipe; "\\DosDevices\\pipe\\"
0x1800a1b0c  mov     eax, 0FFEEh
0x1800a1b11  lea     rcx, [rbp+57h+Destination]; DestinationString
0x1800a1b15  add     [rbp+57h+String2.Length], ax
0x1800a1b19  mov     rbx, r15
0x1800a1b1c  call    cs:__imp_RtlInitUnicodeString
0x1800a1b22  lea     rax, [rbp+57h+Destination]
0x1800a1b26  mov     [rsp+0F0h+OpenOptions], r14d; OpenOptions
0x1800a1b2b  xorps   xmm0, xmm0
0x1800a1b2e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800a1b32  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800a1b36  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800a1b3d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800a1b41  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1800a1b45  mov     edx, 100080h; DesiredAccess
0x1800a1b4a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800a1b51  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a1b55  mov     [rsp+0F0h+ShareAccess], 3; ShareAccess
0x1800a1b5d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a1b62  call    cs:__imp_NtOpenFile
0x1800a1b68  mov     edi, eax
0x1800a1b6a  test    rbx, rbx
0x1800a1b6d  jz      short loc_1800A1B87
0x1800a1b6f  mov     rcx, gs:60h
0x1800a1b78  mov     r8, rbx; P
0x1800a1b7b  xor     edx, edx; Flags
0x1800a1b7d  mov     rcx, [rcx+30h]; HeapHandle
0x1800a1b81  call    cs:__imp_RtlFreeHeap
0x1800a1b87  test    edi, edi
0x1800a1b89  js      loc_1800A1D99
0x1800a1b8f  mov     rcx, gs:60h
0x1800a1b98  movzx   edi, [rbp+57h+String2.Length]
0x1800a1b9c  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800a1ba2  add     edi, 0Eh
0x1800a1ba5  mov     r8d, edi; Size
0x1800a1ba8  mov     rcx, [rcx+30h]; HeapHandle
0x1800a1bac  call    cs:__imp_RtlAllocateHeap
0x1800a1bb2  mov     rbx, rax
0x1800a1bb5  test    rax, rax
0x1800a1bb8  jz      loc_1800A1C8C
0x1800a1bbe  test    esi, esi
0x1800a1bc0  jz      loc_1800A1D8F
0x1800a1bc6  cmp     esi, 0FFFFFFFFh
0x1800a1bc9  jz      loc_1800A1CB4
0x1800a1bcf  imul    rcx, rsi, 0FFFFFFFFFFFFD8F0h
0x1800a1bd6  mov     [rax], rcx
0x1800a1bd9  mov     al, 1
0x1800a1bdb  mov     [rbx+0Ch], al
0x1800a1bde  lea     rcx, [rbx+0Eh]; void *
0x1800a1be2  movzx   eax, [rbp+57h+String2.Length]
0x1800a1be6  mov     [rbx+8], eax
0x1800a1be9  movzx   r8d, [rbp+57h+String2.Length]; Size
0x1800a1bee  mov     rdx, [rbp+57h+String2.Buffer]; Src
0x1800a1bf2  call    memcpy_0
0x1800a1bf7  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800a1bfb  call    cs:__imp_RtlFreeUnicodeString
0x1800a1c01  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a1c05  lea     rax, [rbp+57h+var_20]
0x1800a1c09  mov     [rsp+0F0h+OutputBufferLength], r15d; OutputBufferLength
0x1800a1c0e  xor     r9d, r9d; ApcContext
0x1800a1c11  mov     [rsp+0F0h+OutputBuffer], r15; OutputBuffer
0x1800a1c16  xor     r8d, r8d; ApcRoutine
0x1800a1c19  mov     [rsp+0F0h+InputBufferLength], edi; InputBufferLength
0x1800a1c1d  xor     edx, edx; Event
0x1800a1c1f  mov     [rsp+0F0h+InputBuffer], rbx; InputBuffer
0x1800a1c24  mov     [rsp+0F0h+OpenOptions], 110018h; FsControlCode
0x1800a1c2c  mov     qword ptr [rsp+0F0h+ShareAccess], rax; IoStatusBlock
0x1800a1c31  call    cs:__imp_NtFsControlFile
0x1800a1c37  mov     rcx, gs:60h
0x1800a1c40  mov     r8, rbx; P
0x1800a1c43  xor     edx, edx; Flags
0x1800a1c45  mov     edi, eax
0x1800a1c47  mov     rcx, [rcx+30h]; HeapHandle
0x1800a1c4b  call    cs:__imp_RtlFreeHeap
0x1800a1c51  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800a1c55  call    cs:__imp_NtClose
0x1800a1c5b  test    edi, edi
0x1800a1c5d  jns     short loc_1800A1CAD
0x1800a1c5f  mov     ecx, edi
0x1800a1c61  call    BaseSetLastNTError
0x1800a1c66  xor     eax, eax
0x1800a1c68  mov     rdi, [rsp+0F0h+arg_0]
0x1800a1c70  mov     r14, [rsp+0F0h+arg_8]
0x1800a1c78  mov     rbx, [rsp+0F0h+arg_18]
0x1800a1c80  add     rsp, 0E0h
0x1800a1c87  pop     r15
0x1800a1c89  pop     rsi
0x1800a1c8a  pop     rbp
0x1800a1c8b  retn
0x1800a1c8c  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800a1c90  call    cs:__imp_RtlFreeUnicodeString
0x1800a1c96  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800a1c9a  call    cs:__imp_NtClose
0x1800a1ca0  mov     ecx, 8; LastError
0x1800a1ca5  call    cs:__imp_RtlSetLastWin32Error
0x1800a1cab  jmp     short loc_1800A1C66
0x1800a1cad  mov     eax, 1
0x1800a1cb2  jmp     short loc_1800A1C68
0x1800a1cb4  mov     [rax], r15d
0x1800a1cb7  mov     dword ptr [rax+4], 80000000h
0x1800a1cbe  jmp     loc_1800A1BD9
0x1800a1cc3  mov     rbx, [rbp+57h+String2.Buffer]
0x1800a1cc7  add     rbx, 4
0x1800a1ccb  movzx   eax, word ptr [rbx]
0x1800a1cce  test    ax, ax
0x1800a1cd1  jnz     loc_1800A1DE0
0x1800a1cd7  cmp     [rbx], r15w
0x1800a1cdb  jnz     short loc_1800A1D0A
0x1800a1cdd  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800a1ce1  call    cs:__imp_RtlFreeUnicodeString
0x1800a1ce7  mov     ecx, 0C000003Bh
0x1800a1cec  jmp     loc_1800A1C61
0x1800a1cf1  mov     ecx, 0C000003Bh
0x1800a1cf6  call    BaseSetLastNTError
0x1800a1cfb  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800a1cff  call    cs:__imp_RtlFreeUnicodeString
0x1800a1d05  jmp     loc_1800A1C66
0x1800a1d0a  lea     rcx, [rbx+2]; String1
0x1800a1d0e  mov     r8d, 5; MaxCount
0x1800a1d14  lea     rdx, aPipe_0; "pipe\\"
0x1800a1d1b  call    cs:__imp__wcsnicmp
0x1800a1d21  test    eax, eax
0x1800a1d23  jnz     short loc_1800A1CDD
0x1800a1d25  mov     rax, [rbp+57h+String2.Buffer]
0x1800a1d29  lea     rdi, [rbx+0Ah]
0x1800a1d2d  add     rax, 4
0x1800a1d31  movzx   ecx, di
0x1800a1d34  sub     cx, ax
0x1800a1d37  mov     [rbp+57h+String2.Buffer], rax
0x1800a1d3b  mov     [rbp+57h+String2.Length], cx
0x1800a1d3f  mov     [rbp+57h+String2.MaximumLength], cx
0x1800a1d43  add     cx, 22h ; '"'
0x1800a1d47  movzx   r8d, cx; Size
0x1800a1d4b  mov     [rbp+57h+Destination.MaximumLength], r8w
0x1800a1d50  mov     rcx, gs:60h
0x1800a1d59  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800a1d5f  mov     rcx, [rcx+30h]; HeapHandle
0x1800a1d63  call    cs:__imp_RtlAllocateHeap
0x1800a1d69  mov     [rbp+57h+Destination.Buffer], rax
0x1800a1d6d  mov     rbx, rax
0x1800a1d70  test    rax, rax
0x1800a1d73  jnz     short loc_1800A1DA8
0x1800a1d75  mov     ecx, 8; LastError
0x1800a1d7a  call    cs:__imp_RtlSetLastWin32Error
0x1800a1d80  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800a1d84  call    cs:__imp_RtlFreeUnicodeString
0x1800a1d8a  jmp     loc_1800A1C66
0x1800a1d8f  mov     [rax], r15
0x1800a1d92  xor     al, al
0x1800a1d94  jmp     loc_1800A1BDB
0x1800a1d99  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800a1d9d  call    cs:__imp_RtlFreeUnicodeString
0x1800a1da3  jmp     loc_1800A1C5F
0x1800a1da8  movups  xmm0, xmmword ptr cs:aDosdevicesUnc; "\\DosDevices\\UNC\\"
0x1800a1daf  lea     rdx, [rbp+57h+String2]; Source
0x1800a1db3  lea     rcx, [rbp+57h+Destination]; Destination
0x1800a1db7  movups  xmmword ptr [rax], xmm0
0x1800a1dba  movups  xmm1, xmmword ptr cs:aDosdevicesUnc+10h; "ces\\UNC\\"
0x1800a1dc1  movups  xmmword ptr [rax+10h], xmm1
0x1800a1dc5  mov     [rbp+57h+Destination.Length], r14w
0x1800a1dca  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800a1dd0  lea     rdx, [rdi+2]
0x1800a1dd4  lea     rcx, [rbp+57h+String2]
0x1800a1dd8  jmp     loc_1800A1B1C
0x1800a1de0  cmp     ax, 5Ch ; '\'
0x1800a1de4  jz      loc_1800A1CD7
0x1800a1dea  movzx   eax, word ptr [rbx+2]
0x1800a1dee  add     rbx, 2
0x1800a1df2  test    ax, ax
0x1800a1df5  jnz     short loc_1800A1DE0
0x1800a1df7  jmp     loc_1800A1CD7
0x1800a1dfc  mov     ecx, 8; LastError
0x1800a1e01  call    cs:__imp_RtlSetLastWin32Error
0x1800a1e07  xor     eax, eax
0x1800a1e09  jmp     loc_1800A1C78
```
