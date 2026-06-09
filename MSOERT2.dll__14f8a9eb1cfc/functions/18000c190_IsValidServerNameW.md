# IsValidServerNameW

- ea: `0x18000c190`
- end: `0x18000c31f`
- name: `IsValidServerNameW`
- size: `399`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000cd90`
- `0x18000ce70`

## callees

- `0x1800010f0`
- `0x18000c190`
- `0x18000ffa0`
- `0x180012f8e`
- `0x180012fc0`
- `0x180014010`

## import_xrefs

- `USER32!CharNextW` at `0x18000c2e6`
- `USER32!CharNextW` at `0x18000c2e6`
- `WS2_32!WSAStringToAddressW` at `0x18000c210`
- `WS2_32!WSAStringToAddressW` at `0x18000c23f`
- `WS2_32!WSAStringToAddressW` at `0x18000c210`
- `WS2_32!WSAStringToAddressW` at `0x18000c23f`

## pseudocode

```c
_BOOL8 __fastcall IsValidServerNameW(const WCHAR *Src)
{
  BOOL v1; // ebx
  LPWSTR v2; // rdi
  WCHAR *v3; // rsi
  int v4; // ebx
  WCHAR v5; // cx
  int v6; // eax
  int AddressLength[4]; // [rsp+30h] [rbp-C8h] BYREF
  struct sockaddr Address; // [rsp+40h] [rbp-B8h] BYREF

  v1 = 0;
  v2 = (LPWSTR)Src;
  if ( Src && !(unsigned int)FIsEmptyW(Src) )
  {
    v3 = (WCHAR *)PszDupW(v2);
    if ( !v3
      || ((memset_0(&Address, 0, 0x80u), AddressLength[0] = 128, WSAStringToAddressW(v3, 2, 0, &Address, AddressLength))
        ? (AddressLength[0] = 128, v1 = WSAStringToAddressW(v3, 23, 0, &Address, AddressLength) == 0)
        : (v1 = 1),
          ((void (__fastcall *)(LPMALLOC, WCHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v3),
          !v1) )
    {
      v4 = 0;
      if ( !*v2 )
        return 0;
      while ( 1 )
      {
        if ( v4 == -1 )
          return v4 == 2;
        v5 = *v2;
        if ( *v2 > 0x7Fu )
          break;
        if ( v5 == 46 )
        {
          v6 = 2;
        }
        else if ( v5 == 45 )
        {
          v6 = 3;
        }
        else if ( (unsigned __int16)(v5 - 65) <= 0x19u || (unsigned __int16)(v5 - 97) <= 0x19u )
        {
          v6 = 0;
        }
        else
        {
          if ( (unsigned __int16)(v5 - 48) > 9u )
            break;
          v6 = 1;
        }
        v4 = *((_DWORD *)qword_180016D50 + 3 * v6 + v4);
LABEL_22:
        v2 = CharNextW(v2);
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
0x18000c190  push    rbx
0x18000c192  push    rbp
0x18000c193  push    rsi
0x18000c194  push    rdi
0x18000c195  sub     rsp, 0D8h
0x18000c19c  mov     rax, cs:__security_cookie
0x18000c1a3  xor     rax, rsp
0x18000c1a6  mov     [rsp+0F8h+var_38], rax
0x18000c1ae  xor     ebx, ebx
0x18000c1b0  mov     rdi, rcx
0x18000c1b3  test    rcx, rcx
0x18000c1b6  jz      loc_18000C301
0x18000c1bc  call    FIsEmptyW
0x18000c1c1  test    eax, eax
0x18000c1c3  jnz     loc_18000C301
0x18000c1c9  mov     rcx, rdi; Src
0x18000c1cc  call    PszDupW
0x18000c1d1  lea     ebp, [rbx+1]
0x18000c1d4  mov     rsi, rax
0x18000c1d7  test    rax, rax
0x18000c1da  jz      loc_18000C268
0x18000c1e0  xor     edx, edx; Val
0x18000c1e2  lea     r8d, [rbp+7Fh]; Size
0x18000c1e6  lea     rcx, [rsp+0F8h+Address]; void *
0x18000c1eb  call    memset_0
0x18000c1f0  lea     rax, [rsp+0F8h+AddressLength]
0x18000c1f5  mov     [rsp+0F8h+AddressLength], 80h
0x18000c1fd  lea     r9, [rsp+0F8h+Address]; lpAddress
0x18000c202  mov     [rsp+0F8h+lpAddressLength], rax; lpAddressLength
0x18000c207  xor     r8d, r8d; lpProtocolInfo
0x18000c20a  lea     edx, [rbx+2]; AddressFamily
0x18000c20d  mov     rcx, rsi; AddressString
0x18000c210  call    cs:__imp_WSAStringToAddressW
0x18000c216  test    eax, eax
0x18000c218  jnz     short loc_18000C21E
0x18000c21a  mov     ebx, ebp
0x18000c21c  jmp     short loc_18000C24A
0x18000c21e  xor     r8d, r8d; lpProtocolInfo
0x18000c221  mov     [rsp+0F8h+AddressLength], 80h
0x18000c229  lea     rax, [rsp+0F8h+AddressLength]
0x18000c22e  mov     rcx, rsi; AddressString
0x18000c231  lea     r9, [rsp+0F8h+Address]; lpAddress
0x18000c236  mov     [rsp+0F8h+lpAddressLength], rax; lpAddressLength
0x18000c23b  lea     edx, [r8+17h]; AddressFamily
0x18000c23f  call    cs:__imp_WSAStringToAddressW
0x18000c245  test    eax, eax
0x18000c247  cmovz   ebx, ebp
0x18000c24a  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000c251  mov     rdx, rsi
0x18000c254  mov     rax, [rcx]
0x18000c257  mov     rax, [rax+28h]
0x18000c25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c260  test    ebx, ebx
0x18000c262  jnz     loc_18000C301
0x18000c268  xor     ebx, ebx
0x18000c26a  xor     eax, eax
0x18000c26c  cmp     ax, [rdi]
0x18000c26f  jz      loc_18000C2FF
0x18000c275  or      esi, 0FFFFFFFFh
0x18000c278  cmp     ebx, esi
0x18000c27a  jz      short loc_18000C2F6
0x18000c27c  movzx   ecx, word ptr [rdi]
0x18000c27f  cmp     cx, 7Fh
0x18000c283  ja      short loc_18000C2E1
0x18000c285  mov     eax, 2Eh ; '.'
0x18000c28a  cmp     ax, cx
0x18000c28d  jnz     short loc_18000C296
0x18000c28f  mov     eax, 2
0x18000c294  jmp     short loc_18000C2C9
0x18000c296  mov     eax, 2Dh ; '-'
0x18000c29b  cmp     ax, cx
0x18000c29e  jnz     short loc_18000C2A7
0x18000c2a0  mov     eax, 3
0x18000c2a5  jmp     short loc_18000C2C9
0x18000c2a7  lea     eax, [rcx-41h]
0x18000c2aa  cmp     ax, 19h
0x18000c2ae  jbe     short loc_18000C2C7
0x18000c2b0  lea     eax, [rcx-61h]
0x18000c2b3  cmp     ax, 19h
0x18000c2b7  jbe     short loc_18000C2C7
0x18000c2b9  sub     cx, 30h ; '0'
0x18000c2bd  cmp     cx, 9
0x18000c2c1  ja      short loc_18000C2E1
0x18000c2c3  mov     eax, ebp
0x18000c2c5  jmp     short loc_18000C2C9
0x18000c2c7  xor     eax, eax
0x18000c2c9  cdqe
0x18000c2cb  lea     rcx, [rax+rax*2]
0x18000c2cf  movsxd  rax, ebx
0x18000c2d2  add     rcx, rax
0x18000c2d5  lea     rbx, qword_180016D50
0x18000c2dc  mov     ebx, [rbx+rcx*4]
0x18000c2df  jmp     short loc_18000C2E3
0x18000c2e1  mov     ebx, esi
0x18000c2e3  mov     rcx, rdi; lpsz
0x18000c2e6  call    cs:__imp_CharNextW
0x18000c2ec  mov     rdi, rax
0x18000c2ef  xor     eax, eax
0x18000c2f1  cmp     ax, [rdi]
0x18000c2f4  jnz     short loc_18000C278
0x18000c2f6  cmp     ebx, 2
0x18000c2f9  jnz     short loc_18000C2FF
0x18000c2fb  mov     ebx, ebp
0x18000c2fd  jmp     short loc_18000C301
0x18000c2ff  xor     ebx, ebx
0x18000c301  mov     eax, ebx
0x18000c303  mov     rcx, [rsp+0F8h+var_38]
0x18000c30b  xor     rcx, rsp; StackCookie
0x18000c30e  call    __security_check_cookie
0x18000c313  add     rsp, 0D8h
0x18000c31a  pop     rdi
0x18000c31b  pop     rsi
0x18000c31c  pop     rbp
0x18000c31d  pop     rbx
0x18000c31e  retn
```
