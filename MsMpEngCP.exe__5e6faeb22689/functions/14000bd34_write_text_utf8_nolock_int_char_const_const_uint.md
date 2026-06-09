# write_text_utf8_nolock(int,char const * const,uint)

- ea: `0x14000bd34`
- end: `0x14000bea8`
- name: `?write_text_utf8_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000bfc8`

## callees

- `0x140001350`
- `0x140007bc4`
- `0x14000bd34`
- `0x14000ce70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000be71`
- `KERNEL32!GetLastError` at `0x14000be71`
- `KERNEL32!WriteFile` at `0x14000be4c`
- `KERNEL32!WriteFile` at `0x14000be4c`

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
  v8 = *(void **)(qword_14001A750[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
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
0x14000bd34  mov     [rsp+arg_0], rbx
0x14000bd39  mov     [rsp+arg_10], rbp
0x14000bd3e  push    rsi
0x14000bd3f  push    rdi
0x14000bd40  push    r12
0x14000bd42  push    r14
0x14000bd44  push    r15
0x14000bd46  mov     eax, 1470h
0x14000bd4b  call    __alloca_probe
0x14000bd50  sub     rsp, rax
0x14000bd53  mov     rax, cs:__security_cookie
0x14000bd5a  xor     rax, rsp
0x14000bd5d  mov     [rsp+1498h+var_38], rax
0x14000bd65  movsxd  r10, edx
0x14000bd68  mov     rbx, rcx
0x14000bd6b  mov     rax, r10
0x14000bd6e  mov     r14d, r9d
0x14000bd71  sar     rax, 6
0x14000bd75  lea     rcx, qword_14001A750
0x14000bd7c  and     r10d, 3Fh
0x14000bd80  add     r14, r8
0x14000bd83  mov     r15, r8
0x14000bd86  mov     rdi, r8
0x14000bd89  mov     rax, [rcx+rax*8]
0x14000bd8d  lea     rdx, [r10+r10*8]
0x14000bd91  mov     r12, [rax+rdx*8+28h]
0x14000bd96  xor     eax, eax
0x14000bd98  mov     [rbx], rax
0x14000bd9b  mov     [rbx+8], eax
0x14000bd9e  cmp     r8, r14
0x14000bda1  jnb     loc_14000BE79
0x14000bda7  lea     r9, [rsp+1498h+var_1448]
0x14000bdac  cmp     rdi, r14
0x14000bdaf  jnb     short loc_14000BDDD
0x14000bdb1  movzx   eax, word ptr [rdi]
0x14000bdb4  add     rdi, 2
0x14000bdb8  cmp     ax, 0Ah
0x14000bdbc  jnz     short loc_14000BDC8
0x14000bdbe  mov     word ptr [r9], 0Dh
0x14000bdc4  add     r9, 2
0x14000bdc8  mov     [r9], ax
0x14000bdcc  add     r9, 2
0x14000bdd0  lea     rax, [rsp+1498h+var_DA0]
0x14000bdd8  cmp     r9, rax
0x14000bddb  jb      short loc_14000BDAC
0x14000bddd  and     [rsp+1498h+var_1460], 0
0x14000bde3  lea     rax, [rsp+1498h+var_1448]
0x14000bde8  and     [rsp+1498h+var_1468], 0
0x14000bdee  lea     r8, [rsp+1498h+var_1448]
0x14000bdf3  sub     r9, rax
0x14000bdf6  mov     [rsp+1498h+var_1470], 0D55h
0x14000bdfe  lea     rax, [rsp+1498h+Overlapped]
0x14000be06  sar     r9, 1
0x14000be09  xor     edx, edx
0x14000be0b  mov     [rsp+1498h+lpOverlapped], rax; lpOverlapped
0x14000be10  mov     ecx, 0FDE9h
0x14000be15  call    __acrt_WideCharToMultiByte
0x14000be1a  mov     ebp, eax
0x14000be1c  test    eax, eax
0x14000be1e  jz      short loc_14000BE71
0x14000be20  xor     esi, esi
0x14000be22  test    eax, eax
0x14000be24  jz      short loc_14000BE5E
0x14000be26  and     [rsp+1498h+NumberOfBytesWritten], 0
0x14000be2b  lea     rdx, [rsp+1498h+Overlapped]
0x14000be33  and     [rsp+1498h+lpOverlapped], 0
0x14000be39  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000be3e  mov     ecx, esi
0x14000be40  mov     r8d, ebp
0x14000be43  add     rdx, rcx; lpBuffer
0x14000be46  sub     r8d, esi; nNumberOfBytesToWrite
0x14000be49  mov     rcx, r12; hFile
0x14000be4c  call    cs:WriteFile
0x14000be52  test    eax, eax
0x14000be54  jz      short loc_14000BE71
0x14000be56  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x14000be5a  cmp     esi, ebp
0x14000be5c  jb      short loc_14000BE26
0x14000be5e  mov     eax, edi
0x14000be60  sub     eax, r15d
0x14000be63  mov     [rbx+4], eax
0x14000be66  cmp     rdi, r14
0x14000be69  jb      loc_14000BDA7
0x14000be6f  jmp     short loc_14000BE79
0x14000be71  call    cs:GetLastError
0x14000be77  mov     [rbx], eax
0x14000be79  mov     rax, rbx
0x14000be7c  mov     rcx, [rsp+1498h+var_38]
0x14000be84  xor     rcx, rsp; StackCookie
0x14000be87  call    __security_check_cookie
0x14000be8c  lea     r11, [rsp+1498h+var_28]
0x14000be94  mov     rbx, [r11+30h]
0x14000be98  mov     rbp, [r11+40h]
0x14000be9c  mov     rsp, r11
0x14000be9f  pop     r15
0x14000bea1  pop     r14
0x14000bea3  pop     r12
0x14000bea5  pop     rdi
0x14000bea6  pop     rsi
0x14000bea7  retn
```
