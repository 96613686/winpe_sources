# PrivCopyFileExW

- ea: `0x1800efb50`
- end: `0x1800eff85`
- name: `PrivCopyFileExW`
- size: `1077`
- prototype: `__int64 __usercall@<rax>(PCWSTR DosPathName@<rcx>, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800134a0`
- `0x180048f30`
- `0x1800efb50`
- `0x1800f0120`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800eff1a`
- `ntdll!RtlFreeUnicodeString` at `0x18018c4cd`
- `ntdll!RtlFreeUnicodeString` at `0x1800eff1a`
- `ntdll!RtlFreeUnicodeString` at `0x18018c4cd`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800efc7f`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800efc7f`
- `ntdll!NtFsControlFile` at `0x1800efde0`
- `ntdll!NtFsControlFile` at `0x1800efde0`
- `ntdll!NtCreateFile` at `0x1800efd12`
- `ntdll!NtCreateFile` at `0x1800efd12`
- `ntdll!RtlSetLastWin32Error` at `0x1800efe9f`
- `ntdll!RtlSetLastWin32Error` at `0x1800eff55`
- `ntdll!RtlSetLastWin32Error` at `0x1800efe9f`
- `ntdll!RtlSetLastWin32Error` at `0x1800eff55`
- `ntdll!NtWaitForSingleObject` at `0x1800eff6c`
- `ntdll!NtWaitForSingleObject` at `0x18018c49f`
- `ntdll!NtWaitForSingleObject` at `0x1800eff6c`
- `ntdll!NtWaitForSingleObject` at `0x18018c49f`
- `ntdll!RtlSetCurrentTransaction` at `0x1800efc39`
- `ntdll!RtlSetCurrentTransaction` at `0x1800efecb`
- `ntdll!RtlSetCurrentTransaction` at `0x18018c461`
- `ntdll!RtlSetCurrentTransaction` at `0x1800efc39`
- `ntdll!RtlSetCurrentTransaction` at `0x1800efecb`
- `ntdll!RtlSetCurrentTransaction` at `0x18018c461`
- `ntdll!RtlGetCurrentTransaction` at `0x1800efc26`
- `ntdll!RtlGetCurrentTransaction` at `0x1800efc26`
- `ntdll!NtCreateEvent` at `0x1800efd34`
- `ntdll!NtCreateEvent` at `0x1800efd34`
- `ntdll!NtClose` at `0x1800efeaf`
- `ntdll!NtClose` at `0x1800eff5f`
- `ntdll!NtClose` at `0x1800eff7a`
- `ntdll!NtClose` at `0x18018c487`
- `ntdll!NtClose` at `0x18018c4ac`
- `ntdll!NtClose` at `0x1800efeaf`
- `ntdll!NtClose` at `0x1800eff5f`
- `ntdll!NtClose` at `0x1800eff7a`
- `ntdll!NtClose` at `0x18018c487`
- `ntdll!NtClose` at `0x18018c4ac`

## pseudocode

```c
__int64 __fastcall PrivCopyFileExW(
        WCHAR *DosPathName,
        const WCHAR *a2,
        unsigned __int64 a3,
        __int64 a4,
        int *a5,
        unsigned int a6)
{
  unsigned int v8; // r14d
  unsigned int v9; // ebx
  __int64 CurrentTransaction; // rdi
  NTSTATUS v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // esi
  __int64 CreateDisposition; // [rsp+38h] [rbp-150h]
  HANDLE EventHandle; // [rsp+80h] [rbp-108h] BYREF
  HANDLE FileHandle; // [rsp+88h] [rbp-100h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp-F8h] BYREF
  HANDLE v19; // [rsp+98h] [rbp-F0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+A0h] [rbp-E8h] BYREF
  unsigned __int64 v21; // [rsp+B0h] [rbp-D8h]
  int *v22; // [rsp+B8h] [rbp-D0h]
  __int64 v23; // [rsp+C0h] [rbp-C8h]
  __int64 v24; // [rsp+C8h] [rbp-C0h]
  __int128 v25; // [rsp+D0h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-A8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp-78h] BYREF
  __int64 InputBuffer; // [rsp+120h] [rbp-68h] BYREF
  int v29; // [rsp+128h] [rbp-60h]
  __int128 OutputBuffer; // [rsp+130h] [rbp-58h] BYREF
  __int64 v31; // [rsp+140h] [rbp-48h]

  v23 = a4;
  v21 = a3;
  v22 = a5;
  InputBuffer = 0;
  v29 = 0;
  OutputBuffer = 0;
  v31 = 0;
  FileHandle = (HANDLE)-1LL;
  EventHandle = 0;
  IoStatusBlock = 0;
  NtPathName = 0;
  v19 = (HANDLE)-1LL;
  hObject = (HANDLE)-1LL;
  v25 = 0;
  if ( (a6 & 0x201) == 0x201 || (a6 & 0x20000) != 0 && (a6 & 0x8000) == 0 )
  {
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  v8 = 0;
  v9 = a6 & 0xBFFFFFFF;
  if ( (a6 & 0x40000000) == 0 )
    v9 = a6;
  CurrentTransaction = RtlGetCurrentTransaction();
  v24 = CurrentTransaction;
  RtlSetCurrentTransaction(0);
  if ( (v9 & 0x20000) == 0 )
    goto LABEL_12;
  memset(&ObjectAttributes, 0, 44);
  if ( !RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) )
  {
    RtlSetLastWin32Error(3u);
    goto LABEL_15;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtCreateFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x10040u, 0, 0);
  if ( v11 >= 0 )
  {
    v11 = NtCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0);
    if ( v11 >= 0 )
    {
      InputBuffer = 0x3000C0001LL;
      v29 = 1;
      OutputBuffer = 0;
      v31 = 0;
      v13 = NtFsControlFile(
              FileHandle,
              EventHandle,
              0,
              0,
              &IoStatusBlock,
              0x90240u,
              &InputBuffer,
              0xCu,
              &OutputBuffer,
              0x18u);
      if ( v13 != 259 )
      {
        NtClose(EventHandle);
        EventHandle = 0;
        v12 = v13;
        goto LABEL_10;
      }
LABEL_12:
      v25 = v21;
      LODWORD(CreateDisposition) = v9 & 0xBEE4F88F;
      v8 = BasepCopyFileExW(
             DosPathName,
             a2,
             (__int64)&v25,
             v23,
             v22,
             (__int64)EventHandle,
             (__int64)&FileHandle,
             CreateDisposition,
             v9 & 0x411B0770,
             &hObject,
             &v19,
             CurrentTransaction,
             (a6 & 0x40000000) != 0,
             0,
             0,
             0);
      goto LABEL_15;
    }
  }
  v12 = (unsigned int)v11;
