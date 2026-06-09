# sub_1800E0EEC

- ea: `0x1800e0eec`
- end: `0x1800e1168`
- name: `sub_1800E0EEC`
- size: `636`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180100d30`

## callees

- `0x1800599dc`
- `0x1800e0eec`
- `0x1802de200`
- `0x1802de3a0`

## import_xrefs

- `GDI32!SelectObject` at `0x1800e0fc0`
- `GDI32!SelectObject` at `0x1800e0fe7`
- `GDI32!SelectObject` at `0x1800e0fc0`
- `GDI32!SelectObject` at `0x1800e0fe7`
- `GDI32!DeleteObject` at `0x1800e1138`
- `GDI32!DeleteObject` at `0x1800e1138`
- `GDI32!CreateCompatibleDC` at `0x1800e0f9e`
- `GDI32!CreateCompatibleDC` at `0x1800e0f9e`
- `GDI32!DeleteDC` at `0x1800e1146`
- `GDI32!DeleteDC` at `0x1800e114f`
- `GDI32!DeleteDC` at `0x1800e1146`
- `GDI32!DeleteDC` at `0x1800e114f`
- `GDI32!CreateFontIndirectW` at `0x1800e0faa`
- `GDI32!CreateFontIndirectW` at `0x1800e0faa`
- `GDI32!GetTextCharsetInfo` at `0x1800e0fd8`
- `GDI32!GetTextCharsetInfo` at `0x1800e0fd8`
- `mso40uiWin32Client!mso40uiWin32Client_47867` at `0x1800e1125`
- `mso40uiWin32Client!mso40uiWin32Client_47867` at `0x1800e1125`
- `Mso30Win32Client!Mso30Win32Client_28190` at `0x1800e1034`
- `Mso30Win32Client!Mso30Win32Client_28190` at `0x1800e1034`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x1800e1161`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x1800e1161`

## pseudocode

```c
void __fastcall sub_1800E0EEC(__int64 a1, _WORD *a2)
{
  _BYTE *v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rax
  const LOGFONTW *v6; // rsi
  char v7; // r14
  HDC CompatibleDC; // rbx
  void *FontIndirectW; // rax
  HGDIOBJ v10; // rsi
  __int64 v11; // rax
  DWORD v12; // r8d
  __int64 *v13; // rsi
  int v14; // ebx
  bool v15; // cc
  __int128 v16; // xmm0
  bool v17; // al
  __int64 v18; // rax
  __int128 v19; // [rsp+30h] [rbp-69h]
  int v20; // [rsp+40h] [rbp-59h]
  _BYTE v21[24]; // [rsp+48h] [rbp-51h] BYREF
  tagFONTSIGNATURE Sig; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v23[64]; // [rsp+80h] [rbp-19h] BYREF

  v3 = a2;
  if ( !qword_1815304B0 )
    return;
  if ( !a2 )
    return;
  if ( !*a2 )
    return;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( (int)v4 > 31 )
    return;
  v5 = (*(__int64 (**)(void))(*(_QWORD *)qword_1815304B0 + 368LL))();
  v6 = (const LOGFONTW *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v5 + 40LL))(v5, v3);
  if ( !v6 )
  {
    if ( !(unsigned int)mso40uiWin32Client_47867(v3, v23, 31) )
      return;
    v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_1815304B0 + 368LL))(qword_1815304B0);
    v3 = v23;
    v6 = (const LOGFONTW *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v18 + 40LL))(v18, v23);
    if ( !v6 )
      return;
  }
  memset(&Sig, 0, sizeof(Sig));
  v7 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  FontIndirectW = CreateFontIndirectW(v6);
  if ( CompatibleDC )
  {
    if ( !FontIndirectW )
      goto LABEL_14;
    v10 = SelectObject(CompatibleDC, FontIndirectW);
    if ( !v10 )
      goto LABEL_14;
    GetTextCharsetInfo(CompatibleDC, &Sig, 0);
    v7 = 1;
    FontIndirectW = SelectObject(CompatibleDC, v10);
  }
  if ( FontIndirectW )
    DeleteObject(FontIndirectW);
LABEL_14:
  if ( CompatibleDC )
  {
    DeleteDC(CompatibleDC);
    DeleteDC(CompatibleDC);
  }
  if ( v7 )
  {
    v11 = Mso30Win32Client_28190(v21, &Sig);
    v12 = Sig.fsCsb[0];
    v13 = qword_1810D6540;
    v14 = 0;
    v15 = 1;
    v16 = *(_OWORD *)v11;
    v20 = *(_DWORD *)(v11 + 16);
    v19 = v16;
    while ( 1 )
    {
      if ( !v15 )
      {
        Mso20Win32Client_21217(506589338, 0);
        JUMPOUT(0x1800E1167LL);
      }
      if ( v14 <= 10 )
        break;
      if ( v14 <= 14 )
      {
        v17 = (v12 & *(_DWORD *)v13) != 0;
      }
      else
      {
        if ( ((unsigned __int8)(1 << (*(_BYTE *)v13 & 7)) & *((_BYTE *)&v19 + ((__int64)*(int *)v13 >> 3))) != 0 )
          goto LABEL_30;
        v17 = 0;
      }
      if ( v17 )
        goto LABEL_30;
LABEL_25:
      ++v14;
      v13 = (__int64 *)((char *)v13 + 4);
      v15 = (unsigned int)v14 <= 0x1C;
      if ( v14 > 28 )
        return;
    }
    if ( (v12 & *(_DWORD *)v13) == 0 || (v12 & 0x803E0000) != 0 )
      goto LABEL_25;
LABEL_30:
    sub_1800599DC((void *)(a1 + 32LL * v14 + 16), v3);
    v12 = Sig.fsCsb[0];
    goto LABEL_25;
  }
}

