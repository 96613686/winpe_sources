# VerifyFileSize(SIP_SUBJECTINFO_ *)

- ea: `0x1800092a0`
- end: `0x180009364`
- name: `?VerifyFileSize@@YAHPEAUSIP_SUBJECTINFO_@@@Z`
- size: `196`
- prototype: `_BOOL8 __fastcall(struct SIP_SUBJECTINFO_ *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800022b0`

## callees

- `0x180007074`
- `0x180007e84`
- `0x1800092a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800092f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800092f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009345`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009345`

## pseudocode

```c
_BOOL8 __fastcall VerifyFileSize(struct SIP_SUBJECTINFO_ *a1)
{
  HANDLE hFile; // rbx
  int v2; // esi
  BOOL v4; // edi
  _QWORD v5[4]; // [rsp+40h] [rbp-19h] BYREF
  int v6; // [rsp+60h] [rbp+7h]
  __int16 v7; // [rsp+64h] [rbp+Bh]
  __int64 v8; // [rsp+68h] [rbp+Fh]
  __int64 v9; // [rsp+70h] [rbp+17h]
  __int64 v10; // [rsp+78h] [rbp+1Fh]
  __int64 v11; // [rsp+80h] [rbp+27h]

  hFile = a1->hFile;
  if ( !hFile || (v2 = 0, hFile == (HANDLE)-1LL) )
  {
    v2 = 1;
    hFile = CreateFileW(a1->pwsFileName, 0x80000000, 1u, 0, 3u, 0x100000u, 0);
    if ( hFile == (HANDLE)-1LL )
      return 0;
  }
  v5[0] = hFile;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  memset(&v5[1], 0, 24);
  v4 = CFBFileFormatCheck::VerifyFileSize((CFBFileFormatCheck *)v5) != 0;
  if ( v2 )
    CloseHandle(hFile);
  CFBFileFormatCheck::~CFBFileFormatCheck((CFBFileFormatCheck *)v5);
  return v4;
}

```

## disassembly

```asm
0x1800092a0  push    rbp
0x1800092a2  push    rbx
0x1800092a3  push    rsi
0x1800092a4  push    rdi
0x1800092a5  push    r14
0x1800092a7  lea     rbp, [rsp-37h]
0x1800092ac  sub     rsp, 90h
0x1800092b3  mov     rbx, [rcx+10h]
0x1800092b7  xor     r14d, r14d
0x1800092ba  test    rbx, rbx
0x1800092bd  jz      short loc_1800092C8
0x1800092bf  mov     esi, r14d
0x1800092c2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800092c6  jnz     short loc_180009303
0x1800092c8  mov     rcx, [rcx+18h]; lpFileName
0x1800092cc  xor     r9d, r9d; lpSecurityAttributes
0x1800092cf  mov     [rsp+0B0h+hTemplateFile], r14; hTemplateFile
0x1800092d4  mov     edx, 80000000h; dwDesiredAccess
0x1800092d9  mov     [rsp+0B0h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x1800092e1  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800092e9  lea     esi, [r9+1]
0x1800092ed  mov     r8d, esi; dwShareMode
0x1800092f0  call    cs:__imp_CreateFileW
0x1800092f6  mov     rbx, rax
0x1800092f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800092fd  jnz     short loc_180009303
0x1800092ff  xor     eax, eax
0x180009301  jmp     short loc_180009356
0x180009303  lea     rcx, [rbp+57h+var_70]; this
0x180009307  mov     [rbp+57h+var_70], rbx
0x18000930b  mov     [rbp+57h+var_58], r14
0x18000930f  mov     [rbp+57h+var_50], r14d
0x180009313  mov     [rbp+57h+var_4C], r14w
0x180009318  mov     [rbp+57h+var_48], r14
0x18000931c  mov     [rbp+57h+var_40], r14
0x180009320  mov     [rbp+57h+var_38], r14
0x180009324  mov     [rbp+57h+var_30], r14
0x180009328  mov     [rbp+57h+var_68], r14
0x18000932c  mov     [rbp+57h+var_60], r14
0x180009330  call    ?VerifyFileSize@CFBFileFormatCheck@@QEAAHXZ; CFBFileFormatCheck::VerifyFileSize(void)
0x180009335  test    eax, eax
0x180009337  mov     edi, r14d
0x18000933a  setnz   dil
0x18000933e  test    esi, esi
0x180009340  jz      short loc_18000934B
0x180009342  mov     rcx, rbx; hObject
0x180009345  call    cs:__imp_CloseHandle
0x18000934b  lea     rcx, [rbp+57h+var_70]; this
0x18000934f  call    ??1CFBFileFormatCheck@@QEAA@XZ; CFBFileFormatCheck::~CFBFileFormatCheck(void)
0x180009354  mov     eax, edi
0x180009356  add     rsp, 90h
0x18000935d  pop     r14
0x18000935f  pop     rdi
0x180009360  pop     rsi
0x180009361  pop     rbx
0x180009362  pop     rbp
0x180009363  retn
```
