# QueryDosDeviceW

- ea: `0x1800ae970`
- end: `0x1800af227`
- name: `QueryDosDeviceW`
- size: `2231`
- prototype: `DWORD __stdcall(LPCWSTR lpDeviceName, LPWSTR lpTargetPath, DWORD ucchMax)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180045130`

## callees

- `0x1800134a0`
- `0x1800ae970`
- `0x1800af230`
- `0x180188eb9`
- `0x180188ee9`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800ae9e7`
- `ntdll!RtlInitUnicodeString` at `0x1800aea70`
- `ntdll!RtlInitUnicodeString` at `0x1800aee24`
- `ntdll!RtlInitUnicodeString` at `0x1800ae9e7`
- `ntdll!RtlInitUnicodeString` at `0x1800aea70`
- `ntdll!RtlInitUnicodeString` at `0x1800aee24`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1800aeaca`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1800aeaca`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800aeb37`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800aeb37`
- `ntdll!NtClose` at `0x1800aeb4b`
- `ntdll!NtClose` at `0x1800aef8b`
- `ntdll!NtClose` at `0x1800af1cb`
- `ntdll!NtClose` at `0x18018afd2`
- `ntdll!NtClose` at `0x1800aeb4b`
- `ntdll!NtClose` at `0x1800aef8b`
- `ntdll!NtClose` at `0x1800af1cb`
- `ntdll!NtClose` at `0x18018afd2`
- `ntdll!RtlFreeHeap` at `0x1800aef3d`
- `ntdll!RtlFreeHeap` at `0x1800af11c`
- `ntdll!RtlFreeHeap` at `0x1800af214`
- `ntdll!RtlFreeHeap` at `0x18018aff1`
- `ntdll!RtlFreeHeap` at `0x1800aef3d`
- `ntdll!RtlFreeHeap` at `0x1800af11c`
- `ntdll!RtlFreeHeap` at `0x1800af214`
- `ntdll!RtlFreeHeap` at `0x18018aff1`
- `ntdll!NtOpenDirectoryObject` at `0x1800aea39`
- `ntdll!NtOpenDirectoryObject` at `0x1800aee7a`
- `ntdll!NtOpenDirectoryObject` at `0x1800aea39`
- `ntdll!NtOpenDirectoryObject` at `0x1800aee7a`
- `ntdll!NtQueryDirectoryObject` at `0x1800aef0c`
- `ntdll!NtQueryDirectoryObject` at `0x1800af0ef`
- `ntdll!NtQueryDirectoryObject` at `0x1800aef0c`
- `ntdll!NtQueryDirectoryObject` at `0x1800af0ef`
- `ntdll!RtlCompareMemory` at `0x1800aebd1`
- `ntdll!RtlCompareMemory` at `0x1800aed31`
- `ntdll!RtlCompareMemory` at `0x1800aebd1`
- `ntdll!RtlCompareMemory` at `0x1800aed31`
- `ntdll!RtlAllocateHeap` at `0x1800aeece`
- `ntdll!RtlAllocateHeap` at `0x1800af0af`
- `ntdll!RtlAllocateHeap` at `0x1800aeece`
- `ntdll!RtlAllocateHeap` at `0x1800af0af`

## string_xrefs

- `0x1800aebe1`: `SymbolicLink`
- `0x1800aed41`: `SymbolicLink`

## pseudocode

```c
DWORD __stdcall QueryDosDeviceW(LPCWSTR lpDeviceName, LPWSTR lpTargetPath, DWORD ucchMax)
{
  unsigned __int16 *Heap; // r14
  NTSTATUS v7; // eax
  NTSTATUS v8; // esi
  DWORD v9; // edi
  __int64 v10; // rdi
  unsigned __int16 *v11; // rbx
  size_t v12; // r8
  int v13; // edx
  WCHAR *v14; // rcx
  DWORD v15; // ebx
  int i; // eax
  NTSTATUS v17; // eax
  ULONG Size; // [rsp+48h] [rbp-F0h]
  ULONG DataWritten; // [rsp+50h] [rbp-E8h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-E0h] BYREF
  int v22; // [rsp+60h] [rbp-D8h]
  unsigned __int16 *v23; // [rsp+68h] [rbp-D0h]
  ULONG Context; // [rsp+70h] [rbp-C8h] BYREF
  unsigned __int16 *v25; // [rsp+78h] [rbp-C0h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-B8h] BYREF
  HANDLE SymbolicLinkHandle; // [rsp+98h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-98h] BYREF
  size_t v29; // [rsp+D0h] [rbp-68h]
  LPWSTR v30; // [rsp+D8h] [rbp-60h]
  __int128 Source1; // [rsp+E8h] [rbp-50h] BYREF
  __int128 v32; // [rsp+F8h] [rbp-40h]
  int v33; // [rsp+158h] [rbp+20h]

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  Heap = 0;
  FileHandle = 0;
  SymbolicLinkHandle = 0;
  Context = 0;
  DataWritten = 0;
  Source1 = 0;
  v32 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\??");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenDirectoryObject(&FileHandle, 1u, &ObjectAttributes);
  v8 = v7;
  if ( v7 < 0 )
  {
    BaseSetLastNTError((unsigned int)v7);
    return 0;
  }
  v30 = lpTargetPath;
  v9 = 0;
  v23 = 0;
  if ( !lpDeviceName )
  {
    if ( *(_BYTE *)(BaseStaticServerData + 2508) == 1 )
      v8 = IsGlobalDeviceMap(FileHandle);
    v22 = 0;
    Source1 = 0;
    v32 = 0;
    if ( ucchMax > 0x7FFFFFFF )
    {
      Size = -1;
      v15 = -1;
    }
    else
    {
      Size = 2 * ucchMax;
      v15 = 2 * ucchMax;
    }
    for ( i = 0; ; LOWORD(i) = v33 + 1 )
    {
      v33 = i;
      Heap = 0;
      v23 = 0;
      if ( (unsigned __int16)i >= 3u )
        goto LABEL_24;
      Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v15);
      v23 = Heap;
      if ( !Heap )
      {
        v8 = -1073741670;
        goto LABEL_52;
      }
      v17 = NtQueryDirectoryObject(FileHandle, Heap, Size, 0, 1u, &Context, &DataWritten);
      v8 = v17;
      if ( v17 < 0 )
        break;
      if ( v17 != 261 )
      {
        v11 = Heap;
        v25 = Heap;
        while ( RtlCompareMemory(&Source1, v11, 0x20u) != 32 )
        {
          if ( !wcscmp_0(*((const wchar_t **)v11 + 3), L"SymbolicLink") )
          {
            if ( v9 > ucchMax )
              goto LABEL_14;
            v12 = *v11;
            v29 = v12 >> 1;
            if ( (unsigned int)(v12 >> 1) > ucchMax - v9 || ucchMax - v9 - (unsigned int)(v12 >> 1) < 2 )
              goto LABEL_14;
            memcpy_0(lpTargetPath, *((const void **)v11 + 1), v12);
            v13 = v29;
            v14 = &lpTargetPath[(unsigned int)v29];
            *v14 = 0;
            lpTargetPath = v14 + 1;
            v9 += v13 + 1;
            ++v22;
          }
          v11 += 16;
          v25 = v11;
        }
LABEL_24:
        if ( v8 == 261 )
          goto LABEL_14;
        goto LABEL_25;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      Heap = 0;
      v23 = 0;
      if ( v15 == -1 )
        goto LABEL_24;
      if ( ~v15 < v15 )
      {
        Size = -1;
        v15 = -1;
      }
      else
      {
        Size = 2 * v15;
        v15 *= 2;
      }
      HIWORD(i) = HIWORD(v33);
    }
    if ( v17 != -2147483622 )
      goto LABEL_52;
    v8 = 0;
LABEL_25:
    if ( *(_BYTE *)(BaseStaticServerData + 2508) == 1 && v8 < 0 || v8 < 0 )
      goto LABEL_52;
    if ( !v9 )
    {
      if ( !ucchMax )
        goto LABEL_14;
      *lpTargetPath++ = 0;
      v9 = 1;
    }
    if ( v9 < ucchMax )
    {
      *lpTargetPath = 0;
      ++v9;
      goto LABEL_52;
    }
    goto LABEL_14;
  }
  RtlInitUnicodeString(&DestinationString, lpDeviceName);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = FileHandle;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes);
  if ( v8 < 0 )
    goto LABEL_52;
  DestinationString.Buffer = lpTargetPath;
  DestinationString.Length = 0;
  if ( ucchMax > 0x7FFFFFFF || 2 * ucchMax > 0xFFFF )
    DestinationString.MaximumLength = -1;
  else
    DestinationString.MaximumLength = 2 * ucchMax;
  DataWritten = 0;
  v8 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &DestinationString, &DataWritten);
  NtClose(SymbolicLinkHandle);
  if ( v8 < 0 )
    goto LABEL_52;
  v10 = DataWritten >> 1;
  if ( !(DataWritten >> 1) || lpTargetPath[(unsigned int)(v10 - 1)] )
  {
    if ( (unsigned int)v10 >= ucchMax )
      goto LABEL_13;
    lpTargetPath[v10] = 0;
    v10 = (unsigned int)(v10 + 1);
  }
  if ( (unsigned int)v10 >= ucchMax )
  {
LABEL_13:
    v9 = 0;
LABEL_14:
    v8 = -1073741789;
    goto LABEL_52;
  }
  lpTargetPath[v10] = 0;
  v9 = v10 + 1;
