# BLoadAndInitOemPlugins

- ea: `0x180027964`
- end: `0x180027d95`
- name: `BLoadAndInitOemPlugins`
- size: `1073`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025780`

## callees

- `0x180027964`
- `0x180027d9c`
- `0x18003664c`
- `0x18003dd9c`
- `0x18004ec64`
- `0x180075010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800279e3`
- `KERNEL32!LocalAlloc` at `0x1800279e3`
- `KERNEL32!GetProcAddress` at `0x180027d5d`
- `KERNEL32!GetProcAddress` at `0x180027d5d`

## pseudocode

```c
__int64 __fastcall BLoadAndInitOemPlugins(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v3; // rax
  int v4; // r8d
  HLOCAL v5; // rax
  FARPROC v6; // rdx
  __int64 v7; // r8
  __int64 v9; // rax
  int v10; // r12d
  __int64 v11; // rbx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // r11
  __int64 v15; // r15
  __int64 v16; // r14
  __int64 v17; // r10
  __int64 v18; // rbp
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  int v23; // ecx
  __int64 v24; // rax
  int v25; // esi
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // rax
  int i; // ecx
  __int64 v34; // r9
  unsigned int (__fastcall *v35)(__int64, __int64, __int128 *); // rax
  HMODULE v36; // rcx
  FARPROC ProcAddress; // rax
  __int128 v38; // [rsp+30h] [rbp-38h] BYREF
  int v39; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 1720);
  *(_QWORD *)(a1 + 56) = &off_180077F20;
  v38 = 0;
  v3 = PGetOemPluginInfo(a1, *(void **)(v1 + 24), v1);
  *(_QWORD *)(a1 + 1880) = v3;
  if ( !v3 || !(unsigned int)BLoadOEMPluginModulesInternal(a1, v3, v4) )
    return 0;
  **(_QWORD **)(a1 + 1880) = a1;
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 1880) + 8LL) )
  {
    v5 = LocalAlloc(0x40u, 0x300u);
    *(_QWORD *)(a1 + 1896) = v5;
    if ( !v5 )
      return 0;
    v9 = *(_QWORD *)(a1 + 1880);
    v10 = *(_DWORD *)(v9 + 8);
    v11 = v9 + 24;
    if ( v10 )
    {
      while ( 1 )
      {
        v12 = *(_QWORD *)(v11 + 32);
        if ( v12 )
          break;
LABEL_32:
        v11 += 176;
        if ( !--v10 )
          goto LABEL_33;
      }
      *(_QWORD *)(a1 + 32) = v12;
      *(_QWORD *)(a1 + 8) = *(_QWORD *)(v11 + 40);
      *(_QWORD *)(a1 + 48) = *(_QWORD *)(v11 + 56);
      v38 = 0;
      if ( *(_QWORD *)(v11 + 72) )
      {
        v13 = HComOEMEnableDriver(v11, v6, v7, &v38);
        if ( v13 == -2147467263 )
        {
LABEL_10:
          v14 = *(_QWORD *)IID_IPrintOemUni.Data4;
          v15 = 0;
          v16 = *(_QWORD *)&IID_IPrintOemUni.Data1;
          v17 = *(_QWORD *)IID_IPrintOemUni2.Data4;
          v18 = *(_QWORD *)&IID_IPrintOemUni2.Data1;
          v7 = *(_QWORD *)IID_IPrintOemUni3.Data4;
          v19 = *(_QWORD *)&IID_IPrintOemUni3.Data1;
          while ( 1 )
          {
            v20 = *(_QWORD *)(v11 + 72);
            if ( v20 )
            {
              v21 = *(_QWORD *)(v11 + 80) - v16;
              if ( !v21 )
                v21 = *(_QWORD *)(v11 + 88) - v14;
              if ( !v21 )
                goto LABEL_15;
              v29 = *(_QWORD *)(v11 + 80) - v18;
              if ( !v29 )
                v29 = *(_QWORD *)(v11 + 88) - v17;
              if ( !v29 )
                goto LABEL_15;
              v30 = *(_QWORD *)(v11 + 80) - v19;
              if ( !v30 )
                v30 = *(_QWORD *)(v11 + 88) - v7;
              if ( v30 )
              {
                v23 = -2147467262;
              }
              else
              {
LABEL_15:
                v22 = (*(__int64 (__fastcall **)(__int64, char *, __int64, __int64))(*(_QWORD *)v20 + 88LL))(
                        v20,
                        COMUnidrvProcNames[v15],
                        v7,
                        v19);
                v14 = *(_QWORD *)IID_IPrintOemUni.Data4;
                v23 = v22;
                v17 = *(_QWORD *)IID_IPrintOemUni2.Data4;
                v7 = *(_QWORD *)IID_IPrintOemUni3.Data4;
                v19 = *(_QWORD *)&IID_IPrintOemUni3.Data1;
                v16 = *(_QWORD *)&IID_IPrintOemUni.Data1;
                v18 = *(_QWORD *)&IID_IPrintOemUni2.Data1;
              }
              v6 = (FARPROC)v11;
              if ( v23 )
                v6 = 0;
            }
            else
            {
              v36 = *(HMODULE *)(v11 + 32);
              if ( !v36 )
                goto LABEL_31;
              ProcAddress = GetProcAddress(v36, off_180078530[v15]);
              v14 = *(_QWORD *)IID_IPrintOemUni.Data4;
              v6 = ProcAddress;
              v16 = *(_QWORD *)&IID_IPrintOemUni.Data1;
              v17 = *(_QWORD *)IID_IPrintOemUni2.Data4;
              v18 = *(_QWORD *)&IID_IPrintOemUni2.Data1;
              v7 = *(_QWORD *)IID_IPrintOemUni3.Data4;
              v19 = *(_QWORD *)&IID_IPrintOemUni3.Data1;
            }
            if ( !v6 )
              goto LABEL_31;
            v24 = *(_QWORD *)(a1 + 1896);
            v25 = v15 + 32;
            if ( *(_QWORD *)(v24 + 16LL * ((int)v15 + 32)) )
              goto LABEL_31;
            *(_QWORD *)(v24 + 16LL * v25) = v6;
            v26 = *(_QWORD *)(a1 + 1896);
            v39 = 0;
            *(_QWORD *)(v26 + 16LL * v25 + 8) = v11;
            if ( (_DWORD)v15 == 13 )
            {
              v18 = *(_QWORD *)&IID_IPrintOemUni2.Data1;
              v17 = *(_QWORD *)IID_IPrintOemUni2.Data4;
              v27 = *(_QWORD *)(v11 + 80) - *(_QWORD *)&IID_IPrintOemUni2.Data1;
              if ( !v27 )
                v27 = *(_QWORD *)(v11 + 88) - *(_QWORD *)IID_IPrintOemUni2.Data4;
              if ( v27 )
              {
                v19 = *(_QWORD *)&IID_IPrintOemUni3.Data1;
                v7 = *(_QWORD *)IID_IPrintOemUni3.Data4;
                v28 = *(_QWORD *)(v11 + 80) - *(_QWORD *)&IID_IPrintOemUni3.Data1;
                if ( !v28 )
                  v28 = *(_QWORD *)(v11 + 88) - *(_QWORD *)IID_IPrintOemUni3.Data4;
                if ( v28 )
                  goto LABEL_30;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int *))(**(_QWORD **)(v11 + 72)
                                                                                          + 208LL))(
                      *(_QWORD *)(v11 + 72),
                      0,
                      0,
                      0,
                      &v39) )
              {
                *(_DWORD *)(v11 + 48) |= 8u;
                *(_DWORD *)(a1 + 116) |= 2u;
              }
            }
            v19 = *(_QWORD *)&IID_IPrintOemUni3.Data1;
            v7 = *(_QWORD *)IID_IPrintOemUni3.Data4;
            v18 = *(_QWORD *)&IID_IPrintOemUni2.Data1;
            v17 = *(_QWORD *)IID_IPrintOemUni2.Data4;
LABEL_30:
            v14 = *(_QWORD *)IID_IPrintOemUni.Data4;
            v16 = *(_QWORD *)&IID_IPrintOemUni.Data1;
LABEL_31:
            v15 = (unsigned int)(v15 + 1);
            if ( (unsigned int)v15 >= 0x10 )
              goto LABEL_32;
          }
        }
        if ( v13 >= 0 )
        {
LABEL_43:
          *(_DWORD *)(v11 + 48) |= 1u;
          v6 = (FARPROC)DWORD1(v38);
          v31 = *((_QWORD *)&v38 + 1);
          while ( (_DWORD)v6 )
          {
            v6 = (FARPROC)(unsigned int)((_DWORD)v6 - 1);
            for ( i = 0; ; ++i )
            {
              if ( i >= 32 )
                goto LABEL_45;
              if ( dword_18007FCA0[2 * i] == *(_DWORD *)v31 )
                break;
            }
            v32 = dword_18007FCA4[2 * i];
            if ( (int)v32 >= 0 )
            {
              v34 = *(_QWORD *)(a1 + 1896);
              if ( !*(_QWORD *)(v34 + 16 * v32) )
              {
                *(_QWORD *)(v34 + 16 * v32) = *(_QWORD *)(v31 + 8);
                *(_QWORD *)(*(_QWORD *)(a1 + 1896) + 16 * v32 + 8) = v11;
              }
            }
LABEL_45:
            v31 += 16;
          }
          goto LABEL_10;
        }
      }
      else
      {
        if ( (*(_BYTE *)(v11 + 100) & 4) != 0 )
          v35 = *(unsigned int (__fastcall **)(__int64, __int64, __int128 *))(v11 + 120);
        else
          v35 = (unsigned int (__fastcall *)(__int64, __int64, __int128 *))PGetOemEntrypointAddress(v11, 2);
        if ( !v35 )
          goto LABEL_10;
        if ( v35(0x10000, 16, &v38) && (_DWORD)v38 == 0x10000 )
          goto LABEL_43;
      }
    }
