# write_text_utf8_nolock

- ea: `0x180018704`
- end: `0x180018874`
- name: `write_text_utf8_nolock`
- size: `368`
- prototype: `__int64 __fastcall(__int64, int, WCHAR *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180018960`

## callees

- `0x180007700`
- `0x1800138a4`
- `0x180018704`
- `0x18001aff0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001883d`
- `KERNEL32!GetLastError` at `0x18001883d`
- `KERNEL32!WriteFile` at `0x18001881b`
- `KERNEL32!WriteFile` at `0x18001881b`

## pseudocode

```c
__int64 __fastcall write_text_utf8_nolock(__int64 a1, int a2, WCHAR *a3, unsigned int a4)
{
  unsigned __int64 v5; // r14
  int v6; // r15d
  WCHAR *v7; // rdi
  void *v8; // r12
  bool v9; // cf
  WCHAR *v10; // rax
  WCHAR v11; // cx
  unsigned int v12; // ebp
  unsigned int v13; // esi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-1458h] BYREF
  WCHAR v16[852]; // [rsp+50h] [rbp-1448h] BYREF
  char v17; // [rsp+6F8h] [rbp-DA0h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+700h] [rbp-D98h] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = (int)a3;
  v7 = a3;
  v8 = *(void **)(_pioinfo[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  v9 = (unsigned __int64)a3 < v5;
  *(_DWORD *)(a1 + 8) = 0;
LABEL_2:
  if ( v9 )
  {
    v10 = v16;
    do
    {
      if ( (unsigned __int64)v7 >= v5 )
        break;
      v11 = *v7++;
      if ( v11 == 10 )
        *v10++ = 13;
      *v10++ = v11;
    }
    while ( v10 < (WCHAR *)&v17 );
    v12 = _acrt_WideCharToMultiByte(0xFDE9u, 0, v16, v10 - v16, (CHAR *)&Overlapped, 3413, 0, 0);
    if ( v12 )
    {
      v13 = 0;
      while ( WriteFile(v8, (char *)&Overlapped + v13, v12 - v13, &NumberOfBytesWritten, 0) )
      {
        v13 += NumberOfBytesWritten;
        if ( v13 >= v12 )
        {
          *(_DWORD *)(a1 + 4) = (_DWORD)v7 - v6;
          v9 = (unsigned __int64)v7 < v5;
          goto LABEL_2;
        }
      }
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x180018704  mov     [rsp+arg_0], rbx
0x180018709  mov     [rsp+arg_10], rbp
0x18001870e  push    rsi
0x18001870f  push    rdi
0x180018710  push    r12
0x180018712  push    r14
0x180018714  push    r15
0x180018716  mov     eax, 1470h
0x18001871b  call    _alloca_probe
0x180018720  sub     rsp, rax
0x180018723  mov     rax, cs:__security_cookie
0x18001872a  xor     rax, rsp
0x18001872d  mov     [rsp+1498h+var_38], rax
0x180018735  movsxd  r10, edx
0x180018738  mov     rbx, rcx
0x18001873b  mov     rax, r10
0x18001873e  mov     r14d, r9d
0x180018741  sar     rax, 6
0x180018745  lea     rcx, __pioinfo
0x18001874c  and     r10d, 3Fh
0x180018750  add     r14, r8
0x180018753  mov     r15, r8
0x180018756  mov     rdi, r8
0x180018759  mov     rax, [rcx+rax*8]
0x18001875d  lea     rdx, [r10+r10*8]
0x180018761  mov     r12, [rax+rdx*8+28h]
0x180018766  xor     eax, eax
0x180018768  mov     [rbx], rax
0x18001876b  cmp     r8, r14
0x18001876e  mov     [rbx+8], eax
0x180018771  jnb     loc_180018845
0x180018777  lea     rax, [rsp+1498h+var_1448]
0x18001877c  cmp     rdi, r14
0x18001877f  jnb     short loc_1800187AE
0x180018781  movzx   ecx, word ptr [rdi]
0x180018784  add     rdi, 2
0x180018788  cmp     cx, 0Ah
0x18001878c  jnz     short loc_18001879A
0x18001878e  mov     edx, 0Dh
0x180018793  mov     [rax], dx
0x180018796  add     rax, 2
0x18001879a  mov     [rax], cx
0x18001879d  add     rax, 2
0x1800187a1  lea     rcx, [rsp+1498h+var_DA0]
0x1800187a9  cmp     rax, rcx
0x1800187ac  jb      short loc_18001877C
0x1800187ae  and     [rsp+1498h+var_1460], 0
0x1800187b4  lea     rcx, [rsp+1498h+var_1448]
0x1800187b9  and     [rsp+1498h+var_1468], 0
0x1800187bf  lea     r8, [rsp+1498h+var_1448]
0x1800187c4  sub     rax, rcx
0x1800187c7  mov     [rsp+1498h+var_1470], 0D55h
0x1800187cf  lea     rcx, [rsp+1498h+Overlapped]
0x1800187d7  sar     rax, 1
0x1800187da  mov     [rsp+1498h+lpOverlapped], rcx; lpOverlapped
0x1800187df  mov     r9d, eax
0x1800187e2  mov     ecx, 0FDE9h
0x1800187e7  xor     edx, edx
0x1800187e9  call    __acrt_WideCharToMultiByte
0x1800187ee  mov     ebp, eax
0x1800187f0  test    eax, eax
0x1800187f2  jz      short loc_18001883D
0x1800187f4  xor     esi, esi
0x1800187f6  test    eax, eax
0x1800187f8  jz      short loc_18001882D
0x1800187fa  and     [rsp+1498h+lpOverlapped], 0
0x180018800  lea     rdx, [rsp+1498h+Overlapped]
0x180018808  mov     ecx, esi
0x18001880a  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001880f  mov     r8d, ebp
0x180018812  add     rdx, rcx; lpBuffer
0x180018815  mov     rcx, r12; hFile
0x180018818  sub     r8d, esi; nNumberOfBytesToWrite
0x18001881b  call    cs:__imp_WriteFile
0x180018821  test    eax, eax
0x180018823  jz      short loc_18001883D
0x180018825  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x180018829  cmp     esi, ebp
0x18001882b  jb      short loc_1800187FA
0x18001882d  mov     eax, edi
0x18001882f  sub     eax, r15d
0x180018832  mov     [rbx+4], eax
0x180018835  cmp     rdi, r14
0x180018838  jmp     loc_180018771
0x18001883d  call    cs:__imp_GetLastError
0x180018843  mov     [rbx], eax
0x180018845  mov     rax, rbx
0x180018848  mov     rcx, [rsp+1498h+var_38]
0x180018850  xor     rcx, rsp; StackCookie
0x180018853  call    __security_check_cookie
0x180018858  lea     r11, [rsp+1498h+var_28]
0x180018860  mov     rbx, [r11+30h]
0x180018864  mov     rbp, [r11+40h]
0x180018868  mov     rsp, r11
0x18001886b  pop     r15
0x18001886d  pop     r14
0x18001886f  pop     r12
0x180018871  pop     rdi
0x180018872  pop     rsi
0x180018873  retn
```
