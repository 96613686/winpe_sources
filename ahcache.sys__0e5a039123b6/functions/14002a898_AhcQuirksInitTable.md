# AhcQuirksInitTable

- ea: `0x14002a898`
- end: `0x14002ad29`
- name: `AhcQuirksInitTable`
- size: `1169`
- prototype: `__int64 __fastcall(__int64, PVOID *)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140043858`
- `0x1400438c4`

## callees

- `0x1400021a0`
- `0x1400030d0`
- `0x140007b40`
- `0x14002642c`
- `0x14002726c`
- `0x14002a898`
- `0x14003e364`
- `0x140041d6c`
- `0x140042ad4`
- `0x140044fc8`
- `0x140045d44`
- `0x140054478`
- `0x14005498c`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14002ac9b`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14002ac9b`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14002acce`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14002acce`
- `ntoskrnl!MmIsUserAddress` at `0x14002ac70`
- `ntoskrnl!MmIsUserAddress` at `0x14002ac70`
- `ntoskrnl!ZwClose` at `0x14002a937`
- `ntoskrnl!ZwClose` at `0x14002acaf`
- `ntoskrnl!ZwClose` at `0x14002a937`
- `ntoskrnl!ZwClose` at `0x14002acaf`
- `ntoskrnl!ZwCreateSection` at `0x14002ab31`
- `ntoskrnl!ZwCreateSection` at `0x14002ab31`
- `ntoskrnl!ZwMapViewOfSection` at `0x14002aba9`
- `ntoskrnl!ZwMapViewOfSection` at `0x14002aba9`
- `ntoskrnl!MmSecureVirtualMemory` at `0x14002abd8`
- `ntoskrnl!MmSecureVirtualMemory` at `0x14002abd8`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x14002acdf`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x14002acdf`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x14002a95c`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x14002ad10`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x14002a95c`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x14002ad10`

## string_xrefs

- `0x14002a90c`: `Failed to allocate native sdb path`
- `0x14002ab47`: `Failed to create quirks table section with size %llu: 0x%x`

## pseudocode

