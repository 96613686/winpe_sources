# BdeCfgLogCandidateDrive

- ea: `0x18000dbc0`
- end: `0x18000dda1`
- name: `BdeCfgLogCandidateDrive`
- size: `481`
- prototype: `__int64 __fastcall(ULONGLONG)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002460`
- `0x180002814`

## callees

- `0x18000dbc0`
- `0x1800135c0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x18000dd61`
- `ADVAPI32!EventWrite` at `0x18000dd61`

## pseudocode

```c
__int64 __fastcall BdeCfgLogCandidateDrive(ULONGLONG a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // rax
  signed int v4; // eax
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-B8h] BYREF
  ULONGLONG v7; // [rsp+40h] [rbp-A8h]
  __int64 v8; // [rsp+48h] [rbp-A0h]
  ULONGLONG v9; // [rsp+50h] [rbp-98h]
  int v10; // [rsp+58h] [rbp-90h]
  int v11; // [rsp+5Ch] [rbp-8Ch]
  ULONGLONG v12; // [rsp+60h] [rbp-88h]
  __int64 v13; // [rsp+68h] [rbp-80h]
  ULONGLONG v14; // [rsp+70h] [rbp-78h]
  __int64 v15; // [rsp+78h] [rbp-70h]
  ULONGLONG v16; // [rsp+80h] [rbp-68h]
  __int64 v17; // [rsp+88h] [rbp-60h]
  ULONGLONG v18; // [rsp+90h] [rbp-58h]
  __int64 v19; // [rsp+98h] [rbp-50h]
  int *v20; // [rsp+A0h] [rbp-48h]
  int v21; // [rsp+A8h] [rbp-40h]
  int v22; // [rsp+ACh] [rbp-3Ch]
  ULONGLONG v23; // [rsp+B0h] [rbp-38h]
  __int64 v24; // [rsp+B8h] [rbp-30h]
  ULONGLONG v25; // [rsp+C0h] [rbp-28h]
  __int64 v26; // [rsp+C8h] [rbp-20h]
  int v27; // [rsp+D0h] [rbp-18h] BYREF
  wchar_t v28; // [rsp+D4h] [rbp-14h]

  v27 = *(_DWORD *)L" :";
  v28 = asc_18001763C[2];
  v1 = 0;
  if ( !g_EventRegistrationHandle )
    v1 = -1063256042;
  if ( v1 >= 0 )
  {
    if ( a1 )
    {
      UserData.Ptr = a1;
      *(_QWORD *)&UserData.Size = 4;
      v7 = a1 + 4;
      v8 = 4;
      v2 = -1;
      v3 = -1;
      do
        ++v3;
      while ( *(_WORD *)(a1 + 8 + 2 * v3) );
      v9 = a1 + 8;
      v10 = 2 * v3 + 2;
      v11 = 0;
      v12 = a1 + 528;
      v13 = 8;
      v14 = a1 + 536;
      v15 = 8;
      v16 = a1 + 544;
      v17 = 8;
      v18 = a1 + 552;
      v19 = 4;
      LOWORD(v27) = *(_WORD *)(a1 + 556);
      do
        ++v2;
      while ( *((_WORD *)&v27 + v2) );
      v20 = &v27;
      v21 = 2 * v2 + 2;
      v22 = 0;
      v23 = a1 + 560;
      v24 = 4;
      v25 = a1 + 564;
      v26 = 4;
      v4 = EventWrite(g_EventRegistrationHandle, &BDECFG_EVT_FOUND_CANDIDATE_DRIVE, 0xAu, &UserData);
      if ( v4 )
      {
        if ( v4 > 0 )
          return (unsigned __int16)v4 | 0x80070000;
        else
          return (unsigned int)v4;
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000dbc0  mov     r11, rsp
0x18000dbc3  mov     [r11+8], rbx
0x18000dbc7  push    rdi
0x18000dbc8  sub     rsp, 0E0h
0x18000dbcf  mov     rax, cs:__security_cookie
0x18000dbd6  xor     rax, rsp
0x18000dbd9  mov     [rsp+0E8h+var_10], rax
0x18000dbe1  mov     eax, dword ptr cs:asc_18001763C; " :"
0x18000dbe7  mov     [r11-18h], eax
0x18000dbeb  movzx   eax, word ptr cs:asc_18001763C+4; ""
0x18000dbf2  mov     [r11-14h], ax
0x18000dbf7  xor     edi, edi
0x18000dbf9  mov     ebx, edi
0x18000dbfb  mov     eax, 0C0A00016h
0x18000dc00  mov     r10, cs:?g_EventRegistrationHandle@@3_KA; unsigned __int64 g_EventRegistrationHandle
0x18000dc07  test    r10, r10
0x18000dc0a  cmovz   ebx, eax
0x18000dc0d  mov     [rsp+0E8h+var_C8], ebx
0x18000dc11  test    ebx, ebx
0x18000dc13  js      loc_18000DD7E
0x18000dc19  test    rcx, rcx
0x18000dc1c  jnz     short loc_18000DC28
0x18000dc1e  mov     ebx, 80070057h
0x18000dc23  jmp     loc_18000DD7A
0x18000dc28  mov     [rsp+0E8h+UserData.Ptr], rcx
0x18000dc2d  mov     qword ptr [rsp+0E8h+UserData.Size], 4
0x18000dc36  lea     rax, [rcx+4]
0x18000dc3a  mov     [rsp+0E8h+var_A8], rax
0x18000dc3f  mov     [rsp+0E8h+var_A0], 4
0x18000dc48  lea     r8, [rcx+8]
0x18000dc4c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000dc50  mov     rax, rdx
0x18000dc53  inc     rax
0x18000dc56  cmp     [r8+rax*2], di
0x18000dc5b  jnz     short loc_18000DC53
0x18000dc5d  mov     [rsp+0E8h+var_98], r8
0x18000dc62  lea     eax, ds:2[rax*2]
0x18000dc69  mov     [rsp+0E8h+var_90], eax
0x18000dc6d  mov     [rsp+0E8h+var_8C], edi
0x18000dc71  lea     rax, [rcx+210h]
0x18000dc78  mov     [rsp+0E8h+var_88], rax
0x18000dc7d  mov     [rsp+0E8h+var_80], 8
0x18000dc86  lea     rax, [rcx+218h]
0x18000dc8d  mov     [rsp+0E8h+var_78], rax
0x18000dc92  mov     [rsp+0E8h+var_70], 8
0x18000dc9b  lea     rax, [rcx+220h]
0x18000dca2  mov     [rsp+0E8h+var_68], rax
0x18000dcaa  mov     [rsp+0E8h+var_60], 8
0x18000dcb6  lea     rax, [rcx+228h]
0x18000dcbd  mov     [rsp+0E8h+var_58], rax
0x18000dcc5  mov     [rsp+0E8h+var_50], 4
0x18000dcd1  movzx   eax, word ptr [rcx+22Ch]
0x18000dcd8  mov     [rsp+0E8h+var_18], ax
0x18000dce0  lea     rax, [rsp+0E8h+var_18]
0x18000dce8  inc     rdx
0x18000dceb  cmp     [rax+rdx*2], di
0x18000dcef  jnz     short loc_18000DCE8
0x18000dcf1  lea     rax, [rsp+0E8h+var_18]
0x18000dcf9  mov     [rsp+0E8h+var_48], rax
0x18000dd01  lea     eax, ds:2[rdx*2]
0x18000dd08  mov     [rsp+0E8h+var_40], eax
0x18000dd0f  mov     [rsp+0E8h+var_3C], edi
0x18000dd16  lea     rax, [rcx+230h]
0x18000dd1d  mov     [rsp+0E8h+var_38], rax
0x18000dd25  mov     [rsp+0E8h+var_30], 4
0x18000dd31  lea     rax, [rcx+234h]
0x18000dd38  mov     [rsp+0E8h+var_28], rax
0x18000dd40  mov     [rsp+0E8h+var_20], 4
0x18000dd4c  lea     r9, [rsp+0E8h+UserData]; UserData
0x18000dd51  mov     r8d, 0Ah; UserDataCount
0x18000dd57  lea     rdx, BDECFG_EVT_FOUND_CANDIDATE_DRIVE; EventDescriptor
0x18000dd5e  mov     rcx, r10; RegHandle
0x18000dd61  call    cs:__imp_EventWrite
0x18000dd67  test    eax, eax
0x18000dd69  jz      short loc_18000DD7E
0x18000dd6b  jg      short loc_18000DD71
0x18000dd6d  mov     ebx, eax
0x18000dd6f  jmp     short loc_18000DD7A
0x18000dd71  movzx   ebx, ax
0x18000dd74  or      ebx, 80070000h
0x18000dd7a  mov     [rsp+0E8h+var_C8], ebx
0x18000dd7e  mov     eax, ebx
0x18000dd80  mov     rcx, [rsp+0E8h+var_10]
0x18000dd88  xor     rcx, rsp; StackCookie
0x18000dd8b  call    __security_check_cookie
0x18000dd90  mov     rbx, [rsp+0E8h+arg_0]
0x18000dd98  add     rsp, 0E0h
0x18000dd9f  pop     rdi
0x18000dda0  retn
0x180014149  push    rbp
0x18001414b  sub     rsp, 20h
0x18001414f  mov     rbp, rdx
0x180014152  add     rsp, 20h
0x180014156  pop     rbp
0x180014157  retn
```
