# sub_1800ACBA0

- ea: `0x1800acba0`
- end: `0x1800ace22`
- name: `sub_1800ACBA0`
- size: `642`
- prototype: `int __fastcall(__int64, _BYTE *)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800aca10`
- `0x1800acaa0`

## callees

- `0x180098e08`
- `0x1800a3940`
- `0x1800acba0`
- `0x1800afb0c`
- `0x1800cad3c`
- `0x1800cb388`
- `0x1800cb620`
- `0x1800cc710`
- `0x1800cca28`
- `0x1800cd2a8`
- `0x1800d2dc0`
- `0x1801d4f70`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1800acdad`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1800acdad`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800acc85`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800acc85`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800acd02`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800acd02`

## string_xrefs

- `0x1800acd5a`: `FCMinWriteVer`

## pseudocode

```c
int __fastcall sub_1800ACBA0(__int64 a1, _BYTE *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // r8d
  __int64 v14; // rcx
  __int64 v15; // rbx
  int v16; // r9d
  __int64 v17; // rbx
  wchar_t Source[28]; // [rsp+48h] [rbp-60h] BYREF

  v4 = *(_QWORD *)(a1 + 24);
  v5 = *(int *)(a1 + 672);
  if ( (int)v5 < 0 || (int)v5 >= *(_DWORD *)(v4 + 28) || (v6 = *(int *)(v4 + 4 * v5 + 2560), (_DWORD)v6 == -1) )
    v7 = 0;
  else
    v7 = *(_QWORD *)(v4 + 8 * v6 + 2304);
  v8 = *(_QWORD *)(a1 + 680);
  if ( !v8 || (LODWORD(v9) = *(_DWORD *)(v7 + 68), *(_DWORD *)(v8 + 56) != (_DWORD)v9) )
  {
    v10 = *(_QWORD *)(a1 + 8);
    if ( v8 )
      sub_1800CB620(v8, *(_QWORD *)(a1 + 8));
    v11 = *(_QWORD *)(v10 + 24);
    v12 = 0;
    v13 = *(_DWORD *)(v11 + 100);
    if ( v13 )
    {
      while ( 1 )
      {
        v14 = *(_QWORD *)(*(_QWORD *)(v11 + 88) + 8 * v12);
        if ( *(_DWORD *)(v14 + 56) == *(_DWORD *)(v7 + 68) )
          break;
        v12 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= v13 )
          goto LABEL_13;
      }
    }
    else
    {
LABEL_13:
      v14 = 0;
    }
    *(_QWORD *)(a1 + 680) = v14;
    if ( v14 )
    {
      v9 = *(_QWORD *)(a1 + 24);
      if ( *(_DWORD *)(v14 + 56) != *(_DWORD *)(v9 + 56) )
        LODWORD(v9) = sub_1800CCA28(v14, *(_QWORD *)(v10 + 16), 1);
    }
    else
    {
      LODWORD(v9) = sub_1800D2DC0(*(unsigned int *)(v7 + 68), v10, a2, 0);
      if ( (*a2 & 8) != 0 )
      {
LABEL_34:
        *(_QWORD *)(a1 + 680) = 0;
        return v9;
      }
      v9 = Mso20Win32Client_52497(3432, 2);
      if ( v9 )
        v9 = sub_1800CAD3C(v9, *(_QWORD *)(v10 + 24), a2);
      *(_QWORD *)(a1 + 680) = v9;
      if ( !v9 )
      {
        sub_180098E08(a2, 4294966285LL);
        v9 = *(_QWORD *)(a1 + 680);
      }
      if ( (*a2 & 8) == 0 )
        LODWORD(v9) = sub_1800CC710(v9, v10, *(_DWORD *)(v7 + 68), 1, (__int64)a2);
      v15 = *(_QWORD *)(a1 + 680);
      if ( (*a2 & 8) != 0 )
      {
        if ( v15 )
        {
          sub_1800CB388(*(_QWORD *)(a1 + 680));
          LODWORD(v9) = Mso20Win32Client_53248(v15);
        }
        *(_QWORD *)(a1 + 680) = 0;
      }
      else
      {
        v9 = sub_1800CD2A8(v15, v10);
        if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(v10 + 24) + 132LL) - 3) <= 0xFFFA )
        {
          if ( v9 )
          {
            LODWORD(v9) = sub_1800AFB0C(
                            v10,
                            (unsigned int)L"Tables",
                            v9,
                            v16,
                            (__int64)L"FCMinWriteVer",
                            (__int64)Source);
            if ( (_DWORD)v9 )
            {
              sub_1800A3940(Source);
              v17 = *(_QWORD *)(a1 + 680);
              LODWORD(v9) = wcsncpy_s((wchar_t *)(v17 + 3376), 0x1Au, Source, 0xFFFFFFFFFFFFFFFFuLL);
              *(_DWORD *)(v17 + 3372) = 0;
            }
          }
        }
      }
    }
    if ( (*a2 & 8) == 0 )
    {
      v9 = *(_QWORD *)(a1 + 680);
      ++*(_DWORD *)(v9 + 92);
      return v9;
    }
    goto LABEL_34;
  }
  return v9;
}

```

