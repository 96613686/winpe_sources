# ResizeImageBySizeInMemory(IStream *,ulong,ushort const *,IStream * *,ulong *)

- ea: `0x180006d60`
- end: `0x1800071b9`
- name: `?ResizeImageBySizeInMemory@@YAJPEAUIStream@@KPEBGPEAPEAU1@PEAK@Z`
- size: `1113`
- prototype: `__int64 __fastcall(struct IStream *, unsigned int, const unsigned __int16 *, struct IStream **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800071c0`

## callees

- `0x1800068f0`
- `0x180006d60`
- `0x18000a15a`
- `0x18000a166`
- `0x18000a190`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180007045`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180007045`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006dbc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006dbc`

## pseudocode

```c
__int64 __fastcall ResizeImageBySizeInMemory(
        struct IStream *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct IStream **a4,
        unsigned int *a5)
{
  int v5; // r15d
  HRESULT v9; // eax
  LPVOID v10; // rcx
  int v11; // ebx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rdi
  HRESULT v17; // esi
  float v19; // xmm0_4
  unsigned int v20; // eax
  unsigned int v21; // eax
  void (*v22)(void); // rax
  int v23; // [rsp+38h] [rbp-99h]
  LPSTREAM ppstm; // [rsp+50h] [rbp-81h] BYREF
  int v25; // [rsp+58h] [rbp-79h] BYREF
  int v26; // [rsp+5Ch] [rbp-75h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-71h] BYREF
  __int64 v28; // [rsp+68h] [rbp-69h] BYREF
  __int64 v29; // [rsp+70h] [rbp-61h] BYREF
  const unsigned __int16 *v30; // [rsp+78h] [rbp-59h]
  _BYTE v31[16]; // [rsp+80h] [rbp-51h] BYREF
  unsigned int v32; // [rsp+90h] [rbp-41h]

  v5 = 0;
  v30 = a3;
  ppv = 0;
  v9 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
  v10 = ppv;
  v11 = v9;
  if ( v9 < 0 )
  {
LABEL_58:
    if ( v10 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)v11;
  }
  v12 = *(_QWORD *)ppv;
  v28 = 0;
  v13 = (*(__int64 (__fastcall **)(LPVOID, struct IStream *, _QWORD, _QWORD, __int64 *))(v12 + 32))(ppv, a1, 0, 0, &v28);
  v14 = v28;
  v11 = v13;
  if ( v13 < 0 )
    goto LABEL_3;
  LODWORD(ppstm) = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, LPSTREAM *))(*(_QWORD *)v28 + 96LL))(v28, &ppstm);
  if ( v11 < 0 )
  {
LABEL_6:
    v14 = v28;
LABEL_3:
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_57:
    v10 = ppv;
    goto LABEL_58;
  }
  if ( !(_DWORD)ppstm )
  {
    if ( v28 )
      (*(void (**)(void))(*(_QWORD *)v28 + 16LL))();
    v11 = -2147418113;
    goto LABEL_57;
  }
  v29 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v28 + 104LL))(v28, 0, &v29);
  if ( v11 < 0 )
  {
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    goto LABEL_6;
  }
  v15 = v29;
  v16 = v28;
  v25 = 0;
  v26 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v29 + 24LL))(v29, &v25, &v26);
  if ( v17 < 0 )
  {
    if ( !v16 )
    {
LABEL_14:
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return (unsigned int)v17;
    }
LABEL_13:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    goto LABEL_14;
  }
  v19 = sqrtf_0((float)(int)(10 * a2) / (float)(3 * v25 * v26));
  v25 = (int)(float)((float)v25 * v19);
  v20 = (int)(float)((float)v26 * v19);
  v26 = v20;
  if ( (unsigned int)v25 >= 0x10 || v20 >= 0x10 )
  {
    while ( 1 )
    {
      ppstm = 0;
      v17 = CreateStreamOnHGlobal(0, 1, &ppstm);
      if ( v17 < 0
        || (LOBYTE(v5) = a2 > 0xC800,
            v17 = ResizeImageByDimensionWithMetadata(
                    (_DWORD)ppv,
                    v16,
                    v15,
                    v25,
                    v26,
                    (__int64)v30,
                    v5,
                    v23,
                    (__int64)ppstm),
            v17 < 0)
        || (memset_0(v31, 0, 0x50u),
            v17 = (*(__int64 (__fastcall **)(LPSTREAM, _BYTE *, __int64))(*(_QWORD *)ppstm + 96LL))(ppstm, v31, 1),
            v17 < 0) )
      {
        if ( !ppstm )
          goto LABEL_33;
        v22 = *(void (**)(void))(*(_QWORD *)ppstm + 16LL);
        goto LABEL_32;
      }
      if ( v32 <= a2 )
        break;
      v25 = (int)((double)v25 * 0.8);
      v21 = (int)((double)v26 * 0.8);
      v26 = v21;
      if ( (unsigned int)v25 < 0x10 && v21 < 0x10 )
      {
        if ( ppstm )
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        goto LABEL_37;
      }
      if ( ppstm )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    }
    v17 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
    if ( v17 >= 0 )
    {
      *a4 = ppstm;
      *a5 = v32;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return 0;
    }
    if ( ppstm )
    {
      v22 = *(void (**)(void))(*(_QWORD *)ppstm + 16LL);
LABEL_32:
      v22();
    }
LABEL_33:
    if ( !v16 )
      goto LABEL_14;
    goto LABEL_13;
  }
