# CFspFileSystemOperations::CreateFileW(void *,_FILE_ID_128,ushort const *,ulong,ulong,ulong,ulong,ulong,ulong,void * *)

- ea: `0x180111b4c`
- end: `0x180111f45`
- name: `?CreateFileW@CFspFileSystemOperations@@SAJPEAXU_FILE_ID_128@@PEBGKKKKKKPEAPEAX@Z`
- size: `1017`
- prototype: `static int(void *, struct _FILE_ID_128 *__struct_ptr, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void **)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18010c1e0`
- `0x18010d440`
- `0x18010d738`
- `0x180112960`

## callees

- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x18009adc8`
- `0x180111b4c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180111df3`
- `ntdll!RtlInitUnicodeString` at `0x180111df3`
- `ntdll!NtFsControlFile` at `0x180111db5`
- `ntdll!NtFsControlFile` at `0x180111ecf`
- `ntdll!NtFsControlFile` at `0x180111db5`
- `ntdll!NtFsControlFile` at `0x180111ecf`
- `ntdll!NtCreateFile` at `0x180111d32`
- `ntdll!NtCreateFile` at `0x180111e5f`
- `ntdll!NtCreateFile` at `0x180111d32`
- `ntdll!NtCreateFile` at `0x180111e5f`
- `ntdll!NtClose` at `0x180111f04`
- `ntdll!NtClose` at `0x180111f1b`
- `ntdll!NtClose` at `0x180111f04`
- `ntdll!NtClose` at `0x180111f1b`

## string_xrefs

- `0x180111be8`: `CFspFileSystemOperations::CreateFileW`

## pseudocode

```c
__int64 __fastcall CFspFileSystemOperations::CreateFileW(
        void *a1,
        WCHAR *a2,
        const unsigned __int16 *a3,
        ACCESS_MASK a4,
        unsigned int a5,
        ULONG ShareAccess,
        ULONG CreateOptions,
        ULONG CreateDisposition,
        unsigned int a9,
        void **a10)
{
  void *v11; // r8
  PVOID *v13; // rcx
  char v14; // dl
  __int16 v15; // ax
  int v16; // ebx
  unsigned int v17; // eax
  __int16 v18; // ax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v23; // [rsp+60h] [rbp-91h] BYREF
  int v24; // [rsp+64h] [rbp-8Dh]
  char v25; // [rsp+68h] [rbp-89h]
  const char *v26; // [rsp+70h] [rbp-81h]
  __int64 v27; // [rsp+78h] [rbp-79h]
  struct _UNICODE_STRING InputBuffer; // [rsp+80h] [rbp-71h] BYREF
  __int64 v29; // [rsp+90h] [rbp-61h]
  ACCESS_MASK DesiredAccess; // [rsp+98h] [rbp-59h]
  void *FileHandle; // [rsp+A0h] [rbp-51h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-11h] BYREF

  v11 = a1;
  DesiredAccess = a4;
  *(_QWORD *)&InputBuffer.Length = a1;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, WPP_ce5b6c69d76e344a5abed05d444096ed_Traceguids);
    v13 = (PVOID *)WPP_GLOBAL_Control;
    v11 = *(void **)&InputBuffer.Length;
    LOBYTE(a4) = DesiredAccess;
  }
  if ( (*((_DWORD *)v13 + 17) & 0x100) == 0 || (v14 = 1, *((_BYTE *)v13 + 65) < 6u) )
    v14 = 0;
  v24 = 287;
  v26 = "CFspFileSystemOperations::CreateFileW";
  v25 = v14;
  v27 = 0;
  FileHandle = 0;
  Handle = 0;
  IoStatusBlock = 0;
  if ( a10 )
  {
    *a10 = 0;
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  v15 = 294;
  if ( !v11 || (LOWORD(v24) = 294, v15 = 295, !a3) )
  {
    v16 = -2147024809;
    HIWORD(v24) = v15;
    v23 = -2147024809;
    goto LABEL_34;
  }
  v23 = 0;
  LOWORD(v24) = 295;
  if ( v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 17) & 0x100) != 0 && *((_BYTE *)v13 + 65) >= 4u )
  {
    WPP_SF_iiSDDDDDD(
      (unsigned int)v13[7],
      15,
      (unsigned int)WPP_ce5b6c69d76e344a5abed05d444096ed_Traceguids,
      *((_QWORD *)a2 + 1),
      *(_QWORD *)a2,
      (__int64)a3,
      a4);
    v11 = *(void **)&InputBuffer.Length;
  }
  ObjectAttributes.RootDirectory = v11;
  *(_QWORD *)&InputBuffer.Length = 1048592;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 2;
  InputBuffer.Buffer = a2;
  ObjectAttributes.ObjectName = &InputBuffer;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v17 = NtCreateFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x2021u, 0, 0);
  if ( v17 == -1073741811 )
    v17 = -1073741766;
  v16 = HRESULTFromNTSTATUS(v17);
  v23 = v16;
  v18 = 339;
  if ( v16 < 0 )
    goto LABEL_20;
  LOWORD(v24) = 339;
  if ( a9 )
  {
    v29 = 0;
    InputBuffer = 0;
    *(_DWORD *)&InputBuffer.Length = a9;
    v19 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900FCu, &InputBuffer, 0x18u, 0, 0);
    v16 = HRESULTFromNTSTATUS(v19);
    v23 = v16;
    v18 = 357;
    if ( v16 < 0 )
      goto LABEL_20;
    LOWORD(v24) = 357;
  }
  InputBuffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&InputBuffer, a3);
  ObjectAttributes.RootDirectory = FileHandle;
  ObjectAttributes.ObjectName = &InputBuffer;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 2;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v20 = NtCreateFile(
          &Handle,
          DesiredAccess,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          ShareAccess,
          CreateDisposition,
          CreateOptions,
          0,
          0);
  v16 = HRESULTFromNTSTATUS(v20);
  v23 = v16;
  v18 = 383;
  if ( v16 >= 0 )
  {
    LOWORD(v24) = 383;
    if ( !a9 )
    {
LABEL_28:
      *a10 = Handle;
      goto LABEL_29;
    }
    v29 = 0;
    InputBuffer = 0;
    *(_DWORD *)&InputBuffer.Length = a9;
    v21 = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x900FCu, &InputBuffer, 0x18u, 0, 0);
    v16 = HRESULTFromNTSTATUS(v21);
    v23 = v16;
    v18 = 401;
    if ( v16 >= 0 )
    {
      LOWORD(v24) = 401;
      goto LABEL_28;
    }
  }
