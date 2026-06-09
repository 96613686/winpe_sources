# FindFirstFileNameW

- ea: `0x1800da7a0`
- end: `0x1800dabd2`
- name: `FindFirstFileNameW`
- size: `1074`
- prototype: `HANDLE __stdcall(LPCWSTR lpFileName, DWORD dwFlags, LPDWORD StringLength, PWSTR LinkName)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800134a0`
- `0x180077510`
- `0x1800da7a0`
- `0x1800dad64`
- `0x180188eb9`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800da994`
- `ntdll!NtQueryInformationFile` at `0x1800da994`
- `ntdll!RtlInitializeCriticalSection` at `0x1800da911`
- `ntdll!RtlInitializeCriticalSection` at `0x1800da911`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800da7fd`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800da7fd`
- `ntdll!NtCreateFile` at `0x1800da8a6`
- `ntdll!NtCreateFile` at `0x1800da8a6`
- `ntdll!RtlSetLastWin32Error` at `0x1800dabad`
- `ntdll!RtlSetLastWin32Error` at `0x1800dabad`
- `ntdll!NtClose` at `0x1800dabc0`
- `ntdll!NtClose` at `0x18018bfcb`
- `ntdll!NtClose` at `0x1800dabc0`
- `ntdll!NtClose` at `0x18018bfcb`
- `ntdll!RtlFreeHeap` at `0x1800da94c`
- `ntdll!RtlFreeHeap` at `0x1800dab0f`
- `ntdll!RtlFreeHeap` at `0x1800dab4e`
- `ntdll!RtlFreeHeap` at `0x1800dab6b`
- `ntdll!RtlFreeHeap` at `0x18018bf8f`
- `ntdll!RtlFreeHeap` at `0x18018bfae`
- `ntdll!RtlFreeHeap` at `0x1800da94c`
- `ntdll!RtlFreeHeap` at `0x1800dab0f`
- `ntdll!RtlFreeHeap` at `0x1800dab4e`
- `ntdll!RtlFreeHeap` at `0x1800dab6b`
- `ntdll!RtlFreeHeap` at `0x18018bf8f`
- `ntdll!RtlFreeHeap` at `0x18018bfae`
- `ntdll!RtlAllocateHeap` at `0x1800da8e4`
- `ntdll!RtlAllocateHeap` at `0x1800da964`
- `ntdll!RtlAllocateHeap` at `0x1800da8e4`
- `ntdll!RtlAllocateHeap` at `0x1800da964`

## pseudocode

```c
HANDLE __stdcall FindFirstFileNameW(LPCWSTR lpFileName, DWORD dwFlags, LPDWORD StringLength, PWSTR LinkName)
{
  signed int *v4; // rsi
  signed int v5; // r14d
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  char v7; // r12
  NTSTATUS Parent; // edi
  struct _RTL_CRITICAL_SECTION_DEBUG *v9; // rdi
  struct _RTL_CRITICAL_SECTION *Heap; // rax
  signed int *v11; // rax
  NTSTATUS v12; // eax
  unsigned int *v13; // r15
  size_t v14; // r14
  int v15; // ecx
  DWORD v16; // eax
  DWORD v17; // ecx
  __int64 v18; // rcx
  ULONG_PTR Information; // rax
  ULONG v21; // ecx
  signed int *v22; // [rsp+68h] [rbp-B0h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp-A8h] BYREF
  DWORD v24; // [rsp+78h] [rbp-A0h]
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+80h] [rbp-98h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-90h] BYREF
  struct _UNICODE_STRING v27; // [rsp+98h] [rbp-80h] BYREF
  struct _RTL_CRITICAL_SECTION *v28; // [rsp+A8h] [rbp-70h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-68h] BYREF
  DWORD v30; // [rsp+128h] [rbp+10h]

  IoStatusBlock = 0;
  v4 = 0;
  v22 = 0;
  FileHandle = (HANDLE)-1LL;
  memset(&ObjectAttributes, 0, 44);
  v27 = 0;
  if ( dwFlags )
  {
    v21 = 87;
LABEL_44:
    RtlSetLastWin32Error(v21);
    return (HANDLE)-1LL;
  }
  if ( !RtlDosPathNameToNtPathName_U(lpFileName, &v27, 0, 0) )
  {
    v21 = 3;
    goto LABEL_44;
  }
  v5 = 96;
  v6 = 0;
  v25 = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &v27;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = 1;
  Parent = NtCreateFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x200020u, 0, 0);
  if ( !Parent )
  {
    v9 = (struct _RTL_CRITICAL_SECTION_DEBUG *)FileHandle;
    v28 = 0;
    Heap = (struct _RTL_CRITICAL_SECTION *)RtlAllocateHeap(
                                             NtCurrentPeb()->ProcessHeap,
                                             KernelBaseGlobalData + 786432,
                                             0x50u);
    v6 = Heap;
    v28 = Heap;
    if ( Heap )
    {
      Heap->DebugInfo = v9;
      *(_QWORD *)&Heap->LockCount = 0;
      Heap->OwningThread = 0;
      Heap->LockSemaphore = 0;
      Heap->SpinCount = 0;
      if ( RtlInitializeCriticalSection(Heap + 1) < 0 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
        v6 = 0;
        v28 = 0;
      }
    }
    v25 = v6;
    if ( v6 )
    {
      FileHandle = 0;
      while ( 1 )
      {
        if ( v4 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
        v11 = (signed int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
        v4 = v11;
        v22 = v11;
        if ( !v11 )
          break;
        v12 = NtQueryInformationFile(v6->DebugInfo, &IoStatusBlock, v11, v5, FileHardLinkInformation);
        Parent = v12;
        if ( v12 != -2147483643 )
        {
          if ( !v12 )
          {
            if ( IoStatusBlock.Information )
            {
              *(_QWORD *)&v6->LockCount = v4;
              v13 = (unsigned int *)v4;
              LODWORD(v6->LockSemaphore) = IoStatusBlock.Information;
              HIDWORD(v6->LockSemaphore) = IoStatusBlock.Information;
              v22 = 0;
              Parent = FindParent(v6->DebugInfo, *((_QWORD *)v4 + 2), &v22);
              v4 = v22;
              if ( Parent >= 0 )
              {
                v14 = (unsigned int)*v22;
                v15 = 2;
                if ( (_DWORD)v14 == 2 )
                  v15 = 1;
                else
                  v7 = 0;
                v16 = v15 + v13[6] + ((unsigned int)*v22 >> 1);
                v30 = v16;
                v17 = *StringLength;
                v24 = v17;
                Parent = v17 < v16 ? 0x80000005 : 0;
                *StringLength = v16;
                if ( v16 <= v17 )
                {
                  memcpy_0(LinkName, v4 + 1, v14);
                  if ( !v7 )
                  {
                    *(PWSTR)((char *)LinkName + v14) = 92;
                    LODWORD(v14) = v14 + 2;
                  }
                  memcpy_0((char *)LinkName + (unsigned int)v14, v13 + 7, 2LL * v13[6]);
                  *(WCHAR *)((char *)&LinkName[v13[6]] + (unsigned int)v14) = 0;
                  v16 = v30;
                  v17 = v24;
                }
                if ( v16 <= v17 )
                {
                  v18 = *(_QWORD *)&v6->LockCount;
                  if ( v13[2] )
                  {
                    Information = v13[2];
                    v18 += 8;
                  }
                  else
                  {
                    Information = IoStatusBlock.Information;
                  }
                  v6->OwningThread = (HANDLE)(Information + v18);
                }
              }
            }
            else
            {
              Parent = -1073741807;
            }
          }
          goto LABEL_32;
        }
        v5 = *v4;
      }
    }
    Parent = -1073741670;
  }
LABEL_32:
  if ( v27.Length )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27.Buffer);
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( Parent )
  {
    BaseSetLastNTError((unsigned int)Parent);
    if ( FileHandle != (HANDLE)-1LL )
      NtClose(FileHandle);
    if ( v6 )
      FindClose(v6);
    return (HANDLE)-1LL;
  }
  return v6;
}

