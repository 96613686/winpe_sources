# BfspBackupCorruptStore

- ea: `0x1400045c8`
- end: `0x140004821`
- name: `BfspBackupCorruptStore`
- size: `601`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140004080`

## callees

- `0x1400045c8`
- `0x14001c14c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400047fd`
- `KERNEL32!HeapFree` at `0x1400047fd`
- `KERNEL32!HeapAlloc` at `0x1400046b5`
- `KERNEL32!HeapAlloc` at `0x1400046b5`
- `KERNEL32!GetProcessHeap` at `0x1400046a4`
- `KERNEL32!GetProcessHeap` at `0x1400047ef`
- `KERNEL32!GetProcessHeap` at `0x1400046a4`
- `KERNEL32!GetProcessHeap` at `0x1400047ef`
- `ntdll!RtlFreeHeap` at `0x1400047e4`
- `ntdll!RtlFreeHeap` at `0x1400047e4`
- `ntdll!NtSetInformationFile` at `0x1400047b6`
- `ntdll!NtSetInformationFile` at `0x1400047b6`
- `ntdll!NtOpenFile` at `0x140004687`
- `ntdll!NtOpenFile` at `0x140004687`
- `ntdll!NtClose` at `0x1400047c7`
- `ntdll!NtClose` at `0x1400047c7`
- `ntdll!RtlInitUnicodeString` at `0x140004634`
- `ntdll!RtlInitUnicodeString` at `0x140004634`

## pseudocode

```c
__int64 __fastcall BfspBackupCorruptStore(struct _UNICODE_STRING *a1)
{
  WCHAR *v1; // rsi
  char *v2; // rdi
  int SystemStorePath; // eax
  NTSTATUS v4; // ebx
  unsigned int v5; // r14d
  ULONG v6; // r15d
  HANDLE ProcessHeap; // rax
  _WORD *v8; // rax
  unsigned __int64 v9; // rdx
  PWSTR Buffer; // r11
  _WORD *v11; // r9
  __int64 v12; // r10
  _WORD *v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // r8
  bool v16; // zf
  _WORD *v17; // rcx
  unsigned __int64 v18; // r8
  __int64 v19; // r9
  char *v20; // rax
  const wchar_t *v21; // rcx
  unsigned __int64 i; // r8
  char *v23; // rcx
  HANDLE v24; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  PCWSTR SourceString; // [rsp+B0h] [rbp+30h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+38h] BYREF

  SourceString = 0;
  FileHandle = 0;
  v1 = 0;
  v2 = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a1 )
  {
    DestinationString = *a1;
  }
  else
  {
    SystemStorePath = BcdGetSystemStorePath((wchar_t **)&SourceString);
    v1 = (WCHAR *)SourceString;
    v4 = SystemStorePath;
    if ( SystemStorePath < 0 )
      goto LABEL_27;
    RtlInitUnicodeString(&DestinationString, SourceString);
  }
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenFile(&FileHandle, 0x110080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4020u);
  if ( v4 >= 0 )
  {
    v5 = DestinationString.Length + 18;
    v6 = DestinationString.Length + 38;
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 8u, v6);
    v2 = (char *)v8;
    if ( v8 )
    {
      *(_DWORD *)v8 = 1;
      *((_QWORD *)v8 + 1) = 0;
      v9 = (unsigned __int64)v5 >> 1;
      *((_DWORD *)v8 + 4) = v5 - 2;
      if ( v9 )
      {
        Buffer = DestinationString.Buffer;
        v11 = v8 + 10;
        v12 = 2147483646;
        v13 = v8 + 10;
        v14 = 2147483646;
        v15 = (unsigned __int64)v5 >> 1;
        do
        {
          if ( !v14 )
            break;
          if ( !*Buffer )
            break;
          *v13++ = *Buffer++;
          --v14;
          --v15;
        }
        while ( v15 );
        v16 = v15 == 0;
        v17 = v13 - 1;
        v18 = (unsigned __int64)v5 >> 1;
        if ( !v16 )
          v17 = v13;
        *v17 = 0;
        do
        {
          if ( !*v11 )
            break;
          ++v11;
          --v9;
        }
        while ( v9 );
        v19 = (v18 - v9) & -(__int64)(v9 != 0);
        if ( v9 )
        {
          v20 = &v2[2 * v19 + 20];
          v21 = L".corrupt";
          for ( i = v18 - v19; i; --i )
          {
            if ( !v12 )
              break;
            if ( !*v21 )
              break;
            *(_WORD *)v20 = *v21++;
            v20 += 2;
            --v12;
          }
          v23 = v20 - 2;
          if ( i )
            v23 = v20;
          *(_WORD *)v23 = 0;
        }
      }
      v4 = NtSetInformationFile(FileHandle, &IoStatusBlock, v2, v6, FileRenameInformation);
    }
    else
    {
      v4 = -1073741801;
    }
  }
