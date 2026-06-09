# InternalFindFirstFileExW

- ea: `0x180076e30`
- end: `0x180077504`
- name: `InternalFindFirstFileExW`
- size: `1748`
- prototype: `__int64 __usercall@<rax>(PCWSTR DosName@<rcx>, int, int)`
- caller_count: `7`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180045130`
- `0x180075c30`
- `0x180075dd0`
- `0x180076630`
- `0x180076db0`
- `0x180076df0`
- `0x180078ff0`

## callees

- `0x1800134a0`
- `0x180076e30`
- `0x18012d119`
- `0x180181880`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180076f13`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180076f13`
- `ntdll!RtlInitUnicodeString` at `0x180076eeb`
- `ntdll!RtlInitUnicodeString` at `0x180076eeb`
- `ntdll!RtlReleaseRelativeName` at `0x1800770f9`
- `ntdll!RtlReleaseRelativeName` at `0x180077348`
- `ntdll!RtlReleaseRelativeName` at `0x18007738e`
- `ntdll!RtlReleaseRelativeName` at `0x180077449`
- `ntdll!RtlReleaseRelativeName` at `0x1800770f9`
- `ntdll!RtlReleaseRelativeName` at `0x180077348`
- `ntdll!RtlReleaseRelativeName` at `0x18007738e`
- `ntdll!RtlReleaseRelativeName` at `0x180077449`
- `ntdll!NtOpenFile` at `0x180077002`
- `ntdll!NtOpenFile` at `0x180077411`
- `ntdll!NtOpenFile` at `0x180077002`
- `ntdll!NtOpenFile` at `0x180077411`
- `ntdll!RtlInitializeCriticalSection` at `0x18007721d`
- `ntdll!RtlInitializeCriticalSection` at `0x18007721d`
- `ntdll!RtlSetLastWin32Error` at `0x1800773bc`
- `ntdll!RtlSetLastWin32Error` at `0x1800773cc`
- `ntdll!RtlSetLastWin32Error` at `0x1800774f2`
- `ntdll!RtlSetLastWin32Error` at `0x1800773bc`
- `ntdll!RtlSetLastWin32Error` at `0x1800773cc`
- `ntdll!RtlSetLastWin32Error` at `0x1800774f2`
- `ntdll!RtlIsDosDeviceName_U` at `0x180076f32`
- `ntdll!RtlIsDosDeviceName_U` at `0x180076f32`
- `ntdll!NtClose` at `0x18007732b`
- `ntdll!NtClose` at `0x1800773b1`
- `ntdll!NtClose` at `0x1800774d2`
- `ntdll!NtClose` at `0x18007732b`
- `ntdll!NtClose` at `0x1800773b1`
- `ntdll!NtClose` at `0x1800774d2`
- `ntdll!RtlFreeHeap` at `0x180077111`
- `ntdll!RtlFreeHeap` at `0x180077360`
- `ntdll!RtlFreeHeap` at `0x1800773a6`
- `ntdll!RtlFreeHeap` at `0x180077461`
- `ntdll!RtlFreeHeap` at `0x1800774c7`
- `ntdll!RtlFreeHeap` at `0x180077111`
- `ntdll!RtlFreeHeap` at `0x180077360`
- `ntdll!RtlFreeHeap` at `0x1800773a6`
- `ntdll!RtlFreeHeap` at `0x180077461`
- `ntdll!RtlFreeHeap` at `0x1800774c7`
- `ntdll!RtlCompareMemory` at `0x1800772db`
- `ntdll!RtlCompareMemory` at `0x1800772db`
- `ntdll!NtQueryDirectoryFileEx` at `0x1800770ed`
- `ntdll!NtQueryDirectoryFileEx` at `0x1800770ed`
- `ntdll!RtlAllocateHeap` at `0x1800771f0`
- `ntdll!RtlAllocateHeap` at `0x1800771f0`

## pseudocode

```c
__int64 __fastcall InternalFindFirstFileExW(PCWSTR DosName, int a2, __int64 a3, int a4, int a5, int a6)
{
  bool v10; // r15
  PWSTR Buffer; // r13
  ULONG IsDosDeviceName_U; // eax
  unsigned __int64 v13; // rbx
  USHORT Length; // ax
  __int16 v15; // cx
  unsigned int v16; // edx
  bool v17; // di
  NTSTATUS v18; // eax
  NTSTATUS v19; // ebx
  unsigned int v20; // eax
  WCHAR *v21; // rdx
  int v22; // ebx
  unsigned __int8 *p_Src; // rdx
  int v24; // edi
  unsigned int v25; // eax
  bool v26; // cc
  unsigned __int64 v27; // rbx
  unsigned int v28; // ecx
  unsigned __int64 v29; // rbx
  struct _RTL_CRITICAL_SECTION_DEBUG *v30; // rdi
  struct _RTL_CRITICAL_SECTION *Heap; // rax
  struct _RTL_CRITICAL_SECTION *v32; // rbx
  ULONG v34; // ecx
  ULONG v35; // ecx
  HANDLE FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR PartName[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+88h] [rbp-78h] BYREF
  _WORD v41[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v42; // [rsp+ACh] [rbp-54h]
  char *v43; // [rsp+B0h] [rbp-50h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h] BYREF
  char v46[8]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v47; // [rsp+108h] [rbp+8h]
  __int64 v48; // [rsp+110h] [rbp+10h]
  __int64 v49; // [rsp+118h] [rbp+18h]
  int v50; // [rsp+128h] [rbp+28h]
  int v51; // [rsp+12Ch] [rbp+2Ch]
  int v52; // [rsp+138h] [rbp+38h]
  unsigned int v53; // [rsp+13Ch] [rbp+3Ch]
  int v54; // [rsp+140h] [rbp+40h]
  unsigned __int8 v55; // [rsp+144h] [rbp+44h] BYREF
  char v56[24]; // [rsp+146h] [rbp+46h] BYREF
  char Src; // [rsp+15Eh] [rbp+5Eh] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)PartName = 0;
  NtName = 0;
  IoStatusBlock = 0;
  memset_0(v46, 0, 0x268u);
  v42 = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  DestinationString = 0;
  if ( a2 >= 2 || a4 >= 2 || (a6 & 0xFFFFFFF8) != 0 )
  {
    v35 = 50;
    if ( a4 != 2 )
      v35 = 87;
    RtlSetLastWin32Error(v35);
    return -1;
  }
  RtlInitUnicodeString(&DestinationString, DosName);
  v10 = DestinationString.Length
     && DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] == 46;
  if ( !RtlDosPathNameToRelativeNtPathName_U(DosName, &NtName, &PartName[1], &RelativeName) )
  {
    RtlSetLastWin32Error(3u);
    return -1;
  }
  Buffer = NtName.Buffer;
  IsDosDeviceName_U = RtlIsDosDeviceName_U(DestinationString.Buffer);
  v13 = IsDosDeviceName_U;
  if ( IsDosDeviceName_U )
  {
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    v41[0] = v13;
    v43 = (char *)DestinationString.Buffer + (v13 >> 16);
    v41[1] = v13;
    return BaseFindFirstDevice(v41, a3);
  }
  Length = NtName.Length;
  if ( PartName[1] )
    v15 = NtName.Length + LOWORD(NtName.Buffer) - LOWORD(PartName[1]);
  else
    v15 = 0;
  LOWORD(PartName[0]) = v15;
  WORD1(PartName[0]) = v15;
  if ( !RelativeName.RelativeName.Length || RelativeName.RelativeName.Buffer == PartName[1] )
  {
    RelativeName.ContainingDirectory = 0;
    if ( !PartName[1] )
      goto LABEL_14;
    Length = LOWORD(PartName[1]) - LOWORD(NtName.Buffer);
    goto LABEL_13;
  }
  if ( PartName[1] )
  {
    NtName.Buffer = RelativeName.RelativeName.Buffer;
    Length = LOWORD(PartName[1]) - LOWORD(RelativeName.RelativeName.Buffer);
LABEL_13:
    NtName.MaximumLength = Length;
    NtName.Length = Length;
  }
LABEL_14:
  v16 = Length >> 1;
  v17 = v16 >= 2 && NtName.Buffer[v16 - 2] != 58 && NtName.Buffer[v16 - 1] == 92;
  ObjectAttributes.RootDirectory = RelativeName.ContainingDirectory;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = ((a6 & 1) == 0) << 6;
  ObjectAttributes.ObjectName = &NtName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v18 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
  v19 = v18;
  if ( v17 && (v18 == -1073741565 || v18 == -1073741811) )
  {
    NtName.Length -= 2;
    v19 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
  }
  if ( v19 >= 0 )
  {
    if ( !LOWORD(PartName[0]) )
    {
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      NtClose(FileHandle);
      v34 = 2;
      goto LABEL_65;
    }
    if ( LOWORD(PartName[0]) == 6 && RtlCompareMemory(PartName[1], L"*.*", 6u) == 6 )
    {
      LOWORD(PartName[0]) = 2;
LABEL_29:
      v22 = NtQueryDirectoryFileEx(
              FileHandle,
              0,
              0,
              0,
              &IoStatusBlock,
              v46,
              616,
              3 - (unsigned int)(a2 != 0),
              2 * (a6 & 4 | 1u),
              PartName);
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      if ( v22 < 0 )
      {
        NtClose(FileHandle);
        BaseSetLastNTError((unsigned int)v22);
        return -1;
      }
      p_Src = &v55;
      v24 = v52;
      *(_QWORD *)(a3 + 4) = v47;
      *(_QWORD *)(a3 + 12) = v48;
      *(_QWORD *)(a3 + 20) = v49;
      *(_DWORD *)(a3 + 28) = v51;
      *(_DWORD *)(a3 + 32) = v50;
      v25 = v53;
      v26 = v53 <= 0x206;
      *(_DWORD *)a3 = v24;
      if ( !v26 )
        v25 = 518;
      v27 = v25;
      if ( !a2 )
        p_Src = (unsigned __int8 *)&Src;
      memcpy_0((void *)(a3 + 44), p_Src, v25);
      *(_WORD *)(a3 + 2 * (v27 >> 1) + 44) = 0;
      if ( a2 )
      {
        *(_WORD *)(a3 + 564) = 0;
      }
      else
      {
        if ( v55 > 0x1Au || (v28 = (char)v55, (unsigned int)(char)v55 >= 0x18) )
          v28 = 24;
        v29 = v28;
        memcpy_0((void *)(a3 + 564), v56, v28);
        *(_WORD *)(a3 + 2 * (v29 >> 1) + 564) = 0;
      }
      if ( (v24 & 0x400) != 0 )
        *(_DWORD *)(a3 + 36) = v54;
      v30 = (struct _RTL_CRITICAL_SECTION_DEBUG *)FileHandle;
      Heap = (struct _RTL_CRITICAL_SECTION *)RtlAllocateHeap(
                                               NtCurrentPeb()->ProcessHeap,
                                               KernelBaseGlobalData + 786432,
                                               0x50u);
      v32 = Heap;
      if ( Heap )
      {
        Heap->DebugInfo = v30;
        *(_QWORD *)&Heap->LockCount = 0;
        Heap->OwningThread = 0;
        Heap->LockSemaphore = 0;
        LODWORD(Heap->SpinCount) = a2;
        HIDWORD(Heap->SpinCount) = a6;
        if ( RtlInitializeCriticalSection(Heap + 1) >= 0 )
          return (__int64)v32;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v32);
      }
      NtClose(FileHandle);
      v34 = 8;
LABEL_65:
      RtlSetLastWin32Error(v34);
      return -1;
    }
    v20 = 0;
    v21 = (WCHAR *)PartName[1];
    if ( ((__int64)PartName[0] & 0xFFFE) == 0 )
    {
LABEL_28:
      if ( v10 && *(v21 - 1) == 42 )
        *(v21 - 1) = 60;
      goto LABEL_29;
    }
    while ( 1 )
    {
      if ( v20 && *v21 == 46 && *(v21 - 1) == 42 )
        *(v21 - 1) = 60;
      if ( *v21 == 63 )
        break;
      if ( *v21 == 42 )
        goto LABEL_45;
LABEL_27:
      ++v20;
      ++v21;
      if ( v20 >= LOWORD(PartName[0]) >> 1 )
        goto LABEL_28;
    }
    *v21 = 62;
LABEL_45:
    if ( v20 && *(v21 - 1) == 46 )
      *(v21 - 1) = 34;
    goto LABEL_27;
  }
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v19 == -1073741788 || v19 == -1073741772 )
    v19 = -1073741766;
  BaseSetLastNTError((unsigned int)v19);
  return -1;
}

