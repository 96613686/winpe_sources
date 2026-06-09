# init_decompression

- ea: `0x1800c6e9c`
- end: `0x1800c75c8`
- name: `init_decompression`
- size: `1836`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800c8f50`

## callees

- `0x180006c00`
- `0x18000fc38`
- `0x180014fc0`
- `0x180016130`
- `0x180016210`
- `0x180021f90`
- `0x180022df0`
- `0x180022e80`
- `0x180039580`
- `0x18003baa0`
- `0x1800b7ae4`
- `0x1800b7b68`
- `0x1800c6e9c`
- `0x1800c8ed0`
- `0x18011736c`
- `0x180117448`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c7215`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c73c5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c7215`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c73c5`

## string_xrefs

- `0x1800c731e`: `mis-compiled library`
- `0x1800c7325`: `Internal error initializing decompressor: %s`

## pseudocode

```c
__int64 __fastcall init_decompression(__int64 a1, __int64 a2, unsigned int *a3, unsigned int *a4)
{
  unsigned int v6; // r9d
  unsigned int v7; // r15d
  __int64 v8; // rdx
  __int64 v10; // r14
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rsi
  unsigned int v14; // r9d
  unsigned __int8 *v15; // rax
  int v16; // ecx
  __int64 *v17; // r12
  __int64 v18; // r9
  __int64 v19; // r8
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rax
  unsigned int v23; // esi
  int v25; // eax
  const char *v26; // r9
  __int64 v27; // rcx
  int v28; // eax
  int v29; // r10d
  unsigned __int8 *v30; // rcx
  int v31; // r13d
  unsigned int v32; // edi
  __int64 v33; // rax
  __int128 v34; // [rsp+30h] [rbp-69h] BYREF
  __int128 v35; // [rsp+40h] [rbp-59h]
  __int64 v36; // [rsp+50h] [rbp-49h]
  __int64 v37; // [rsp+60h] [rbp-39h] BYREF
  _QWORD v38[7]; // [rsp+68h] [rbp-31h]

  v6 = *a3;
  v7 = -1;
  *(_DWORD *)(a2 + 288) = *a3;
  *(_DWORD *)(a2 + 292) = -1;
  v8 = 50528515;
  v10 = a1;
  v11 = 50528773;
  if ( (!v6 || v6 == 197633 || v6 == 262408 || v6 == 262658 || v6 == 83300609) && a4 )
  {
    a1 = *a4;
    if ( (_DWORD)a1 != 50528515
      && (_DWORD)a1 != 50528539
      && (_DWORD)a1 != 50529537
      && (_DWORD)a1 != 10
      && (_DWORD)a1 != 50528773
      && (_DWORD)a1 != 50530309 )
    {
      archive_set_error(v10, 0xFFFFFFFFLL, "Unsupported filter %lx for %lx", a1, *a3);
      return 4294967271LL;
    }
    *(_DWORD *)(a2 + 292) = a1;
    *(_DWORD *)(a2 + 19956) = 0;
    if ( *a4 == 50528515 )
    {
      *(_QWORD *)(a2 + 19976) = -1;
      *(_DWORD *)(a2 + 19984) = 0;
      *(_DWORD *)(a2 + 19988) = 5;
    }
    else if ( *a4 == 50529537 )
    {
      *(_DWORD *)(a2 + 19988) = 8;
    }
  }
  if ( v6 > 0x303011B )
  {
    if ( v6 == 50528773 || v6 == 50529281 || v6 == 50529537 || v6 == 50530049 || v6 == 50530309 )
      goto LABEL_68;
    if ( v6 != 83300609 )
    {
      if ( v6 == 116457729 || v6 == 116458243 || v6 == 116459265 )
      {
        v33 = *(_QWORD *)(v10 + 144);
        if ( v33 )
        {
          *(_BYTE *)(v33 + 800) |= 2u;
          *(_BYTE *)(*(_QWORD *)(v10 + 144) + 800LL) |= 1u;
          *(_DWORD *)(a2 + 20712) = 1;
        }
        archive_set_error(v10, 0xFFFFFFFFLL, "Crypto codec not supported yet (ID: 0x%lX)");
        return 4294967271LL;
      }
      goto LABEL_108;
    }
    if ( *(_DWORD *)(a2 + 632) )
    {
      ZSTD_freeDStream(*(void **)(a2 + 624));
      *(_DWORD *)(a2 + 632) = 0;
    }
    *(_QWORD *)(a2 + 624) = ZSTD_createDStream(a1, v8, v11);
    *(_DWORD *)(a2 + 632) = 1;
  }
  else
  {
    if ( v6 == 50528539 )
      goto LABEL_68;
    if ( v6 > 0x30101 )
    {
      switch ( v6 )
      {
        case 0x30401u:
          if ( *(_DWORD *)(a2 + 19952) )
          {
            free(*(void **)(a2 + 704));
            *(_DWORD *)(a2 + 692) = 0;
            *(_QWORD *)(a2 + 704) = 0;
            *(_DWORD *)(a2 + 19952) = 0;
          }
          if ( *((_QWORD *)a3 + 3) < 5u
            || (v30 = (unsigned __int8 *)*((_QWORD *)a3 + 4), v31 = *v30, (unsigned int)(v31 - 2) > 0x3E)
            || (v32 = v30[1] | ((v30[2] | (*(unsigned __int16 *)(v30 + 3) << 8)) << 8), v32 - 2048 > 0xFFFFF7DB) )
          {
            archive_set_error(v10, 0xFFFFFFFFLL, "Malformed PPMd parameter");
            return 4294967271LL;
          }
          Ppmd7_Construct(a2 + 640);
          if ( !(unsigned int)Ppmd7_Alloc(a2 + 640, v32) )
          {
            archive_set_error(v10, 12, "Coludn't allocate memory for PPMd");
            return 4294967266LL;
          }
          *(_DWORD *)(a2 + 676) = v31;
          RestartModel(a2 + 640);
          *(_DWORD *)(a2 + 1836) = 1074200576;
          *(_QWORD *)(a2 + 19824) = Range_GetThreshold;
          *(_QWORD *)(a2 + 19832) = Range_Decode_7z;
          *(_QWORD *)(a2 + 19840) = Range_DecodeBit_7z;
          *(_DWORD *)(a2 + 19952) = 1;
          *(_DWORD *)(a2 + 636) = 0;
          *(_DWORD *)(a2 + 19944) = 0;
          *(_QWORD *)(a2 + 19904) = 0;
          *(_QWORD *)(a2 + 19936) = 0;
          break;
        case 0x40108u:
          v27 = a2 + 528;
          if ( *(_DWORD *)(a2 + 616) )
          {
            v28 = inflateReset(v27, 50528515, 50528773);
          }
          else
          {
            v28 = inflateInit2_(v27, 4294967281LL, 50528773);
            v29 = 0;
          }
          if ( v28 )
          {
            archive_set_error(v10, 0xFFFFFFFFLL, "Couldn't initialize zlib stream.");
            return 4294967271LL;
          }
          *(_DWORD *)(a2 + 616) = 1;
          *(_DWORD *)(a2 + 540) = v29;
          *(_DWORD *)(a2 + 556) = v29;
          break;
        case 0x40202u:
          if ( *(_DWORD *)(a2 + 520) )
          {
            BZ2_bzDecompressEnd(a2 + 440);
            *(_DWORD *)(a2 + 520) = 0;
          }
          v25 = BZ2_bzDecompressInit(a2 + 440, 0, 0);
          if ( v25 == -3 )
            v25 = BZ2_bzDecompressInit(a2 + 440, 0, 1);
          if ( v25 )
          {
            switch ( v25 )
            {
              case -9:
                v26 = "mis-compiled library";
                break;
              case -3:
                v7 = 12;
                v26 = "out of memory";
                break;
              case -2:
                v26 = "invalid setup parameter";
                break;
              default:
                v26 = "??";
                break;
            }
            archive_set_error(v10, v7, "Internal error initializing decompressor: %s", v26);
            *(_DWORD *)(a2 + 520) = 0;
            return 4294967271LL;
          }
          *(_DWORD *)(a2 + 520) = 1;
          *(_QWORD *)(a2 + 452) = 0;
          *(_QWORD *)(a2 + 476) = 0;
          break;
        case 0x3030103u:
          goto LABEL_68;
        default:
          goto LABEL_108;
      }
    }
    else
    {
      if ( v6 == 196865 )
        goto LABEL_27;
      if ( v6 )
      {
        if ( v6 == 3 || v6 == 10 || v6 == 11 )
          goto LABEL_68;
        if ( v6 == 33 )
        {
LABEL_27:
          v34 = 0;
          v36 = 0;
          v35 = 0;
          if ( *(_DWORD *)(a2 + 432) )
          {
            lzma_end(a2 + 296);
            LODWORD(v11) = 50528773;
            *(_DWORD *)(a2 + 432) = 0;
          }
          v12 = 33;
          v13 = 0;
          if ( !a4 )
            goto LABEL_56;
          v14 = *a4;
          *(_DWORD *)(a2 + 292) = *a4;
          v38[0] = 0;
          if ( v14 > 0x3030205 )
          {
            switch ( v14 )
            {
              case 0x3030401u:
                v37 = 6;
                break;
              case 0x3030501u:
                v37 = 7;
                break;
              case 0x3030701u:
                v37 = 8;
                break;
              case 0x3030805u:
                v37 = 9;
                break;
              default:
                goto LABEL_68;
            }
          }
          else if ( v14 == (_DWORD)v11 )
          {
            v37 = 5;
          }
          else
          {
            switch ( v14 )
            {
              case 3u:
                if ( *((_QWORD *)a4 + 3) != 1 )
                {
                  archive_set_error(v10, 0xFFFFFFFFLL, "Invalid Delta parameter");
                  return 4294967271LL;
                }
                v37 = 3;
                v36 = 0;
                v15 = (unsigned __int8 *)*((_QWORD *)a4 + 4);
                v34 = 0;
                v35 = 0;
                v16 = *v15;
                v38[0] = &v34;
                DWORD1(v34) = v16 + 1;
                break;
              case 0xAu:
                v37 = 10;
                break;
              case 0xBu:
                v37 = 11;
                break;
              case 0x3030103u:
                if ( *(_DWORD *)(a2 + 288) != 33 )
                {
                  *(_DWORD *)(a2 + 19956) = 0;
                  *(_QWORD *)(a2 + 19976) = -1;
                  *(_DWORD *)(a2 + 19984) = 0;
                  *(_DWORD *)(a2 + 19988) = 5;
                  goto LABEL_56;
                }
                v37 = 4;
                break;
              case 0x303011Bu:
                *(_DWORD *)(a2 + 19956) = 0;
LABEL_56:
                v17 = &v38[2 * v13 - 1];
                if ( *(_DWORD *)(a2 + 288) != 33 )
                  v12 = 0x4000000000000001LL;
                *v17 = v12;
                v18 = *((_QWORD *)a3 + 3);
                v19 = *((_QWORD *)a3 + 4);
                v38[2 * v13] = 0;
                v20 = lzma_properties_decode(&v38[2 * v13 - 1], 0, v19, v18);
                if ( v20 )
                {
                  v21 = v20;
LABEL_60:
                  set_error_0(v10, v21);
                  return 4294967271LL;
                }
                v22 = 2 * (v13 + 1);
                v38[v22 - 1] = -1;
                v38[v22] = 0;
                v23 = lzma_raw_decoder(a2 + 296, &v37);
                free((void *)v17[1]);
                if ( v23 )
                {
                  v21 = v23;
                  goto LABEL_60;
                }
                *(_DWORD *)(a2 + 432) = 1;
                *(_QWORD *)(a2 + 312) = 0;
                *(_QWORD *)(a2 + 336) = 0;
                return 0;
              default:
LABEL_68:
                archive_set_error(v10, 0xFFFFFFFFLL, "Unexpected codec ID: %lX");
                return 4294967271LL;
            }
          }
          v13 = 1;
          goto LABEL_56;
        }
LABEL_108:
        archive_set_error(v10, 0xFFFFFFFFLL, "Unknown codec ID: %lX");
        return 4294967271LL;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800c6e9c  push    rbp
0x1800c6e9e  push    rbx
0x1800c6e9f  push    rsi
0x1800c6ea0  push    rdi
0x1800c6ea1  push    r12
0x1800c6ea3  push    r13
0x1800c6ea5  push    r14
0x1800c6ea7  push    r15
0x1800c6ea9  lea     rbp, [rsp-1Fh]
0x1800c6eae  sub     rsp, 0B8h
0x1800c6eb5  mov     rax, cs:__security_cookie
0x1800c6ebc  xor     rax, rsp
0x1800c6ebf  mov     [rbp+57h+var_50], rax
0x1800c6ec3  mov     r12, r9
0x1800c6ec6  mov     rbx, rdx
0x1800c6ec9  mov     r9d, [r8]
0x1800c6ecc  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800c6ed0  mov     [rdx+120h], r9d
0x1800c6ed7  xor     r10d, r10d
0x1800c6eda  mov     dword ptr [rdx+124h], 0FFFFFFFFh
0x1800c6ee4  mov     edx, 3030103h
0x1800c6ee9  mov     r13, r8
0x1800c6eec  mov     r14, rcx
0x1800c6eef  mov     esi, 40108h
0x1800c6ef4  mov     edi, 4F71101h
0x1800c6ef9  mov     r11d, 3030501h
0x1800c6eff  mov     r8d, 3030205h
0x1800c6f05  lea     eax, [rdx+18h]
0x1800c6f08  test    r9d, r9d
0x1800c6f0b  jz      short loc_1800C6F2D
0x1800c6f0d  cmp     r9d, 30401h
0x1800c6f14  jz      short loc_1800C6F2D
0x1800c6f16  cmp     r9d, esi
0x1800c6f19  jz      short loc_1800C6F2D
0x1800c6f1b  cmp     r9d, 40202h
0x1800c6f22  jz      short loc_1800C6F2D
0x1800c6f24  cmp     r9d, edi
0x1800c6f27  jnz     loc_1800C6FB8
0x1800c6f2d  test    r12, r12
0x1800c6f30  jz      loc_1800C6FB8
0x1800c6f36  mov     ecx, [r12]
0x1800c6f3a  cmp     ecx, edx
0x1800c6f3c  jz      short loc_1800C6F7B
0x1800c6f3e  cmp     ecx, eax
0x1800c6f40  jz      short loc_1800C6F7B
0x1800c6f42  cmp     ecx, r11d
0x1800c6f45  jz      short loc_1800C6F7B
0x1800c6f47  cmp     ecx, 0Ah
0x1800c6f4a  jz      short loc_1800C6F7B
0x1800c6f4c  cmp     ecx, r8d
0x1800c6f4f  jz      short loc_1800C6F7B
0x1800c6f51  cmp     ecx, 3030805h
0x1800c6f57  jz      short loc_1800C6F7B
0x1800c6f59  mov     eax, [r13+0]
0x1800c6f5d  lea     r8, aUnsupportedFil_0; "Unsupported filter %lx for %lx"
0x1800c6f64  mov     r9d, ecx
0x1800c6f67  mov     [rsp+0F0h+var_D0], eax
0x1800c6f6b  mov     rcx, r14
0x1800c6f6e  mov     edx, r15d
0x1800c6f71  call    archive_set_error
0x1800c6f76  jmp     loc_1800C7276
0x1800c6f7b  mov     [rbx+124h], ecx
0x1800c6f81  mov     [rbx+4DF4h], r10d
0x1800c6f88  cmp     [r12], edx
0x1800c6f8c  jnz     short loc_1800C6FA8
0x1800c6f8e  mov     [rbx+4E08h], r15
0x1800c6f95  mov     [rbx+4E10h], r10d
0x1800c6f9c  mov     dword ptr [rbx+4E14h], 5
0x1800c6fa6  jmp     short loc_1800C6FB8
0x1800c6fa8  cmp     [r12], r11d
0x1800c6fac  jnz     short loc_1800C6FB8
0x1800c6fae  mov     dword ptr [rbx+4E14h], 8
0x1800c6fb8  cmp     r9d, eax
0x1800c6fbb  ja      loc_1800C74E8
0x1800c6fc1  jz      loc_1800C7264
0x1800c6fc7  mov     eax, 30101h
0x1800c6fcc  cmp     r9d, eax
0x1800c6fcf  ja      loc_1800C723C
0x1800c6fd5  jz      short loc_1800C7007
0x1800c6fd7  mov     eax, r9d
0x1800c6fda  test    r9d, r9d
0x1800c6fdd  jz      loc_1800C75C1
0x1800c6fe3  sub     eax, 3
0x1800c6fe6  jz      loc_1800C7264
0x1800c6fec  sub     eax, 7
0x1800c6fef  jz      loc_1800C7264
0x1800c6ff5  sub     eax, 1
0x1800c6ff8  jz      loc_1800C7264
0x1800c6ffe  cmp     eax, 16h
0x1800c7001  jnz     loc_1800C7541
0x1800c7007  xor     eax, eax
0x1800c7009  xorps   xmm0, xmm0
0x1800c700c  movups  [rbp+57h+var_C0], xmm0
0x1800c7010  mov     [rbp+57h+var_A0], rax
0x1800c7014  movups  [rbp+57h+var_B0], xmm0
0x1800c7018  cmp     [rbx+1B0h], r10d
0x1800c701f  jz      short loc_1800C7043
0x1800c7021  lea     rcx, [rbx+128h]
0x1800c7028  call    lzma_end
0x1800c702d  xor     r10d, r10d
0x1800c7030  mov     r8d, 3030205h
0x1800c7036  mov     [rbx+1B0h], r10d
0x1800c703d  mov     r11d, 3030501h
0x1800c7043  mov     edx, 21h ; '!'
0x1800c7048  mov     rsi, r10
0x1800c704b  lea     edi, [rdx-20h]
0x1800c704e  test    r12, r12
0x1800c7051  jz      loc_1800C719A
0x1800c7057  mov     r9d, [r12]
0x1800c705b  mov     [rbx+124h], r9d
0x1800c7062  mov     [rbp+57h+var_88], r10
0x1800c7066  cmp     r9d, r8d
0x1800c7069  ja      loc_1800C714D
0x1800c706f  jz      loc_1800C7143
0x1800c7075  mov     eax, r9d
0x1800c7078  sub     eax, 3
0x1800c707b  jz      short loc_1800C70F5
0x1800c707d  sub     eax, 7
0x1800c7080  jz      short loc_1800C70E8
0x1800c7082  sub     eax, edi
0x1800c7084  jz      short loc_1800C70DB
0x1800c7086  sub     eax, 30300F8h
0x1800c708b  jz      short loc_1800C70A2
0x1800c708d  cmp     eax, 18h
0x1800c7090  jnz     loc_1800C7264
0x1800c7096  mov     [rbx+4DF4h], r10d
0x1800c709d  jmp     loc_1800C719A
0x1800c70a2  cmp     [rbx+120h], edx
0x1800c70a8  jnz     short loc_1800C70B7
0x1800c70aa  mov     [rbp+57h+var_90], 4
0x1800c70b2  jmp     loc_1800C7197
0x1800c70b7  mov     [rbx+4DF4h], r10d
0x1800c70be  mov     [rbx+4E08h], r15
0x1800c70c5  mov     [rbx+4E10h], r10d
0x1800c70cc  mov     dword ptr [rbx+4E14h], 5
0x1800c70d6  jmp     loc_1800C719A
0x1800c70db  mov     [rbp+57h+var_90], 0Bh
0x1800c70e3  jmp     loc_1800C7197
0x1800c70e8  mov     [rbp+57h+var_90], 0Ah
0x1800c70f0  jmp     loc_1800C7197
0x1800c70f5  cmp     [r12+18h], rdi
0x1800c70fa  jz      short loc_1800C7113
0x1800c70fc  lea     r8, aInvalidDeltaPa; "Invalid Delta parameter"
0x1800c7103  mov     edx, r15d
0x1800c7106  mov     rcx, r14
0x1800c7109  call    archive_set_error
0x1800c710e  jmp     loc_1800C7276
0x1800c7113  xor     eax, eax
0x1800c7115  mov     [rbp+57h+var_90], 3
0x1800c711d  mov     [rbp+57h+var_A0], rax
0x1800c7121  xorps   xmm0, xmm0
0x1800c7124  mov     rax, [r12+20h]
0x1800c7129  movups  [rbp+57h+var_C0], xmm0
0x1800c712d  movups  [rbp+57h+var_B0], xmm0
0x1800c7131  movzx   ecx, byte ptr [rax]
0x1800c7134  lea     rax, [rbp+57h+var_C0]
0x1800c7138  add     ecx, edi
0x1800c713a  mov     [rbp+57h+var_88], rax
0x1800c713e  mov     dword ptr [rbp+57h+var_C0+4], ecx
0x1800c7141  jmp     short loc_1800C7197
0x1800c7143  mov     [rbp+57h+var_90], 5
0x1800c714b  jmp     short loc_1800C7197
0x1800c714d  cmp     r9d, 3030401h
0x1800c7154  jz      short loc_1800C718F
0x1800c7156  cmp     r9d, r11d
0x1800c7159  jz      short loc_1800C7185
0x1800c715b  cmp     r9d, 3030701h
0x1800c7162  jz      short loc_1800C717B
0x1800c7164  cmp     r9d, 3030805h
0x1800c716b  jnz     loc_1800C7264
0x1800c7171  mov     [rbp+57h+var_90], 9
0x1800c7179  jmp     short loc_1800C7197
0x1800c717b  mov     [rbp+57h+var_90], 8
0x1800c7183  jmp     short loc_1800C7197
0x1800c7185  mov     [rbp+57h+var_90], 7
0x1800c718d  jmp     short loc_1800C7197
0x1800c718f  mov     [rbp+57h+var_90], 6
0x1800c7197  mov     rsi, rdi
0x1800c719a  mov     rcx, 4000000000000001h
0x1800c71a4  lea     r12, [rbp+57h+var_90]
0x1800c71a8  mov     rax, rsi
0x1800c71ab  shl     rax, 4
0x1800c71af  add     r12, rax
0x1800c71b2  cmp     [rbx+120h], edx
0x1800c71b8  cmovnz  rdx, rcx
0x1800c71bc  mov     rcx, r12
0x1800c71bf  mov     [r12], rdx
0x1800c71c3  xor     edx, edx
0x1800c71c5  mov     r9, [r13+18h]
0x1800c71c9  mov     r8, [r13+20h]
0x1800c71cd  mov     [rbp+rax+57h+var_88], r10
0x1800c71d2  call    lzma_properties_decode
0x1800c71d7  xor     r13d, r13d
0x1800c71da  test    eax, eax
0x1800c71dc  jz      short loc_1800C71ED
0x1800c71de  mov     edx, eax
0x1800c71e0  mov     rcx, r14
0x1800c71e3  call    set_error_0
0x1800c71e8  jmp     loc_1800C7276
0x1800c71ed  lea     rax, [rsi+1]
0x1800c71f1  add     rax, rax
0x1800c71f4  lea     rcx, [rbx+128h]
0x1800c71fb  lea     rdx, [rbp+57h+var_90]
0x1800c71ff  mov     [rbp+rax*8+57h+var_90], r15
0x1800c7204  mov     [rbp+rax*8+57h+var_88], r13
0x1800c7209  call    lzma_raw_decoder
0x1800c720e  mov     rcx, [r12+8]; Block
0x1800c7213  mov     esi, eax
0x1800c7215  call    cs:__imp_free
0x1800c721b  test    esi, esi
0x1800c721d  jz      short loc_1800C7223
0x1800c721f  mov     edx, esi
0x1800c7221  jmp     short loc_1800C71E0
0x1800c7223  mov     [rbx+1B0h], edi
0x1800c7229  mov     [rbx+138h], r13
0x1800c7230  mov     [rbx+150h], r13
0x1800c7237  jmp     loc_1800C75C1
0x1800c723c  cmp     r9d, 30401h
0x1800c7243  jz      loc_1800C73B5
0x1800c7249  cmp     r9d, esi
0x1800c724c  jz      loc_1800C7364
0x1800c7252  cmp     r9d, 40202h
0x1800c7259  jz      short loc_1800C729B
0x1800c725b  cmp     r9d, edx
0x1800c725e  jnz     loc_1800C7541
0x1800c7264  lea     r8, aUnexpectedCode; "Unexpected codec ID: %lX"
0x1800c726b  mov     edx, r15d
0x1800c726e  mov     rcx, r14
0x1800c7271  call    archive_set_error
0x1800c7276  mov     eax, 0FFFFFFE7h
0x1800c727b  mov     rcx, [rbp+57h+var_50]
0x1800c727f  xor     rcx, rsp; StackCookie
0x1800c7282  call    __security_check_cookie
0x1800c7287  add     rsp, 0B8h
0x1800c728e  pop     r15
0x1800c7290  pop     r14
0x1800c7292  pop     r13
0x1800c7294  pop     r12
0x1800c7296  pop     rdi
0x1800c7297  pop     rsi
0x1800c7298  pop     rbx
0x1800c7299  pop     rbp
0x1800c729a  retn
0x1800c729b  cmp     [rbx+208h], r10d
0x1800c72a2  jz      short loc_1800C72BC
0x1800c72a4  lea     rcx, [rbx+1B8h]
0x1800c72ab  call    BZ2_bzDecompressEnd
0x1800c72b0  xor     r13d, r13d
0x1800c72b3  mov     [rbx+208h], r13d
0x1800c72ba  jmp     short loc_1800C72BF
0x1800c72bc  xor     r13d, r13d
0x1800c72bf  lea     rsi, [rbx+1B8h]
0x1800c72c6  xor     r8d, r8d
0x1800c72c9  mov     rcx, rsi
0x1800c72cc  xor     edx, edx
0x1800c72ce  call    BZ2_bzDecompressInit
0x1800c72d3  mov     edi, 1
0x1800c72d8  cmp     eax, 0FFFFFFFDh
0x1800c72db  jnz     short loc_1800C72EA
0x1800c72dd  mov     r8d, edi
0x1800c72e0  xor     edx, edx
0x1800c72e2  mov     rcx, rsi
0x1800c72e5  call    BZ2_bzDecompressInit
0x1800c72ea  test    eax, eax
0x1800c72ec  jz      short loc_1800C7343
0x1800c72ee  cmp     eax, 0FFFFFFF7h
0x1800c72f1  jz      short loc_1800C731E
0x1800c72f3  cmp     eax, 0FFFFFFFDh
0x1800c72f6  jz      short loc_1800C730F
0x1800c72f8  cmp     eax, 0FFFFFFFEh
0x1800c72fb  jnz     short loc_1800C7306
0x1800c72fd  lea     r9, aInvalidSetupPa; "invalid setup parameter"
0x1800c7304  jmp     short loc_1800C7325
0x1800c7306  lea     r9, asc_18012F668; "??"
0x1800c730d  jmp     short loc_1800C7325
0x1800c730f  mov     r15d, 0Ch
0x1800c7315  lea     r9, aOutOfMemory; "out of memory"
0x1800c731c  jmp     short loc_1800C7325
0x1800c731e  lea     r9, aMisCompiledLib; "mis-compiled library"
0x1800c7325  lea     r8, aInternalErrorI_5; "Internal error initializing decompresso"...
0x1800c732c  mov     edx, r15d
0x1800c732f  mov     rcx, r14
0x1800c7332  call    archive_set_error
0x1800c7337  mov     [rbx+208h], r13d
0x1800c733e  jmp     loc_1800C7276
0x1800c7343  mov     [rbx+208h], edi
0x1800c7349  mov     qword ptr [rbx+1C4h], 0
0x1800c7354  mov     qword ptr [rbx+1DCh], 0
0x1800c735f  jmp     loc_1800C75C1
0x1800c7364  lea     rcx, [rbx+210h]
0x1800c736b  cmp     [rbx+268h], r10d
0x1800c7372  jz      short loc_1800C737B
0x1800c7374  call    inflateReset
0x1800c7379  jmp     short loc_1800C7388
0x1800c737b  mov     edx, 0FFFFFFF1h
0x1800c7380  call    inflateInit2_
0x1800c7385  xor     r10d, r10d
0x1800c7388  test    eax, eax
0x1800c738a  jz      short loc_1800C7398
0x1800c738c  lea     r8, aCouldnTInitial; "Couldn't initialize zlib stream."
  ... truncated ...
```
