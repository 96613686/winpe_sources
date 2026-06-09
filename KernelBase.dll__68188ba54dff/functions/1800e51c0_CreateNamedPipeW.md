# CreateNamedPipeW

- ea: `0x1800e51c0`
- end: `0x1800e5515`
- name: `CreateNamedPipeW`
- size: `853`
- prototype: `HANDLE __stdcall(LPCWSTR lpName, DWORD dwOpenMode, DWORD dwPipeMode, DWORD nMaxInstances, DWORD nOutBufferSize, DWORD nInBufferSize, DWORD nDefaultTimeOut, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800134a0`
- `0x1800e51c0`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800e523f`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800e523f`
- `ntdll!RtlSetLastWin32Error` at `0x1800e5446`
- `ntdll!RtlSetLastWin32Error` at `0x1800e54af`
- `ntdll!RtlSetLastWin32Error` at `0x1800e5446`
- `ntdll!RtlSetLastWin32Error` at `0x1800e54af`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800e52a2`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800e52a2`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800e52b6`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800e52b6`
- `ntdll!RtlFreeHeap` at `0x1800e5411`
- `ntdll!RtlFreeHeap` at `0x1800e5433`
- `ntdll!RtlFreeHeap` at `0x1800e5464`
- `ntdll!RtlFreeHeap` at `0x1800e54e3`
- `ntdll!RtlFreeHeap` at `0x1800e5505`
- `ntdll!RtlFreeHeap` at `0x1800e5411`
- `ntdll!RtlFreeHeap` at `0x1800e5433`
- `ntdll!RtlFreeHeap` at `0x1800e5464`
- `ntdll!RtlFreeHeap` at `0x1800e54e3`
- `ntdll!RtlFreeHeap` at `0x1800e5505`
- `ntdll!RtlDefaultNpAcl` at `0x1800e5289`
- `ntdll!RtlDefaultNpAcl` at `0x1800e5289`
- `ntdll!NtCreateNamedPipeFile` at `0x1800e53e1`
- `ntdll!NtCreateNamedPipeFile` at `0x1800e53e1`

## pseudocode

```c
HANDLE __stdcall CreateNamedPipeW(
        LPCWSTR lpName,
        DWORD dwOpenMode,
        DWORD dwPipeMode,
        DWORD nMaxInstances,
        DWORD nOutBufferSize,
        DWORD nInBufferSize,
        DWORD nDefaultTimeOut,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  ULONG MaxInstances; // r15d
  PWSTR Buffer; // rdi
  ULONG v12; // ecx
  NTSTATUS v13; // ebx
  LPVOID lpSecurityDescriptor; // rax
  union _LARGE_INTEGER v15; // rcx
  ULONG ShareAccess; // ebx
  int v17; // r14d
  ULONG WriteModeMessage; // r8d
  NTSTATUS v19; // eax
  ULONG v20; // ecx
  __int64 v22; // rcx
  PACL pAcl; // [rsp+70h] [rbp-90h] BYREF
  union _LARGE_INTEGER DefaultTimeOut; // [rsp+78h] [rbp-88h] BYREF
  HANDLE NamedPipeFileHandle; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR NtFileNamePart; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v31; // [rsp+100h] [rbp+0h]

  NamedPipeFileHandle = 0;
  DefaultTimeOut.QuadPart = 0;
  NtFileNamePart = 0;
  v31 = 0;
  pAcl = 0;
  memset(&ObjectAttributes, 0, 44);
  NtPathName = 0;
  IoStatusBlock = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( nMaxInstances - 1 > 0xFE )
  {
LABEL_40:
    v22 = 3221225485LL;
    goto LABEL_30;
  }
  MaxInstances = -1;
  if ( nMaxInstances != 255 )
    MaxInstances = nMaxInstances;
  if ( !RtlDosPathNameToNtPathName_U(lpName, &NtPathName, &NtFileNamePart, 0) )
  {
    RtlSetLastWin32Error(3u);
    return (HANDLE)-1LL;
  }
  Buffer = NtPathName.Buffer;
  v12 = 64;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( !lpSecurityAttributes )
    goto LABEL_6;
  lpSecurityDescriptor = lpSecurityAttributes->lpSecurityDescriptor;
  if ( lpSecurityAttributes->bInheritHandle )
    v12 = 66;
  ObjectAttributes.SecurityDescriptor = lpSecurityAttributes->lpSecurityDescriptor;
  ObjectAttributes.Attributes = v12;
  if ( !lpSecurityDescriptor )
  {
LABEL_6:
    v13 = RtlDefaultNpAcl(&pAcl);
    if ( v13 < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
LABEL_29:
      v22 = (unsigned int)v13;
LABEL_30:
      BaseSetLastNTError(v22);
      return (HANDLE)-1LL;
    }
    RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, pAcl, 0);
    ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
  }
  if ( nDefaultTimeOut )
    v15.QuadPart = -10000LL * nDefaultTimeOut;
  else
    v15.QuadPart = -500000;
  DefaultTimeOut = v15;
  if ( (dwOpenMode & 0x3EF3FFFC) != 0 || (dwPipeMode & 0xFFFFFFF0) != 0 )
  {
LABEL_38:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    if ( pAcl )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pAcl);
    goto LABEL_40;
  }
  ShareAccess = 3;
  switch ( dwOpenMode & 3 )
  {
    case 1u:
      ShareAccess = 2;
      v17 = -2146435072;
      break;
    case 2u:
      ShareAccess = 1;
      v17 = 1074790400;
      break;
    case 3u:
      v17 = -1072693248;
      break;
    default:
      goto LABEL_38;
  }
  WriteModeMessage = (dwPipeMode >> 2) & 1 | 2;
  if ( (dwPipeMode & 8) == 0 )
    WriteModeMessage = (dwPipeMode >> 2) & 1;
  v19 = NtCreateNamedPipeFile(
          &NamedPipeFileHandle,
          v17 | dwOpenMode & 0x10C0000,
          &ObjectAttributes,
          &IoStatusBlock,
          ShareAccess,
          ((dwOpenMode & 0x80000) == 0) | 2,
          ~(dwOpenMode >> 25) & 0x20 | ((int)dwOpenMode >> 31) & 2,
          WriteModeMessage,
          (dwPipeMode >> 1) & 1,
          dwPipeMode & 1,
          MaxInstances,
          nInBufferSize,
          nOutBufferSize,
          &DefaultTimeOut);
  v13 = v19;
  if ( v19 == -1073741637 || v19 == -1073741808 )
    v13 = -1073741773;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( pAcl )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pAcl);
  if ( v13 < 0 )
    goto LABEL_29;
  if ( IoStatusBlock.Information == 1 )
    v20 = 183;
  else
    v20 = 0;
  RtlSetLastWin32Error(v20);
  return NamedPipeFileHandle;
}

```

