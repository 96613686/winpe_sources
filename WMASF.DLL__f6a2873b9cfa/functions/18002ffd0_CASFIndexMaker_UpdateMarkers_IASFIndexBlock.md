# CASFIndexMaker::UpdateMarkers(IASFIndexBlock *)

- ea: `0x18002ffd0`
- end: `0x1800302a3`
- name: `?UpdateMarkers@CASFIndexMaker@@MEAAJPEAUIASFIndexBlock@@@Z`
- size: `723`
- prototype: `__int64 __fastcall(CASFIndexMaker *__hidden this, struct IASFIndexBlock *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800015d0`
- `0x18002e900`
- `0x18002ebb0`
- `0x18002ffd0`
- `0x180030a00`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexMaker::UpdateMarkers(CASFIndexMaker *this, struct IASFIndexBlock *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  unsigned __int16 i; // r14
  int v7; // ebx
  __int64 v8; // rbx
  unsigned __int16 j; // si
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // r8
  unsigned __int16 v13; // di
  int v14; // eax
  __int64 v16; // [rsp+30h] [rbp-29h] BYREF
  __int64 v17; // [rsp+38h] [rbp-21h] BYREF
  _WORD v18[2]; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int16 v19; // [rsp+44h] [rbp-15h] BYREF
  _WORD v20[2]; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int16 v21; // [rsp+4Ch] [rbp-Dh] BYREF
  __int64 v22; // [rsp+50h] [rbp-9h] BYREF
  __int64 v23; // [rsp+58h] [rbp-1h] BYREF
  __int64 v24; // [rsp+60h] [rbp+7h] BYREF
  __int64 v25; // [rsp+68h] [rbp+Fh] BYREF
  int v26; // [rsp+70h] [rbp+17h]
  __int64 v27; // [rsp+78h] [rbp+1Fh] BYREF
  int v28; // [rsp+80h] [rbp+27h]

  v2 = *(_QWORD *)a2;
  v23 = 0;
  v24 = 0;
  (*(void (__fastcall **)(struct IASFIndexBlock *, __int64 *, __int64 *))(v2 + 104))(a2, &v23, &v24);
  v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 10);
  v17 = 0;
  if ( (int)ASFFindHeaderObject(v5, (__int64)&CLSID_ASFMarkerObject, (__int64)&IID_IASFMarkerObject, (__int64)&v17) >= 0 )
  {
    v21 = 0;
    v20[0] = 0;
    (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v17 + 88LL))(v17, &v21);
    (*(void (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v17 + 80LL))(v17, v20);
    for ( i = 0; i < v21; ++i )
    {
      v16 = 0;
      (*(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 120LL))(v17, i, &v16);
      v25 = 0;
      v26 = 0;
      v22 = 0;
      v27 = 0;
      v28 = 0;
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 24LL))(v16, &v25);
      v7 = ASFGetTimeBase(*((_QWORD *)this + 10), 0, &v27);
      if ( v7 < 0 )
      {
        if ( v16 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          v16 = 0;
        }
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        return (unsigned int)v7;
      }
      ASFPresTimeToTime(&v27, &v25, &v22);
      v8 = v22 / 10000;
      if ( v22 / 10000 >= v23 && v8 <= v24 )
      {
        for ( j = 0; j < v20[0]; ++j )
        {
          v19 = 0;
          v18[0] = 0;
          v22 = 0;
          (*(void (__fastcall **)(__int64, _QWORD, unsigned __int16 *, _WORD *))(*(_QWORD *)v17 + 96LL))(
            v17,
            j,
            &v19,
            v18);
          v10 = (*(__int64 (__fastcall **)(struct IASFIndexBlock *, __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)a2 + 120LL))(
                  a2,
                  v8,
                  v19,
                  v18[0],
                  &v22);
          if ( v10 < 0 )
          {
            v13 = v18[0];
            if ( v10 == -1072887824 )
            {
              do
              {
                if ( v13 >= 3u )
                  break;
                v14 = (*(__int64 (__fastcall **)(struct IASFIndexBlock *, __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)a2 + 120LL))(
                        a2,
                        v8,
                        v19,
                        ++v13,
                        &v22);
                if ( v14 >= 0 )
                  goto LABEL_9;
              }
              while ( v14 == -1072887824 );
              v13 = v18[0];
            }
            v11 = -1;
            v12 = v13;
          }
          else
          {
LABEL_9:
            v11 = v22;
            v12 = v18[0];
          }
          (*(void (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v16 + 64LL))(v16, v19, v12, v11);
        }
      }
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    if ( v17 )
      (*(void (**)(void))(*(_QWORD *)v17 + 16LL))();
  }
  return 0;
}

