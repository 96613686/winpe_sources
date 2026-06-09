# ValidateDSAKeyBlobV1Format

- ea: `0x18001c464`
- end: `0x18001c60e`
- name: `ValidateDSAKeyBlobV1Format`
- size: `426`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, const wchar_t *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001b36c`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18001c464`
- `0x18007f765`

## string_xrefs

- `0x18001c49c`: `onecore\ds\security\cryptoapi\ncrypt\common\keyblobvalidate.c`
- `0x18001c5d0`: `onecore\ds\security\cryptoapi\ncrypt\common\keyblobvalidate.c`

## pseudocode

```c
__int64 __fastcall ValidateDSAKeyBlobV1Format(_DWORD *a1, unsigned int a2, const wchar_t *a3, int *a4)
{
  int v4; // r15d
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  int v13; // ebx

  v4 = 0;
  if ( a1 && a3 )
  {
    if ( a2 >= 0x34 )
    {
      v11 = (unsigned int)a1[1];
      if ( (v11 & 7) != 0 || (unsigned int)(v11 - 64) > 0x40 )
      {
        v9 = 123;
        goto LABEL_5;
      }
      v12 = 3 * v11;
      if ( v12 > 0xFFFFFFFF )
      {
        v9 = 131;
        goto LABEL_5;
      }
      v13 = v12 + 52;
      if ( (int)v12 + 52 >= (unsigned int)v12 )
      {
        if ( (int)v12 + 72 >= (unsigned int)(v12 + 52) )
        {
          if ( !wcscmp_0(a3, L"DSAPUBLICBLOB") || !wcscmp_0(a3, L"PUBLICBLOB") )
          {
            if ( *a1 != 1112560452 || a2 != v13 )
            {
              v9 = 156;
              goto LABEL_5;
            }
          }
          else
          {
            if ( wcscmp_0(a3, L"DSAPRIVATEBLOB") && wcscmp_0(a3, L"PRIVATEBLOB") )
            {
              v9 = 175;
              goto LABEL_5;
            }
            v4 = 1;
            if ( *a1 != 1448104772 || a2 != v13 + 20 )
            {
              v9 = 168;
              goto LABEL_5;
            }
          }
          v10 = 0;
          goto LABEL_30;
        }
        v9 = 145;
      }
      else
      {
        v9 = 138;
      }
    }
    else
    {
      v9 = 111;
    }
LABEL_5:
    v10 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\keyblobvalidate.c", v9);
    goto LABEL_30;
  }
  v10 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\keyblobvalidate.c",
      104);
LABEL_30:
  *a4 = v4;
  return v10;
}

```

## disassembly

