# write_text_utf8_nolock

- ea: `0x18003ca5c`
- end: `0x18003cbda`
- name: `write_text_utf8_nolock`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18003cd08`

## callees

- `0x18002cc10`
- `0x18002d2b0`
- `0x18002dee0`
- `0x18003ca5c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003cba3`
- `KERNEL32!GetLastError` at `0x18003cba3`
- `KERNEL32!WriteFile` at `0x18003cb7e`
- `KERNEL32!WriteFile` at `0x18003cb7e`

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
  _BYTE v17[3424]; // [rsp+700h] [rbp-D98h] BYREF

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
    v11 = _acrt_WideCharToMultiByte(65001, 0, (unsigned int)v15, (v9 - v15) >> 1, (unsigned int)v17, 3413, 0, 0);
    if ( v11 )
    {
      v12 = 0;
      while ( 1 )
      {
        NumberOfBytesWritten = 0;
        if ( !WriteFile(v8, &v17[v12], v11 - v12, &NumberOfBytesWritten, 0) )
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
0x18003ca5c  mov     [rsp+arg_0], rbx
0x18003ca61  mov     [rsp+arg_10], rbp
0x18003ca66  push    rsi
0x18003ca67  push    rdi
0x18003ca68  push    r12
0x18003ca6a  push    r14
0x18003ca6c  push    r15
0x18003ca6e  mov     eax, 1470h
0x18003ca73  call    _alloca_probe
0x18003ca78  sub     rsp, rax
0x18003ca7b  mov     rax, cs:__security_cookie
0x18003ca82  xor     rax, rsp
0x18003ca85  mov     [rsp+1498h+var_38], rax
0x18003ca8d  mov     eax, edx
0x18003ca8f  movsxd  r10, edx
0x18003ca92  and     eax, 3Fh
0x18003ca95  sar     r10, 6
0x18003ca99  mov     rbx, rcx
0x18003ca9c  mov     r14d, r9d
0x18003ca9f  lea     rcx, __pioinfo
0x18003caa6  add     r14, r8
0x18003caa9  mov     r15, r8
0x18003caac  mov     rdi, r8
0x18003caaf  lea     rdx, [rax+rax*8]
0x18003cab3  mov     rax, [rcx+r10*8]
0x18003cab7  mov     r12, [rax+rdx*8+28h]
0x18003cabc  xor     eax, eax
0x18003cabe  mov     [rbx], rax
0x18003cac1  mov     [rbx+8], eax
0x18003cac4  cmp     r8, r14
0x18003cac7  jnb     loc_18003CBAB
0x18003cacd  lea     r9, [rsp+1498h+var_1448]
0x18003cad2  cmp     rdi, r14
0x18003cad5  jnb     short loc_18003CB03
0x18003cad7  movzx   eax, word ptr [rdi]
0x18003cada  add     rdi, 2
0x18003cade  cmp     ax, 0Ah
0x18003cae2  jnz     short loc_18003CAEE
0x18003cae4  mov     word ptr [r9], 0Dh
0x18003caea  add     r9, 2
0x18003caee  mov     [r9], ax
0x18003caf2  add     r9, 2
0x18003caf6  lea     rax, [rsp+1498h+var_DA0]
0x18003cafe  cmp     r9, rax
0x18003cb01  jb      short loc_18003CAD2
0x18003cb03  mov     [rsp+1498h+var_1460], 0
0x18003cb0c  lea     rax, [rsp+1498h+var_1448]
0x18003cb11  sub     r9, rax
0x18003cb14  mov     [rsp+1498h+var_1468], 0
0x18003cb1d  lea     rax, [rsp+1498h+var_D98]
0x18003cb25  sar     r9, 1
0x18003cb28  mov     [rsp+1498h+var_1470], 0D55h
0x18003cb30  lea     r8, [rsp+1498h+var_1448]
0x18003cb35  xor     edx, edx
0x18003cb37  mov     [rsp+1498h+lpOverlapped], rax
0x18003cb3c  mov     ecx, 0FDE9h
0x18003cb41  call    __acrt_WideCharToMultiByte
0x18003cb46  mov     ebp, eax
0x18003cb48  test    eax, eax
0x18003cb4a  jz      short loc_18003CBA3
0x18003cb4c  xor     esi, esi
0x18003cb4e  test    eax, eax
0x18003cb50  jz      short loc_18003CB90
0x18003cb52  mov     ecx, esi
0x18003cb54  lea     rdx, [rsp+1498h+var_D98]
0x18003cb5c  mov     r8d, ebp
0x18003cb5f  mov     [rsp+1498h+NumberOfBytesWritten], 0
0x18003cb67  add     rdx, rcx; lpBuffer
0x18003cb6a  mov     [rsp+1498h+lpOverlapped], 0; lpOverlapped
0x18003cb73  mov     rcx, r12; hFile
0x18003cb76  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003cb7b  sub     r8d, esi; nNumberOfBytesToWrite
0x18003cb7e  call    cs:__imp_WriteFile
0x18003cb84  test    eax, eax
0x18003cb86  jz      short loc_18003CBA3
0x18003cb88  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x18003cb8c  cmp     esi, ebp
0x18003cb8e  jb      short loc_18003CB52
0x18003cb90  mov     eax, edi
0x18003cb92  sub     eax, r15d
0x18003cb95  mov     [rbx+4], eax
0x18003cb98  cmp     rdi, r14
0x18003cb9b  jb      loc_18003CACD
0x18003cba1  jmp     short loc_18003CBAB
0x18003cba3  call    cs:__imp_GetLastError
0x18003cba9  mov     [rbx], eax
0x18003cbab  mov     rax, rbx
0x18003cbae  mov     rcx, [rsp+1498h+var_38]
0x18003cbb6  xor     rcx, rsp; StackCookie
0x18003cbb9  call    __security_check_cookie
0x18003cbbe  lea     r11, [rsp+1498h+var_28]
0x18003cbc6  mov     rbx, [r11+30h]
0x18003cbca  mov     rbp, [r11+40h]
0x18003cbce  mov     rsp, r11
0x18003cbd1  pop     r15
0x18003cbd3  pop     r14
0x18003cbd5  pop     r12
0x18003cbd7  pop     rdi
0x18003cbd8  pop     rsi
0x18003cbd9  retn
```
