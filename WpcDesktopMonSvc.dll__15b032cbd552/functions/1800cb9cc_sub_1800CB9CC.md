# sub_1800CB9CC

- ea: `0x1800cb9cc`
- end: `0x1800cbb1a`
- name: `sub_1800CB9CC`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800cbb20`

## callees

- `0x1800061a0`
- `0x180009090`
- `0x180011758`
- `0x1800adda8`
- `0x1800ae9ac`
- `0x1800c7e84`
- `0x1800c7ef0`
- `0x1800c86b0`
- `0x1800cb9cc`
- `0x1800f9010`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800cba7b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800cba7b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800cba59`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800cba59`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800cba27`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800cba27`

## pseudocode

```c
__int64 __fastcall sub_1800CB9CC(__int64 a1, _QWORD *a2)
{
  const FILETIME *v4; // rax
  const WCHAR *v5; // rcx
  const WCHAR *v6; // rdx
  const WCHAR *v7; // rcx
  _QWORD *v8; // rdx
  FILETIME FileTime2; // [rsp+20h] [rbp-59h] BYREF
  int v11; // [rsp+28h] [rbp-51h]
  __int64 v12; // [rsp+30h] [rbp-49h] BYREF
  __int64 v13; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v14[24]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v15[16]; // [rsp+58h] [rbp-21h] BYREF
  _QWORD *v16; // [rsp+68h] [rbp-11h]
  LPCWSTR lpFileName[3]; // [rsp+70h] [rbp-9h] BYREF
  unsigned __int64 v18; // [rsp+88h] [rbp+Fh]
  LPCWSTR lpExistingFileName[4]; // [rsp+90h] [rbp+17h] BYREF

  v16 = a2;
  sub_1800AE9AC(&FileTime2);
  v12 = 12096000000000LL;
  v4 = (const FILETIME *)sub_1800ADDA8(a1 + 76, v15, &v12);
  if ( CompareFileTime(v4, &FileTime2) < 0 )
  {
    sub_180011758((__int64)lpFileName, a1 + 32);
    sub_180011758((__int64)lpExistingFileName, a1);
    v5 = (const WCHAR *)lpFileName;
    if ( v18 > 7 )
      v5 = lpFileName[0];
    DeleteFileW(v5);
    v6 = (const WCHAR *)lpFileName;
    if ( v18 > 7 )
      v6 = lpFileName[0];
    v7 = (const WCHAR *)lpExistingFileName;
    if ( lpExistingFileName[3] > (LPCWSTR)7 )
      v7 = lpExistingFileName[0];
    MoveFileW(v7, v6);
    *(FILETIME *)(a1 + 76) = FileTime2;
    *(_DWORD *)(a1 + 84) = v11;
    sub_180009090(lpExistingFileName);
    sub_180009090(lpFileName);
  }
  sub_1800C7E84(&v13, a1);
  sub_1800C86B0(v14, 2);
  if ( a2[3] <= 7u )
    v8 = a2;
  else
    v8 = (_QWORD *)*a2;
  (*(void (__fastcall **)(__int64 *, _QWORD *, __int64))(v13 + 8))(&v13, v8, 2LL * a2[2]);
  sub_1800C7EF0(&v13);
  return sub_180009090(a2);
}

