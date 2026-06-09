# DeserializeTlsParams

- ea: `0x180008b90`
- end: `0x1800091ad`
- name: `DeserializeTlsParams`
- size: `1565`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180001e70`

## callees

- `0x18000896c`
- `0x180008b90`
- `0x18000a4bc`
- `0x18000a4c8`
- `0x18000b080`
- `0x18000c250`
- `0x18000c2ac`
- `0x18000c2fc`
- `0x18000c370`
- `0x18000c42c`
- `0x18000c4cc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180008d8c`
- `ntdll!RtlInitUnicodeString` at `0x180008efe`
- `ntdll!RtlInitUnicodeString` at `0x18000905e`
- `ntdll!RtlInitUnicodeString` at `0x180008d8c`
- `ntdll!RtlInitUnicodeString` at `0x180008efe`
- `ntdll!RtlInitUnicodeString` at `0x18000905e`

## pseudocode

```c
__int64 __fastcall DeserializeTlsParams(int a1, __int64 a2, char *a3, unsigned int a4)
{
  size_t v4; // r14
  unsigned int v8; // r12d
  unsigned int *v9; // r8
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  __int64 v13; // r15
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // r13
  __int64 v19; // rdi
  char *v20; // rsi
  __int64 v21; // rbx
  unsigned int *v22; // r14
  unsigned int v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  unsigned __int64 v27; // rax
  unsigned int v28; // r12d
  unsigned __int64 v29; // rbx
  __int64 v30; // rcx
  size_t v31; // r8
  __int64 v32; // rdx
  int v33; // ecx
  unsigned int v34; // eax
  __int64 v35; // rcx
  unsigned __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // r12
  __int64 v39; // r15
  void *v40; // rdi
  unsigned int *v41; // rbx
  size_t v42; // r8
  __int64 v43; // rcx
  int v44; // edi
  int v45; // ecx
  __int16 v46; // ax
  __int64 v47; // rdx
  unsigned int v48; // eax
  unsigned int v49; // ecx
  unsigned __int64 v50; // rax
  __int64 v51; // r12
  unsigned int v52; // r15d
  const WCHAR *v53; // rbx
  __int64 v54; // rcx
  size_t v55; // r8
  __int64 v56; // r8
  __int16 v57; // ax
  int v59; // [rsp+28h] [rbp-D8h]
  int v60; // [rsp+30h] [rbp-D0h]
  int v61; // [rsp+38h] [rbp-C8h]
  int v62; // [rsp+60h] [rbp-A0h]
  __int64 v63; // [rsp+68h] [rbp-98h]
  __int64 v64; // [rsp+70h] [rbp-90h]
  __int64 v65; // [rsp+70h] [rbp-90h]
  __int64 v66; // [rsp+78h] [rbp-88h]
  __int64 v67; // [rsp+78h] [rbp-88h]
  __int64 v68; // [rsp+80h] [rbp-80h]
  __int64 v69; // [rsp+88h] [rbp-78h]
  __int64 v70; // [rsp+90h] [rbp-70h]
  int v71; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v72; // [rsp+9Ch] [rbp-64h]
  __int64 v73; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v74; // [rsp+A8h] [rbp-58h]
  __int128 v75; // [rsp+B0h] [rbp-50h]
  __int128 v76; // [rsp+C0h] [rbp-40h]
  __int128 v77; // [rsp+D0h] [rbp-30h]
  __int128 v78; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v79; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v80[5]; // [rsp+100h] [rbp+0h] BYREF

  v4 = a4;
  v73 = 0;
  v71 = 0;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_dqqd(a1, a2, (_DWORD)a3, a1, a2, a3, a4);
  if ( !a2 || !a3 )
  {
    v8 = 87;
    goto LABEL_57;
  }
  memset_0(a3, 0, v4);
  v72 = CopyServiceConfigEx(a1, a2, (_DWORD)a3, v4, (__int64)&v73, (__int64)&v71);
  v8 = v72;
  if ( !v72 )
  {
    v10 = a1 - 8;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( !v11 )
      {
LABEL_12:
        v13 = 152;
        goto LABEL_14;
      }
      v12 = v11 - 1;
      if ( v12 )
      {
        if ( v12 != 2 )
        {
          v8 = 5023;
          goto LABEL_57;
        }
        goto LABEL_12;
      }
    }
    v13 = 144;
LABEL_14:
    v14 = *(_QWORD *)(v13 + a2 + 8);
    v69 = v13;
    v74 = v14;
    if ( v14 )
    {
      v15 = v73;
      *(_QWORD *)&a3[v13 + 8] = v73;
      v16 = *(unsigned int *)(v13 + a2);
      *(_DWORD *)&a3[v13] = v16;
      v70 = v15;
      if ( (byte_1800126A3 & 4) != 0 )
      {
        WPP_SF_d(1050, 34, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids, v16);
        v14 = v74;
      }
      v17 = *(unsigned int *)(v13 + a2);
      v18 = 0;
      v19 = v70;
      v20 = (char *)(v70 + 40 * v17);
      if ( (_DWORD)v17 )
      {
        do
        {
          v21 = 5 * v18;
          v68 = v21;
          v22 = (unsigned int *)(v14 + 5264LL * (unsigned int)v18);
          v23 = v22[1315];
          *(_DWORD *)(v19 + 8 * v21 + 32) = v23;
          v24 = v22[129];
          *(_DWORD *)(v19 + 8 * v21 + 16) = v24;
          if ( (byte_1800126A3 & 4) != 0 )
            WPP_SF_dDD(v24, 35, v9, (unsigned int)v18, v23, v24);
          v25 = *v22;
          *(_DWORD *)(v19 + 40 * v18) = *v22;
          if ( (byte_1800126A3 & 4) != 0 )
            WPP_SF_dd(v24, 36, v9, (unsigned int)v18, v25);
          v26 = *v22;
          if ( (_DWORD)v26 )
          {
            v27 = (unsigned __int64)(v20 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
            *(_QWORD *)(v19 + 40 * v18 + 8) = v27;
            v26 = *v22;
            v20 = (char *)(v27 + 16 * v26);
          }
          v28 = 0;
          if ( (_DWORD)v26 )
          {
            do
            {
              v29 = (unsigned __int64)v28 << 6;
              v66 = 16LL * v28;
              RtlInitUnicodeString(
                (PUNICODE_STRING)(*(_QWORD *)(v19 + 40 * v18 + 8) + v66),
                (PCWSTR)((char *)v22 + v29 + 4));
              *(_QWORD *)(v66 + *(_QWORD *)(v19 + 40 * v18 + 8) + 8) = v20;
              v30 = *(_QWORD *)(v19 + 40 * v18 + 8);
              v31 = *(unsigned __int16 *)(v66 + v30 + 2);
              v20 += v31;
              memcpy_0(*(void **)(v66 + v30 + 8), (char *)v22 + v29 + 4, v31);
              if ( (byte_1800126A3 & 4) != 0 )
              {
                v32 = *(_QWORD *)(v19 + 40 * v18 + 8);
                v33 = *(unsigned __int16 *)(v32 + 16LL * v28);
                if ( (unsigned __int16)v33 > 0x1F40u )
                  v33 = 8000;
                *((_QWORD *)&v75 + 1) = *(_QWORD *)(v32 + v66 + 8);
                LOWORD(v75) = v33;
                WORD1(v75) = v33;
                DWORD1(v75) = 0;
                v79 = v75;
                WPP_SF_dd_CTDSTRW_(v33, 37, 8000, v18, v28, (__int64)&v79);
              }
              ++v28;
            }
            while ( v28 < *v22 );
            v13 = v69;
            v21 = v68;
          }
          v34 = v22[130];
          *(_DWORD *)(v19 + 8 * v21 + 20) = v34;
          if ( (byte_1800126A3 & 4) != 0 )
            WPP_SF_dd(v26, 38, v9, (unsigned int)v18, v34);
          LODWORD(v35) = v22[130];
          if ( (_DWORD)v35 )
          {
            v36 = (unsigned __int64)(v20 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
            *(_QWORD *)(v19 + 8 * v21 + 24) = v36;
            v35 = v22[130];
            v20 = (char *)(v36 + 48 * v35);
          }
          v37 = 0;
          v62 = 0;
          if ( (_DWORD)v35 )
          {
            v38 = v70;
            v39 = v68;
            do
            {
              v40 = v20;
              v64 = 48 * v37;
              v63 = *(_QWORD *)(v38 + 8 * v39 + 24);
              v67 = 148 * v37;
              v41 = &v22[148 * v37];
              *(_DWORD *)(v64 + v63) = v41[131];
              *(_DWORD *)(v64 + v63 + 40) = v41[277];
              *(_DWORD *)(v64 + v63 + 44) = v41[278];
              *(_QWORD *)&v78 = 48 * v37 + v63 + 8;
              RtlInitUnicodeString((PUNICODE_STRING)v78, (PCWSTR)v41 + 264);
              v42 = *(unsigned __int16 *)(v64 + v63 + 10);
              *(_QWORD *)(v64 + v63 + 16) = v20;
              v20 += v42;
              memcpy_0(v40, v41 + 132, v42);
              v44 = v62;
              if ( (byte_1800126A3 & 4) != 0 )
              {
                DWORD1(v76) = 0;
                v45 = *(unsigned __int16 *)v78;
                v46 = *(_WORD *)v78;
                if ( (unsigned __int16)v45 > 0x1F40u )
                  v46 = 8000;
                LOWORD(v76) = v46;
                WORD1(v76) = v46;
                *((_QWORD *)&v76 + 1) = *(_QWORD *)(v64 + v63 + 16);
                v61 = *(_DWORD *)(v64 + v63 + 44);
                v60 = *(_DWORD *)(v64 + v63 + 40);
                v59 = *(_DWORD *)(v64 + v63);
                v78 = v76;
                WPP_SF_dddddqd_CTDSTRW_(v45, 39, v63, v18, v62, v59, v60, v61, DWORD2(v76), v45, (__int64)&v78);
              }
              v9 = (unsigned int *)(v67 * 4);
              v47 = v63;
              v48 = v22[v67 + 148];
              *(_DWORD *)(v64 + v63 + 24) = v48;
              if ( (byte_1800126A3 & 4) != 0 )
              {
                WPP_SF_dDD(v43, 40, v67 * 4, (unsigned int)v18, v62, v48);
                v47 = v63;
                v9 = (unsigned int *)(v67 * 4);
              }
              v49 = *(unsigned int *)((char *)v9 + (_QWORD)v22 + 592);
              if ( v49 )
              {
                v50 = (unsigned __int64)(v20 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
                *(_QWORD *)(v64 + v47 + 32) = v50;
                v49 = *(unsigned int *)((char *)v9 + (_QWORD)v22 + 592);
                v20 = (char *)(v50 + 16LL * v49);
              }
              if ( v49 )
              {
                v51 = v64;
                v52 = 0;
                v9 = (unsigned int *)((char *)v9 + (_QWORD)v22 + 596);
                do
                {
                  v65 = 16LL * v52;
                  v53 = (const WCHAR *)&v9[16 * (unsigned __int64)v52];
                  RtlInitUnicodeString((PUNICODE_STRING)(*(_QWORD *)(v51 + v47 + 32) + v65), v53);
                  *(_QWORD *)(*(_QWORD *)(v51 + v63 + 32) + v65 + 8) = v20;
                  v54 = *(_QWORD *)(v51 + v63 + 32);
                  v55 = *(unsigned __int16 *)(v65 + v54 + 2);
                  v20 += v55;
                  memcpy_0(*(void **)(v65 + v54 + 8), v53, v55);
                  if ( (byte_1800126A3 & 4) != 0 )
                  {
                    v56 = *(_QWORD *)(v51 + v63 + 32);
                    v57 = *(_WORD *)(v56 + 16LL * v52);
                    if ( (unsigned __int16)v57 > 0x1F40u )
                      v57 = 8000;
                    LOWORD(v77) = v57;
                    WORD1(v77) = v57;
                    *((_QWORD *)&v77 + 1) = *(_QWORD *)(v56 + 16LL * v52 + 8);
                    DWORD1(v77) = 0;
                    v80[0] = v77;
                    WPP_SF_dddqd_CTDSTRW_(
                      (unsigned int)v80,
                      41,
                      v56,
                      v18,
                      v62,
                      v52,
                      *(_QWORD *)(v56 + 16LL * v52 + 8),
                      *(unsigned __int16 *)(v56 + 16LL * v52),
                      (__int64)v80);
                  }
                  ++v52;
                  v47 = v63;
                  v9 = &v22[v67 + 149];
                }
                while ( v52 < v22[v67 + 148] );
                v38 = v70;
                v39 = v68;
              }
              ++v62;
              v37 = (unsigned int)(v44 + 1);
            }
            while ( v44 + 1 < v22[130] );
            v13 = v69;
            v19 = v70;
          }
          v18 = (unsigned int)(v18 + 1);
          v14 = v74;
        }
        while ( (unsigned int)v18 < *(_DWORD *)(v13 + a2) );
        v8 = v72;
      }
    }
  }
LABEL_57:
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_d(1050, 42, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180008b90  mov     [rsp-8+arg_8], rdx
0x180008b95  push    rbp
0x180008b96  push    rbx
0x180008b97  push    rsi
0x180008b98  push    rdi
0x180008b99  push    r12
0x180008b9b  push    r13
0x180008b9d  push    r14
0x180008b9f  push    r15
0x180008ba1  lea     rbp, [rsp-18h]
0x180008ba6  sub     rsp, 118h
0x180008bad  mov     r14d, r9d
0x180008bb0  mov     rdi, r8
0x180008bb3  mov     rsi, rdx
0x180008bb6  mov     [rbp+50h+var_B0], 0
0x180008bbe  mov     ebx, ecx
0x180008bc0  mov     [rbp+50h+var_B8], 0
0x180008bc7  test    cs:byte_1800126A3, 4
0x180008bce  jz      short loc_180008BE7
0x180008bd0  mov     dword ptr [rsp+150h+var_120], r14d
0x180008bd5  mov     r9d, ecx
0x180008bd8  mov     [rsp+150h+var_128], r8
0x180008bdd  mov     [rsp+150h+var_130], rdx
0x180008be2  call    WPP_SF_dqqd
0x180008be7  test    rsi, rsi
0x180008bea  jnz     short loc_180008BF7
0x180008bec  mov     r12d, 57h ; 'W'
0x180008bf2  jmp     loc_180009174
0x180008bf7  test    rdi, rdi
0x180008bfa  jz      short loc_180008BEC
0x180008bfc  mov     r8, r14; Size
0x180008bff  xor     edx, edx; Val
0x180008c01  mov     rcx, rdi; void *
0x180008c04  call    memset_0
0x180008c09  lea     rax, [rbp+50h+var_B8]
0x180008c0d  mov     r9d, r14d
0x180008c10  mov     [rsp+150h+var_128], rax
0x180008c15  mov     r8, rdi
0x180008c18  lea     rax, [rbp+50h+var_B0]
0x180008c1c  mov     rdx, rsi
0x180008c1f  mov     ecx, ebx
0x180008c21  mov     [rsp+150h+var_130], rax
0x180008c26  call    CopyServiceConfigEx
0x180008c2b  mov     [rbp+50h+var_B4], eax
0x180008c2e  mov     r12d, eax
0x180008c31  test    eax, eax
0x180008c33  jnz     loc_180009174
0x180008c39  sub     ebx, 8
0x180008c3c  jz      short loc_180008C60
0x180008c3e  sub     ebx, 1
0x180008c41  jz      short loc_180008C58
0x180008c43  sub     ebx, 1
0x180008c46  jz      short loc_180008C60
0x180008c48  cmp     ebx, 2
0x180008c4b  jz      short loc_180008C58
0x180008c4d  mov     r12d, 139Fh
0x180008c53  jmp     loc_180009174
0x180008c58  mov     r15d, 98h
0x180008c5e  jmp     short loc_180008C66
0x180008c60  mov     r15d, 90h
0x180008c66  mov     rdx, [r15+rsi+8]
0x180008c6b  mov     [rbp+50h+var_C8], r15
0x180008c6f  mov     [rbp+50h+var_A8], rdx
0x180008c73  test    rdx, rdx
0x180008c76  jz      loc_180009174
0x180008c7c  mov     rax, [rbp+50h+var_B0]
0x180008c80  mov     [r15+rdi+8], rax
0x180008c85  mov     r9d, [r15+rsi]
0x180008c89  mov     [r15+rdi], r9d
0x180008c8d  mov     [rbp+50h+var_C0], rax
0x180008c91  test    cs:byte_1800126A3, 4
0x180008c98  jz      short loc_180008CB4
0x180008c9a  mov     edx, 22h ; '"'
0x180008c9f  lea     r8, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids
0x180008ca6  mov     ecx, 41Ah
0x180008cab  call    WPP_SF_d
0x180008cb0  mov     rdx, [rbp+50h+var_A8]
0x180008cb4  mov     ecx, [r15+rsi]
0x180008cb8  xor     r13d, r13d
0x180008cbb  mov     rdi, [rbp+50h+var_C0]
0x180008cbf  lea     rax, [rcx+rcx*4]
0x180008cc3  lea     rsi, [rdi+rax*8]
0x180008cc7  test    ecx, ecx
0x180008cc9  jz      loc_180009174
0x180008ccf  mov     eax, r13d
0x180008cd2  lea     rbx, ds:0[r13*4]
0x180008cda  add     rbx, r13
0x180008cdd  imul    r14, rax, 1490h
0x180008ce4  mov     [rbp+50h+var_D0], rbx
0x180008ce8  add     r14, rdx
0x180008ceb  mov     eax, [r14+148Ch]
0x180008cf2  mov     [rdi+rbx*8+20h], eax
0x180008cf6  mov     ecx, [r14+204h]
0x180008cfd  mov     [rdi+rbx*8+10h], ecx
0x180008d01  test    cs:byte_1800126A3, 4
0x180008d08  jz      short loc_180008D1F
0x180008d0a  mov     dword ptr [rsp+150h+var_128], ecx
0x180008d0e  mov     edx, 23h ; '#'
0x180008d13  mov     r9d, r13d
0x180008d16  mov     dword ptr [rsp+150h+var_130], eax
0x180008d1a  call    WPP_SF_dDD
0x180008d1f  mov     eax, [r14]
0x180008d22  mov     [rdi+rbx*8], eax
0x180008d25  test    cs:byte_1800126A3, 4
0x180008d2c  jz      short loc_180008D3F
0x180008d2e  mov     edx, 24h ; '$'
0x180008d33  mov     dword ptr [rsp+150h+var_130], eax
0x180008d37  mov     r9d, r13d
0x180008d3a  call    WPP_SF_dd
0x180008d3f  mov     ecx, [r14]
0x180008d42  test    ecx, ecx
0x180008d44  jz      short loc_180008D5F
0x180008d46  lea     rax, [rsi+7]
0x180008d4a  and     rax, 0FFFFFFFFFFFFFFF8h
0x180008d4e  mov     [rdi+rbx*8+8], rax
0x180008d53  mov     ecx, [r14]
0x180008d56  mov     esi, ecx
0x180008d58  shl     rsi, 4
0x180008d5c  add     rsi, rax
0x180008d5f  xor     r12d, r12d
0x180008d62  test    ecx, ecx
0x180008d64  jz      loc_180008E37
0x180008d6a  mov     r15, rbx
0x180008d6d  mov     ebx, r12d
0x180008d70  shl     rbx, 6
0x180008d74  mov     ecx, r12d
0x180008d77  shl     rcx, 4
0x180008d7b  mov     [rsp+150h+var_D8], rcx
0x180008d80  add     rcx, [rdi+r15*8+8]; DestinationString
0x180008d85  lea     rdx, [rbx+4]
0x180008d89  add     rdx, r14; SourceString
0x180008d8c  call    cs:__imp_RtlInitUnicodeString
0x180008d92  mov     r9, [rsp+150h+var_D8]
0x180008d97  lea     rdx, [rbx+4]
0x180008d9b  mov     rax, [rdi+r15*8+8]
0x180008da0  add     rdx, r14; Src
0x180008da3  mov     [r9+rax+8], rsi
0x180008da8  mov     rcx, [rdi+r15*8+8]
0x180008dad  movzx   r8d, word ptr [r9+rcx+2]; Size
0x180008db3  mov     rcx, [r9+rcx+8]; void *
0x180008db8  add     rsi, r8
0x180008dbb  call    memcpy_0
0x180008dc0  test    cs:byte_1800126A3, 4
0x180008dc7  jz      short loc_180008E23
0x180008dc9  mov     rdx, [rdi+r15*8+8]
0x180008dce  mov     r8d, 1F40h
0x180008dd4  mov     rax, [rsp+150h+var_D8]
0x180008dd9  movzx   ecx, word ptr [rdx+rax]
0x180008ddd  cmp     cx, r8w
0x180008de1  jbe     short loc_180008DE7
0x180008de3  movzx   ecx, r8w
0x180008de7  mov     rax, [rdx+rax+8]
0x180008dec  mov     r9d, r13d
0x180008def  mov     qword ptr [rbp+50h+var_A0+8], rax
0x180008df3  mov     edx, 25h ; '%'
0x180008df8  lea     rax, [rbp+50h+var_60]
0x180008dfc  mov     word ptr [rbp+50h+var_A0], cx
0x180008e00  mov     word ptr [rbp+50h+var_A0+2], cx
0x180008e04  mov     [rsp+150h+var_128], rax
0x180008e09  mov     dword ptr [rbp+50h+var_A0+4], 0
0x180008e10  movaps  xmm0, [rbp+50h+var_A0]
0x180008e14  mov     dword ptr [rsp+150h+var_130], r12d
0x180008e19  movdqa  [rbp+50h+var_60], xmm0
0x180008e1e  call    WPP_SF_dd_CTDSTRW_
0x180008e23  inc     r12d
0x180008e26  cmp     r12d, [r14]
0x180008e29  jb      loc_180008D6D
0x180008e2f  mov     r15, [rbp+50h+var_C8]
0x180008e33  mov     rbx, [rbp+50h+var_D0]
0x180008e37  mov     eax, [r14+208h]
0x180008e3e  mov     [rdi+rbx*8+14h], eax
0x180008e42  test    cs:byte_1800126A3, 4
0x180008e49  jz      short loc_180008E5C
0x180008e4b  mov     edx, 26h ; '&'
0x180008e50  mov     dword ptr [rsp+150h+var_130], eax
0x180008e54  mov     r9d, r13d
0x180008e57  call    WPP_SF_dd
0x180008e5c  mov     ecx, [r14+208h]
0x180008e63  test    ecx, ecx
0x180008e65  jz      short loc_180008E86
0x180008e67  lea     rax, [rsi+7]
0x180008e6b  and     rax, 0FFFFFFFFFFFFFFF8h
0x180008e6f  mov     [rdi+rbx*8+18h], rax
0x180008e74  mov     ecx, [r14+208h]
0x180008e7b  lea     rsi, [rcx+rcx*2]
0x180008e7f  shl     rsi, 4
0x180008e83  add     rsi, rax
0x180008e86  xor     eax, eax
0x180008e88  mov     [rsp+150h+var_F0], eax
0x180008e8c  test    ecx, ecx
0x180008e8e  jz      loc_18000915B
0x180008e94  mov     r12, [rbp+50h+var_C0]
0x180008e98  mov     r15, [rbp+50h+var_D0]
0x180008e9c  mov     rdx, [r12+r15*8+18h]
0x180008ea1  lea     rcx, [rax+rax*2]
0x180008ea5  imul    r8, rax, 250h
0x180008eac  shl     rcx, 4
0x180008eb0  mov     rdi, rsi
0x180008eb3  mov     [rsp+150h+var_E0], rcx
0x180008eb8  mov     [rsp+150h+var_E8], rdx
0x180008ebd  mov     [rsp+150h+var_D8], r8
0x180008ec2  mov     eax, [r14+r8+20Ch]
0x180008eca  lea     rbx, [r8+r14]
0x180008ece  mov     [rcx+rdx], eax
0x180008ed1  mov     eax, [r14+r8+454h]
0x180008ed9  mov     [rcx+rdx+28h], eax
0x180008edd  mov     eax, [r14+r8+458h]
0x180008ee5  mov     [rcx+rdx+2Ch], eax
0x180008ee9  lea     rax, [rdx+8]
0x180008eed  add     rax, rcx
0x180008ef0  lea     rdx, [rbx+210h]; SourceString
0x180008ef7  mov     rcx, rax; DestinationString
0x180008efa  mov     qword ptr [rbp+50h+var_70], rax
0x180008efe  call    cs:__imp_RtlInitUnicodeString
0x180008f04  mov     rax, [rsp+150h+var_E0]
0x180008f09  lea     rdx, [rbx+210h]; Src
0x180008f10  mov     rcx, [rsp+150h+var_E8]
0x180008f15  movzx   r8d, word ptr [rax+rcx+0Ah]; Size
0x180008f1b  mov     [rax+rcx+10h], rsi
0x180008f20  add     rsi, r8
0x180008f23  mov     rcx, rdi; void *
0x180008f26  call    memcpy_0
0x180008f2b  test    cs:byte_1800126A3, 4
0x180008f32  mov     rbx, [rsp+150h+var_E0]
0x180008f37  mov     edi, [rsp+150h+var_F0]
0x180008f3b  jz      short loc_180008FB4
0x180008f3d  mov     rax, qword ptr [rbp+50h+var_70]
0x180008f41  lea     r9, [rbp+50h+var_70]
0x180008f45  mov     r8, [rsp+150h+var_E8]
0x180008f4a  mov     edx, 1F40h
0x180008f4f  mov     [rsp+150h+var_100], r9
0x180008f54  mov     r9d, r13d
0x180008f57  mov     dword ptr [rbp+50h+var_90+4], 0
0x180008f5e  movzx   ecx, word ptr [rax]
0x180008f61  mov     [rsp+150h+var_108], ecx
0x180008f65  cmp     cx, dx
0x180008f68  mov     eax, ecx
0x180008f6a  cmova   eax, edx
0x180008f6d  mov     edx, 27h ; '''
0x180008f72  mov     word ptr [rbp+50h+var_90], ax
0x180008f76  mov     word ptr [rbp+50h+var_90+2], ax
0x180008f7a  mov     rax, [rbx+r8+10h]
0x180008f7f  mov     [rsp+150h+var_110], rax
0x180008f84  mov     qword ptr [rbp+50h+var_90+8], rax
0x180008f88  mov     eax, [rbx+r8+2Ch]
0x180008f8d  movaps  xmm0, [rbp+50h+var_90]
0x180008f91  mov     [rsp+150h+var_118], eax
0x180008f95  mov     eax, [rbx+r8+28h]
0x180008f9a  mov     dword ptr [rsp+150h+var_120], eax
0x180008f9e  mov     eax, [rbx+r8]
0x180008fa2  mov     dword ptr [rsp+150h+var_128], eax
0x180008fa6  mov     dword ptr [rsp+150h+var_130], edi
0x180008faa  movdqa  [rbp+50h+var_70], xmm0
0x180008faf  call    WPP_SF_dddddqd_CTDSTRW_
0x180008fb4  mov     r8, [rsp+150h+var_D8]
0x180008fb9  mov     rdx, [rsp+150h+var_E8]
0x180008fbe  mov     eax, [r14+r8+250h]
0x180008fc6  mov     [rbx+rdx+18h], eax
0x180008fca  test    cs:byte_1800126A3, 4
0x180008fd1  jz      short loc_180008FF2
0x180008fd3  mov     dword ptr [rsp+150h+var_128], eax
0x180008fd7  mov     edx, 28h ; '('
0x180008fdc  mov     r9d, r13d
0x180008fdf  mov     dword ptr [rsp+150h+var_130], edi
0x180008fe3  call    WPP_SF_dDD
0x180008fe8  mov     rdx, [rsp+150h+var_E8]
0x180008fed  mov     r8, [rsp+150h+var_D8]
0x180008ff2  mov     ecx, [r14+r8+250h]
0x180008ffa  test    ecx, ecx
0x180008ffc  jz      short loc_18000901C
0x180008ffe  lea     rax, [rsi+7]
0x180009002  and     rax, 0FFFFFFFFFFFFFFF8h
0x180009006  mov     [rbx+rdx+20h], rax
0x18000900b  mov     ecx, [r14+r8+250h]
0x180009013  mov     esi, ecx
0x180009015  shl     rsi, 4
0x180009019  add     rsi, rax
0x18000901c  mov     [rsp+150h+var_F0], 0
0x180009024  test    ecx, ecx
0x180009026  jz      loc_18000913E
0x18000902c  mov     r12, [rsp+150h+var_E0]
0x180009031  add     r8, 254h
0x180009038  mov     r15d, [rsp+150h+var_F0]
0x18000903d  add     r8, r14
0x180009040  mov     ecx, r15d
0x180009043  shl     rcx, 4
0x180009047  mov     [rsp+150h+var_E0], rcx
0x18000904c  add     rcx, [r12+rdx+20h]; DestinationString
0x180009051  mov     ebx, r15d
0x180009054  shl     rbx, 6
0x180009058  add     rbx, r8
0x18000905b  mov     rdx, rbx; SourceString
0x18000905e  call    cs:__imp_RtlInitUnicodeString
0x180009064  mov     rdx, [rsp+150h+var_E0]
0x180009069  mov     rcx, [rsp+150h+var_E8]
0x18000906e  mov     rax, [r12+rcx+20h]
0x180009073  mov     [rax+rdx+8], rsi
0x180009078  mov     rcx, [r12+rcx+20h]
0x18000907d  movzx   r8d, word ptr [rdx+rcx+2]; Size
0x180009083  mov     rdx, rbx; Src
  ... truncated ...
```
