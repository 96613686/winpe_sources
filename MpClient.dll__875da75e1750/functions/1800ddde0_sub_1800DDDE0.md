# sub_1800DDDE0

- ea: `0x1800ddde0`
- end: `0x1800de6d0`
- name: `sub_1800DDDE0`
- size: `2288`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update`

## callers

- `0x1800dd3b4`

## callees

- `0x180002784`
- `0x18001b270`
- `0x18001bb0c`
- `0x18001bb14`
- `0x18001e9b8`
- `0x18001ef60`
- `0x1800217f0`
- `0x180021a44`
- `0x18003b830`
- `0x18003bcc8`
- `0x1800733a8`
- `0x1800733fc`
- `0x18007b188`
- `0x180088620`
- `0x18008ca50`
- `0x1800c7598`
- `0x1800c76d0`
- `0x1800cb1b4`
- `0x1800dd850`
- `0x1800ddb98`
- `0x1800ddde0`
- `0x1800dead4`
- `0x180125920`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800de669`
- `KERNEL32!HeapFree` at `0x1800de669`

## string_xrefs

- `0x1800dde7a`: `Signature Updates`
- `0x1800de24b`: `Signature Updates`
- `0x1800de2a2`: `SignaturesLastUpdated`
- `0x1800dde73`: `DefinitionUpdateFileSharesSources`

## pseudocode

