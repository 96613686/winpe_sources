# ConvertToDIBProc

- ea: `0x180001010`
- end: `0x180001839`
- name: `ConvertToDIBProc`
- size: `2089`
- prototype: `HGLOBAL __fastcall(__int64, unsigned int, unsigned int *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001010`
- `0x180001840`
- `0x1800022a6`
- `0x180002340`
- `0x180003010`

## import_xrefs

- `KERNEL32!GlobalSize` at `0x1800014a4`
- `KERNEL32!GlobalSize` at `0x1800014a4`
- `KERNEL32!GlobalFree` at `0x1800014e4`
- `KERNEL32!GlobalFree` at `0x180001736`
- `KERNEL32!GlobalFree` at `0x1800014e4`
- `KERNEL32!GlobalFree` at `0x180001736`
- `KERNEL32!GlobalReAlloc` at `0x1800014c1`
- `KERNEL32!GlobalReAlloc` at `0x1800014c1`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180001490`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180001490`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000115a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000115a`
- `WindowsCodecs!WICCreateImagingFactory_Proxy` at `0x180001103`
- `WindowsCodecs!WICCreateImagingFactory_Proxy` at `0x180001103`

## pseudocode

```c
HGLOBAL __fastcall ConvertToDIBProc(__int64 a1, unsigned int a2, unsigned int *a3, int a4)
{
  unsigned int i; // edx
  GUID *v9; // rdx
  int v10; // edi
  unsigned int v11; // eax
  unsigned int v12; // ebx
  HGLOBAL v13; // rax
  int v15; // eax
  unsigned int v16; // ebx
  unsigned __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // r8d
  unsigned int v20; // r9d
  unsigned int v21; // r10d
  GUID v22; // xmm0
  __int64 v23; // [rsp+20h] [rbp-E8h] BYREF
  __int64 v24; // [rsp+28h] [rbp-E0h] BYREF
  HGLOBAL phglobal; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v26; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v28; // [rsp+48h] [rbp-C0h]
  int v29; // [rsp+4Ch] [rbp-BCh] BYREF
  unsigned int v30; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+70h] [rbp-98h] BYREF
  LPSTREAM ppstm; // [rsp+78h] [rbp-90h] BYREF
  __int64 v36; // [rsp+80h] [rbp-88h] BYREF
  __int64 v37; // [rsp+88h] [rbp-80h] BYREF
  __int64 v38; // [rsp+90h] [rbp-78h] BYREF
  __int64 v39; // [rsp+98h] [rbp-70h] BYREF
  __int128 v40; // [rsp+A0h] [rbp-68h] BYREF
  GUID Buf1; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v42; // [rsp+C0h] [rbp-48h] BYREF

  v34 = 0;
  ppstm = 0;
  v27 = 0;
  v37 = 0;
  v38 = 0;
  v32 = 0;
  v26 = 0;
  v36 = 0;
  v39 = 0;
  v31 = 0;
  v24 = 0;
  v33 = 0;
  Buf1 = GUID_WICPixelFormat32bppBGRA;
  v42 = 0;
  v23 = 0;
  v40 = 0u;
  v29 = 0;
  phglobal = 0;
  v30 = 0;
  v28 = 0;
  for ( i = 0; ; i += 4096 )
  {
    v28 = i;
    if ( i >= a2 )
      break;
  }
  if ( ((a4 & 2) != 0 || (a4 & 0x80000001) != 0)
    && (int)WICCreateImagingFactory_Proxy(567, &v27) >= 0
    && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 112LL))(v27, &v34) >= 0
    && (*(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v34 + 128LL))(v34, a1, a2) >= 0
    && CreateStreamOnHGlobal(0, 0, &ppstm) >= 0 )
  {
    if ( (a4 & 1) != 0 )
    {
      v9 = &CLSID_WICPngDecoder2;
    }
    else
    {
      v9 = &CLSID_WICJpegDecoder;
      if ( (a4 & 2) == 0 )
        v9 = 0;
    }
    if ( (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v27 + 48LL))(v27, v9, &v37) >= 0
      && (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v37)(v37, &IID_IWICBitmapDecoderInfo, &v39) >= 0
      && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 200LL))(v39, &v32) >= 0
      && (*(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v32 + 32LL))(v32, v34, 0) >= 0
      && (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 96LL))(v32, &v29) >= 0
      && v29
      && (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 104LL))(v32, 0, &v26) >= 0
      && (*(int (__fastcall **)(__int64, __int64 *, char *))(*(_QWORD *)v26 + 24LL))(v26, &v23, (char *)&v23 + 4) >= 0
      && (*(int (__fastcall **)(__int64, char *, __int128 *))(*(_QWORD *)v26 + 40LL))(v26, (char *)&v40 + 8, &v40) >= 0 )
    {
      if ( (a4 & 2) != 0 )
      {
        if ( (*(int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v26 + 32LL))(v26, &Buf1) < 0 )
          goto LABEL_44;
        if ( !memcmp_0(&Buf1, &GUID_WICPixelFormat24bppBGR, 0x10u)
          || !memcmp_0(&Buf1, &GUID_WICPixelFormat8bppGray, 0x10u) )
        {
          v22 = GUID_WICPixelFormat24bppBGR;
        }
        else
        {
          v22 = GUID_WICPixelFormat32bppBGRA;
        }
        Buf1 = v22;
      }
      v10 = 0;
      if ( a4 < 0 )
      {
        if ( !memcmp_0(&Buf1, &GUID_WICPixelFormat32bppBGRA, 0x10u) )
        {
          v16 = v23;
          v17 = 32LL * (unsigned int)v23;
          if ( v17 > 0xFFFFFFFF )
            goto LABEL_44;
          v18 = v17 + 31;
          if ( v18 < (unsigned int)(32 * v23) )
            goto LABEL_44;
          v19 = (v18 >> 3) & 0xFFFFFFFC;
        }
        else
        {
          if ( memcmp_0(&Buf1, &GUID_WICPixelFormat24bppBGR, 0x10u) )
            goto LABEL_44;
          v16 = v23;
          if ( !(unsigned int)BitmapWidth((unsigned int)v23, 24, &v30) )
            goto LABEL_44;
          v19 = v30;
        }
        if ( v16 + 31 < v16 )
          goto LABEL_44;
        v20 = -HIDWORD(v23);
        if ( SHIDWORD(v23) > 0 )
          v20 = HIDWORD(v23);
        if ( v20 )
        {
          v21 = ((int)(v16 + 31) >> 3) & 0xFFFFFFFC;
          if ( v21 < 0xFFFFFFFF / v20 && v19 < 0xFFFFFFFF / v20 )
            v10 = v21 * v20;
        }
      }
      if ( (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v27 + 48LL))(v27, &CLSID_WICBmpEncoder, &v38) >= 0
        && (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v38)(v38, &IID_IWICBitmapEncoderInfo, &v36) >= 0
        && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 184LL))(v36, &v31) >= 0
        && (*(int (__fastcall **)(__int64, LPSTREAM, __int64))(*(_QWORD *)v31 + 24LL))(v31, ppstm, 2) >= 0
        && (*(int (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v31 + 80LL))(v31, &v24, 0) >= 0
        && (*(int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 24LL))(v24, 0) >= 0
        && (*(int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v24 + 32LL))(
             v24,
             (unsigned int)v23,
             HIDWORD(v23)) >= 0
        && (*(int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v24 + 48LL))(v24, &Buf1) >= 0
        && (*(int (__fastcall **)(__int64))(*(_QWORD *)v24 + 40LL))(v24) >= 0 )
      {
        if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 72LL))(v27, &v33) < 0
          || ((v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 48LL))(v26, v33),
               (int)(v15 + 0x80000000) < 0)
           || v15 == -2003292347)
          && (v15 == -2003292347 || (*(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 64LL))(v24, v33) >= 0) )
        {
          *(_QWORD *)&v42 = 0;
          *((_QWORD *)&v42 + 1) = v23;
          if ( (*(int (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v24 + 88LL))(v24, v26, &v42) >= 0
            && (*(int (__fastcall **)(__int64))(*(_QWORD *)v24 + 96LL))(v24) >= 0
            && (*(int (__fastcall **)(__int64))(*(_QWORD *)v31 + 88LL))(v31) >= 0
            && GetHGlobalFromStream(ppstm, &phglobal) >= 0 )
          {
            if ( phglobal )
            {
              v11 = GlobalSize(phglobal);
              v12 = v11;
              if ( v11 > 0x36 )
              {
                if ( v10 )
                {
                  v13 = GlobalReAlloc(phglobal, v11 + v10, 0);
                  if ( !v13 )
                  {
                    GlobalFree(phglobal);
                    phglobal = 0;
                    goto LABEL_44;
                  }
                  phglobal = v13;
                }
                if ( a3 )
                  *a3 = v12;
              }
            }
          }
        }
      }
    }
  }
