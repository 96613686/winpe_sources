# ResizeImageByDimensionWithMetadata

- ea: `0x1800068f0`
- end: `0x180006d53`
- name: `ResizeImageByDimensionWithMetadata`
- size: `1123`
- prototype: `__int64 __fastcall(__int64 *, __int64, void (__fastcall ***)(_QWORD, GUID *, __int64 *), unsigned int, unsigned int, const WCHAR *, int, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006d60`

## callees

- `0x180005df8`
- `0x1800068f0`
- `0x18000a136`
- `0x18000a190`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ResizeImageByDimensionWithMetadata(
        __int64 *a1,
        __int64 a2,
        void (__fastcall ***a3)(_QWORD, GUID *, __int64 *),
        unsigned int a4,
        unsigned int a5,
        const WCHAR *a6,
        int a7,
        int a8,
        __int64 a9)
{
  __int64 v9; // rax
  int v14; // eax
  __int64 v15; // rcx
  int ContainerFormatFromMimeType; // ebx
  void (*v17)(void); // rax
  unsigned int v19; // ecx
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rcx
  void (*v23)(void); // rax
  int v24; // eax
  int v25; // eax
  __int64 v26; // rcx
  void (*v27)(void); // rax
  __int64 (__fastcall *v28)(__int64, GUID *); // rax
  __int64 v29; // rcx
  void (*v30)(void); // rax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // [rsp+30h] [rbp-81h] BYREF
  __int64 v36; // [rsp+38h] [rbp-79h] BYREF
  __int64 v37; // [rsp+40h] [rbp-71h] BYREF
  __int64 v38; // [rsp+48h] [rbp-69h] BYREF
  __int64 v39; // [rsp+50h] [rbp-61h] BYREF
  __int64 v40; // [rsp+58h] [rbp-59h] BYREF
  GUID v41; // [rsp+60h] [rbp-51h] BYREF
  GUID Buf2; // [rsp+70h] [rbp-41h] BYREF
  GUID Buf1; // [rsp+80h] [rbp-31h] BYREF
  GUID v44; // [rsp+90h] [rbp-21h] BYREF

  v9 = *a1;
  v35 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v9 + 112))(a1, &v35);
  v15 = v35;
  ContainerFormatFromMimeType = v14;
  if ( v14 < 0 )
    goto LABEL_2;
  ContainerFormatFromMimeType = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 112LL))(v35, a9);
  if ( ContainerFormatFromMimeType < 0
    || (v41 = GUID_NULL,
        ContainerFormatFromMimeType = GetContainerFormatFromMimeType(v19, a6, (__int64)&v41),
        ContainerFormatFromMimeType < 0) )
  {
    v15 = v35;
LABEL_2:
    if ( !v15 )
      return (unsigned int)ContainerFormatFromMimeType;
    v17 = *(void (**)(void))(*(_QWORD *)v15 + 16LL);
LABEL_4:
    v17();
    return (unsigned int)ContainerFormatFromMimeType;
  }
  v20 = *a1;
  v36 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD, __int64 *))(v20 + 64))(a1, &v41, 0, &v36);
  v22 = v36;
  ContainerFormatFromMimeType = v21;
  if ( v21 < 0
    || (v24 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v36 + 24LL))(v36, v35, 2),
        v22 = v36,
        ContainerFormatFromMimeType = v24,
        v24 < 0) )
  {
    if ( !v22 )
    {
LABEL_13:
      if ( !v35 )
        return (unsigned int)ContainerFormatFromMimeType;
      v17 = *(void (**)(void))(*(_QWORD *)v35 + 16LL);
      goto LABEL_4;
    }
    v23 = *(void (**)(void))(*(_QWORD *)v22 + 16LL);
LABEL_12:
    v23();
    goto LABEL_13;
  }
  v37 = 0;
  v25 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v36 + 80LL))(v36, &v37, 0);
  v26 = v37;
  ContainerFormatFromMimeType = v25;
  if ( v25 < 0 )
    goto LABEL_17;
  ContainerFormatFromMimeType = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37 + 24LL))(v37, 0);
  if ( ContainerFormatFromMimeType < 0 )
  {
LABEL_23:
    v26 = v37;
LABEL_17:
    if ( !v26 )
    {
LABEL_20:
      if ( !v36 )
        goto LABEL_13;
      v23 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
      goto LABEL_12;
    }
    v27 = *(void (**)(void))(*(_QWORD *)v26 + 16LL);
LABEL_19:
    v27();
    goto LABEL_20;
  }
  if ( a7 )
  {
    v28 = *(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)a2 + 40LL);
    Buf1 = GUID_NULL;
    ContainerFormatFromMimeType = v28(a2, &Buf1);
    if ( ContainerFormatFromMimeType < 0 )
      goto LABEL_23;
    Buf2 = GUID_NULL;
    ContainerFormatFromMimeType = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v36 + 32LL))(v36, &Buf2);
    if ( ContainerFormatFromMimeType < 0 )
      goto LABEL_23;
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
    {
      v39 = 0;
      if ( a3 )
      {
        (**a3)(a3, &GUID_feaa2a8d_b3f3_43e4_b25c_d1de990a1ae1, &v39);
        v29 = v39;
        if ( v39 )
        {
          v40 = 0;
          if ( v37 )
          {
            (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v37)(
              v37,
              &GUID_08fb9676_b444_41e8_8dbe_6a53a542bff1,
              &v40);
            if ( v40 )
            {
              ContainerFormatFromMimeType = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 56LL))(
                                              v40,
                                              v39);
              if ( ContainerFormatFromMimeType < 0 )
              {
                if ( v40 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
                if ( !v39 )
                  goto LABEL_38;
                v30 = *(void (**)(void))(*(_QWORD *)v39 + 16LL);
                goto LABEL_37;
              }
              if ( v40 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
            }
            v29 = v39;
          }
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
      }
    }
  }
  v31 = *a1;
  v38 = 0;
  v32 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v31 + 88))(a1, &v38);
  v33 = v38;
  ContainerFormatFromMimeType = v32;
  if ( v32 < 0 )
  {
LABEL_46:
    if ( !v33 )
      goto LABEL_38;
    v30 = *(void (**)(void))(*(_QWORD *)v33 + 16LL);
LABEL_37:
    v30();
LABEL_38:
    if ( !v37 )
      goto LABEL_20;
    v27 = *(void (**)(void))(*(_QWORD *)v37 + 16LL);
    goto LABEL_19;
  }
  ContainerFormatFromMimeType = (*(__int64 (__fastcall **)(__int64, void (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD, _QWORD, int))(*(_QWORD *)v38 + 64LL))(
                                  v38,
                                  a3,
                                  a4,
                                  a5,
                                  2);
  if ( ContainerFormatFromMimeType < 0
    || (v44 = GUID_WICPixelFormat24bppRGB,
        ContainerFormatFromMimeType = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v37 + 48LL))(v37, &v44),
        ContainerFormatFromMimeType < 0)
    || (ContainerFormatFromMimeType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v37 + 88LL))(
                                        v37,
                                        v38,
                                        0),
        ContainerFormatFromMimeType < 0)
    || (ContainerFormatFromMimeType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 96LL))(v37),
        ContainerFormatFromMimeType < 0)
    || (ContainerFormatFromMimeType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 88LL))(v36),
        ContainerFormatFromMimeType < 0)
    || (ContainerFormatFromMimeType = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a9 + 40LL))(
                                        a9,
                                        0,
                                        0,
                                        0),
        ContainerFormatFromMimeType < 0) )
  {
    v33 = v38;
    goto LABEL_46;
  }
  v34 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a9 + 64LL))(a9, 0);
  v33 = v38;
  ContainerFormatFromMimeType = v34;
  if ( v34 < 0 )
    goto LABEL_46;
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  return 0;
}