LABEL_37:
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180006d60  push    rbp
0x180006d62  push    rbx
0x180006d63  push    rsi
0x180006d64  push    rdi
0x180006d65  push    r12
0x180006d67  push    r13
0x180006d69  push    r14
0x180006d6b  push    r15
0x180006d6d  lea     rbp, [rsp-17h]
0x180006d72  sub     rsp, 0E8h
0x180006d79  mov     rax, cs:__security_cookie
0x180006d80  xor     rax, rsp
0x180006d83  mov     [rbp+4Fh+var_50], rax
0x180006d87  mov     r13, [rbp+4Fh+arg_20]
0x180006d8b  lea     rax, [rbp+4Fh+var_C0]
0x180006d8f  xor     r15d, r15d
0x180006d92  mov     [rbp+4Fh+var_A8], r8
0x180006d96  mov     r12, r9
0x180006d99  mov     [rbp+4Fh+var_C0], r15
0x180006d9d  mov     r14d, edx
0x180006da0  mov     [rsp+120h+ppv], rax; ppv
0x180006da5  mov     rdi, rcx
0x180006da8  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180006daf  lea     r8d, [r15+1]; dwClsContext
0x180006db3  xor     edx, edx; pUnkOuter
0x180006db5  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180006dbc  call    cs:__imp_CoCreateInstance
0x180006dc2  mov     rcx, [rbp+4Fh+var_C0]
0x180006dc6  mov     ebx, eax
0x180006dc8  test    eax, eax
0x180006dca  js      loc_180007186
0x180006dd0  mov     rax, [rcx]
0x180006dd3  lea     rdx, [rbp+4Fh+var_B8]
0x180006dd7  mov     [rsp+120h+ppv], rdx
0x180006ddc  xor     r9d, r9d
0x180006ddf  xor     r8d, r8d
0x180006de2  mov     [rbp+4Fh+var_B8], r15
0x180006de6  mov     rdx, rdi
0x180006de9  mov     rax, [rax+20h]
0x180006ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006df2  mov     rcx, [rbp+4Fh+var_B8]
0x180006df6  mov     ebx, eax
0x180006df8  test    eax, eax
0x180006dfa  jns     short loc_180006E16
0x180006dfc  test    rcx, rcx
0x180006dff  jz      loc_180007182
0x180006e05  mov     rax, [rcx]
0x180006e08  mov     rax, [rax+10h]
0x180006e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e11  jmp     loc_180007182
0x180006e16  mov     dword ptr [rsp+120h+ppstm], r15d
0x180006e1b  lea     rdx, [rsp+120h+ppstm]
0x180006e20  mov     rax, [rcx]
0x180006e23  mov     rax, [rax+60h]
0x180006e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e2c  mov     ebx, eax
0x180006e2e  test    eax, eax
0x180006e30  jns     short loc_180006E38
0x180006e32  mov     rcx, [rbp+4Fh+var_B8]
0x180006e36  jmp     short loc_180006DFC
0x180006e38  mov     rcx, [rbp+4Fh+var_B8]
0x180006e3c  cmp     dword ptr [rsp+120h+ppstm], r15d
0x180006e41  jbe     loc_18000716C
0x180006e47  mov     [rbp+4Fh+var_B0], r15
0x180006e4b  lea     r8, [rbp+4Fh+var_B0]
0x180006e4f  mov     rax, [rcx]
0x180006e52  xor     edx, edx
0x180006e54  mov     rax, [rax+68h]
0x180006e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e5d  mov     ebx, eax
0x180006e5f  test    eax, eax
0x180006e61  jns     short loc_180006E7A
0x180006e63  mov     rcx, [rbp+4Fh+var_B0]
0x180006e67  test    rcx, rcx
0x180006e6a  jz      short loc_180006E32
0x180006e6c  mov     rax, [rcx]
0x180006e6f  mov     rax, [rax+10h]
0x180006e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e78  jmp     short loc_180006E32
0x180006e7a  mov     rbx, [rbp+4Fh+var_B0]
0x180006e7e  lea     r8, [rbp+4Fh+var_C4]
0x180006e82  mov     rdi, [rbp+4Fh+var_B8]
0x180006e86  lea     rdx, [rbp+4Fh+var_C8]
0x180006e8a  mov     [rbp+4Fh+var_C8], r15d
0x180006e8e  mov     rcx, rbx
0x180006e91  mov     [rbp+4Fh+var_C4], r15d
0x180006e95  mov     rax, [rbx]
0x180006e98  mov     rax, [rax+18h]
0x180006e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea1  mov     esi, eax
0x180006ea3  test    eax, eax
0x180006ea5  jns     short loc_180006EEB
0x180006ea7  test    rdi, rdi
0x180006eaa  jz      short loc_180006EBB
0x180006eac  mov     rcx, [rdi]
0x180006eaf  mov     rax, [rcx+10h]
0x180006eb3  mov     rcx, rdi
0x180006eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ebb  test    rbx, rbx
0x180006ebe  jz      short loc_180006ECF
0x180006ec0  mov     rax, [rbx]
0x180006ec3  mov     rcx, rbx
0x180006ec6  mov     rax, [rax+10h]
0x180006eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ecf  mov     rcx, [rbp+4Fh+var_C0]
0x180006ed3  test    rcx, rcx
0x180006ed6  jz      short loc_180006EE4
0x180006ed8  mov     rax, [rcx]
0x180006edb  mov     rax, [rax+10h]
0x180006edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ee4  mov     eax, esi
0x180006ee6  jmp     loc_180007199
0x180006eeb  lea     eax, [r14+r14*4]
0x180006eef  xorps   xmm0, xmm0
0x180006ef2  add     eax, eax
0x180006ef4  xorps   xmm1, xmm1
0x180006ef7  cvtsi2ss xmm0, rax
0x180006efc  mov     eax, [rbp+4Fh+var_C4]
0x180006eff  imul    eax, [rbp+4Fh+var_C8]
0x180006f03  lea     ecx, [rax+rax*2]
0x180006f06  cvtsi2ss xmm1, rcx
0x180006f0b  divss   xmm0, xmm1; X
0x180006f0f  call    sqrtf_0
0x180006f14  mov     eax, [rbp+4Fh+var_C8]
0x180006f17  xorps   xmm1, xmm1
0x180006f1a  cvtsi2ss xmm1, rax
0x180006f1f  mov     eax, [rbp+4Fh+var_C4]
0x180006f22  mulss   xmm1, xmm0
0x180006f26  cvttss2si rcx, xmm1
0x180006f2b  xorps   xmm1, xmm1
0x180006f2e  mov     [rbp+4Fh+var_C8], ecx
0x180006f31  cvtsi2ss xmm1, rax
0x180006f36  mulss   xmm1, xmm0
0x180006f3a  cvttss2si rax, xmm1
0x180006f3f  mov     [rbp+4Fh+var_C4], eax
0x180006f42  cmp     ecx, 10h
0x180006f45  jnb     short loc_180006F50
0x180006f47  cmp     eax, 10h
0x180006f4a  jb      loc_180007096
0x180006f50  cmp     r14d, 0C800h
0x180006f57  setnbe  r15b
0x180006f5b  jmp     loc_180007030
0x180006f60  mov     rax, [rsp+120h+ppstm]
0x180006f65  mov     r8, rbx
0x180006f68  mov     edx, [rbp+4Fh+var_C4]
0x180006f6b  mov     r9d, [rbp+4Fh+var_C8]
0x180006f6f  mov     rcx, [rbp+4Fh+var_C0]
0x180006f73  mov     [rsp+120h+var_E0], rax
0x180006f78  mov     rax, [rbp+4Fh+var_A8]
0x180006f7c  mov     [rsp+120h+var_F0], r15d
0x180006f81  mov     [rsp+120h+var_F8], rax
0x180006f86  mov     dword ptr [rsp+120h+ppv], edx
0x180006f8a  mov     rdx, rdi
0x180006f8d  call    ResizeImageByDimensionWithMetadata
0x180006f92  mov     esi, eax
0x180006f94  test    eax, eax
0x180006f96  js      loc_180007055
0x180006f9c  xor     edx, edx; Val
0x180006f9e  lea     rcx, [rbp+4Fh+var_A0]; void *
0x180006fa2  lea     r8d, [rdx+50h]; Size
0x180006fa6  call    memset_0
0x180006fab  mov     rcx, [rsp+120h+ppstm]
0x180006fb0  lea     rdx, [rbp+4Fh+var_A0]
0x180006fb4  mov     r8d, 1
0x180006fba  mov     rax, [rcx]
0x180006fbd  mov     rax, [rax+60h]
0x180006fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc6  mov     esi, eax
0x180006fc8  test    eax, eax
0x180006fca  js      loc_180007055
0x180006fd0  cmp     [rbp+4Fh+var_90], r14d
0x180006fd4  jbe     loc_1800070DD
0x180006fda  mov     eax, [rbp+4Fh+var_C8]
0x180006fdd  xorps   xmm0, xmm0
0x180006fe0  cvtsi2sd xmm0, rax
0x180006fe5  mov     eax, [rbp+4Fh+var_C4]
0x180006fe8  mulsd   xmm0, cs:__real@3fe999999999999a
0x180006ff0  cvttsd2si rcx, xmm0
0x180006ff5  xorps   xmm0, xmm0
0x180006ff8  mov     [rbp+4Fh+var_C8], ecx
0x180006ffb  cvtsi2sd xmm0, rax
0x180007000  mulsd   xmm0, cs:__real@3fe999999999999a
0x180007008  cvttsd2si rax, xmm0
0x18000700d  mov     [rbp+4Fh+var_C4], eax
0x180007010  cmp     ecx, 10h
0x180007013  jnb     short loc_18000701A
0x180007015  cmp     eax, 10h
0x180007018  jb      short loc_180007080
0x18000701a  mov     rcx, [rsp+120h+ppstm]
0x18000701f  test    rcx, rcx
0x180007022  jz      short loc_180007030
0x180007024  mov     rax, [rcx]
0x180007027  mov     rax, [rax+10h]
0x18000702b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007030  lea     r8, [rsp+120h+ppstm]; ppstm
0x180007035  mov     [rsp+120h+ppstm], 0
0x18000703e  mov     edx, 1; fDeleteOnRelease
0x180007043  xor     ecx, ecx; hGlobal
0x180007045  call    cs:__imp_CreateStreamOnHGlobal
0x18000704b  mov     esi, eax
0x18000704d  test    eax, eax
0x18000704f  jns     loc_180006F60
0x180007055  mov     rcx, [rsp+120h+ppstm]
0x18000705a  test    rcx, rcx
0x18000705d  jz      short loc_18000706B
0x18000705f  mov     rax, [rcx]
0x180007062  mov     rax, [rax+10h]
0x180007066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000706b  test    rdi, rdi
0x18000706e  jz      loc_180006EBB
0x180007074  mov     rax, [rdi]
0x180007077  mov     rax, [rax+10h]
0x18000707b  jmp     loc_180006EB3
0x180007080  mov     rcx, [rsp+120h+ppstm]
0x180007085  test    rcx, rcx
0x180007088  jz      short loc_180007096
0x18000708a  mov     rax, [rcx]
0x18000708d  mov     rax, [rax+10h]
0x180007091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007096  test    rdi, rdi
0x180007099  jz      short loc_1800070AA
0x18000709b  mov     rax, [rdi]
0x18000709e  mov     rcx, rdi
0x1800070a1  mov     rax, [rax+10h]
0x1800070a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070aa  test    rbx, rbx
0x1800070ad  jz      short loc_1800070BE
0x1800070af  mov     rax, [rbx]
0x1800070b2  mov     rcx, rbx
0x1800070b5  mov     rax, [rax+10h]
0x1800070b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070be  mov     rcx, [rbp+4Fh+var_C0]
0x1800070c2  test    rcx, rcx
0x1800070c5  jz      short loc_1800070D3
0x1800070c7  mov     rax, [rcx]
0x1800070ca  mov     rax, [rax+10h]
0x1800070ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070d3  mov     eax, 80004005h
0x1800070d8  jmp     loc_180007199
0x1800070dd  mov     rcx, [rsp+120h+ppstm]
0x1800070e2  xor     r9d, r9d
0x1800070e5  mov     rdx, cs:qword_18000D340
0x1800070ec  xor     r8d, r8d
0x1800070ef  mov     rax, [rcx]
0x1800070f2  mov     rax, [rax+28h]
0x1800070f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070fb  mov     esi, eax
0x1800070fd  test    eax, eax
0x1800070ff  jns     short loc_18000711B
0x180007101  mov     rcx, [rsp+120h+ppstm]
0x180007106  test    rcx, rcx
0x180007109  jz      loc_18000706B
0x18000710f  mov     rdx, [rcx]
0x180007112  mov     rax, [rdx+10h]
0x180007116  jmp     loc_180007066
0x18000711b  mov     rax, [rsp+120h+ppstm]
0x180007120  mov     [r12], rax
0x180007124  mov     eax, [rbp+4Fh+var_90]
0x180007127  mov     [r13+0], eax
0x18000712b  test    rdi, rdi
0x18000712e  jz      short loc_18000713F
0x180007130  mov     rax, [rdi]
0x180007133  mov     rcx, rdi
0x180007136  mov     rax, [rax+10h]
0x18000713a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000713f  test    rbx, rbx
0x180007142  jz      short loc_180007153
0x180007144  mov     rax, [rbx]
0x180007147  mov     rcx, rbx
0x18000714a  mov     rax, [rax+10h]
0x18000714e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007153  mov     rcx, [rbp+4Fh+var_C0]
0x180007157  test    rcx, rcx
0x18000715a  jz      short loc_180007168
0x18000715c  mov     rax, [rcx]
0x18000715f  mov     rax, [rax+10h]
0x180007163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007168  xor     eax, eax
0x18000716a  jmp     short loc_180007199
0x18000716c  test    rcx, rcx
0x18000716f  jz      short loc_18000717D
0x180007171  mov     rax, [rcx]
0x180007174  mov     rax, [rax+10h]
0x180007178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000717d  mov     ebx, 8000FFFFh
0x180007182  mov     rcx, [rbp+4Fh+var_C0]
0x180007186  test    rcx, rcx
0x180007189  jz      short loc_180007197
0x18000718b  mov     rdx, [rcx]
0x18000718e  mov     rax, [rdx+10h]
0x180007192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007197  mov     eax, ebx
0x180007199  mov     rcx, [rbp+4Fh+var_50]
0x18000719d  xor     rcx, rsp; StackCookie
0x1800071a0  call    __security_check_cookie
0x1800071a5  add     rsp, 0E8h
0x1800071ac  pop     r15
0x1800071ae  pop     r14
0x1800071b0  pop     r13
0x1800071b2  pop     r12
  ... truncated ...
```
