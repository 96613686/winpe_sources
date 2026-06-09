# XCF_ReadDictionary

- ea: `0x180048bd0`
- end: `0x180048e04`
- name: `XCF_ReadDictionary`
- size: `564`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180046ce0`
- `0x1800487e0`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x18004702c`
- `0x180048bd0`
- `0x18004e048`
- `0x18004e0e0`
- `0x18004e3b4`

## pseudocode

```c
__int64 __fastcall XCF_ReadDictionary(__int64 a1)
{
  unsigned __int64 v1; // rsi
  __int64 result; // rax
  int v4; // ebp
  int NextOperator; // eax
  int v6; // edx
  int v7; // edi
  __int64 v8; // r8
  int v9; // r9d
  int v10; // esi
  int v11; // r11d
  int v12; // r10d
  int v13; // eax
  int v14; // edi
  __int64 v15; // rax
  int v16; // eax
  _WORD v17[8]; // [rsp+30h] [rbp-F8h] BYREF
  _DWORD v18[48]; // [rsp+40h] [rbp-E8h] BYREF

  v1 = *(_QWORD *)(a1 + 14160);
  result = 0;
  v17[0] = 0;
  if ( v1 < *(_QWORD *)(a1 + 14152) )
  {
    v4 = 0;
    do
    {
      NextOperator = XCF_FindNextOperator(a1, v17, 1);
      v6 = v17[0];
      v7 = NextOperator;
      if ( v17[0] == 31 )
      {
        *(_DWORD *)(a1 + 6840) = 0;
        while ( v4 || (_WORD)v6 == 31 )
        {
          switch ( (_WORD)v6 )
          {
            case 0x1F:
              v4 = 1;
              if ( v7 )
              {
                XCF_SaveDictArgumentList(a1, a1 + 4 * (*(_DWORD *)(a1 + 6840) + 1711), v1, v7, 0);
                *(_DWORD *)(a1 + 6840) += v7;
              }
              break;
            case 0xE:
              v4 = 0;
              break;
            case 0x10:
              memset_0(v18, 0, sizeof(v18));
              if ( v7 )
              {
                if ( v7 > 48 )
                  XCF_FatalErrorHandler(a1, 24);
                XCF_SaveDictArgumentList(a1, (unsigned int)v18, v1, v7, 0);
                v8 = 0;
                v9 = (__int16)v17[2 * v7 + 7];
                v10 = v9;
                if ( v9 > 0 )
                {
                  do
                  {
                    v11 = v18[v8];
                    *(_DWORD *)(a1 + 4LL * *(int *)(a1 + 6840) + 6844) = v11;
                    v12 = *(_DWORD *)(a1 + 6840) + 1;
                    v13 = *(_DWORD *)(a1 + 488) - 1;
                    *(_DWORD *)(a1 + 6840) = v12;
                    if ( v13 > 0 )
                    {
                      v14 = 0;
                      do
                      {
                        v15 = v10;
                        ++v14;
                        ++v10;
                        *(_DWORD *)(a1 + 4LL * v12 + 6844) = v11 + v18[v15];
                        v12 = *(_DWORD *)(a1 + 6840) + 1;
                        *(_DWORD *)(a1 + 6840) = v12;
                      }
                      while ( v14 < *(_DWORD *)(a1 + 488) - 1 );
                    }
                    v8 = (unsigned int)(v8 + 1);
                  }
                  while ( (int)v8 < v9 );
                }
              }
              break;
          }
          v1 = *(_QWORD *)(a1 + 14160);
          v16 = XCF_FindNextOperator(a1, v17, 1);
          v6 = v17[0];
          v7 = v16;
        }
        result = SaveDictEntry(a1, v6, 0, *(_DWORD *)(a1 + 6840), 1);
      }
      else
      {
        result = SaveDictEntry(a1, v17[0], v1, NextOperator, 0);
      }
      v1 = *(_QWORD *)(a1 + 14160);
    }
    while ( v1 < *(_QWORD *)(a1 + 14152) );
  }
  return result;
}

```

## disassembly

