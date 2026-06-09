# sub_1800EEF9C

- ea: `0x1800eef9c`
- end: `0x1800ef306`
- name: `sub_1800EEF9C`
- size: `874`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, loader_planting`

## callers

- `0x1800e6a1c`
- `0x1800eeef8`

## callees

- `0x180001f48`
- `0x180057e60`
- `0x1800589f0`
- `0x180068b50`
- `0x18008f654`
- `0x180098da4`
- `0x18009c1c0`
- `0x1800d94b0`
- `0x1800e5b80`
- `0x1800e8e38`
- `0x1800eef9c`
- `0x1800ef308`
- `0x1800ef360`
- `0x1801819e0`
- `0x180271ab0`
- `0x180271e70`

## import_xrefs

- `ntdll!ZwQueryEaFile` at `0x1800ef0a6`
- `ntdll!ZwQueryEaFile` at `0x1800ef13d`
- `ntdll!ZwQueryEaFile` at `0x1800ef0a6`
- `ntdll!ZwQueryEaFile` at `0x1800ef13d`
- `KERNEL32!CreateFileW` at `0x1800ef028`
- `KERNEL32!CreateFileW` at `0x1800ef028`
- `KERNEL32!CloseHandle` at `0x1800ef296`
- `KERNEL32!CloseHandle` at `0x1800ef296`

## string_xrefs

- `0x1800ef044`: `failed to open a file for getting EA`

## pseudocode

```c
_QWORD *__fastcall sub_1800EEF9C(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  char *FileW; // r14
  NTSTATUS v7; // eax
  unsigned int *v8; // rbx
  char v9; // dl
  NTSTATUS v10; // eax
  unsigned int Information; // esi
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD *v14; // rax
  _DWORD *v15; // rcx
  unsigned int v17; // eax
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v20[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h]
  char *v22; // [rsp+78h] [rbp-88h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-80h] BYREF
  _BYTE Buffer[4096]; // [rsp+90h] [rbp-70h] BYREF
  void *retaddr; // [rsp+10D8h] [rbp+FD8h]

  v19 = (__int64)a1;
  LODWORD(v18) = 1;
  *(_OWORD *)v20 = 0;
  v21 = 0;
  if ( !*(_QWORD *)(a2 + 8) )
    sub_1800E5B80();
  FileW = (char *)CreateFileW(*(LPCWSTR *)a2, 8u, 0, 0, 3u, 0x80u, 0);
  v22 = FileW;
  sub_1800EF308(
    (_DWORD)retaddr,
    81,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\WindowsDelphiEa\\src\\windowsDelphiEa.cpp",
    FileW + 1 != 0,
    (__int64)"failed to open a file for getting EA");
  IoStatusBlock = 0;
  sub_180271AB0(Buffer, 0, 4096);
  v7 = ZwQueryEaFile(FileW, &IoStatusBlock, Buffer, 0x1000u, 0, 0, 0, 0, 1u);
  if ( v7 < 0 )
  {
    _mm_lfence();
    if ( v7 == -1073741789 || (v9 = 1, v7 == -2147483643) )
      v9 = 0;
    sub_1800E8E38(
      (_DWORD)retaddr,
      109,
      (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\WindowsDelphiEa\\src\\windowsDelphiEa.cpp",
      v7 | 0x10000000,
      v9,
      (__int64)"ZwQueryEaFile failed");
    sub_180098DA4(v20, 0x4000);
    v10 = ZwQueryEaFile(FileW, &IoStatusBlock, v20[0], LODWORD(v20[1]) - LODWORD(v20[0]), 0, 0, 0, 0, 1u);
    sub_1800E8E38(
      (_DWORD)retaddr,
      124,
      (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\WindowsDelphiEa\\src\\windowsDelphiEa.cpp",
      v10 | 0x10000000,
      v10 < 0,
      (__int64)"ZwQueryEaFile failed");
    v8 = (unsigned int *)v20[0];
  }
  else
  {
    v8 = (unsigned int *)Buffer;
  }
  Information = IoStatusBlock.Information;
  while ( 1 )
  {
    if ( Information < 0xC )
      goto LABEL_24;
    v12 = *((unsigned __int8 *)v8 + 5);
    if ( v12 == a3[1] && Information >= (unsigned __int64)(v12 + 8) && !(unsigned int)sub_180068B50(v8 + 2, *a3) )
      break;
    if ( !*v8 )
      goto LABEL_24;
    sub_1800E8E38(
      (_DWORD)retaddr,
      165,
      (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\WindowsDelphiEa\\src\\windowsDelphiEa.cpp",
      -1879048172,
      *v8 >= Information,
      (__int64)"The extended attribute (EA) list is inconsistent");
    v13 = *v8;
    Information -= v13;
    v8 = (unsigned int *)((char *)v8 + v13);
  }
  if ( !*((_WORD *)v8 + 3)
    || Information < *((unsigned __int16 *)v8 + 3) + (unsigned __int64)*((unsigned __int8 *)v8 + 5) + 9 )
  {
LABEL_24:
    v17 = sub_1800D94B0(3489660980LL);
    sub_1800EF360(
      retaddr,
      172,
      "src\\epp\\Dlp\\EndpointDlp\\WindowsDelphiEa\\src\\windowsDelphiEa.cpp",
      v17,
      "Failed to find EA");
  }
  v14 = (_QWORD *)sub_1801819E0();
  v15 = (_DWORD *)*v14;
  if ( *(_DWORD *)*v14 > 5u )
  {
    v18 = *(_QWORD *)a2;
    v19 = (__int64)L"Found EA for the file";
    sub_180001F48((int)v15, (int)&byte_1802F9679, (__int64)&v19, (__int64)&v18);
  }
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  sub_18009C1C0(a1, *((unsigned __int16 *)v8 + 3));
  sub_180271E70(*a1, (char *)v8 + *((unsigned __int8 *)v8 + 5) + 9, *((unsigned __int16 *)v8 + 3));
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  sub_18008F654(v20);
  return a1;
}

```

## disassembly

```asm
0x1800eef9c  mov     [rsp-8+arg_18], rbx
0x1800eefa1  push    rbp
0x1800eefa2  push    rsi
0x1800eefa3  push    rdi
0x1800eefa4  push    r12
0x1800eefa6  push    r13
0x1800eefa8  push    r14
0x1800eefaa  push    r15
0x1800eefac  lea     rbp, [rsp-0FA0h]
0x1800eefb4  mov     eax, 10A0h
0x1800eefb9  call    __alloca_probe
0x1800eefbe  sub     rsp, rax
0x1800eefc1  mov     rax, cs:__security_cookie
0x1800eefc8  xor     rax, rsp
0x1800eefcb  mov     [rbp+0FD0h+var_40], rax
0x1800eefd2  mov     r13, r8
0x1800eefd5  mov     r12, rdx
0x1800eefd8  mov     rdi, rcx
0x1800eefdb  mov     [rsp+10D0h+var_1078], rcx
0x1800eefe0  mov     dword ptr [rsp+10D0h+var_1080], 1
0x1800eefe8  xorps   xmm1, xmm1
0x1800eefeb  movdqu  xmmword ptr [rsp+10D0h+var_1070], xmm1
0x1800eeff1  xor     r15d, r15d
0x1800eeff4  mov     [rsp+10D0h+var_1060], r15
0x1800eeff9  cmp     [rdx+8], r15
0x1800eeffd  jnz     short loc_1800EF005
0x1800eefff  call    sub_1800E5B80
0x1800ef004  nop
0x1800ef005  mov     [rsp+10D0h+hTemplateFile], r15; hTemplateFile
0x1800ef00a  mov     [rsp+10D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800ef012  mov     [rsp+10D0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ef01a  xor     r9d, r9d; lpSecurityAttributes
0x1800ef01d  xor     r8d, r8d; dwShareMode
0x1800ef020  lea     edx, [r9+8]; dwDesiredAccess
0x1800ef024  mov     rcx, [r12]; lpFileName
0x1800ef028  call    cs:CreateFileW
0x1800ef02e  mov     r14, rax
0x1800ef031  mov     [rsp+10D0h+var_1058], rax
0x1800ef036  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ef03a  setnz   al
0x1800ef03d  mov     rcx, [rbp+0FD8h]
0x1800ef044  lea     rdx, aFailedToOpenAF; "failed to open a file for getting EA"
0x1800ef04b  mov     qword ptr [rsp+10D0h+dwCreationDisposition], rdx
0x1800ef050  movzx   r9d, al
0x1800ef054  lea     r8, aSrcEppDlpEndpo_4; "src\\epp\\Dlp\\EndpointDlp\\WindowsDelp"...
0x1800ef05b  mov     edx, 51h ; 'Q'
0x1800ef060  call    sub_1800EF308
0x1800ef065  xorps   xmm0, xmm0
0x1800ef068  movups  xmmword ptr [rbp+0FD0h+IoStatusBlock], xmm0
0x1800ef06c  mov     ebx, 1000h
0x1800ef071  mov     r8d, ebx
0x1800ef074  xor     edx, edx
0x1800ef076  lea     rcx, [rbp+0FD0h+Buffer]
0x1800ef07a  call    sub_180271AB0
0x1800ef07f  mov     [rsp+10D0h+RestartScan], 1; RestartScan
0x1800ef084  mov     [rsp+10D0h+EaIndex], r15; EaIndex
0x1800ef089  mov     dword ptr [rsp+10D0h+hTemplateFile], r15d; EaListLength
0x1800ef08e  mov     qword ptr [rsp+10D0h+dwFlagsAndAttributes], r15; EaList
0x1800ef093  mov     byte ptr [rsp+10D0h+dwCreationDisposition], r15b; ReturnSingleEntry
0x1800ef098  mov     r9d, ebx; Length
0x1800ef09b  lea     r8, [rbp+0FD0h+Buffer]; Buffer
0x1800ef09f  lea     rdx, [rbp+0FD0h+IoStatusBlock]; IoStatusBlock
0x1800ef0a3  mov     rcx, r14; FileHandle
0x1800ef0a6  call    cs:ZwQueryEaFile
0x1800ef0ac  test    eax, eax
0x1800ef0ae  js      short loc_1800EF0B9
0x1800ef0b0  lea     rbx, [rbp+0FD0h+Buffer]
0x1800ef0b4  jmp     loc_1800EF172
0x1800ef0b9  lfence
0x1800ef0bc  cmp     eax, 0C0000023h
0x1800ef0c1  jz      short loc_1800EF0CC
0x1800ef0c3  cmp     eax, 80000005h
0x1800ef0c8  mov     dl, 1
0x1800ef0ca  jnz     short loc_1800EF0CF
0x1800ef0cc  mov     dl, r15b
0x1800ef0cf  mov     ebx, 10000000h
0x1800ef0d4  or      eax, ebx
0x1800ef0d6  mov     rcx, [rbp+0FD8h]
0x1800ef0dd  lea     rsi, aZwqueryeafileF; "ZwQueryEaFile failed"
0x1800ef0e4  mov     qword ptr [rsp+10D0h+dwFlagsAndAttributes], rsi
0x1800ef0e9  mov     byte ptr [rsp+10D0h+dwCreationDisposition], dl
0x1800ef0ed  mov     r9d, eax
0x1800ef0f0  lea     r8, aSrcEppDlpEndpo_4; "src\\epp\\Dlp\\EndpointDlp\\WindowsDelp"...
0x1800ef0f7  mov     edx, 6Dh ; 'm'
0x1800ef0fc  call    sub_1800E8E38
0x1800ef101  mov     edx, 4000h
0x1800ef106  lea     rcx, [rsp+10D0h+var_1070]
0x1800ef10b  call    sub_180098DA4
0x1800ef110  mov     r9d, dword ptr [rsp+10D0h+var_1070+8]
0x1800ef115  mov     r8, [rsp+10D0h+var_1070]; Buffer
0x1800ef11a  sub     r9d, r8d; Length
0x1800ef11d  mov     [rsp+10D0h+RestartScan], 1; RestartScan
0x1800ef122  mov     [rsp+10D0h+EaIndex], r15; EaIndex
0x1800ef127  mov     dword ptr [rsp+10D0h+hTemplateFile], r15d; EaListLength
0x1800ef12c  mov     qword ptr [rsp+10D0h+dwFlagsAndAttributes], r15; EaList
0x1800ef131  mov     byte ptr [rsp+10D0h+dwCreationDisposition], r15b; ReturnSingleEntry
0x1800ef136  lea     rdx, [rbp+0FD0h+IoStatusBlock]; IoStatusBlock
0x1800ef13a  mov     rcx, r14; FileHandle
0x1800ef13d  call    cs:ZwQueryEaFile
0x1800ef143  mov     r9d, eax
0x1800ef146  shr     eax, 1Fh
0x1800ef149  or      r9d, ebx
0x1800ef14c  mov     rcx, [rbp+0FD8h]
0x1800ef153  mov     qword ptr [rsp+10D0h+dwFlagsAndAttributes], rsi
0x1800ef158  mov     byte ptr [rsp+10D0h+dwCreationDisposition], al
0x1800ef15c  lea     r8, aSrcEppDlpEndpo_4; "src\\epp\\Dlp\\EndpointDlp\\WindowsDelp"...
0x1800ef163  mov     edx, 7Ch ; '|'
0x1800ef168  call    sub_1800E8E38
0x1800ef16d  mov     rbx, [rsp+10D0h+var_1070]
0x1800ef172  mov     esi, dword ptr [rbp+0FD0h+IoStatusBlock.Information]
0x1800ef175  jmp     short loc_1800EF1E9
0x1800ef177  mov     r8, [r13+8]
0x1800ef17b  movzx   eax, byte ptr [rbx+5]
0x1800ef17f  cmp     rax, r8
0x1800ef182  jnz     short loc_1800EF1A6
0x1800ef184  mov     r15d, esi
0x1800ef187  add     rax, 8
0x1800ef18b  cmp     r15, rax
0x1800ef18e  jb      short loc_1800EF1A3
0x1800ef190  lea     rcx, [rbx+8]
0x1800ef194  mov     rdx, [r13+0]
0x1800ef198  call    sub_180068B50
0x1800ef19d  xor     ecx, ecx
0x1800ef19f  test    eax, eax
0x1800ef1a1  jz      short loc_1800EF1F4
0x1800ef1a3  xor     r15d, r15d
0x1800ef1a6  cmp     [rbx], r15d
0x1800ef1a9  jz      loc_1800EF2D4
0x1800ef1af  cmp     [rbx], esi
0x1800ef1b1  setnb   al
0x1800ef1b4  mov     rcx, [rbp+0FD8h]
0x1800ef1bb  lea     rdx, aTheExtendedAtt; "The extended attribute (EA) list is inc"...
0x1800ef1c2  mov     qword ptr [rsp+10D0h+dwFlagsAndAttributes], rdx
0x1800ef1c7  mov     byte ptr [rsp+10D0h+dwCreationDisposition], al
0x1800ef1cb  mov     r9d, 90000014h
0x1800ef1d1  lea     r8, aSrcEppDlpEndpo_4; "src\\epp\\Dlp\\EndpointDlp\\WindowsDelp"...
0x1800ef1d8  mov     edx, 0A5h
0x1800ef1dd  call    sub_1800E8E38
0x1800ef1e2  mov     eax, [rbx]
0x1800ef1e4  sub     esi, eax
0x1800ef1e6  add     rbx, rax
0x1800ef1e9  cmp     esi, 0Ch
0x1800ef1ec  jb      loc_1800EF2D4
0x1800ef1f2  jmp     short loc_1800EF177
0x1800ef1f4  cmp     [rbx+6], cx
0x1800ef1f8  jbe     loc_1800EF2D4
0x1800ef1fe  movzx   ecx, byte ptr [rbx+5]
0x1800ef202  movzx   eax, word ptr [rbx+6]
0x1800ef206  add     rcx, 9
0x1800ef20a  add     rcx, rax
0x1800ef20d  cmp     r15, rcx
0x1800ef210  jb      loc_1800EF2D4
0x1800ef216  call    sub_1801819E0
0x1800ef21b  mov     rcx, [rax]; int
0x1800ef21e  cmp     dword ptr [rcx], 5
0x1800ef221  jbe     short loc_1800EF258
0x1800ef223  mov     rax, [r12]
0x1800ef227  mov     [rsp+10D0h+var_1080], rax
0x1800ef22c  lea     rax, aFoundEaForTheF; "Found EA for the file"
0x1800ef233  mov     [rsp+10D0h+var_1078], rax
0x1800ef238  lea     rax, [rsp+10D0h+var_1080]
0x1800ef23d  mov     qword ptr [rsp+10D0h+dwFlagsAndAttributes], rax; __int64
0x1800ef242  lea     rax, [rsp+10D0h+var_1078]
0x1800ef247  mov     qword ptr [rsp+10D0h+dwCreationDisposition], rax; __int64
0x1800ef24c  lea     rdx, byte_1802F9679; int
0x1800ef253  call    sub_180001F48
0x1800ef258  xorps   xmm0, xmm0
0x1800ef25b  xor     eax, eax
0x1800ef25d  movups  xmmword ptr [rdi], xmm0
0x1800ef260  mov     [rdi+10h], rax
0x1800ef264  movzx   edx, word ptr [rbx+6]
0x1800ef268  mov     rcx, rdi
0x1800ef26b  call    sub_18009C1C0
0x1800ef270  movzx   r8d, word ptr [rbx+6]
0x1800ef275  movzx   edx, byte ptr [rbx+5]
0x1800ef279  add     rdx, 9
0x1800ef27d  add     rdx, rbx
0x1800ef280  mov     rcx, [rdi]
0x1800ef283  call    sub_180271E70
0x1800ef288  nop
0x1800ef289  lea     rcx, [r14-1]
0x1800ef28d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800ef291  ja      short loc_1800EF29D
0x1800ef293  mov     rcx, r14; hObject
0x1800ef296  call    cs:CloseHandle
0x1800ef29c  nop
0x1800ef29d  lea     rcx, [rsp+10D0h+var_1070]
0x1800ef2a2  call    sub_18008F654
0x1800ef2a7  mov     rax, rdi
0x1800ef2aa  mov     rcx, [rbp+0FD0h+var_40]
0x1800ef2b1  xor     rcx, rsp; StackCookie
0x1800ef2b4  call    __security_check_cookie
0x1800ef2b9  mov     rbx, [rsp+10D0h+arg_18]
0x1800ef2c1  add     rsp, 10A0h
0x1800ef2c8  pop     r15
0x1800ef2ca  pop     r14
0x1800ef2cc  pop     r13
0x1800ef2ce  pop     r12
0x1800ef2d0  pop     rdi
0x1800ef2d1  pop     rsi
0x1800ef2d2  pop     rbp
0x1800ef2d3  retn
0x1800ef2d4  mov     ecx, 0D0000034h
0x1800ef2d9  call    sub_1800D94B0
0x1800ef2de  mov     r9d, eax
0x1800ef2e1  mov     rcx, [rbp+0FD8h]
0x1800ef2e8  lea     rax, aFailedToFindEa; "Failed to find EA"
0x1800ef2ef  mov     qword ptr [rsp+10D0h+dwCreationDisposition], rax
0x1800ef2f4  lea     r8, aSrcEppDlpEndpo_4; "src\\epp\\Dlp\\EndpointDlp\\WindowsDelp"...
0x1800ef2fb  mov     edx, 0ACh
0x1800ef300  call    sub_1800EF360
```
