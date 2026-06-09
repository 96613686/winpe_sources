# CFspFileSystemOperations::CreateFileW(ushort const *,ulong,ulong,ulong,ulong,ulong,ulong,void * *)

- ea: `0x180111f4c`
- end: `0x1801121df`
- name: `?CreateFileW@CFspFileSystemOperations@@SAJPEBGKKKKKKPEAPEAX@Z`
- size: `659`
- prototype: `__int64 __fastcall(PCWSTR SourceString, ACCESS_MASK DesiredAccess, __int64, ULONG, ULONG, unsigned int, unsigned int, void **)`
- caller_count: `8`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18010e084`
- `0x18010e248`
- `0x18010eae8`
- `0x18010f5a0`
- `0x18010fd2c`
- `0x18011038c`
- `0x180110c70`
- `0x180112aa0`

## callees

- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x180063cec`
- `0x180111f4c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1801120a1`
- `ntdll!RtlInitUnicodeString` at `0x1801120a1`
- `ntdll!NtFsControlFile` at `0x18011217a`
- `ntdll!NtFsControlFile` at `0x18011217a`
- `ntdll!NtCreateFile` at `0x180112110`
- `ntdll!NtCreateFile` at `0x180112110`
- `ntdll!NtClose` at `0x1801121a2`
- `ntdll!NtClose` at `0x1801121a2`

## string_xrefs

- `0x180111fd7`: `CFspFileSystemOperations::CreateFileW`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CFspFileSystemOperations::CreateFileW(
        PCWSTR SourceString,
        ACCESS_MASK DesiredAccess,
        __int64 a3,
        ULONG a4,
        ULONG a5,
        unsigned int a6,
        unsigned int a7,
        void **a8)
{
  PVOID *v11; // rcx
  char v12; // dl
  void **v13; // rdi
  int v14; // ebx
  unsigned int v15; // esi
  ULONG CreateOptions; // r14d
  unsigned int v17; // eax
  __int16 v18; // ax
  unsigned int v19; // eax
  int v21; // [rsp+60h] [rbp-79h] BYREF
  int v22; // [rsp+64h] [rbp-75h]
  char v23; // [rsp+68h] [rbp-71h]
  const char *v24; // [rsp+70h] [rbp-69h]
  __int64 v25; // [rsp+78h] [rbp-61h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-39h] BYREF
  __int128 InputBuffer; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v30; // [rsp+E0h] [rbp+7h]
  void *FileHandle; // [rsp+120h] [rbp+47h] BYREF

  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_ce5b6c69d76e344a5abed05d444096ed_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( (*((_DWORD *)v11 + 17) & 0x100) != 0 && *((_BYTE *)v11 + 65) >= 6u )
  {
    v12 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v12 = 0;
LABEL_9:
  v13 = a8;
  v22 = 174;
  v23 = v12;
  v24 = "CFspFileSystemOperations::CreateFileW";
  v25 = 0;
  FileHandle = 0;
  if ( a8 )
  {
    *a8 = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !SourceString )
  {
    v14 = -2147024809;
    HIWORD(v22) = 179;
    v21 = -2147024809;
    goto LABEL_24;
  }
  v21 = 0;
  LOWORD(v22) = 179;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  v15 = a7;
  CreateOptions = a5;
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x100) != 0 && *((_BYTE *)v11 + 65) >= 4u )
    WPP_SF_SDDDDDD(
      (unsigned int)v11[7],
      13,
      (unsigned int)WPP_ce5b6c69d76e344a5abed05d444096ed_Traceguids,
      (_DWORD)SourceString,
      DesiredAccess);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 2;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v17 = NtCreateFile(
          &FileHandle,
          DesiredAccess,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          a4,
          1u,
          CreateOptions,
          0,
          0);
  v14 = HRESULTFromNTSTATUS(v17);
  v21 = v14;
  v18 = 207;
  if ( v14 >= 0 )
  {
    LOWORD(v22) = 207;
    if ( v15 )
    {
      v30 = 0;
      InputBuffer = 0;
      LODWORD(InputBuffer) = v15;
      v19 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900FCu, &InputBuffer, 0x18u, 0, 0);
      v14 = HRESULTFromNTSTATUS(v19);
      v21 = v14;
      v18 = 224;
      if ( v14 < 0 )
        goto LABEL_20;
      LOWORD(v22) = 224;
    }
    *v13 = FileHandle;
    goto LABEL_24;
  }
LABEL_20:
  HIWORD(v22) = v18;
  if ( FileHandle )
  {
    NtClose(FileHandle);
    v14 = v21;
  }
