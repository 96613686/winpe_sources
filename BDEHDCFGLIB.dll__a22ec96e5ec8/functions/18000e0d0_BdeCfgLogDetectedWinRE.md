# BdeCfgLogDetectedWinRE

- ea: `0x18000e0d0`
- end: `0x18000e2bc`
- name: `BdeCfgLogDetectedWinRE`
- size: `492`
- prototype: `__int64 __fastcall(_WORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800067f0`

## callees

- `0x18000e0d0`
- `0x1800135c0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x18000e280`
- `ADVAPI32!EventWrite` at `0x18000e280`

## pseudocode

```c
__int64 __fastcall BdeCfgLogDetectedWinRE(_WORD *a1, __int64 a2)
{
  ULONGLONG v2; // r8
  signed int v3; // ebx
  __int64 v4; // rax
  int v5; // r9d
  unsigned __int64 v6; // rax
  ULONG v7; // ecx
  __int64 v8; // rax
  signed int v9; // eax
  __int64 v11; // [rsp+28h] [rbp-A0h]
  __int64 v12; // [rsp+30h] [rbp-98h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-78h] BYREF
  int *v14; // [rsp+60h] [rbp-68h]
  int v15; // [rsp+68h] [rbp-60h]
  int v16; // [rsp+6Ch] [rbp-5Ch]
  __int64 v17; // [rsp+70h] [rbp-58h]
  __int64 v18; // [rsp+78h] [rbp-50h]
  __int64 v19; // [rsp+80h] [rbp-48h]
  __int64 v20; // [rsp+88h] [rbp-40h]
  int v21; // [rsp+90h] [rbp-38h] BYREF
  wchar_t v22; // [rsp+94h] [rbp-34h]

  v2 = (ULONGLONG)a1;
  v21 = *(_DWORD *)L" :";
  v22 = asc_18001763C[2];
  v3 = 0;
  if ( !g_EventRegistrationHandle )
    v3 = -1063256042;
  if ( v3 >= 0 )
  {
    if ( a1 )
    {
      v4 = 512;
      v5 = 0;
      while ( v4 && *a1 )
      {
        ++a1;
        --v4;
      }
      if ( !v4 )
        v5 = -2147024809;
      v3 = v5;
      if ( v5 < 0 )
        v12 = 0;
      else
        v12 = 512 - v4;
      if ( v5 < 0 )
        v11 = 0;
      else
        v11 = 2 * v12;
      if ( v5 >= 0 )
      {
        v6 = v11 + 2;
        v7 = -1;
        if ( (unsigned __int64)(v11 + 2) <= 0xFFFFFFFF )
          v7 = v11 + 2;
        v3 = v6 > 0xFFFFFFFF ? 0x80070216 : 0;
        if ( v6 <= 0xFFFFFFFF )
        {
          UserData.Ptr = v2;
          UserData.Size = v7;
          UserData.Reserved = 0;
          LOWORD(v21) = *(_WORD *)(a2 + 520);
          v8 = -1;
          do
            ++v8;
          while ( *((_WORD *)&v21 + v8) );
          v14 = &v21;
          v15 = 2 * v8 + 2;
          v16 = 0;
          v17 = a2 + 524;
          v18 = 4;
          v19 = a2 + 528;
          v20 = 4;
          v9 = EventWrite(g_EventRegistrationHandle, &BDECFG_EVT_LOG_WINRE_DETECTED, 4u, &UserData);
          if ( v9 )
          {
            if ( v9 > 0 )
              return (unsigned __int16)v9 | 0x80070000;
            else
              return (unsigned int)v9;
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000e0d0  mov     r11, rsp
0x18000e0d3  push    rbx
0x18000e0d4  push    rsi
0x18000e0d5  push    rdi
0x18000e0d6  push    r14
0x18000e0d8  sub     rsp, 0A8h
0x18000e0df  mov     rax, cs:__security_cookie
0x18000e0e6  xor     rax, rsp
0x18000e0e9  mov     [rsp+0C8h+var_30], rax
0x18000e0f1  mov     r10, rdx
0x18000e0f4  mov     r8, rcx
0x18000e0f7  xor     edi, edi
0x18000e0f9  mov     [rsp+0C8h+var_A0], rdi
0x18000e0fe  mov     eax, dword ptr cs:asc_18001763C; " :"
0x18000e104  mov     [r11-38h], eax
0x18000e108  movzx   eax, word ptr cs:asc_18001763C+4; ""
0x18000e10f  mov     [r11-34h], ax
0x18000e114  mov     ebx, edi
0x18000e116  mov     eax, 0C0A00016h
0x18000e11b  mov     r11, cs:?g_EventRegistrationHandle@@3_KA; unsigned __int64 g_EventRegistrationHandle
0x18000e122  test    r11, r11
0x18000e125  cmovz   ebx, eax
0x18000e128  mov     [rsp+0C8h+var_A8], ebx
0x18000e12c  test    ebx, ebx
0x18000e12e  js      loc_18000E29D
0x18000e134  test    rcx, rcx
0x18000e137  jnz     short loc_18000E143
0x18000e139  mov     ebx, 80070057h
0x18000e13e  jmp     loc_18000E299
0x18000e143  lea     rsi, [rsp+0C8h+var_A0]
0x18000e148  mov     [rsp+0C8h+var_98], rdi
0x18000e14d  lea     r14, [rsp+0C8h+var_98]
0x18000e152  mov     edx, 200h
0x18000e157  mov     eax, edx
0x18000e159  mov     [rsp+0C8h+var_88], rdx
0x18000e15e  mov     [rsp+0C8h+var_90], rcx
0x18000e163  mov     r9d, edi
0x18000e166  test    rax, rax
0x18000e169  jz      short loc_18000E183
0x18000e16b  cmp     [rcx], di
0x18000e16e  jz      short loc_18000E183
0x18000e170  add     rcx, 2
0x18000e174  mov     [rsp+0C8h+var_90], rcx
0x18000e179  dec     rax
0x18000e17c  mov     [rsp+0C8h+var_88], rax
0x18000e181  jmp     short loc_18000E166
0x18000e183  mov     ebx, 80070057h
0x18000e188  test    rax, rax
0x18000e18b  cmovz   r9d, ebx
0x18000e18f  mov     ebx, r9d
0x18000e192  test    r9d, r9d
0x18000e195  js      short loc_18000E19F
0x18000e197  sub     rdx, rax
0x18000e19a  mov     [r14], rdx
0x18000e19d  jmp     short loc_18000E1A2
0x18000e19f  mov     [r14], rdi
0x18000e1a2  test    ebx, ebx
0x18000e1a4  js      short loc_18000E1B3
0x18000e1a6  mov     rax, [rsp+0C8h+var_98]
0x18000e1ab  add     rax, rax
0x18000e1ae  mov     [rsi], rax
0x18000e1b1  jmp     short loc_18000E1B6
0x18000e1b3  mov     [rsi], rdi
0x18000e1b6  mov     [rsp+0C8h+var_A8], ebx
0x18000e1ba  test    ebx, ebx
0x18000e1bc  js      loc_18000E29D
0x18000e1c2  mov     rax, [rsp+0C8h+var_A0]
0x18000e1c7  add     rax, 2
0x18000e1cb  mov     [rsp+0C8h+var_A0], rax
0x18000e1d0  mov     edx, 0FFFFFFFFh
0x18000e1d5  mov     ecx, edx
0x18000e1d7  cmp     rax, rdx
0x18000e1da  cmovbe  ecx, eax
0x18000e1dd  cmp     rdx, rax
0x18000e1e0  sbb     ebx, ebx
0x18000e1e2  and     ebx, 80070216h
0x18000e1e8  mov     [rsp+0C8h+var_A8], ebx
0x18000e1ec  cmp     rax, rdx
0x18000e1ef  ja      loc_18000E29D
0x18000e1f5  mov     [rsp+0C8h+UserData.Ptr], r8
0x18000e1fa  mov     [rsp+0C8h+UserData.Size], ecx
0x18000e1fe  mov     dword ptr [rsp+0C8h+UserData.0Ch], edi
0x18000e202  movzx   eax, word ptr [r10+208h]
0x18000e20a  mov     [rsp+0C8h+var_38], ax
0x18000e212  lea     rcx, [rsp+0C8h+var_38]
0x18000e21a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e21e  inc     rax
0x18000e221  cmp     [rcx+rax*2], di
0x18000e225  jnz     short loc_18000E21E
0x18000e227  lea     rcx, [rsp+0C8h+var_38]
0x18000e22f  mov     [rsp+0C8h+var_68], rcx
0x18000e234  lea     eax, ds:2[rax*2]
0x18000e23b  mov     [rsp+0C8h+var_60], eax
0x18000e23f  mov     [rsp+0C8h+var_5C], edi
0x18000e243  lea     rax, [r10+20Ch]
0x18000e24a  mov     [rsp+0C8h+var_58], rax
0x18000e24f  mov     r8d, 4; UserDataCount
0x18000e255  mov     [rsp+0C8h+var_50], r8
0x18000e25a  lea     rax, [r10+210h]
0x18000e261  mov     [rsp+0C8h+var_48], rax
0x18000e269  mov     [rsp+0C8h+var_40], r8
0x18000e271  lea     r9, [rsp+0C8h+UserData]; UserData
0x18000e276  lea     rdx, BDECFG_EVT_LOG_WINRE_DETECTED; EventDescriptor
0x18000e27d  mov     rcx, r11; RegHandle
0x18000e280  call    cs:__imp_EventWrite
0x18000e286  test    eax, eax
0x18000e288  jz      short loc_18000E29D
0x18000e28a  jg      short loc_18000E290
0x18000e28c  mov     ebx, eax
0x18000e28e  jmp     short loc_18000E299
0x18000e290  movzx   ebx, ax
0x18000e293  or      ebx, 80070000h
0x18000e299  mov     [rsp+0C8h+var_A8], ebx
0x18000e29d  mov     eax, ebx
0x18000e29f  mov     rcx, [rsp+0C8h+var_30]
0x18000e2a7  xor     rcx, rsp; StackCookie
0x18000e2aa  call    __security_check_cookie
0x18000e2af  add     rsp, 0A8h
0x18000e2b6  pop     r14
0x18000e2b8  pop     rdi
0x18000e2b9  pop     rsi
0x18000e2ba  pop     rbx
0x18000e2bb  retn
0x180014149  push    rbp
0x18001414b  sub     rsp, 20h
0x18001414f  mov     rbp, rdx
0x180014152  add     rsp, 20h
0x180014156  pop     rbp
0x180014157  retn
```