```

## disassembly

```asm
0x1800e0eec  mov     [rsp-8+arg_10], rbx
0x1800e0ef1  mov     [rsp-8+arg_18], rsi
0x1800e0ef6  push    rbp
0x1800e0ef7  push    rdi
0x1800e0ef8  push    r12
0x1800e0efa  push    r14
0x1800e0efc  push    r15
0x1800e0efe  lea     rbp, [rsp-37h]
0x1800e0f03  sub     rsp, 0D0h
0x1800e0f0a  mov     rax, cs:__security_cookie
0x1800e0f11  xor     rax, rsp
0x1800e0f14  mov     [rbp+57h+var_30], rax
0x1800e0f18  mov     r15, rcx
0x1800e0f1b  xor     r12d, r12d
0x1800e0f1e  mov     rcx, cs:qword_1815304B0
0x1800e0f25  mov     rdi, rdx
0x1800e0f28  test    rcx, rcx
0x1800e0f2b  jz      loc_1800E1004
0x1800e0f31  test    rdx, rdx
0x1800e0f34  jz      loc_1800E1004
0x1800e0f3a  cmp     [rdx], r12w
0x1800e0f3e  jz      loc_1800E1004
0x1800e0f44  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e0f48  inc     rax
0x1800e0f4b  cmp     [rdx+rax*2], r12w
0x1800e0f50  jnz     short loc_1800E0F48
0x1800e0f52  cmp     eax, 1Fh
0x1800e0f55  jg      loc_1800E1004
0x1800e0f5b  mov     rax, [rcx]
0x1800e0f5e  mov     rax, [rax+170h]
0x1800e0f65  call    cs:__guard_dispatch_icall_fptr
0x1800e0f6b  mov     r9, rax
0x1800e0f6e  mov     rdx, rdi
0x1800e0f71  mov     rcx, [rax]
0x1800e0f74  mov     rax, [rcx+28h]
0x1800e0f78  mov     rcx, r9
0x1800e0f7b  call    cs:__guard_dispatch_icall_fptr
0x1800e0f81  mov     rsi, rax
0x1800e0f84  test    rax, rax
0x1800e0f87  jz      loc_1800E110D
0x1800e0f8d  xor     ecx, ecx; hdc
0x1800e0f8f  mov     qword ptr [rbp+57h+Sig.fsUsb], r12
0x1800e0f93  mov     r14b, r12b
0x1800e0f96  mov     qword ptr [rbp+57h+Sig.fsUsb+8], r12
0x1800e0f9a  mov     qword ptr [rbp+57h+Sig.fsCsb], r12
0x1800e0f9e  call    cs:CreateCompatibleDC
0x1800e0fa4  mov     rcx, rsi; lplf
0x1800e0fa7  mov     rbx, rax
0x1800e0faa  call    cs:CreateFontIndirectW
0x1800e0fb0  test    rbx, rbx
0x1800e0fb3  jz      short loc_1800E0FED
0x1800e0fb5  test    rax, rax
0x1800e0fb8  jz      short loc_1800E0FF6
0x1800e0fba  mov     rdx, rax; h
0x1800e0fbd  mov     rcx, rbx; hdc
0x1800e0fc0  call    cs:SelectObject
0x1800e0fc6  mov     rsi, rax
0x1800e0fc9  test    rax, rax
0x1800e0fcc  jz      short loc_1800E0FF6
0x1800e0fce  xor     r8d, r8d; dwFlags
0x1800e0fd1  lea     rdx, [rbp+57h+Sig]; lpSig
0x1800e0fd5  mov     rcx, rbx; hdc
0x1800e0fd8  call    cs:GetTextCharsetInfo
0x1800e0fde  mov     rdx, rsi; h
0x1800e0fe1  mov     rcx, rbx; hdc
0x1800e0fe4  mov     r14b, 1
0x1800e0fe7  call    cs:SelectObject
0x1800e0fed  test    rax, rax
0x1800e0ff0  jnz     loc_1800E1135
0x1800e0ff6  test    rbx, rbx
0x1800e0ff9  jnz     loc_1800E1143
0x1800e0fff  test    r14b, r14b
0x1800e1002  jnz     short loc_1800E102C
0x1800e1004  mov     rcx, [rbp+57h+var_30]
0x1800e1008  xor     rcx, rsp; StackCookie
0x1800e100b  call    __security_check_cookie
0x1800e1010  lea     r11, [rsp+0F0h+var_20]
0x1800e1018  mov     rbx, [r11+40h]
0x1800e101c  mov     rsi, [r11+48h]
0x1800e1020  mov     rsp, r11
0x1800e1023  pop     r15
0x1800e1025  pop     r14
0x1800e1027  pop     r12
0x1800e1029  pop     rdi
0x1800e102a  pop     rbp
0x1800e102b  retn
0x1800e102c  lea     rdx, [rbp+57h+Sig]
0x1800e1030  lea     rcx, [rbp+57h+var_A8]
0x1800e1034  call    cs:Mso30Win32Client_28190
0x1800e103a  mov     r8d, [rbp+57h+Sig.fsCsb]
0x1800e103e  lea     rsi, qword_1810D6540
0x1800e1045  mov     ebx, r12d
0x1800e1048  cmp     ebx, 1Ch
0x1800e104b  movups  xmm0, xmmword ptr [rax]
0x1800e104e  mov     eax, [rax+10h]
0x1800e1051  mov     [rbp+57h+var_B0], eax
0x1800e1054  movups  [rbp+57h+var_C0], xmm0
0x1800e1058  ja      loc_1800E115A
0x1800e105e  cmp     ebx, 0Ah
0x1800e1061  jle     short loc_1800E10A0
0x1800e1063  cmp     ebx, 0Eh
0x1800e1066  jle     short loc_1800E1098
0x1800e1068  movsxd  rax, dword ptr [rsi]
0x1800e106b  mov     edx, 1
0x1800e1070  mov     ecx, [rsi]
0x1800e1072  and     ecx, 7
0x1800e1075  sar     rax, 3
0x1800e1079  shl     edx, cl
0x1800e107b  test    byte ptr [rbp+rax+57h+var_C0], dl
0x1800e107f  jnz     short loc_1800E10AE
0x1800e1081  mov     al, r12b
0x1800e1084  test    al, al
0x1800e1086  jnz     short loc_1800E10AE
0x1800e1088  inc     ebx
0x1800e108a  add     rsi, 4
0x1800e108e  cmp     ebx, 1Ch
0x1800e1091  jle     short loc_1800E1058
0x1800e1093  jmp     loc_1800E1004
0x1800e1098  test    [rsi], r8d
0x1800e109b  setnz   al
0x1800e109e  jmp     short loc_1800E1084
0x1800e10a0  test    [rsi], r8d
0x1800e10a3  jz      short loc_1800E1088
0x1800e10a5  test    r8d, 803E0000h
0x1800e10ac  jnz     short loc_1800E1088
0x1800e10ae  movsxd  rcx, ebx
0x1800e10b1  mov     rdx, rdi; Src
0x1800e10b4  shl     rcx, 5
0x1800e10b8  add     rcx, 10h
0x1800e10bc  add     rcx, r15; void *
0x1800e10bf  call    sub_1800599DC
0x1800e10c4  mov     r8d, [rbp+57h+Sig.fsCsb]
0x1800e10c8  jmp     short loc_1800E1088
0x1800e10ca  mov     rcx, cs:qword_1815304B0
0x1800e10d1  mov     rax, [rcx]
0x1800e10d4  mov     rax, [rax+170h]
0x1800e10db  call    cs:__guard_dispatch_icall_fptr
0x1800e10e1  mov     r8, rax
0x1800e10e4  lea     rdx, [rbp+57h+var_70]
0x1800e10e8  mov     rcx, [rax]
0x1800e10eb  mov     rax, [rcx+28h]
0x1800e10ef  mov     rcx, r8
0x1800e10f2  call    cs:__guard_dispatch_icall_fptr
0x1800e10f8  lea     rdi, [rbp+57h+var_70]
0x1800e10fc  mov     rsi, rax
0x1800e10ff  test    rax, rax
0x1800e1102  jz      loc_1800E1004
0x1800e1108  jmp     loc_1800E0F8D
0x1800e110d  xor     r9d, r9d
0x1800e1110  mov     [rsp+0F0h+var_C8], r12d
0x1800e1115  lea     rdx, [rbp+57h+var_70]
0x1800e1119  mov     [rsp+0F0h+var_D0], r12d
0x1800e111e  mov     rcx, rdi
0x1800e1121  lea     r8d, [r9+1Fh]
0x1800e1125  call    cs:mso40uiWin32Client_47867
0x1800e112b  test    eax, eax
0x1800e112d  jz      loc_1800E1004
0x1800e1133  jmp     short loc_1800E10CA
0x1800e1135  mov     rcx, rax; ho
0x1800e1138  call    cs:DeleteObject
0x1800e113e  jmp     loc_1800E0FF6
0x1800e1143  mov     rcx, rbx; hdc
0x1800e1146  call    cs:DeleteDC
0x1800e114c  mov     rcx, rbx; hdc
0x1800e114f  call    cs:DeleteDC
0x1800e1155  jmp     loc_1800E0FFF
0x1800e115a  xor     edx, edx
0x1800e115c  mov     ecx, 1E31F09Ah
0x1800e1161  call    cs:Mso20Win32Client_21217
```
