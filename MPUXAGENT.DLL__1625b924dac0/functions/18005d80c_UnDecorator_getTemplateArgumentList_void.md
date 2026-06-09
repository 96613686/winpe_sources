# UnDecorator::getTemplateArgumentList(void)

- ea: `0x18005d80c`
- end: `0x18005da7b`
- name: `?getTemplateArgumentList@UnDecorator@@CA?AVDName@@XZ`
- size: `623`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180032eb4`

## callees

- `0x1800074c8`
- `0x1800095a0`
- `0x18005d3cc`
- `0x18005d80c`
- `0x18005da7c`
- `0x18005db18`
- `0x18005dd54`
- `0x18005dde4`
- `0x18005de80`
- `0x1800684a0`

## pseudocode

```c
__int64 __fastcall UnDecorator::getTemplateArgumentList(__int64 a1, unsigned int a2, __int64 a3)
{
  int v6; // ebx
  int v7; // eax
  LONG v8; // eax
  int v9; // r8d
  LONG v10; // edi
  int v11; // eax
  int v12; // edx
  int v13; // r8d
  _DWORD v15[2]; // [rsp+48h] [rbp-79h] BYREF
  __int64 v16; // [rsp+50h] [rbp-71h]
  __int64 v17; // [rsp+58h] [rbp-69h]
  __int64 v18; // [rsp+60h] [rbp-61h]
  _DWORD v19[6]; // [rsp+68h] [rbp-59h] BYREF
  __int64 v20; // [rsp+80h] [rbp-41h]
  int v21; // [rsp+88h] [rbp-39h]
  _DWORD *v22; // [rsp+90h] [rbp-31h]
  int v23; // [rsp+98h] [rbp-29h]
  __int64 v24; // [rsp+A0h] [rbp-21h]
  int v25; // [rsp+B0h] [rbp-11h]
  __int64 *v26; // [rsp+B8h] [rbp-9h]
  GUID v27; // [rsp+C8h] [rbp+7h] BYREF
  __int64 v28; // [rsp+D8h] [rbp+17h] BYREF
  int v29; // [rsp+E0h] [rbp+1Fh]
  unsigned int v30; // [rsp+E4h] [rbp+23h]
  int v31; // [rsp+E8h] [rbp+27h]
  __int64 v32; // [rsp+ECh] [rbp+2Bh]
  int v33; // [rsp+F4h] [rbp+33h]

  v6 = 0;
  v27.Data1 = 11191659;
  *(_DWORD *)&v27.Data2 = 298896708;
  *(_DWORD *)v27.Data4 = -1073692020;
  *(_DWORD *)&v27.Data4[4] = -292175281;
  sub_1800684A0(v19, 0, 88);
  v15[1] = 0;
  v18 = 0;
  v30 = 0;
  v32 = 0;
  v33 = 0;
  v19[0] = 88;
  v21 = 1;
  v22 = v15;
  v20 = 2;
  v26 = &v28;
  v7 = 0;
  if ( (a2 & 8) == 0 )
    v7 = 16;
  v25 = v7;
  if ( (a2 & 0x10) == 0 )
    v25 = v7 | 0x1000;
  v15[0] = 32;
  v16 = a1;
  v17 = a3;
  v28 = 32;
  v29 = 3;
  while ( 1 )
  {
    v24 = 0;
    v23 = 1;
    v31 = 0;
    v8 = sub_18005D3CC(HWND_MESSAGE|0x2LL, &v27, v19);
    v10 = v8;
    if ( v8 < 0 )
    {
      if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 0x10) != 0 )
        sub_18005DDE4(*((_QWORD *)off_180096D60 + 2), 20, v9, a1, SBYTE4(v28), v30, v8);
      goto LABEL_16;
    }
    if ( !v24 )
    {
      sub_18005DA7C(v19);
      return 2147549183LL;
    }
    v11 = sub_18005DB18(v24, a2);
    v10 = v11;
    if ( v11 >= 0 )
      break;
    if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 0x10) != 0 )
      sub_18005DDE4(*((_QWORD *)off_180096D60 + 2), 19, v13, a1, SBYTE4(v28), v30, v11);
    sub_18005DA7C(v19);
LABEL_16:
    if ( !HIDWORD(v28) )
      v6 = v10;
    if ( (unsigned int)sub_1800074C8() )
    {
      if ( ++HIDWORD(v28) <= v30 )
        continue;
    }
    if ( v6 >= 0 )
      v6 = -2147467259;
    if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 1) != 0 )
      sub_18005DE80(*((_QWORD *)off_180096D60 + 2), 21, (unsigned int)&stru_180085FD8, a1, a2, v6);
    return (unsigned int)v6;
  }
  if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 4) != 0 )
    sub_18005DD54(*((_QWORD *)off_180096D60 + 2), v12, v13, a1, SBYTE4(v28), v30);
  sub_18005DA7C(v19);
  return 0;
}