```

## disassembly

```asm
0x180076e30  push    rbp
0x180076e32  push    rbx
0x180076e33  push    rsi
0x180076e34  push    rdi
0x180076e35  push    r12
0x180076e37  push    r14
0x180076e39  lea     rbp, [rsp-288h]
0x180076e41  sub     rsp, 388h
0x180076e48  mov     rax, cs:__security_cookie
0x180076e4f  xor     rax, rsp
0x180076e52  mov     [rbp+2B0h+var_40], rax
0x180076e59  xorps   xmm0, xmm0
0x180076e5c  mov     rsi, r8
0x180076e5f  mov     r12d, edx
0x180076e62  mov     rbx, rcx
0x180076e65  xorps   xmm1, xmm1
0x180076e68  lea     rcx, [rbp+2B0h+var_2B0]; void *
0x180076e6c  movups  xmmword ptr [rbp+2B0h+ObjectAttributes.ObjectName], xmm0
0x180076e70  xor     r14d, r14d
0x180076e73  xor     eax, eax
0x180076e75  xor     edx, edx; Val
0x180076e77  mov     [rsp+3B0h+FileHandle], r14
0x180076e7c  mov     r8d, 268h; Size
0x180076e82  mov     edi, r9d
0x180076e85  movups  xmmword ptr [rbp+2B0h+ObjectAttributes+1Ch], xmm0
0x180076e89  movups  xmmword ptr [rbp+2B0h+ObjectAttributes.Length], xmm0
0x180076e8d  movups  xmmword ptr [rsp+3B0h+PartName], xmm0
0x180076e92  movups  xmmword ptr [rsp+3B0h+NtName.Length], xmm1
0x180076e97  movups  xmmword ptr [rbp+2B0h+IoStatusBlock], xmm0
0x180076e9b  call    memset_0
0x180076ea0  mov     [rbp+2B0h+var_304], r14d
0x180076ea4  xorps   xmm0, xmm0
0x180076ea7  movups  xmmword ptr [rbp+2B0h+RelativeName.RelativeName.Length], xmm0
0x180076eab  movups  xmmword ptr [rbp+2B0h+RelativeName.ContainingDirectory], xmm0
0x180076eaf  movups  xmmword ptr [rsp+3B0h+DestinationString.Length], xmm0
0x180076eb4  cmp     r12d, 2
0x180076eb8  jge     loc_1800774E2
0x180076ebe  cmp     edi, 2
0x180076ec1  jge     loc_1800774E2
0x180076ec7  mov     r14d, [rbp+2B0h+arg_28]
0x180076ece  test    r14d, 0FFFFFFF8h
0x180076ed5  jnz     loc_1800774E2
0x180076edb  mov     rdx, rbx; SourceString
0x180076ede  mov     [rsp+3B0h+var_30], r15
0x180076ee6  lea     rcx, [rsp+3B0h+DestinationString]; DestinationString
0x180076eeb  call    cs:__imp_RtlInitUnicodeString
0x180076ef1  movzx   eax, [rsp+3B0h+DestinationString.Length]
0x180076ef6  test    ax, ax
0x180076ef9  jnz     loc_180077280
0x180076eff  xor     r15b, r15b
0x180076f02  lea     r9, [rbp+2B0h+RelativeName]; RelativeName
0x180076f06  mov     rcx, rbx; DosName
0x180076f09  lea     r8, [rsp+3B0h+PartName+8]; PartName
0x180076f0e  lea     rdx, [rsp+3B0h+NtName]; NtName
0x180076f13  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180076f19  test    al, al
0x180076f1b  jz      loc_1800773C7
0x180076f21  mov     rcx, [rbp+2B0h+DestinationString.Buffer]; Name
0x180076f25  mov     [rsp+3B0h+arg_8], r13
0x180076f2d  mov     r13, [rsp+3B0h+NtName.Buffer]
0x180076f32  call    cs:__imp_RtlIsDosDeviceName_U
0x180076f38  mov     ebx, eax
0x180076f3a  test    eax, eax
0x180076f3c  jnz     loc_180077445
0x180076f42  mov     rdx, [rsp+3B0h+PartName+8]
0x180076f47  movzx   r8d, word ptr [rsp+3B0h+PartName+8]
0x180076f4d  movzx   r9d, word ptr [rsp+3B0h+NtName.Buffer]
0x180076f53  movzx   eax, [rsp+3B0h+NtName.Length]
0x180076f58  test    rdx, rdx
0x180076f5b  jz      loc_1800773DE
0x180076f61  movzx   ecx, r9w
0x180076f65  sub     cx, r8w
0x180076f69  add     cx, ax
0x180076f6c  cmp     [rbp+2B0h+RelativeName.RelativeName.Length], 0
0x180076f71  mov     word ptr [rsp+3B0h+PartName], cx
0x180076f76  mov     word ptr [rsp+3B0h+PartName+2], cx
0x180076f7b  jnz     loc_18007741E
0x180076f81  mov     [rbp+2B0h+RelativeName.ContainingDirectory], 0
0x180076f89  test    rdx, rdx
0x180076f8c  jz      short loc_180076FA0
0x180076f8e  movzx   eax, r8w
0x180076f92  sub     ax, r9w
0x180076f96  mov     [rsp+3B0h+NtName.MaximumLength], ax
0x180076f9b  mov     [rsp+3B0h+NtName.Length], ax
0x180076fa0  movzx   edx, ax
0x180076fa3  shr     edx, 1
0x180076fa5  cmp     edx, 2
0x180076fa8  jnb     loc_18007729E
0x180076fae  xor     dil, dil
0x180076fb1  mov     rax, [rbp+2B0h+RelativeName.ContainingDirectory]
0x180076fb5  lea     r9, [rbp+2B0h+IoStatusBlock]; IoStatusBlock
0x180076fb9  mov     [rbp+2B0h+ObjectAttributes.RootDirectory], rax
0x180076fbd  lea     r8, [rbp+2B0h+ObjectAttributes]; ObjectAttributes
0x180076fc1  movzx   eax, r14b
0x180076fc5  mov     [rsp+3B0h+OpenOptions], 4021h; OpenOptions
0x180076fcd  not     al
0x180076fcf  mov     [rbp+2B0h+ObjectAttributes.Length], 30h ; '0'
0x180076fd6  and     eax, 1
0x180076fd9  mov     [rsp+3B0h+ShareAccess], 7; ShareAccess
0x180076fe1  shl     eax, 6
0x180076fe4  lea     rcx, [rsp+3B0h+FileHandle]; FileHandle
0x180076fe9  mov     [rbp+2B0h+ObjectAttributes.Attributes], eax
0x180076fec  xorps   xmm0, xmm0
0x180076fef  lea     rax, [rsp+3B0h+NtName]
0x180076ff4  mov     edx, 100001h; DesiredAccess
0x180076ff9  mov     [rbp+2B0h+ObjectAttributes.ObjectName], rax
0x180076ffd  movdqu  xmmword ptr [rbp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180077002  call    cs:__imp_NtOpenFile
0x180077008  mov     ebx, eax
0x18007700a  test    dil, dil
0x18007700d  jz      short loc_180077025
0x18007700f  cmp     eax, 0C0000103h
0x180077014  jz      loc_1800773E5
0x18007701a  cmp     eax, 0C000000Dh
0x18007701f  jz      loc_1800773E5
0x180077025  test    ebx, ebx
0x180077027  js      loc_180077344
0x18007702d  cmp     word ptr [rsp+3B0h+PartName], 0
0x180077033  jz      loc_18007738A
0x180077039  cmp     word ptr [rsp+3B0h+PartName], 6
0x18007703f  jz      loc_1800772C9
0x180077045  movzx   ecx, word ptr [rsp+3B0h+PartName]
0x18007704a  xor     eax, eax
0x18007704c  mov     rdx, [rsp+3B0h+PartName+8]
0x180077051  mov     r10d, 3Ch ; '<'
0x180077057  test    ecx, 0FFFFFFFEh
0x18007705d  jbe     short loc_180077096
0x18007705f  nop
0x180077060  test    eax, eax
0x180077062  jz      short loc_18007706E
0x180077064  cmp     word ptr [rdx], 2Eh ; '.'
0x180077068  jz      loc_1800772FA
0x18007706e  movzx   ecx, word ptr [rdx]
0x180077071  cmp     cx, 3Fh ; '?'
0x180077075  jz      loc_18007725D
0x18007707b  cmp     cx, 2Ah ; '*'
0x18007707f  jz      loc_180077262
0x180077085  movzx   ecx, word ptr [rsp+3B0h+PartName]
0x18007708a  inc     eax
0x18007708c  shr     ecx, 1
0x18007708e  add     rdx, 2
0x180077092  cmp     eax, ecx
0x180077094  jb      short loc_180077060
0x180077096  test    r15b, r15b
0x180077099  jnz     loc_1800774A0
0x18007709f  mov     edx, r14d
0x1800770a2  mov     eax, r12d
0x1800770a5  and     edx, 4
0x1800770a8  or      edx, 1
0x1800770ab  add     edx, edx
0x1800770ad  neg     eax
0x1800770af  lea     rax, [rsp+3B0h+PartName]
0x1800770b4  mov     [rsp+3B0h+var_368], rax
0x1800770b9  sbb     ecx, ecx
0x1800770bb  mov     [rsp+3B0h+var_370], edx
0x1800770bf  lea     rax, [rbp+2B0h+var_2B0]
0x1800770c3  add     ecx, 3
0x1800770c6  xor     r9d, r9d
0x1800770c9  mov     [rsp+3B0h+var_378], ecx
0x1800770cd  xor     r8d, r8d
0x1800770d0  mov     rcx, [rsp+3B0h+FileHandle]
0x1800770d5  xor     edx, edx
0x1800770d7  mov     [rsp+3B0h+var_380], 268h
0x1800770df  mov     qword ptr [rsp+3B0h+OpenOptions], rax
0x1800770e4  lea     rax, [rbp+2B0h+IoStatusBlock]
0x1800770e8  mov     qword ptr [rsp+3B0h+ShareAccess], rax
0x1800770ed  call    cs:__imp_NtQueryDirectoryFileEx
0x1800770f3  lea     rcx, [rbp+2B0h+RelativeName]; RelativeName
0x1800770f7  mov     ebx, eax
0x1800770f9  call    cs:__imp_RtlReleaseRelativeName
0x1800770ff  mov     rcx, gs:60h
0x180077108  mov     r8, r13; P
0x18007710b  xor     edx, edx; Flags
0x18007710d  mov     rcx, [rcx+30h]; HeapHandle
0x180077111  call    cs:__imp_RtlFreeHeap
0x180077117  test    ebx, ebx
0x180077119  js      loc_180077326
0x18007711f  mov     rax, [rbp+2B0h+var_2A8]
0x180077123  lea     rdx, [rbp+2B0h+var_26C]
0x180077127  mov     rdi, [rbp+2B0h+var_278]
0x18007712b  mov     ecx, 206h
0x180077130  mov     [rsi+4], rax
0x180077134  mov     rax, [rbp+2B0h+var_2A0]
0x180077138  mov     [rsi+0Ch], rax
0x18007713c  mov     rax, [rbp+2B0h+var_298]
0x180077140  mov     [rsi+14h], rax
0x180077144  mov     eax, [rbp+2B0h+var_284]
0x180077147  mov     [rsi+1Ch], eax
0x18007714a  mov     eax, [rbp+2B0h+var_288]
0x18007714d  mov     [rsi+20h], eax
0x180077150  mov     eax, dword ptr [rbp+2B0h+var_278+4]
0x180077153  cmp     eax, ecx
0x180077155  mov     [rsi], edi
0x180077157  cmova   eax, ecx
0x18007715a  test    r12d, r12d
0x18007715d  mov     ebx, eax
0x18007715f  lea     rcx, [rsi+2Ch]; void *
0x180077163  lea     rax, [rbp+2B0h+Src]
0x180077167  mov     r8d, ebx; Size
0x18007716a  cmovz   rdx, rax; Src
0x18007716e  call    memcpy_0
0x180077173  shr     rbx, 1
0x180077176  xor     r15d, r15d
0x180077179  mov     [rsi+rbx*2+2Ch], r15w
0x18007717f  test    r12d, r12d
0x180077182  jnz     loc_18007730F
0x180077188  movsx   eax, [rbp+2B0h+var_26C]
0x18007718c  cmp     al, 1Ah
0x18007718e  ja      loc_18007731C
0x180077194  mov     ecx, eax
0x180077196  cmp     eax, 18h
0x180077199  jnb     loc_18007731C
0x18007719f  mov     ebx, ecx
0x1800771a1  lea     rdx, [rbp+2B0h+var_26A]; Src
0x1800771a5  mov     r8d, ebx; Size
0x1800771a8  lea     rcx, [rsi+234h]; void *
0x1800771af  call    memcpy_0
0x1800771b4  shr     rbx, 1
0x1800771b7  mov     [rsi+rbx*2+234h], r15w
0x1800771c0  bt      edi, 0Ah
0x1800771c4  jnb     short loc_1800771CC
0x1800771c6  mov     eax, [rbp+2B0h+var_270]
0x1800771c9  mov     [rsi+24h], eax
0x1800771cc  mov     rcx, gs:60h
0x1800771d5  mov     r8d, 50h ; 'P'; Size
0x1800771db  mov     edx, cs:KernelBaseGlobalData
0x1800771e1  mov     rdi, [rsp+3B0h+FileHandle]
0x1800771e6  add     edx, 0C0000h; Flags
0x1800771ec  mov     rcx, [rcx+30h]; HeapHandle
0x1800771f0  call    cs:__imp_RtlAllocateHeap
0x1800771f6  mov     rbx, rax
0x1800771f9  test    rax, rax
0x1800771fc  jz      loc_1800774CD
0x180077202  lea     rcx, [rax+28h]; CriticalSection
0x180077206  mov     [rax], rdi
0x180077209  mov     [rax+8], r15
0x18007720d  mov     [rax+10h], r15
0x180077211  mov     [rax+18h], r15
0x180077215  mov     [rax+20h], r12d
0x180077219  mov     [rax+24h], r14d
0x18007721d  call    cs:__imp_RtlInitializeCriticalSection
0x180077223  test    eax, eax
0x180077225  js      loc_1800774B5
0x18007722b  mov     rax, rbx
0x18007722e  mov     r13, [rsp+3B0h+arg_8]
0x180077236  mov     r15, [rsp+3B0h+var_30]
0x18007723e  mov     rcx, [rbp+2B0h+var_40]
0x180077245  xor     rcx, rsp; StackCookie
0x180077248  call    __security_check_cookie
0x18007724d  add     rsp, 388h
0x180077254  pop     r14
0x180077256  pop     r12
0x180077258  pop     rdi
0x180077259  pop     rsi
0x18007725a  pop     rbx
0x18007725b  pop     rbp
0x18007725c  retn
0x18007725d  mov     word ptr [rdx], 3Eh ; '>'
0x180077262  test    eax, eax
0x180077264  jz      loc_180077085
0x18007726a  cmp     word ptr [rdx-2], 2Eh ; '.'
0x18007726f  jnz     loc_180077085
0x180077275  mov     word ptr [rdx-2], 22h ; '"'
0x18007727b  jmp     loc_180077085
0x180077280  mov     rcx, rax
0x180077283  mov     rax, [rbp+2B0h+DestinationString.Buffer]
0x180077287  shr     rcx, 1
0x18007728a  cmp     word ptr [rax+rcx*2-2], 2Eh ; '.'
0x180077290  jnz     loc_180076EFF
0x180077296  mov     r15b, 1
0x180077299  jmp     loc_180076F02
0x18007729e  mov     r8, [rsp+3B0h+NtName.Buffer]
0x1800772a3  lea     eax, [rdx-2]
0x1800772a6  cmp     word ptr [r8+rax*2], 3Ah ; ':'
0x1800772ac  jz      loc_180076FAE
0x1800772b2  lea     eax, [rdx-1]
0x1800772b5  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x1800772bb  jnz     loc_180076FAE
0x1800772c1  mov     dil, 1
0x1800772c4  jmp     loc_180076FB1
0x1800772c9  mov     rcx, [rsp+3B0h+PartName+8]; Source1
0x1800772ce  lea     rdx, asc_180294BD0; "*.*"
0x1800772d5  mov     r8d, 6; Length
0x1800772db  call    cs:__imp_RtlCompareMemory
0x1800772e1  cmp     rax, 6
0x1800772e5  jnz     loc_180077045
0x1800772eb  mov     eax, 2
0x1800772f0  mov     word ptr [rsp+3B0h+PartName], ax
0x1800772f5  jmp     loc_18007709F
0x1800772fa  cmp     word ptr [rdx-2], 2Ah ; '*'
0x1800772ff  jnz     loc_18007706E
0x180077305  mov     [rdx-2], r10w
0x18007730a  jmp     loc_18007706E
0x18007730f  mov     [rsi+234h], r15w
0x180077317  jmp     loc_1800771C0
0x18007731c  mov     ecx, 18h
0x180077321  jmp     loc_18007719F
0x180077326  mov     rcx, [rsp+3B0h+FileHandle]; Handle
0x18007732b  call    cs:__imp_NtClose
0x180077331  mov     ecx, ebx
  ... truncated ...
```
