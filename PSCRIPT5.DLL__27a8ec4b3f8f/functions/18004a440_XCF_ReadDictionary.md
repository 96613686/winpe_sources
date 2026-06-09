# XCF_ReadDictionary

- ea: `0x18004a440`
- end: `0x18004a675`
- name: `XCF_ReadDictionary`
- size: `565`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180048608`
- `0x18004a050`

## callees

- `0x180001f20`
- `0x180002938`
- `0x180048958`
- `0x18004a440`
- `0x18004f8e4`
- `0x18004f980`
- `0x18004fc58`

## pseudocode

```c
__int64 __fastcall XCF_ReadDictionary(__int64 a1)
{
  unsigned __int8 *v1; // rsi
  __int64 result; // rax
  int v4; // ebp
  unsigned int NextOperator; // eax
  unsigned __int16 v6; // dx
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
  unsigned __int16 v17[8]; // [rsp+30h] [rbp-F8h] BYREF
  _DWORD v18[48]; // [rsp+40h] [rbp-E8h] BYREF

  v1 = *(unsigned __int8 **)(a1 + 14160);
  result = 0;
  v17[0] = 0;
  if ( (unsigned __int64)v1 < *(_QWORD *)(a1 + 14152) )
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
        while ( v4 || v6 == 31 )
        {
          switch ( v6 )
          {
            case 0x1Fu:
              v4 = 1;
              if ( v7 )
              {
                XCF_SaveDictArgumentList(a1, (_DWORD *)(a1 + 4 * (*(int *)(a1 + 6840) + 1711LL)), v1, v7);
                *(_DWORD *)(a1 + 6840) += v7;
              }
              break;
            case 0xEu:
              v4 = 0;
              break;
            case 0x10u:
              memset_0(v18, 0, sizeof(v18));
              if ( v7 )
              {
                if ( v7 > 48 )
                  XCF_FatalErrorHandler((_JBTYPE *)a1, 24);
                XCF_SaveDictArgumentList(a1, v18, v1, v7);
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
          v1 = *(unsigned __int8 **)(a1 + 14160);
          v16 = XCF_FindNextOperator(a1, v17, 1);
          v6 = v17[0];
          v7 = v16;
        }
        result = SaveDictEntry(a1, v6, 0, *(_DWORD *)(a1 + 6840), 1);
      }
      else
      {
        result = SaveDictEntry(a1, v17[0], (__int64)v1, NextOperator, 0);
      }
      v1 = *(unsigned __int8 **)(a1 + 14160);
    }
    while ( (unsigned __int64)v1 < *(_QWORD *)(a1 + 14152) );
  }
  return result;
}

