# IsTerminalFolderRedirection(ushort *,bool *)

- ea: `0x18000c890`
- end: `0x18000cccf`
- name: `?IsTerminalFolderRedirection@@YAJPEAGPEA_N@Z`
- size: `1087`
- prototype: `__int64 __fastcall(unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b020`
- `0x18000bc10`

## callees

- `0x180006260`
- `0x180009f60`
- `0x18000c890`
- `0x180034070`
- `0x180034e83`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18000c902`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18000c902`
- `ntdll!NtOpenFile` at `0x18000c959`
- `ntdll!NtOpenFile` at `0x18000c959`
- `ntdll!NtQueryInformationFile` at `0x18000c987`
- `ntdll!NtQueryInformationFile` at `0x18000c987`
- `ntdll!NtClose` at `0x18000ca45`
- `ntdll!NtClose` at `0x18000cb16`
- `ntdll!NtClose` at `0x18000ca45`
- `ntdll!NtClose` at `0x18000cb16`

## pseudocode

```c
__int64 __fastcall IsTerminalFolderRedirection(unsigned __int16 *a1, bool *a2)
{
  unsigned int v2; // ebx
  NTSTATUS v5; // eax
  int v6; // eax
  int v7; // eax
  signed int v8; // eax
  PVOID *v9; // rcx
  __int64 v10; // rdx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  signed int v14; // eax
  signed int v15; // eax
  void *FileHandle; // [rsp+30h] [rbp-29h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-21h] BYREF
  __int64 FileInformation; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v19; // [rsp+70h] [rbp+17h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+27h] BYREF

  FileHandle = (void *)-1LL;
  v2 = 0;
  FileInformation = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v19 = 0;
  if ( !a1 )
  {
    v2 = -2147024809;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v2;
    v10 = 10;
    goto LABEL_14;
  }
  if ( !a2 )
  {
    v2 = -2147467261;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v2;
    v10 = 11;
LABEL_14:
    WPP_SF_d(v9[2], v10, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v2);
    goto LABEL_15;
  }
  *a2 = 1;
  v5 = RtlDosPathNameToNtPathName_U_WithStatus(a1, &v19, 0, 0);
  if ( v5 < 0 )
  {
    v15 = RtlNtStatusToDosError_0(v5);
    v2 = v15;
    if ( v15 > 0 )
      v2 = (unsigned __int16)v15 | 0x80070000;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_15;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v2);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 0x40) == 0 )
      goto LABEL_15;
    v10 = 13;
    goto LABEL_14;
  }
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v19;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = NtOpenFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 1u, 0x200000u);
  if ( v6 < 0 )
  {
    v14 = RtlNtStatusToDosError_0(v6);
    v2 = v14;
    if ( v14 > 0 )
      v2 = (unsigned __int16)v14 | 0x80070000;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_15;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v2);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 0x40) == 0 )
      goto LABEL_15;
    v10 = 15;
    goto LABEL_14;
  }
  v7 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 8u, FileAttributeTagInformation);
  if ( v7 < 0 )
  {
    v8 = RtlNtStatusToDosError_0(v7);
    v2 = v8;
    if ( v8 > 0 )
      v2 = (unsigned __int16)v8 | 0x80070000;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_15;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v2);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 0x40) == 0 )
      goto LABEL_15;
    v10 = 17;
    goto LABEL_14;
  }
  if ( NtClose(FileHandle) >= 0 )
    FileHandle = (void *)-1LL;
  if ( (FileInformation & 0x10) == 0 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, a1);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v2 = -2147024809;
    if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 0x40) == 0 )
      goto LABEL_15;
    v10 = 19;
    goto LABEL_14;
  }
  if ( (FileInformation & 0x400) != 0 )
  {
    if ( (FileInformation & 0x2000000000000000LL) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, a1);
      goto LABEL_15;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_26;
    v13 = 21;
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_26;
    v13 = 20;
  }
  WPP_SF_S(v12[2], v13, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, a1);
LABEL_26:
  *a2 = 0;
LABEL_15:
  if ( FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  return v2;
}

```