```asm
0x18001c464  push    rbx
0x18001c466  push    rbp
0x18001c467  push    rsi
0x18001c468  push    rdi
0x18001c469  push    r12
0x18001c46b  push    r14
0x18001c46d  push    r15
0x18001c46f  sub     rsp, 40h
0x18001c473  xor     r15d, r15d
0x18001c476  mov     r12, r9
0x18001c479  mov     rdi, r8
0x18001c47c  mov     ebp, edx
0x18001c47e  mov     rsi, rcx
0x18001c481  test    rcx, rcx
0x18001c484  jz      loc_18001C5AE
0x18001c48a  test    r8, r8
0x18001c48d  jz      loc_18001C5AE
0x18001c493  cmp     edx, 34h ; '4'
0x18001c496  jnb     short loc_18001C4BE
0x18001c498  lea     r9d, [r15+6Fh]
0x18001c49c  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c4a3  mov     ecx, 0C000000Dh
0x18001c4a8  lea     rdx, aStatus; "Status"
0x18001c4af  mov     ebx, 0C000000Dh
0x18001c4b4  call    DebugTraceError
0x18001c4b9  jmp     loc_18001C5F8
0x18001c4be  mov     ecx, [rcx+4]
0x18001c4c1  test    cl, 7
0x18001c4c4  jnz     loc_18001C5A3
0x18001c4ca  lea     eax, [rcx-40h]
0x18001c4cd  cmp     eax, 40h ; '@'
0x18001c4d0  ja      loc_18001C5A3
0x18001c4d6  lea     rcx, [rcx+rcx*2]
0x18001c4da  mov     eax, 0FFFFFFFFh
0x18001c4df  cmp     rcx, rax
0x18001c4e2  ja      loc_18001C598
0x18001c4e8  lea     ebx, [rcx+34h]
0x18001c4eb  cmp     ebx, ecx
0x18001c4ed  jnb     short loc_18001C4F7
0x18001c4ef  mov     r9d, 8Ah
0x18001c4f5  jmp     short loc_18001C49C
0x18001c4f7  lea     r14d, [rbx+14h]
0x18001c4fb  cmp     r14d, ebx
0x18001c4fe  jnb     short loc_18001C508
0x18001c500  mov     r9d, 91h
0x18001c506  jmp     short loc_18001C49C
0x18001c508  lea     rdx, aDsapublicblob; "DSAPUBLICBLOB"
0x18001c50f  mov     rcx, rdi; String1
0x18001c512  call    wcscmp_0
0x18001c517  test    eax, eax
0x18001c519  jz      short loc_18001C57D
0x18001c51b  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18001c522  mov     rcx, rdi; String1
0x18001c525  call    wcscmp_0
0x18001c52a  test    eax, eax
0x18001c52c  jz      short loc_18001C57D
0x18001c52e  lea     rdx, aDsaprivateblob; "DSAPRIVATEBLOB"
0x18001c535  mov     rcx, rdi; String1
0x18001c538  call    wcscmp_0
0x18001c53d  test    eax, eax
0x18001c53f  jz      short loc_18001C55F
0x18001c541  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18001c548  mov     rcx, rdi; String1
0x18001c54b  call    wcscmp_0
0x18001c550  test    eax, eax
0x18001c552  jz      short loc_18001C55F
0x18001c554  mov     r9d, 0AFh
0x18001c55a  jmp     loc_18001C49C
0x18001c55f  cmp     dword ptr [rsi], 56505344h
0x18001c565  mov     r15d, 1
0x18001c56b  jnz     short loc_18001C572
0x18001c56d  cmp     ebp, r14d
0x18001c570  jz      short loc_18001C589
0x18001c572  mov     r9d, 0A8h
0x18001c578  jmp     loc_18001C49C
0x18001c57d  cmp     dword ptr [rsi], 42505344h
0x18001c583  jnz     short loc_18001C58D
0x18001c585  cmp     ebp, ebx
0x18001c587  jnz     short loc_18001C58D
0x18001c589  xor     ebx, ebx
0x18001c58b  jmp     short loc_18001C5F8
0x18001c58d  mov     r9d, 9Ch
0x18001c593  jmp     loc_18001C49C
0x18001c598  mov     r9d, 83h
0x18001c59e  jmp     loc_18001C49C
0x18001c5a3  mov     r9d, 7Bh ; '{'
0x18001c5a9  jmp     loc_18001C49C
0x18001c5ae  mov     ebx, 0C000000Dh
0x18001c5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5ba  lea     rax, WPP_GLOBAL_Control
0x18001c5c1  cmp     rcx, rax
0x18001c5c4  jz      short loc_18001C5F8
0x18001c5c6  test    byte ptr [rcx+1Ch], 1
0x18001c5ca  jz      short loc_18001C5F8
0x18001c5cc  mov     rcx, [rcx+10h]
0x18001c5d0  lea     rax, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c5d7  mov     [rsp+78h+var_48], 68h ; 'h'
0x18001c5df  lea     r9, aStatus; "Status"
0x18001c5e6  mov     [rsp+78h+var_50], rax
0x18001c5eb  mov     [rsp+78h+var_58], 0C000000Dh
0x18001c5f3  call    WPP_SF_sDsd
0x18001c5f8  mov     [r12], r15d
0x18001c5fc  mov     eax, ebx
0x18001c5fe  add     rsp, 40h
0x18001c602  pop     r15
0x18001c604  pop     r14
0x18001c606  pop     r12
0x18001c608  pop     rdi
0x18001c609  pop     rsi
0x18001c60a  pop     rbp
0x18001c60b  pop     rbx
0x18001c60c  retn
```
