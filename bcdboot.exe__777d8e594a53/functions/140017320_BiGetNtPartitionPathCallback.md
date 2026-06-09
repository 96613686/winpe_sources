# BiGetNtPartitionPathCallback

- ea: `0x140017320`
- end: `0x14001764f`
- name: `BiGetNtPartitionPathCallback`
- size: `815`
- prototype: `char __fastcall(__int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140001864`
- `0x140016fe4`
- `0x140017320`
- `0x140017800`

## import_xrefs

- `msvcrt!swprintf_s` at `0x140017455`
- `msvcrt!swprintf_s` at `0x1400175bb`
- `msvcrt!swprintf_s` at `0x140017455`
- `msvcrt!swprintf_s` at `0x1400175bb`
- `ntdll!ZwClose` at `0x1400174b5`
- `ntdll!ZwClose` at `0x1400174b5`
- `ntdll!RtlFreeHeap` at `0x140017412`
- `ntdll!RtlFreeHeap` at `0x1400174d0`
- `ntdll!RtlFreeHeap` at `0x140017524`
- `ntdll!RtlFreeHeap` at `0x1400175fe`
- `ntdll!RtlFreeHeap` at `0x140017412`
- `ntdll!RtlFreeHeap` at `0x1400174d0`
- `ntdll!RtlFreeHeap` at `0x140017524`
- `ntdll!RtlFreeHeap` at `0x1400175fe`
- `ntdll!RtlInitUnicodeString` at `0x140017462`
- `ntdll!RtlInitUnicodeString` at `0x140017462`
- `ntdll!ZwOpenFile` at `0x1400174a7`
- `ntdll!ZwOpenFile` at `0x1400174a7`

## pseudocode

```c
char __fastcall BiGetNtPartitionPathCallback(__int64 a1, unsigned int a2, __int64 a3)
{
  wchar_t *v3; // r14
  wchar_t *v4; // rsi
  _QWORD *v5; // r13
  __int64 v6; // rbx
  char v7; // di
  _DWORD *v8; // r12
  _DWORD *v9; // r15
  wchar_t *v10; // rbx
  int v11; // r14d
  wchar_t *v12; // rsi
  const wchar_t *v13; // rax
  _QWORD *v15; // rsi
  __int64 v16; // r13
  const wchar_t *PartitionVhdFilePath; // rax
  bool v18; // zf
  __int64 ShareAccess; // [rsp+28h] [rbp-89h]
  PVOID P; // [rsp+38h] [rbp-79h] BYREF
  wchar_t *Buffer; // [rsp+40h] [rbp-71h]
  void *FileHandle; // [rsp+48h] [rbp-69h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-61h]
  _OWORD v24[2]; // [rsp+58h] [rbp-59h] BYREF
  __int64 v25; // [rsp+78h] [rbp-39h]
  _QWORD *v26; // [rsp+80h] [rbp-31h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp+17h] BYREF
  char v32; // [rsp+130h] [rbp+7Fh]

  v3 = *(wchar_t **)(a3 + 8);
  v4 = *(wchar_t **)(a3 + 16);
  v5 = *(_QWORD **)(a3 + 32);
  v6 = *(_QWORD *)(a3 + 24);
  v7 = 0;
  v8 = *(_DWORD **)(a3 + 40);
  v25 = 0;
  FileHandle = 0;
  P = 0;
  v32 = *(_BYTE *)(a3 + 1);
  String1 = v3;
  memset(v24, 0, sizeof(v24));
  Buffer = v4;
  v26 = v5;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  if ( (int)BiGetDriveLayoutBlock(a1, &P, v24) < 0 )
    return v7;
  if ( LODWORD(v24[0]) == 7 )
  {
    if ( *(_DWORD *)v6 != 7 )
      goto LABEL_6;
  }
  else if ( v3 )
  {
    goto LABEL_6;
  }
  if ( *(_OWORD *)(v6 + 4) != *(_OWORD *)((char *)v24 + 4) || *(_DWORD *)(v6 + 20) != DWORD1(v24[1]) )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    return v7;
  }
LABEL_6:
  v9 = P;
  v10 = 0;
  if ( *(_DWORD *)P )
  {
    if ( *(_DWORD *)P == 1 )
      v11 = 0;
    else
      v11 = 2;
  }
  else
  {
    v11 = 1;
  }
  if ( !v8 )
  {
    if ( v11 == 1 )
      goto LABEL_33;
    goto LABEL_32;
  }
  if ( v11 != 1 )
  {
LABEL_32:
    if ( v11 )
      goto LABEL_20;
LABEL_33:
    v15 = 0;
    if ( !v11 )
    {
      if ( v8 )
      {
        v15 = v8;
      }
      else if ( v5 )
      {
        v15 = v5;
      }
    }
    v16 = 0;
    if ( !*((_DWORD *)P + 1) )
      goto LABEL_20;
    while ( 1 )
    {
      if ( v9[36 * v16 + 18] )
      {
        LODWORD(ShareAccess) = v9[36 * v16 + 18];
        swprintf_s(Buffer, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", a2, ShareAccess);
        if ( v32 )
        {
          PartitionVhdFilePath = (const wchar_t *)BiGetPartitionVhdFilePath(Buffer);
          v10 = (wchar_t *)PartitionVhdFilePath;
          if ( PartitionVhdFilePath )
          {
            if ( !wcsicmp_0(String1, PartitionVhdFilePath) )
              goto LABEL_19;
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
            v10 = 0;
          }
        }
        if ( v11 == 1 )
        {
          if ( v26 )
          {
            v18 = *v26 == *(_QWORD *)&v9[36 * v16 + 14];
            goto LABEL_50;
          }
        }
        else if ( v15 && *v15 == *(_QWORD *)&v9[36 * v16 + 24] )
        {
          v18 = v15[1] == *(_QWORD *)&v9[36 * v16 + 26];
LABEL_50:
          if ( v18 )
            goto LABEL_19;
        }
      }
      v16 = (unsigned int)(v16 + 1);
      if ( (unsigned int)v16 >= v9[1] )
        goto LABEL_20;
    }
  }
  swprintf_s(v4, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", a2, *v8);
  RtlInitUnicodeString(&DestinationString, v4);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 3u, 0) >= 0 )
  {
    ZwClose(FileHandle);
LABEL_19:
    v7 = 1;
  }
LABEL_20:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  v12 = String1;
  if ( !String1 || v32 || !v7 )
  {
LABEL_26:
    if ( !v10 )
      goto LABEL_28;
    goto LABEL_27;
  }
  v13 = (const wchar_t *)BiGetPartitionVhdFilePath(Buffer);
  v10 = (wchar_t *)v13;
  if ( !v13 || wcsicmp_0(v12, v13) )
  {
    v7 = 0;
    goto LABEL_26;
  }
LABEL_27:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
LABEL_28:
  if ( v7 )
    *(_BYTE *)a3 = 1;
  return v7;
}

```