```asm
0x180048bd0  mov     [rsp+arg_8], rbx
0x180048bd5  mov     [rsp+arg_10], rbp
0x180048bda  push    rsi
0x180048bdb  push    rdi
0x180048bdc  push    r15
0x180048bde  sub     rsp, 110h
0x180048be5  mov     rax, cs:__security_cookie
0x180048bec  xor     rax, rsp
0x180048bef  mov     [rsp+128h+var_28], rax
0x180048bf7  mov     rsi, [rcx+3750h]
0x180048bfe  xor     eax, eax
0x180048c00  mov     rbx, rcx
0x180048c03  mov     [rsp+128h+var_F8], ax
0x180048c08  cmp     rsi, [rcx+3748h]
0x180048c0f  jnb     loc_180048DD1
0x180048c15  xor     ebp, ebp
0x180048c17  lea     r15d, [rax+1]
0x180048c1b  mov     r8d, r15d
0x180048c1e  lea     rdx, [rsp+128h+var_F8]
0x180048c23  mov     rcx, rbx
0x180048c26  call    XCF_FindNextOperator
0x180048c2b  movzx   edx, [rsp+128h+var_F8]
0x180048c30  mov     edi, eax
0x180048c32  cmp     dx, 1Fh
0x180048c36  jz      short loc_180048C4B
0x180048c38  mov     [rsp+128h+var_108], 0
0x180048c40  mov     r9d, eax
0x180048c43  mov     r8, rsi
0x180048c46  jmp     loc_180048DB5
0x180048c4b  mov     dword ptr [rbx+1AB8h], 0
0x180048c55  test    ebp, ebp
0x180048c57  jnz     short loc_180048C63
0x180048c59  cmp     dx, 1Fh
0x180048c5d  jnz     loc_180048DA6
0x180048c63  cmp     dx, 1Fh
0x180048c67  jnz     short loc_180048CA6
0x180048c69  mov     ebp, r15d
0x180048c6c  test    edi, edi
0x180048c6e  jz      loc_180048D83
0x180048c74  movsxd  rax, dword ptr [rbx+1AB8h]
0x180048c7b  mov     r9d, edi
0x180048c7e  add     rax, 6AFh
0x180048c84  mov     [rsp+128h+var_108], 0
0x180048c8c  mov     r8, rsi
0x180048c8f  mov     rcx, rbx
0x180048c92  lea     rdx, [rbx+rax*4]
0x180048c96  call    XCF_SaveDictArgumentList
0x180048c9b  add     [rbx+1AB8h], edi
0x180048ca1  jmp     loc_180048D83
0x180048ca6  cmp     dx, 0Eh
0x180048caa  jnz     short loc_180048CB3
0x180048cac  xor     ebp, ebp
0x180048cae  jmp     loc_180048D83
0x180048cb3  cmp     dx, 10h
0x180048cb7  jnz     loc_180048D83
0x180048cbd  xor     edx, edx; Val
0x180048cbf  lea     rcx, [rsp+128h+var_E8]; void *
0x180048cc4  mov     r8d, 0C0h; Size
0x180048cca  call    memset_0
0x180048ccf  test    edi, edi
0x180048cd1  jz      loc_180048D83
0x180048cd7  mov     rcx, rbx
0x180048cda  cmp     edi, 30h ; '0'
0x180048cdd  jg      loc_180048DF9
0x180048ce3  mov     r9d, edi
0x180048ce6  mov     [rsp+128h+var_108], 0
0x180048cee  mov     r8, rsi
0x180048cf1  lea     rdx, [rsp+128h+var_E8]
0x180048cf6  call    XCF_SaveDictArgumentList
0x180048cfb  movsxd  rax, edi
0x180048cfe  xor     r8d, r8d
0x180048d01  movsx   r9d, [rsp+rax*4+128h+var_EA]
0x180048d07  mov     esi, r9d
0x180048d0a  test    r9d, r9d
0x180048d0d  jle     short loc_180048D83
0x180048d0f  movsxd  rax, dword ptr [rbx+1AB8h]
0x180048d16  mov     r11d, [rsp+r8*4+128h+var_E8]
0x180048d1b  mov     [rbx+rax*4+1ABCh], r11d
0x180048d23  mov     r10d, [rbx+1AB8h]
0x180048d2a  mov     eax, [rbx+1E8h]
0x180048d30  inc     r10d
0x180048d33  sub     eax, r15d
0x180048d36  mov     [rbx+1AB8h], r10d
0x180048d3d  test    eax, eax
0x180048d3f  jle     short loc_180048D7B
0x180048d41  xor     edi, edi
0x180048d43  movsxd  rax, esi
0x180048d46  add     edi, r15d
0x180048d49  add     esi, r15d
0x180048d4c  mov     edx, [rsp+rax*4+128h+var_E8]
0x180048d50  movsxd  rax, r10d
0x180048d53  add     edx, r11d
0x180048d56  mov     [rbx+rax*4+1ABCh], edx
0x180048d5d  mov     r10d, [rbx+1AB8h]
0x180048d64  inc     r10d
0x180048d67  mov     [rbx+1AB8h], r10d
0x180048d6e  mov     eax, [rbx+1E8h]
0x180048d74  sub     eax, r15d
0x180048d77  cmp     edi, eax
0x180048d79  jl      short loc_180048D43
0x180048d7b  add     r8d, r15d
0x180048d7e  cmp     r8d, r9d
0x180048d81  jl      short loc_180048D0F
0x180048d83  mov     rsi, [rbx+3750h]
0x180048d8a  lea     rdx, [rsp+128h+var_F8]
0x180048d8f  mov     r8d, r15d
0x180048d92  mov     rcx, rbx
0x180048d95  call    XCF_FindNextOperator
0x180048d9a  movzx   edx, [rsp+128h+var_F8]
0x180048d9f  mov     edi, eax
0x180048da1  jmp     loc_180048C55
0x180048da6  mov     r9d, [rbx+1AB8h]
0x180048dad  xor     r8d, r8d
0x180048db0  mov     [rsp+128h+var_108], r15d
0x180048db5  mov     rcx, rbx
0x180048db8  call    SaveDictEntry
0x180048dbd  mov     rsi, [rbx+3750h]
0x180048dc4  cmp     rsi, [rbx+3748h]
0x180048dcb  jb      loc_180048C1B
0x180048dd1  mov     rcx, [rsp+128h+var_28]
0x180048dd9  xor     rcx, rsp; StackCookie
0x180048ddc  call    __security_check_cookie
0x180048de1  lea     r11, [rsp+128h+var_18]
0x180048de9  mov     rbx, [r11+28h]
0x180048ded  mov     rbp, [r11+30h]
0x180048df1  mov     rsp, r11
0x180048df4  pop     r15
0x180048df6  pop     rdi
0x180048df7  pop     rsi
0x180048df8  retn
0x180048df9  mov     edx, 18h
0x180048dfe  call    XCF_FatalErrorHandler
```
