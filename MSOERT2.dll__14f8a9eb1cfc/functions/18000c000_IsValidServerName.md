# IsValidServerName

- ea: `0x18000c000`
- end: `0x18000c17c`
- name: `IsValidServerName`
- size: `380`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000cd10`
- `0x18000ce20`

## callees

- `0x180001900`
- `0x18000c000`
- `0x18000fc40`
- `0x180012f8e`
- `0x180012fc0`
- `0x180014010`

## import_xrefs

- `KERNEL32!IsDBCSLeadByte` at `0x18000c0e8`
- `KERNEL32!IsDBCSLeadByte` at `0x18000c0e8`
- `USER32!CharNextA` at `0x18000c145`
- `USER32!CharNextA` at `0x18000c145`
- `WS2_32!WSAStringToAddressA` at `0x18000c080`
- `WS2_32!WSAStringToAddressA` at `0x18000c0af`
- `WS2_32!WSAStringToAddressA` at `0x18000c080`
- `WS2_32!WSAStringToAddressA` at `0x18000c0af`

## pseudocode

```c
_BOOL8 __fastcall IsValidServerName(const CHAR *Src)
{
  BOOL v1; // edi
  LPSTR v2; // rbx
  CHAR *v3; // rsi
  int v4; // edi
  CHAR v5; // cl
  int v6; // eax
  int AddressLength[4]; // [rsp+30h] [rbp-C8h] BYREF
  sockaddr Address; // [rsp+40h] [rbp-B8h] BYREF

  v1 = 0;
  v2 = (LPSTR)Src;
  if ( Src && !(unsigned int)FIsEmptyA(Src) )
  {
    v3 = (CHAR *)PszDupA(v2);
    if ( !v3
      || ((memset_0(&Address, 0, 0x80u), AddressLength[0] = 128, WSAStringToAddressA(v3, 2, 0, &Address, AddressLength))
        ? (AddressLength[0] = 128, v1 = WSAStringToAddressA(v3, 23, 0, &Address, AddressLength) == 0)
        : (v1 = 1),
          ((void (__fastcall *)(LPMALLOC, CHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v3),
          !v1) )
    {
      v4 = 0;
      if ( !*v2 )
        return 0;
      while ( 1 )
      {
        if ( v4 == -1 )
          return v4 == 2;
        if ( IsDBCSLeadByte(*v2) )
          break;
        v5 = *v2;
        if ( *v2 == 46 )
        {
          v6 = 2;
        }
        else if ( v5 == 45 )
        {
          v6 = 3;
        }
        else if ( (unsigned __int8)(v5 - 65) <= 0x19u || (unsigned __int8)(v5 - 97) <= 0x19u )
        {
          v6 = 0;
        }
        else
        {
          if ( (unsigned __int8)(v5 - 48) > 9u )
            break;
          v6 = 1;
        }
        v4 = *((_DWORD *)qword_180016D50 + 3 * v6 + v4);
LABEL_22:
        v2 = CharNextA(v2);
        if ( !*v2 )
          return v4 == 2;
      }
      v4 = -1;
      goto LABEL_22;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000c000  push    rbx
0x18000c002  push    rbp
0x18000c003  push    rsi
0x18000c004  push    rdi
0x18000c005  sub     rsp, 0D8h
0x18000c00c  mov     rax, cs:__security_cookie
0x18000c013  xor     rax, rsp
0x18000c016  mov     [rsp+0F8h+var_38], rax
0x18000c01e  xor     edi, edi
0x18000c020  mov     rbx, rcx
0x18000c023  test    rcx, rcx
0x18000c026  jz      loc_18000C15E
0x18000c02c  call    FIsEmptyA
0x18000c031  test    eax, eax
0x18000c033  jnz     loc_18000C15E
0x18000c039  mov     rcx, rbx; Src
0x18000c03c  call    PszDupA
0x18000c041  lea     ebp, [rdi+1]
0x18000c044  mov     rsi, rax
0x18000c047  test    rax, rax
0x18000c04a  jz      loc_18000C0D8
0x18000c050  xor     edx, edx; Val
0x18000c052  lea     r8d, [rbp+7Fh]; Size
0x18000c056  lea     rcx, [rsp+0F8h+Address]; void *
0x18000c05b  call    memset_0
0x18000c060  lea     rax, [rsp+0F8h+AddressLength]
0x18000c065  mov     [rsp+0F8h+AddressLength], 80h
0x18000c06d  lea     r9, [rsp+0F8h+Address]; lpAddress
0x18000c072  mov     [rsp+0F8h+lpAddressLength], rax; lpAddressLength
0x18000c077  xor     r8d, r8d; lpProtocolInfo
0x18000c07a  lea     edx, [rdi+2]; AddressFamily
0x18000c07d  mov     rcx, rsi; AddressString
0x18000c080  call    cs:__imp_WSAStringToAddressA
0x18000c086  test    eax, eax
0x18000c088  jnz     short loc_18000C08E
0x18000c08a  mov     edi, ebp
0x18000c08c  jmp     short loc_18000C0BA
0x18000c08e  xor     r8d, r8d; lpProtocolInfo
0x18000c091  mov     [rsp+0F8h+AddressLength], 80h
0x18000c099  lea     rax, [rsp+0F8h+AddressLength]
0x18000c09e  mov     rcx, rsi; AddressString
0x18000c0a1  lea     r9, [rsp+0F8h+Address]; lpAddress
0x18000c0a6  mov     [rsp+0F8h+lpAddressLength], rax; lpAddressLength
0x18000c0ab  lea     edx, [r8+17h]; AddressFamily
0x18000c0af  call    cs:__imp_WSAStringToAddressA
0x18000c0b5  test    eax, eax
0x18000c0b7  cmovz   edi, ebp
0x18000c0ba  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000c0c1  mov     rdx, rsi
0x18000c0c4  mov     rax, [rcx]
0x18000c0c7  mov     rax, [rax+28h]
0x18000c0cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0d0  test    edi, edi
0x18000c0d2  jnz     loc_18000C15E
0x18000c0d8  xor     edi, edi
0x18000c0da  cmp     [rbx], dil
0x18000c0dd  jz      short loc_18000C15C
0x18000c0df  or      esi, 0FFFFFFFFh
0x18000c0e2  cmp     edi, esi
0x18000c0e4  jz      short loc_18000C153
0x18000c0e6  mov     cl, [rbx]; TestChar
0x18000c0e8  call    cs:__imp_IsDBCSLeadByte
0x18000c0ee  test    eax, eax
0x18000c0f0  jnz     short loc_18000C140
0x18000c0f2  mov     cl, [rbx]
0x18000c0f4  cmp     cl, 2Eh ; '.'
0x18000c0f7  jnz     short loc_18000C100
0x18000c0f9  mov     eax, 2
0x18000c0fe  jmp     short loc_18000C128
0x18000c100  cmp     cl, 2Dh ; '-'
0x18000c103  jnz     short loc_18000C10C
0x18000c105  mov     eax, 3
0x18000c10a  jmp     short loc_18000C128
0x18000c10c  lea     eax, [rcx-41h]
0x18000c10f  cmp     al, 19h
0x18000c111  jbe     short loc_18000C126
0x18000c113  lea     eax, [rcx-61h]
0x18000c116  cmp     al, 19h
0x18000c118  jbe     short loc_18000C126
0x18000c11a  sub     cl, 30h ; '0'
0x18000c11d  cmp     cl, 9
0x18000c120  ja      short loc_18000C140
0x18000c122  mov     eax, ebp
0x18000c124  jmp     short loc_18000C128
0x18000c126  xor     eax, eax
0x18000c128  cdqe
0x18000c12a  lea     rcx, [rax+rax*2]
0x18000c12e  movsxd  rax, edi
0x18000c131  add     rcx, rax
0x18000c134  lea     rdi, qword_180016D50
0x18000c13b  mov     edi, [rdi+rcx*4]
0x18000c13e  jmp     short loc_18000C142
0x18000c140  mov     edi, esi
0x18000c142  mov     rcx, rbx; lpsz
0x18000c145  call    cs:__imp_CharNextA
0x18000c14b  mov     rbx, rax
0x18000c14e  cmp     byte ptr [rax], 0
0x18000c151  jnz     short loc_18000C0E2
0x18000c153  cmp     edi, 2
0x18000c156  jnz     short loc_18000C15C
0x18000c158  mov     edi, ebp
0x18000c15a  jmp     short loc_18000C15E
0x18000c15c  xor     edi, edi
0x18000c15e  mov     eax, edi
0x18000c160  mov     rcx, [rsp+0F8h+var_38]
0x18000c168  xor     rcx, rsp; StackCookie
0x18000c16b  call    __security_check_cookie
0x18000c170  add     rsp, 0D8h
0x18000c177  pop     rdi
0x18000c178  pop     rsi
0x18000c179  pop     rbp
0x18000c17a  pop     rbx
0x18000c17b  retn
```
