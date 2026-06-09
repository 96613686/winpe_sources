# WevtXMLParser::EndElementTag(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x180023890`
- end: `0x1800239b8`
- name: `?EndElementTag@WevtXMLParser@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(WevtXMLParser *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018468`

## callees

- `0x180019434`
- `0x18001cf80`
- `0x180023548`
- `0x180023890`
- `0x180038fb4`

## pseudocode

```c
void __fastcall WevtXMLParser::EndElementTag(WevtXMLParser *this, __int128 *a2)
{
  __int64 v2; // rdi
  WevtXMLParser *v3; // r11
  __int128 v4; // [rsp+20h] [rbp-40h] BYREF
  __int128 pExceptionObject; // [rsp+30h] [rbp-30h] BYREF
  __int64 v6; // [rsp+40h] [rbp-20h]
  int v7; // [rsp+48h] [rbp-18h]
  int v8; // [rsp+4Ch] [rbp-14h]
  int v9; // [rsp+50h] [rbp-10h]

  v2 = *((_QWORD *)this + 1);
  v3 = this;
  if ( *(_QWORD *)this == v2 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids, 15008);
    }
    v6 = 0;
    v7 = 15008;
    v8 = -1;
    pExceptionObject = 0;
    v9 = 205;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *((_QWORD *)a2 + 1) )
  {
    v4 = *a2;
    if ( (unsigned int)HashStringCaseSensitive(&v4) != *(_DWORD *)(v2 - 4) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids, 15008);
      }
      v6 = 0;
      v7 = 15008;
      v8 = -1;
      pExceptionObject = 0;
      v9 = 220;
      throw (EvtException *)&pExceptionObject;
    }
  }
  WevtXMLParser::EndCurrentElement(v3);
}

```

## disassembly

```asm
0x180023890  mov     [rsp-8+arg_0], rdi
0x180023895  push    rbp
0x180023896  mov     rbp, rsp
0x180023899  sub     rsp, 60h
0x18002389d  mov     rdi, [rcx+8]
0x1800238a1  mov     r11, rcx
0x1800238a4  cmp     [rcx], rdi
0x1800238a7  jnz     short loc_180023917
0x1800238a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238b0  lea     rax, WPP_GLOBAL_Control
0x1800238b7  mov     edi, 3AA0h
0x1800238bc  cmp     rcx, rax
0x1800238bf  jz      short loc_1800238E5
0x1800238c1  test    byte ptr [rcx+1Ch], 2
0x1800238c5  jz      short loc_1800238E5
0x1800238c7  cmp     byte ptr [rcx+19h], 2
0x1800238cb  jb      short loc_1800238E5
0x1800238cd  mov     rcx, [rcx+10h]
0x1800238d1  lea     r8, WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids
0x1800238d8  mov     edx, 14h
0x1800238dd  mov     r9d, edi
0x1800238e0  call    WPP_SF_D
0x1800238e5  xorps   xmm0, xmm0
0x1800238e8  mov     [rbp+var_20], 0
0x1800238f0  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800238f7  mov     [rbp+var_18], edi
0x1800238fa  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800238fe  mov     [rbp+var_14], 0FFFFFFFFh
0x180023905  movdqu  [rbp+pExceptionObject], xmm0
0x18002390a  mov     [rbp+var_10], 0CDh
0x180023911  call    _CxxThrowException_0
0x180023917  cmp     qword ptr [rdx+8], 0
0x18002391c  jz      loc_1800239A6
0x180023922  movaps  xmm0, xmmword ptr [rdx]
0x180023925  lea     rcx, [rbp+var_40]
0x180023929  movdqa  [rbp+var_40], xmm0
0x18002392e  call    ?HashStringCaseSensitive@@YAKV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; HashStringCaseSensitive(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180023933  cmp     eax, [rdi-4]
0x180023936  jz      short loc_1800239A6
0x180023938  mov     rcx, cs:WPP_GLOBAL_Control
0x18002393f  lea     rax, WPP_GLOBAL_Control
0x180023946  mov     edi, 3AA0h
0x18002394b  cmp     rcx, rax
0x18002394e  jz      short loc_180023974
0x180023950  test    byte ptr [rcx+1Ch], 2
0x180023954  jz      short loc_180023974
0x180023956  cmp     byte ptr [rcx+19h], 2
0x18002395a  jb      short loc_180023974
0x18002395c  mov     rcx, [rcx+10h]
0x180023960  lea     r8, WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids
0x180023967  mov     edx, 15h
0x18002396c  mov     r9d, edi
0x18002396f  call    WPP_SF_D
0x180023974  xorps   xmm0, xmm0
0x180023977  mov     [rbp+var_20], 0
0x18002397f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180023986  mov     [rbp+var_18], edi
0x180023989  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002398d  mov     [rbp+var_14], 0FFFFFFFFh
0x180023994  movdqu  [rbp+pExceptionObject], xmm0
0x180023999  mov     [rbp+var_10], 0DCh
0x1800239a0  call    _CxxThrowException_0
0x1800239a6  mov     rcx, r11; this
0x1800239a9  mov     rdi, [rsp+60h+arg_0]
0x1800239ae  add     rsp, 60h
0x1800239b2  pop     rbp
0x1800239b3  jmp     ?EndCurrentElement@WevtXMLParser@@AEAAXXZ; WevtXMLParser::EndCurrentElement(void)
```
