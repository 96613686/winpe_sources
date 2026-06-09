# CspDeleteContainer

- ea: `0x18001dbec`
- end: `0x18001dcfb`
- name: `CspDeleteContainer`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001e9b8`

## callees

- `0x180017bac`
- `0x18001c71c`
- `0x18001dbec`
- `0x18001f3a4`
- `0x180021b48`
- `0x180021ddc`
- `0x18002cfa0`
- `0x18002e010`

## string_xrefs

- `0x18001dca6`: `Cached_ContainerInfo`

## pseudocode

```c
__int64 __fastcall CspDeleteContainer(__int64 a1, unsigned __int8 a2)
{
  int v2; // esi
  unsigned int v4; // ebx
  int v5; // r9d
  __int64 v6; // rdx
  wchar_t pszDest[264]; // [rsp+40h] [rbp-228h] BYREF

  v2 = a2;
  if ( *(_QWORD *)(a1 + 8) )
  {
    v4 = CspIncrementCacheFreshness((struct _CARD_STATE *)a1);
    if ( !v4 )
    {
      LOBYTE(v6) = v2;
      v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)(a1 + 8) + 136LL))(
             *(_QWORD *)(a1 + 8),
             v6,
             0);
      if ( !v4 )
      {
        StringCbPrintfW(pszDest, 0x104u, L"%s_%02x", L"Cached_ContainerInfo", v2);
        DeleteCachedCardData(a1, pszDest);
      }
    }
  }
  else
  {
    v4 = 87;
    WppTraceIndent(a1, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
        v5,
        (__int64)"pCardState->pCardData");
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001dbec  mov     [rsp+arg_10], rbx
0x18001dbf1  mov     [rsp+arg_18], rsi
0x18001dbf6  push    rdi
0x18001dbf7  sub     rsp, 260h
0x18001dbfe  mov     rax, cs:__security_cookie
0x18001dc05  xor     rax, rsp
0x18001dc08  mov     [rsp+268h+var_18], rax
0x18001dc10  xor     eax, eax
0x18001dc12  movzx   esi, dl
0x18001dc15  mov     rdi, rcx
0x18001dc18  mov     [rsp+268h+var_238], eax
0x18001dc1c  mov     [rsp+268h+var_234], ax
0x18001dc21  lea     edx, [rax+2]
0x18001dc24  cmp     [rcx+8], rax
0x18001dc28  jnz     short loc_18001DC7A
0x18001dc2a  lea     ebx, [rax+57h]
0x18001dc2d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001dc32  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc39  lea     rax, WPP_GLOBAL_Control
0x18001dc40  cmp     rcx, rax
0x18001dc43  jz      loc_18001DCD4
0x18001dc49  test    byte ptr [rcx+1Ch], 1
0x18001dc4d  jz      loc_18001DCD4
0x18001dc53  cmp     byte ptr [rcx+19h], 2
0x18001dc57  jb      short loc_18001DCD4
0x18001dc59  mov     rcx, [rcx+10h]
0x18001dc5d  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18001dc64  lea     edx, [rbx-4Bh]
0x18001dc67  mov     [rsp+268h+var_248], rax
0x18001dc6c  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001dc73  call    WPP_SF_ss
0x18001dc78  jmp     short loc_18001DCD4
0x18001dc7a  lea     r8, [rsp+268h+var_238]
0x18001dc7f  call    CspIncrementCacheFreshness
0x18001dc84  mov     ebx, eax
0x18001dc86  test    eax, eax
0x18001dc88  jnz     short loc_18001DCD4
0x18001dc8a  mov     rcx, [rdi+8]
0x18001dc8e  xor     r8d, r8d
0x18001dc91  mov     dl, sil
0x18001dc94  mov     rax, [rcx+88h]
0x18001dc9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dca0  mov     ebx, eax
0x18001dca2  test    eax, eax
0x18001dca4  jnz     short loc_18001DCD4
0x18001dca6  lea     r9, aCachedContaine_0; "Cached_ContainerInfo"
0x18001dcad  mov     dword ptr [rsp+268h+var_248], esi
0x18001dcb1  lea     r8, aS02x; "%s_%02x"
0x18001dcb8  mov     edx, 104h; cbDest
0x18001dcbd  lea     rcx, [rsp+268h+pszDest]; pszDest
0x18001dcc2  call    StringCbPrintfW
0x18001dcc7  lea     rdx, [rsp+268h+pszDest]
0x18001dccc  mov     rcx, rdi
0x18001dccf  call    DeleteCachedCardData
0x18001dcd4  mov     eax, ebx
0x18001dcd6  mov     rcx, [rsp+268h+var_18]
0x18001dcde  xor     rcx, rsp; StackCookie
0x18001dce1  call    __security_check_cookie
0x18001dce6  lea     r11, [rsp+268h+var_8]
0x18001dcee  mov     rbx, [r11+20h]
0x18001dcf2  mov     rsi, [r11+28h]
0x18001dcf6  mov     rsp, r11
0x18001dcf9  pop     rdi
0x18001dcfa  retn
```
