# write_text_utf8_nolock

- ea: `0x180015a08`
- end: `0x180015b7c`
- name: `write_text_utf8_nolock`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180015d70`

## callees

- `0x180002810`
- `0x18000b794`
- `0x180015a08`
- `0x180032a50`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180015b20`
- `KERNEL32!WriteFile` at `0x180015b20`
- `KERNEL32!GetLastError` at `0x180015b45`
- `KERNEL32!GetLastError` at `0x180015b45`

## pseudocode

```c
__int64 __fastcall write_text_utf8_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // r14
  int v6; // r15d
  __int16 *v7; // rdi
  void *v8; // r12
  char *v9; // r9
  __int16 v10; // ax
  unsigned int v11; // ebp
  unsigned int v12; // esi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-1458h] BYREF
  _BYTE v15[1704]; // [rsp+50h] [rbp-1448h] BYREF
  char v16; // [rsp+6F8h] [rbp-DA0h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+700h] [rbp-D98h] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = (int)a3;
  v7 = a3;
  v8 = *(void **)(_pioinfo[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)a3 < v5 )
  {
LABEL_2:
    v9 = v15;
    do
    {
      if ( (unsigned __int64)v7 >= v5 )
        break;
      v10 = *v7++;
      if ( v10 == 10 )
      {
        *(_WORD *)v9 = 13;
        v9 += 2;
      }
      *(_WORD *)v9 = v10;
      v9 += 2;
    }
    while ( v9 < &v16 );
    v11 = _acrt_WideCharToMultiByte(65001, 0, (unsigned int)v15, (v9 - v15) >> 1, (unsigned int)&Overlapped, 3413, 0, 0);
    if ( v11 )
    {
      v12 = 0;
      while ( 1 )
      {
        NumberOfBytesWritten = 0;
        if ( !WriteFile(v8, (char *)&Overlapped + v12, v11 - v12, &NumberOfBytesWritten, 0) )
          break;
        v12 += NumberOfBytesWritten;
        if ( v12 >= v11 )
        {
          *(_DWORD *)(a1 + 4) = (_DWORD)v7 - v6;
          if ( (unsigned __int64)v7 < v5 )
            goto LABEL_2;
          return a1;
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
0x180015a08  mov     [rsp+arg_0], rbx
0x180015a0d  mov     [rsp+arg_10], rbp
0x180015a12  push    rsi
0x180015a13  push    rdi
0x180015a14  push    r12
0x180015a16  push    r14
0x180015a18  push    r15
0x180015a1a  mov     eax, 1470h
0x180015a1f  call    _alloca_probe
0x180015a24  sub     rsp, rax
0x180015a27  mov     rax, cs:__security_cookie
0x180015a2e  xor     rax, rsp
0x180015a31  mov     [rsp+1498h+var_38], rax
0x180015a39  movsxd  r10, edx
0x180015a3c  mov     rbx, rcx
0x180015a3f  mov     rax, r10
0x180015a42  mov     r14d, r9d
0x180015a45  sar     rax, 6
0x180015a49  lea     rcx, __pioinfo
0x180015a50  and     r10d, 3Fh
0x180015a54  add     r14, r8
0x180015a57  mov     r15, r8
0x180015a5a  mov     rdi, r8
0x180015a5d  mov     rax, [rcx+rax*8]
0x180015a61  lea     rdx, [r10+r10*8]
0x180015a65  mov     r12, [rax+rdx*8+28h]
0x180015a6a  xor     eax, eax
0x180015a6c  mov     [rbx], rax
0x180015a6f  mov     [rbx+8], eax
0x180015a72  cmp     r8, r14
0x180015a75  jnb     loc_180015B4D
0x180015a7b  lea     r9, [rsp+1498h+var_1448]
0x180015a80  cmp     rdi, r14
0x180015a83  jnb     short loc_180015AB1
0x180015a85  movzx   eax, word ptr [rdi]
0x180015a88  add     rdi, 2
0x180015a8c  cmp     ax, 0Ah
0x180015a90  jnz     short loc_180015A9C
0x180015a92  mov     word ptr [r9], 0Dh
0x180015a98  add     r9, 2
0x180015a9c  mov     [r9], ax
0x180015aa0  add     r9, 2
0x180015aa4  lea     rax, [rsp+1498h+var_DA0]
0x180015aac  cmp     r9, rax
0x180015aaf  jb      short loc_180015A80
0x180015ab1  and     [rsp+1498h+var_1460], 0
0x180015ab7  lea     rax, [rsp+1498h+var_1448]
0x180015abc  and     [rsp+1498h+var_1468], 0
0x180015ac2  lea     r8, [rsp+1498h+var_1448]
0x180015ac7  sub     r9, rax
0x180015aca  mov     [rsp+1498h+var_1470], 0D55h
0x180015ad2  lea     rax, [rsp+1498h+Overlapped]
0x180015ada  sar     r9, 1
0x180015add  xor     edx, edx
0x180015adf  mov     [rsp+1498h+lpOverlapped], rax; lpOverlapped
0x180015ae4  mov     ecx, 0FDE9h
0x180015ae9  call    __acrt_WideCharToMultiByte
0x180015aee  mov     ebp, eax
0x180015af0  test    eax, eax
0x180015af2  jz      short loc_180015B45
0x180015af4  xor     esi, esi
0x180015af6  test    eax, eax
0x180015af8  jz      short loc_180015B32
0x180015afa  and     [rsp+1498h+NumberOfBytesWritten], 0
0x180015aff  lea     rdx, [rsp+1498h+Overlapped]
0x180015b07  and     [rsp+1498h+lpOverlapped], 0
0x180015b0d  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180015b12  mov     ecx, esi
0x180015b14  mov     r8d, ebp
0x180015b17  add     rdx, rcx; lpBuffer
0x180015b1a  sub     r8d, esi; nNumberOfBytesToWrite
0x180015b1d  mov     rcx, r12; hFile
0x180015b20  call    cs:__imp_WriteFile
0x180015b26  test    eax, eax
0x180015b28  jz      short loc_180015B45
0x180015b2a  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x180015b2e  cmp     esi, ebp
0x180015b30  jb      short loc_180015AFA
0x180015b32  mov     eax, edi
0x180015b34  sub     eax, r15d
0x180015b37  mov     [rbx+4], eax
0x180015b3a  cmp     rdi, r14
0x180015b3d  jb      loc_180015A7B
0x180015b43  jmp     short loc_180015B4D
0x180015b45  call    cs:__imp_GetLastError
0x180015b4b  mov     [rbx], eax
0x180015b4d  mov     rax, rbx
0x180015b50  mov     rcx, [rsp+1498h+var_38]
0x180015b58  xor     rcx, rsp; StackCookie
0x180015b5b  call    __security_check_cookie
0x180015b60  lea     r11, [rsp+1498h+var_28]
0x180015b68  mov     rbx, [r11+30h]
0x180015b6c  mov     rbp, [r11+40h]
0x180015b70  mov     rsp, r11
0x180015b73  pop     r15
0x180015b75  pop     r14
0x180015b77  pop     r12
0x180015b79  pop     rdi
0x180015b7a  pop     rsi
0x180015b7b  retn
```