## disassembly

```asm
0x140017320  mov     rax, rsp
0x140017323  mov     [rax+8], rbx
0x140017327  mov     [rax+18h], r8
0x14001732b  mov     [rax+10h], edx
0x14001732e  push    rbp
0x14001732f  push    rsi
0x140017330  push    rdi
0x140017331  push    r12
0x140017333  push    r13
0x140017335  push    r14
0x140017337  push    r15
0x140017339  lea     rbp, [rax-5Fh]
0x14001733d  sub     rsp, 0D0h
0x140017344  mov     r14, [r8+8]
0x140017348  xorps   xmm0, xmm0
0x14001734b  mov     rsi, [r8+10h]
0x14001734f  xor     edx, edx
0x140017351  mov     r13, [r8+20h]
0x140017355  xorps   xmm1, xmm1
0x140017358  mov     rbx, [r8+18h]
0x14001735c  xor     dil, dil
0x14001735f  mov     r12, [r8+28h]
0x140017363  mov     [rbp+57h+var_90], rdx
0x140017367  mov     [rbp+57h+FileHandle], rdx
0x14001736b  mov     [rbp+57h+P], rdx
0x14001736f  mov     dl, [r8+1]
0x140017373  lea     r8, [rbp+57h+var_B0]
0x140017377  mov     [rbp+57h+arg_18], dl
0x14001737a  lea     rdx, [rbp+57h+P]
0x14001737e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140017382  mov     [rbp+57h+String1], r14
0x140017386  movups  [rbp+57h+var_B0], xmm0
0x14001738a  mov     [rbp+57h+Buffer], rsi
0x14001738e  movups  [rbp+57h+var_A0], xmm0
0x140017392  mov     [rbp+57h+var_88], r13
0x140017396  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14001739a  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14001739e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400173a2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1400173a6  call    BiGetDriveLayoutBlock
0x1400173ab  test    eax, eax
0x1400173ad  js      loc_140017536
0x1400173b3  cmp     dword ptr [rbp+57h+var_B0], 7
0x1400173b7  jnz     short loc_1400173F8
0x1400173b9  cmp     dword ptr [rbx], 7
0x1400173bc  jnz     short loc_1400173F2
0x1400173be  mov     rax, [rbx+4]
0x1400173c2  cmp     rax, qword ptr [rbp+57h+var_B0+4]
0x1400173c6  jnz     short loc_1400173FF
0x1400173c8  mov     rax, [rbx+0Ch]
0x1400173cc  cmp     rax, qword ptr [rbp+57h+var_B0+0Ch]
0x1400173d0  jnz     short loc_1400173FF
0x1400173d2  mov     eax, [rbx+14h]
0x1400173d5  cmp     eax, dword ptr [rbp+57h+var_A0+4]
0x1400173d8  jnz     short loc_1400173FF
0x1400173da  mov     r15, [rbp+57h+P]
0x1400173de  xor     ebx, ebx
0x1400173e0  mov     ecx, [r15]
0x1400173e3  test    ecx, ecx
0x1400173e5  jz      short loc_140017422
0x1400173e7  cmp     ecx, 1
0x1400173ea  jz      short loc_14001741D
0x1400173ec  lea     r14d, [rbx+2]
0x1400173f0  jmp     short loc_140017428
0x1400173f2  cmp     dword ptr [rbp+57h+var_B0], 7
0x1400173f6  jz      short loc_1400173DA
0x1400173f8  test    r14, r14
0x1400173fb  jnz     short loc_1400173DA
0x1400173fd  jmp     short loc_1400173BE
0x1400173ff  mov     rcx, gs:60h
0x140017408  xor     edx, edx; Flags
0x14001740a  mov     r8, [rbp+57h+P]; P
0x14001740e  mov     rcx, [rcx+30h]; HeapHandle
0x140017412  call    cs:__imp_RtlFreeHeap
0x140017418  jmp     loc_140017536
0x14001741d  xor     r14d, r14d
0x140017420  jmp     short loc_140017428
0x140017422  mov     r14d, 1
0x140017428  test    r12, r12
0x14001742b  jz      loc_140017554
0x140017431  cmp     r14d, 1
0x140017435  jnz     loc_14001755A
0x14001743b  mov     eax, [r12]
0x14001743f  lea     r8, aDeviceHarddisk_0; "\\Device\\Harddisk%lu\\Partition%lu"
0x140017446  mov     r9d, [rbp+57h+arg_8]
0x14001744a  lea     edx, [r14+34h]; BufferCount
0x14001744e  mov     rcx, rsi; Buffer
0x140017451  mov     [rsp+100h+ShareAccess], eax
0x140017455  call    cs:__imp_swprintf_s
0x14001745b  mov     rdx, rsi; SourceString
0x14001745e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140017462  call    cs:__imp_RtlInitUnicodeString
0x140017468  lea     rax, [rbp+57h+DestinationString]
0x14001746c  mov     [rsp+28h], ebx; OpenOptions
0x140017470  xorps   xmm0, xmm0
0x140017473  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140017477  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14001747b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140017482  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140017486  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x14001748a  mov     edx, 80000000h; DesiredAccess
0x14001748f  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140017496  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14001749a  mov     [rsp+100h+ShareAccess], 3; ShareAccess
0x1400174a2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400174a7  call    cs:__imp_ZwOpenFile
0x1400174ad  test    eax, eax
0x1400174af  js      short loc_1400174BE
0x1400174b1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400174b5  call    cs:__imp_ZwClose
0x1400174bb  mov     dil, 1
0x1400174be  mov     rcx, gs:60h
0x1400174c7  mov     r8, r15; P
0x1400174ca  xor     edx, edx; Flags
0x1400174cc  mov     rcx, [rcx+30h]; HeapHandle
0x1400174d0  call    cs:__imp_RtlFreeHeap
0x1400174d6  mov     rsi, [rbp+57h+String1]
0x1400174da  test    rsi, rsi
0x1400174dd  jz      short loc_14001750D
0x1400174df  cmp     [rbp+57h+arg_18], 0
0x1400174e3  jnz     short loc_14001750D
0x1400174e5  test    dil, dil
0x1400174e8  jz      short loc_14001750D
0x1400174ea  mov     rcx, [rbp+57h+Buffer]; SourceString
0x1400174ee  call    BiGetPartitionVhdFilePath
0x1400174f3  mov     rbx, rax
0x1400174f6  test    rax, rax
0x1400174f9  jz      short loc_14001750A
0x1400174fb  mov     rdx, rax; String2
0x1400174fe  mov     rcx, rsi; String1
0x140017501  call    _wcsicmp_0
0x140017506  test    eax, eax
0x140017508  jz      short loc_140017512
0x14001750a  xor     dil, dil
0x14001750d  test    rbx, rbx
0x140017510  jz      short loc_14001752A
0x140017512  mov     rcx, gs:60h
0x14001751b  mov     r8, rbx; P
0x14001751e  xor     edx, edx; Flags
0x140017520  mov     rcx, [rcx+30h]; HeapHandle
0x140017524  call    cs:__imp_RtlFreeHeap
0x14001752a  test    dil, dil
0x14001752d  jz      short loc_140017536
0x14001752f  mov     rax, [rbp+57h+arg_10]
0x140017533  mov     byte ptr [rax], 1
0x140017536  mov     rbx, [rsp+100h+arg_0]
0x14001753e  mov     al, dil
0x140017541  add     rsp, 0D0h
0x140017548  pop     r15
0x14001754a  pop     r14
0x14001754c  pop     r13
0x14001754e  pop     r12
0x140017550  pop     rdi
0x140017551  pop     rsi
0x140017552  pop     rbp
0x140017553  retn
0x140017554  cmp     r14d, 1
0x140017558  jz      short loc_140017563
0x14001755a  test    r14d, r14d
0x14001755d  jnz     loc_1400174BE
0x140017563  xor     esi, esi
0x140017565  test    r14d, r14d
0x140017568  jnz     short loc_14001757B
0x14001756a  test    r12, r12
0x14001756d  jz      short loc_140017574
0x14001756f  mov     rsi, r12
0x140017572  jmp     short loc_14001757B
0x140017574  test    r13, r13
0x140017577  cmovnz  rsi, r13
0x14001757b  xor     r13d, r13d
0x14001757e  cmp     [r15+4], ebx
0x140017582  jbe     loc_1400174BE
0x140017588  lea     r12, ds:0[r13*8]
0x140017590  add     r12, r13
0x140017593  add     r12, r12
0x140017596  mov     eax, [r15+r12*8+48h]
0x14001759b  test    eax, eax
0x14001759d  jz      loc_14001763D
0x1400175a3  mov     r9d, [rbp+57h+arg_8]
0x1400175a7  lea     r8, aDeviceHarddisk_0; "\\Device\\Harddisk%lu\\Partition%lu"
0x1400175ae  mov     rcx, [rbp+57h+Buffer]; Buffer
0x1400175b2  mov     edx, 35h ; '5'; BufferCount
0x1400175b7  mov     [rsp+100h+ShareAccess], eax
0x1400175bb  call    cs:__imp_swprintf_s
0x1400175c1  cmp     [rbp+57h+arg_18], dil
0x1400175c5  jz      short loc_140017606
0x1400175c7  mov     rcx, [rbp+57h+Buffer]; SourceString
0x1400175cb  call    BiGetPartitionVhdFilePath
0x1400175d0  mov     rbx, rax
0x1400175d3  test    rax, rax
0x1400175d6  jz      short loc_140017606
0x1400175d8  mov     rcx, [rbp+57h+String1]; String1
0x1400175dc  mov     rdx, rax; String2
0x1400175df  call    _wcsicmp_0
0x1400175e4  test    eax, eax
0x1400175e6  jz      loc_1400174BB
0x1400175ec  mov     rcx, gs:60h
0x1400175f5  mov     r8, rbx; P
0x1400175f8  xor     edx, edx; Flags
0x1400175fa  mov     rcx, [rcx+30h]; HeapHandle
0x1400175fe  call    cs:__imp_RtlFreeHeap
0x140017604  xor     ebx, ebx
0x140017606  cmp     r14d, 1
0x14001760a  jnz     short loc_14001761F
0x14001760c  mov     rcx, [rbp+57h+var_88]
0x140017610  test    rcx, rcx
0x140017613  jz      short loc_14001763D
0x140017615  mov     rax, [r15+r12*8+38h]
0x14001761a  cmp     [rcx], rax
0x14001761d  jmp     short loc_140017637
0x14001761f  test    rsi, rsi
0x140017622  jz      short loc_14001763D
0x140017624  mov     rax, [rsi]
0x140017627  cmp     rax, [r15+r12*8+60h]
0x14001762c  jnz     short loc_14001763D
0x14001762e  mov     rax, [rsi+8]
0x140017632  cmp     rax, [r15+r12*8+68h]
0x140017637  jz      loc_1400174BB
0x14001763d  inc     r13d
0x140017640  cmp     r13d, [r15+4]
0x140017644  jb      loc_140017588
0x14001764a  jmp     loc_1400174BE
```