## disassembly

```asm
0x1800acba0  mov     [rsp+arg_10], rbx
0x1800acba5  mov     [rsp+arg_18], rbp
0x1800acbaa  push    rsi
0x1800acbab  push    rdi
0x1800acbac  push    r14
0x1800acbae  sub     rsp, 90h
0x1800acbb5  mov     rax, cs:__security_cookie
0x1800acbbc  xor     rax, rsp
0x1800acbbf  mov     [rsp+0A8h+var_28], rax
0x1800acbc7  mov     rbp, rdx
0x1800acbca  mov     rdi, rcx
0x1800acbcd  mov     rcx, [rcx+18h]
0x1800acbd1  movsxd  rax, dword ptr [rdi+2A0h]
0x1800acbd8  test    eax, eax
0x1800acbda  js      short loc_1800ACBF8
0x1800acbdc  cmp     eax, [rcx+1Ch]
0x1800acbdf  jge     short loc_1800ACBF8
0x1800acbe1  movsxd  rdx, dword ptr [rcx+rax*4+0A00h]
0x1800acbe9  cmp     edx, 0FFFFFFFFh
0x1800acbec  jz      short loc_1800ACBF8
0x1800acbee  mov     r14, [rcx+rdx*8+900h]
0x1800acbf6  jmp     short loc_1800ACBFB
0x1800acbf8  xor     r14d, r14d
0x1800acbfb  mov     rcx, [rdi+2A8h]
0x1800acc02  test    rcx, rcx
0x1800acc05  jz      short loc_1800ACC14
0x1800acc07  mov     eax, [r14+44h]
0x1800acc0b  cmp     [rcx+38h], eax
0x1800acc0e  jz      loc_1800ACDFA
0x1800acc14  mov     rsi, [rdi+8]
0x1800acc18  test    rcx, rcx
0x1800acc1b  jz      short loc_1800ACC25
0x1800acc1d  mov     rdx, rsi
0x1800acc20  call    sub_1800CB620
0x1800acc25  mov     rax, [rsi+18h]
0x1800acc29  mov     r10d, [r14+44h]
0x1800acc2d  xor     edx, edx
0x1800acc2f  mov     r8d, [rax+64h]
0x1800acc33  test    r8d, r8d
0x1800acc36  jz      short loc_1800ACC4D
0x1800acc38  mov     r9, [rax+58h]
0x1800acc3c  mov     rcx, [r9+rdx*8]
0x1800acc40  cmp     [rcx+38h], r10d
0x1800acc44  jz      short loc_1800ACC4F
0x1800acc46  inc     edx
0x1800acc48  cmp     edx, r8d
0x1800acc4b  jb      short loc_1800ACC3C
0x1800acc4d  xor     ecx, ecx
0x1800acc4f  mov     [rdi+2A8h], rcx
0x1800acc56  test    rcx, rcx
0x1800acc59  jnz     loc_1800ACDBF
0x1800acc5f  xor     r9d, r9d
0x1800acc62  mov     r8, rbp
0x1800acc65  mov     rdx, rsi
0x1800acc68  mov     ecx, [r14+44h]
0x1800acc6c  call    sub_1800D2DC0
0x1800acc71  test    byte ptr [rbp+0], 8
0x1800acc75  jnz     loc_1800ACDE3
0x1800acc7b  mov     edx, 2
0x1800acc80  mov     ecx, 0D68h
0x1800acc85  call    cs:Mso20Win32Client_52497
0x1800acc8b  mov     [rsp+0A8h+var_68], rax
0x1800acc90  test    rax, rax
0x1800acc93  jz      short loc_1800ACCA5
0x1800acc95  mov     r8, rbp
0x1800acc98  mov     rdx, [rsi+18h]
0x1800acc9c  mov     rcx, rax
0x1800acc9f  call    sub_1800CAD3C
0x1800acca4  nop
0x1800acca5  mov     [rdi+2A8h], rax
0x1800accac  test    rax, rax
0x1800accaf  jnz     short loc_1800ACCC5
0x1800accb1  mov     edx, 0FFFFFC0Dh
0x1800accb6  mov     rcx, rbp
0x1800accb9  call    sub_180098E08
0x1800accbe  mov     rax, [rdi+2A8h]
0x1800accc5  test    byte ptr [rbp+0], 8
0x1800accc9  jnz     short loc_1800ACCE5
0x1800acccb  mov     [rsp+0A8h+var_88], rbp
0x1800accd0  mov     r9d, 1
0x1800accd6  mov     r8d, [r14+44h]
0x1800accda  mov     rdx, rsi
0x1800accdd  mov     rcx, rax
0x1800acce0  call    sub_1800CC710
0x1800acce5  mov     rbx, [rdi+2A8h]
0x1800accec  test    byte ptr [rbp+0], 8
0x1800accf0  jz      short loc_1800ACD18
0x1800accf2  test    rbx, rbx
0x1800accf5  jz      short loc_1800ACD08
0x1800accf7  mov     rcx, rbx
0x1800accfa  call    sub_1800CB388
0x1800accff  mov     rcx, rbx
0x1800acd02  call    cs:Mso20Win32Client_53248
0x1800acd08  mov     qword ptr [rdi+2A8h], 0
0x1800acd13  jmp     loc_1800ACDDD
0x1800acd18  mov     dword ptr [rsp+0A8h+var_68], 0
0x1800acd20  mov     rdx, rsi
0x1800acd23  mov     rcx, rbx
0x1800acd26  call    sub_1800CD2A8
0x1800acd2b  mov     rdx, [rsi+18h]
0x1800acd2f  mov     r8d, [rdx+84h]
0x1800acd36  add     r8d, 0FFFFFFFDh
0x1800acd3a  cmp     r8d, 0FFFAh
0x1800acd41  ja      loc_1800ACDDD
0x1800acd47  test    rax, rax
0x1800acd4a  jz      loc_1800ACDDD
0x1800acd50  lea     rcx, [rsp+0A8h+Source]
0x1800acd55  mov     [rsp+0A8h+var_80], rcx
0x1800acd5a  lea     rcx, aFcminwritever; "FCMinWriteVer"
0x1800acd61  mov     [rsp+0A8h+var_88], rcx
0x1800acd66  mov     r8, rax
0x1800acd69  lea     rdx, aTables; "Tables"
0x1800acd70  mov     rcx, rsi
0x1800acd73  call    sub_1800AFB0C
0x1800acd78  test    eax, eax
0x1800acd7a  jz      short loc_1800ACDDD
0x1800acd7c  lea     rdx, [rsp+0A8h+var_68]
0x1800acd81  lea     rcx, [rsp+0A8h+Source]; Source
0x1800acd86  call    sub_1800A3940
0x1800acd8b  cmp     dword ptr [rsp+0A8h+var_68], 0
0x1800acd90  jnz     short loc_1800ACDDD
0x1800acd92  mov     rbx, [rdi+2A8h]
0x1800acd99  lea     rcx, [rbx+0D30h]; Destination
0x1800acda0  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800acda4  lea     r8, [rsp+0A8h+Source]; Source
0x1800acda9  lea     edx, [r9+1Bh]; SizeInWords
0x1800acdad  call    cs:wcsncpy_s
0x1800acdb3  mov     dword ptr [rbx+0D2Ch], 0
0x1800acdbd  jmp     short loc_1800ACDDD
0x1800acdbf  mov     rax, [rdi+18h]
0x1800acdc3  mov     edx, [rax+38h]
0x1800acdc6  cmp     [rcx+38h], edx
0x1800acdc9  jz      short loc_1800ACDDD
0x1800acdcb  mov     r9, rbp
0x1800acdce  mov     r8d, 1
0x1800acdd4  mov     rdx, [rsi+10h]
0x1800acdd8  call    sub_1800CCA28
0x1800acddd  test    byte ptr [rbp+0], 8
0x1800acde1  jz      short loc_1800ACDF0
0x1800acde3  mov     qword ptr [rdi+2A8h], 0
0x1800acdee  jmp     short loc_1800ACDFA
0x1800acdf0  mov     rax, [rdi+2A8h]
0x1800acdf7  inc     dword ptr [rax+5Ch]
0x1800acdfa  mov     rcx, [rsp+0A8h+var_28]
0x1800ace02  xor     rcx, rsp; StackCookie
0x1800ace05  call    __security_check_cookie
0x1800ace0a  lea     r11, [rsp+0A8h+var_18]
0x1800ace12  mov     rbx, [r11+30h]
0x1800ace16  mov     rbp, [r11+38h]
0x1800ace1a  mov     rsp, r11
0x1800ace1d  pop     r14
0x1800ace1f  pop     rdi
0x1800ace20  pop     rsi
0x1800ace21  retn
```
