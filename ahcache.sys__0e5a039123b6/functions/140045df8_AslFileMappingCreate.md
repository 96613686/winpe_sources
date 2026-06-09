# AslFileMappingCreate

- ea: `0x140045df8`
- end: `0x14004603f`
- name: `AslFileMappingCreate`
- size: `583`
- prototype: `__int64 __fastcall(__int64 *, const WCHAR *, void *)`
- caller_count: `8`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x140026974`
- `0x14002af6c`
- `0x14002f430`
- `0x1400341b0`
- `0x140034418`
- `0x140042ad4`
- `0x140049ec0`
- `0x140059d78`

## callees

- `0x140002f84`
- `0x1400043fd`
- `0x14000440f`
- `0x140004553`
- `0x1400079f0`
- `0x14003e364`
- `0x14003e76c`
- `0x140045df8`
- `0x140046048`
- `0x140046074`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14004602e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004602e`

## string_xrefs

- `0x140045fe6`: `AslFileMappingCreate`
- `0x140046010`: `AslFileMappingCreate`
- `0x140045fed`: `RtlFileMapInitializeByFilePath failed %S [%x]`

## pseudocode

```c
__int64 __fastcall AslFileMappingCreate(__int64 *a1, const WCHAR *a2, void *a3)
{
  __int64 Pool2_0; // rax
  __int64 v7; // rdi
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  void *v10; // rax
  HANDLE *v11; // rsi
  int v12; // eax
  const char *v14; // r9
  __int64 v15; // r8
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rcx
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-50h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-30h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-20h] BYREF
  __int64 v24; // [rsp+60h] [rbp-10h]

  v24 = 0;
  FileInformation = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  if ( !a2 || !*a2 || !a1 )
    return 3221225485LL;
  *a1 = 0;
  RtlInitUnicodeString_0(&DestinationString, a2);
  Pool2_0 = ExAllocatePool2_0(256, 88, 1953517633);
  v7 = Pool2_0;
  if ( !Pool2_0 )
  {
    v9 = -1073741801;
    goto LABEL_12;
  }
  v8 = AslStringDuplicate(Pool2_0, a2);
  v9 = v8;
  if ( v8 < 0 )
  {
    v14 = "AslStringDuplicate failed [%x]";
    v15 = 123;
LABEL_28:
    FileInformationClass[0] = v8;
    AslLogCallPrintf(1, "AslFileMappingCreate", v15, v14, *(_QWORD *)FileInformationClass);
LABEL_16:
    AslFileMappingDelete((PVOID *)v7);
    goto LABEL_12;
  }
  v10 = 0;
  if ( a3 != (void *)-1LL )
    v10 = a3;
  v11 = (HANDLE *)(v7 + 8);
  if ( v10 )
  {
    *(_OWORD *)v11 = 0;
    *(_OWORD *)(v7 + 24) = 0;
    *(_OWORD *)(v7 + 40) = 0;
    *(_QWORD *)(v7 + 56) = 0;
    *v11 = v10;
  }
  else
  {
    v12 = RtlFileMapInitializeByNtPath(v7 + 8, &DestinationString);
    v9 = v12;
    if ( v12 < 0 )
    {
      if ( !(unsigned int)AslFileNotFound((unsigned int)v12) )
      {
        v16 = v9 + 1073741805;
        if ( (unsigned int)v16 <= 0x30 && (v17 = 0x1000000008001LL, _bittest64(&v17, v16)) || v9 == -1073741638 )
        {
          v18 = 163;
          v19 = 3;
        }
        else
        {
          v18 = 161;
          v19 = 1;
        }
        AslLogCallPrintf(v19, "AslFileMappingCreate", v18, "RtlFileMapInitializeByFilePath failed %S [%x]", a2, v9);
      }
      goto LABEL_16;
    }
  }
  v24 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v8 = ZwQueryInformationFile_0(*v11, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
  v9 = v8;
  if ( v8 < 0 )
  {
    v14 = "NtQueryInformationFile failed [%x]";
    v15 = 183;
    goto LABEL_28;
  }
  v9 = 0;
  *(_QWORD *)(v7 + 24) = *((_QWORD *)&FileInformation + 1);
  *(_DWORD *)(v7 + 64) = (*((_QWORD *)&FileInformation + 1) != 0) + 1;
  *a1 = v7;
LABEL_12:
  if ( DestinationString.Buffer != a2 )
    RtlFreeUnicodeString(&DestinationString);
  return v9;
}

```

