# LogMsiCofire

- ea: `0x180004bf4`
- end: `0x180004f07`
- name: `LogMsiCofire`
- size: `787`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800036f0`

## callees

- `0x18000108c`
- `0x180004bf4`
- `0x180007040`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180004cc8`
- `msvcrt!wcsrchr` at `0x180004cf0`
- `msvcrt!wcsrchr` at `0x180004cc8`
- `msvcrt!wcsrchr` at `0x180004cf0`
- `ADVAPI32!EventSetInformation` at `0x180004ca5`
- `ADVAPI32!EventSetInformation` at `0x180004ca5`
- `ADVAPI32!EventRegister` at `0x180004c7d`
- `ADVAPI32!EventRegister` at `0x180004c7d`

## pseudocode

```c
__int64 __fastcall LogMsiCofire(__int64 a1, __int64 a2, int a3, int a4)
{
  const wchar_t *v4; // rbx
  const wchar_t *v8; // rsi
  const wchar_t *v9; // rdi
  int v10; // r12d
  wchar_t *v11; // rax
  wchar_t *v12; // rax
  int v13; // eax
  const wchar_t *v14; // rcx
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  int v18; // edx
  __int64 v19; // rcx
  int v20; // ecx
  __int64 v21; // rcx
  int v22; // ecx
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  int v25; // [rsp+34h] [rbp-CCh] BYREF
  int v26; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+3Ch] [rbp-C4h] BYREF
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29; // [rsp+44h] [rbp-BCh] BYREF
  GUID ProviderId; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v32; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+88h] [rbp-78h]
  int v34; // [rsp+8Ch] [rbp-74h]
  const wchar_t *v35; // [rsp+90h] [rbp-70h]
  int v36; // [rsp+98h] [rbp-68h]
  int v37; // [rsp+9Ch] [rbp-64h]
  int *v38; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  int *v40; // [rsp+B0h] [rbp-50h]
  __int64 v41; // [rsp+B8h] [rbp-48h]
  const wchar_t *v42; // [rsp+C0h] [rbp-40h]
  int v43; // [rsp+C8h] [rbp-38h]
  int v44; // [rsp+CCh] [rbp-34h]
  const wchar_t *v45; // [rsp+D0h] [rbp-30h]
  int v46; // [rsp+D8h] [rbp-28h]
  int v47; // [rsp+DCh] [rbp-24h]
  int *v48; // [rsp+E0h] [rbp-20h]
  __int64 v49; // [rsp+E8h] [rbp-18h]
  int *v50; // [rsp+F0h] [rbp-10h]
  __int64 v51; // [rsp+F8h] [rbp-8h]
  int *v52; // [rsp+100h] [rbp+0h]
  __int64 v53; // [rsp+108h] [rbp+8h]
  int *v54; // [rsp+110h] [rbp+10h]
  __int64 v55; // [rsp+118h] [rbp+18h]

  v4 = L"Not available";
  v24 = a3;
  v8 = L"Not available";
  v9 = L"Not available";
  ProviderId = (GUID)*((_OWORD *)off_18000E020 - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_18000E040 = 0;
  v10 = 2;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_18000E018, &RegHandle) )
    EventSetInformation(RegHandle, 2, off_18000E020, *(unsigned __int16 *)off_18000E020);
  if ( a1 )
  {
    v8 = *(const wchar_t **)a1;
    if ( *(_QWORD *)a1 )
    {
      v11 = wcsrchr(*(const wchar_t **)a1, 0x5Cu);
      if ( v11 )
        v8 = v11 + 1;
    }
    else
    {
      v8 = L"Not available";
    }
    v9 = *(const wchar_t **)(a1 + 8);
    if ( v9 )
    {
      v12 = wcsrchr(*(const wchar_t **)(a1 + 8), 0x5Cu);
      if ( v12 )
        v9 = v12 + 1;
    }
    else
    {
      v9 = L"Not available";
    }
  }
  if ( (unsigned int)dword_18000E018 > 5
    && (qword_18000E028 & 0x200000000000LL) != 0
    && (qword_18000E030 & 0x200000000000LL) == qword_18000E030 )
  {
    if ( a2 )
    {
      v25 = *(_DWORD *)(a2 + 24);
      v13 = *(_DWORD *)(a2 + 16);
    }
    else
    {
      v25 = 0;
      v13 = 0;
    }
    v26 = v13;
    v28 = v24;
    v27 = a4;
    if ( a2 )
    {
      v14 = *(const wchar_t **)(a2 + 8);
      v4 = *(const wchar_t **)a2;
    }
    else
    {
      v14 = L"Not available";
    }
    if ( a1 )
    {
      v24 = *(_DWORD *)(a1 + 16);
      v15 = *(_DWORD *)(a1 + 20);
    }
    else
    {
      v24 = 0;
      v15 = 0;
    }
    v29 = v15;
    v55 = 4;
    v54 = &v25;
    v52 = &v26;
    v50 = &v27;
    v48 = &v28;
    v16 = -1;
    v53 = 4;
    v51 = 4;
    v49 = 4;
    if ( v14 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v14[v17] );
      v18 = 2 * v17 + 2;
    }
    else
    {
      v14 = (const wchar_t *)&unk_18000B23C;
      v18 = 2;
    }
    v45 = v14;
    v46 = v18;
    v47 = 0;
    if ( v4 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v4[v19] );
      v20 = 2 * v19 + 2;
    }
    else
    {
      v4 = (const wchar_t *)&unk_18000B23C;
      v20 = 2;
    }
    v43 = v20;
    v40 = &v24;
    v38 = &v29;
    v42 = v4;
    v44 = 0;
    v41 = 4;
    v39 = 4;
    if ( v9 )
    {
      v21 = -1;
      do
        ++v21;
      while ( v9[v21] );
      v22 = 2 * v21 + 2;
    }
    else
    {
      v9 = (const wchar_t *)&unk_18000B23C;
      v22 = 2;
    }
    v35 = v9;
    v36 = v22;
    v37 = 0;
    if ( v8 )
    {
      do
        ++v16;
      while ( v8[v16] );
      v10 = 2 * v16 + 2;
    }
    else
    {
      v8 = (const wchar_t *)&unk_18000B23C;
    }
    v34 = 0;
    v32 = v8;
    v33 = v10;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18000E018, byte_18000B8D9, 0, 0, 0xCu, &v31);
  }
  return 0;
}

```