```

## disassembly

```asm
0x1800068f0  push    rbp
0x1800068f2  push    rbx
0x1800068f3  push    rsi
0x1800068f4  push    rdi
0x1800068f5  push    r12
0x1800068f7  push    r13
0x1800068f9  push    r14
0x1800068fb  push    r15
0x1800068fd  lea     rbp, [rsp-7]
0x180006902  sub     rsp, 0B8h
0x180006909  mov     rax, cs:__security_cookie
0x180006910  xor     rax, rsp
0x180006913  mov     [rbp+3Fh+var_50], rax
0x180006917  mov     rax, [rcx]
0x18000691a  mov     r12, rdx
0x18000691d  mov     r15, [rbp+3Fh+arg_28]
0x180006921  lea     rdx, [rsp+0F0h+var_C0]
0x180006926  mov     rdi, [rbp+3Fh+arg_40]
0x18000692d  mov     r13d, r9d
0x180006930  mov     rsi, r8
0x180006933  mov     [rsp+0F0h+var_C0], 0
0x18000693c  mov     rax, [rax+70h]
0x180006940  mov     r14, rcx
0x180006943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006948  mov     rcx, [rsp+0F0h+var_C0]
0x18000694d  mov     ebx, eax
0x18000694f  test    eax, eax
0x180006951  jns     short loc_18000696B
0x180006953  test    rcx, rcx
0x180006956  jz      short loc_180006964
0x180006958  mov     rdx, [rcx]
0x18000695b  mov     rax, [rdx+10h]
0x18000695f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006964  mov     eax, ebx
0x180006966  jmp     loc_180006D33
0x18000696b  mov     rax, [rcx]
0x18000696e  mov     rdx, rdi
0x180006971  mov     rax, [rax+70h]
0x180006975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000697a  mov     ebx, eax
0x18000697c  test    eax, eax
0x18000697e  jns     short loc_180006987
0x180006980  mov     rcx, [rsp+0F0h+var_C0]
0x180006985  jmp     short loc_180006953
0x180006987  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000698e  lea     r8, [rbp+3Fh+var_90]
0x180006992  mov     rdx, r15
0x180006995  movdqu  [rbp+3Fh+var_90], xmm0
0x18000699a  call    GetContainerFormatFromMimeType
0x18000699f  xor     r15d, r15d
0x1800069a2  mov     ebx, eax
0x1800069a4  test    eax, eax
0x1800069a6  js      short loc_180006980
0x1800069a8  mov     rax, [r14]
0x1800069ab  lea     r9, [rbp+3Fh+var_B8]
0x1800069af  xor     r8d, r8d
0x1800069b2  mov     [rbp+3Fh+var_B8], r15
0x1800069b6  lea     rdx, [rbp+3Fh+var_90]
0x1800069ba  mov     rcx, r14
0x1800069bd  mov     rax, [rax+40h]
0x1800069c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069c6  mov     rcx, [rbp+3Fh+var_B8]
0x1800069ca  mov     ebx, eax
0x1800069cc  test    eax, eax
0x1800069ce  jns     short loc_1800069FB
0x1800069d0  test    rcx, rcx
0x1800069d3  jz      short loc_1800069E1
0x1800069d5  mov     rdx, [rcx]
0x1800069d8  mov     rax, [rdx+10h]
0x1800069dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069e1  mov     rcx, [rsp+0F0h+var_C0]
0x1800069e6  test    rcx, rcx
0x1800069e9  jz      loc_180006964
0x1800069ef  mov     rax, [rcx]
0x1800069f2  mov     rax, [rax+10h]
0x1800069f6  jmp     loc_18000695F
0x1800069fb  mov     rax, [rcx]
0x1800069fe  mov     r8d, 2
0x180006a04  mov     rdx, [rsp+0F0h+var_C0]
0x180006a09  mov     rax, [rax+18h]
0x180006a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a12  mov     rcx, [rbp+3Fh+var_B8]
0x180006a16  mov     ebx, eax
0x180006a18  test    eax, eax
0x180006a1a  js      short loc_1800069D0
0x180006a1c  mov     [rbp+3Fh+var_B0], r15
0x180006a20  lea     rdx, [rbp+3Fh+var_B0]
0x180006a24  mov     rax, [rcx]
0x180006a27  xor     r8d, r8d
0x180006a2a  mov     rax, [rax+50h]
0x180006a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a33  mov     rcx, [rbp+3Fh+var_B0]
0x180006a37  mov     ebx, eax
0x180006a39  test    eax, eax
0x180006a3b  jns     short loc_180006A63
0x180006a3d  test    rcx, rcx
0x180006a40  jz      short loc_180006A4E
0x180006a42  mov     rdx, [rcx]
0x180006a45  mov     rax, [rdx+10h]
0x180006a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a4e  mov     rcx, [rbp+3Fh+var_B8]
0x180006a52  test    rcx, rcx
0x180006a55  jz      short loc_1800069E1
0x180006a57  mov     rax, [rcx]
0x180006a5a  mov     rax, [rax+10h]
0x180006a5e  jmp     loc_1800069DC
0x180006a63  mov     rax, [rcx]
0x180006a66  xor     edx, edx
0x180006a68  mov     rax, [rax+18h]
0x180006a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a71  mov     ebx, eax
0x180006a73  test    eax, eax
0x180006a75  jns     short loc_180006A7D
0x180006a77  mov     rcx, [rbp+3Fh+var_B0]
0x180006a7b  jmp     short loc_180006A3D
0x180006a7d  cmp     [rbp+3Fh+arg_30], r15d
0x180006a81  jz      loc_180006BD3
0x180006a87  mov     rax, [r12]
0x180006a8b  lea     rdx, [rbp+3Fh+Buf1]
0x180006a8f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180006a96  mov     rcx, r12
0x180006a99  mov     rax, [rax+28h]
0x180006a9d  movdqu  [rbp+3Fh+Buf1], xmm0
0x180006aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aa7  mov     ebx, eax
0x180006aa9  test    eax, eax
0x180006aab  js      short loc_180006A77
0x180006aad  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180006ab4  mov     rcx, [rbp+3Fh+var_B8]
0x180006ab8  lea     rdx, [rbp+3Fh+Buf2]
0x180006abc  movdqu  [rbp+3Fh+Buf2], xmm0
0x180006ac1  mov     rax, [rcx]
0x180006ac4  mov     rax, [rax+20h]
0x180006ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006acd  mov     ebx, eax
0x180006acf  test    eax, eax
0x180006ad1  js      short loc_180006A77
0x180006ad3  mov     r8d, 10h; Size
0x180006ad9  lea     rdx, [rbp+3Fh+Buf2]; Buf2
0x180006add  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x180006ae1  call    memcmp_0
0x180006ae6  test    eax, eax
0x180006ae8  jnz     loc_180006BD3
0x180006aee  mov     [rbp+3Fh+var_A0], r15
0x180006af2  test    rsi, rsi
0x180006af5  jz      loc_180006BD3
0x180006afb  mov     rax, [rsi]
0x180006afe  lea     r8, [rbp+3Fh+var_A0]
0x180006b02  lea     rdx, _GUID_feaa2a8d_b3f3_43e4_b25c_d1de990a1ae1
0x180006b09  mov     rcx, rsi
0x180006b0c  mov     rax, [rax]
0x180006b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b14  mov     rcx, [rbp+3Fh+var_A0]
0x180006b18  test    rcx, rcx
0x180006b1b  jz      loc_180006BD3
0x180006b21  mov     r9, [rbp+3Fh+var_B0]
0x180006b25  mov     [rbp+3Fh+var_98], r15
0x180006b29  test    r9, r9
0x180006b2c  jz      loc_180006BC2
0x180006b32  mov     rax, [r9]
0x180006b35  lea     r8, [rbp+3Fh+var_98]
0x180006b39  lea     rdx, _GUID_08fb9676_b444_41e8_8dbe_6a53a542bff1
0x180006b40  mov     rcx, r9
0x180006b43  mov     rax, [rax]
0x180006b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b4b  mov     rcx, [rbp+3Fh+var_98]
0x180006b4f  test    rcx, rcx
0x180006b52  jz      short loc_180006BBE
0x180006b54  mov     rax, [rcx]
0x180006b57  mov     rdx, [rbp+3Fh+var_A0]
0x180006b5b  mov     rax, [rax+38h]
0x180006b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b64  mov     rcx, [rbp+3Fh+var_98]
0x180006b68  mov     ebx, eax
0x180006b6a  test    eax, eax
0x180006b6c  jns     short loc_180006BAD
0x180006b6e  test    rcx, rcx
0x180006b71  jz      short loc_180006B7F
0x180006b73  mov     rdx, [rcx]
0x180006b76  mov     rax, [rdx+10h]
0x180006b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b7f  mov     rcx, [rbp+3Fh+var_A0]
0x180006b83  test    rcx, rcx
0x180006b86  jz      short loc_180006B94
0x180006b88  mov     rax, [rcx]
0x180006b8b  mov     rax, [rax+10h]
0x180006b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b94  mov     rcx, [rbp+3Fh+var_B0]
0x180006b98  test    rcx, rcx
0x180006b9b  jz      loc_180006A4E
0x180006ba1  mov     rax, [rcx]
0x180006ba4  mov     rax, [rax+10h]
0x180006ba8  jmp     loc_180006A49
0x180006bad  test    rcx, rcx
0x180006bb0  jz      short loc_180006BBE
0x180006bb2  mov     rax, [rcx]
0x180006bb5  mov     rax, [rax+10h]
0x180006bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bbe  mov     rcx, [rbp+3Fh+var_A0]
0x180006bc2  test    rcx, rcx
0x180006bc5  jz      short loc_180006BD3
0x180006bc7  mov     rax, [rcx]
0x180006bca  mov     rax, [rax+10h]
0x180006bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bd3  mov     rax, [r14]
0x180006bd6  lea     rdx, [rbp+3Fh+var_A8]
0x180006bda  mov     rcx, r14
0x180006bdd  mov     [rbp+3Fh+var_A8], r15
0x180006be1  mov     rax, [rax+58h]
0x180006be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bea  mov     rcx, [rbp+3Fh+var_A8]
0x180006bee  mov     ebx, eax
0x180006bf0  test    eax, eax
0x180006bf2  jns     short loc_180006C02
0x180006bf4  test    rcx, rcx
0x180006bf7  jz      short loc_180006B94
0x180006bf9  mov     rdx, [rcx]
0x180006bfc  mov     rax, [rdx+10h]
0x180006c00  jmp     short loc_180006B8F
0x180006c02  mov     rax, [rcx]
0x180006c05  mov     r8d, r13d
0x180006c08  mov     r9d, [rbp+3Fh+arg_20]
0x180006c0c  mov     rdx, rsi
0x180006c0f  mov     [rsp+0F0h+var_D0], 2
0x180006c17  mov     rax, [rax+40h]
0x180006c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c20  mov     ebx, eax
0x180006c22  test    eax, eax
0x180006c24  jns     short loc_180006C2C
0x180006c26  mov     rcx, [rbp+3Fh+var_A8]
0x180006c2a  jmp     short loc_180006BF4
0x180006c2c  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat24bppRGB.Data1
0x180006c33  mov     rcx, [rbp+3Fh+var_B0]
0x180006c37  lea     rdx, [rbp+3Fh+var_60]
0x180006c3b  movdqu  [rbp+3Fh+var_60], xmm0
0x180006c40  mov     rax, [rcx]
0x180006c43  mov     rax, [rax+30h]
0x180006c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c4c  mov     ebx, eax
0x180006c4e  test    eax, eax
0x180006c50  js      short loc_180006C26
0x180006c52  mov     rcx, [rbp+3Fh+var_B0]
0x180006c56  xor     r8d, r8d
0x180006c59  mov     rdx, [rbp+3Fh+var_A8]
0x180006c5d  mov     rax, [rcx]
0x180006c60  mov     rax, [rax+58h]
0x180006c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c69  mov     ebx, eax
0x180006c6b  test    eax, eax
0x180006c6d  js      short loc_180006C26
0x180006c6f  mov     rcx, [rbp+3Fh+var_B0]
0x180006c73  mov     rax, [rcx]
0x180006c76  mov     rax, [rax+60h]
0x180006c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c7f  mov     ebx, eax
0x180006c81  test    eax, eax
0x180006c83  js      short loc_180006C26
0x180006c85  mov     rcx, [rbp+3Fh+var_B8]
0x180006c89  mov     rax, [rcx]
0x180006c8c  mov     rax, [rax+58h]
0x180006c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c95  mov     ebx, eax
0x180006c97  test    eax, eax
0x180006c99  js      short loc_180006C26
0x180006c9b  mov     rax, [rdi]
0x180006c9e  xor     r9d, r9d
0x180006ca1  mov     rdx, cs:qword_18000D340
0x180006ca8  xor     r8d, r8d
0x180006cab  mov     rcx, rdi
0x180006cae  mov     rax, [rax+28h]
0x180006cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cb7  mov     ebx, eax
0x180006cb9  test    eax, eax
0x180006cbb  js      loc_180006C26
0x180006cc1  mov     rax, [rdi]
0x180006cc4  xor     edx, edx
0x180006cc6  mov     rcx, rdi
0x180006cc9  mov     rax, [rax+40h]
0x180006ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cd2  mov     rcx, [rbp+3Fh+var_A8]
0x180006cd6  mov     ebx, eax
0x180006cd8  test    eax, eax
0x180006cda  js      loc_180006BF4
0x180006ce0  test    rcx, rcx
0x180006ce3  jz      short loc_180006CF1
0x180006ce5  mov     rax, [rcx]
0x180006ce8  mov     rax, [rax+10h]
0x180006cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cf1  mov     rcx, [rbp+3Fh+var_B0]
0x180006cf5  test    rcx, rcx
0x180006cf8  jz      short loc_180006D06
0x180006cfa  mov     rax, [rcx]
0x180006cfd  mov     rax, [rax+10h]
0x180006d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d06  mov     rcx, [rbp+3Fh+var_B8]
0x180006d0a  test    rcx, rcx
0x180006d0d  jz      short loc_180006D1B
0x180006d0f  mov     rax, [rcx]
0x180006d12  mov     rax, [rax+10h]
0x180006d16  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