LABEL_52:
  if ( FileHandle )
    NtClose(FileHandle);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v8 < 0 )
  {
    v9 = 0;
    BaseSetLastNTError((unsigned int)v8);
  }
  return v9;
}

```

## disassembly

```asm
0x1800ae970  mov     r11, rsp
0x1800ae973  mov     [r11+8], rbx
0x1800ae977  mov     [r11+18h], rsi
0x1800ae97b  push    rdi
0x1800ae97c  push    r12
0x1800ae97e  push    r13
0x1800ae980  push    r14
0x1800ae982  push    r15
0x1800ae984  sub     rsp, 110h
0x1800ae98b  mov     r12d, r8d
0x1800ae98e  mov     r15, rdx
0x1800ae991  mov     rbx, rcx
0x1800ae994  xorps   xmm0, xmm0
0x1800ae997  movups  xmmword ptr [rsp+138h+DestinationString.Length], xmm0
0x1800ae99f  xor     eax, eax
0x1800ae9a1  movups  xmmword ptr [rsp+138h+ObjectAttributes.Length], xmm0
0x1800ae9a9  movups  xmmword ptr [rsp+138h+ObjectAttributes.ObjectName], xmm0
0x1800ae9b1  movups  xmmword ptr [r11-7Ch], xmm0
0x1800ae9b6  xor     r14d, r14d
0x1800ae9b9  mov     [rsp+138h+FileHandle], r14
0x1800ae9be  mov     [r11-0A0h], r14
0x1800ae9c5  mov     [rsp+138h+var_C8], r14d
0x1800ae9ca  mov     [rsp+138h+DataWritten], r14d
0x1800ae9cf  movups  xmmword ptr [r11-50h], xmm0
0x1800ae9d4  movups  xmmword ptr [r11-40h], xmm0
0x1800ae9d9  lea     rdx, asc_1802972F8; "\\??"
0x1800ae9e0  lea     rcx, [r11-0B8h]; DestinationString
0x1800ae9e7  call    cs:__imp_RtlInitUnicodeString
0x1800ae9ed  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x1800ae9f8  mov     [rsp+138h+ObjectAttributes.RootDirectory], r14
0x1800aea00  mov     [rsp+138h+ObjectAttributes.Attributes], 40h ; '@'
0x1800aea0b  lea     rax, [rsp+138h+DestinationString]
0x1800aea13  mov     [rsp+138h+ObjectAttributes.ObjectName], rax
0x1800aea1b  xorps   xmm0, xmm0
0x1800aea1e  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800aea27  lea     r8, [rsp+138h+ObjectAttributes]; ObjectAttributes
0x1800aea2f  mov     edx, 1; DesiredAccess
0x1800aea34  lea     rcx, [rsp+138h+FileHandle]; FileHandle
0x1800aea39  call    cs:__imp_NtOpenDirectoryObject
0x1800aea3f  mov     esi, eax
0x1800aea41  test    eax, eax
0x1800aea43  js      loc_1800AF21C
0x1800aea49  xor     r13b, r13b
0x1800aea4c  mov     [rsp+138h+var_60], r15
0x1800aea54  mov     edi, r14d
0x1800aea57  mov     [rsp+138h+var_D0], r14
0x1800aea5c  test    rbx, rbx
0x1800aea5f  jz      loc_1800AF003
0x1800aea65  mov     rdx, rbx; SourceString
0x1800aea68  lea     rcx, [rsp+138h+DestinationString]; DestinationString
0x1800aea70  call    cs:__imp_RtlInitUnicodeString
0x1800aea76  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x1800aea81  mov     rax, [rsp+138h+FileHandle]
0x1800aea86  mov     [rsp+138h+ObjectAttributes.RootDirectory], rax
0x1800aea8e  mov     [rsp+138h+ObjectAttributes.Attributes], 40h ; '@'
0x1800aea99  lea     rax, [rsp+138h+DestinationString]
0x1800aeaa1  mov     [rsp+138h+ObjectAttributes.ObjectName], rax
0x1800aeaa9  xorps   xmm0, xmm0
0x1800aeaac  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800aeab5  lea     r8, [rsp+138h+ObjectAttributes]; ObjectAttributes
0x1800aeabd  mov     edx, 1; DesiredAccess
0x1800aeac2  lea     rcx, [rsp+138h+SymbolicLinkHandle]; SymbolicLinkHandle
0x1800aeaca  call    cs:__imp_NtOpenSymbolicLinkObject
0x1800aead0  mov     esi, eax
0x1800aead2  mov     [rsp+138h+var_F8], eax
0x1800aead6  test    eax, eax
0x1800aead8  js      loc_1800AF1C1
0x1800aeade  mov     [rsp+138h+DestinationString.Buffer], r15
0x1800aeae6  xor     eax, eax
0x1800aeae8  mov     [rsp+138h+DestinationString.Length], ax
0x1800aeaf0  mov     ecx, 0FFFFh
0x1800aeaf5  cmp     r12d, 7FFFFFFFh
0x1800aeafc  ja      loc_1800AF186
0x1800aeb02  lea     eax, [r12+r12]
0x1800aeb06  mov     dword ptr [rsp+138h+Size], eax
0x1800aeb0a  cmp     eax, ecx
0x1800aeb0c  ja      loc_1800AF18E
0x1800aeb12  mov     [rsp+138h+DestinationString.MaximumLength], ax
0x1800aeb1a  mov     [rsp+138h+DataWritten], 0
0x1800aeb22  lea     r8, [rsp+138h+DataWritten]; DataWritten
0x1800aeb27  lea     rdx, [rsp+138h+DestinationString]; LinkTarget
0x1800aeb2f  mov     rcx, [rsp+138h+SymbolicLinkHandle]; SymLinkObjHandle
0x1800aeb37  call    cs:__imp_NtQuerySymbolicLinkObject
0x1800aeb3d  mov     esi, eax
0x1800aeb3f  mov     [rsp+138h+var_F8], eax
0x1800aeb43  mov     rcx, [rsp+138h+SymbolicLinkHandle]; Handle
0x1800aeb4b  call    cs:__imp_NtClose
0x1800aeb51  test    esi, esi
0x1800aeb53  js      loc_1800AF1C1
0x1800aeb59  mov     edi, [rsp+138h+DataWritten]
0x1800aeb5d  shr     edi, 1
0x1800aeb5f  mov     dword ptr [rsp+138h+Size+4], edi
0x1800aeb63  jz      short loc_1800AEB87
0x1800aeb65  lea     eax, [rdi-1]
0x1800aeb68  cmp     word ptr [r15+rax*2], 0
0x1800aeb6e  jnz     short loc_1800AEB87
0x1800aeb70  cmp     edi, r12d
0x1800aeb73  jnb     short loc_1800AEB8C
0x1800aeb75  xor     eax, eax
0x1800aeb77  mov     [r15+rdi*2], ax
0x1800aeb7c  inc     edi
0x1800aeb7e  mov     dword ptr [rsp+138h+Size+4], edi
0x1800aeb82  jmp     loc_1800AF1C1
0x1800aeb87  cmp     edi, r12d
0x1800aeb8a  jb      short loc_1800AEBA0
0x1800aeb8c  xor     edi, edi
0x1800aeb8e  mov     dword ptr [rsp+138h+Size+4], edi
0x1800aeb92  mov     esi, 0C0000023h
0x1800aeb97  mov     [rsp+138h+var_F8], esi
0x1800aeb9b  jmp     loc_1800AF1C1
0x1800aeba0  xor     eax, eax
0x1800aeba2  mov     [r15+rdi*2], ax
0x1800aeba7  inc     edi
0x1800aeba9  mov     dword ptr [rsp+138h+Size+4], edi
0x1800aebad  jmp     short loc_1800AEB70
0x1800aebaf  mov     r13, r14
0x1800aebb2  mov     [rsp+138h+var_C0], r14
0x1800aebb7  mov     rbx, [rsp+138h+var_60]
0x1800aebbf  nop
0x1800aebc0  mov     r8d, 20h ; ' '; Length
0x1800aebc6  mov     rdx, r13; Source2
0x1800aebc9  lea     rcx, [rsp+138h+Source1]; Source1
0x1800aebd1  call    cs:__imp_RtlCompareMemory
0x1800aebd7  cmp     rax, 20h ; ' '
0x1800aebdb  jz      loc_1800AEF9F
0x1800aebe1  lea     rdx, aSymboliclink; "SymbolicLink"
0x1800aebe8  mov     rcx, [r13+18h]; String1
0x1800aebec  call    wcscmp_0
0x1800aebf1  test    eax, eax
0x1800aebf3  jnz     loc_1800AED05
0x1800aebf9  mov     rcx, rbx
0x1800aebfc  mov     [rsp+138h+var_58], rbx
0x1800aec04  mov     r11, [r13+8]
0x1800aec08  xor     r10d, r10d
0x1800aec0b  mov     [rsp+138h+var_A8], r10d
0x1800aec13  test    r11, r11
0x1800aec16  jz      loc_1800AED05
0x1800aec1c  test    rbx, rbx
0x1800aec1f  jz      loc_1800AED05
0x1800aec25  mov     [rsp+138h+var_F4], r10b
0x1800aec2a  cmp     r10d, [rsp+138h+var_D8]
0x1800aec2f  jnb     short loc_1800AEC90
0x1800aec31  mov     rax, r11
0x1800aec34  mov     r9, rcx
0x1800aec37  sub     r9, r11
0x1800aec3a  nop     word ptr [rax+rax+00h]
0x1800aec40  movzx   r8d, word ptr [rax]
0x1800aec44  movzx   edx, word ptr [rax+r9]
0x1800aec49  sub     r8d, edx
0x1800aec4c  jnz     short loc_1800AEC56
0x1800aec4e  add     rax, 2
0x1800aec52  test    edx, edx
0x1800aec54  jnz     short loc_1800AEC40
0x1800aec56  test    r8d, r8d
0x1800aec59  jz      short loc_1800AEC88
0x1800aec5b  inc     r10d
0x1800aec5e  mov     [rsp+138h+var_A8], r10d
0x1800aec66  nop     word ptr [rax+rax+00000000h]
0x1800aec70  movzx   eax, word ptr [rcx]
0x1800aec73  add     rcx, 2
0x1800aec77  mov     [rsp+138h+var_58], rcx
0x1800aec7f  test    ax, ax
0x1800aec82  jz      short loc_1800AEC86
0x1800aec84  jmp     short loc_1800AEC70
0x1800aec86  jmp     short loc_1800AEC2A
0x1800aec88  lea     rax, [rsp+138h+var_F4]
0x1800aec8d  mov     byte ptr [rax], 1
0x1800aec90  cmp     [rsp+138h+var_F4], 0
0x1800aec95  jnz     short loc_1800AED05
0x1800aec97  cmp     edi, r12d
0x1800aec9a  ja      loc_1800AEB92
0x1800aeca0  movzx   r8d, word ptr [r13+0]; Size
0x1800aeca5  mov     r13d, r8d
0x1800aeca8  shr     r13, 1
0x1800aecab  mov     eax, r12d
0x1800aecae  sub     eax, edi
0x1800aecb0  cmp     r13d, eax
0x1800aecb3  ja      loc_1800AEB92
0x1800aecb9  sub     eax, r13d
0x1800aecbc  cmp     eax, 2
0x1800aecbf  jb      loc_1800AEB92
0x1800aecc5  mov     rdx, [rsp+138h+var_C0]
0x1800aecca  mov     rdx, [rdx+8]; Src
0x1800aecce  mov     rcx, r15; void *
0x1800aecd1  call    memcpy_0
0x1800aecd6  mov     eax, r13d
0x1800aecd9  lea     rcx, [r15+rax*2]
0x1800aecdd  mov     [rsp+138h+arg_8], rcx
0x1800aece5  xor     eax, eax
0x1800aece7  mov     [rcx], ax
0x1800aecea  lea     r15, [rcx+2]
0x1800aecee  mov     [rsp+138h+arg_8], r15
0x1800aecf6  inc     r13d
0x1800aecf9  add     edi, r13d
0x1800aecfc  mov     dword ptr [rsp+138h+Size+4], edi
0x1800aed00  mov     r13, [rsp+138h+var_C0]
0x1800aed05  add     r13, 20h ; ' '
0x1800aed09  mov     [rsp+138h+var_C0], r13
0x1800aed0e  jmp     loc_1800AEBC0
0x1800aed13  mov     rbx, r14
0x1800aed16  mov     [rsp+138h+var_C0], rbx
0x1800aed1b  nop     dword ptr [rax+rax+00h]
0x1800aed20  mov     r8d, 20h ; ' '; Length
0x1800aed26  mov     rdx, rbx; Source2
0x1800aed29  lea     rcx, [rsp+138h+Source1]; Source1
0x1800aed31  call    cs:__imp_RtlCompareMemory
0x1800aed37  cmp     rax, 20h ; ' '
0x1800aed3b  jz      loc_1800AEDD5
0x1800aed41  lea     rdx, aSymboliclink; "SymbolicLink"
0x1800aed48  mov     rcx, [rbx+18h]; String1
0x1800aed4c  call    wcscmp_0
0x1800aed51  test    eax, eax
0x1800aed53  jnz     short loc_1800AEDC7
0x1800aed55  cmp     edi, r12d
0x1800aed58  ja      loc_1800AEB92
0x1800aed5e  movzx   r8d, word ptr [rbx]; Size
0x1800aed62  mov     ecx, r8d
0x1800aed65  shr     rcx, 1
0x1800aed68  mov     [rsp+138h+var_68], rcx
0x1800aed70  mov     eax, r12d
0x1800aed73  sub     eax, edi
0x1800aed75  cmp     ecx, eax
0x1800aed77  ja      loc_1800AEB92
0x1800aed7d  sub     eax, ecx
0x1800aed7f  cmp     eax, 2
0x1800aed82  jb      loc_1800AEB92
0x1800aed88  mov     rdx, [rbx+8]; Src
0x1800aed8c  mov     rcx, r15; void *
0x1800aed8f  call    memcpy_0
0x1800aed94  mov     rdx, [rsp+138h+var_68]
0x1800aed9c  mov     eax, edx
0x1800aed9e  lea     rcx, [r15+rax*2]
0x1800aeda2  mov     [rsp+138h+arg_8], rcx
0x1800aedaa  xor     eax, eax
0x1800aedac  mov     [rcx], ax
0x1800aedaf  lea     r15, [rcx+2]
0x1800aedb3  mov     [rsp+138h+arg_8], r15
0x1800aedbb  inc     edi
0x1800aedbd  add     edi, edx
0x1800aedbf  mov     dword ptr [rsp+138h+Size+4], edi
0x1800aedc3  inc     [rsp+138h+var_D8]
0x1800aedc7  add     rbx, 20h ; ' '
0x1800aedcb  mov     [rsp+138h+var_C0], rbx
0x1800aedd0  jmp     loc_1800AED20
0x1800aedd5  cmp     esi, 105h
0x1800aeddb  jz      loc_1800AEB92
0x1800aede1  mov     rax, cs:BaseStaticServerData
0x1800aede8  cmp     byte ptr [rax+9CCh], 1
0x1800aedef  jnz     loc_1800AEFAB
0x1800aedf5  test    esi, esi
0x1800aedf7  js      loc_1800AF1C1
0x1800aedfd  cmp     r13b, 1
0x1800aee01  jnz     loc_1800AEFAB
0x1800aee07  mov     rcx, [rsp+138h+FileHandle]; Handle
0x1800aee0c  test    rcx, rcx
0x1800aee0f  jnz     loc_1800AEF8B
0x1800aee15  lea     rdx, aGlobal_0; "\\GLOBAL??"
0x1800aee1c  lea     rcx, [rsp+138h+DestinationString]; DestinationString
0x1800aee24  call    cs:__imp_RtlInitUnicodeString
0x1800aee2a  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x1800aee35  mov     [rsp+138h+ObjectAttributes.RootDirectory], 0
0x1800aee41  mov     [rsp+138h+ObjectAttributes.Attributes], 40h ; '@'
0x1800aee4c  lea     rax, [rsp+138h+DestinationString]
0x1800aee54  mov     [rsp+138h+ObjectAttributes.ObjectName], rax
0x1800aee5c  xorps   xmm0, xmm0
0x1800aee5f  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800aee68  lea     r8, [rsp+138h+ObjectAttributes]; ObjectAttributes
0x1800aee70  mov     edx, 1; DesiredAccess
0x1800aee75  lea     rcx, [rsp+138h+FileHandle]; FileHandle
0x1800aee7a  call    cs:__imp_NtOpenDirectoryObject
0x1800aee80  mov     esi, eax
0x1800aee82  mov     [rsp+138h+var_F8], eax
0x1800aee86  test    eax, eax
0x1800aee88  js      loc_1800AEF73
0x1800aee8e  mov     r13d, [rsp+138h+arg_18]
0x1800aee96  nop     word ptr [rax+rax+00000000h]
0x1800aeea0  cmp     r13w, 3
0x1800aeea5  jnb     loc_1800AEF9F
0x1800aeeab  test    r14, r14
0x1800aeeae  jnz     loc_1800AEF6A
0x1800aeeb4  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800aeeba  mov     ebx, dword ptr [rsp+138h+Size]
0x1800aeebe  mov     r8d, ebx; Size
0x1800aeec1  mov     rcx, gs:60h
0x1800aeeca  mov     rcx, [rcx+30h]; HeapHandle
0x1800aeece  call    cs:__imp_RtlAllocateHeap
0x1800aeed4  mov     r14, rax
0x1800aeed7  mov     [rsp+138h+var_D0], rax
0x1800aeedc  test    rax, rax
0x1800aeedf  jz      loc_1800AF1A5
0x1800aeee5  lea     rax, [rsp+138h+DataWritten]
0x1800aeeea  mov     [rsp+138h+ReturnLength], rax; ReturnLength
0x1800aeeef  lea     rax, [rsp+138h+var_C8]
0x1800aeef4  mov     [rsp+138h+Context], rax; Context
0x1800aeef9  mov     [rsp+138h+RestartScan], 1; RestartScan
0x1800aeefe  xor     r9d, r9d; ReturnSingleEntry
0x1800aef01  mov     r8d, ebx; BufferLength
0x1800aef04  mov     rdx, r14; Buffer
0x1800aef07  mov     rcx, [rsp+138h+FileHandle]; DirectoryHandle
0x1800aef0c  call    cs:__imp_NtQueryDirectoryObject
  ... truncated ...
```