```

## disassembly

```asm
0x1800cb9cc  mov     [rsp-8+arg_10], rbx
0x1800cb9d1  push    rbp
0x1800cb9d2  push    rsi
0x1800cb9d3  push    rdi
0x1800cb9d4  lea     rbp, [rsp-47h]
0x1800cb9d9  sub     rsp, 0C0h
0x1800cb9e0  mov     rax, cs:__security_cookie
0x1800cb9e7  xor     rax, rsp
0x1800cb9ea  mov     [rbp+57h+var_20], rax
0x1800cb9ee  mov     rbx, rdx
0x1800cb9f1  mov     rdi, rcx
0x1800cb9f4  mov     [rbp+57h+var_68], rdx
0x1800cb9f8  lea     rcx, [rbp+57h+FileTime2]
0x1800cb9fc  call    sub_1800AE9AC
0x1800cba01  mov     rax, 0B0051C88000h
0x1800cba0b  mov     [rbp+57h+var_A0], rax
0x1800cba0f  lea     r8, [rbp+57h+var_A0]
0x1800cba13  lea     rdx, [rbp+57h+var_78]
0x1800cba17  lea     rcx, [rdi+4Ch]
0x1800cba1b  call    sub_1800ADDA8
0x1800cba20  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x1800cba24  mov     rcx, rax; lpFileTime1
0x1800cba27  call    cs:CompareFileTime
0x1800cba2d  test    eax, eax
0x1800cba2f  jns     short loc_1800CBAA4
0x1800cba31  lea     rdx, [rdi+20h]
0x1800cba35  lea     rcx, [rbp+57h+lpFileName]
0x1800cba39  call    sub_180011758
0x1800cba3e  nop
0x1800cba3f  mov     rdx, rdi
0x1800cba42  lea     rcx, [rbp+57h+lpExistingFileName]
0x1800cba46  call    sub_180011758
0x1800cba4b  lea     rcx, [rbp+57h+lpFileName]
0x1800cba4f  cmp     [rbp+57h+var_48], 7
0x1800cba54  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1800cba59  call    cs:DeleteFileW
0x1800cba5f  lea     rdx, [rbp+57h+lpFileName]
0x1800cba63  cmp     [rbp+57h+var_48], 7
0x1800cba68  cmova   rdx, [rbp+57h+lpFileName]; lpNewFileName
0x1800cba6d  lea     rcx, [rbp+57h+lpExistingFileName]
0x1800cba71  cmp     [rbp+57h+var_28], 7
0x1800cba76  cmova   rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x1800cba7b  call    cs:MoveFileW
0x1800cba81  movsd   xmm0, qword ptr [rbp+57h+FileTime2.dwLowDateTime]
0x1800cba86  movsd   qword ptr [rdi+4Ch], xmm0
0x1800cba8b  mov     eax, [rbp+57h+var_A8]
0x1800cba8e  mov     [rdi+54h], eax
0x1800cba91  lea     rcx, [rbp+57h+lpExistingFileName]
0x1800cba95  call    sub_180009090
0x1800cba9a  nop
0x1800cba9b  lea     rcx, [rbp+57h+lpFileName]
0x1800cba9f  call    sub_180009090
0x1800cbaa4  mov     rdx, rdi
0x1800cbaa7  lea     rcx, [rbp+57h+var_98]
0x1800cbaab  call    sub_1800C7E84
0x1800cbab0  nop
0x1800cbab1  xor     r8d, r8d
0x1800cbab4  lea     edx, [r8+2]
0x1800cbab8  lea     rcx, [rbp+57h+var_90]
0x1800cbabc  call    sub_1800C86B0
0x1800cbac1  mov     r8, [rbx+10h]
0x1800cbac5  cmp     qword ptr [rbx+18h], 7
0x1800cbaca  jbe     short loc_1800CBAD1
0x1800cbacc  mov     rdx, [rbx]
0x1800cbacf  jmp     short loc_1800CBAD4
0x1800cbad1  mov     rdx, rbx
0x1800cbad4  add     r8, r8
0x1800cbad7  mov     rax, [rbp+57h+var_98]
0x1800cbadb  lea     rcx, [rbp+57h+var_98]
0x1800cbadf  mov     rax, [rax+8]
0x1800cbae3  call    j__guard_dispatch_icall
0x1800cbae8  nop
0x1800cbae9  lea     rcx, [rbp+57h+var_98]
0x1800cbaed  call    sub_1800C7EF0
0x1800cbaf2  nop
0x1800cbaf3  mov     rcx, rbx
0x1800cbaf6  call    sub_180009090
0x1800cbafb  mov     rcx, [rbp+57h+var_20]
0x1800cbaff  xor     rcx, rsp; StackCookie
0x1800cbb02  call    __security_check_cookie
0x1800cbb07  mov     rbx, [rsp+0D0h+arg_10]
0x1800cbb0f  add     rsp, 0C0h
0x1800cbb16  pop     rdi
0x1800cbb17  pop     rsi
0x1800cbb18  pop     rbp
0x1800cbb19  retn
```
