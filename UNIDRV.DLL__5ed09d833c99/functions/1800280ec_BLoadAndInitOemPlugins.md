# BLoadAndInitOemPlugins

- ea: `0x1800280ec`
- end: `0x18002852e`
- name: `BLoadAndInitOemPlugins`
- size: `1090`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025dc0`

## callees

- `0x1800280ec`
- `0x180028534`
- `0x180037070`
- `0x18003ebf0`
- `0x18005039c`
- `0x180077010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18002816b`
- `KERNEL32!LocalAlloc` at `0x18002816b`
- `KERNEL32!GetProcAddress` at `0x1800284f0`
- `KERNEL32!GetProcAddress` at `0x1800284f0`

## pseudocode

```c
__int64 __fastcall BLoadAndInitOemPlugins(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v3; // rax
  int v4; // r8d
  HLOCAL v5; // rax
  __int64 v7; // rax
  int v8; // r12d
  __int64 v9; // rbx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // r11
  __int64 v13; // r15
  __int64 v14; // r14
  __int64 v15; // r10
  __int64 v16; // rbp
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  int v22; // ecx
  __int64 v23; // rdx
  __int64 v24; // rax
  int v25; // esi
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // edx
  __int64 v32; // r8
  __int64 v33; // rax
  int i; // ecx
  __int64 v35; // r9
  unsigned int (__fastcall *v36)(__int64, __int64, __int128 *); // rax
  HMODULE v37; // rcx
  FARPROC ProcAddress; // rax
  __int128 v39; // [rsp+30h] [rbp-38h] BYREF
  int v40; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 1720);
  *(_QWORD *)(a1 + 56) = &off_180079F20;
  v39 = 0;
  v3 = PGetOemPluginInfo(a1, *(wchar_t **)(v1 + 24), v1);
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
    v7 = *(_QWORD *)(a1 + 1880);
    v8 = *(_DWORD *)(v7 + 8);
    v9 = v7 + 24;
    if ( v8 )
    {
      while ( 1 )
      {
        v10 = *(_QWORD *)(v9 + 32);
        if ( v10 )
          break;
LABEL_32:
        v9 += 176;
        if ( !--v8 )
          goto LABEL_33;
      }
      *(_QWORD *)(a1 + 32) = v10;
      *(_QWORD *)(a1 + 8) = *(_QWORD *)(v9 + 40);
      *(_QWORD *)(a1 + 48) = *(_QWORD *)(v9 + 56);
      v39 = 0;
      if ( *(_QWORD *)(v9 + 72) )
      {
        v11 = HComOEMEnableDriver(v9);
        if ( v11 == -2147467263 )
        {
LABEL_10:
          v12 = *(_QWORD *)IID_IPrintOemUni.Data4;
          v13 = 0;
          v14 = *(_QWORD *)&IID_IPrintOemUni.Data1;
          v15 = *(_QWORD *)IID_IPrintOemUni2.Data4;
          v16 = *(_QWORD *)&IID_IPrintOemUni2.Data1;
          v17 = *(_QWORD *)IID_IPrintOemUni3.Data4;
          v18 = *(_QWORD *)&IID_IPrintOemUni3.Data1;
          while ( 1 )
          {
            v19 = *(_QWORD *)(v9 + 72);
            if ( v19 )
            {
              v20 = *(_QWORD *)(v9 + 80) - v14;
              if ( !v20 )
                v20 = *(_QWORD *)(v9 + 88) - v12;
              if ( !v20 )
                goto LABEL_15;
              v29 = *(_QWORD *)(v9 + 80) - v16;
              if ( !v29 )
                v29 = *(_QWORD *)(v9 + 88) - v15;
              if ( !v29 )
                goto LABEL_15;
              v30 = *(_QWORD *)(v9 + 80) - v18;
              if ( !v30 )
                v30 = *(_QWORD *)(v9 + 88) - v17;
              if ( v30 )
              {
                v22 = -2147467262;
              }
              else
              {
LABEL_15:
                v21 = (*(__int64 (__fastcall **)(__int64, char *, __int64, __int64))(*(_QWORD *)v19 + 88LL))(
                        v19,
                        COMUnidrvProcNames[v13],
                        v17,
                        v18);
                v12 = *(_QWORD *)IID_IPrintOemUni.Data4;
                v22 = v21;
                v15 = *(_QWORD *)IID_IPrintOemUni2.Data4;
                v17 = *(_QWORD *)IID_IPrintOemUni3.Data4;
                v18 = *(_QWORD *)&IID_IPrintOemUni3.Data1;
                v14 = *(_QWORD *)&IID_IPrintOemUni.Data1;
                v16 = *(_QWORD *)&IID_IPrintOemUni2.Data1;
              }
              v23 = v9;
              if ( v22 )
                v23 = 0;
            }
            else
            {
              v37 = *(HMODULE *)(v9 + 32);
              if ( !v37 )
                goto LABEL_31;
              ProcAddress = GetProcAddress(v37, off_18007A530[v13]);
              v12 = *(_QWORD *)IID_IPrintOemUni.Data4;
              v23 = (__int64)ProcAddress;
              v14 = *(_QWORD *)&IID_IPrintOemUni.Data1;
              v15 = *(_QWORD *)IID_IPrintOemUni2.Data4;
              v16 = *(_QWORD *)&IID_IPrintOemUni2.Data1;
              v17 = *(_QWORD *)IID_IPrintOemUni3.Data4;
              v18 = *(_QWORD *)&IID_IPrintOemUni3.Data1;
            }
            if ( !v23 )
              goto LABEL_31;
            v24 = *(_QWORD *)(a1 + 1896);
            v25 = v13 + 32;
            if ( *(_QWORD *)(v24 + 16LL * ((int)v13 + 32)) )
              goto LABEL_31;
            *(_QWORD *)(v24 + 16LL * v25) = v23;
            v26 = *(_QWORD *)(a1 + 1896);
            v40 = 0;
            *(_QWORD *)(v26 + 16LL * v25 + 8) = v9;
            if ( (_DWORD)v13 == 13 )
            {
              v16 = *(_QWORD *)&IID_IPrintOemUni2.Data1;
              v15 = *(_QWORD *)IID_IPrintOemUni2.Data4;
              v27 = *(_QWORD *)(v9 + 80) - *(_QWORD *)&IID_IPrintOemUni2.Data1;
              if ( !v27 )
                v27 = *(_QWORD *)(v9 + 88) - *(_QWORD *)IID_IPrintOemUni2.Data4;
              if ( v27 )
              {
                v18 = *(_QWORD *)&IID_IPrintOemUni3.Data1;
                v17 = *(_QWORD *)IID_IPrintOemUni3.Data4;
                v28 = *(_QWORD *)(v9 + 80) - *(_QWORD *)&IID_IPrintOemUni3.Data1;
                if ( !v28 )
                  v28 = *(_QWORD *)(v9 + 88) - *(_QWORD *)IID_IPrintOemUni3.Data4;
                if ( v28 )
                  goto LABEL_30;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int *))(**(_QWORD **)(v9 + 72)
                                                                                          + 208LL))(
                      *(_QWORD *)(v9 + 72),
                      0,
                      0,
                      0,
                      &v40) )
              {
                *(_DWORD *)(v9 + 48) |= 8u;
                *(_DWORD *)(a1 + 116) |= 2u;
              }
            }
            v18 = *(_QWORD *)&IID_IPrintOemUni3.Data1;
            v17 = *(_QWORD *)IID_IPrintOemUni3.Data4;
            v16 = *(_QWORD *)&IID_IPrintOemUni2.Data1;
            v15 = *(_QWORD *)IID_IPrintOemUni2.Data4;
LABEL_30:
            v12 = *(_QWORD *)IID_IPrintOemUni.Data4;
            v14 = *(_QWORD *)&IID_IPrintOemUni.Data1;
LABEL_31:
            v13 = (unsigned int)(v13 + 1);
            if ( (unsigned int)v13 >= 0x10 )
              goto LABEL_32;
          }
        }
        if ( v11 >= 0 )
        {
LABEL_43:
          *(_DWORD *)(v9 + 48) |= 1u;
          v31 = DWORD1(v39);
          v32 = *((_QWORD *)&v39 + 1);
          while ( v31 )
          {
            --v31;
            for ( i = 0; ; ++i )
            {
              if ( i >= 32 )
                goto LABEL_45;
              if ( dword_180081CA0[2 * i] == *(_DWORD *)v32 )
                break;
            }
            v33 = dword_180081CA4[2 * i];
            if ( (int)v33 >= 0 )
            {
              v35 = *(_QWORD *)(a1 + 1896);
              if ( !*(_QWORD *)(v35 + 16 * v33) )
              {
                *(_QWORD *)(v35 + 16 * v33) = *(_QWORD *)(v32 + 8);
                *(_QWORD *)(*(_QWORD *)(a1 + 1896) + 16 * v33 + 8) = v9;
              }
            }
LABEL_45:
            v32 += 16;
          }
          goto LABEL_10;
        }
      }
      else
      {
        if ( (*(_BYTE *)(v9 + 100) & 4) != 0 )
          v36 = *(unsigned int (__fastcall **)(__int64, __int64, __int128 *))(v9 + 120);
        else
          v36 = (unsigned int (__fastcall *)(__int64, __int64, __int128 *))PGetOemEntrypointAddress(v9, 2u);
        if ( !v36 )
          goto LABEL_10;
        if ( v36(0x10000, 16, &v39) && (_DWORD)v39 == 0x10000 )
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
0x1800280ec  mov     [rsp+arg_8], rbx
0x1800280f1  mov     [rsp+arg_10], rbp
0x1800280f6  push    rsi
0x1800280f7  push    rdi
0x1800280f8  push    r12
0x1800280fa  push    r14
0x1800280fc  push    r15
0x1800280fe  sub     rsp, 40h
0x180028102  mov     rdx, [rcx+6B8h]
0x180028109  lea     rax, off_180079F20
0x180028110  xorps   xmm0, xmm0
0x180028113  mov     [rcx+38h], rax
0x180028117  movups  [rsp+68h+var_38], xmm0
0x18002811c  mov     r8, rdx
0x18002811f  mov     rdi, rcx
0x180028122  mov     rdx, [rdx+18h]
0x180028126  call    PGetOemPluginInfo
0x18002812b  mov     [rdi+758h], rax
0x180028132  test    rax, rax
0x180028135  jz      short loc_180028183
0x180028137  mov     rdx, rax
0x18002813a  mov     rcx, rdi
0x18002813d  call    BLoadOEMPluginModulesInternal
0x180028142  test    eax, eax
0x180028144  jz      short loc_180028183
0x180028146  mov     rax, [rdi+758h]
0x18002814d  mov     [rax], rdi
0x180028150  mov     rax, [rdi+758h]
0x180028157  cmp     dword ptr [rax+8], 0
0x18002815b  jz      loc_1800283AC
0x180028161  mov     edx, 300h; uBytes
0x180028166  mov     ecx, 40h ; '@'; uFlags
0x18002816b  call    cs:__imp_LocalAlloc
0x180028172  nop     dword ptr [rax+rax+00h]
0x180028177  mov     [rdi+768h], rax
0x18002817e  test    rax, rax
0x180028181  jnz     short loc_18002818A
0x180028183  xor     eax, eax
0x180028185  jmp     loc_1800283B1
0x18002818a  mov     rax, [rdi+758h]
0x180028191  mov     r12d, [rax+8]
0x180028195  lea     rbx, [rax+18h]
0x180028199  test    r12d, r12d
0x18002819c  jz      loc_180028397
0x1800281a2  lea     rsi, cs:180000000h
0x1800281a9  mov     rax, [rbx+20h]
0x1800281ad  test    rax, rax
0x1800281b0  jz      loc_180028386
0x1800281b6  mov     [rdi+20h], rax
0x1800281ba  xorps   xmm0, xmm0
0x1800281bd  mov     rax, [rbx+28h]
0x1800281c1  mov     [rdi+8], rax
0x1800281c5  mov     rax, [rbx+38h]
0x1800281c9  mov     [rdi+30h], rax
0x1800281cd  movups  [rsp+68h+var_38], xmm0
0x1800281d2  cmp     qword ptr [rbx+48h], 0
0x1800281d7  jz      loc_18002848A
0x1800281dd  lea     r9, [rsp+68h+var_38]
0x1800281e2  mov     rcx, rbx
0x1800281e5  call    HComOEMEnableDriver
0x1800281ea  cmp     eax, 80004001h
0x1800281ef  jnz     loc_180028414
0x1800281f5  mov     r11, qword ptr cs:IID_IPrintOemUni.Data4
0x1800281fc  xor     r15d, r15d
0x1800281ff  mov     r14, qword ptr cs:IID_IPrintOemUni.Data1
0x180028206  mov     r10, qword ptr cs:IID_IPrintOemUni2.Data4
0x18002820d  mov     rbp, qword ptr cs:IID_IPrintOemUni2.Data1
0x180028214  mov     r8, qword ptr cs:IID_IPrintOemUni3.Data4
0x18002821b  mov     r9, qword ptr cs:IID_IPrintOemUni3.Data1
0x180028222  mov     rcx, [rbx+48h]
0x180028226  test    rcx, rcx
0x180028229  jz      loc_1800284DB
0x18002822f  mov     rax, [rbx+50h]
0x180028233  mov     rdx, ds:rva COMUnidrvProcNames[rsi+r15*8]
0x18002823b  sub     rax, r14
0x18002823e  jnz     short loc_180028247
0x180028240  mov     rax, [rbx+58h]
0x180028244  sub     rax, r11
0x180028247  test    rax, rax
0x18002824a  jnz     loc_1800283CB
0x180028250  mov     rax, [rcx]
0x180028253  mov     rax, [rax+58h]
0x180028257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002825c  mov     r11, qword ptr cs:IID_IPrintOemUni.Data4
0x180028263  mov     ecx, eax
0x180028265  mov     r10, qword ptr cs:IID_IPrintOemUni2.Data4
0x18002826c  mov     r8, qword ptr cs:IID_IPrintOemUni3.Data4
0x180028273  mov     r9, qword ptr cs:IID_IPrintOemUni3.Data1
0x18002827a  mov     r14, qword ptr cs:IID_IPrintOemUni.Data1
0x180028281  mov     rbp, qword ptr cs:IID_IPrintOemUni2.Data1
0x180028288  xor     eax, eax
0x18002828a  mov     rdx, rbx
0x18002828d  test    ecx, ecx
0x18002828f  cmovnz  rdx, rax
0x180028293  test    rdx, rdx
0x180028296  jz      loc_180028379
0x18002829c  mov     rax, [rdi+768h]
0x1800282a3  lea     esi, [r15+20h]
0x1800282a7  movsxd  rcx, esi
0x1800282aa  add     rcx, rcx
0x1800282ad  cmp     qword ptr [rax+rcx*8], 0
0x1800282b2  jnz     loc_180028372
0x1800282b8  mov     [rax+rcx*8], rdx
0x1800282bc  mov     rax, [rdi+768h]
0x1800282c3  mov     [rsp+68h+arg_0], 0
0x1800282cb  mov     [rax+rcx*8+8], rbx
0x1800282d0  cmp     esi, 2Dh ; '-'
0x1800282d3  jnz     short loc_180028348
0x1800282d5  mov     rax, [rbx+50h]
0x1800282d9  mov     rbp, qword ptr cs:IID_IPrintOemUni2.Data1
0x1800282e0  mov     r10, qword ptr cs:IID_IPrintOemUni2.Data4
0x1800282e7  sub     rax, rbp
0x1800282ea  jnz     short loc_1800282F3
0x1800282ec  mov     rax, [rbx+58h]
0x1800282f0  sub     rax, r10
0x1800282f3  test    rax, rax
0x1800282f6  jz      short loc_18002831B
0x1800282f8  mov     rax, [rbx+50h]
0x1800282fc  mov     r9, qword ptr cs:IID_IPrintOemUni3.Data1
0x180028303  mov     r8, qword ptr cs:IID_IPrintOemUni3.Data4
0x18002830a  sub     rax, r9
0x18002830d  jnz     short loc_180028316
0x18002830f  mov     rax, [rbx+58h]
0x180028313  sub     rax, r8
0x180028316  test    rax, rax
0x180028319  jnz     short loc_180028364
0x18002831b  mov     rcx, [rbx+48h]
0x18002831f  lea     rdx, [rsp+68h+arg_0]
0x180028324  mov     [rsp+68h+var_48], rdx
0x180028329  xor     r9d, r9d
0x18002832c  xor     r8d, r8d
0x18002832f  xor     edx, edx
0x180028331  mov     rax, [rcx]
0x180028334  mov     rax, [rax+0D0h]
0x18002833b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028340  test    eax, eax
0x180028342  jz      loc_180028407
0x180028348  mov     r9, qword ptr cs:IID_IPrintOemUni3.Data1
0x18002834f  mov     r8, qword ptr cs:IID_IPrintOemUni3.Data4
0x180028356  mov     rbp, qword ptr cs:IID_IPrintOemUni2.Data1
0x18002835d  mov     r10, qword ptr cs:IID_IPrintOemUni2.Data4
0x180028364  mov     r11, qword ptr cs:IID_IPrintOemUni.Data4
0x18002836b  mov     r14, qword ptr cs:IID_IPrintOemUni.Data1
0x180028372  lea     rsi, cs:180000000h
0x180028379  inc     r15d
0x18002837c  cmp     r15d, 10h
0x180028380  jb      loc_180028222
0x180028386  add     rbx, 0B0h
0x18002838d  add     r12d, 0FFFFFFFFh
0x180028391  jnz     loc_1800281A9
0x180028397  mov     rax, [rdi+768h]
0x18002839e  mov     rcx, [rax+200h]
0x1800283a5  mov     [rdi+778h], rcx
0x1800283ac  mov     eax, 1
0x1800283b1  lea     r11, [rsp+68h+var_28]
0x1800283b6  mov     rbx, [r11+38h]
0x1800283ba  mov     rbp, [r11+40h]
0x1800283be  mov     rsp, r11
0x1800283c1  pop     r15
0x1800283c3  pop     r14
0x1800283c5  pop     r12
0x1800283c7  pop     rdi
0x1800283c8  pop     rsi
0x1800283c9  retn
0x1800283cb  mov     rax, [rbx+50h]
0x1800283cf  sub     rax, rbp
0x1800283d2  jnz     short loc_1800283DB
0x1800283d4  mov     rax, [rbx+58h]
0x1800283d8  sub     rax, r10
0x1800283db  test    rax, rax
0x1800283de  jz      loc_180028250
0x1800283e4  mov     rax, [rbx+50h]
0x1800283e8  sub     rax, r9
0x1800283eb  jnz     short loc_1800283F4
0x1800283ed  mov     rax, [rbx+58h]
0x1800283f1  sub     rax, r8
0x1800283f4  test    rax, rax
0x1800283f7  jz      loc_180028250
0x1800283fd  mov     ecx, 80004002h
0x180028402  jmp     loc_180028288
0x180028407  or      dword ptr [rbx+30h], 8
0x18002840b  or      dword ptr [rdi+74h], 2
0x18002840f  jmp     loc_180028348
0x180028414  test    eax, eax
0x180028416  js      loc_180028397
0x18002841c  or      dword ptr [rbx+30h], 1
0x180028420  mov     edx, dword ptr [rsp+68h+var_38+4]
0x180028424  mov     r8, qword ptr [rsp+68h+var_38+8]
0x180028429  jmp     short loc_18002843B
0x18002842b  movsxd  rax, ds:rva dword_180081CA4[rsi+r9*8]
0x180028433  test    eax, eax
0x180028435  jns     short loc_180028460
0x180028437  add     r8, 10h
0x18002843b  test    edx, edx
0x18002843d  jz      loc_1800281F5
0x180028443  dec     edx
0x180028445  xor     ecx, ecx
0x180028447  cmp     ecx, 20h ; ' '
0x18002844a  jge     short loc_180028437
0x18002844c  mov     eax, [r8]
0x18002844f  movsxd  r9, ecx
0x180028452  cmp     ds:rva dword_180081CA0[rsi+r9*8], eax
0x18002845a  jz      short loc_18002842B
0x18002845c  inc     ecx
0x18002845e  jmp     short loc_180028447
0x180028460  mov     r9, [rdi+768h]
0x180028467  mov     rcx, rax
0x18002846a  add     rcx, rcx
0x18002846d  cmp     qword ptr [r9+rcx*8], 0
0x180028472  jnz     short loc_180028437
0x180028474  mov     rax, [r8+8]
0x180028478  mov     [r9+rcx*8], rax
0x18002847c  mov     rax, [rdi+768h]
0x180028483  mov     [rax+rcx*8+8], rbx
0x180028488  jmp     short loc_180028437
0x18002848a  test    byte ptr [rbx+64h], 4
0x18002848e  jz      short loc_180028496
0x180028490  mov     rax, [rbx+78h]
0x180028494  jmp     short loc_1800284A3
0x180028496  mov     edx, 2
0x18002849b  mov     rcx, rbx
0x18002849e  call    PGetOemEntrypointAddress
0x1800284a3  test    rax, rax
0x1800284a6  jz      loc_1800281F5
0x1800284ac  lea     r8, [rsp+68h+var_38]
0x1800284b1  mov     edx, 10h
0x1800284b6  mov     ecx, 10000h
0x1800284bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284c0  test    eax, eax
0x1800284c2  jz      loc_180028397
0x1800284c8  cmp     dword ptr [rsp+68h+var_38], 10000h
0x1800284d0  jnz     loc_180028397
0x1800284d6  jmp     loc_18002841C
0x1800284db  mov     rcx, [rbx+20h]; hModule
0x1800284df  test    rcx, rcx
0x1800284e2  jz      loc_180028379
0x1800284e8  mov     rdx, ds:rva off_18007A530[rsi+r15*8]; lpProcName
0x1800284f0  call    cs:__imp_GetProcAddress
0x1800284f7  nop     dword ptr [rax+rax+00h]
0x1800284fc  mov     r11, qword ptr cs:IID_IPrintOemUni.Data4
0x180028503  mov     rdx, rax
0x180028506  mov     r14, qword ptr cs:IID_IPrintOemUni.Data1
0x18002850d  mov     r10, qword ptr cs:IID_IPrintOemUni2.Data4
0x180028514  mov     rbp, qword ptr cs:IID_IPrintOemUni2.Data1
0x18002851b  mov     r8, qword ptr cs:IID_IPrintOemUni3.Data4
0x180028522  mov     r9, qword ptr cs:IID_IPrintOemUni3.Data1
0x180028529  jmp     loc_180028293
```