```

## disassembly

```asm
0x18005d80c  mov     rax, rsp
0x18005d80f  mov     [rax+10h], rbx
0x18005d813  mov     [rax+18h], rsi
0x18005d817  mov     [rax+20h], rdi
0x18005d81b  push    rbp
0x18005d81c  push    r14
0x18005d81e  push    r15
0x18005d820  lea     rbp, [rax-5Fh]
0x18005d824  sub     rsp, 100h
0x18005d82b  mov     rax, cs:__security_cookie
0x18005d832  xor     rax, rsp
0x18005d835  mov     [rbp+57h+var_20], rax
0x18005d839  mov     rdi, r8
0x18005d83c  mov     r14d, edx
0x18005d83f  mov     rsi, rcx
0x18005d842  xor     ebx, ebx
0x18005d844  mov     [rbp+57h+var_50], 0AAC56Bh
0x18005d84b  mov     [rbp+57h+var_4C], 11D0CD44h
0x18005d852  mov     [rbp+57h+var_48], 0C000C28Ch
0x18005d859  mov     [rbp+57h+var_44], 0EE95C24Fh
0x18005d860  lea     r15d, [rbx+58h]
0x18005d864  mov     r8d, r15d
0x18005d867  xor     edx, edx
0x18005d869  lea     rcx, [rbp+57h+var_B0]
0x18005d86d  call    sub_1800684A0
0x18005d872  mov     [rbp+57h+var_CC], ebx
0x18005d875  mov     [rbp+57h+var_B8], rbx
0x18005d879  mov     [rbp+57h+var_34], ebx
0x18005d87c  mov     [rbp+57h+var_2C], rbx
0x18005d880  mov     [rbp+57h+var_24], ebx
0x18005d883  mov     [rbp+57h+var_B0], r15d
0x18005d887  mov     [rbp+57h+var_90], 1
0x18005d88e  lea     rax, [rbp+57h+var_D0]
0x18005d892  mov     [rbp+57h+var_88], rax
0x18005d896  mov     [rbp+57h+var_98], 2
0x18005d89e  lea     rax, [rbp+57h+var_40]
0x18005d8a2  mov     [rbp+57h+var_60], rax
0x18005d8a6  test    r14b, 8
0x18005d8aa  mov     eax, ebx
0x18005d8ac  lea     ecx, [rbx+10h]
0x18005d8af  cmovz   eax, ecx
0x18005d8b2  mov     [rbp+57h+var_68], eax
0x18005d8b5  test    cl, r14b
0x18005d8b8  jnz     short loc_18005D8C1
0x18005d8ba  bts     eax, 0Ch
0x18005d8be  mov     [rbp+57h+var_68], eax
0x18005d8c1  mov     eax, 20h ; ' '
0x18005d8c6  mov     [rbp+57h+var_D0], eax
0x18005d8c9  mov     [rbp+57h+var_C8], rsi
0x18005d8cd  mov     [rbp+57h+var_C0], rdi
0x18005d8d1  mov     [rbp+57h+var_40], rax
0x18005d8d5  mov     [rbp+57h+var_38], 3
0x18005d8dc  lea     r15, off_180096D60
0x18005d8e3  mov     [rbp+57h+var_78], 0
0x18005d8eb  mov     [rbp+57h+var_80], 1
0x18005d8f2  mov     [rbp+57h+var_30], 0
0x18005d8f9  lea     r8, [rbp+57h+var_B0]
0x18005d8fd  lea     rdx, [rbp+57h+var_50]
0x18005d901  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005d905  call    sub_18005D3CC
0x18005d90a  mov     edi, eax
0x18005d90c  test    eax, eax
0x18005d90e  js      short loc_18005D971
0x18005d910  mov     rcx, [rbp+57h+var_78]
0x18005d914  test    rcx, rcx
0x18005d917  jz      loc_18005DA6A
0x18005d91d  mov     edx, r14d
0x18005d920  call    sub_18005DB18
0x18005d925  mov     edi, eax
0x18005d927  test    eax, eax
0x18005d929  jns     loc_18005DA2F
0x18005d92f  mov     rcx, cs:off_180096D60
0x18005d936  cmp     rcx, r15
0x18005d939  jz      short loc_18005D965
0x18005d93b  test    byte ptr [rcx+1Ch], 10h
0x18005d93f  jz      short loc_18005D965
0x18005d941  mov     edx, 13h
0x18005d946  mov     [rsp+110h+var_E0], eax
0x18005d94a  mov     eax, [rbp+57h+var_34]
0x18005d94d  mov     [rsp+110h+var_E8], eax
0x18005d951  mov     eax, dword ptr [rbp+57h+var_40+4]
0x18005d954  mov     [rsp+110h+var_F0], eax
0x18005d958  mov     r9, rsi
0x18005d95b  mov     rcx, [rcx+10h]
0x18005d95f  call    sub_18005DDE4
0x18005d964  nop
0x18005d965  lea     rcx, [rbp+57h+var_B0]
0x18005d969  call    sub_18005DA7C
0x18005d96e  nop
0x18005d96f  jmp     short loc_18005D9A6
0x18005d971  mov     rcx, cs:off_180096D60
0x18005d978  cmp     rcx, r15
0x18005d97b  jz      short loc_18005D9A6
0x18005d97d  test    byte ptr [rcx+1Ch], 10h
0x18005d981  jz      short loc_18005D9A6
0x18005d983  mov     edx, 14h
0x18005d988  mov     [rsp+110h+var_E0], eax
0x18005d98c  mov     eax, [rbp+57h+var_34]
0x18005d98f  mov     [rsp+110h+var_E8], eax
0x18005d993  mov     eax, dword ptr [rbp+57h+var_40+4]
0x18005d996  mov     [rsp+110h+var_F0], eax
0x18005d99a  mov     r9, rsi
0x18005d99d  mov     rcx, [rcx+10h]
0x18005d9a1  call    sub_18005DDE4
0x18005d9a6  cmp     dword ptr [rbp+57h+var_40+4], 0
0x18005d9aa  cmovz   ebx, edi
0x18005d9ad  call    sub_1800074C8
0x18005d9b2  test    eax, eax
0x18005d9b4  jz      short loc_18005D9C7
0x18005d9b6  mov     eax, dword ptr [rbp+57h+var_40+4]
0x18005d9b9  inc     eax
0x18005d9bb  mov     dword ptr [rbp+57h+var_40+4], eax
0x18005d9be  cmp     eax, [rbp+57h+var_34]
0x18005d9c1  jbe     loc_18005D8E3
0x18005d9c7  mov     eax, 80004005h
0x18005d9cc  test    ebx, ebx
0x18005d9ce  cmovns  ebx, eax
0x18005d9d1  mov     rcx, cs:off_180096D60
0x18005d9d8  cmp     rcx, r15
0x18005d9db  jz      short loc_18005DA04
0x18005d9dd  test    byte ptr [rcx+1Ch], 1
0x18005d9e1  jz      short loc_18005DA04
0x18005d9e3  mov     edx, 15h
0x18005d9e8  mov     [rsp+110h+var_E8], ebx
0x18005d9ec  mov     [rsp+110h+var_F0], r14d
0x18005d9f1  mov     r9, rsi
0x18005d9f4  lea     r8, stru_180085FD8
0x18005d9fb  mov     rcx, [rcx+10h]
0x18005d9ff  call    sub_18005DE80
0x18005da04  mov     eax, ebx
0x18005da06  mov     rcx, [rbp+57h+var_20]
0x18005da0a  xor     rcx, rsp; StackCookie
0x18005da0d  call    __security_check_cookie
0x18005da12  lea     r11, [rsp+110h+var_10]
0x18005da1a  mov     rbx, [r11+28h]
0x18005da1e  mov     rsi, [r11+30h]
0x18005da22  mov     rdi, [r11+38h]
0x18005da26  mov     rsp, r11
0x18005da29  pop     r15
0x18005da2b  pop     r14
0x18005da2d  pop     rbp
0x18005da2e  retn
0x18005da2f  mov     rcx, cs:off_180096D60
0x18005da36  cmp     rcx, r15
0x18005da39  jz      short loc_18005DA5C
0x18005da3b  test    byte ptr [rcx+1Ch], 4
0x18005da3f  jz      short loc_18005DA5C
0x18005da41  mov     eax, [rbp+57h+var_34]
0x18005da44  mov     [rsp+110h+var_E8], eax
0x18005da48  mov     eax, dword ptr [rbp+57h+var_40+4]
0x18005da4b  mov     [rsp+110h+var_F0], eax
0x18005da4f  mov     r9, rsi
0x18005da52  mov     rcx, [rcx+10h]
0x18005da56  call    sub_18005DD54
0x18005da5b  nop
0x18005da5c  lea     rcx, [rbp+57h+var_B0]
0x18005da60  call    sub_18005DA7C
0x18005da65  nop
0x18005da66  xor     eax, eax
0x18005da68  jmp     short loc_18005DA06
0x18005da6a  lea     rcx, [rbp+57h+var_B0]
0x18005da6e  call    sub_18005DA7C
0x18005da73  nop
0x18005da74  mov     eax, 8000FFFFh
0x18005da79  jmp     short loc_18005DA06
```