```

## disassembly

```asm
0x18002ffd0  mov     [rsp-8+arg_10], rbx
0x18002ffd5  mov     [rsp-8+arg_18], rsi
0x18002ffda  push    rbp
0x18002ffdb  push    rdi
0x18002ffdc  push    r13
0x18002ffde  push    r14
0x18002ffe0  push    r15
0x18002ffe2  lea     rbp, [rsp-37h]
0x18002ffe7  sub     rsp, 90h
0x18002ffee  mov     rax, cs:__security_cookie
0x18002fff5  xor     rax, rsp
0x18002fff8  mov     [rbp+57h+var_28], rax
0x18002fffc  mov     rax, [rdx]
0x18002ffff  lea     r8, [rbp+57h+var_50]
0x180030003  mov     r15, rdx
0x180030006  mov     [rbp+57h+var_58], 0
0x18003000e  mov     r13, rcx
0x180030011  mov     [rbp+57h+var_50], 0
0x180030019  lea     rdx, [rbp+57h+var_58]
0x18003001d  mov     rcx, r15
0x180030020  mov     rax, [rax+68h]
0x180030024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030029  mov     rcx, [r13+50h]
0x18003002d  lea     r9, [rbp+57h+var_78]
0x180030031  lea     r8, IID_IASFMarkerObject
0x180030038  mov     [rbp+57h+var_78], 0
0x180030040  lea     rdx, CLSID_ASFMarkerObject
0x180030047  call    ASFFindHeaderObject
0x18003004c  test    eax, eax
0x18003004e  js      loc_180030279
0x180030054  mov     rcx, [rbp+57h+var_78]
0x180030058  lea     rdx, [rbp+57h+var_64]
0x18003005c  xor     eax, eax
0x18003005e  mov     [rbp+57h+var_64], ax
0x180030062  mov     [rbp+57h+var_68], ax
0x180030066  mov     rax, [rcx]
0x180030069  mov     rax, [rax+58h]
0x18003006d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030072  mov     rcx, [rbp+57h+var_78]
0x180030076  lea     rdx, [rbp+57h+var_68]
0x18003007a  mov     rax, [rcx]
0x18003007d  mov     rax, [rax+50h]
0x180030081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030086  xor     r14d, r14d
0x180030089  mov     rcx, [rbp+57h+var_78]
0x18003008d  cmp     r14w, [rbp+57h+var_64]
0x180030092  jnb     loc_180030268
0x180030098  mov     [rbp+57h+var_80], 0
0x1800300a0  lea     r8, [rbp+57h+var_80]
0x1800300a4  mov     rax, [rcx]
0x1800300a7  movzx   edx, r14w
0x1800300ab  mov     rax, [rax+78h]
0x1800300af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300b4  mov     rcx, [rbp+57h+var_80]
0x1800300b8  lea     rdx, [rbp+57h+var_48]
0x1800300bc  xor     eax, eax
0x1800300be  mov     [rbp+57h+var_48], rax
0x1800300c2  mov     [rbp+57h+var_40], eax
0x1800300c5  mov     [rbp+57h+var_60], rax
0x1800300c9  mov     [rbp+57h+var_38], rax
0x1800300cd  mov     [rbp+57h+var_30], eax
0x1800300d0  mov     rax, [rcx]
0x1800300d3  mov     rax, [rax+18h]
0x1800300d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300dc  mov     rcx, [r13+50h]
0x1800300e0  lea     r8, [rbp+57h+var_38]
0x1800300e4  xor     edx, edx
0x1800300e6  call    ASFGetTimeBase
0x1800300eb  mov     ebx, eax
0x1800300ed  test    eax, eax
0x1800300ef  js      loc_180030232
0x1800300f5  lea     r8, [rbp+57h+var_60]
0x1800300f9  lea     rdx, [rbp+57h+var_48]
0x1800300fd  lea     rcx, [rbp+57h+var_38]
0x180030101  call    ASFPresTimeToTime
0x180030106  mov     rax, 346DC5D63886594Bh
0x180030110  imul    [rbp+57h+var_60]
0x180030114  mov     rbx, rdx
0x180030117  sar     rbx, 0Bh
0x18003011b  mov     rax, rbx
0x18003011e  shr     rax, 3Fh
0x180030122  add     rbx, rax
0x180030125  cmp     rbx, [rbp+57h+var_58]
0x180030129  jl      loc_180030214
0x18003012f  cmp     rbx, [rbp+57h+var_50]
0x180030133  jg      loc_180030214
0x180030139  xor     esi, esi
0x18003013b  xor     eax, eax
0x18003013d  cmp     ax, [rbp+57h+var_68]
0x180030141  jnb     loc_180030214
0x180030147  mov     rcx, [rbp+57h+var_78]
0x18003014b  lea     r9, [rbp+57h+var_70]
0x18003014f  xor     eax, eax
0x180030151  lea     r8, [rbp+57h+var_6C]
0x180030155  mov     [rbp+57h+var_6C], ax
0x180030159  movzx   edx, si
0x18003015c  mov     [rbp+57h+var_70], ax
0x180030160  mov     [rbp+57h+var_60], rax
0x180030164  mov     rax, [rcx]
0x180030167  mov     rax, [rax+60h]
0x18003016b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030170  mov     rax, [r15]
0x180030173  lea     rcx, [rbp+57h+var_60]
0x180030177  movzx   r9d, [rbp+57h+var_70]
0x18003017c  mov     rdx, rbx
0x18003017f  movzx   r8d, [rbp+57h+var_6C]
0x180030184  mov     [rsp+0B0h+var_90], rcx
0x180030189  mov     rcx, r15
0x18003018c  mov     rax, [rax+78h]
0x180030190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030195  test    eax, eax
0x180030197  js      short loc_1800301A4
0x180030199  mov     r9, [rbp+57h+var_60]
0x18003019d  movzx   r8d, [rbp+57h+var_70]
0x1800301a2  jmp     short loc_1800301F3
0x1800301a4  movzx   edi, [rbp+57h+var_70]
0x1800301a8  cmp     eax, 0C00D07F0h
0x1800301ad  jnz     short loc_1800301EB
0x1800301af  cmp     di, 3
0x1800301b3  jnb     short loc_1800301E7
0x1800301b5  mov     rax, [r15]
0x1800301b8  lea     rcx, [rbp+57h+var_60]
0x1800301bc  movzx   r8d, [rbp+57h+var_6C]
0x1800301c1  inc     di
0x1800301c4  mov     [rsp+0B0h+var_90], rcx
0x1800301c9  movzx   r9d, di
0x1800301cd  mov     rdx, rbx
0x1800301d0  mov     rcx, r15
0x1800301d3  mov     rax, [rax+78h]
0x1800301d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301dc  test    eax, eax
0x1800301de  jns     short loc_180030199
0x1800301e0  cmp     eax, 0C00D07F0h
0x1800301e5  jz      short loc_1800301AF
0x1800301e7  movzx   edi, [rbp+57h+var_70]
0x1800301eb  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800301ef  movzx   r8d, di
0x1800301f3  mov     rcx, [rbp+57h+var_80]
0x1800301f7  movzx   edx, [rbp+57h+var_6C]
0x1800301fb  mov     rax, [rcx]
0x1800301fe  mov     rax, [rax+40h]
0x180030202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030207  inc     si
0x18003020a  cmp     si, [rbp+57h+var_68]
0x18003020e  jb      loc_180030147
0x180030214  mov     rcx, [rbp+57h+var_80]
0x180030218  test    rcx, rcx
0x18003021b  jz      short loc_180030229
0x18003021d  mov     rax, [rcx]
0x180030220  mov     rax, [rax+10h]
0x180030224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030229  inc     r14w
0x18003022d  jmp     loc_180030089
0x180030232  mov     rcx, [rbp+57h+var_80]
0x180030236  test    rcx, rcx
0x180030239  jz      short loc_18003024F
0x18003023b  mov     rax, [rcx]
0x18003023e  mov     rax, [rax+10h]
0x180030242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030247  mov     [rbp+57h+var_80], 0
0x18003024f  mov     rcx, [rbp+57h+var_78]
0x180030253  test    rcx, rcx
0x180030256  jz      short loc_180030264
0x180030258  mov     rax, [rcx]
0x18003025b  mov     rax, [rax+10h]
0x18003025f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030264  mov     eax, ebx
0x180030266  jmp     short loc_18003027B
0x180030268  test    rcx, rcx
0x18003026b  jz      short loc_180030279
0x18003026d  mov     rax, [rcx]
0x180030270  mov     rax, [rax+10h]
0x180030274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030279  xor     eax, eax
0x18003027b  mov     rcx, [rbp+57h+var_28]
0x18003027f  xor     rcx, rsp; StackCookie
0x180030282  call    __security_check_cookie
0x180030287  lea     r11, [rsp+0B0h+var_20]
0x18003028f  mov     rbx, [r11+40h]
0x180030293  mov     rsi, [r11+48h]
0x180030297  mov     rsp, r11
0x18003029a  pop     r15
0x18003029c  pop     r14
0x18003029e  pop     r13
0x1800302a0  pop     rdi
0x1800302a1  pop     rbp
0x1800302a2  retn
```