LABEL_24:
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v21);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180111f4c  mov     [rsp-8+arg_8], rbx
0x180111f51  mov     [rsp-8+arg_10], rsi
0x180111f56  push    rbp
0x180111f57  push    rdi
0x180111f58  push    r12
0x180111f5a  push    r14
0x180111f5c  push    r15
0x180111f5e  lea     rbp, [rsp-17h]
0x180111f63  sub     rsp, 0F0h
0x180111f6a  mov     r15d, r9d
0x180111f6d  mov     r12d, edx
0x180111f70  mov     rbx, rcx
0x180111f73  mov     rcx, cs:WPP_GLOBAL_Control
0x180111f7a  lea     r9, WPP_GLOBAL_Control
0x180111f81  mov     r8d, 100h
0x180111f87  cmp     rcx, r9
0x180111f8a  jz      short loc_180111FC1
0x180111f8c  test    [rcx+44h], r8d
0x180111f90  jz      short loc_180111FD1
0x180111f92  cmp     byte ptr [rcx+41h], 6
0x180111f96  jb      short loc_180111FC1
0x180111f98  mov     rcx, [rcx+38h]
0x180111f9c  lea     r8, WPP_ce5b6c69d76e344a5abed05d444096ed_Traceguids
0x180111fa3  mov     edx, 0Ch
0x180111fa8  call    WPP_SF_
0x180111fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180111fb4  lea     r9, WPP_GLOBAL_Control
0x180111fbb  mov     r8d, 100h
0x180111fc1  test    [rcx+44h], r8d
0x180111fc5  jz      short loc_180111FD1
0x180111fc7  cmp     byte ptr [rcx+41h], 6
0x180111fcb  jb      short loc_180111FD1
0x180111fcd  mov     dl, 1
0x180111fcf  jmp     short loc_180111FD3
0x180111fd1  xor     dl, dl
0x180111fd3  mov     rdi, [rbp+37h+arg_38]
0x180111fd7  lea     rax, aCfspfilesystem_3; "CFspFileSystemOperations::CreateFileW"
0x180111fde  mov     [rbp+37h+var_AC], 0AEh
0x180111fe5  mov     [rbp+37h+var_A8], dl
0x180111fe8  mov     [rbp+37h+var_A0], rax
0x180111fec  mov     [rbp+37h+var_98], 0
0x180111ff4  mov     [rbp+37h+FileHandle], 0
0x180111ffc  test    rdi, rdi
0x180111fff  jz      short loc_18011200F
0x180112001  mov     qword ptr [rdi], 0
0x180112008  mov     rcx, cs:WPP_GLOBAL_Control
0x18011200f  mov     eax, 0B3h
0x180112014  test    rbx, rbx
0x180112017  jnz     short loc_18011202A
0x180112019  mov     ebx, 80070057h
0x18011201e  mov     word ptr [rbp+37h+var_AC+2], ax
0x180112022  mov     [rbp+37h+var_B0], ebx
0x180112025  jmp     loc_1801121B8
0x18011202a  xorps   xmm1, xmm1
0x18011202d  mov     [rbp+37h+var_B0], 0
0x180112034  xorps   xmm0, xmm0
0x180112037  mov     word ptr [rbp+37h+var_AC], ax
0x18011203b  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x18011203f  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm1
0x180112043  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm1
0x180112047  movups  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm1
0x18011204b  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x18011204f  mov     esi, [rbp+37h+arg_30]
0x180112052  mov     r14d, [rbp+37h+arg_20]
0x180112056  cmp     rcx, r9
0x180112059  jz      short loc_18011209A
0x18011205b  test    [rcx+44h], r8d
0x18011205f  jz      short loc_18011209A
0x180112061  cmp     byte ptr [rcx+41h], 4
0x180112065  jb      short loc_18011209A
0x180112067  mov     rcx, [rcx+38h]
0x18011206b  lea     r8, WPP_ce5b6c69d76e344a5abed05d444096ed_Traceguids
0x180112072  mov     dword ptr [rsp+110h+EaBuffer], esi
0x180112076  mov     edx, 0Dh
0x18011207b  mov     [rsp+110h+CreateOptions], 1
0x180112083  mov     r9, rbx
0x180112086  mov     [rsp+110h+CreateDisposition], r14d
0x18011208b  mov     [rsp+110h+ShareAccess], r15d
0x180112090  mov     dword ptr [rsp+110h+AllocationSize], r12d
0x180112095  call    WPP_SF_SDDDDDD
0x18011209a  mov     rdx, rbx; SourceString
0x18011209d  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x1801120a1  call    cs:__imp_RtlInitUnicodeString
0x1801120a7  mov     [rsp+110h+EaLength], 0; EaLength
0x1801120af  lea     rax, [rbp+37h+DestinationString]
0x1801120b3  mov     [rsp+110h+EaBuffer], 0; EaBuffer
0x1801120bc  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x1801120c0  mov     [rsp+110h+CreateOptions], r14d; CreateOptions
0x1801120c5  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x1801120c9  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x1801120d1  lea     rcx, [rbp+37h+FileHandle]; FileHandle
0x1801120d5  mov     [rsp+110h+ShareAccess], r15d; ShareAccess
0x1801120da  xorps   xmm0, xmm0
0x1801120dd  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x1801120e5  mov     edx, r12d; DesiredAccess
0x1801120e8  mov     [rsp+110h+AllocationSize], 0; AllocationSize
0x1801120f1  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x1801120f8  mov     [rbp+37h+ObjectAttributes.RootDirectory], 0
0x180112100  mov     [rbp+37h+ObjectAttributes.Attributes], 2
0x180112107  mov     [rbp+37h+ObjectAttributes.ObjectName], rax
0x18011210b  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x180112110  call    cs:__imp_NtCreateFile
0x180112116  mov     ecx, eax
0x180112118  call    HRESULTFromNTSTATUS
0x18011211d  mov     ebx, eax
0x18011211f  mov     [rbp+37h+var_B0], eax
0x180112122  test    eax, eax
0x180112124  mov     eax, 0CFh
0x180112129  js      short loc_180112195
0x18011212b  mov     word ptr [rbp+37h+var_AC], ax
0x18011212f  test    esi, esi
0x180112131  jz      short loc_1801121B1
0x180112133  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x180112137  xor     eax, eax
0x180112139  mov     dword ptr [rsp+110h+EaBuffer], eax; OutputBufferLength
0x18011213d  xorps   xmm0, xmm0
0x180112140  mov     qword ptr [rsp+110h+CreateOptions], rax; OutputBuffer
0x180112145  xor     r9d, r9d; ApcContext
0x180112148  mov     [rbp+37h+var_30], rax
0x18011214c  xor     r8d, r8d; ApcRoutine
0x18011214f  mov     [rsp+110h+CreateDisposition], 18h; InputBufferLength
0x180112157  lea     rax, [rbp+37h+InputBuffer]
0x18011215b  mov     qword ptr [rsp+110h+ShareAccess], rax; InputBuffer
0x180112160  xor     edx, edx; Event
0x180112162  lea     rax, [rbp+37h+IoStatusBlock]
0x180112166  mov     [rsp+110h+FileAttributes], 900FCh; FsControlCode
0x18011216e  movups  [rbp+37h+InputBuffer], xmm0
0x180112172  mov     [rsp+110h+AllocationSize], rax; IoStatusBlock
0x180112177  mov     dword ptr [rbp+37h+InputBuffer], esi
0x18011217a  call    cs:__imp_NtFsControlFile
0x180112180  mov     ecx, eax
0x180112182  call    HRESULTFromNTSTATUS
0x180112187  mov     ebx, eax
0x180112189  mov     [rbp+37h+var_B0], eax
0x18011218c  test    eax, eax
0x18011218e  mov     eax, 0E0h
0x180112193  jns     short loc_1801121AD
0x180112195  mov     rcx, [rbp+37h+FileHandle]; Handle
0x180112199  mov     word ptr [rbp+37h+var_AC+2], ax
0x18011219d  test    rcx, rcx
0x1801121a0  jz      short loc_1801121B8
0x1801121a2  call    cs:__imp_NtClose
0x1801121a8  mov     ebx, [rbp+37h+var_B0]
0x1801121ab  jmp     short loc_1801121B8
0x1801121ad  mov     word ptr [rbp+37h+var_AC], ax
0x1801121b1  mov     rcx, [rbp+37h+FileHandle]
0x1801121b5  mov     [rdi], rcx
0x1801121b8  lea     rcx, [rbp+37h+var_B0]; this
0x1801121bc  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1801121c1  lea     r11, [rsp+110h+var_20]
0x1801121c9  mov     eax, ebx
0x1801121cb  mov     rbx, [r11+38h]
0x1801121cf  mov     rsi, [r11+40h]
0x1801121d3  mov     rsp, r11
0x1801121d6  pop     r15
0x1801121d8  pop     r14
0x1801121da  pop     r12
0x1801121dc  pop     rdi
0x1801121dd  pop     rbp
0x1801121de  retn
```
