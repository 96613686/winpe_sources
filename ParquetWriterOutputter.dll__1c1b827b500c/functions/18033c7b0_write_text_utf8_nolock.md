# write_text_utf8_nolock

- ea: `0x18033c7b0`
- end: `0x18033c922`
- name: `write_text_utf8_nolock`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18033ca10`

## callees

- `0x18030c3f0`
- `0x18030cf60`
- `0x18033c7b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18033c8eb`
- `KERNEL32!GetLastError` at `0x18033c8eb`
- `KERNEL32!WideCharToMultiByte` at `0x18033c896`
- `KERNEL32!WideCharToMultiByte` at `0x18033c896`
- `KERNEL32!WriteFile` at `0x18033c8c9`
- `KERNEL32!WriteFile` at `0x18033c8c9`

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
  WCHAR WideCharStr[852]; // [rsp+50h] [rbp-1448h] BYREF
  char v17; // [rsp+6F8h] [rbp-DA0h] BYREF
  CHAR MultiByteStr[3424]; // [rsp+700h] [rbp-D98h] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = (int)a3;
  v7 = a3;
  v8 = *(void **)(_pioinfo[(__int64)a2 >> 6] + ((unsigned __int64)(a2 & 0x3F) << 6) + 40);
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 4) = 0;
  v9 = (unsigned __int64)a3 < v5;
LABEL_2:
  if ( v9 )
  {
    v10 = WideCharStr;
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
    v12 = WideCharToMultiByte(0xFDE9u, 0, WideCharStr, v10 - WideCharStr, MultiByteStr, 3413, 0, 0);
    if ( v12 )
    {
      v13 = 0;
      while ( WriteFile(v8, &MultiByteStr[v13], v12 - v13, &NumberOfBytesWritten, 0) )
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
0x18033c7b0  mov     [rsp+arg_0], rbx
0x18033c7b5  mov     [rsp+arg_10], rbp
0x18033c7ba  push    rsi
0x18033c7bb  push    rdi
0x18033c7bc  push    r12
0x18033c7be  push    r14
0x18033c7c0  push    r15
0x18033c7c2  mov     eax, 1470h
0x18033c7c7  call    _alloca_probe
0x18033c7cc  sub     rsp, rax
0x18033c7cf  mov     rax, cs:__security_cookie
0x18033c7d6  xor     rax, rsp
0x18033c7d9  mov     [rsp+1498h+var_38], rax
0x18033c7e1  movsxd  r10, edx
0x18033c7e4  mov     rbx, rcx
0x18033c7e7  mov     rax, r10
0x18033c7ea  mov     r14d, r9d
0x18033c7ed  sar     rax, 6
0x18033c7f1  lea     rcx, __pioinfo
0x18033c7f8  and     r10d, 3Fh
0x18033c7fc  add     r14, r8
0x18033c7ff  shl     r10, 6
0x18033c803  mov     r15, r8
0x18033c806  mov     rdi, r8
0x18033c809  mov     rax, [rcx+rax*8]
0x18033c80d  mov     r12, [rax+r10+28h]
0x18033c812  xor     eax, eax
0x18033c814  and     dword ptr [rbx], 0
0x18033c817  mov     [rbx+4], rax
0x18033c81b  cmp     r8, r14
0x18033c81e  jnb     loc_18033C8F3
0x18033c824  lea     rax, [rsp+1498h+WideCharStr]
0x18033c829  cmp     rdi, r14
0x18033c82c  jnb     short loc_18033C85B
0x18033c82e  movzx   ecx, word ptr [rdi]
0x18033c831  add     rdi, 2
0x18033c835  cmp     cx, 0Ah
0x18033c839  jnz     short loc_18033C847
0x18033c83b  mov     edx, 0Dh
0x18033c840  mov     [rax], dx
0x18033c843  add     rax, 2
0x18033c847  mov     [rax], cx
0x18033c84a  add     rax, 2
0x18033c84e  lea     rcx, [rsp+1498h+var_DA0]
0x18033c856  cmp     rax, rcx
0x18033c859  jb      short loc_18033C829
0x18033c85b  and     [rsp+1498h+var_1460], 0
0x18033c861  lea     rcx, [rsp+1498h+WideCharStr]
0x18033c866  and     [rsp+1498h+var_1468], 0
0x18033c86c  lea     r8, [rsp+1498h+WideCharStr]; lpWideCharStr
0x18033c871  sub     rax, rcx
0x18033c874  mov     [rsp+1498h+cbMultiByte], 0D55h; cbMultiByte
0x18033c87c  lea     rcx, [rsp+1498h+MultiByteStr]
0x18033c884  sar     rax, 1
0x18033c887  mov     [rsp+1498h+lpMultiByteStr], rcx; lpOverlapped
0x18033c88c  mov     r9d, eax; cchWideChar
0x18033c88f  mov     ecx, 0FDE9h; CodePage
0x18033c894  xor     edx, edx; dwFlags
0x18033c896  call    cs:__imp_WideCharToMultiByte
0x18033c89c  mov     ebp, eax
0x18033c89e  test    eax, eax
0x18033c8a0  jz      short loc_18033C8EB
0x18033c8a2  xor     esi, esi
0x18033c8a4  test    eax, eax
0x18033c8a6  jz      short loc_18033C8DB
0x18033c8a8  and     [rsp+1498h+lpMultiByteStr], 0
0x18033c8ae  lea     rdx, [rsp+1498h+MultiByteStr]
0x18033c8b6  mov     ecx, esi
0x18033c8b8  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18033c8bd  mov     r8d, ebp
0x18033c8c0  add     rdx, rcx; lpBuffer
0x18033c8c3  mov     rcx, r12; hFile
0x18033c8c6  sub     r8d, esi; nNumberOfBytesToWrite
0x18033c8c9  call    cs:__imp_WriteFile
0x18033c8cf  test    eax, eax
0x18033c8d1  jz      short loc_18033C8EB
0x18033c8d3  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x18033c8d7  cmp     esi, ebp
0x18033c8d9  jb      short loc_18033C8A8
0x18033c8db  mov     eax, edi
0x18033c8dd  sub     eax, r15d
0x18033c8e0  mov     [rbx+4], eax
0x18033c8e3  cmp     rdi, r14
0x18033c8e6  jmp     loc_18033C81E
0x18033c8eb  call    cs:__imp_GetLastError
0x18033c8f1  mov     [rbx], eax
0x18033c8f3  mov     rax, rbx
0x18033c8f6  mov     rcx, [rsp+1498h+var_38]
0x18033c8fe  xor     rcx, rsp; StackCookie
0x18033c901  call    __security_check_cookie
0x18033c906  lea     r11, [rsp+1498h+var_28]
0x18033c90e  mov     rbx, [r11+30h]
0x18033c912  mov     rbp, [r11+40h]
0x18033c916  mov     rsp, r11
0x18033c919  pop     r15
0x18033c91b  pop     r14
0x18033c91d  pop     r12
0x18033c91f  pop     rdi
0x18033c920  pop     rsi
0x18033c921  retn
```