## disassembly

```asm
0x1800e51c0  push    rbp
0x1800e51c2  push    rbx
0x1800e51c3  push    rsi
0x1800e51c4  push    rdi
0x1800e51c5  push    r12
0x1800e51c7  push    r14
0x1800e51c9  push    r15
0x1800e51cb  lea     rbp, [rsp-10h]
0x1800e51d0  sub     rsp, 110h
0x1800e51d7  xor     eax, eax
0x1800e51d9  xorps   xmm0, xmm0
0x1800e51dc  mov     [rbp+40h+NamedPipeFileHandle], rax
0x1800e51e0  xorps   xmm1, xmm1
0x1800e51e3  mov     qword ptr [rsp+140h+var_C8], rax
0x1800e51e8  mov     r12d, r8d
0x1800e51eb  mov     [rbp+40h+NtFileNamePart], rax
0x1800e51ef  mov     esi, edx
0x1800e51f1  mov     [rbp+40h+var_40], rax
0x1800e51f5  mov     [rsp+140h+pAcl], rax
0x1800e51fa  lea     eax, [r9-1]
0x1800e51fe  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x1800e5202  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x1800e5206  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x1800e520a  movups  xmmword ptr [rbp+40h+NtPathName.Length], xmm0
0x1800e520e  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm1
0x1800e5212  movups  [rbp+40h+SecurityDescriptor], xmm0
0x1800e5216  movups  [rbp+40h+var_50], xmm0
0x1800e521a  cmp     eax, 0FEh
0x1800e521f  ja      loc_1800E550B
0x1800e5225  or      r15d, 0FFFFFFFFh
0x1800e5229  lea     r8, [rbp+40h+NtFileNamePart]; NtFileNamePart
0x1800e522d  cmp     r9d, 0FFh
0x1800e5234  lea     rdx, [rbp+40h+NtPathName]; NtPathName
0x1800e5238  cmovnz  r15d, r9d
0x1800e523c  xor     r9d, r9d; DirectoryInfo
0x1800e523f  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800e5245  test    al, al
0x1800e5247  jz      loc_1800E54AA
0x1800e524d  mov     rdx, [rbp+40h+lpSecurityAttributes]
0x1800e5254  lea     rax, [rbp+40h+NtPathName]
0x1800e5258  mov     rdi, [rbp+40h+NtPathName.Buffer]
0x1800e525c  mov     ecx, 40h ; '@'
0x1800e5261  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x1800e5268  xorps   xmm0, xmm0
0x1800e526b  mov     [rbp+40h+ObjectAttributes.RootDirectory], 0
0x1800e5273  mov     [rbp+40h+ObjectAttributes.Attributes], ecx
0x1800e5276  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x1800e527a  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800e527f  test    rdx, rdx
0x1800e5282  jnz     short loc_1800E52C6
0x1800e5284  lea     rcx, [rsp+140h+pAcl]; pAcl
0x1800e5289  call    cs:__imp_RtlDefaultNpAcl
0x1800e528f  mov     ebx, eax
0x1800e5291  test    eax, eax
0x1800e5293  js      loc_1800E5452
0x1800e5299  mov     edx, 1; Revision
0x1800e529e  lea     rcx, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x1800e52a2  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800e52a8  mov     r8, [rsp+140h+pAcl]; Dacl
0x1800e52ad  lea     rcx, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x1800e52b1  xor     r9d, r9d; DaclDefaulted
0x1800e52b4  mov     dl, 1; DaclPresent
0x1800e52b6  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800e52bc  lea     rax, [rbp+40h+SecurityDescriptor]
0x1800e52c0  mov     [rbp+40h+ObjectAttributes.SecurityDescriptor], rax
0x1800e52c4  jmp     short loc_1800E52E4
0x1800e52c6  cmp     dword ptr [rdx+10h], 0
0x1800e52ca  mov     r8d, 42h ; 'B'
0x1800e52d0  mov     rax, [rdx+8]
0x1800e52d4  cmovnz  ecx, r8d
0x1800e52d8  mov     [rbp+40h+ObjectAttributes.SecurityDescriptor], rax
0x1800e52dc  mov     [rbp+40h+ObjectAttributes.Attributes], ecx
0x1800e52df  test    rax, rax
0x1800e52e2  jz      short loc_1800E5284
0x1800e52e4  mov     eax, [rbp+40h+nDefaultTimeOut]
0x1800e52ea  mov     r11d, esi
0x1800e52ed  shr     r11d, 19h
0x1800e52f1  not     r11d
0x1800e52f4  and     r11d, 20h
0x1800e52f8  test    eax, eax
0x1800e52fa  jnz     loc_1800E5497
0x1800e5300  mov     rcx, 0FFFFFFFFFFF85EE0h
0x1800e5307  test    esi, 3EF3FFFCh
0x1800e530d  mov     qword ptr [rsp+140h+var_C8], rcx
0x1800e5312  setz    cl
0x1800e5315  test    r12d, 0FFFFFFF0h
0x1800e531c  setz    al
0x1800e531f  test    al, cl
0x1800e5321  jz      loc_1800E54D1
0x1800e5327  mov     eax, esi
0x1800e5329  mov     ebx, 3
0x1800e532e  and     eax, ebx
0x1800e5330  sub     eax, 1
0x1800e5333  jz      loc_1800E5487
0x1800e5339  sub     eax, 1
0x1800e533c  jz      loc_1800E54B7
0x1800e5342  cmp     eax, 1
0x1800e5345  jnz     loc_1800E54D1
0x1800e534b  mov     r14d, 0C0100000h
0x1800e5351  mov     ecx, esi
0x1800e5353  mov     edx, esi
0x1800e5355  mov     eax, r12d
0x1800e5358  mov     r9d, r12d
0x1800e535b  shr     eax, 2
0x1800e535e  mov     r10d, r12d
0x1800e5361  and     eax, 1
0x1800e5364  shr     r9d, 1
0x1800e5367  mov     r8d, eax
0x1800e536a  and     r9d, 1
0x1800e536e  or      r8d, 2
0x1800e5372  and     r10d, 1
0x1800e5376  test    r12b, 8
0x1800e537a  cmovz   r8d, eax
0x1800e537e  shr     ecx, 13h
0x1800e5381  sar     edx, 1Fh
0x1800e5384  lea     rax, [rsp+140h+var_C8]
0x1800e5389  mov     [rsp+140h+DefaultTimeOut], rax; DefaultTimeOut
0x1800e538e  not     ecx
0x1800e5390  mov     eax, [rbp+40h+nOutBufferSize]
0x1800e5393  and     edx, 2
0x1800e5396  mov     [rsp+140h+OutBufferSize], eax; OutBufferSize
0x1800e539a  and     ecx, 1
0x1800e539d  mov     eax, [rbp+40h+nInBufferSize]
0x1800e53a0  or      edx, r11d
0x1800e53a3  mov     [rsp+140h+InBufferSize], eax; InBufferSize
0x1800e53a7  or      ecx, 2
0x1800e53aa  mov     [rsp+140h+MaxInstances], r15d; MaxInstances
0x1800e53af  and     esi, 10C0000h
0x1800e53b5  mov     [rsp+140h+NonBlocking], r10d; NonBlocking
0x1800e53ba  or      esi, r14d
0x1800e53bd  mov     [rsp+140h+ReadModeMessage], r9d; ReadModeMessage
0x1800e53c2  lea     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x1800e53c6  mov     [rsp+140h+WriteModeMessage], r8d; WriteModeMessage
0x1800e53cb  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x1800e53cf  mov     [rsp+140h+CreateOptions], edx; CreateOptions
0x1800e53d3  mov     edx, esi; DesiredAccess
0x1800e53d5  mov     [rsp+140h+CreateDisposition], ecx; CreateDisposition
0x1800e53d9  lea     rcx, [rbp+40h+NamedPipeFileHandle]; NamedPipeFileHandle
0x1800e53dd  mov     [rsp+140h+ShareAccess], ebx; ShareAccess
0x1800e53e1  call    cs:__imp_NtCreateNamedPipeFile
0x1800e53e7  mov     ebx, eax
0x1800e53e9  cmp     eax, 0C00000BBh
0x1800e53ee  jz      loc_1800E54C7
0x1800e53f4  cmp     eax, 0C0000010h
0x1800e53f9  jz      loc_1800E54C7
0x1800e53ff  mov     rcx, gs:60h
0x1800e5408  mov     r8, rdi; P
0x1800e540b  xor     edx, edx; Flags
0x1800e540d  mov     rcx, [rcx+30h]; HeapHandle
0x1800e5411  call    cs:__imp_RtlFreeHeap
0x1800e5417  cmp     [rsp+140h+pAcl], 0
0x1800e541d  jz      short loc_1800E5439
0x1800e541f  mov     rcx, gs:60h
0x1800e5428  xor     edx, edx; Flags
0x1800e542a  mov     r8, [rsp+140h+pAcl]; P
0x1800e542f  mov     rcx, [rcx+30h]; HeapHandle
0x1800e5433  call    cs:__imp_RtlFreeHeap
0x1800e5439  test    ebx, ebx
0x1800e543b  js      short loc_1800E546A
0x1800e543d  cmp     [rbp+40h+IoStatusBlock.Information], 1
0x1800e5442  jz      short loc_1800E54A3
0x1800e5444  xor     ecx, ecx; LastError
0x1800e5446  call    cs:__imp_RtlSetLastWin32Error
0x1800e544c  mov     rax, [rbp+40h+NamedPipeFileHandle]
0x1800e5450  jmp     short loc_1800E5475
0x1800e5452  mov     rcx, gs:60h
0x1800e545b  mov     r8, rdi; P
0x1800e545e  xor     edx, edx; Flags
0x1800e5460  mov     rcx, [rcx+30h]; HeapHandle
0x1800e5464  call    cs:__imp_RtlFreeHeap
0x1800e546a  mov     ecx, ebx
0x1800e546c  call    BaseSetLastNTError
0x1800e5471  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e5475  add     rsp, 110h
0x1800e547c  pop     r15
0x1800e547e  pop     r14
0x1800e5480  pop     r12
0x1800e5482  pop     rdi
0x1800e5483  pop     rsi
0x1800e5484  pop     rbx
0x1800e5485  pop     rbp
0x1800e5486  retn
0x1800e5487  mov     ebx, 2
0x1800e548c  mov     r14d, 80100000h
0x1800e5492  jmp     loc_1800E5351
0x1800e5497  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x1800e549e  jmp     loc_1800E5307
0x1800e54a3  mov     ecx, 0B7h
0x1800e54a8  jmp     short loc_1800E5446
0x1800e54aa  mov     ecx, 3; LastError
0x1800e54af  call    cs:__imp_RtlSetLastWin32Error
0x1800e54b5  jmp     short loc_1800E5471
0x1800e54b7  mov     ebx, 1
0x1800e54bc  mov     r14d, 40100000h
0x1800e54c2  jmp     loc_1800E5351
0x1800e54c7  mov     ebx, 0C0000033h
0x1800e54cc  jmp     loc_1800E53FF
0x1800e54d1  mov     rcx, gs:60h
0x1800e54da  mov     r8, rdi; P
0x1800e54dd  xor     edx, edx; Flags
0x1800e54df  mov     rcx, [rcx+30h]; HeapHandle
0x1800e54e3  call    cs:__imp_RtlFreeHeap
0x1800e54e9  cmp     [rsp+140h+pAcl], 0
0x1800e54ef  jz      short loc_1800E550B
0x1800e54f1  mov     rcx, gs:60h
0x1800e54fa  xor     edx, edx; Flags
0x1800e54fc  mov     r8, [rsp+140h+pAcl]; P
0x1800e5501  mov     rcx, [rcx+30h]; HeapHandle
0x1800e5505  call    cs:__imp_RtlFreeHeap
0x1800e550b  mov     ecx, 0C000000Dh
0x1800e5510  jmp     loc_1800E546C
```