LABEL_27:
  if ( FileHandle )
    NtClose(FileHandle);
  if ( v1 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
  if ( v2 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v2);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400045c8  mov     [rsp-28h+arg_10], rbx
0x1400045cd  mov     [rsp-28h+arg_18], rsi
0x1400045d2  push    rbp
0x1400045d3  push    rdi
0x1400045d4  push    r12
0x1400045d6  push    r14
0x1400045d8  push    r15
0x1400045da  mov     rbp, rsp
0x1400045dd  sub     rsp, 80h
0x1400045e4  xor     r12d, r12d
0x1400045e7  xorps   xmm0, xmm0
0x1400045ea  xor     eax, eax
0x1400045ec  mov     [rbp+SourceString], r12
0x1400045f0  mov     [rbp+FileHandle], r12
0x1400045f4  xorps   xmm1, xmm1
0x1400045f7  mov     esi, r12d
0x1400045fa  mov     edi, r12d
0x1400045fd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140004601  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140004605  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140004609  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x14000460d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140004611  test    rcx, rcx
0x140004614  jnz     short loc_14000463C
0x140004616  lea     rcx, [rbp+SourceString]
0x14000461a  call    BcdGetSystemStorePath
0x14000461f  mov     rsi, [rbp+SourceString]
0x140004623  mov     ebx, eax
0x140004625  test    eax, eax
0x140004627  js      loc_1400047BE
0x14000462d  mov     rdx, rsi; SourceString
0x140004630  lea     rcx, [rbp+DestinationString]; DestinationString
0x140004634  call    cs:__imp_RtlInitUnicodeString
0x14000463a  jmp     short loc_140004644
0x14000463c  movups  xmm0, xmmword ptr [rcx]
0x14000463f  movdqu  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140004644  lea     rax, [rbp+DestinationString]
0x140004648  mov     [rsp+80h+OpenOptions], 4020h; OpenOptions
0x140004650  xorps   xmm0, xmm0
0x140004653  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140004657  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14000465b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140004662  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140004666  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x14000466a  mov     edx, 110080h; DesiredAccess
0x14000466f  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140004676  lea     rcx, [rbp+FileHandle]; FileHandle
0x14000467a  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x140004682  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140004687  call    cs:__imp_NtOpenFile
0x14000468d  mov     ebx, eax
0x14000468f  test    eax, eax
0x140004691  js      loc_1400047BE
0x140004697  movzx   r14d, [rbp+DestinationString.Length]
0x14000469c  add     r14d, 12h
0x1400046a0  lea     r15d, [r14+14h]
0x1400046a4  call    cs:__imp_GetProcessHeap
0x1400046aa  mov     r8d, r15d; dwBytes
0x1400046ad  mov     edx, 8; dwFlags
0x1400046b2  mov     rcx, rax; hHeap
0x1400046b5  call    cs:__imp_HeapAlloc
0x1400046bb  mov     rdi, rax
0x1400046be  test    rax, rax
0x1400046c1  jnz     short loc_1400046CD
0x1400046c3  mov     ebx, 0C0000017h
0x1400046c8  jmp     loc_1400047BE
0x1400046cd  mov     dword ptr [rax], 1
0x1400046d3  mov     [rax+8], r12
0x1400046d7  lea     eax, [r14-2]
0x1400046db  mov     edx, r14d
0x1400046de  shr     rdx, 1
0x1400046e1  mov     [rdi+10h], eax
0x1400046e4  jz      loc_1400047A0
0x1400046ea  mov     r11, [rbp+DestinationString.Buffer]
0x1400046ee  lea     r9, [rdi+14h]
0x1400046f2  mov     r10d, 7FFFFFFEh
0x1400046f8  mov     rax, r9
0x1400046fb  mov     ecx, r10d
0x1400046fe  mov     r8, rdx
0x140004701  test    rcx, rcx
0x140004704  jz      short loc_140004723
0x140004706  movzx   ebx, word ptr [r11]
0x14000470a  test    bx, bx
0x14000470d  jz      short loc_140004723
0x14000470f  mov     [rax], bx
0x140004712  add     r11, 2
0x140004716  add     rax, 2
0x14000471a  dec     rcx
0x14000471d  sub     r8, 1
0x140004721  jnz     short loc_140004701
0x140004723  test    r8, r8
0x140004726  lea     rcx, [rax-2]
0x14000472a  mov     r8, rdx
0x14000472d  cmovnz  rcx, rax
0x140004731  mov     [rcx], r12w
0x140004735  cmp     [r9], r12w
0x140004739  jz      short loc_140004745
0x14000473b  add     r9, 2
0x14000473f  sub     rdx, 1
0x140004743  jnz     short loc_140004735
0x140004745  mov     rcx, r8
0x140004748  mov     rax, rdx
0x14000474b  sub     rcx, rdx
0x14000474e  neg     rax
0x140004751  sbb     r9, r9
0x140004754  and     r9, rcx
0x140004757  test    rdx, rdx
0x14000475a  jz      short loc_1400047A0
0x14000475c  lea     rax, [rdi+14h]
0x140004760  lea     rax, [rax+r9*2]
0x140004764  lea     rcx, aCorrupt; ".corrupt"
0x14000476b  sub     r8, r9
0x14000476e  jz      short loc_140004791
0x140004770  test    r10, r10
0x140004773  jz      short loc_140004791
0x140004775  movzx   edx, word ptr [rcx]
0x140004778  test    dx, dx
0x14000477b  jz      short loc_140004791
0x14000477d  mov     [rax], dx
0x140004780  add     rcx, 2
0x140004784  add     rax, 2
0x140004788  dec     r10
0x14000478b  sub     r8, 1
0x14000478f  jnz     short loc_140004770
0x140004791  test    r8, r8
0x140004794  lea     rcx, [rax-2]
0x140004798  cmovnz  rcx, rax
0x14000479c  mov     [rcx], r12w
0x1400047a0  mov     rcx, [rbp+FileHandle]; FileHandle
0x1400047a4  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x1400047a8  mov     r9d, r15d; Length
0x1400047ab  mov     [rsp+80h+ShareAccess], 0Ah; FileInformationClass
0x1400047b3  mov     r8, rdi; FileInformation
0x1400047b6  call    cs:__imp_NtSetInformationFile
0x1400047bc  mov     ebx, eax
0x1400047be  mov     rcx, [rbp+FileHandle]; Handle
0x1400047c2  test    rcx, rcx
0x1400047c5  jz      short loc_1400047CD
0x1400047c7  call    cs:__imp_NtClose
0x1400047cd  test    rsi, rsi
0x1400047d0  jz      short loc_1400047EA
0x1400047d2  mov     rcx, gs:60h
0x1400047db  mov     r8, rsi; P
0x1400047de  xor     edx, edx; Flags
0x1400047e0  mov     rcx, [rcx+30h]; HeapHandle
0x1400047e4  call    cs:__imp_RtlFreeHeap
0x1400047ea  test    rdi, rdi
0x1400047ed  jz      short loc_140004803
0x1400047ef  call    cs:__imp_GetProcessHeap
0x1400047f5  mov     r8, rdi; lpMem
0x1400047f8  xor     edx, edx; dwFlags
0x1400047fa  mov     rcx, rax; hHeap
0x1400047fd  call    cs:__imp_HeapFree
0x140004803  lea     r11, [rsp+80h+var_s0]
0x14000480b  mov     eax, ebx
0x14000480d  mov     rbx, [r11+40h]
0x140004811  mov     rsi, [r11+48h]
0x140004815  mov     rsp, r11
0x140004818  pop     r15
0x14000481a  pop     r14
0x14000481c  pop     r12
0x14000481e  pop     rdi
0x14000481f  pop     rbp
0x140004820  retn
```
