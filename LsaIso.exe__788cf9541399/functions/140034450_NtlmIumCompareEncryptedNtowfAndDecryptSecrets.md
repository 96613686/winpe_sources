# NtlmIumCompareEncryptedNtowfAndDecryptSecrets

- ea: `0x140034450`
- end: `0x1400346f3`
- name: `NtlmIumCompareEncryptedNtowfAndDecryptSecrets`
- size: `675`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140034450`
- `0x140036330`
- `0x140038cd2`
- `0x140038d10`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140034492`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140034492`

## pseudocode

```c
__int64 __fastcall NtlmIumCompareEncryptedNtowfAndDecryptSecrets(__int64 a1, __int64 a2, _OWORD *a3, _OWORD *a4)
{
  _OWORD *v5; // rdi
  __int64 v8; // rbp
  _OWORD *v9; // rcx
  _OWORD *v10; // rax
  __int64 v11; // rdx
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  int v24; // esi
  __int64 v25; // r15
  char v26; // r8
  __int64 v27; // rdx
  char v28; // cl
  char v29; // al
  _OWORD *v30; // rax
  __int64 v31; // rcx
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  _OWORD *v44; // rax
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  __int128 v54; // xmm1
  __int128 v55; // xmm0
  __int128 v56; // xmm1
  _BYTE *v57; // rax
  _BYTE v58[352]; // [rsp+20h] [rbp-2F8h] BYREF
  _BYTE v59[352]; // [rsp+180h] [rbp-198h] BYREF

  v5 = a3;
  if ( qword_140052C50 == a1 )
  {
    v8 = 2;
    v9 = v59;
    v10 = a3;
    v11 = 2;
    do
    {
      v12 = v10[1];
      *v9 = *v10;
      v13 = v10[2];
      v9[1] = v12;
      v14 = v10[3];
      v9[2] = v13;
      v15 = v10[4];
      v9[3] = v14;
      v16 = v10[5];
      v9[4] = v15;
      v17 = v10[6];
      v9[5] = v16;
      v18 = v10[7];
      v10 += 8;
      v9[6] = v17;
      v9[7] = v18;
      v9 += 8;
      --v11;
    }
    while ( v11 );
    v19 = v10[1];
    *v9 = *v10;
    v20 = v10[2];
    v9[1] = v19;
    v21 = v10[3];
    v9[2] = v20;
    v22 = v10[4];
    v9[3] = v21;
    v23 = v10[5];
    v9[4] = v22;
    v9[5] = v23;
    v24 = IumpUnprotectCredential((struct _MSV1_0_SECRETS_WRAPPER *)v59);
    v25 = 352;
    if ( v24 >= 0 )
    {
      if ( v59[9] )
      {
        if ( *(_WORD *)a2 != 16 )
          goto LABEL_17;
        v26 = 0;
        v27 = 0;
        do
        {
          v28 = *(_BYTE *)(v27 + *(_QWORD *)(a2 + 8));
          v29 = v59[v27++ + 38];
          v26 |= v29 ^ v28;
        }
        while ( v27 != 16 );
        if ( v26 )
        {
LABEL_17:
          v24 = -1073741718;
        }
        else
        {
          memset_0(v58, 0, sizeof(v58));
          v30 = v58;
          v31 = 2;
          do
          {
            v32 = v30[1];
            *v5 = *v30;
            v33 = v30[2];
            v5[1] = v32;
            v34 = v30[3];
            v5[2] = v33;
            v35 = v30[4];
            v5[3] = v34;
            v36 = v30[5];
            v5[4] = v35;
            v37 = v30[6];
            v5[5] = v36;
            v38 = v30[7];
            v30 += 8;
            v5[6] = v37;
            v5[7] = v38;
            v5 += 8;
            --v31;
          }
          while ( v31 );
          v39 = v30[1];
          *v5 = *v30;
          v40 = v30[2];
          v5[1] = v39;
          v41 = v30[3];
          v5[2] = v40;
          v42 = v30[4];
          v5[3] = v41;
          v43 = v30[5];
          v44 = v59;
          v5[4] = v42;
          v5[5] = v43;
          do
          {
            v45 = v44[1];
            *a4 = *v44;
            v46 = v44[2];
            a4[1] = v45;
            v47 = v44[3];
            a4[2] = v46;
            v48 = v44[4];
            a4[3] = v47;
            v49 = v44[5];
            a4[4] = v48;
            v50 = v44[6];
            a4[5] = v49;
            v51 = v44[7];
            v44 += 8;
            a4[6] = v50;
            a4[7] = v51;
            a4 += 8;
            --v8;
          }
          while ( v8 );
          v52 = v44[1];
          *a4 = *v44;
          v53 = v44[2];
          a4[1] = v52;
          v54 = v44[3];
          a4[2] = v53;
          v55 = v44[4];
          a4[3] = v54;
          v56 = v44[5];
          a4[4] = v55;
          a4[5] = v56;
        }
      }
      else
      {
        v24 = -1073741637;
      }
    }
    v57 = v59;
    do
    {
      *v57++ = 0;
      --v25;
    }
    while ( v25 );
    return (unsigned int)v24;
  }
  else
  {
    Sleep(5u);
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x140034450  mov     [rsp+arg_0], rbx
0x140034455  mov     [rsp+arg_8], rbp
0x14003445a  push    rsi
0x14003445b  push    rdi
0x14003445c  push    r12
0x14003445e  push    r14
0x140034460  push    r15
0x140034462  sub     rsp, 2F0h
0x140034469  mov     rax, cs:__security_cookie
0x140034470  xor     rax, rsp
0x140034473  mov     [rsp+318h+var_38], rax
0x14003447b  cmp     cs:qword_140052C50, rcx
0x140034482  mov     rbx, r9
0x140034485  mov     rdi, r8
0x140034488  mov     r14, rdx
0x14003448b  jz      short loc_1400344A2
0x14003448d  mov     ecx, 5; dwMilliseconds
0x140034492  call    cs:__imp_Sleep
0x140034498  mov     eax, 0C0000022h
0x14003449d  jmp     loc_1400346C7
0x1400344a2  mov     ebp, 2
0x1400344a7  lea     rcx, [rsp+318h+var_198]
0x1400344af  mov     rax, r8
0x1400344b2  mov     edx, ebp
0x1400344b4  lea     r12d, [rbp+7Eh]
0x1400344b8  movups  xmm0, xmmword ptr [rax]
0x1400344bb  movups  xmm1, xmmword ptr [rax+10h]
0x1400344bf  movups  xmmword ptr [rcx], xmm0
0x1400344c2  movups  xmm0, xmmword ptr [rax+20h]
0x1400344c6  movups  xmmword ptr [rcx+10h], xmm1
0x1400344ca  movups  xmm1, xmmword ptr [rax+30h]
0x1400344ce  movups  xmmword ptr [rcx+20h], xmm0
0x1400344d2  movups  xmm0, xmmword ptr [rax+40h]
0x1400344d6  movups  xmmword ptr [rcx+30h], xmm1
0x1400344da  movups  xmm1, xmmword ptr [rax+50h]
0x1400344de  movups  xmmword ptr [rcx+40h], xmm0
0x1400344e2  movups  xmm0, xmmword ptr [rax+60h]
0x1400344e6  movups  xmmword ptr [rcx+50h], xmm1
0x1400344ea  movups  xmm1, xmmword ptr [rax+70h]
0x1400344ee  add     rax, r12
0x1400344f1  movups  xmmword ptr [rcx+60h], xmm0
0x1400344f5  movups  xmmword ptr [rcx+70h], xmm1
0x1400344f9  add     rcx, r12
0x1400344fc  sub     rdx, 1
0x140034500  jnz     short loc_1400344B8
0x140034502  movups  xmm0, xmmword ptr [rax]
0x140034505  movups  xmm1, xmmword ptr [rax+10h]
0x140034509  movups  xmmword ptr [rcx], xmm0
0x14003450c  movups  xmm0, xmmword ptr [rax+20h]
0x140034510  movups  xmmword ptr [rcx+10h], xmm1
0x140034514  movups  xmm1, xmmword ptr [rax+30h]
0x140034518  movups  xmmword ptr [rcx+20h], xmm0
0x14003451c  movups  xmm0, xmmword ptr [rax+40h]
0x140034520  movups  xmmword ptr [rcx+30h], xmm1
0x140034524  movups  xmm1, xmmword ptr [rax+50h]
0x140034528  movups  xmmword ptr [rcx+40h], xmm0
0x14003452c  movups  xmmword ptr [rcx+50h], xmm1
0x140034530  lea     rcx, [rsp+318h+var_198]; struct _MSV1_0_SECRETS_WRAPPER *
0x140034538  call    ?IumpUnprotectCredential@@YAJPEAU_MSV1_0_SECRETS_WRAPPER@@@Z; IumpUnprotectCredential(_MSV1_0_SECRETS_WRAPPER *)
0x14003453d  mov     esi, eax
0x14003453f  mov     r15d, 160h
0x140034545  test    eax, eax
0x140034547  js      loc_1400346B1
0x14003454d  cmp     [rsp+318h+var_18F], 0
0x140034555  jnz     short loc_140034561
0x140034557  mov     esi, 0C00000BBh
0x14003455c  jmp     loc_1400346B1
0x140034561  mov     r10d, 10h
0x140034567  cmp     [r14], r10w
0x14003456b  jnz     loc_1400346AC
0x140034571  mov     r9, [r14+8]
0x140034575  xor     r8b, r8b
0x140034578  xor     edx, edx
0x14003457a  mov     cl, [rdx+r9]
0x14003457e  mov     al, [rsp+rdx+318h+var_172]
0x140034585  inc     rdx
0x140034588  xor     cl, al
0x14003458a  or      r8b, cl
0x14003458d  cmp     rdx, r10
0x140034590  jnz     short loc_14003457A
0x140034592  test    r8b, r8b
0x140034595  jnz     loc_1400346AC
0x14003459b  mov     r8, r15; Size
0x14003459e  lea     rcx, [rsp+318h+var_2F8]; void *
0x1400345a3  xor     edx, edx; Val
0x1400345a5  call    memset_0
0x1400345aa  lea     rax, [rsp+318h+var_2F8]
0x1400345af  mov     rcx, rbp
0x1400345b2  movups  xmm0, xmmword ptr [rax]
0x1400345b5  movups  xmm1, xmmword ptr [rax+10h]
0x1400345b9  movups  xmmword ptr [rdi], xmm0
0x1400345bc  movups  xmm0, xmmword ptr [rax+20h]
0x1400345c0  movups  xmmword ptr [rdi+10h], xmm1
0x1400345c4  movups  xmm1, xmmword ptr [rax+30h]
0x1400345c8  movups  xmmword ptr [rdi+20h], xmm0
0x1400345cc  movups  xmm0, xmmword ptr [rax+40h]
0x1400345d0  movups  xmmword ptr [rdi+30h], xmm1
0x1400345d4  movups  xmm1, xmmword ptr [rax+50h]
0x1400345d8  movups  xmmword ptr [rdi+40h], xmm0
0x1400345dc  movups  xmm0, xmmword ptr [rax+60h]
0x1400345e0  movups  xmmword ptr [rdi+50h], xmm1
0x1400345e4  movups  xmm1, xmmword ptr [rax+70h]
0x1400345e8  add     rax, r12
0x1400345eb  movups  xmmword ptr [rdi+60h], xmm0
0x1400345ef  movups  xmmword ptr [rdi+70h], xmm1
0x1400345f3  add     rdi, r12
0x1400345f6  sub     rcx, 1
0x1400345fa  jnz     short loc_1400345B2
0x1400345fc  movups  xmm0, xmmword ptr [rax]
0x1400345ff  movups  xmm1, xmmword ptr [rax+10h]
0x140034603  movups  xmmword ptr [rdi], xmm0
0x140034606  movups  xmm0, xmmword ptr [rax+20h]
0x14003460a  movups  xmmword ptr [rdi+10h], xmm1
0x14003460e  movups  xmm1, xmmword ptr [rax+30h]
0x140034612  movups  xmmword ptr [rdi+20h], xmm0
0x140034616  movups  xmm0, xmmword ptr [rax+40h]
0x14003461a  movups  xmmword ptr [rdi+30h], xmm1
0x14003461e  movups  xmm1, xmmword ptr [rax+50h]
0x140034622  lea     rax, [rsp+318h+var_198]
0x14003462a  movups  xmmword ptr [rdi+40h], xmm0
0x14003462e  movups  xmmword ptr [rdi+50h], xmm1
0x140034632  movups  xmm0, xmmword ptr [rax]
0x140034635  movups  xmm1, xmmword ptr [rax+10h]
0x140034639  movups  xmmword ptr [rbx], xmm0
0x14003463c  movups  xmm0, xmmword ptr [rax+20h]
0x140034640  movups  xmmword ptr [rbx+10h], xmm1
0x140034644  movups  xmm1, xmmword ptr [rax+30h]
0x140034648  movups  xmmword ptr [rbx+20h], xmm0
0x14003464c  movups  xmm0, xmmword ptr [rax+40h]
0x140034650  movups  xmmword ptr [rbx+30h], xmm1
0x140034654  movups  xmm1, xmmword ptr [rax+50h]
0x140034658  movups  xmmword ptr [rbx+40h], xmm0
0x14003465c  movups  xmm0, xmmword ptr [rax+60h]
0x140034660  movups  xmmword ptr [rbx+50h], xmm1
0x140034664  movups  xmm1, xmmword ptr [rax+70h]
0x140034668  add     rax, r12
0x14003466b  movups  xmmword ptr [rbx+60h], xmm0
0x14003466f  movups  xmmword ptr [rbx+70h], xmm1
0x140034673  add     rbx, r12
0x140034676  sub     rbp, 1
0x14003467a  jnz     short loc_140034632
0x14003467c  movups  xmm0, xmmword ptr [rax]
0x14003467f  movups  xmm1, xmmword ptr [rax+10h]
0x140034683  movups  xmmword ptr [rbx], xmm0
0x140034686  movups  xmm0, xmmword ptr [rax+20h]
0x14003468a  movups  xmmword ptr [rbx+10h], xmm1
0x14003468e  movups  xmm1, xmmword ptr [rax+30h]
0x140034692  movups  xmmword ptr [rbx+20h], xmm0
0x140034696  movups  xmm0, xmmword ptr [rax+40h]
0x14003469a  movups  xmmword ptr [rbx+30h], xmm1
0x14003469e  movups  xmm1, xmmword ptr [rax+50h]
0x1400346a2  movups  xmmword ptr [rbx+40h], xmm0
0x1400346a6  movups  xmmword ptr [rbx+50h], xmm1
0x1400346aa  jmp     short loc_1400346B1
0x1400346ac  mov     esi, 0C000006Ah
0x1400346b1  lea     rax, [rsp+318h+var_198]
0x1400346b9  mov     byte ptr [rax], 0
0x1400346bc  inc     rax
0x1400346bf  sub     r15, 1
0x1400346c3  jnz     short loc_1400346B9
0x1400346c5  mov     eax, esi
0x1400346c7  mov     rcx, [rsp+318h+var_38]
0x1400346cf  xor     rcx, rsp; StackCookie
0x1400346d2  call    __security_check_cookie
0x1400346d7  lea     r11, [rsp+318h+var_28]
0x1400346df  mov     rbx, [r11+30h]
0x1400346e3  mov     rbp, [r11+38h]
0x1400346e7  mov     rsp, r11
0x1400346ea  pop     r15
0x1400346ec  pop     r14
0x1400346ee  pop     r12
0x1400346f0  pop     rdi
0x1400346f1  pop     rsi
0x1400346f2  retn
```