```c
__int64 __fastcall AhcQuirksInitTable(__int64 a1, PVOID *a2)
{
  void *v3; // rsi
  __int64 v4; // rdi
  __int64 v5; // r12
  int PathSystemSdbAlloc; // eax
  __int64 v7; // rdx
  __int64 v8; // r13
  __int64 v9; // r14
  int v10; // ebx
  HANDLE v11; // rcx
  __int64 v12; // rcx
  int MergeStubPath; // eax
  __int64 v15; // rdx
  NTSTATUS Count; // eax
  const char *v17; // r9
  __int64 v18; // r8
  NTSTATUS v19; // eax
  __int64 v20; // rcx
  HANDLE v21; // r13
  __int64 v22; // rax
  int v23; // eax
  struct _ERESOURCE *v24; // rcx
  ULONG SectionPageProtection[2]; // [rsp+20h] [rbp-69h]
  union _LARGE_INTEGER MaximumSize; // [rsp+50h] [rbp-39h] BYREF
  PVOID BaseAddress; // [rsp+58h] [rbp-31h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-29h] BYREF
  __int64 v29; // [rsp+68h] [rbp-21h] BYREF
  __int64 v30; // [rsp+70h] [rbp-19h] BYREF
  ULONG_PTR ViewSize; // [rsp+78h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int16 v34; // [rsp+100h] [rbp+77h] BYREF
  unsigned __int16 v35; // [rsp+108h] [rbp+7Fh] BYREF

  BaseAddress = 0;
  ViewSize = 0;
  v35 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v3 = 0;
  v4 = 0;
  v34 = 0;
  v5 = 0;
  Handle = 0;
  MaximumSize.QuadPart = 0;
  v30 = 0;
  v29 = 0;
  PathSystemSdbAlloc = SdbGetPathSystemSdbAlloc(&v30, a2, 0);
  v8 = v30;
  if ( !PathSystemSdbAlloc )
  {
    v9 = 0;
    AslLogCallPrintf(1, "AhcQuirksInitTable", 77, "Failed to allocate native sdb path");
    v10 = -1073741801;
    goto LABEL_3;
  }
  v9 = SdbOpenDatabaseEx(v30, v7, 0);
  if ( !v9 )
  {
    AslLogCallPrintf(1, "AhcQuirksInitTable", 84, "Failed to initialize quirks database");
LABEL_19:
    v10 = -1073741823;
    goto LABEL_3;
  }
  MergeStubPath = SdbGetMergeStubPath(&v29, v8);
  v5 = v29;
  v10 = MergeStubPath;
  if ( MergeStubPath != -1073741772 )
  {
    if ( MergeStubPath < 0 )
    {
      AslLogCallPrintf(1, "AhcQuirksInitTable", 95, "Unable to find merge stub database [%x]", MergeStubPath);
      goto LABEL_3;
    }
    if ( !(unsigned int)SdbPdbIsRedirected(v9, v8) )
    {
      v4 = SdbOpenDatabaseEx(v5, v15, 0);
      if ( !v4 )
      {
        AslLogCallPrintf(1, "AhcQuirksInitTable", 106, "Failed to initialize stub database");
        v10 = -1073741811;
        goto LABEL_3;
      }
    }
  }
  Count = QuirksGetCount(v9, v4, &v35, &v34);
  v10 = Count;
  if ( Count < 0 )
  {
    v17 = "Failed to get quirks count from the database: 0x%x";
    v18 = 115;
LABEL_28:
    SectionPageProtection[0] = Count;
    AslLogCallPrintf(1, "AhcQuirksInitTable", v18, v17, *(_QWORD *)SectionPageProtection);
    goto LABEL_3;
  }
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  MaximumSize.QuadPart = 556LL * v35 + 24 + 16LL * v34;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  v19 = ZwCreateSection(&Handle, 6u, &ObjectAttributes, &MaximumSize, 4u, 0x8000000u, 0);
  v10 = v19;
  if ( v19 >= 0 )
  {
    Count = ZwMapViewOfSection(
              Handle,
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              &BaseAddress,
              0,
              MaximumSize.QuadPart,
              0,
              &ViewSize,
              ViewUnmap,
              0,
              4u);
    v10 = Count;
    if ( Count < 0 )
    {
      v17 = "Failed to map quirks table: 0x%x";
      v18 = 169;
      goto LABEL_28;
    }
    v21 = MmSecureVirtualMemory(BaseAddress, MaximumSize.QuadPart, 4u);
    if ( !v21 )
    {
      AslLogCallPrintf(1, "AhcQuirksInitTable", 183, "Unable to secure quirks table before initializing it");
      goto LABEL_19;
    }
    v22 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))AslAlloc)(v20, (union _LARGE_INTEGER)MaximumSize.QuadPart, 1);
    v3 = (void *)v22;
    if ( v22 )
    {
      *(_WORD *)(v22 + 2) = v34;
      *(_DWORD *)(v22 + 4) = MaximumSize.LowPart;
      *(_WORD *)v22 = v35;
      v23 = QuirksLoadFromDb(v9, v4, v22);
      v10 = v23;
      if ( v23 >= 0 )
      {
        if ( (unsigned __int8)MmIsUserAddress(BaseAddress) )
          RtlCopyToUser(BaseAddress, v3, MaximumSize.QuadPart);
        else
          memmove(BaseAddress, v3, MaximumSize.QuadPart);
        ExEnterCriticalRegionAndAcquireResourceExclusive(*(PERESOURCE *)(a1 + 16));
        if ( *(_QWORD *)a1 )
          ZwClose(*(HANDLE *)a1);
        v24 = *(struct _ERESOURCE **)(a1 + 16);
        *(_QWORD *)a1 = Handle;
        *(union _LARGE_INTEGER *)(a1 + 8) = MaximumSize;
        ExReleaseResourceAndLeaveCriticalRegion(v24);
        v10 = 0;
      }
      else
      {
        AslLogCallPrintf(1, "AhcQuirksInitTable", 206, "Unable to load quirks from database: 0x%x", v23);
      }
    }
    else
    {
      v10 = -1073741801;
    }
    MmUnsecureVirtualMemory(v21);
    if ( v10 >= 0 )
    {
      if ( a2 )
      {
        *a2 = BaseAddress;
      }
      else
      {
        ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
        BaseAddress = 0;
      }
LABEL_9:
      SdbCloseDatabaseRead(v9);
      goto LABEL_10;
    }
  }
  else
  {
    AslLogCallPrintf(
      1,
      "AhcQuirksInitTable",
      148,
      "Failed to create quirks table section with size %llu: 0x%x",
      MaximumSize.QuadPart,
      v19);
  }
LABEL_3:
  v11 = Handle;
  if ( Handle )
  {
    ZwClose(Handle);
    Handle = 0;
  }
  if ( v10 < 0 && BaseAddress )
  {
    ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
    BaseAddress = 0;
  }
  if ( v9 )
    goto LABEL_9;
LABEL_10:
  if ( v4 )
    SdbCloseDatabaseRead(v4);
  if ( v3 )
    AslFree(v11, v3);
  AslFree(v11, v30);
  if ( v5 )
    AslFree(v12, v5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14002a898  mov     [rsp-8+arg_0], rbx
0x14002a89d  mov     [rsp-8+arg_8], rdx
0x14002a8a2  push    rbp
0x14002a8a3  push    rsi
0x14002a8a4  push    rdi
0x14002a8a5  push    r12
0x14002a8a7  push    r13
0x14002a8a9  push    r14
0x14002a8ab  push    r15
0x14002a8ad  lea     rbp, [rsp-27h]
0x14002a8b2  sub     rsp, 0B0h
0x14002a8b9  xor     ebx, ebx
0x14002a8bb  xorps   xmm0, xmm0
0x14002a8be  mov     r15, rcx
0x14002a8c1  mov     [rbp+57h+BaseAddress], rbx
0x14002a8c5  lea     rcx, [rbp+57h+var_70]
0x14002a8c9  mov     [rbp+57h+ViewSize], rbx
0x14002a8cd  xor     r8d, r8d
0x14002a8d0  mov     [rbp+57h+arg_18], bx
0x14002a8d4  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14002a8d8  mov     esi, ebx
0x14002a8da  mov     edi, ebx
0x14002a8dc  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14002a8e0  mov     [rbp+57h+arg_10], bx
0x14002a8e4  mov     r12d, ebx
0x14002a8e7  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002a8eb  mov     [rbp+57h+Handle], rbx
0x14002a8ef  mov     qword ptr [rbp+57h+MaximumSize], rbx
0x14002a8f3  mov     [rbp+57h+var_70], rbx
0x14002a8f7  mov     [rbp+57h+var_78], rbx
0x14002a8fb  call    SdbGetPathSystemSdbAlloc
0x14002a900  mov     r13, [rbp+57h+var_70]
0x14002a904  test    eax, eax
0x14002a906  jnz     loc_14002A9CB
0x14002a90c  lea     r9, aFailedToAlloca_20; "Failed to allocate native sdb path"
0x14002a913  mov     r14d, ebx
0x14002a916  lea     r8d, [rbx+4Dh]
0x14002a91a  lea     rdx, aAhcquirksinitt; "AhcQuirksInitTable"
0x14002a921  lea     ecx, [rbx+1]
0x14002a924  call    AslLogCallPrintf
0x14002a929  mov     ebx, 0C0000017h
0x14002a92e  mov     rcx, [rbp+57h+Handle]; Handle
0x14002a932  test    rcx, rcx
0x14002a935  jz      short loc_14002A94B
0x14002a937  call    cs:__imp_ZwClose
0x14002a93e  nop     dword ptr [rax+rax+00h]
0x14002a943  mov     [rbp+57h+Handle], 0
0x14002a94b  test    ebx, ebx
0x14002a94d  jns     short loc_14002A970
0x14002a94f  mov     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x14002a953  test    rdx, rdx
0x14002a956  jz      short loc_14002A970
0x14002a958  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14002a95c  call    cs:__imp_ZwUnmapViewOfSection
0x14002a963  nop     dword ptr [rax+rax+00h]
0x14002a968  mov     [rbp+57h+BaseAddress], 0
0x14002a970  test    r14, r14
0x14002a973  jz      short loc_14002A97D
0x14002a975  mov     rcx, r14
0x14002a978  call    SdbCloseDatabaseRead
0x14002a97d  test    rdi, rdi
0x14002a980  jz      short loc_14002A98A
0x14002a982  mov     rcx, rdi
0x14002a985  call    SdbCloseDatabaseRead
0x14002a98a  test    rsi, rsi
0x14002a98d  jz      short loc_14002A997
0x14002a98f  mov     rdx, rsi
0x14002a992  call    AslFree
0x14002a997  mov     rdx, [rbp+57h+var_70]
0x14002a99b  call    AslFree
0x14002a9a0  test    r12, r12
0x14002a9a3  jz      short loc_14002A9AD
0x14002a9a5  mov     rdx, r12
0x14002a9a8  call    AslFree
0x14002a9ad  mov     eax, ebx
0x14002a9af  mov     rbx, [rsp+0E0h+arg_0]
0x14002a9b7  add     rsp, 0B0h
0x14002a9be  pop     r15
0x14002a9c0  pop     r14
0x14002a9c2  pop     r13
0x14002a9c4  pop     r12
0x14002a9c6  pop     rdi
0x14002a9c7  pop     rsi
0x14002a9c8  pop     rbp
0x14002a9c9  retn
0x14002a9cb  xor     r8d, r8d
0x14002a9ce  mov     rcx, r13
0x14002a9d1  call    SdbOpenDatabaseEx
0x14002a9d6  mov     r14, rax
0x14002a9d9  test    rax, rax
0x14002a9dc  jnz     short loc_14002AA04
0x14002a9de  lea     r9, aFailedToInitia_6; "Failed to initialize quirks database"
0x14002a9e5  lea     r8d, [rax+54h]
0x14002a9e9  lea     rdx, aAhcquirksinitt; "AhcQuirksInitTable"
0x14002a9f0  mov     ecx, 1
0x14002a9f5  call    AslLogCallPrintf
0x14002a9fa  mov     ebx, 0C0000001h
0x14002a9ff  jmp     loc_14002A92E
0x14002aa04  mov     rdx, r13
0x14002aa07  lea     rcx, [rbp+57h+var_78]
0x14002aa0b  call    SdbGetMergeStubPath
0x14002aa10  mov     r12, [rbp+57h+var_78]
0x14002aa14  mov     ebx, eax
0x14002aa16  cmp     eax, 0C0000034h
0x14002aa1b  jz      short loc_14002AA8D
0x14002aa1d  test    eax, eax
0x14002aa1f  jns     short loc_14002AA47
0x14002aa21  mov     r8d, 5Fh ; '_'
0x14002aa27  mov     [rsp+0E0h+SectionPageProtection], eax
0x14002aa2b  lea     r9, aUnableToFindMe_0; "Unable to find merge stub database [%x]"
0x14002aa32  lea     rdx, aAhcquirksinitt; "AhcQuirksInitTable"
0x14002aa39  lea     ecx, [r8-5Eh]
0x14002aa3d  call    AslLogCallPrintf
0x14002aa42  jmp     loc_14002A92E
0x14002aa47  mov     rdx, r13
0x14002aa4a  mov     rcx, r14
0x14002aa4d  call    SdbPdbIsRedirected
0x14002aa52  test    eax, eax
0x14002aa54  jnz     short loc_14002AA8D
0x14002aa56  xor     r8d, r8d
0x14002aa59  mov     rcx, r12
0x14002aa5c  call    SdbOpenDatabaseEx
0x14002aa61  mov     rdi, rax
0x14002aa64  test    rax, rax
0x14002aa67  jnz     short loc_14002AA8D
0x14002aa69  lea     r9, aFailedToInitia_14; "Failed to initialize stub database"
0x14002aa70  lea     r8d, [rax+6Ah]
0x14002aa74  lea     rdx, aAhcquirksinitt; "AhcQuirksInitTable"
0x14002aa7b  lea     ecx, [rax+1]
0x14002aa7e  call    AslLogCallPrintf
0x14002aa83  mov     ebx, 0C000000Dh
0x14002aa88  jmp     loc_14002A92E
0x14002aa8d  lea     r9, [rbp+57h+arg_10]
0x14002aa91  mov     rdx, rdi
0x14002aa94  lea     r8, [rbp+57h+arg_18]
0x14002aa98  mov     rcx, r14
0x14002aa9b  call    QuirksGetCount
0x14002aaa0  mov     ebx, eax
0x14002aaa2  test    eax, eax
0x14002aaa4  jns     short loc_14002AACD
0x14002aaa6  lea     r9, aFailedToGetQui; "Failed to get quirks count from the dat"...
0x14002aaad  mov     r8d, 73h ; 's'
0x14002aab3  lea     rdx, aAhcquirksinitt; "AhcQuirksInitTable"
0x14002aaba  mov     [rsp+0E0h+SectionPageProtection], eax
0x14002aabe  mov     ecx, 1
0x14002aac3  call    AslLogCallPrintf
0x14002aac8  jmp     loc_14002A92E
0x14002aacd  movzx   eax, [rbp+57h+arg_18]
0x14002aad1  lea     r9, [rbp+57h+MaximumSize]; MaximumSize
0x14002aad5  imul    rcx, rax, 22Ch
0x14002aadc  xorps   xmm0, xmm0
0x14002aadf  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002aae4  movzx   eax, [rbp+57h+arg_10]
0x14002aae8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002aaec  add     rcx, 18h
0x14002aaf0  shl     rax, 4
0x14002aaf4  add     rax, rcx
0x14002aaf7  mov     [rsp+0E0h+FileHandle], rsi; FileHandle
0x14002aafc  mov     r13d, 4
0x14002ab02  mov     [rsp+0E0h+AllocationAttributes], 8000000h; AllocationAttributes
0x14002ab0a  lea     rcx, [rbp+57h+Handle]; SectionHandle
0x14002ab0e  mov     qword ptr [rbp+57h+MaximumSize], rax
0x14002ab12  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002ab19  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x14002ab1d  lea     edx, [r13+2]; DesiredAccess
0x14002ab21  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14002ab28  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x14002ab2c  mov     [rsp+0E0h+SectionPageProtection], r13d; SectionPageProtection
0x14002ab31  call    cs:__imp_ZwCreateSection
0x14002ab38  nop     dword ptr [rax+rax+00h]
0x14002ab3d  mov     ebx, eax
0x14002ab3f  test    eax, eax
0x14002ab41  jns     short loc_14002AB72
0x14002ab43  mov     [rsp+0E0h+AllocationAttributes], eax
0x14002ab47  lea     r9, aFailedToCreate_9; "Failed to create quirks table section w"...
0x14002ab4e  mov     rax, qword ptr [rbp+57h+MaximumSize]
0x14002ab52  lea     rdx, aAhcquirksinitt; "AhcQuirksInitTable"
0x14002ab59  mov     r8d, 94h
0x14002ab5f  mov     qword ptr [rsp+0E0h+SectionPageProtection], rax
0x14002ab64  lea     ecx, [r13-3]
0x14002ab68  call    AslLogCallPrintf
0x14002ab6d  jmp     loc_14002A92E
0x14002ab72  mov     rcx, [rbp+57h+Handle]; SectionHandle
0x14002ab76  lea     rax, [rbp+57h+ViewSize]
0x14002ab7a  mov     [rsp+0E0h+Win32Protect], r13d; Win32Protect
0x14002ab7f  lea     r8, [rbp+57h+BaseAddress]; BaseAddress
0x14002ab83  mov     [rsp+0E0h+AllocationType], esi; AllocationType
0x14002ab87  xor     r9d, r9d; ZeroBits
0x14002ab8a  mov     [rsp+0E0h+InheritDisposition], 2; InheritDisposition
0x14002ab92  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14002ab96  mov     [rsp+0E0h+FileHandle], rax; ViewSize
0x14002ab9b  mov     rax, qword ptr [rbp+57h+MaximumSize]
0x14002ab9f  mov     qword ptr [rsp+0E0h+AllocationAttributes], rsi; SectionOffset
0x14002aba4  mov     qword ptr [rsp+0E0h+SectionPageProtection], rax; CommitSize
0x14002aba9  call    cs:__imp_ZwMapViewOfSection
0x14002abb0  nop     dword ptr [rax+rax+00h]
0x14002abb5  mov     ebx, eax
0x14002abb7  test    eax, eax
0x14002abb9  jns     short loc_14002ABCD
0x14002abbb  lea     r9, aFailedToMapQui_1; "Failed to map quirks table: 0x%x"
0x14002abc2  mov     r8d, 0A9h
0x14002abc8  jmp     loc_14002AAB3
0x14002abcd  mov     rdx, qword ptr [rbp+57h+MaximumSize]; Size
0x14002abd1  mov     r8d, r13d; ProbeMode
0x14002abd4  mov     rcx, [rbp+57h+BaseAddress]; Address
0x14002abd8  call    cs:__imp_MmSecureVirtualMemory
0x14002abdf  nop     dword ptr [rax+rax+00h]
0x14002abe4  mov     r13, rax
0x14002abe7  test    rax, rax
0x14002abea  jnz     short loc_14002ABFE
0x14002abec  lea     r9, aUnableToSecure; "Unable to secure quirks table before in"...
0x14002abf3  mov     r8d, 0B7h
0x14002abf9  jmp     loc_14002A9E9
0x14002abfe  mov     rdx, qword ptr [rbp+57h+MaximumSize]
0x14002ac02  mov     r8d, 1
0x14002ac08  call    AslAlloc
0x14002ac0d  mov     rsi, rax
0x14002ac10  test    rax, rax
0x14002ac13  jnz     short loc_14002AC1F
0x14002ac15  mov     ebx, 0C0000017h
0x14002ac1a  jmp     loc_14002ACDC
0x14002ac1f  movzx   eax, [rbp+57h+arg_10]
0x14002ac23  mov     r8, rsi
0x14002ac26  mov     [rsi+2], ax
0x14002ac2a  mov     rdx, rdi
0x14002ac2d  mov     eax, dword ptr [rbp+57h+MaximumSize]
0x14002ac30  mov     rcx, r14
0x14002ac33  mov     [rsi+4], eax
0x14002ac36  movzx   eax, [rbp+57h+arg_18]
0x14002ac3a  mov     [rsi], ax
0x14002ac3d  call    QuirksLoadFromDb
0x14002ac42  mov     ebx, eax
0x14002ac44  test    eax, eax
0x14002ac46  jns     short loc_14002AC6C
0x14002ac48  lea     r9, aUnableToLoadQu; "Unable to load quirks from database: 0x"...
0x14002ac4f  mov     [rsp+0E0h+SectionPageProtection], eax
0x14002ac53  mov     r8d, 0CEh
0x14002ac59  lea     rdx, aAhcquirksinitt; "AhcQuirksInitTable"
0x14002ac60  mov     ecx, 1
0x14002ac65  call    AslLogCallPrintf
0x14002ac6a  jmp     short loc_14002ACDC
0x14002ac6c  mov     rcx, [rbp+57h+BaseAddress]
0x14002ac70  call    cs:__imp_MmIsUserAddress
0x14002ac77  nop     dword ptr [rax+rax+00h]
0x14002ac7c  mov     r8, qword ptr [rbp+57h+MaximumSize]; Size
0x14002ac80  mov     rdx, rsi; Src
0x14002ac83  mov     rcx, [rbp+57h+BaseAddress]; void *
0x14002ac87  test    al, al
0x14002ac89  jz      short loc_14002AC92
0x14002ac8b  call    RtlCopyToUser
0x14002ac90  jmp     short loc_14002AC97
0x14002ac92  call    memmove
0x14002ac97  mov     rcx, [r15+10h]; Resource
0x14002ac9b  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14002aca2  nop     dword ptr [rax+rax+00h]
0x14002aca7  mov     rcx, [r15]; Handle
0x14002acaa  test    rcx, rcx
0x14002acad  jz      short loc_14002ACBB
0x14002acaf  call    cs:__imp_ZwClose
0x14002acb6  nop     dword ptr [rax+rax+00h]
0x14002acbb  mov     rax, [rbp+57h+Handle]
0x14002acbf  mov     rcx, [r15+10h]; Resource
0x14002acc3  mov     [r15], rax
0x14002acc6  mov     rax, qword ptr [rbp+57h+MaximumSize]
0x14002acca  mov     [r15+8], rax
0x14002acce  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14002acd5  nop     dword ptr [rax+rax+00h]
0x14002acda  xor     ebx, ebx
0x14002acdc  mov     rcx, r13; SecureHandle
0x14002acdf  call    cs:__imp_MmUnsecureVirtualMemory
0x14002ace6  nop     dword ptr [rax+rax+00h]
0x14002aceb  test    ebx, ebx
0x14002aced  js      loc_14002A92E
0x14002acf3  mov     rcx, [rbp+57h+arg_8]
0x14002acf7  test    rcx, rcx
0x14002acfa  jz      short loc_14002AD08
0x14002acfc  mov     rax, [rbp+57h+BaseAddress]
0x14002ad00  mov     [rcx], rax
0x14002ad03  jmp     loc_14002A975
0x14002ad08  mov     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x14002ad0c  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14002ad10  call    cs:__imp_ZwUnmapViewOfSection
0x14002ad17  nop     dword ptr [rax+rax+00h]
0x14002ad1c  mov     [rbp+57h+BaseAddress], 0
0x14002ad24  jmp     loc_14002A975
```
