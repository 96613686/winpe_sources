# BsdLogWriteEvent

- ea: `0x140003a48`
- end: `0x140003bef`
- name: `BsdLogWriteEvent`
- size: `423`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140002a00`

## callees

- `0x1400029a8`
- `0x140002b24`
- `0x140003a48`
- `0x140026650`

## pseudocode

```c
__int64 __fastcall BsdLogWriteEvent(__int64 a1, __int64 a2, _DWORD *a3, void *a4)
{
  NTSTATUS v6; // edx
  unsigned int v7; // eax
  unsigned int v8; // r8d
  unsigned int v9; // edi
  unsigned int v10; // ebx
  ULONG v11; // r8d
  unsigned int v12; // edi
  __int128 v14; // [rsp+20h] [rbp-50h] BYREF
  unsigned int v15; // [rsp+30h] [rbp-40h]
  __int128 v16; // [rsp+38h] [rbp-38h] BYREF
  __int128 v17; // [rsp+48h] [rbp-28h]
  __int64 v18; // [rsp+58h] [rbp-18h]

  v15 = 0;
  v18 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v6 = BfspBsdLogRead(0, &v14, 0x14u);
  if ( v6 >= 0 )
  {
    v7 = a3[6];
    v8 = DWORD2(v14);
    if ( v7 <= DWORD2(v14) )
    {
      if ( (_DWORD)v14 == 4 )
      {
        v9 = HIDWORD(v14);
        v10 = v15;
        if ( v15 == HIDWORD(v14) )
          goto LABEL_35;
        if ( HIDWORD(v14) + v7 <= DWORD2(v14) )
          goto LABEL_20;
        v16 = 0;
        if ( v15 > HIDWORD(v14) )
          v10 = DWORD1(v14);
        v11 = DWORD2(v14) - HIDWORD(v14);
        v18 = 0;
        v17 = 0;
        if ( (unsigned int)(DWORD2(v14) - HIDWORD(v14)) > 0x28 )
          v11 = 40;
        v6 = BfspBsdLogWrite(HIDWORD(v14), &v16, v11);
        if ( v6 >= 0 )
        {
          v9 = DWORD1(v14);
          v8 = DWORD2(v14);
LABEL_20:
          while ( v10 <= v9 + a3[6] )
          {
            if ( v10 >= v8 )
              goto LABEL_24;
            if ( v10 < v9 )
              break;
            v6 = BfspBsdLogRead(v10, &v16, 0x28u);
            if ( v6 < 0 )
              return (unsigned int)v6;
            v8 = DWORD2(v14);
            if ( (unsigned __int64)v10 + 40 <= DWORD2(v14) )
            {
              if ( DWORD2(v17) )
              {
                v10 += DWORD2(v17);
                if ( v10 <= DWORD2(v14) )
                  continue;
              }
            }
            v10 = DWORD1(v14);
            break;
          }
          if ( v10 < v8 )
            goto LABEL_25;
LABEL_24:
          v10 = DWORD1(v14);
LABEL_25:
          if ( v10 != DWORD1(v14) || v9 != DWORD1(v14) )
          {
LABEL_35:
            v6 = BfspBsdLogWrite(v9, a3, 0x28u);
            if ( v6 >= 0 )
            {
              v12 = v9 + 40;
              if ( a4 )
              {
                v6 = BfspBsdLogWrite(v12, a4, 0xCu);
                if ( v6 < 0 )
                  return (unsigned int)v6;
                v12 += 12;
              }
              HIDWORD(v14) = v12;
              v15 = v10;
              return (unsigned int)BfspBsdLogWrite(0, &v14, 0x14u);
            }
          }
        }
      }
      else
      {
        return (unsigned int)-1073741735;
      }
    }
    else
    {
      return (unsigned int)-2147483643;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140003a48  mov     [rsp-28h+arg_0], rbx
0x140003a4d  push    rbp
0x140003a4e  push    rsi
0x140003a4f  push    rdi
0x140003a50  push    r14
0x140003a52  push    r15
0x140003a54  mov     rbp, rsp
0x140003a57  sub     rsp, 70h
0x140003a5b  mov     rax, cs:__security_cookie
0x140003a62  xor     rax, rsp
0x140003a65  mov     [rbp+var_10], rax
0x140003a69  xor     eax, eax
0x140003a6b  lea     rdx, [rbp+var_50]
0x140003a6f  xorps   xmm1, xmm1
0x140003a72  mov     [rbp+var_40], eax
0x140003a75  mov     rsi, r8
0x140003a78  mov     [rbp+var_18], rax
0x140003a7c  xorps   xmm0, xmm0
0x140003a7f  xor     ecx, ecx
0x140003a81  lea     r8d, [rax+14h]
0x140003a85  mov     r14, r9
0x140003a88  movups  [rbp+var_50], xmm0
0x140003a8c  movups  [rbp+var_38], xmm1
0x140003a90  movups  [rbp+var_28], xmm1
0x140003a94  call    BfspBsdLogRead
0x140003a99  mov     edx, eax
0x140003a9b  test    eax, eax
0x140003a9d  js      loc_140003BCD
0x140003aa3  mov     eax, [rsi+18h]
0x140003aa6  mov     r8d, dword ptr [rbp+var_50+8]
0x140003aaa  cmp     eax, r8d
0x140003aad  jbe     short loc_140003AB9
0x140003aaf  mov     edx, 80000005h
0x140003ab4  jmp     loc_140003BCD
0x140003ab9  cmp     dword ptr [rbp+var_50], 4
0x140003abd  jz      short loc_140003AC9
0x140003abf  mov     edx, 0C0000059h
0x140003ac4  jmp     loc_140003BCD
0x140003ac9  mov     edi, dword ptr [rbp+var_50+0Ch]
0x140003acc  mov     r15d, 28h ; '('
0x140003ad2  mov     ebx, [rbp+var_40]
0x140003ad5  cmp     ebx, edi
0x140003ad7  jz      loc_140003B80
0x140003add  add     eax, edi
0x140003adf  cmp     eax, r8d
0x140003ae2  jbe     short loc_140003B60
0x140003ae4  xorps   xmm0, xmm0
0x140003ae7  lea     rdx, [rbp+var_38]
0x140003aeb  cmp     ebx, edi
0x140003aed  mov     ecx, edi
0x140003aef  movups  [rbp+var_38], xmm0
0x140003af3  cmova   ebx, dword ptr [rbp+var_50+4]
0x140003af7  xor     eax, eax
0x140003af9  sub     r8d, edi
0x140003afc  mov     [rbp+var_18], rax
0x140003b00  cmp     r8d, r15d
0x140003b03  movups  [rbp+var_28], xmm0
0x140003b07  cmova   r8d, r15d
0x140003b0b  call    BfspBsdLogWrite
0x140003b10  mov     edx, eax
0x140003b12  test    eax, eax
0x140003b14  js      loc_140003BCD
0x140003b1a  mov     edi, dword ptr [rbp+var_50+4]
0x140003b1d  mov     r8d, dword ptr [rbp+var_50+8]
0x140003b21  jmp     short loc_140003B60
0x140003b23  cmp     ebx, r8d
0x140003b26  jnb     short loc_140003B73
0x140003b28  cmp     ebx, edi
0x140003b2a  jb      short loc_140003B6E
0x140003b2c  mov     r8d, r15d
0x140003b2f  lea     rdx, [rbp+var_38]
0x140003b33  mov     ecx, ebx
0x140003b35  call    BfspBsdLogRead
0x140003b3a  mov     edx, eax
0x140003b3c  test    eax, eax
0x140003b3e  js      loc_140003BCD
0x140003b44  mov     r8d, dword ptr [rbp+var_50+8]
0x140003b48  mov     ecx, ebx
0x140003b4a  add     rcx, r15
0x140003b4d  cmp     rcx, r8
0x140003b50  ja      short loc_140003B6B
0x140003b52  mov     eax, dword ptr [rbp+var_28+8]
0x140003b55  test    eax, eax
0x140003b57  jz      short loc_140003B6B
0x140003b59  add     ebx, eax
0x140003b5b  cmp     ebx, r8d
0x140003b5e  ja      short loc_140003B6B
0x140003b60  mov     ecx, [rsi+18h]
0x140003b63  add     ecx, edi
0x140003b65  cmp     ebx, ecx
0x140003b67  jbe     short loc_140003B23
0x140003b69  jmp     short loc_140003B6E
0x140003b6b  mov     ebx, dword ptr [rbp+var_50+4]
0x140003b6e  cmp     ebx, r8d
0x140003b71  jb      short loc_140003B76
0x140003b73  mov     ebx, dword ptr [rbp+var_50+4]
0x140003b76  cmp     ebx, dword ptr [rbp+var_50+4]
0x140003b79  jnz     short loc_140003B80
0x140003b7b  cmp     edi, dword ptr [rbp+var_50+4]
0x140003b7e  jz      short loc_140003BCD
0x140003b80  mov     r8d, r15d
0x140003b83  mov     rdx, rsi
0x140003b86  mov     ecx, edi
0x140003b88  call    BfspBsdLogWrite
0x140003b8d  mov     edx, eax
0x140003b8f  test    eax, eax
0x140003b91  js      short loc_140003BCD
0x140003b93  add     edi, r15d
0x140003b96  test    r14, r14
0x140003b99  jz      short loc_140003BB4
0x140003b9b  mov     r8d, 0Ch
0x140003ba1  mov     rdx, r14
0x140003ba4  mov     ecx, edi
0x140003ba6  call    BfspBsdLogWrite
0x140003bab  mov     edx, eax
0x140003bad  test    eax, eax
0x140003baf  js      short loc_140003BCD
0x140003bb1  add     edi, 0Ch
0x140003bb4  mov     r8d, 14h
0x140003bba  mov     dword ptr [rbp+var_50+0Ch], edi
0x140003bbd  lea     rdx, [rbp+var_50]
0x140003bc1  mov     [rbp+var_40], ebx
0x140003bc4  xor     ecx, ecx
0x140003bc6  call    BfspBsdLogWrite
0x140003bcb  mov     edx, eax
0x140003bcd  mov     eax, edx
0x140003bcf  mov     rcx, [rbp+var_10]
0x140003bd3  xor     rcx, rsp; StackCookie
0x140003bd6  call    __security_check_cookie
0x140003bdb  mov     rbx, [rsp+70h+arg_0]
0x140003be3  add     rsp, 70h
0x140003be7  pop     r15
0x140003be9  pop     r14
0x140003beb  pop     rdi
0x140003bec  pop     rsi
0x140003bed  pop     rbp
0x140003bee  retn
```