LABEL_44:
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( ppstm )
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
  return phglobal;
}

```

## disassembly

```asm
0x180001010  mov     r11, rsp
0x180001013  mov     [r11+20h], rbx
0x180001017  push    rsi
0x180001018  push    rdi
0x180001019  push    r12
0x18000101b  push    r14
0x18000101d  push    r15
0x18000101f  sub     rsp, 0E0h
0x180001026  mov     rax, cs:__security_cookie
0x18000102d  xor     rax, rsp
0x180001030  mov     [rsp+108h+var_38], rax
0x180001038  mov     r14d, r9d
0x18000103b  mov     r15, r8
0x18000103e  mov     ebx, edx
0x180001040  mov     rdi, rcx
0x180001043  xor     r12d, r12d
0x180001046  mov     [rsp+108h+var_98], r12
0x18000104b  mov     [rsp+108h+ppstm], r12
0x180001050  mov     [rsp+108h+var_C8], r12
0x180001055  mov     [r11-80h], r12
0x180001059  mov     [r11-78h], r12
0x18000105d  mov     [rsp+108h+var_A8], r12
0x180001062  mov     [rsp+108h+var_D0], r12
0x180001067  mov     [r11-88h], r12
0x18000106e  mov     [r11-70h], r12
0x180001072  mov     [rsp+108h+var_B0], r12
0x180001077  mov     [rsp+108h+var_E0], r12
0x18000107c  mov     [rsp+108h+var_A0], r12
0x180001081  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x180001088  movups  xmmword ptr [r11-58h], xmm0
0x18000108d  xorps   xmm0, xmm0
0x180001090  movups  xmmword ptr [r11-48h], xmm0
0x180001095  mov     [rsp+108h+var_E8], r12d
0x18000109a  mov     [rsp+108h+var_E4], r12d
0x18000109f  movsd   qword ptr [r11-60h], xmm0
0x1800010a5  movsd   qword ptr [r11-68h], xmm0
0x1800010ab  mov     [rsp+108h+var_BC], r12d
0x1800010b0  mov     [rsp+108h+phglobal], r12
0x1800010b5  mov     [rsp+108h+var_B8], r12d
0x1800010ba  mov     [rsp+108h+var_C0], r12d
0x1800010bf  mov     edx, r12d
0x1800010c2  mov     [rsp+108h+var_C0], edx
0x1800010c6  cmp     edx, ebx
0x1800010c8  jnb     short loc_1800010D8
0x1800010ca  mov     eax, edx
0x1800010cc  movzx   ecx, byte ptr [rax+rdi]
0x1800010d0  add     edx, 1000h
0x1800010d6  jmp     short loc_1800010C2
0x1800010d8  movzx   ecx, byte ptr [rbx+rdi-1]
0x1800010dd  jmp     short loc_1800010E4
0x1800010df  jmp     loc_1800014F3
0x1800010e4  mov     esi, r14d
0x1800010e7  and     esi, 2
0x1800010ea  jnz     short loc_1800010F9
0x1800010ec  test    r14d, 80000001h
0x1800010f3  jz      loc_1800014F3
0x1800010f9  lea     rdx, [rsp+108h+var_C8]
0x1800010fe  mov     ecx, 237h
0x180001103  call    cs:__imp_WICCreateImagingFactory_Proxy
0x180001109  test    eax, eax
0x18000110b  js      loc_1800014F3
0x180001111  mov     rcx, [rsp+108h+var_C8]
0x180001116  mov     rax, [rcx]
0x180001119  lea     rdx, [rsp+108h+var_98]
0x18000111e  mov     rax, [rax+70h]
0x180001122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001127  test    eax, eax
0x180001129  js      loc_1800014F3
0x18000112f  mov     rcx, [rsp+108h+var_98]
0x180001134  mov     rax, [rcx]
0x180001137  mov     r8d, ebx
0x18000113a  mov     rdx, rdi
0x18000113d  mov     rax, [rax+80h]
0x180001144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001149  test    eax, eax
0x18000114b  js      loc_1800014F3
0x180001151  lea     r8, [rsp+108h+ppstm]; ppstm
0x180001156  xor     edx, edx; fDeleteOnRelease
0x180001158  xor     ecx, ecx; hGlobal
0x18000115a  call    cs:__imp_CreateStreamOnHGlobal
0x180001160  test    eax, eax
0x180001162  js      loc_1800014F3
0x180001168  test    r14b, 1
0x18000116c  jz      loc_18000175E
0x180001172  lea     rdx, CLSID_WICPngDecoder2
0x180001179  mov     rcx, [rsp+108h+var_C8]
0x18000117e  mov     rax, [rcx]
0x180001181  lea     r8, [rsp+108h+var_80]
0x180001189  mov     rax, [rax+30h]
0x18000118d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001192  test    eax, eax
0x180001194  js      loc_1800014F3
0x18000119a  mov     rcx, [rsp+108h+var_80]
0x1800011a2  mov     rax, [rcx]
0x1800011a5  lea     r8, [rsp+108h+var_70]
0x1800011ad  lea     rdx, IID_IWICBitmapDecoderInfo
0x1800011b4  mov     rax, [rax]
0x1800011b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011bc  test    eax, eax
0x1800011be  js      loc_1800014F3
0x1800011c4  mov     rcx, [rsp+108h+var_70]
0x1800011cc  mov     rax, [rcx]
0x1800011cf  lea     rdx, [rsp+108h+var_A8]
0x1800011d4  mov     rax, [rax+0C8h]
0x1800011db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011e0  test    eax, eax
0x1800011e2  js      loc_1800014F3
0x1800011e8  mov     rcx, [rsp+108h+var_A8]
0x1800011ed  mov     rax, [rcx]
0x1800011f0  xor     r8d, r8d
0x1800011f3  mov     rdx, [rsp+108h+var_98]
0x1800011f8  mov     rax, [rax+20h]
0x1800011fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001201  test    eax, eax
0x180001203  js      loc_1800014F3
0x180001209  mov     rcx, [rsp+108h+var_A8]
0x18000120e  mov     rax, [rcx]
0x180001211  lea     rdx, [rsp+108h+var_BC]
0x180001216  mov     rax, [rax+60h]
0x18000121a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000121f  test    eax, eax
0x180001221  js      loc_1800014F3
0x180001227  cmp     [rsp+108h+var_BC], 1
0x18000122c  jb      loc_1800014F3
0x180001232  mov     rcx, [rsp+108h+var_A8]
0x180001237  mov     rax, [rcx]
0x18000123a  lea     r8, [rsp+108h+var_D0]
0x18000123f  xor     edx, edx
0x180001241  mov     rax, [rax+68h]
0x180001245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000124a  test    eax, eax
0x18000124c  js      loc_1800014F3
0x180001252  mov     rcx, [rsp+108h+var_D0]
0x180001257  mov     rax, [rcx]
0x18000125a  lea     r8, [rsp+108h+var_E4]
0x18000125f  lea     rdx, [rsp+108h+var_E8]
0x180001264  mov     rax, [rax+18h]
0x180001268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000126d  test    eax, eax
0x18000126f  js      loc_1800014F3
0x180001275  mov     rcx, [rsp+108h+var_D0]
0x18000127a  mov     rax, [rcx]
0x18000127d  lea     r8, [rsp+108h+var_68]
0x180001285  lea     rdx, [rsp+108h+var_60]
0x18000128d  mov     rax, [rax+28h]
0x180001291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001296  test    eax, eax
0x180001298  js      loc_1800014F3
0x18000129e  test    esi, esi
0x1800012a0  jnz     loc_180001770
0x1800012a6  mov     edi, r12d
0x1800012a9  test    r14d, r14d
0x1800012ac  js      loc_180001688
0x1800012b2  mov     rcx, [rsp+108h+var_C8]
0x1800012b7  mov     rax, [rcx]
0x1800012ba  lea     r8, [rsp+108h+var_78]
0x1800012c2  lea     rdx, CLSID_WICBmpEncoder
0x1800012c9  mov     rax, [rax+30h]
0x1800012cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012d2  test    eax, eax
0x1800012d4  js      loc_1800014F3
0x1800012da  mov     rcx, [rsp+108h+var_78]
0x1800012e2  mov     rax, [rcx]
0x1800012e5  lea     r8, [rsp+108h+var_88]
0x1800012ed  lea     rdx, IID_IWICBitmapEncoderInfo
0x1800012f4  mov     rax, [rax]
0x1800012f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012fc  test    eax, eax
0x1800012fe  js      loc_1800014F3
0x180001304  mov     rcx, [rsp+108h+var_88]
0x18000130c  mov     rax, [rcx]
0x18000130f  lea     rdx, [rsp+108h+var_B0]
0x180001314  mov     rax, [rax+0B8h]
0x18000131b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001320  test    eax, eax
0x180001322  js      loc_1800014F3
0x180001328  mov     rcx, [rsp+108h+var_B0]
0x18000132d  mov     rax, [rcx]
0x180001330  mov     r8d, 2
0x180001336  mov     rdx, [rsp+108h+ppstm]
0x18000133b  mov     rax, [rax+18h]
0x18000133f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001344  test    eax, eax
0x180001346  js      loc_1800014F3
0x18000134c  mov     rcx, [rsp+108h+var_B0]
0x180001351  mov     rax, [rcx]
0x180001354  xor     r8d, r8d
0x180001357  lea     rdx, [rsp+108h+var_E0]
0x18000135c  mov     rax, [rax+50h]
0x180001360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001365  test    eax, eax
0x180001367  js      loc_1800014F3
0x18000136d  mov     rcx, [rsp+108h+var_E0]
0x180001372  mov     rax, [rcx]
0x180001375  xor     edx, edx
0x180001377  mov     rax, [rax+18h]
0x18000137b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001380  test    eax, eax
0x180001382  js      loc_1800014F3
0x180001388  mov     rcx, [rsp+108h+var_E0]
0x18000138d  mov     rax, [rcx]
0x180001390  mov     r8d, [rsp+108h+var_E4]
0x180001395  mov     edx, [rsp+108h+var_E8]
0x180001399  mov     rax, [rax+20h]
0x18000139d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013a2  test    eax, eax
0x1800013a4  js      loc_1800014F3
0x1800013aa  mov     rcx, [rsp+108h+var_E0]
0x1800013af  mov     rax, [rcx]
0x1800013b2  lea     rdx, [rsp+108h+Buf1]
0x1800013ba  mov     rax, [rax+30h]
0x1800013be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013c3  test    eax, eax
0x1800013c5  js      loc_1800014F3
0x1800013cb  mov     rcx, [rsp+108h+var_E0]
0x1800013d0  mov     rax, [rcx]
0x1800013d3  movsd   xmm2, [rsp+108h+var_68]
0x1800013dc  movsd   xmm1, [rsp+108h+var_60]
0x1800013e5  mov     rax, [rax+28h]
0x1800013e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013ee  test    eax, eax
0x1800013f0  js      loc_1800014F3
0x1800013f6  mov     rcx, [rsp+108h+var_C8]
0x1800013fb  mov     rax, [rcx]
0x1800013fe  lea     rdx, [rsp+108h+var_A0]
0x180001403  mov     rax, [rax+48h]
0x180001407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000140c  test    eax, eax
0x18000140e  jns     loc_180001634
0x180001414  mov     [rsp+108h+var_48], r12
0x18000141c  mov     eax, [rsp+108h+var_E8]
0x180001420  mov     [rsp+108h+var_40], eax
0x180001427  mov     eax, [rsp+108h+var_E4]
0x18000142b  mov     [rsp+108h+var_3C], eax
0x180001432  mov     rcx, [rsp+108h+var_E0]
0x180001437  mov     rax, [rcx]
0x18000143a  lea     r8, [rsp+108h+var_48]
0x180001442  mov     rdx, [rsp+108h+var_D0]
0x180001447  mov     rax, [rax+58h]
0x18000144b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001450  test    eax, eax
0x180001452  js      loc_1800014F3
0x180001458  mov     rcx, [rsp+108h+var_E0]
0x18000145d  mov     rax, [rcx]
0x180001460  mov     rax, [rax+60h]
0x180001464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001469  test    eax, eax
0x18000146b  js      loc_1800014F3
0x180001471  mov     rcx, [rsp+108h+var_B0]
0x180001476  mov     rax, [rcx]
0x180001479  mov     rax, [rax+58h]
0x18000147d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001482  test    eax, eax
0x180001484  js      short loc_1800014F3
0x180001486  lea     rdx, [rsp+108h+phglobal]; phglobal
0x18000148b  mov     rcx, [rsp+108h+ppstm]; pstm
0x180001490  call    cs:__imp_GetHGlobalFromStream
0x180001496  test    eax, eax
0x180001498  js      short loc_1800014F3
0x18000149a  mov     rcx, [rsp+108h+phglobal]; hMem
0x18000149f  test    rcx, rcx
0x1800014a2  jz      short loc_1800014F3
0x1800014a4  call    cs:__imp_GlobalSize
0x1800014aa  mov     rbx, rax
0x1800014ad  cmp     eax, 36h ; '6'
0x1800014b0  jbe     short loc_1800014F3
0x1800014b2  test    edi, edi
0x1800014b4  jz      short loc_1800014D5
0x1800014b6  lea     edx, [rax+rdi]; dwBytes
0x1800014b9  xor     r8d, r8d; uFlags
0x1800014bc  mov     rcx, [rsp+108h+phglobal]; hMem
0x1800014c1  call    cs:__imp_GlobalReAlloc
0x1800014c7  test    rax, rax
0x1800014ca  jz      loc_180001731
0x1800014d0  mov     [rsp+108h+phglobal], rax
0x1800014d5  test    r15, r15
0x1800014d8  jz      short loc_1800014DD
0x1800014da  mov     [r15], ebx
0x1800014dd  jmp     short loc_1800014F3
0x1800014df  mov     rcx, [rsp+108h+phglobal]; hMem
0x1800014e4  call    cs:__imp_GlobalFree
0x1800014ea  mov     [rsp+108h+phglobal], 0
0x1800014f3  mov     rcx, [rsp+108h+var_A0]
0x1800014f8  test    rcx, rcx
0x1800014fb  jz      short loc_180001509
0x1800014fd  mov     rax, [rcx]
0x180001500  mov     rax, [rax+10h]
0x180001504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001509  mov     rcx, [rsp+108h+var_E0]
0x18000150e  test    rcx, rcx
0x180001511  jz      short loc_18000151F
0x180001513  mov     rax, [rcx]
0x180001516  mov     rax, [rax+10h]
0x18000151a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000151f  mov     rcx, [rsp+108h+var_88]
0x180001527  test    rcx, rcx
0x18000152a  jz      short loc_180001538
0x18000152c  mov     rax, [rcx]
0x18000152f  mov     rax, [rax+10h]
0x180001533  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