```c
void __fastcall sub_1800DDDE0(__int64 a1)
{
  int v1; // eax
  int v2; // ebx
  int v3; // r14d
  int v4; // r12d
  int v5; // eax
  int v6; // eax
  __int64 v7; // r15
  int v8; // eax
  _QWORD *v9; // rcx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  _QWORD *v14; // r10
  LPVOID v15; // rbx
  unsigned int v16; // eax
  struct _RTL_CRITICAL_SECTION *v17; // r15
  const wchar_t *v18; // r9
  LPVOID v19; // rbx
  __int64 v20; // rcx
  int v21; // eax
  unsigned __int8 v22; // [rsp+E0h] [rbp-D8h] BYREF
  unsigned __int8 v23; // [rsp+E1h] [rbp-D7h] BYREF
  char v24; // [rsp+E2h] [rbp-D6h] BYREF
  int v25; // [rsp+E4h] [rbp-D4h] BYREF
  int v26; // [rsp+E8h] [rbp-D0h] BYREF
  int v27; // [rsp+ECh] [rbp-CCh] BYREF
  int v28; // [rsp+F0h] [rbp-C8h] BYREF
  int v29; // [rsp+F4h] [rbp-C4h] BYREF
  int v30; // [rsp+F8h] [rbp-C0h] BYREF
  int v31; // [rsp+FCh] [rbp-BCh] BYREF
  int v32; // [rsp+100h] [rbp-B8h] BYREF
  int v33; // [rsp+104h] [rbp-B4h] BYREF
  int v34; // [rsp+108h] [rbp-B0h] BYREF
  int v35; // [rsp+10Ch] [rbp-ACh] BYREF
  __int64 v36; // [rsp+110h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+118h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+120h] [rbp-98h] BYREF
  __int64 v39; // [rsp+128h] [rbp-90h] BYREF
  __int64 v40; // [rsp+130h] [rbp-88h] BYREF
  __int64 v41; // [rsp+138h] [rbp-80h] BYREF
  __int64 v42; // [rsp+140h] [rbp-78h] BYREF
  __int64 v43; // [rsp+148h] [rbp-70h] BYREF
  __int64 v44; // [rsp+150h] [rbp-68h] BYREF
  __int64 v45; // [rsp+158h] [rbp-60h] BYREF
  __int64 v46; // [rsp+160h] [rbp-58h]
  LPVOID v47; // [rsp+178h] [rbp-40h] BYREF
  __int64 v48; // [rsp+180h] [rbp-38h] BYREF
  LPVOID v49; // [rsp+188h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+190h] [rbp-28h] BYREF

  v46 = a1;
  v36 = a1;
  v1 = sub_1800CB1B4(0, 0);
  if ( v1 < 0 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 2) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 14, &stru_18014B648, (unsigned int)v1);
    return;
  }
  lpMem = 0;
  v2 = sub_1800C76D0(&lpMem, L"Signature Updates", L"DefinitionUpdateFileSharesSources", 0);
  v3 = 0;
  v27 = 0;
  if ( v2 == -2147024894 || (unsigned __int8)sub_1800217F0(lpMem) )
  {
    v3 = 1;
    v27 = 1;
  }
  if ( v2 < 0 && off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
    sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 15, &stru_18014B648, (unsigned int)v2);
  v4 = 0;
  v25 = 0;
  if ( lpMem && !v3 )
  {
    v49 = 0;
    v5 = sub_18001E9B8(&v49, lpMem);
    if ( v5 < 0 && off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 16, &stru_18014B648, (unsigned int)v5);
    v47 = 0;
    v48 = 0;
    v6 = sub_180021A44((unsigned int)&v48, (unsigned int)&v47, (_DWORD)v49, (unsigned int)L"|", 1, -1);
    v2 = v6;
    if ( v6 >= 0 )
    {
      v7 = 0;
      if ( v48 )
      {
        while ( 1 )
        {
          v8 = sub_18001EF60(*((_QWORD *)v47 + v7));
          v2 = v8;
          if ( !v8 )
            break;
          v9 = off_18019DE80;
          if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          {
            sub_1800733FC(*((_QWORD *)off_18019DE80 + 2), 18, (unsigned int)&stru_18014B648, *((_QWORD *)v47 + v7), v8);
            v9 = off_18019DE80;
          }
          v2 = 0;
          if ( ++v7 >= (unsigned __int64)v48 )
            goto LABEL_32;
        }
        v4 = 1;
        v25 = 1;
      }
      v9 = off_18019DE80;
LABEL_32:
      if ( v2 < 0 && v9 != &off_18019DE80 && (*((_BYTE *)v9 + 28) & 1) != 0 )
        sub_1800733A8(v9[2], 19, &stru_18014B648, (unsigned int)v2);
    }
    else
    {
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
        sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 17, &stru_18014B648, (unsigned int)v6);
      v2 = 0;
    }
    if ( v47 )
      sub_18003BCC8(v47);
    if ( v49 )
      sub_18003BCC8(v49);
  }
  v25 = 0;
  if ( (int)sub_1800C7598(&v25, L".", L"ProductFeature", 0) < 0
    && off_18019DE80 != (_UNKNOWN *)&off_18019DE80
    && (*((_BYTE *)off_18019DE80 + 28) & 2) != 0 )
  {
    sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 20, &stru_18014B648, (unsigned int)v2);
  }
  v24 = 0;
  v23 = 0;
  v22 = 0;
  v10 = sub_1800DDB98((bool *)&v24);
  if ( v10 < 0 && off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 2) != 0 )
    sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 21, &stru_18014B648, (unsigned int)v10);
  v11 = sub_1800DD850(&v22, 2);
  if ( v11 < 0 && off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 2) != 0 )
    sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 22, &stru_18014B648, (unsigned int)v11);
  v12 = sub_1800DD850(&v23, 1);
  if ( v12 < 0 && off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 2) != 0 )
    sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 23, &stru_18014B648, (unsigned int)v12);
  v47 = 0;
  v48 = 0;
  v13 = MpConfigOpen((__int64)L"Signature Updates", (__int64)&v47);
  if ( v13 >= 0 )
  {
    v15 = v47;
    v16 = sub_18008CA50(v47, L"SignaturesLastUpdated", &v48);
    if ( (int)(v16 + 0x80000000) >= 0 && v16 != -2147024894 )
    {
      v14 = off_18019DE80;
      if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
        goto LABEL_67;
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 25, &stru_18014B648, v16);
    }
    goto LABEL_66;
  }
  v14 = off_18019DE80;
  if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
  {
    sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 24, &stru_18014B648, (unsigned int)v13);
    v15 = v47;
LABEL_66:
    v14 = off_18019DE80;
    goto LABEL_67;
  }
  v15 = v47;
LABEL_67:
  v17 = lpCriticalSection;
  if ( lpCriticalSection )
  {
    EnterCriticalSection(lpCriticalSection);
    if ( (unsigned int)dword_18019D000 > 5
      && (*(_QWORD *)algn_18019D010 & 0x400000000000LL) != 0
      && (*(_QWORD *)&algn_18019D010[8] & 0x400000000000LL) == *(_QWORD *)&algn_18019D010[8] )
    {
      v37 = v48;
      v27 = v22;
      v26 = v23;
      v28 = v25;
      v29 = (unsigned __int8)v24;
      v30 = v4;
      v31 = v3;
      v38 = v36;
      v32 = *(_DWORD *)(qword_1801A6308 + 72);
      v33 = *(_DWORD *)(qword_1801A6308 + 68);
      v34 = *(_DWORD *)(qword_1801A6308 + 64);
      v35 = *(unsigned __int8 *)(qword_1801A6308 + 60);
      LODWORD(v36) = *(unsigned __int8 *)(qword_1801A6308 + 59);
      LODWORD(v49) = *(unsigned __int8 *)(qword_1801A6308 + 58);
      LODWORD(v48) = *(unsigned __int8 *)(qword_1801A6308 + 57);
      LODWORD(v47) = *(unsigned __int8 *)(qword_1801A6308 + 56);
      v39 = *(_QWORD *)(qword_1801A6308 + 48);
      v40 = *(_QWORD *)(qword_1801A6308 + 40);
      v41 = *(_QWORD *)(qword_1801A6308 + 32);
      v42 = *(_QWORD *)(qword_1801A6308 + 24);
      v43 = *(_QWORD *)(qword_1801A6308 + 16);
      v44 = *(_QWORD *)(qword_1801A6308 + 8);
      v45 = 0x2000000;
      sub_180002784(
        (int)&dword_18019D000,
        (int)&dword_18017D76C,
        (__int64)&v45,
        (__int64)&v44,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v47,
        (__int64)&v48,
        (__int64)&v49,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v38,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v26,
        (__int64)&v27,
        (__int64)&v37);
    }
    LeaveCriticalSection(v17);
    v14 = off_18019DE80;
  }
  if ( v14 != &off_18019DE80 && (*((_BYTE *)v14 + 28) & 2) != 0 )
  {
    LODWORD(v18) = v46;
    if ( !v46 )
      v18 = L"NULL";
    sub_1800DEAD4(v14[2], (unsigned __int8)v24, (unsigned int)L"NULL", (_DWORD)v18, v3, v4, v24, v25, v23, v22);
  }
  if ( v15 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 8LL))(v15);
  v19 = lpMem;
  if ( lpMem )
  {
    if ( qword_1801A9738 )
    {
      if ( !HeapFree(qword_1801A9738, 0, lpMem) )
      {
        v21 = sub_18001B270(v20);
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v19, v21);
      }
    }
  }
}

```

