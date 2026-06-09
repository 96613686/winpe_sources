# BdeCfgLogCommandLineParams

- ea: `0x18000ddf0`
- end: `0x18000e0c4`
- name: `BdeCfgLogCommandLineParams`
- size: `724`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ddf0`
- `0x1800135c0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x18000e088`
- `ADVAPI32!EventWrite` at `0x18000e088`

## pseudocode

```c
__int64 __fastcall BdeCfgLogCommandLineParams(_WORD *a1, unsigned __int8 *a2)
{
  ULONGLONG v2; // r10
  signed int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rax
  int v6; // r8d
  unsigned __int64 v7; // rax
  ULONG v8; // ecx
  __int64 v9; // rcx
  __int64 v10; // rax
  signed int v11; // eax
  int v13; // [rsp+20h] [rbp-108h] BYREF
  signed int v14; // [rsp+24h] [rbp-104h]
  __int64 v15; // [rsp+28h] [rbp-100h]
  __int64 v16; // [rsp+30h] [rbp-F8h]
  _WORD *v17; // [rsp+38h] [rbp-F0h]
  __int64 v18; // [rsp+40h] [rbp-E8h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-D8h] BYREF
  int *v20; // [rsp+60h] [rbp-C8h]
  __int64 v21; // [rsp+68h] [rbp-C0h]
  int *v22; // [rsp+70h] [rbp-B8h]
  __int64 v23; // [rsp+78h] [rbp-B0h]
  int *v24; // [rsp+80h] [rbp-A8h]
  int v25; // [rsp+88h] [rbp-A0h]
  int v26; // [rsp+8Ch] [rbp-9Ch]
  unsigned __int8 *v27; // [rsp+90h] [rbp-98h]
  __int64 v28; // [rsp+98h] [rbp-90h]
  int *v29; // [rsp+A0h] [rbp-88h]
  int v30; // [rsp+A8h] [rbp-80h]
  int v31; // [rsp+ACh] [rbp-7Ch]
  unsigned __int8 *v32; // [rsp+B0h] [rbp-78h]
  __int64 v33; // [rsp+B8h] [rbp-70h]
  int *v34; // [rsp+C0h] [rbp-68h]
  __int64 v35; // [rsp+C8h] [rbp-60h]
  int *v36; // [rsp+D0h] [rbp-58h]
  __int64 v37; // [rsp+D8h] [rbp-50h]
  int v38; // [rsp+E0h] [rbp-48h] BYREF
  wchar_t v39; // [rsp+E4h] [rbp-44h]
  int v40; // [rsp+E8h] [rbp-40h] BYREF
  wchar_t v41; // [rsp+ECh] [rbp-3Ch]

  v2 = (ULONGLONG)a1;
  v15 = 0;
  v38 = *(_DWORD *)L" :";
  v39 = asc_18001763C[2];
  v40 = *(_DWORD *)L" :";
  v41 = asc_18001763C[2];
  v3 = 0;
  if ( !g_EventRegistrationHandle )
    v3 = -1063256042;
  v14 = v3;
  if ( v3 >= 0 )
  {
    if ( !a2 )
    {
      v3 = -2147024809;
LABEL_33:
      v14 = v3;
      return (unsigned int)v3;
    }
    v4 = 0;
    v16 = 0;
    if ( a1 )
    {
      v5 = 512;
      v18 = 512;
      v17 = a1;
      v6 = 0;
      while ( v5 && *a1 )
      {
        v17 = ++a1;
        v18 = --v5;
      }
      if ( !v5 )
        v6 = -2147024809;
      v3 = v6;
      if ( v6 < 0 )
        v16 = 0;
      else
        v16 = 512 - v5;
      v4 = v16;
    }
    else
    {
      v3 = -2147024809;
    }
    if ( v3 < 0 )
      v15 = 0;
    else
      v15 = 2 * v4;
    v14 = v3;
    if ( v3 >= 0 )
    {
      v7 = v15 + 2;
      v15 = v7;
      v8 = -1;
      if ( v7 <= 0xFFFFFFFF )
        v8 = v7;
      v3 = v7 > 0xFFFFFFFF ? 0x80070216 : 0;
      v14 = v3;
      if ( v7 <= 0xFFFFFFFF )
      {
        UserData.Ptr = v2;
        UserData.Size = v8;
        UserData.Reserved = 0;
        v13 = *a2;
        v20 = &v13;
        v21 = 4;
        v13 = a2[1];
        v22 = &v13;
        v23 = 4;
        LOWORD(v38) = *((_WORD *)a2 + 1);
        v9 = -1;
        v10 = -1;
        do
          ++v10;
        while ( *((_WORD *)&v38 + v10) );
        v24 = &v38;
        v25 = 2 * v10 + 2;
        v26 = 0;
        v27 = a2 + 4;
        v28 = 4;
        LOWORD(v40) = *((_WORD *)a2 + 4);
        do
          ++v9;
        while ( *((_WORD *)&v40 + v9) );
        v29 = &v40;
        v30 = 2 * v9 + 2;
        v31 = 0;
        v32 = a2 + 16;
        v33 = 8;
        v13 = a2[24];
        v34 = &v13;
        v35 = 4;
        v13 = a2[25];
        v36 = &v13;
        v37 = 4;
        v11 = EventWrite(g_EventRegistrationHandle, &BDECFG_EVT_LOG_COMMAND_LINE_PARAMS, 9u, &UserData);
        if ( v11 )
        {
          if ( v11 > 0 )
            v3 = (unsigned __int16)v11 | 0x80070000;
          else
            v3 = v11;
          goto LABEL_33;
        }
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ddf0  mov     r11, rsp
0x18000ddf3  push    rbx
0x18000ddf4  push    rsi
0x18000ddf5  push    rdi
0x18000ddf6  push    r14
0x18000ddf8  sub     rsp, 108h
0x18000ddff  mov     rax, cs:__security_cookie
0x18000de06  xor     rax, rsp
0x18000de09  mov     [rsp+128h+var_38], rax
0x18000de11  mov     r9, rdx
0x18000de14  mov     r10, rcx
0x18000de17  xor     edi, edi
0x18000de19  mov     [rsp+128h+var_100], rdi
0x18000de1e  mov     r8d, dword ptr cs:asc_18001763C; " :"
0x18000de25  mov     [r11-48h], r8d
0x18000de29  movzx   eax, word ptr cs:asc_18001763C+4; ""
0x18000de30  mov     [r11-44h], ax
0x18000de35  mov     [r11-40h], r8d
0x18000de39  mov     [r11-3Ch], ax
0x18000de3e  mov     ebx, edi
0x18000de40  mov     eax, 0C0A00016h
0x18000de45  mov     r11, cs:?g_EventRegistrationHandle@@3_KA; unsigned __int64 g_EventRegistrationHandle
0x18000de4c  test    r11, r11
0x18000de4f  cmovz   ebx, eax
0x18000de52  mov     [rsp+128h+var_104], ebx
0x18000de56  test    ebx, ebx
0x18000de58  js      loc_18000E0A5
0x18000de5e  test    rdx, rdx
0x18000de61  jnz     short loc_18000DE6D
0x18000de63  mov     ebx, 80070057h
0x18000de68  jmp     loc_18000E0A1
0x18000de6d  lea     rsi, [rsp+128h+var_100]
0x18000de72  mov     rax, rdi
0x18000de75  mov     [rsp+128h+var_F8], rax
0x18000de7a  test    r10, r10
0x18000de7d  jz      short loc_18000DEDB
0x18000de7f  lea     r14, [rsp+128h+var_F8]
0x18000de84  mov     edx, 200h
0x18000de89  mov     eax, edx
0x18000de8b  mov     [rsp+128h+var_E8], rdx
0x18000de90  mov     [rsp+128h+var_F0], rcx
0x18000de95  mov     r8d, edi
0x18000de98  test    rax, rax
0x18000de9b  jz      short loc_18000DEB5
0x18000de9d  cmp     [rcx], di
0x18000dea0  jz      short loc_18000DEB5
0x18000dea2  add     rcx, 2
0x18000dea6  mov     [rsp+128h+var_F0], rcx
0x18000deab  dec     rax
0x18000deae  mov     [rsp+128h+var_E8], rax
0x18000deb3  jmp     short loc_18000DE98
0x18000deb5  mov     ebx, 80070057h
0x18000deba  test    rax, rax
0x18000debd  cmovz   r8d, ebx
0x18000dec1  mov     ebx, r8d
0x18000dec4  test    r8d, r8d
0x18000dec7  js      short loc_18000DED1
0x18000dec9  sub     rdx, rax
0x18000decc  mov     [r14], rdx
0x18000decf  jmp     short loc_18000DED4
0x18000ded1  mov     [r14], rdi
0x18000ded4  mov     rax, [rsp+128h+var_F8]
0x18000ded9  jmp     short loc_18000DEE0
0x18000dedb  mov     ebx, 80070057h
0x18000dee0  test    ebx, ebx
0x18000dee2  js      short loc_18000DEEC
0x18000dee4  add     rax, rax
0x18000dee7  mov     [rsi], rax
0x18000deea  jmp     short loc_18000DEEF
0x18000deec  mov     [rsi], rdi
0x18000deef  mov     [rsp+128h+var_104], ebx
0x18000def3  test    ebx, ebx
0x18000def5  js      loc_18000E0A5
0x18000defb  mov     rax, [rsp+128h+var_100]
0x18000df00  add     rax, 2
0x18000df04  mov     [rsp+128h+var_100], rax
0x18000df09  mov     edx, 0FFFFFFFFh
0x18000df0e  mov     ecx, edx
0x18000df10  cmp     rax, rdx
0x18000df13  cmovbe  ecx, eax
0x18000df16  cmp     rdx, rax
0x18000df19  sbb     ebx, ebx
0x18000df1b  and     ebx, 80070216h
0x18000df21  mov     [rsp+128h+var_104], ebx
0x18000df25  cmp     rax, rdx
0x18000df28  ja      loc_18000E0A5
0x18000df2e  mov     [rsp+128h+UserData.Ptr], r10
0x18000df33  mov     [rsp+128h+UserData.Size], ecx
0x18000df37  mov     dword ptr [rsp+128h+UserData.0Ch], edi
0x18000df3b  movzx   eax, byte ptr [r9]
0x18000df3f  mov     [rsp+128h+var_108], eax
0x18000df43  lea     rax, [rsp+128h+var_108]
0x18000df48  mov     [rsp+128h+var_C8], rax
0x18000df4d  mov     [rsp+128h+var_C0], 4
0x18000df56  movzx   eax, byte ptr [r9+1]
0x18000df5b  mov     [rsp+128h+var_108], eax
0x18000df5f  lea     rax, [rsp+128h+var_108]
0x18000df64  mov     [rsp+128h+var_B8], rax
0x18000df69  mov     [rsp+128h+var_B0], 4
0x18000df72  movzx   eax, word ptr [r9+2]
0x18000df77  mov     [rsp+128h+var_48], ax
0x18000df7f  lea     rdx, [rsp+128h+var_48]
0x18000df87  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000df8b  mov     rax, rcx
0x18000df8e  inc     rax
0x18000df91  cmp     [rdx+rax*2], di
0x18000df95  jnz     short loc_18000DF8E
0x18000df97  lea     rdx, [rsp+128h+var_48]
0x18000df9f  mov     [rsp+128h+var_A8], rdx
0x18000dfa7  lea     eax, ds:2[rax*2]
0x18000dfae  mov     [rsp+128h+var_A0], eax
0x18000dfb5  mov     [rsp+128h+var_9C], edi
0x18000dfbc  lea     rax, [r9+4]
0x18000dfc0  mov     [rsp+128h+var_98], rax
0x18000dfc8  mov     [rsp+128h+var_90], 4
0x18000dfd4  movzx   eax, word ptr [r9+8]
0x18000dfd9  mov     [rsp+128h+var_40], ax
0x18000dfe1  lea     rax, [rsp+128h+var_40]
0x18000dfe9  inc     rcx
0x18000dfec  cmp     [rax+rcx*2], di
0x18000dff0  jnz     short loc_18000DFE9
0x18000dff2  lea     rax, [rsp+128h+var_40]
0x18000dffa  mov     [rsp+128h+var_88], rax
0x18000e002  lea     eax, ds:2[rcx*2]
0x18000e009  mov     [rsp+128h+var_80], eax
0x18000e010  mov     [rsp+128h+var_7C], edi
0x18000e017  lea     rax, [r9+10h]
0x18000e01b  mov     [rsp+128h+var_78], rax
0x18000e023  mov     [rsp+128h+var_70], 8
0x18000e02f  movzx   eax, byte ptr [r9+18h]
0x18000e034  mov     [rsp+128h+var_108], eax
0x18000e038  lea     rax, [rsp+128h+var_108]
0x18000e03d  mov     [rsp+128h+var_68], rax
0x18000e045  mov     [rsp+128h+var_60], 4
0x18000e051  movzx   eax, byte ptr [r9+19h]
0x18000e056  mov     [rsp+128h+var_108], eax
0x18000e05a  lea     rax, [rsp+128h+var_108]
0x18000e05f  mov     [rsp+128h+var_58], rax
0x18000e067  mov     [rsp+128h+var_50], 4
0x18000e073  lea     r9, [rsp+128h+UserData]; UserData
0x18000e078  mov     r8d, 9; UserDataCount
0x18000e07e  lea     rdx, BDECFG_EVT_LOG_COMMAND_LINE_PARAMS; EventDescriptor
0x18000e085  mov     rcx, r11; RegHandle
0x18000e088  call    cs:__imp_EventWrite
0x18000e08e  test    eax, eax
0x18000e090  jz      short loc_18000E0A5
0x18000e092  jg      short loc_18000E098
0x18000e094  mov     ebx, eax
0x18000e096  jmp     short loc_18000E0A1
0x18000e098  movzx   ebx, ax
0x18000e09b  or      ebx, 80070000h
0x18000e0a1  mov     [rsp+128h+var_104], ebx
0x18000e0a5  mov     eax, ebx
0x18000e0a7  mov     rcx, [rsp+128h+var_38]
0x18000e0af  xor     rcx, rsp; StackCookie
0x18000e0b2  call    __security_check_cookie
0x18000e0b7  add     rsp, 108h
0x18000e0be  pop     r14
0x18000e0c0  pop     rdi
0x18000e0c1  pop     rsi
0x18000e0c2  pop     rbx
0x18000e0c3  retn
0x180014149  push    rbp
0x18001414b  sub     rsp, 20h
0x18001414f  mov     rbp, rdx
0x180014152  add     rsp, 20h
0x180014156  pop     rbp
0x180014157  retn
```