## disassembly

```asm
0x180004bf4  push    rbp
0x180004bf6  push    rbx
0x180004bf7  push    rsi
0x180004bf8  push    rdi
0x180004bf9  push    r12
0x180004bfb  push    r13
0x180004bfd  push    r14
0x180004bff  push    r15
0x180004c01  lea     rbp, [rsp-38h]
0x180004c06  sub     rsp, 138h
0x180004c0d  mov     rax, cs:__security_cookie
0x180004c14  xor     rax, rsp
0x180004c17  mov     [rbp+70h+var_50], rax
0x180004c1b  cmp     cs:RegHandle, 0
0x180004c23  lea     rbx, aNotAvailable; "Not available"
0x180004c2a  mov     rax, cs:off_18000E020
0x180004c31  mov     r13d, r9d
0x180004c34  mov     [rsp+170h+var_140], r8d
0x180004c39  mov     r14, rdx
0x180004c3c  mov     r15, rcx
0x180004c3f  mov     rsi, rbx
0x180004c42  mov     rdi, rbx
0x180004c45  movups  xmm0, xmmword ptr [rax-10h]
0x180004c49  movdqu  xmmword ptr [rsp+170h+ProviderId.Data1], xmm0
0x180004c4f  jz      short loc_180004C58
0x180004c51  mov     ecx, 5
0x180004c56  int     29h; Win8: RtlFailFast(ecx)
0x180004c58  xorps   xmm0, xmm0
0x180004c5b  lea     r9, RegHandle; RegHandle
0x180004c62  lea     r8, dword_18000E018; CallbackContext
0x180004c69  lea     rdx, _tlgEnableCallback; EnableCallback
0x180004c70  lea     rcx, [rsp+170h+ProviderId]; ProviderId
0x180004c75  movdqu  cs:xmmword_18000E040, xmm0
0x180004c7d  call    cs:__imp_EventRegister
0x180004c83  xor     r8d, r8d
0x180004c86  mov     r12d, 2
0x180004c8c  test    eax, eax
0x180004c8e  jnz     short loc_180004CAE
0x180004c90  mov     r8, cs:off_18000E020
0x180004c97  mov     edx, r12d
0x180004c9a  mov     rcx, cs:RegHandle
0x180004ca1  movzx   r9d, word ptr [r8]
0x180004ca5  call    cs:__imp_EventSetInformation
0x180004cab  xor     r8d, r8d
0x180004cae  test    r15, r15
0x180004cb1  jz      short loc_180004D02
0x180004cb3  mov     rsi, [r15]
0x180004cb6  test    rsi, rsi
0x180004cb9  jnz     short loc_180004CC0
0x180004cbb  mov     rsi, rbx
0x180004cbe  jmp     short loc_180004CDA
0x180004cc0  mov     edx, 5Ch ; '\'; Ch
0x180004cc5  mov     rcx, rsi; Str
0x180004cc8  call    cs:__imp_wcsrchr
0x180004cce  xor     r8d, r8d
0x180004cd1  test    rax, rax
0x180004cd4  jz      short loc_180004CDA
0x180004cd6  lea     rsi, [rax+2]
0x180004cda  mov     rdi, [r15+8]
0x180004cde  test    rdi, rdi
0x180004ce1  jnz     short loc_180004CE8
0x180004ce3  mov     rdi, rbx
0x180004ce6  jmp     short loc_180004D02
0x180004ce8  mov     edx, 5Ch ; '\'; Ch
0x180004ced  mov     rcx, rdi; Str
0x180004cf0  call    cs:__imp_wcsrchr
0x180004cf6  xor     r8d, r8d
0x180004cf9  test    rax, rax
0x180004cfc  jz      short loc_180004D02
0x180004cfe  lea     rdi, [rax+2]
0x180004d02  mov     eax, cs:dword_18000E018
0x180004d08  cmp     eax, 5
0x180004d0b  jbe     loc_180004EE5
0x180004d11  mov     rcx, cs:qword_18000E030
0x180004d18  mov     rdx, 200000000000h
0x180004d22  mov     rax, cs:qword_18000E028
0x180004d29  test    rdx, rax
0x180004d2c  jz      loc_180004EE5
0x180004d32  mov     rax, rcx
0x180004d35  and     rax, rdx
0x180004d38  cmp     rax, rcx
0x180004d3b  jnz     loc_180004EE5
0x180004d41  test    r14, r14
0x180004d44  jz      short loc_180004D54
0x180004d46  mov     eax, [r14+18h]
0x180004d4a  mov     [rsp+170h+var_13C], eax
0x180004d4e  mov     eax, [r14+10h]
0x180004d52  jmp     short loc_180004D5C
0x180004d54  mov     [rsp+170h+var_13C], r8d
0x180004d59  mov     eax, r8d
0x180004d5c  mov     [rsp+170h+var_138], eax
0x180004d60  mov     eax, [rsp+170h+var_140]
0x180004d64  mov     [rsp+170h+var_130], eax
0x180004d68  mov     [rsp+170h+var_134], r13d
0x180004d6d  test    r14, r14
0x180004d70  jz      short loc_180004D7B
0x180004d72  mov     rcx, [r14+8]
0x180004d76  mov     rbx, [r14]
0x180004d79  jmp     short loc_180004D7E
0x180004d7b  mov     rcx, rbx
0x180004d7e  test    r15, r15
0x180004d81  jz      short loc_180004D91
0x180004d83  mov     eax, [r15+10h]
0x180004d87  mov     [rsp+170h+var_140], eax
0x180004d8b  mov     eax, [r15+14h]
0x180004d8f  jmp     short loc_180004D99
0x180004d91  mov     [rsp+170h+var_140], r8d
0x180004d96  mov     eax, r8d
0x180004d99  mov     [rsp+170h+var_12C], eax
0x180004d9d  lea     r10, unk_18000B23C
0x180004da4  lea     rax, [rsp+170h+var_13C]
0x180004da9  mov     [rbp+70h+var_58], 4
0x180004db1  mov     [rbp+70h+var_60], rax
0x180004db5  lea     rax, [rsp+170h+var_138]
0x180004dba  mov     [rbp+70h+var_70], rax
0x180004dbe  lea     rax, [rsp+170h+var_134]
0x180004dc3  mov     [rbp+70h+var_80], rax
0x180004dc7  lea     rax, [rsp+170h+var_130]
0x180004dcc  mov     [rbp+70h+var_90], rax
0x180004dd0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004dd4  mov     [rbp+70h+var_68], 4
0x180004ddc  mov     [rbp+70h+var_78], 4
0x180004de4  mov     [rbp+70h+var_88], 4
0x180004dec  test    rcx, rcx
0x180004def  jz      short loc_180004E07
0x180004df1  mov     rdx, rax
0x180004df4  inc     rdx
0x180004df7  cmp     [rcx+rdx*2], r8w
0x180004dfc  jnz     short loc_180004DF4
0x180004dfe  lea     edx, ds:2[rdx*2]
0x180004e05  jmp     short loc_180004E0D
0x180004e07  mov     rcx, r10
0x180004e0a  mov     edx, r12d
0x180004e0d  mov     [rbp+70h+var_A0], rcx
0x180004e11  mov     [rbp+70h+var_98], edx
0x180004e14  mov     [rbp+70h+var_94], r8d
0x180004e18  test    rbx, rbx
0x180004e1b  jz      short loc_180004E33
0x180004e1d  mov     rcx, rax
0x180004e20  inc     rcx
0x180004e23  cmp     [rbx+rcx*2], r8w
0x180004e28  jnz     short loc_180004E20
0x180004e2a  lea     ecx, ds:2[rcx*2]
0x180004e31  jmp     short loc_180004E39
0x180004e33  mov     rbx, r10
0x180004e36  mov     ecx, r12d
0x180004e39  mov     [rbp+70h+var_A8], ecx
0x180004e3c  lea     rcx, [rsp+170h+var_140]
0x180004e41  mov     [rbp+70h+var_C0], rcx
0x180004e45  lea     rcx, [rsp+170h+var_12C]
0x180004e4a  mov     [rbp+70h+var_D0], rcx
0x180004e4e  mov     [rbp+70h+var_B0], rbx
0x180004e52  mov     [rbp+70h+var_A4], r8d
0x180004e56  mov     [rbp+70h+var_B8], 4
0x180004e5e  mov     [rbp+70h+var_C8], 4
0x180004e66  test    rdi, rdi
0x180004e69  jz      short loc_180004E81
0x180004e6b  mov     rcx, rax
0x180004e6e  inc     rcx
0x180004e71  cmp     [rdi+rcx*2], r8w
0x180004e76  jnz     short loc_180004E6E
0x180004e78  lea     ecx, ds:2[rcx*2]
0x180004e7f  jmp     short loc_180004E87
0x180004e81  mov     rdi, r10
0x180004e84  mov     ecx, r12d
0x180004e87  mov     [rbp+70h+var_E0], rdi
0x180004e8b  mov     [rbp+70h+var_D8], ecx
0x180004e8e  mov     [rbp+70h+var_D4], r8d
0x180004e92  test    rsi, rsi
0x180004e95  jz      short loc_180004EAB
0x180004e97  inc     rax
0x180004e9a  cmp     [rsi+rax*2], r8w
0x180004e9f  jnz     short loc_180004E97
0x180004ea1  lea     r12d, ds:2[rax*2]
0x180004ea9  jmp     short loc_180004EAE
0x180004eab  mov     rsi, r10
0x180004eae  lea     rax, [rsp+170h+var_110]
0x180004eb3  mov     [rbp+70h+var_E4], r8d
0x180004eb7  mov     [rsp+170h+var_148], rax
0x180004ebc  lea     rdx, byte_18000B8D9
0x180004ec3  xor     r9d, r9d
0x180004ec6  mov     [rsp+170h+var_150], 0Ch
0x180004ece  xor     r8d, r8d
0x180004ed1  mov     [rbp+70h+var_F0], rsi
0x180004ed5  lea     rcx, dword_18000E018
0x180004edc  mov     [rbp+70h+var_E8], r12d
0x180004ee0  call    _tlgWriteTransfer_EventWriteTransfer
0x180004ee5  xor     eax, eax
0x180004ee7  mov     rcx, [rbp+70h+var_50]
0x180004eeb  xor     rcx, rsp; StackCookie
0x180004eee  call    __security_check_cookie
0x180004ef3  add     rsp, 138h
0x180004efa  pop     r15
0x180004efc  pop     r14
0x180004efe  pop     r13
0x180004f00  pop     r12
0x180004f02  pop     rdi
0x180004f03  pop     rsi
0x180004f04  pop     rbx
0x180004f05  pop     rbp
0x180004f06  retn
```
