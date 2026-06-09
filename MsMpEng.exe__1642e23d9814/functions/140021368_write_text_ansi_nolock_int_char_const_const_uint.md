# write_text_ansi_nolock(int,char const * const,uint)

- ea: `0x140021368`
- end: `0x14002146f`
- name: `?write_text_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `263`
- prototype: `__int64 __fastcall(__int64, int, char *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1400218b8`

## callees

- `0x14000a640`
- `0x140021368`
- `0x140025090`

## import_xrefs

- `KERNEL32!WriteFile` at `0x140021420`
- `KERNEL32!WriteFile` at `0x140021420`
- `KERNEL32!GetLastError` at `0x14002143c`
- `KERNEL32!GetLastError` at `0x14002143c`

## pseudocode

```c
__int64 __fastcall write_text_ansi_nolock(__int64 a1, int a2, char *a3, int a4)
{
  unsigned __int64 v5; // rbp
  char *v6; // rsi
  void *v7; // r14
  char *v8; // rbx
  char v9; // al
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5119]; // [rsp+40h] [rbp-1428h] BYREF
  char v15; // [rsp+143Fh] [rbp-29h] BYREF

  v5 = (unsigned __int64)&a3[a4];
  v6 = a3;
  v7 = *(void **)(qword_14003E600[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)a3 < v5 )
  {
    while ( 1 )
    {
      v8 = Buffer;
      do
      {
        if ( (unsigned __int64)v6 >= v5 )
          break;
        v9 = *v6++;
        if ( v9 == 10 )
        {
          ++*(_DWORD *)(a1 + 8);
          *v8++ = 13;
        }
        *v8++ = v9;
      }
      while ( v8 < &v15 );
      NumberOfBytesWritten = 0;
      v10 = (_DWORD)v8 - (unsigned int)Buffer;
      if ( !WriteFile(v7, Buffer, v10, &NumberOfBytesWritten, 0) )
        break;
      v11 = NumberOfBytesWritten;
      *(_DWORD *)(a1 + 4) += NumberOfBytesWritten;
      if ( v11 < v10 || (unsigned __int64)v6 >= v5 )
        return a1;
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x140021368  mov     [rsp+arg_0], rbx
0x14002136d  mov     [rsp+arg_10], rbp
0x140021372  push    rsi
0x140021373  push    rdi
0x140021374  push    r14
0x140021376  mov     eax, 1450h
0x14002137b  call    __alloca_probe
0x140021380  sub     rsp, rax
0x140021383  mov     rax, cs:__security_cookie
0x14002138a  xor     rax, rsp
0x14002138d  mov     [rsp+1468h+var_28], rax
0x140021395  movsxd  r10, edx
0x140021398  mov     rdi, rcx
0x14002139b  mov     rax, r10
0x14002139e  mov     ebp, r9d
0x1400213a1  sar     rax, 6
0x1400213a5  lea     rcx, qword_14003E600
0x1400213ac  and     r10d, 3Fh
0x1400213b0  add     rbp, r8
0x1400213b3  mov     rsi, r8
0x1400213b6  mov     rax, [rcx+rax*8]
0x1400213ba  lea     rdx, [r10+r10*8]
0x1400213be  mov     r14, [rax+rdx*8+28h]
0x1400213c3  xor     eax, eax
0x1400213c5  mov     [rdi], rax
0x1400213c8  mov     [rdi+8], eax
0x1400213cb  cmp     r8, rbp
0x1400213ce  jnb     short loc_140021444
0x1400213d0  lea     rbx, [rsp+1468h+Buffer]
0x1400213d5  cmp     rsi, rbp
0x1400213d8  jnb     short loc_1400213FE
0x1400213da  mov     al, [rsi]
0x1400213dc  inc     rsi
0x1400213df  cmp     al, 0Ah
0x1400213e1  jnz     short loc_1400213EC
0x1400213e3  inc     dword ptr [rdi+8]
0x1400213e6  mov     byte ptr [rbx], 0Dh
0x1400213e9  inc     rbx
0x1400213ec  mov     [rbx], al
0x1400213ee  inc     rbx
0x1400213f1  lea     rax, [rsp+1468h+var_29]
0x1400213f9  cmp     rbx, rax
0x1400213fc  jb      short loc_1400213D5
0x1400213fe  and     [rsp+1468h+NumberOfBytesWritten], 0
0x140021403  lea     rax, [rsp+1468h+Buffer]
0x140021408  and     [rsp+1468h+var_1448], 0
0x14002140e  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140021413  sub     ebx, eax
0x140021415  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x14002141a  mov     r8d, ebx; nNumberOfBytesToWrite
0x14002141d  mov     rcx, r14; hFile
0x140021420  call    cs:WriteFile
0x140021426  test    eax, eax
0x140021428  jz      short loc_14002143C
0x14002142a  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x14002142e  add     [rdi+4], eax
0x140021431  cmp     eax, ebx
0x140021433  jb      short loc_140021444
0x140021435  cmp     rsi, rbp
0x140021438  jb      short loc_1400213D0
0x14002143a  jmp     short loc_140021444
0x14002143c  call    cs:GetLastError
0x140021442  mov     [rdi], eax
0x140021444  mov     rax, rdi
0x140021447  mov     rcx, [rsp+1468h+var_28]
0x14002144f  xor     rcx, rsp; StackCookie
0x140021452  call    __security_check_cookie
0x140021457  lea     r11, [rsp+1468h+var_18]
0x14002145f  mov     rbx, [r11+20h]
0x140021463  mov     rbp, [r11+30h]
0x140021467  mov     rsp, r11
0x14002146a  pop     r14
0x14002146c  pop     rdi
0x14002146d  pop     rsi
0x14002146e  retn
```