LABEL_33:
    *(_QWORD *)(a1 + 1912) = *(_QWORD *)(*(_QWORD *)(a1 + 1896) + 512LL);
  }
  return 1;
}

```

## disassembly

```asm
0x180027964  mov     [rsp+arg_8], rbx
0x180027969  mov     [rsp+arg_10], rbp
0x18002796e  push    rsi
0x18002796f  push    rdi
0x180027970  push    r12
0x180027972  push    r14
0x180027974  push    r15
0x180027976  sub     rsp, 40h
0x18002797a  mov     rdx, [rcx+6B8h]
0x180027981  lea     rax, off_180077F20
0x180027988  xorps   xmm0, xmm0
0x18002798b  mov     [rcx+38h], rax
0x18002798f  movups  [rsp+68h+var_38], xmm0
0x180027994  mov     r8, rdx
0x180027997  mov     rdi, rcx
0x18002799a  mov     rdx, [rdx+18h]
0x18002799e  call    PGetOemPluginInfo
0x1800279a3  mov     [rdi+758h], rax
0x1800279aa  test    rax, rax
0x1800279ad  jz      short loc_1800279F5
0x1800279af  mov     rdx, rax
0x1800279b2  mov     rcx, rdi
0x1800279b5  call    BLoadOEMPluginModulesInternal
0x1800279ba  test    eax, eax
0x1800279bc  jz      short loc_1800279F5
0x1800279be  mov     rax, [rdi+758h]
0x1800279c5  mov     [rax], rdi
0x1800279c8  mov     rax, [rdi+758h]
0x1800279cf  cmp     dword ptr [rax+8], 0
0x1800279d3  jz      loc_180027C1E
0x1800279d9  mov     edx, 300h; uBytes
0x1800279de  mov     ecx, 40h ; '@'; uFlags
0x1800279e3  call    cs:__imp_LocalAlloc
0x1800279e9  mov     [rdi+768h], rax
0x1800279f0  test    rax, rax
0x1800279f3  jnz     short loc_1800279FC
0x1800279f5  xor     eax, eax
0x1800279f7  jmp     loc_180027C23
0x1800279fc  mov     rax, [rdi+758h]
0x180027a03  mov     r12d, [rax+8]
0x180027a07  lea     rbx, [rax+18h]
0x180027a0b  test    r12d, r12d
0x180027a0e  jz      loc_180027C09
0x180027a14  lea     rsi, cs:180000000h
0x180027a1b  mov     rax, [rbx+20h]
0x180027a1f  test    rax, rax
0x180027a22  jz      loc_180027BF8
0x180027a28  mov     [rdi+20h], rax
0x180027a2c  xorps   xmm0, xmm0
0x180027a2f  mov     rax, [rbx+28h]
0x180027a33  mov     [rdi+8], rax
0x180027a37  mov     rax, [rbx+38h]
0x180027a3b  mov     [rdi+30h], rax
0x180027a3f  movups  [rsp+68h+var_38], xmm0
0x180027a44  cmp     qword ptr [rbx+48h], 0
0x180027a49  jz      loc_180027CF7
0x180027a4f  lea     r9, [rsp+68h+var_38]
0x180027a54  mov     rcx, rbx
0x180027a57  call    HComOEMEnableDriver
0x180027a5c  cmp     eax, 80004001h
0x180027a61  jnz     loc_180027C85
0x180027a67  mov     r11, qword ptr cs:IID_IPrintOemUni.Data4
0x180027a6e  xor     r15d, r15d
0x180027a71  mov     r14, qword ptr cs:IID_IPrintOemUni.Data1
0x180027a78  mov     r10, qword ptr cs:IID_IPrintOemUni2.Data4
0x180027a7f  mov     rbp, qword ptr cs:IID_IPrintOemUni2.Data1
0x180027a86  mov     r8, qword ptr cs:IID_IPrintOemUni3.Data4
0x180027a8d  mov     r9, qword ptr cs:IID_IPrintOemUni3.Data1
0x180027a94  mov     rcx, [rbx+48h]
0x180027a98  test    rcx, rcx
0x180027a9b  jz      loc_180027D48
0x180027aa1  mov     rax, [rbx+50h]
0x180027aa5  mov     rdx, ds:rva COMUnidrvProcNames[rsi+r15*8]
0x180027aad  sub     rax, r14
0x180027ab0  jnz     short loc_180027AB9
0x180027ab2  mov     rax, [rbx+58h]
0x180027ab6  sub     rax, r11
0x180027ab9  test    rax, rax
0x180027abc  jnz     loc_180027C3C
0x180027ac2  mov     rax, [rcx]
0x180027ac5  mov     rax, [rax+58h]
0x180027ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ace  mov     r11, qword ptr cs:IID_IPrintOemUni.Data4
0x180027ad5  mov     ecx, eax
0x180027ad7  mov     r10, qword ptr cs:IID_IPrintOemUni2.Data4
0x180027ade  mov     r8, qword ptr cs:IID_IPrintOemUni3.Data4
0x180027ae5  mov     r9, qword ptr cs:IID_IPrintOemUni3.Data1
0x180027aec  mov     r14, qword ptr cs:IID_IPrintOemUni.Data1
0x180027af3  mov     rbp, qword ptr cs:IID_IPrintOemUni2.Data1
0x180027afa  xor     eax, eax
0x180027afc  mov     rdx, rbx
0x180027aff  test    ecx, ecx
0x180027b01  cmovnz  rdx, rax
0x180027b05  test    rdx, rdx
0x180027b08  jz      loc_180027BEB
0x180027b0e  mov     rax, [rdi+768h]
0x180027b15  lea     esi, [r15+20h]
0x180027b19  movsxd  rcx, esi
0x180027b1c  add     rcx, rcx
0x180027b1f  cmp     qword ptr [rax+rcx*8], 0
0x180027b24  jnz     loc_180027BE4
0x180027b2a  mov     [rax+rcx*8], rdx
0x180027b2e  mov     rax, [rdi+768h]
0x180027b35  mov     [rsp+68h+arg_0], 0
0x180027b3d  mov     [rax+rcx*8+8], rbx
0x180027b42  cmp     esi, 2Dh ; '-'
0x180027b45  jnz     short loc_180027BBA
0x180027b47  mov     rax, [rbx+50h]
0x180027b4b  mov     rbp, qword ptr cs:IID_IPrintOemUni2.Data1
0x180027b52  mov     r10, qword ptr cs:IID_IPrintOemUni2.Data4
0x180027b59  sub     rax, rbp
0x180027b5c  jnz     short loc_180027B65
0x180027b5e  mov     rax, [rbx+58h]
0x180027b62  sub     rax, r10
0x180027b65  test    rax, rax
0x180027b68  jz      short loc_180027B8D
0x180027b6a  mov     rax, [rbx+50h]
0x180027b6e  mov     r9, qword ptr cs:IID_IPrintOemUni3.Data1
0x180027b75  mov     r8, qword ptr cs:IID_IPrintOemUni3.Data4
0x180027b7c  sub     rax, r9
0x180027b7f  jnz     short loc_180027B88
0x180027b81  mov     rax, [rbx+58h]
0x180027b85  sub     rax, r8
0x180027b88  test    rax, rax
0x180027b8b  jnz     short loc_180027BD6
0x180027b8d  mov     rcx, [rbx+48h]
0x180027b91  lea     rdx, [rsp+68h+arg_0]
0x180027b96  mov     [rsp+68h+var_48], rdx
0x180027b9b  xor     r9d, r9d
0x180027b9e  xor     r8d, r8d
0x180027ba1  xor     edx, edx
0x180027ba3  mov     rax, [rcx]
0x180027ba6  mov     rax, [rax+0D0h]
0x180027bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bb2  test    eax, eax
0x180027bb4  jz      loc_180027C78
0x180027bba  mov     r9, qword ptr cs:IID_IPrintOemUni3.Data1
0x180027bc1  mov     r8, qword ptr cs:IID_IPrintOemUni3.Data4
0x180027bc8  mov     rbp, qword ptr cs:IID_IPrintOemUni2.Data1
0x180027bcf  mov     r10, qword ptr cs:IID_IPrintOemUni2.Data4
0x180027bd6  mov     r11, qword ptr cs:IID_IPrintOemUni.Data4
0x180027bdd  mov     r14, qword ptr cs:IID_IPrintOemUni.Data1
0x180027be4  lea     rsi, cs:180000000h
0x180027beb  inc     r15d
0x180027bee  cmp     r15d, 10h
0x180027bf2  jb      loc_180027A94
0x180027bf8  add     rbx, 0B0h
0x180027bff  add     r12d, 0FFFFFFFFh
0x180027c03  jnz     loc_180027A1B
0x180027c09  mov     rax, [rdi+768h]
0x180027c10  mov     rcx, [rax+200h]
0x180027c17  mov     [rdi+778h], rcx
0x180027c1e  mov     eax, 1
0x180027c23  lea     r11, [rsp+68h+var_28]
0x180027c28  mov     rbx, [r11+38h]
0x180027c2c  mov     rbp, [r11+40h]
0x180027c30  mov     rsp, r11
0x180027c33  pop     r15
0x180027c35  pop     r14
0x180027c37  pop     r12
0x180027c39  pop     rdi
0x180027c3a  pop     rsi
0x180027c3b  retn
0x180027c3c  mov     rax, [rbx+50h]
0x180027c40  sub     rax, rbp
0x180027c43  jnz     short loc_180027C4C
0x180027c45  mov     rax, [rbx+58h]
0x180027c49  sub     rax, r10
0x180027c4c  test    rax, rax
0x180027c4f  jz      loc_180027AC2
0x180027c55  mov     rax, [rbx+50h]
0x180027c59  sub     rax, r9
0x180027c5c  jnz     short loc_180027C65
0x180027c5e  mov     rax, [rbx+58h]
0x180027c62  sub     rax, r8
0x180027c65  test    rax, rax
0x180027c68  jz      loc_180027AC2
0x180027c6e  mov     ecx, 80004002h
0x180027c73  jmp     loc_180027AFA
0x180027c78  or      dword ptr [rbx+30h], 8
0x180027c7c  or      dword ptr [rdi+74h], 2
0x180027c80  jmp     loc_180027BBA
0x180027c85  test    eax, eax
0x180027c87  js      short loc_180027C09
0x180027c89  or      dword ptr [rbx+30h], 1
0x180027c8d  mov     edx, dword ptr [rsp+68h+var_38+4]
0x180027c91  mov     r8, qword ptr [rsp+68h+var_38+8]
0x180027c96  jmp     short loc_180027CA8
0x180027c98  movsxd  rax, ds:rva dword_18007FCA4[rsi+r9*8]
0x180027ca0  test    eax, eax
0x180027ca2  jns     short loc_180027CCD
0x180027ca4  add     r8, 10h
0x180027ca8  test    edx, edx
0x180027caa  jz      loc_180027A67
0x180027cb0  dec     edx
0x180027cb2  xor     ecx, ecx
0x180027cb4  cmp     ecx, 20h ; ' '
0x180027cb7  jge     short loc_180027CA4
0x180027cb9  mov     eax, [r8]
0x180027cbc  movsxd  r9, ecx
0x180027cbf  cmp     ds:rva dword_18007FCA0[rsi+r9*8], eax
0x180027cc7  jz      short loc_180027C98
0x180027cc9  inc     ecx
0x180027ccb  jmp     short loc_180027CB4
0x180027ccd  mov     r9, [rdi+768h]
0x180027cd4  mov     rcx, rax
0x180027cd7  add     rcx, rcx
0x180027cda  cmp     qword ptr [r9+rcx*8], 0
0x180027cdf  jnz     short loc_180027CA4
0x180027ce1  mov     rax, [r8+8]
0x180027ce5  mov     [r9+rcx*8], rax
0x180027ce9  mov     rax, [rdi+768h]
0x180027cf0  mov     [rax+rcx*8+8], rbx
0x180027cf5  jmp     short loc_180027CA4
0x180027cf7  test    byte ptr [rbx+64h], 4
0x180027cfb  jz      short loc_180027D03
0x180027cfd  mov     rax, [rbx+78h]
0x180027d01  jmp     short loc_180027D10
0x180027d03  mov     edx, 2
0x180027d08  mov     rcx, rbx
0x180027d0b  call    PGetOemEntrypointAddress
0x180027d10  test    rax, rax
0x180027d13  jz      loc_180027A67
0x180027d19  lea     r8, [rsp+68h+var_38]
0x180027d1e  mov     edx, 10h
0x180027d23  mov     ecx, 10000h
0x180027d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d2d  test    eax, eax
0x180027d2f  jz      loc_180027C09
0x180027d35  cmp     dword ptr [rsp+68h+var_38], 10000h
0x180027d3d  jnz     loc_180027C09
0x180027d43  jmp     loc_180027C89
0x180027d48  mov     rcx, [rbx+20h]; hModule
0x180027d4c  test    rcx, rcx
0x180027d4f  jz      loc_180027BEB
0x180027d55  mov     rdx, ds:rva off_180078530[rsi+r15*8]; lpProcName
0x180027d5d  call    cs:__imp_GetProcAddress
0x180027d63  mov     r11, qword ptr cs:IID_IPrintOemUni.Data4
0x180027d6a  mov     rdx, rax
0x180027d6d  mov     r14, qword ptr cs:IID_IPrintOemUni.Data1
0x180027d74  mov     r10, qword ptr cs:IID_IPrintOemUni2.Data4
0x180027d7b  mov     rbp, qword ptr cs:IID_IPrintOemUni2.Data1
0x180027d82  mov     r8, qword ptr cs:IID_IPrintOemUni3.Data4
0x180027d89  mov     r9, qword ptr cs:IID_IPrintOemUni3.Data1
0x180027d90  jmp     loc_180027B05
```