## disassembly

```asm
0x18000c890  mov     [rsp-8+arg_10], rbx
0x18000c895  mov     [rsp-8+arg_18], rsi
0x18000c89a  push    rbp
0x18000c89b  push    rdi
0x18000c89c  push    r14
0x18000c89e  lea     rbp, [rsp-47h]
0x18000c8a3  sub     rsp, 0A0h
0x18000c8aa  mov     rax, cs:__security_cookie
0x18000c8b1  xor     rax, rsp
0x18000c8b4  mov     [rbp+57h+var_20], rax
0x18000c8b8  xorps   xmm0, xmm0
0x18000c8bb  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18000c8c3  xor     ebx, ebx
0x18000c8c5  mov     rdi, rdx
0x18000c8c8  mov     [rbp+57h+FileInformation], rbx
0x18000c8cc  mov     rsi, rcx
0x18000c8cf  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000c8d3  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000c8d7  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000c8db  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000c8df  movups  [rbp+57h+var_40], xmm0
0x18000c8e3  test    rcx, rcx
0x18000c8e6  jz      loc_18000CB96
0x18000c8ec  test    rdx, rdx
0x18000c8ef  jz      loc_18000CBC6
0x18000c8f5  mov     byte ptr [rdx], 1
0x18000c8f8  xor     r9d, r9d
0x18000c8fb  lea     rdx, [rbp+57h+var_40]
0x18000c8ff  xor     r8d, r8d
0x18000c902  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18000c909  nop     dword ptr [rax+rax+00h]
0x18000c90e  test    eax, eax
0x18000c910  js      loc_18000CB27
0x18000c916  lea     rax, [rbp+57h+var_40]
0x18000c91a  mov     [rsp+0B0h+OpenOptions], 200000h; OpenOptions
0x18000c922  xorps   xmm0, xmm0
0x18000c925  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000c929  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000c92d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000c934  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000c938  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x18000c93c  mov     edx, 80h; DesiredAccess
0x18000c941  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000c948  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000c94c  mov     [rsp+0B0h+ShareAccess], 1; ShareAccess
0x18000c954  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000c959  call    cs:__imp_NtOpenFile
0x18000c960  nop     dword ptr [rax+rax+00h]
0x18000c965  test    eax, eax
0x18000c967  js      loc_18000CAA7
0x18000c96d  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000c971  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18000c975  mov     r9d, 8; Length
0x18000c97b  mov     [rsp+0B0h+ShareAccess], 23h ; '#'; FileInformationClass
0x18000c983  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000c987  call    cs:__imp_NtQueryInformationFile
0x18000c98e  nop     dword ptr [rax+rax+00h]
0x18000c993  test    eax, eax
0x18000c995  jns     loc_18000CA41
0x18000c99b  mov     ecx, eax; Status
0x18000c99d  call    RtlNtStatusToDosError_0
0x18000c9a2  mov     ebx, eax
0x18000c9a4  test    eax, eax
0x18000c9a6  jle     short loc_18000C9B1
0x18000c9a8  movzx   ebx, ax
0x18000c9ab  or      ebx, 80070000h
0x18000c9b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9b8  lea     r14, WPP_GLOBAL_Control
0x18000c9bf  cmp     rcx, r14
0x18000c9c2  jz      short loc_18000CA0C
0x18000c9c4  test    byte ptr [rcx+1Ch], 2
0x18000c9c8  jz      short loc_18000C9E9
0x18000c9ca  mov     rcx, [rcx+10h]
0x18000c9ce  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x18000c9d5  mov     edx, 10h
0x18000c9da  mov     r9d, ebx
0x18000c9dd  call    WPP_SF_d
0x18000c9e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9e9  cmp     rcx, r14
0x18000c9ec  jz      short loc_18000CA0C
0x18000c9ee  test    byte ptr [rcx+1Ch], 40h
0x18000c9f2  jz      short loc_18000CA0C
0x18000c9f4  mov     edx, 11h
0x18000c9f9  mov     rcx, [rcx+10h]
0x18000c9fd  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x18000ca04  mov     r9d, ebx
0x18000ca07  call    WPP_SF_d
0x18000ca0c  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18000ca10  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ca14  jnz     loc_18000CB16
0x18000ca1a  mov     eax, ebx
0x18000ca1c  mov     rcx, [rbp+57h+var_20]
0x18000ca20  xor     rcx, rsp; StackCookie
0x18000ca23  call    __security_check_cookie
0x18000ca28  lea     r11, [rsp+0B0h+var_10]
0x18000ca30  mov     rbx, [r11+30h]
0x18000ca34  mov     rsi, [r11+38h]
0x18000ca38  mov     rsp, r11
0x18000ca3b  pop     r14
0x18000ca3d  pop     rdi
0x18000ca3e  pop     rbp
0x18000ca3f  retn
0x18000ca41  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18000ca45  call    cs:__imp_NtClose
0x18000ca4c  nop     dword ptr [rax+rax+00h]
0x18000ca51  test    eax, eax
0x18000ca53  jns     loc_18000CBF6
0x18000ca59  mov     rax, [rbp+57h+FileInformation]
0x18000ca5d  test    al, 10h
0x18000ca5f  jz      loc_18000CC03
0x18000ca65  bt      eax, 0Ah
0x18000ca69  jb      loc_18000CC5D
0x18000ca6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca76  lea     r14, WPP_GLOBAL_Control
0x18000ca7d  cmp     rcx, r14
0x18000ca80  jz      short loc_18000CAA0
0x18000ca82  test    byte ptr [rcx+1Ch], 8
0x18000ca86  jz      short loc_18000CAA0
0x18000ca88  mov     edx, 14h
0x18000ca8d  mov     rcx, [rcx+10h]
0x18000ca91  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x18000ca98  mov     r9, rsi
0x18000ca9b  call    WPP_SF_S
0x18000caa0  mov     [rdi], bl
0x18000caa2  jmp     loc_18000CA0C
0x18000caa7  mov     ecx, eax; Status
0x18000caa9  call    RtlNtStatusToDosError_0
0x18000caae  mov     ebx, eax
0x18000cab0  test    eax, eax
0x18000cab2  jle     short loc_18000CABD
0x18000cab4  movzx   ebx, ax
0x18000cab7  or      ebx, 80070000h
0x18000cabd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cac4  lea     r14, WPP_GLOBAL_Control
0x18000cacb  cmp     rcx, r14
0x18000cace  jz      loc_18000CA0C
0x18000cad4  test    byte ptr [rcx+1Ch], 2
0x18000cad8  jz      short loc_18000CAF9
0x18000cada  mov     rcx, [rcx+10h]
0x18000cade  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x18000cae5  mov     edx, 0Eh
0x18000caea  mov     r9d, ebx
0x18000caed  call    WPP_SF_d
0x18000caf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000caf9  cmp     rcx, r14
0x18000cafc  jz      loc_18000CA0C
0x18000cb02  test    byte ptr [rcx+1Ch], 40h
0x18000cb06  jz      loc_18000CA0C
0x18000cb0c  mov     edx, 0Fh
0x18000cb11  jmp     loc_18000C9F9
0x18000cb16  call    cs:__imp_NtClose
0x18000cb1d  nop     dword ptr [rax+rax+00h]
0x18000cb22  jmp     loc_18000CA1A
0x18000cb27  mov     ecx, eax; Status
0x18000cb29  call    RtlNtStatusToDosError_0
0x18000cb2e  mov     ebx, eax
0x18000cb30  test    eax, eax
0x18000cb32  jle     short loc_18000CB3D
0x18000cb34  movzx   ebx, ax
0x18000cb37  or      ebx, 80070000h
0x18000cb3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb44  lea     r14, WPP_GLOBAL_Control
0x18000cb4b  cmp     rcx, r14
0x18000cb4e  jz      loc_18000CA0C
0x18000cb54  test    byte ptr [rcx+1Ch], 2
0x18000cb58  jz      short loc_18000CB79
0x18000cb5a  mov     rcx, [rcx+10h]
0x18000cb5e  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x18000cb65  mov     edx, 0Ch
0x18000cb6a  mov     r9d, ebx
0x18000cb6d  call    WPP_SF_d
0x18000cb72  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb79  cmp     rcx, r14
0x18000cb7c  jz      loc_18000CA0C
0x18000cb82  test    byte ptr [rcx+1Ch], 40h
0x18000cb86  jz      loc_18000CA0C
0x18000cb8c  mov     edx, 0Dh
0x18000cb91  jmp     loc_18000C9F9
0x18000cb96  mov     ebx, 80070057h
0x18000cb9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cba2  lea     r14, WPP_GLOBAL_Control
0x18000cba9  cmp     rcx, r14
0x18000cbac  jz      loc_18000CA1A
0x18000cbb2  test    byte ptr [rcx+1Ch], 40h
0x18000cbb6  jz      loc_18000CA1A
0x18000cbbc  mov     edx, 0Ah
0x18000cbc1  jmp     loc_18000C9F9
0x18000cbc6  mov     ebx, 80004003h
0x18000cbcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbd2  lea     r14, WPP_GLOBAL_Control
0x18000cbd9  cmp     rcx, r14
0x18000cbdc  jz      loc_18000CA1A
0x18000cbe2  test    byte ptr [rcx+1Ch], 40h
0x18000cbe6  jz      loc_18000CA1A
0x18000cbec  mov     edx, 0Bh
0x18000cbf1  jmp     loc_18000C9F9
0x18000cbf6  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18000cbfe  jmp     loc_18000CA59
0x18000cc03  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc0a  lea     r14, WPP_GLOBAL_Control
0x18000cc11  cmp     rcx, r14
0x18000cc14  jz      short loc_18000CC3B
0x18000cc16  test    byte ptr [rcx+1Ch], 2
0x18000cc1a  jz      short loc_18000CC3B
0x18000cc1c  mov     rcx, [rcx+10h]
0x18000cc20  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x18000cc27  mov     edx, 12h
0x18000cc2c  mov     r9, rsi
0x18000cc2f  call    WPP_SF_S
0x18000cc34  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc3b  mov     ebx, 80070057h
0x18000cc40  cmp     rcx, r14
0x18000cc43  jz      loc_18000CA0C
0x18000cc49  test    byte ptr [rcx+1Ch], 40h
0x18000cc4d  jz      loc_18000CA0C
0x18000cc53  mov     edx, 13h
0x18000cc58  jmp     loc_18000C9F9
0x18000cc5d  test    dword ptr [rbp+57h+FileInformation+4], 20000000h
0x18000cc64  jnz     short loc_18000CC91
0x18000cc66  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc6d  lea     r14, WPP_GLOBAL_Control
0x18000cc74  cmp     rcx, r14
0x18000cc77  jz      loc_18000CAA0
0x18000cc7d  test    byte ptr [rcx+1Ch], 8
0x18000cc81  jz      loc_18000CAA0
0x18000cc87  mov     edx, 15h
0x18000cc8c  jmp     loc_18000CA8D
0x18000cc91  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc98  lea     r14, WPP_GLOBAL_Control
0x18000cc9f  cmp     rcx, r14
0x18000cca2  jz      loc_18000CA0C
0x18000cca8  test    byte ptr [rcx+1Ch], 8
0x18000ccac  jz      loc_18000CA0C
0x18000ccb2  mov     rcx, [rcx+10h]
0x18000ccb6  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x18000ccbd  mov     edx, 16h
0x18000ccc2  mov     r9, rsi
0x18000ccc5  call    WPP_SF_S
0x18000ccca  jmp     loc_18000CA0C
```
