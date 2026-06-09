# sub_1800ADCB4

- ea: `0x1800adcb4`
- end: `0x1800adda2`
- name: `sub_1800ADCB4`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800d7fe0`

## callees

- `0x1800106b8`
- `0x1800ad6a4`
- `0x1800adcb4`
- `0x1800f4270`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800add4e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800add4e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800add3c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800add3c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800add03`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800add03`

## pseudocode

```c
bool __fastcall sub_1800ADCB4(_QWORD *a1, __int64 a2)
{
  bool v3; // bl
  const WCHAR *v4; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v6; // rcx
  BOOL v7; // eax
  __int128 v9; // [rsp+20h] [rbp-40h]
  LPCWSTR lpFileName[3]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v11; // [rsp+48h] [rbp-18h]

  *(_QWORD *)(a2 + 8) = &off_180218888;
  v3 = 0;
  *(_DWORD *)a2 = 0;
  sub_1800AD6A4((__int64)lpFileName, a1, a2);
  v4 = (const WCHAR *)lpFileName;
  if ( v11 > 7 )
    v4 = lpFileName[0];
  FileAttributesW = GetFileAttributesW(v4);
  if ( FileAttributesW == -1 )
  {
    LODWORD(v9) = 2;
    *((_QWORD *)&v9 + 1) = &off_18018C1A0;
    *(_OWORD *)a2 = v9;
  }
  else
  {
    v6 = (const WCHAR *)lpFileName;
    if ( (FileAttributesW & 0x10) != 0 )
    {
      if ( v11 > 7 )
        v6 = lpFileName[0];
      v7 = RemoveDirectoryW(v6);
    }
    else
    {
      if ( v11 > 7 )
        v6 = lpFileName[0];
      v7 = DeleteFileW(v6);
    }
    if ( !v7 )
    {
      LODWORD(v9) = 1;
      *((_QWORD *)&v9 + 1) = &off_18018C1A0;
      *(_OWORD *)a2 = v9;
    }
    v3 = v7;
  }
  sub_1800106B8(lpFileName);
  return v3;
}

```

## disassembly

```asm
0x1800adcb4  mov     [rsp-8+arg_10], rbx
0x1800adcb9  mov     [rsp-8+arg_18], rdi
0x1800adcbe  push    rbp
0x1800adcbf  mov     rbp, rsp
0x1800adcc2  sub     rsp, 60h
0x1800adcc6  mov     rax, cs:__security_cookie
0x1800adccd  xor     rax, rsp
0x1800adcd0  mov     [rbp+var_10], rax
0x1800adcd4  lea     rax, off_180218888
0x1800adcdb  mov     rdi, rdx
0x1800adcde  mov     [rdx+8], rax
0x1800adce2  mov     r8, rdx
0x1800adce5  xor     ebx, ebx
0x1800adce7  mov     [rdx], ebx
0x1800adce9  mov     rdx, rcx
0x1800adcec  lea     rcx, [rbp+lpFileName]
0x1800adcf0  call    sub_1800AD6A4
0x1800adcf5  cmp     [rbp+var_18], 7
0x1800adcfa  lea     rcx, [rbp+lpFileName]
0x1800adcfe  cmova   rcx, [rbp+lpFileName]; lpFileName
0x1800add03  call    cs:GetFileAttributesW
0x1800add09  cmp     eax, 0FFFFFFFFh
0x1800add0c  jnz     short loc_1800ADD2A
0x1800add0e  lea     rax, off_18018C1A0
0x1800add15  mov     dword ptr [rbp+var_40], 2
0x1800add1c  mov     qword ptr [rbp+var_40+8], rax
0x1800add20  movups  xmm0, [rbp+var_40]
0x1800add24  movdqu  xmmword ptr [rdi], xmm0
0x1800add28  jmp     short loc_1800ADD79
0x1800add2a  lea     rcx, [rbp+lpFileName]
0x1800add2e  test    al, 10h
0x1800add30  jz      short loc_1800ADD44
0x1800add32  cmp     [rbp+var_18], 7
0x1800add37  cmova   rcx, [rbp+lpFileName]; lpPathName
0x1800add3c  call    cs:RemoveDirectoryW
0x1800add42  jmp     short loc_1800ADD54
0x1800add44  cmp     [rbp+var_18], 7
0x1800add49  cmova   rcx, [rbp+lpFileName]; lpFileName
0x1800add4e  call    cs:DeleteFileW
0x1800add54  test    eax, eax
0x1800add56  setnz   cl
0x1800add59  test    cl, cl
0x1800add5b  jnz     short loc_1800ADD77
0x1800add5d  lea     rax, off_18018C1A0
0x1800add64  mov     dword ptr [rbp+var_40], 1
0x1800add6b  mov     qword ptr [rbp+var_40+8], rax
0x1800add6f  movups  xmm0, [rbp+var_40]
0x1800add73  movdqu  xmmword ptr [rdi], xmm0
0x1800add77  mov     bl, cl
0x1800add79  lea     rcx, [rbp+lpFileName]
0x1800add7d  call    sub_1800106B8
0x1800add82  mov     al, bl
0x1800add84  mov     rcx, [rbp+var_10]
0x1800add88  xor     rcx, rsp; StackCookie
0x1800add8b  call    __security_check_cookie
0x1800add90  lea     r11, [rsp+60h+var_s0]
0x1800add95  mov     rbx, [r11+20h]
0x1800add99  mov     rdi, [r11+28h]
0x1800add9d  mov     rsp, r11
0x1800adda0  pop     rbp
0x1800adda1  retn
```