```

## disassembly

```asm
0x1800da7a0  mov     rax, rsp
0x1800da7a3  mov     [rax+20h], r9
0x1800da7a7  mov     [rax+18h], r8
0x1800da7ab  push    rbx
0x1800da7ac  push    rsi
0x1800da7ad  push    rdi
0x1800da7ae  push    r12
0x1800da7b0  push    r13
0x1800da7b2  push    r14
0x1800da7b4  push    r15
0x1800da7b6  sub     rsp, 0E0h
0x1800da7bd  xorps   xmm0, xmm0
0x1800da7c0  movups  xmmword ptr [rax-90h], xmm0
0x1800da7c7  xor     r13d, r13d
0x1800da7ca  mov     esi, r13d
0x1800da7cd  mov     [rsp+118h+var_B0], r13
0x1800da7d2  mov     [rsp+118h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800da7db  xor     r8d, r8d; NtFileNamePart
0x1800da7de  movups  xmmword ptr [rax-68h], xmm0
0x1800da7e2  movups  xmmword ptr [rax-58h], xmm0
0x1800da7e6  movups  xmmword ptr [rax-4Ch], xmm0
0x1800da7ea  movups  xmmword ptr [rax-80h], xmm0
0x1800da7ee  test    edx, edx
0x1800da7f0  jnz     loc_1800DABA8
0x1800da7f6  xor     r9d, r9d; DirectoryInfo
0x1800da7f9  lea     rdx, [rax-80h]; NtPathName
0x1800da7fd  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800da803  test    al, al
0x1800da805  jz      loc_1800DABB9
0x1800da80b  mov     [rsp+118h+var_B8], 0C000000Dh
0x1800da813  lea     r14d, [r13+60h]
0x1800da817  mov     ebx, r13d
0x1800da81a  mov     [rsp+118h+var_98], rbx
0x1800da822  mov     [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x1800da82d  mov     [rsp+118h+ObjectAttributes.RootDirectory], r13
0x1800da835  mov     [rsp+118h+ObjectAttributes.Attributes], 40h ; '@'
0x1800da840  lea     rax, [rsp+118h+var_80]
0x1800da848  mov     [rsp+118h+ObjectAttributes.ObjectName], rax
0x1800da850  xorps   xmm0, xmm0
0x1800da853  movdqu  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800da85c  mov     [rsp+118h+EaLength], r13d; EaLength
0x1800da861  mov     [rsp+118h+EaBuffer], r13; EaBuffer
0x1800da866  mov     [rsp+118h+CreateOptions], 200020h; CreateOptions
0x1800da86e  lea     r12d, [r13+1]
0x1800da872  mov     [rsp+118h+CreateDisposition], r12d; CreateDisposition
0x1800da877  mov     [rsp+118h+ShareAccess], 7; ShareAccess
0x1800da87f  mov     [rsp+118h+FileAttributes], 80h; FileAttributes
0x1800da887  mov     [rsp+118h+AllocationSize], r13; AllocationSize
0x1800da88c  lea     r9, [rsp+118h+IoStatusBlock]; IoStatusBlock
0x1800da894  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x1800da89c  mov     edx, 100080h; DesiredAccess
0x1800da8a1  lea     rcx, [rsp+118h+FileHandle]; FileHandle
0x1800da8a6  call    cs:__imp_NtCreateFile
0x1800da8ac  mov     edi, eax
0x1800da8ae  mov     [rsp+118h+var_B8], eax
0x1800da8b2  test    eax, eax
0x1800da8b4  jnz     loc_1800DAB2C
0x1800da8ba  mov     rdi, [rsp+118h+FileHandle]
0x1800da8bf  mov     [rsp+118h+var_70], r13
0x1800da8c7  mov     edx, cs:KernelBaseGlobalData
0x1800da8cd  add     edx, 0C0000h; Flags
0x1800da8d3  mov     rcx, gs:60h
0x1800da8dc  lea     r8d, [r13+50h]; Size
0x1800da8e0  mov     rcx, [rcx+30h]; HeapHandle
0x1800da8e4  call    cs:__imp_RtlAllocateHeap
0x1800da8ea  mov     rbx, rax
0x1800da8ed  mov     [rsp+118h+var_70], rax
0x1800da8f5  test    rax, rax
0x1800da8f8  jz      short loc_1800DA91F
0x1800da8fa  mov     [rax], rdi
0x1800da8fd  mov     [rax+8], r13
0x1800da901  mov     [rax+10h], r13
0x1800da905  mov     [rax+18h], r13
0x1800da909  mov     [rax+20h], r13
0x1800da90d  lea     rcx, [rax+28h]; CriticalSection
0x1800da911  call    cs:__imp_RtlInitializeCriticalSection
0x1800da917  test    eax, eax
0x1800da919  js      loc_1800DAAFD
0x1800da91f  mov     [rsp+118h+var_98], rbx
0x1800da927  test    rbx, rbx
0x1800da92a  jz      loc_1800DAADB
0x1800da930  mov     [rsp+118h+FileHandle], r13
0x1800da935  test    rsi, rsi
0x1800da938  jz      short loc_1800DA952
0x1800da93a  mov     rcx, gs:60h
0x1800da943  mov     r8, rsi; P
0x1800da946  xor     edx, edx; Flags
0x1800da948  mov     rcx, [rcx+30h]; HeapHandle
0x1800da94c  call    cs:__imp_RtlFreeHeap
0x1800da952  movsxd  r8, r14d; Size
0x1800da955  mov     rcx, gs:60h
0x1800da95e  xor     edx, edx; Flags
0x1800da960  mov     rcx, [rcx+30h]; HeapHandle
0x1800da964  call    cs:__imp_RtlAllocateHeap
0x1800da96a  mov     rsi, rax
0x1800da96d  mov     [rsp+118h+var_B0], rax
0x1800da972  test    rax, rax
0x1800da975  jz      loc_1800DAADB
0x1800da97b  mov     dword ptr [rsp+118h+AllocationSize], 2Eh ; '.'; FileInformationClass
0x1800da983  mov     r9d, r14d; Length
0x1800da986  mov     r8, rax; FileInformation
0x1800da989  lea     rdx, [rsp+118h+IoStatusBlock]; IoStatusBlock
0x1800da991  mov     rcx, [rbx]; FileHandle
0x1800da994  call    cs:__imp_NtQueryInformationFile
0x1800da99a  mov     edi, eax
0x1800da99c  mov     [rsp+118h+var_B8], eax
0x1800da9a0  cmp     eax, 80000005h
0x1800da9a5  jz      loc_1800DAAD3
0x1800da9ab  test    eax, eax
0x1800da9ad  jnz     loc_1800DAB2C
0x1800da9b3  cmp     [rsp+118h+IoStatusBlock.Information], r13
0x1800da9bb  jz      loc_1800DAB25
0x1800da9c1  mov     [rbx+8], rsi
0x1800da9c5  mov     r15, rsi
0x1800da9c8  mov     rax, [rsp+118h+IoStatusBlock.Information]
0x1800da9d0  mov     [rbx+18h], eax
0x1800da9d3  mov     rax, [rsp+118h+IoStatusBlock.Information]
0x1800da9db  mov     [rbx+1Ch], eax
0x1800da9de  mov     [rsp+118h+var_B0], r13
0x1800da9e3  lea     r8, [rsp+118h+var_B0]
0x1800da9e8  mov     rdx, [rsi+10h]
0x1800da9ec  mov     rcx, [rbx]
0x1800da9ef  call    FindParent
0x1800da9f4  mov     edi, eax
0x1800da9f6  mov     [rsp+118h+var_B8], eax
0x1800da9fa  mov     rsi, [rsp+118h+var_B0]
0x1800da9ff  test    eax, eax
0x1800daa01  js      loc_1800DAB2C
0x1800daa07  mov     r14d, [rsi]
0x1800daa0a  mov     ecx, 2
0x1800daa0f  cmp     r14d, ecx
0x1800daa12  jz      loc_1800DAAEB
0x1800daa18  mov     r12b, r13b
0x1800daa1b  mov     rax, r14
0x1800daa1e  shr     rax, 1
0x1800daa21  add     eax, [r15+18h]
0x1800daa25  add     eax, ecx
0x1800daa27  mov     [rsp+118h+arg_8], eax
0x1800daa2e  mov     rdx, [rsp+118h+arg_10]
0x1800daa36  mov     ecx, [rdx]
0x1800daa38  mov     [rsp+118h+var_A0], ecx
0x1800daa3c  cmp     ecx, eax
0x1800daa3e  sbb     edi, edi
0x1800daa40  and     edi, 80000005h
0x1800daa46  mov     [rdx], eax
0x1800daa48  cmp     eax, ecx
0x1800daa4a  ja      loc_1800DAAE6
0x1800daa50  lea     rdx, [rsi+4]; Src
0x1800daa54  mov     r8, r14; Size
0x1800daa57  mov     rcx, [rsp+118h+arg_18]; void *
0x1800daa5f  call    memcpy_0
0x1800daa64  test    r12b, r12b
0x1800daa67  mov     r12, [rsp+118h+arg_18]
0x1800daa6f  jnz     short loc_1800DAA7F
0x1800daa71  mov     eax, 5Ch ; '\'
0x1800daa76  mov     [r12+r14], ax
0x1800daa7b  add     r14d, 2
0x1800daa7f  mov     r8d, [r15+18h]
0x1800daa83  add     r8, r8; Size
0x1800daa86  lea     rdx, [r15+1Ch]; Src
0x1800daa8a  mov     ecx, r14d
0x1800daa8d  add     rcx, r12; void *
0x1800daa90  call    memcpy_0
0x1800daa95  mov     eax, [r15+18h]
0x1800daa99  lea     ecx, [r14+rax*2]
0x1800daa9d  xor     r13d, r13d
0x1800daaa0  mov     [rcx+r12], r13w
0x1800daaa5  mov     eax, [rsp+118h+arg_8]
0x1800daaac  mov     ecx, [rsp+118h+var_A0]
0x1800daab0  mov     [rsp+118h+var_B8], edi
0x1800daab4  cmp     eax, ecx
0x1800daab6  ja      short loc_1800DAB2C
0x1800daab8  mov     rcx, [rbx+8]
0x1800daabc  cmp     [r15+8], r13d
0x1800daac0  jbe     short loc_1800DAAF3
0x1800daac2  mov     eax, [r15+8]
0x1800daac6  add     rcx, 8
0x1800daaca  add     rcx, rax
0x1800daacd  mov     [rbx+10h], rcx
0x1800daad1  jmp     short loc_1800DAB2C
0x1800daad3  mov     r14d, [rsi]
0x1800daad6  jmp     loc_1800DA935
0x1800daadb  mov     edi, 0C000009Ah
0x1800daae0  mov     [rsp+118h+var_B8], edi
0x1800daae4  jmp     short loc_1800DAB2C
0x1800daae6  xor     r13d, r13d
0x1800daae9  jmp     short loc_1800DAAB0
0x1800daaeb  mov     ecx, r12d
0x1800daaee  jmp     loc_1800DAA1B
0x1800daaf3  mov     rax, [rsp+118h+IoStatusBlock.Information]
0x1800daafb  jmp     short loc_1800DAACA
0x1800daafd  mov     rcx, gs:60h
0x1800dab06  mov     r8, rbx; P
0x1800dab09  xor     edx, edx; Flags
0x1800dab0b  mov     rcx, [rcx+30h]; HeapHandle
0x1800dab0f  call    cs:__imp_RtlFreeHeap
0x1800dab15  mov     rbx, r13
0x1800dab18  mov     [rsp+118h+var_70], rbx
0x1800dab20  jmp     loc_1800DA91F
0x1800dab25  mov     edi, 0C0000011h
0x1800dab2a  jmp     short loc_1800DAAE0
0x1800dab2c  cmp     [rsp+118h+var_80], r13w
0x1800dab35  jz      short loc_1800DAB54
0x1800dab37  mov     rcx, gs:60h
0x1800dab40  mov     r8, [rsp+118h+P]; P
0x1800dab48  xor     edx, edx; Flags
0x1800dab4a  mov     rcx, [rcx+30h]; HeapHandle
0x1800dab4e  call    cs:__imp_RtlFreeHeap
0x1800dab54  test    rsi, rsi
0x1800dab57  jz      short loc_1800DAB71
0x1800dab59  mov     rcx, gs:60h
0x1800dab62  mov     r8, rsi; P
0x1800dab65  xor     edx, edx; Flags
0x1800dab67  mov     rcx, [rcx+30h]; HeapHandle
0x1800dab6b  call    cs:__imp_RtlFreeHeap
0x1800dab71  test    edi, edi
0x1800dab73  jnz     short loc_1800DAB8B
0x1800dab75  mov     rax, rbx
0x1800dab78  add     rsp, 0E0h
0x1800dab7f  pop     r15
0x1800dab81  pop     r14
0x1800dab83  pop     r13
0x1800dab85  pop     r12
0x1800dab87  pop     rdi
0x1800dab88  pop     rsi
0x1800dab89  pop     rbx
0x1800dab8a  retn
0x1800dab8b  mov     ecx, edi
0x1800dab8d  call    BaseSetLastNTError
0x1800dab92  mov     rcx, [rsp+118h+FileHandle]; Handle
0x1800dab97  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800dab9b  jnz     short loc_1800DABC0
0x1800dab9d  test    rbx, rbx
0x1800daba0  jnz     short loc_1800DABC8
0x1800daba2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800daba6  jmp     short loc_1800DAB75
0x1800daba8  mov     ecx, 57h ; 'W'; LastError
0x1800dabad  call    cs:__imp_RtlSetLastWin32Error
0x1800dabb3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800dabb7  jmp     short loc_1800DAB78
0x1800dabb9  mov     ecx, 3
0x1800dabbe  jmp     short loc_1800DABAD
0x1800dabc0  call    cs:__imp_NtClose
0x1800dabc6  jmp     short loc_1800DAB9D
0x1800dabc8  mov     rcx, rbx; hFindFile
0x1800dabcb  call    FindClose
0x1800dabd0  jmp     short loc_1800DABA2
0x18018bf66  push    rbp
0x18018bf68  sub     rsp, 60h
0x18018bf6c  mov     rbp, rdx
0x18018bf6f  cmp     word ptr [rbp+98h], 0
0x18018bf77  jz      short loc_18018BF96
0x18018bf79  mov     rcx, gs:60h
0x18018bf82  mov     r8, [rbp+0A0h]; P
0x18018bf89  xor     edx, edx; Flags
0x18018bf8b  mov     rcx, [rcx+30h]; HeapHandle
0x18018bf8f  call    cs:__imp_RtlFreeHeap
0x18018bf95  nop
0x18018bf96  mov     r8, [rbp+68h]; P
0x18018bf9a  test    r8, r8
0x18018bf9d  jz      short loc_18018BFB5
0x18018bf9f  mov     rcx, gs:60h
0x18018bfa8  xor     edx, edx; Flags
0x18018bfaa  mov     rcx, [rcx+30h]; HeapHandle
0x18018bfae  call    cs:__imp_RtlFreeHeap
0x18018bfb4  nop
0x18018bfb5  mov     ecx, [rbp+60h]
0x18018bfb8  test    ecx, ecx
0x18018bfba  jz      short loc_18018BFEF
0x18018bfbc  call    BaseSetLastNTError
0x18018bfc1  mov     rcx, [rbp+70h]; Handle
0x18018bfc5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18018bfc9  jz      short loc_18018BFD2
0x18018bfcb  call    cs:__imp_NtClose
0x18018bfd1  nop
0x18018bfd2  mov     rcx, [rbp+80h]; hFindFile
0x18018bfd9  test    rcx, rcx
0x18018bfdc  jz      short loc_18018BFE4
0x18018bfde  call    FindClose
0x18018bfe3  nop
0x18018bfe4  mov     qword ptr [rbp+80h], 0FFFFFFFFFFFFFFFFh
0x18018bfef  add     rsp, 60h
0x18018bff3  pop     rbp
0x18018bff4  retn
```