```

## disassembly

```asm
0x18004a440  mov     [rsp+arg_8], rbx
0x18004a445  mov     [rsp+arg_10], rbp
0x18004a44a  push    rsi
0x18004a44b  push    rdi
0x18004a44c  push    r15
0x18004a44e  sub     rsp, 110h
0x18004a455  mov     rax, cs:__security_cookie
0x18004a45c  xor     rax, rsp
0x18004a45f  mov     [rsp+128h+var_28], rax
0x18004a467  mov     rsi, [rcx+3750h]
0x18004a46e  xor     eax, eax
0x18004a470  mov     rbx, rcx
0x18004a473  mov     [rsp+128h+var_F8], ax
0x18004a478  cmp     rsi, [rcx+3748h]
0x18004a47f  jnb     loc_18004A641
0x18004a485  xor     ebp, ebp
0x18004a487  lea     r15d, [rax+1]
0x18004a48b  mov     r8d, r15d
0x18004a48e  lea     rdx, [rsp+128h+var_F8]
0x18004a493  mov     rcx, rbx
0x18004a496  call    XCF_FindNextOperator
0x18004a49b  movzx   edx, [rsp+128h+var_F8]
0x18004a4a0  mov     edi, eax
0x18004a4a2  cmp     dx, 1Fh
0x18004a4a6  jz      short loc_18004A4BB
0x18004a4a8  mov     [rsp+128h+var_108], 0
0x18004a4b0  mov     r9d, eax
0x18004a4b3  mov     r8, rsi
0x18004a4b6  jmp     loc_18004A625
0x18004a4bb  mov     dword ptr [rbx+1AB8h], 0
0x18004a4c5  test    ebp, ebp
0x18004a4c7  jnz     short loc_18004A4D3
0x18004a4c9  cmp     dx, 1Fh
0x18004a4cd  jnz     loc_18004A616
0x18004a4d3  cmp     dx, 1Fh
0x18004a4d7  jnz     short loc_18004A516
0x18004a4d9  mov     ebp, r15d
0x18004a4dc  test    edi, edi
0x18004a4de  jz      loc_18004A5F3
0x18004a4e4  movsxd  rax, dword ptr [rbx+1AB8h]
0x18004a4eb  mov     r9d, edi
0x18004a4ee  add     rax, 6AFh
0x18004a4f4  mov     [rsp+128h+var_108], 0
0x18004a4fc  mov     r8, rsi
0x18004a4ff  mov     rcx, rbx
0x18004a502  lea     rdx, [rbx+rax*4]
0x18004a506  call    XCF_SaveDictArgumentList
0x18004a50b  add     [rbx+1AB8h], edi
0x18004a511  jmp     loc_18004A5F3
0x18004a516  cmp     dx, 0Eh
0x18004a51a  jnz     short loc_18004A523
0x18004a51c  xor     ebp, ebp
0x18004a51e  jmp     loc_18004A5F3
0x18004a523  cmp     dx, 10h
0x18004a527  jnz     loc_18004A5F3
0x18004a52d  xor     edx, edx; Val
0x18004a52f  lea     rcx, [rsp+128h+var_E8]; void *
0x18004a534  mov     r8d, 0C0h; Size
0x18004a53a  call    memset_0
0x18004a53f  test    edi, edi
0x18004a541  jz      loc_18004A5F3
0x18004a547  mov     rcx, rbx
0x18004a54a  cmp     edi, 30h ; '0'
0x18004a54d  jg      loc_18004A66A
0x18004a553  mov     r9d, edi
0x18004a556  mov     [rsp+128h+var_108], 0
0x18004a55e  mov     r8, rsi
0x18004a561  lea     rdx, [rsp+128h+var_E8]
0x18004a566  call    XCF_SaveDictArgumentList
0x18004a56b  movsxd  rax, edi
0x18004a56e  xor     r8d, r8d
0x18004a571  movsx   r9d, [rsp+rax*4+128h+var_EA]
0x18004a577  mov     esi, r9d
0x18004a57a  test    r9d, r9d
0x18004a57d  jle     short loc_18004A5F3
0x18004a57f  movsxd  rax, dword ptr [rbx+1AB8h]
0x18004a586  mov     r11d, [rsp+r8*4+128h+var_E8]
0x18004a58b  mov     [rbx+rax*4+1ABCh], r11d
0x18004a593  mov     r10d, [rbx+1AB8h]
0x18004a59a  mov     eax, [rbx+1E8h]
0x18004a5a0  inc     r10d
0x18004a5a3  sub     eax, r15d
0x18004a5a6  mov     [rbx+1AB8h], r10d
0x18004a5ad  test    eax, eax
0x18004a5af  jle     short loc_18004A5EB
0x18004a5b1  xor     edi, edi
0x18004a5b3  movsxd  rax, esi
0x18004a5b6  add     edi, r15d
0x18004a5b9  add     esi, r15d
0x18004a5bc  mov     edx, [rsp+rax*4+128h+var_E8]
0x18004a5c0  movsxd  rax, r10d
0x18004a5c3  add     edx, r11d
0x18004a5c6  mov     [rbx+rax*4+1ABCh], edx
0x18004a5cd  mov     r10d, [rbx+1AB8h]
0x18004a5d4  inc     r10d
0x18004a5d7  mov     [rbx+1AB8h], r10d
0x18004a5de  mov     eax, [rbx+1E8h]
0x18004a5e4  sub     eax, r15d
0x18004a5e7  cmp     edi, eax
0x18004a5e9  jl      short loc_18004A5B3
0x18004a5eb  add     r8d, r15d
0x18004a5ee  cmp     r8d, r9d
0x18004a5f1  jl      short loc_18004A57F
0x18004a5f3  mov     rsi, [rbx+3750h]
0x18004a5fa  lea     rdx, [rsp+128h+var_F8]
0x18004a5ff  mov     r8d, r15d
0x18004a602  mov     rcx, rbx
0x18004a605  call    XCF_FindNextOperator
0x18004a60a  movzx   edx, [rsp+128h+var_F8]
0x18004a60f  mov     edi, eax
0x18004a611  jmp     loc_18004A4C5
0x18004a616  mov     r9d, [rbx+1AB8h]
0x18004a61d  xor     r8d, r8d
0x18004a620  mov     [rsp+128h+var_108], r15d
0x18004a625  mov     rcx, rbx
0x18004a628  call    SaveDictEntry
0x18004a62d  mov     rsi, [rbx+3750h]
0x18004a634  cmp     rsi, [rbx+3748h]
0x18004a63b  jb      loc_18004A48B
0x18004a641  mov     rcx, [rsp+128h+var_28]
0x18004a649  xor     rcx, rsp; StackCookie
0x18004a64c  call    __security_check_cookie
0x18004a651  lea     r11, [rsp+128h+var_18]
0x18004a659  mov     rbx, [r11+28h]
0x18004a65d  mov     rbp, [r11+30h]
0x18004a661  mov     rsp, r11
0x18004a664  pop     r15
0x18004a666  pop     rdi
0x18004a667  pop     rsi
0x18004a668  retn
0x18004a66a  mov     edx, 18h
0x18004a66f  call    XCF_FatalErrorHandler
```