## disassembly

```asm
0x1800ddde0  mov     [rsp+arg_8], rbx
0x1800ddde5  mov     [rsp+arg_10], rsi
0x1800dddea  push    r12
0x1800dddec  push    r14
0x1800dddee  push    r15
0x1800dddf0  sub     rsp, 1A0h
0x1800dddf7  mov     rax, cs:__security_cookie
0x1800dddfe  xor     rax, rsp
0x1800dde01  mov     [rsp+1B8h+var_20], rax
0x1800dde09  mov     [rsp+1B8h+var_58], rcx
0x1800dde11  mov     [rsp+1B8h+var_A8], rcx
0x1800dde19  xor     edx, edx
0x1800dde1b  xor     ecx, ecx
0x1800dde1d  call    sub_1800CB1B4
0x1800dde22  test    eax, eax
0x1800dde24  jns     short loc_1800DDE64
0x1800dde26  lea     rsi, off_18019DE80
0x1800dde2d  mov     rcx, cs:off_18019DE80
0x1800dde34  cmp     rcx, rsi
0x1800dde37  jz      loc_1800DE6A6
0x1800dde3d  test    byte ptr [rcx+1Ch], 2
0x1800dde41  jz      loc_1800DE6A6
0x1800dde47  mov     edx, 0Eh
0x1800dde4c  mov     r9d, eax
0x1800dde4f  lea     r8, stru_18014B648
0x1800dde56  mov     rcx, [rcx+10h]
0x1800dde5a  call    sub_1800733A8
0x1800dde5f  jmp     loc_1800DE6A6
0x1800dde64  mov     [rsp+1B8h+lpMem], 0
0x1800dde70  xor     r9d, r9d
0x1800dde73  lea     r8, aDefinitionupda; "DefinitionUpdateFileSharesSources"
0x1800dde7a  lea     rdx, aSignatureUpdat; "Signature Updates"
0x1800dde81  lea     rcx, [rsp+1B8h+lpMem]
0x1800dde89  call    sub_1800C76D0
0x1800dde8e  mov     ebx, eax
0x1800dde90  xor     r14d, r14d
0x1800dde93  mov     dword ptr [rsp+1B8h+var_D0+4], r14d
0x1800dde9b  cmp     eax, 80070002h
0x1800ddea0  jz      short loc_1800DDEB3
0x1800ddea2  mov     rcx, [rsp+1B8h+lpMem]
0x1800ddeaa  call    sub_1800217F0
0x1800ddeaf  test    al, al
0x1800ddeb1  jz      short loc_1800DDEC1
0x1800ddeb3  mov     r14d, 1
0x1800ddeb9  mov     dword ptr [rsp+1B8h+var_D0+4], r14d
0x1800ddec1  test    ebx, ebx
0x1800ddec3  jns     short loc_1800DDEF8
0x1800ddec5  lea     rsi, off_18019DE80
0x1800ddecc  mov     rcx, cs:off_18019DE80
0x1800dded3  cmp     rcx, rsi
0x1800dded6  jz      short loc_1800DDEFF
0x1800dded8  test    byte ptr [rcx+1Ch], 1
0x1800ddedc  jz      short loc_1800DDEFF
0x1800ddede  mov     edx, 0Fh
0x1800ddee3  mov     r9d, ebx
0x1800ddee6  lea     r8, stru_18014B648
0x1800ddeed  mov     rcx, [rcx+10h]
0x1800ddef1  call    sub_1800733A8
0x1800ddef6  jmp     short loc_1800DDEFF
0x1800ddef8  lea     rsi, off_18019DE80
0x1800ddeff  xor     r12d, r12d
0x1800ddf02  mov     [rsp+1B8h+var_D4], r12d
0x1800ddf0a  mov     rdx, [rsp+1B8h+lpMem]
0x1800ddf12  test    rdx, rdx
0x1800ddf15  jz      loc_1800DE101
0x1800ddf1b  test    r14d, r14d
0x1800ddf1e  jnz     loc_1800DE101
0x1800ddf24  mov     [rsp+1B8h+var_30], r12
0x1800ddf2c  lea     rcx, [rsp+1B8h+var_30]
0x1800ddf34  call    sub_18001E9B8
0x1800ddf39  test    eax, eax
0x1800ddf3b  jns     short loc_1800DDF67
0x1800ddf3d  mov     rcx, cs:off_18019DE80
0x1800ddf44  cmp     rcx, rsi
0x1800ddf47  jz      short loc_1800DDF67
0x1800ddf49  test    byte ptr [rcx+1Ch], 1
0x1800ddf4d  jz      short loc_1800DDF67
0x1800ddf4f  lea     edx, [r12+10h]
0x1800ddf54  mov     r9d, eax
0x1800ddf57  lea     r8, stru_18014B648
0x1800ddf5e  mov     rcx, [rcx+10h]
0x1800ddf62  call    sub_1800733A8
0x1800ddf67  mov     [rsp+1B8h+var_40], r12
0x1800ddf6f  mov     [rsp+1B8h+var_38], r12
0x1800ddf77  mov     [rsp+1B8h+var_190], 0FFFFFFFFFFFFFFFFh
0x1800ddf80  mov     byte ptr [rsp+1B8h+var_198], 1
0x1800ddf85  lea     r9, asc_180148044; "|"
0x1800ddf8c  mov     r8, [rsp+1B8h+var_30]
0x1800ddf94  lea     rdx, [rsp+1B8h+var_40]
0x1800ddf9c  lea     rcx, [rsp+1B8h+var_38]
0x1800ddfa4  call    sub_180021A44
0x1800ddfa9  mov     ebx, eax
0x1800ddfab  test    eax, eax
0x1800ddfad  jns     short loc_1800DDFE0
0x1800ddfaf  mov     rcx, cs:off_18019DE80
0x1800ddfb6  cmp     rcx, rsi
0x1800ddfb9  jz      short loc_1800DDFD9
0x1800ddfbb  test    byte ptr [rcx+1Ch], 1
0x1800ddfbf  jz      short loc_1800DDFD9
0x1800ddfc1  mov     edx, 11h
0x1800ddfc6  mov     r9d, eax
0x1800ddfc9  lea     r8, stru_18014B648
0x1800ddfd0  mov     rcx, [rcx+10h]
0x1800ddfd4  call    sub_1800733A8
0x1800ddfd9  xor     ebx, ebx
0x1800ddfdb  jmp     loc_1800DE0DD
0x1800ddfe0  xor     r15d, r15d
0x1800ddfe3  cmp     [rsp+1B8h+var_38], r15
0x1800ddfeb  jbe     short loc_1800DE061
0x1800ddfed  mov     rcx, [rsp+1B8h+var_40]
0x1800ddff5  mov     rcx, [rcx+r15*8]
0x1800ddff9  call    sub_18001EF60
0x1800ddffe  mov     ebx, eax
0x1800de000  test    eax, eax
0x1800de002  jz      short loc_1800DE053
0x1800de004  mov     rcx, cs:off_18019DE80
0x1800de00b  cmp     rcx, rsi
0x1800de00e  jz      short loc_1800DE042
0x1800de010  test    byte ptr [rcx+1Ch], 1
0x1800de014  jz      short loc_1800DE042
0x1800de016  mov     edx, 12h
0x1800de01b  mov     dword ptr [rsp+1B8h+var_198], eax
0x1800de01f  mov     r9, [rsp+1B8h+var_40]
0x1800de027  mov     r9, [r9+r15*8]
0x1800de02b  lea     r8, stru_18014B648
0x1800de032  mov     rcx, [rcx+10h]
0x1800de036  call    sub_1800733FC
0x1800de03b  mov     rcx, cs:off_18019DE80
0x1800de042  xor     ebx, ebx
0x1800de044  inc     r15
0x1800de047  cmp     r15, [rsp+1B8h+var_38]
0x1800de04f  jb      short loc_1800DDFED
0x1800de051  jmp     short loc_1800DE068
0x1800de053  mov     r12d, 1
0x1800de059  mov     [rsp+1B8h+var_D4], r12d
0x1800de061  mov     rcx, cs:off_18019DE80
0x1800de068  jmp     short loc_1800DE0B6
0x1800de06a  lea     rsi, off_18019DE80
0x1800de071  mov     ebx, dword ptr [rsp+1B8h+var_D0]
0x1800de078  mov     r14d, dword ptr [rsp+1B8h+var_D0+4]
0x1800de080  mov     r12d, [rsp+1B8h+var_D4]
0x1800de088  mov     rcx, cs:off_18019DE80
0x1800de08f  jmp     short loc_1800DE0BA
0x1800de091  lea     rsi, off_18019DE80
0x1800de098  mov     ebx, dword ptr [rsp+1B8h+var_D0]
0x1800de09f  mov     r14d, dword ptr [rsp+1B8h+var_D0+4]
0x1800de0a7  mov     r12d, [rsp+1B8h+var_D4]
0x1800de0af  mov     rcx, cs:off_18019DE80
0x1800de0b6  test    ebx, ebx
0x1800de0b8  jns     short loc_1800DE0DD
0x1800de0ba  cmp     rcx, rsi
0x1800de0bd  jz      short loc_1800DE0DD
0x1800de0bf  test    byte ptr [rcx+1Ch], 1
0x1800de0c3  jz      short loc_1800DE0DD
0x1800de0c5  mov     edx, 13h
0x1800de0ca  mov     r9d, ebx
0x1800de0cd  lea     r8, stru_18014B648
0x1800de0d4  mov     rcx, [rcx+10h]
0x1800de0d8  call    sub_1800733A8
0x1800de0dd  mov     rcx, [rsp+1B8h+var_40]; lpMem
0x1800de0e5  test    rcx, rcx
0x1800de0e8  jz      short loc_1800DE0EF
0x1800de0ea  call    sub_18003BCC8
0x1800de0ef  mov     rcx, [rsp+1B8h+var_30]; lpMem
0x1800de0f7  test    rcx, rcx
0x1800de0fa  jz      short loc_1800DE101
0x1800de0fc  call    sub_18003BCC8
0x1800de101  mov     [rsp+1B8h+var_D4], 0
0x1800de10c  xor     r9d, r9d
0x1800de10f  lea     r8, aProductfeature; "ProductFeature"
0x1800de116  lea     rdx, asc_1801457FC; "."
0x1800de11d  lea     rcx, [rsp+1B8h+var_D4]
0x1800de125  call    sub_1800C7598
0x1800de12a  test    eax, eax
0x1800de12c  jns     short loc_1800DE158
0x1800de12e  mov     rcx, cs:off_18019DE80
0x1800de135  cmp     rcx, rsi
0x1800de138  jz      short loc_1800DE158
0x1800de13a  test    byte ptr [rcx+1Ch], 2
0x1800de13e  jz      short loc_1800DE158
0x1800de140  mov     edx, 14h
0x1800de145  mov     r9d, ebx
0x1800de148  lea     r8, stru_18014B648
0x1800de14f  mov     rcx, [rcx+10h]
0x1800de153  call    sub_1800733A8
0x1800de158  mov     [rsp+1B8h+var_D6], 0
0x1800de160  mov     [rsp+1B8h+var_D7], 0
0x1800de168  mov     [rsp+1B8h+var_D8], 0
0x1800de170  lea     rcx, [rsp+1B8h+var_D6]
0x1800de178  call    sub_1800DDB98
0x1800de17d  test    eax, eax
0x1800de17f  jns     short loc_1800DE1AB
0x1800de181  mov     rcx, cs:off_18019DE80
0x1800de188  cmp     rcx, rsi
0x1800de18b  jz      short loc_1800DE1AB
0x1800de18d  test    byte ptr [rcx+1Ch], 2
0x1800de191  jz      short loc_1800DE1AB
0x1800de193  mov     edx, 15h
0x1800de198  mov     r9d, eax
0x1800de19b  lea     r8, stru_18014B648
0x1800de1a2  mov     rcx, [rcx+10h]
0x1800de1a6  call    sub_1800733A8
0x1800de1ab  mov     edx, 2
0x1800de1b0  lea     rcx, [rsp+1B8h+var_D8]
0x1800de1b8  call    sub_1800DD850
0x1800de1bd  test    eax, eax
0x1800de1bf  jns     short loc_1800DE1EB
0x1800de1c1  mov     rcx, cs:off_18019DE80
0x1800de1c8  cmp     rcx, rsi
0x1800de1cb  jz      short loc_1800DE1EB
0x1800de1cd  test    byte ptr [rcx+1Ch], 2
0x1800de1d1  jz      short loc_1800DE1EB
0x1800de1d3  mov     edx, 16h
0x1800de1d8  mov     r9d, eax
0x1800de1db  lea     r8, stru_18014B648
0x1800de1e2  mov     rcx, [rcx+10h]
0x1800de1e6  call    sub_1800733A8
0x1800de1eb  mov     edx, 1
0x1800de1f0  lea     rcx, [rsp+1B8h+var_D7]
0x1800de1f8  call    sub_1800DD850
0x1800de1fd  test    eax, eax
0x1800de1ff  jns     short loc_1800DE22B
0x1800de201  mov     rcx, cs:off_18019DE80
0x1800de208  cmp     rcx, rsi
0x1800de20b  jz      short loc_1800DE22B
0x1800de20d  test    byte ptr [rcx+1Ch], 2
0x1800de211  jz      short loc_1800DE22B
0x1800de213  mov     edx, 17h
0x1800de218  mov     r9d, eax
0x1800de21b  lea     r8, stru_18014B648
0x1800de222  mov     rcx, [rcx+10h]
0x1800de226  call    sub_1800733A8
0x1800de22b  mov     [rsp+1B8h+var_40], 0
0x1800de237  mov     [rsp+1B8h+var_38], 0
0x1800de243  lea     rdx, [rsp+1B8h+var_40]
0x1800de24b  lea     rcx, aSignatureUpdat; "Signature Updates"
0x1800de252  call    MpConfigOpen
0x1800de257  test    eax, eax
0x1800de259  jns     short loc_1800DE29A
0x1800de25b  mov     r10, cs:off_18019DE80
0x1800de262  cmp     r10, rsi
0x1800de265  jz      short loc_1800DE290
0x1800de267  test    byte ptr [r10+1Ch], 1
0x1800de26c  jz      short loc_1800DE290
0x1800de26e  mov     edx, 18h
0x1800de273  mov     r9d, eax
0x1800de276  lea     r8, stru_18014B648
0x1800de27d  mov     rcx, [r10+10h]
0x1800de281  call    sub_1800733A8
0x1800de286  mov     rbx, [rsp+1B8h+var_40]
0x1800de28e  jmp     short loc_1800DE2F7
0x1800de290  mov     rbx, [rsp+1B8h+var_40]
0x1800de298  jmp     short loc_1800DE2FE
0x1800de29a  lea     r8, [rsp+1B8h+var_38]
0x1800de2a2  lea     rdx, aSignatureslast; "SignaturesLastUpdated"
0x1800de2a9  mov     rbx, [rsp+1B8h+var_40]
0x1800de2b1  mov     rcx, rbx
0x1800de2b4  call    sub_18008CA50
0x1800de2b9  mov     edx, 80000000h
0x1800de2be  lea     ecx, [rax+rdx]
0x1800de2c1  test    edx, ecx
0x1800de2c3  jnz     short loc_1800DE2F7
0x1800de2c5  cmp     eax, 80070002h
0x1800de2ca  jz      short loc_1800DE2F7
0x1800de2cc  mov     r10, cs:off_18019DE80
0x1800de2d3  cmp     r10, rsi
0x1800de2d6  jz      short loc_1800DE2FE
0x1800de2d8  test    byte ptr [r10+1Ch], 1
0x1800de2dd  jz      short loc_1800DE2FE
0x1800de2df  mov     edx, 19h
0x1800de2e4  mov     r9d, eax
0x1800de2e7  lea     r8, stru_18014B648
0x1800de2ee  mov     rcx, [r10+10h]
0x1800de2f2  call    sub_1800733A8
0x1800de2f7  mov     r10, cs:off_18019DE80
0x1800de2fe  mov     r15, cs:lpCriticalSection
0x1800de305  test    r15, r15
0x1800de308  jz      loc_1800DE5D1
0x1800de30e  mov     rcx, r15; lpCriticalSection
0x1800de311  call    EnterCriticalSection
0x1800de316  mov     r8, cs:off_180132D58
0x1800de31d  cmp     dword ptr [r8], 5
0x1800de321  jbe     loc_1800DE5C2
0x1800de327  mov     rcx, 400000000000h
0x1800de331  test    [r8+10h], rcx
0x1800de335  jz      loc_1800DE5C2
0x1800de33b  mov     rax, [r8+18h]
0x1800de33f  and     rax, rcx
0x1800de342  cmp     rax, [r8+18h]
0x1800de346  jnz     loc_1800DE5C2
0x1800de34c  mov     rax, [rsp+1B8h+var_38]
0x1800de354  mov     [rsp+1B8h+var_A0], rax
0x1800de35c  movzx   eax, [rsp+1B8h+var_D8]
0x1800de364  mov     dword ptr [rsp+1B8h+var_D0+4], eax
0x1800de36b  movzx   eax, [rsp+1B8h+var_D7]
0x1800de373  mov     dword ptr [rsp+1B8h+var_D0], eax
0x1800de37a  mov     eax, [rsp+1B8h+var_D4]
0x1800de381  mov     dword ptr [rsp+1B8h+var_C8], eax
0x1800de388  movzx   eax, [rsp+1B8h+var_D6]
0x1800de390  mov     dword ptr [rsp+1B8h+var_C8+4], eax
  ... truncated ...
```