## disassembly

```asm
0x140045df8  mov     [rsp-28h+arg_10], rbx
0x140045dfd  mov     [rsp-28h+arg_18], rsi
0x140045e02  push    rbp
0x140045e03  push    rdi
0x140045e04  push    r12
0x140045e06  push    r14
0x140045e08  push    r15
0x140045e0a  mov     rbp, rsp
0x140045e0d  sub     rsp, 70h
0x140045e11  mov     rax, cs:__security_cookie
0x140045e18  xor     rax, rsp
0x140045e1b  mov     [rbp+var_8], rax
0x140045e1f  xor     eax, eax
0x140045e21  xorps   xmm0, xmm0
0x140045e24  xor     r12d, r12d
0x140045e27  mov     [rbp+var_10], rax
0x140045e2b  xorps   xmm1, xmm1
0x140045e2e  mov     rsi, r8
0x140045e31  mov     r14, rdx
0x140045e34  mov     r15, rcx
0x140045e37  movups  [rbp+FileInformation], xmm0
0x140045e3b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140045e3f  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x140045e43  test    rdx, rdx
0x140045e46  jz      loc_140045F6E
0x140045e4c  cmp     [rdx], r12w
0x140045e50  jz      loc_140045F6E
0x140045e56  test    rcx, rcx
0x140045e59  jz      loc_140045F6E
0x140045e5f  mov     [rcx], r12
0x140045e62  lea     rcx, [rbp+DestinationString]; DestinationString
0x140045e66  call    RtlInitUnicodeString_0
0x140045e6b  lea     edx, [r12+58h]
0x140045e70  mov     ecx, 100h
0x140045e75  mov     r8d, 74705041h
0x140045e7b  call    ExAllocatePool2_0
0x140045e80  mov     rdi, rax
0x140045e83  test    rax, rax
0x140045e86  jz      loc_140045F91
0x140045e8c  mov     rdx, r14
0x140045e8f  mov     rcx, rax
0x140045e92  call    AslStringDuplicate
0x140045e97  mov     ebx, eax
0x140045e99  test    eax, eax
0x140045e9b  js      loc_140045F98
0x140045ea1  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140045ea5  mov     eax, r12d
0x140045ea8  cmovnz  rax, rsi
0x140045eac  lea     rsi, [rdi+8]
0x140045eb0  test    rax, rax
0x140045eb3  jnz     loc_140045F75
0x140045eb9  lea     rdx, [rbp+DestinationString]
0x140045ebd  mov     rcx, rsi
0x140045ec0  call    RtlFileMapInitializeByNtPath
0x140045ec5  mov     ebx, eax
0x140045ec7  test    eax, eax
0x140045ec9  js      loc_140045F59
0x140045ecf  xor     eax, eax
0x140045ed1  mov     [rsp+70h+FileInformationClass], 5; FileInformationClass
0x140045ed9  xorps   xmm0, xmm0
0x140045edc  mov     [rbp+var_10], rax
0x140045ee0  xorps   xmm1, xmm1
0x140045ee3  lea     r8, [rbp+FileInformation]; FileInformation
0x140045ee7  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x140045eeb  lea     r9d, [rax+18h]; Length
0x140045eef  movups  [rbp+FileInformation], xmm1
0x140045ef3  mov     rcx, [rsi]; FileHandle
0x140045ef6  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x140045efa  call    ZwQueryInformationFile_0
0x140045eff  mov     ebx, eax
0x140045f01  test    eax, eax
0x140045f03  js      loc_140046003
0x140045f09  mov     rax, qword ptr [rbp+FileInformation+8]
0x140045f0d  mov     ebx, r12d
0x140045f10  mov     [rdi+18h], rax
0x140045f14  mov     rax, qword ptr [rbp+FileInformation+8]
0x140045f18  neg     rax
0x140045f1b  sbb     ecx, ecx
0x140045f1d  neg     ecx
0x140045f1f  inc     ecx
0x140045f21  mov     [rdi+40h], ecx
0x140045f24  mov     [r15], rdi
0x140045f27  cmp     [rbp+DestinationString.Buffer], r14
0x140045f2b  jnz     loc_14004602A
0x140045f31  mov     eax, ebx
0x140045f33  mov     rcx, [rbp+var_8]
0x140045f37  xor     rcx, rsp; StackCookie
0x140045f3a  call    __security_check_cookie
0x140045f3f  lea     r11, [rsp+70h+var_s0]
0x140045f44  mov     rbx, [r11+40h]
0x140045f48  mov     rsi, [r11+48h]
0x140045f4c  mov     rsp, r11
0x140045f4f  pop     r15
0x140045f51  pop     r14
0x140045f53  pop     r12
0x140045f55  pop     rdi
0x140045f56  pop     rbp
0x140045f57  retn
0x140045f59  mov     ecx, ebx
0x140045f5b  call    AslFileNotFound
0x140045f60  test    eax, eax
0x140045f62  jz      short loc_140045FA7
0x140045f64  mov     rcx, rdi; P
0x140045f67  call    AslFileMappingDelete
0x140045f6c  jmp     short loc_140045F27
0x140045f6e  mov     eax, 0C000000Dh
0x140045f73  jmp     short loc_140045F33
0x140045f75  xorps   xmm0, xmm0
0x140045f78  xor     ecx, ecx
0x140045f7a  movups  xmmword ptr [rsi], xmm0
0x140045f7d  movups  xmmword ptr [rsi+10h], xmm0
0x140045f81  movups  xmmword ptr [rsi+20h], xmm0
0x140045f85  mov     [rsi+30h], rcx
0x140045f89  mov     [rsi], rax
0x140045f8c  jmp     loc_140045ECF
0x140045f91  mov     ebx, 0C0000017h
0x140045f96  jmp     short loc_140045F27
0x140045f98  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x140045f9f  mov     r8d, 7Bh ; '{'
0x140045fa5  jmp     short loc_140046010
0x140045fa7  lea     eax, [rbx+3FFFFFEDh]
0x140045fad  cmp     eax, 30h ; '0'
0x140045fb0  ja      short loc_140045FC2
0x140045fb2  mov     rcx, 1000000008001h
0x140045fbc  bt      rcx, rax
0x140045fc0  jb      short loc_140045FD7
0x140045fc2  cmp     ebx, 0C00000BAh
0x140045fc8  jz      short loc_140045FD7
0x140045fca  mov     r8d, 0A1h
0x140045fd0  mov     ecx, 1
0x140045fd5  jmp     short loc_140045FE2
0x140045fd7  mov     r8d, 0A3h
0x140045fdd  mov     ecx, 3
0x140045fe2  mov     [rsp+70h+var_48], ebx
0x140045fe6  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x140045fed  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x140045ff4  mov     qword ptr [rsp+70h+FileInformationClass], r14
0x140045ff9  call    AslLogCallPrintf
0x140045ffe  jmp     loc_140045F64
0x140046003  lea     r9, aNtqueryinforma_0; "NtQueryInformationFile failed [%x]"
0x14004600a  mov     r8d, 0B7h
0x140046010  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x140046017  mov     [rsp+70h+FileInformationClass], eax
0x14004601b  mov     ecx, 1
0x140046020  call    AslLogCallPrintf
0x140046025  jmp     loc_140045F64
0x14004602a  lea     rcx, [rbp+DestinationString]; UnicodeString
0x14004602e  call    cs:__imp_RtlFreeUnicodeString
0x140046035  nop     dword ptr [rax+rax+00h]
0x14004603a  jmp     loc_140045F31
```
