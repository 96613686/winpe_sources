# ConvertUnicodeStringInPlace(ushort const *)

- ea: `0x1800279f0`
- end: `0x180027b69`
- name: `?ConvertUnicodeStringInPlace@@YAHPEBG@Z`
- size: `377`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `26`
- callee_count: `5`
- tags: ``

## callers

- `0x18000bf50`
- `0x18000c530`
- `0x18000c9a0`
- `0x18000ceb0`
- `0x18000d560`
- `0x18000d900`
- `0x18000e040`
- `0x18000e400`
- `0x18000eb50`
- `0x18000f540`
- `0x18000fd80`
- `0x1800154f0`
- `0x180018064`
- `0x18001c640`
- `0x18001c8a0`
- `0x18001d160`
- `0x18001d460`
- `0x18001db40`
- `0x18001e330`
- `0x180021910`
- `0x180021a20`
- `0x180022470`
- `0x180022a20`
- `0x180023200`
- `0x180023300`
- `0x180027c20`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x1800279f0`
- `0x18002bb58`
- `0x18002c890`

## import_xrefs

- `msvcrt!_mbstrlen` at `0x180027a6f`
- `msvcrt!_mbstrlen` at `0x180027a6f`
- `KERNEL32!SetLastError` at `0x180027a90`
- `KERNEL32!SetLastError` at `0x180027a90`

## pseudocode

```c
__int64 __fastcall ConvertUnicodeStringInPlace(WCHAR *lpWideCharStr)
{
  CHAR *v3; // rax
  CHAR *v4; // rbp
  __int64 v5; // rdi
  unsigned __int64 v6; // rdi
  DWORD v7; // ecx
  signed int v8; // ebx
  __int64 v9; // rax
  CHAR *v10; // rcx
  WCHAR *v11; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a4158162aa603b3b4cac811f54679e94_Traceguids);
  }
  if ( !lpWideCharStr )
    return 1;
  v3 = UnicodeStringToAnsiString(lpWideCharStr);
  v4 = v3;
  if ( v3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( lpWideCharStr[v5] );
    v6 = 2 * v5 + 2;
    if ( v6 >= _mbstrlen(v3) + 1 )
    {
      if ( v6 )
      {
        if ( v6 <= 0x7FFFFFFF )
        {
          v9 = 2147483646;
          v10 = v4;
          do
          {
            if ( !v9 )
              break;
            if ( !*v10 )
              break;
            *(_BYTE *)lpWideCharStr = *v10++;
            lpWideCharStr = (WCHAR *)((char *)lpWideCharStr + 1);
            --v9;
            --v6;
          }
          while ( v6 );
          v11 = (WCHAR *)((char *)lpWideCharStr - 1);
          if ( v6 )
            v11 = lpWideCharStr;
          v8 = v6 == 0 ? 0x8007007A : 0;
          *(_BYTE *)v11 = 0;
        }
        else
        {
          v8 = -2147024809;
          *(_BYTE *)lpWideCharStr = 0;
        }
      }
      else
      {
        v8 = -2147024809;
      }
      pMemFree(v4);
      if ( v8 >= 0 )
        return 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_a4158162aa603b3b4cac811f54679e94_Traceguids,
          (unsigned int)v8);
      }
      v7 = (unsigned __int16)v8;
      if ( (v8 & 0x1FFF0000) != 0x70000 )
        v7 = v8;
    }
    else
    {
      pMemFree(v4);
      v7 = 87;
    }
    SetLastError(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x1800279f0  push    rbx
0x1800279f2  push    rbp
0x1800279f3  push    rsi
0x1800279f4  push    rdi
0x1800279f5  push    r12
0x1800279f7  push    r14
0x1800279f9  sub     rsp, 28h
0x1800279fd  mov     rsi, rcx
0x180027a00  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a07  lea     r12, WPP_GLOBAL_Control
0x180027a0e  cmp     rcx, r12
0x180027a11  jz      short loc_180027A37
0x180027a13  test    dword ptr [rcx+1Ch], 1000h
0x180027a1a  jz      short loc_180027A37
0x180027a1c  cmp     byte ptr [rcx+19h], 5
0x180027a20  jb      short loc_180027A37
0x180027a22  mov     rcx, [rcx+10h]
0x180027a26  lea     r8, WPP_a4158162aa603b3b4cac811f54679e94_Traceguids
0x180027a2d  mov     edx, 0Ah
0x180027a32  call    WPP_SF_
0x180027a37  xor     r14d, r14d
0x180027a3a  test    rsi, rsi
0x180027a3d  jnz     short loc_180027A46
0x180027a3f  mov     eax, 1
0x180027a44  jmp     short loc_180027A9E
0x180027a46  mov     rcx, rsi; lpWideCharStr
0x180027a49  call    UnicodeStringToAnsiString
0x180027a4e  mov     rbp, rax
0x180027a51  test    rax, rax
0x180027a54  jz      short loc_180027A9C
0x180027a56  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180027a5a  inc     rdi
0x180027a5d  cmp     [rsi+rdi*2], r14w
0x180027a62  jnz     short loc_180027A5A
0x180027a64  mov     rcx, rbp; String
0x180027a67  lea     rdi, ds:2[rdi*2]
0x180027a6f  call    cs:__imp__mbstrlen
0x180027a76  nop     dword ptr [rax+rax+00h]
0x180027a7b  inc     rax
0x180027a7e  cmp     rdi, rax
0x180027a81  jnb     short loc_180027AAC
0x180027a83  mov     rcx, rbp; lpMem
0x180027a86  call    pMemFree
0x180027a8b  mov     ecx, 57h ; 'W'; dwErrCode
0x180027a90  call    cs:__imp_SetLastError
0x180027a97  nop     dword ptr [rax+rax+00h]
0x180027a9c  xor     eax, eax
0x180027a9e  add     rsp, 28h
0x180027aa2  pop     r14
0x180027aa4  pop     r12
0x180027aa6  pop     rdi
0x180027aa7  pop     rsi
0x180027aa8  pop     rbp
0x180027aa9  pop     rbx
0x180027aaa  retn
0x180027aac  test    rdi, rdi
0x180027aaf  jz      short loc_180027B02
0x180027ab1  cmp     rdi, 7FFFFFFFh
0x180027ab8  jbe     short loc_180027AC1
0x180027aba  mov     ebx, 80070057h
0x180027abf  jmp     short loc_180027B0C
0x180027ac1  mov     eax, 7FFFFFFEh
0x180027ac6  mov     rcx, rbp
0x180027ac9  test    rax, rax
0x180027acc  jz      short loc_180027AE5
0x180027ace  mov     dl, [rcx]
0x180027ad0  test    dl, dl
0x180027ad2  jz      short loc_180027AE5
0x180027ad4  mov     [rsi], dl
0x180027ad6  inc     rcx
0x180027ad9  inc     rsi
0x180027adc  dec     rax
0x180027adf  sub     rdi, 1
0x180027ae3  jnz     short loc_180027AC9
0x180027ae5  test    rdi, rdi
0x180027ae8  lea     rax, [rsi-1]
0x180027aec  cmovnz  rax, rsi
0x180027af0  neg     rdi
0x180027af3  sbb     ebx, ebx
0x180027af5  not     ebx
0x180027af7  and     ebx, 8007007Ah
0x180027afd  mov     [rax], r14b
0x180027b00  jmp     short loc_180027B0F
0x180027b02  mov     ebx, 80070057h
0x180027b07  test    rdi, rdi
0x180027b0a  jz      short loc_180027B0F
0x180027b0c  mov     [rsi], r14b
0x180027b0f  mov     rcx, rbp; lpMem
0x180027b12  call    pMemFree
0x180027b17  test    ebx, ebx
0x180027b19  jns     loc_180027A3F
0x180027b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b26  cmp     rcx, r12
0x180027b29  jz      short loc_180027B52
0x180027b2b  test    dword ptr [rcx+1Ch], 1000h
0x180027b32  jz      short loc_180027B52
0x180027b34  cmp     byte ptr [rcx+19h], 2
0x180027b38  jb      short loc_180027B52
0x180027b3a  mov     rcx, [rcx+10h]
0x180027b3e  lea     r8, WPP_a4158162aa603b3b4cac811f54679e94_Traceguids
0x180027b45  mov     edx, 0Bh
0x180027b4a  mov     r9d, ebx
0x180027b4d  call    WPP_SF_d
0x180027b52  mov     eax, ebx
0x180027b54  movzx   ecx, bx
0x180027b57  and     eax, 1FFF0000h
0x180027b5c  cmp     eax, 70000h
0x180027b61  cmovnz  ecx, ebx
0x180027b64  jmp     loc_180027A90
```