LABEL_10:
  BaseSetLastNTError(v12);
LABEL_15:
  RtlSetCurrentTransaction(CurrentTransaction);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( FileHandle != (HANDLE)-1LL )
    NtClose(FileHandle);
  if ( EventHandle )
  {
    NtWaitForSingleObject(EventHandle, 0, 0);
    NtClose(EventHandle);
  }
  if ( v19 != (HANDLE)-1LL )
    CloseHandle(v19);
  RtlFreeUnicodeString(&NtPathName);
  return v8;
}

```

## disassembly

```asm
0x1800efb50  mov     r11, rsp
0x1800efb53  push    rbx
0x1800efb54  push    rsi
0x1800efb55  push    rdi
0x1800efb56  push    r12
0x1800efb58  push    r13
0x1800efb5a  push    r14
0x1800efb5c  push    r15
0x1800efb5e  sub     rsp, 150h
0x1800efb65  mov     rax, cs:__security_cookie
0x1800efb6c  xor     rax, rsp
0x1800efb6f  mov     [rsp+188h+var_40], rax
0x1800efb77  mov     [rsp+188h+var_C8], r9
0x1800efb7f  mov     [rsp+188h+var_D8], r8
0x1800efb87  mov     r13, rdx
0x1800efb8a  mov     r12, rcx
0x1800efb8d  mov     rax, [rsp+188h+arg_20]
0x1800efb95  mov     [rsp+188h+var_D0], rax
0x1800efb9d  xor     eax, eax
0x1800efb9f  mov     [r11-68h], rax
0x1800efba3  mov     [r11-60h], eax
0x1800efba7  xorps   xmm0, xmm0
0x1800efbaa  movups  xmmword ptr [r11-58h], xmm0
0x1800efbaf  mov     [r11-48h], rax
0x1800efbb3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800efbb7  mov     [r11-100h], rax
0x1800efbbe  xor     esi, esi
0x1800efbc0  mov     [r11-108h], rsi
0x1800efbc7  movups  xmmword ptr [r11-78h], xmm0
0x1800efbcc  xorps   xmm1, xmm1
0x1800efbcf  movups  xmmword ptr [rsp+188h+NtPathName.Length], xmm1
0x1800efbd7  mov     [r11-0F0h], rax
0x1800efbde  mov     [r11-0F8h], rax
0x1800efbe5  movups  [rsp+188h+var_B8], xmm0
0x1800efbed  mov     ecx, [rsp+188h+arg_28]
0x1800efbf4  mov     eax, ecx
0x1800efbf6  mov     edx, 201h
0x1800efbfb  and     eax, edx
0x1800efbfd  cmp     eax, edx
0x1800efbff  jz      loc_1800EFF50
0x1800efc05  bt      ecx, 11h
0x1800efc09  jb      loc_1800EFF46
0x1800efc0f  mov     r14d, esi
0x1800efc12  mov     ebx, ecx
0x1800efc14  btr     ebx, 1Eh
0x1800efc18  bt      ecx, 1Eh
0x1800efc1c  cmovnb  ebx, ecx
0x1800efc1f  mov     r15d, esi
0x1800efc22  setb    r15b
0x1800efc26  call    cs:__imp_RtlGetCurrentTransaction
0x1800efc2c  mov     rdi, rax
0x1800efc2f  mov     [rsp+188h+var_C0], rax
0x1800efc37  xor     ecx, ecx
0x1800efc39  call    cs:__imp_RtlSetCurrentTransaction
0x1800efc3f  nop
0x1800efc40  bt      ebx, 11h
0x1800efc44  jnb     loc_1800EFDF5
0x1800efc4a  xor     eax, eax
0x1800efc4c  mov     dword ptr [rsp+188h+ObjectAttributes+4], eax
0x1800efc53  xorps   xmm0, xmm0
0x1800efc56  movups  xmmword ptr [rsp+188h+ObjectAttributes.Length], xmm0
0x1800efc5e  movups  xmmword ptr [rsp+188h+ObjectAttributes.ObjectName], xmm0
0x1800efc66  movups  xmmword ptr [rsp+188h+ObjectAttributes+1Ch], xmm0
0x1800efc6e  xor     r9d, r9d; DirectoryInfo
0x1800efc71  xor     r8d, r8d; NtFileNamePart
0x1800efc74  lea     rdx, [rsp+188h+NtPathName]; NtPathName
0x1800efc7c  mov     rcx, r12; DosPathName
0x1800efc7f  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800efc85  test    al, al
0x1800efc87  jz      loc_1800EFE9A
0x1800efc8d  mov     [rsp+188h+ObjectAttributes.Length], 30h ; '0'
0x1800efc98  mov     [rsp+188h+ObjectAttributes.RootDirectory], rsi
0x1800efca0  mov     [rsp+188h+ObjectAttributes.Attributes], 40h ; '@'
0x1800efcab  lea     rax, [rsp+188h+NtPathName]
0x1800efcb3  mov     [rsp+188h+ObjectAttributes.ObjectName], rax
0x1800efcbb  xorps   xmm0, xmm0
0x1800efcbe  movdqu  xmmword ptr [rsp+188h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800efcc7  mov     [rsp+188h+EaLength], esi; EaLength
0x1800efccb  mov     [rsp+188h+EaBuffer], rsi; EaBuffer
0x1800efcd0  mov     [rsp+188h+CreateOptions], 10040h; CreateOptions
0x1800efcd8  mov     dword ptr [rsp+188h+CreateDisposition], 1; CreateDisposition
0x1800efce0  mov     [rsp+188h+ShareAccess], 7; ShareAccess
0x1800efce8  mov     [rsp+188h+FileAttributes], 80h; FileAttributes
0x1800efcf0  mov     [rsp+188h+AllocationSize], rsi; AllocationSize
0x1800efcf5  lea     r9, [rsp+188h+IoStatusBlock]; IoStatusBlock
0x1800efcfd  lea     r8, [rsp+188h+ObjectAttributes]; ObjectAttributes
0x1800efd05  mov     edx, 120089h; DesiredAccess
0x1800efd0a  lea     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800efd12  call    cs:__imp_NtCreateFile
0x1800efd18  test    eax, eax
0x1800efd1a  js      short loc_1800EFD3E
0x1800efd1c  mov     byte ptr [rsp+188h+AllocationSize], sil; InitialState
0x1800efd21  xor     r9d, r9d; EventType
0x1800efd24  xor     r8d, r8d; ObjectAttributes
0x1800efd27  mov     edx, 1F0003h; DesiredAccess
0x1800efd2c  lea     rcx, [rsp+188h+EventHandle]; EventHandle
0x1800efd34  call    cs:__imp_NtCreateEvent
0x1800efd3a  test    eax, eax
0x1800efd3c  jns     short loc_1800EFD4A
0x1800efd3e  mov     ecx, eax
0x1800efd40  call    BaseSetLastNTError
0x1800efd45  jmp     loc_1800EFEC8
0x1800efd4a  xor     eax, eax
0x1800efd4c  mov     [rsp+188h+InputBuffer], rax
0x1800efd54  mov     [rsp+188h+InputBuffer+4], 3
0x1800efd60  mov     eax, 1
0x1800efd65  mov     dword ptr [rsp+188h+InputBuffer], 0C0001h
0x1800efd70  lea     ecx, [rax+0Bh]
0x1800efd73  mov     [rsp+188h+var_60], eax
0x1800efd7a  xorps   xmm0, xmm0
0x1800efd7d  xor     eax, eax
0x1800efd7f  movups  [rsp+188h+OutputBuffer], xmm0
0x1800efd87  mov     [rsp+188h+var_48], rax
0x1800efd8f  mov     dword ptr [rsp+188h+EaBuffer], 18h; OutputBufferLength
0x1800efd97  lea     rax, [rsp+188h+OutputBuffer]
0x1800efd9f  mov     qword ptr [rsp+188h+CreateOptions], rax; OutputBuffer
0x1800efda4  mov     dword ptr [rsp+188h+CreateDisposition], ecx; InputBufferLength
0x1800efda8  lea     rax, [rsp+188h+InputBuffer]
0x1800efdb0  mov     qword ptr [rsp+188h+ShareAccess], rax; InputBuffer
0x1800efdb5  mov     [rsp+188h+FileAttributes], 90240h; FsControlCode
0x1800efdbd  lea     rax, [rsp+188h+IoStatusBlock]
0x1800efdc5  mov     [rsp+188h+AllocationSize], rax; IoStatusBlock
0x1800efdca  xor     r9d, r9d; ApcContext
0x1800efdcd  xor     r8d, r8d; ApcRoutine
0x1800efdd0  mov     rdx, [rsp+188h+EventHandle]; Event
0x1800efdd8  mov     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800efde0  call    cs:__imp_NtFsControlFile
0x1800efde6  mov     esi, eax
0x1800efde8  cmp     eax, 103h
0x1800efded  jnz     loc_1800EFEA7
0x1800efdf3  xor     esi, esi
0x1800efdf5  mov     rax, [rsp+188h+var_D8]
0x1800efdfd  mov     qword ptr [rsp+188h+var_B8], rax
0x1800efe05  mov     qword ptr [rsp+188h+var_B8+8], rsi
0x1800efe0d  mov     eax, ebx
0x1800efe0f  and     eax, 411B0770h
0x1800efe14  and     ebx, 0BEE4F88Fh
0x1800efe1a  mov     [rsp+188h+var_110], rsi
0x1800efe1f  mov     [rsp+188h+var_118], esi
0x1800efe23  mov     [rsp+188h+var_120], esi
0x1800efe27  mov     [rsp+188h+var_128], r15d
0x1800efe2c  mov     [rsp+188h+var_130], rdi
0x1800efe31  lea     rcx, [rsp+188h+var_F0]
0x1800efe39  mov     qword ptr [rsp+188h+EaLength], rcx
0x1800efe3e  lea     rcx, [rsp+188h+hObject]
0x1800efe46  mov     [rsp+188h+EaBuffer], rcx
0x1800efe4b  mov     [rsp+188h+CreateOptions], eax
0x1800efe4f  mov     dword ptr [rsp+188h+CreateDisposition], ebx
0x1800efe53  lea     rax, [rsp+188h+FileHandle]
0x1800efe5b  mov     qword ptr [rsp+188h+ShareAccess], rax
0x1800efe60  mov     rax, [rsp+188h+EventHandle]
0x1800efe68  mov     qword ptr [rsp+188h+FileAttributes], rax
0x1800efe6d  mov     rax, [rsp+188h+var_D0]
0x1800efe75  mov     [rsp+188h+AllocationSize], rax
0x1800efe7a  mov     r9, [rsp+188h+var_C8]
0x1800efe82  lea     r8, [rsp+188h+var_B8]
0x1800efe8a  mov     rdx, r13
0x1800efe8d  mov     rcx, r12
0x1800efe90  call    BasepCopyFileExW
0x1800efe95  mov     r14d, eax
0x1800efe98  jmp     short loc_1800EFEC8
0x1800efe9a  mov     ecx, 3; LastError
0x1800efe9f  call    cs:__imp_RtlSetLastWin32Error
0x1800efea5  jmp     short loc_1800EFEC8
0x1800efea7  mov     rcx, [rsp+188h+EventHandle]; Handle
0x1800efeaf  call    cs:__imp_NtClose
0x1800efeb5  mov     [rsp+188h+EventHandle], 0
0x1800efec1  mov     ecx, esi
0x1800efec3  jmp     loc_1800EFD40
0x1800efec8  mov     rcx, rdi
0x1800efecb  call    cs:__imp_RtlSetCurrentTransaction
0x1800efed1  mov     rcx, [rsp+188h+hObject]; hObject
0x1800efed9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800efedd  jz      short loc_1800EFEE4
0x1800efedf  call    CloseHandle
0x1800efee4  mov     rcx, [rsp+188h+FileHandle]; Handle
0x1800efeec  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800efef0  jnz     short loc_1800EFF5F
0x1800efef2  mov     rcx, [rsp+188h+EventHandle]; Handle
0x1800efefa  test    rcx, rcx
0x1800efefd  jnz     short loc_1800EFF67
0x1800efeff  mov     rcx, [rsp+188h+var_F0]; hObject
0x1800eff07  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800eff0b  jz      short loc_1800EFF12
0x1800eff0d  call    CloseHandle
0x1800eff12  lea     rcx, [rsp+188h+NtPathName]; UnicodeString
0x1800eff1a  call    cs:__imp_RtlFreeUnicodeString
0x1800eff20  mov     eax, r14d
0x1800eff23  mov     rcx, [rsp+188h+var_40]
0x1800eff2b  xor     rcx, rsp; StackCookie
0x1800eff2e  call    __security_check_cookie
0x1800eff33  add     rsp, 150h
0x1800eff3a  pop     r15
0x1800eff3c  pop     r14
0x1800eff3e  pop     r13
0x1800eff40  pop     r12
0x1800eff42  pop     rdi
0x1800eff43  pop     rsi
0x1800eff44  pop     rbx
0x1800eff45  retn
0x1800eff46  bt      ecx, 0Fh
0x1800eff4a  jb      loc_1800EFC0F
0x1800eff50  mov     ecx, 57h ; 'W'; LastError
0x1800eff55  call    cs:__imp_RtlSetLastWin32Error
0x1800eff5b  xor     eax, eax
0x1800eff5d  jmp     short loc_1800EFF23
0x1800eff5f  call    cs:__imp_NtClose
0x1800eff65  jmp     short loc_1800EFEF2
0x1800eff67  xor     r8d, r8d; Timeout
0x1800eff6a  xor     edx, edx; Alertable
0x1800eff6c  call    cs:__imp_NtWaitForSingleObject
0x1800eff72  mov     rcx, [rsp+188h+EventHandle]; Handle
0x1800eff7a  call    cs:__imp_NtClose
0x1800eff80  jmp     loc_1800EFEFF
0x18018c44e  push    rbp
0x18018c450  sub     rsp, 80h
0x18018c457  mov     rbp, rdx
0x18018c45a  mov     rcx, [rbp+0C8h]
0x18018c461  call    cs:__imp_RtlSetCurrentTransaction
0x18018c467  mov     rcx, [rbp+90h]; hObject
0x18018c46e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18018c472  jz      short loc_18018C47A
0x18018c474  call    CloseHandle
0x18018c479  nop
0x18018c47a  mov     rcx, [rbp+88h]; Handle
0x18018c481  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18018c485  jz      short loc_18018C48E
0x18018c487  call    cs:__imp_NtClose
0x18018c48d  nop
0x18018c48e  mov     rcx, [rbp+80h]; Handle
0x18018c495  test    rcx, rcx
0x18018c498  jz      short loc_18018C4B3
0x18018c49a  xor     r8d, r8d; Timeout
0x18018c49d  xor     edx, edx; Alertable
0x18018c49f  call    cs:__imp_NtWaitForSingleObject
0x18018c4a5  mov     rcx, [rbp+80h]; Handle
0x18018c4ac  call    cs:__imp_NtClose
0x18018c4b2  nop
0x18018c4b3  mov     rcx, [rbp+98h]; hObject
0x18018c4ba  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18018c4be  jz      short loc_18018C4C6
0x18018c4c0  call    CloseHandle
0x18018c4c5  nop
0x18018c4c6  lea     rcx, [rbp+0A0h]; UnicodeString
0x18018c4cd  call    cs:__imp_RtlFreeUnicodeString
0x18018c4d3  nop
0x18018c4d4  add     rsp, 80h
0x18018c4db  pop     rbp
0x18018c4dc  retn
```