LABEL_20:
  HIWORD(v24) = v18;
LABEL_29:
  if ( FileHandle )
  {
    NtClose(FileHandle);
    v16 = v23;
  }
  if ( v16 < 0 && Handle )
  {
    NtClose(Handle);
    v16 = v23;
  }
LABEL_34:
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v23);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180111b4c  push    rbp
0x180111b4e  push    rbx
0x180111b4f  push    rsi
0x180111b50  push    rdi
0x180111b51  push    r12
0x180111b53  push    r13
0x180111b55  push    r14
0x180111b57  push    r15
0x180111b59  lea     rbp, [rsp-7]
0x180111b5e  sub     rsp, 0F8h
0x180111b65  mov     rsi, [rbp+3Fh+arg_48]
0x180111b6c  mov     r14, r8
0x180111b6f  mov     r8, rcx
0x180111b72  mov     [rbp+3Fh+DesiredAccess], r9d
0x180111b76  mov     rbx, rdx
0x180111b79  mov     qword ptr [rbp+3Fh+InputBuffer], rcx
0x180111b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180111b84  lea     rax, WPP_GLOBAL_Control
0x180111b8b  mov     r11d, 100h
0x180111b91  cmp     rcx, rax
0x180111b94  jz      short loc_180111BCC
0x180111b96  test    [rcx+44h], r11d
0x180111b9a  jz      short loc_180111BCC
0x180111b9c  cmp     byte ptr [rcx+41h], 6
0x180111ba0  jb      short loc_180111BCC
0x180111ba2  mov     rcx, [rcx+38h]
0x180111ba6  lea     r8, WPP_ce5b6c69d76e344a5abed05d444096ed_Traceguids
0x180111bad  mov     edx, 0Eh
0x180111bb2  call    WPP_SF_
0x180111bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180111bbe  mov     r11d, 100h
0x180111bc4  mov     r8, qword ptr [rbp+3Fh+InputBuffer]
0x180111bc8  mov     r9d, [rbp+3Fh+DesiredAccess]
0x180111bcc  xor     r10d, r10d
0x180111bcf  test    [rcx+44h], r11d
0x180111bd3  jz      short loc_180111BDD
0x180111bd5  cmp     byte ptr [rcx+41h], 6
0x180111bd9  mov     dl, 1
0x180111bdb  jnb     short loc_180111BE0
0x180111bdd  mov     dl, r10b
0x180111be0  mov     [rsp+130h+var_CC], 11Fh
0x180111be8  lea     rax, aCfspfilesystem_3; "CFspFileSystemOperations::CreateFileW"
0x180111bef  mov     [rsp+130h+var_C0], rax
0x180111bf4  xorps   xmm0, xmm0
0x180111bf7  mov     [rsp+130h+var_C8], dl
0x180111bfb  mov     [rbp+3Fh+var_B8], r10
0x180111bff  mov     [rbp+3Fh+FileHandle], r10
0x180111c03  mov     [rbp+3Fh+Handle], r10
0x180111c07  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x180111c0b  test    rsi, rsi
0x180111c0e  jz      short loc_180111C1A
0x180111c10  mov     [rsi], r10
0x180111c13  mov     rcx, cs:WPP_GLOBAL_Control
0x180111c1a  mov     eax, 126h
0x180111c1f  test    r8, r8
0x180111c22  jnz     short loc_180111C37
0x180111c24  mov     ebx, 80070057h
0x180111c29  mov     word ptr [rsp+130h+var_CC+2], ax
0x180111c2e  mov     [rsp+130h+var_D0], ebx
0x180111c32  jmp     loc_180111F25
0x180111c37  mov     word ptr [rsp+130h+var_CC], ax
0x180111c3c  mov     eax, 127h
0x180111c41  test    r14, r14
0x180111c44  jz      short loc_180111C24
0x180111c46  mov     [rsp+130h+var_D0], r10d
0x180111c4b  mov     word ptr [rsp+130h+var_CC], ax
0x180111c50  mov     edi, [rbp+3Fh+arg_40]
0x180111c56  lea     rax, WPP_GLOBAL_Control
0x180111c5d  mov     r15d, [rbp+3Fh+arg_38]
0x180111c64  mov     r12d, [rbp+3Fh+arg_30]
0x180111c68  mov     r13d, [rbp+3Fh+arg_28]
0x180111c6c  cmp     rcx, rax
0x180111c6f  jz      short loc_180111CC2
0x180111c71  test    [rcx+44h], r11d
0x180111c75  jz      short loc_180111CC2
0x180111c77  cmp     byte ptr [rcx+41h], 4
0x180111c7b  jb      short loc_180111CC2
0x180111c7d  mov     rax, [rbx]
0x180111c80  lea     r8, WPP_ce5b6c69d76e344a5abed05d444096ed_Traceguids
0x180111c87  mov     rcx, [rcx+38h]
0x180111c8b  mov     edx, 0Fh
0x180111c90  mov     [rsp+130h+var_D8], edi
0x180111c94  mov     [rsp+130h+EaLength], r15d
0x180111c99  mov     dword ptr [rsp+130h+EaBuffer], r12d
0x180111c9e  mov     [rsp+130h+CreateOptions], r13d
0x180111ca3  mov     [rsp+130h+ShareAccess], r9d
0x180111ca8  mov     r9, [rbx+8]
0x180111cac  mov     qword ptr [rsp+130h+FileAttributes], r14
0x180111cb1  mov     [rsp+130h+AllocationSize], rax
0x180111cb6  call    WPP_SF_iiSDDDDDD
0x180111cbb  mov     r8, qword ptr [rbp+3Fh+InputBuffer]
0x180111cbf  xor     r10d, r10d
0x180111cc2  mov     [rsp+130h+EaLength], r10d; EaLength
0x180111cc7  lea     rax, [rbp+3Fh+InputBuffer]
0x180111ccb  mov     [rsp+130h+EaBuffer], r10; EaBuffer
0x180111cd0  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x180111cd4  mov     [rsp+130h+CreateOptions], 2021h; CreateOptions
0x180111cdc  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x180111ce0  mov     [rsp+130h+CreateDisposition], 1; CreateDisposition
0x180111ce8  xorps   xmm0, xmm0
0x180111ceb  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x180111cf3  mov     edx, 100000h; DesiredAccess
0x180111cf8  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r8
0x180111cfc  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x180111d00  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x180111d08  mov     [rsp+130h+AllocationSize], r10; AllocationSize
0x180111d0d  mov     qword ptr [rbp+3Fh+InputBuffer], 100010h
0x180111d15  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x180111d1d  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 2
0x180111d25  mov     qword ptr [rbp+3Fh+InputBuffer+8], rbx
0x180111d29  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x180111d2d  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180111d32  call    cs:__imp_NtCreateFile
0x180111d38  mov     ecx, 0C000003Ah
0x180111d3d  cmp     eax, 0C000000Dh
0x180111d42  cmovz   eax, ecx
0x180111d45  mov     ecx, eax
0x180111d47  call    HRESULTFromNTSTATUS
0x180111d4c  mov     ebx, eax
0x180111d4e  mov     [rsp+130h+var_D0], eax
0x180111d52  test    eax, eax
0x180111d54  mov     eax, 153h
0x180111d59  jns     short loc_180111D65
0x180111d5b  mov     word ptr [rsp+130h+var_CC+2], ax
0x180111d60  jmp     loc_180111EFB
0x180111d65  mov     word ptr [rsp+130h+var_CC], ax
0x180111d6a  test    edi, edi
0x180111d6c  jz      short loc_180111DD6
0x180111d6e  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x180111d72  xor     eax, eax
0x180111d74  mov     dword ptr [rsp+130h+EaBuffer], eax; OutputBufferLength
0x180111d78  xorps   xmm0, xmm0
0x180111d7b  mov     qword ptr [rsp+130h+CreateOptions], rax; OutputBuffer
0x180111d80  xor     r9d, r9d; ApcContext
0x180111d83  mov     [rbp+3Fh+var_A0], rax
0x180111d87  xor     r8d, r8d; ApcRoutine
0x180111d8a  mov     [rsp+130h+CreateDisposition], 18h; InputBufferLength
0x180111d92  lea     rax, [rbp+3Fh+InputBuffer]
0x180111d96  mov     qword ptr [rsp+130h+ShareAccess], rax; InputBuffer
0x180111d9b  xor     edx, edx; Event
0x180111d9d  lea     rax, [rbp+3Fh+IoStatusBlock]
0x180111da1  mov     [rsp+130h+FileAttributes], 900FCh; FsControlCode
0x180111da9  movups  [rbp+3Fh+InputBuffer], xmm0
0x180111dad  mov     [rsp+130h+AllocationSize], rax; IoStatusBlock
0x180111db2  mov     dword ptr [rbp+3Fh+InputBuffer], edi
0x180111db5  call    cs:__imp_NtFsControlFile
0x180111dbb  mov     ecx, eax
0x180111dbd  call    HRESULTFromNTSTATUS
0x180111dc2  mov     ebx, eax
0x180111dc4  mov     [rsp+130h+var_D0], eax
0x180111dc8  test    eax, eax
0x180111dca  mov     eax, 165h
0x180111dcf  js      short loc_180111D5B
0x180111dd1  mov     word ptr [rsp+130h+var_CC], ax
0x180111dd6  xorps   xmm1, xmm1
0x180111dd9  lea     rcx, [rbp+3Fh+InputBuffer]; DestinationString
0x180111ddd  xorps   xmm0, xmm0
0x180111de0  mov     rdx, r14; SourceString
0x180111de3  movups  [rbp+3Fh+InputBuffer], xmm0
0x180111de7  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm1
0x180111deb  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm1
0x180111def  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm1
0x180111df3  call    cs:__imp_RtlInitUnicodeString
0x180111df9  mov     rax, [rbp+3Fh+FileHandle]
0x180111dfd  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x180111e01  mov     edx, [rbp+3Fh+DesiredAccess]; DesiredAccess
0x180111e04  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x180111e08  mov     [rsp+130h+EaLength], 0; EaLength
0x180111e10  lea     rcx, [rbp+3Fh+Handle]; FileHandle
0x180111e14  mov     [rsp+130h+EaBuffer], 0; EaBuffer
0x180111e1d  xorps   xmm0, xmm0
0x180111e20  mov     [rsp+130h+CreateOptions], r12d; CreateOptions
0x180111e25  mov     [rsp+130h+CreateDisposition], r15d; CreateDisposition
0x180111e2a  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rax
0x180111e2e  lea     rax, [rbp+3Fh+InputBuffer]
0x180111e32  mov     [rsp+130h+ShareAccess], r13d; ShareAccess
0x180111e37  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x180111e3f  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x180111e43  mov     [rsp+130h+AllocationSize], 0; AllocationSize
0x180111e4c  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x180111e53  mov     [rbp+3Fh+ObjectAttributes.Attributes], 2
0x180111e5a  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180111e5f  call    cs:__imp_NtCreateFile
0x180111e65  mov     ecx, eax
0x180111e67  call    HRESULTFromNTSTATUS
0x180111e6c  mov     ebx, eax
0x180111e6e  mov     [rsp+130h+var_D0], eax
0x180111e72  test    eax, eax
0x180111e74  mov     eax, 17Fh
0x180111e79  js      loc_180111D5B
0x180111e7f  mov     word ptr [rsp+130h+var_CC], ax
0x180111e84  test    edi, edi
0x180111e86  jz      short loc_180111EF4
0x180111e88  mov     rcx, [rbp+3Fh+Handle]; FileHandle
0x180111e8c  xor     eax, eax
0x180111e8e  mov     dword ptr [rsp+130h+EaBuffer], eax; OutputBufferLength
0x180111e92  xorps   xmm0, xmm0
0x180111e95  mov     qword ptr [rsp+130h+CreateOptions], rax; OutputBuffer
0x180111e9a  xor     r9d, r9d; ApcContext
0x180111e9d  mov     [rbp+3Fh+var_A0], rax
0x180111ea1  xor     r8d, r8d; ApcRoutine
0x180111ea4  mov     [rsp+130h+CreateDisposition], 18h; InputBufferLength
0x180111eac  lea     rax, [rbp+3Fh+InputBuffer]
0x180111eb0  mov     qword ptr [rsp+130h+ShareAccess], rax; InputBuffer
0x180111eb5  xor     edx, edx; Event
0x180111eb7  lea     rax, [rbp+3Fh+IoStatusBlock]
0x180111ebb  mov     [rsp+130h+FileAttributes], 900FCh; FsControlCode
0x180111ec3  movups  [rbp+3Fh+InputBuffer], xmm0
0x180111ec7  mov     [rsp+130h+AllocationSize], rax; IoStatusBlock
0x180111ecc  mov     dword ptr [rbp+3Fh+InputBuffer], edi
0x180111ecf  call    cs:__imp_NtFsControlFile
0x180111ed5  mov     ecx, eax
0x180111ed7  call    HRESULTFromNTSTATUS
0x180111edc  mov     ebx, eax
0x180111ede  mov     [rsp+130h+var_D0], eax
0x180111ee2  test    eax, eax
0x180111ee4  mov     eax, 191h
0x180111ee9  js      loc_180111D5B
0x180111eef  mov     word ptr [rsp+130h+var_CC], ax
0x180111ef4  mov     rax, [rbp+3Fh+Handle]
0x180111ef8  mov     [rsi], rax
0x180111efb  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x180111eff  test    rcx, rcx
0x180111f02  jz      short loc_180111F0E
0x180111f04  call    cs:__imp_NtClose
0x180111f0a  mov     ebx, [rsp+130h+var_D0]
0x180111f0e  test    ebx, ebx
0x180111f10  jns     short loc_180111F25
0x180111f12  mov     rcx, [rbp+3Fh+Handle]; Handle
0x180111f16  test    rcx, rcx
0x180111f19  jz      short loc_180111F25
0x180111f1b  call    cs:__imp_NtClose
0x180111f21  mov     ebx, [rsp+130h+var_D0]
0x180111f25  lea     rcx, [rsp+130h+var_D0]; this
0x180111f2a  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180111f2f  mov     eax, ebx
0x180111f31  add     rsp, 0F8h
0x180111f38  pop     r15
0x180111f3a  pop     r14
0x180111f3c  pop     r13
0x180111f3e  pop     r12
0x180111f40  pop     rdi
0x180111f41  pop     rsi
0x180111f42  pop     rbx
0x180111f43  pop     rbp
0x180111f44  retn
```
