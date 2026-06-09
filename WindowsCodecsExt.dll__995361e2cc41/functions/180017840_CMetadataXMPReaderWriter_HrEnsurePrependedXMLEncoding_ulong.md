# CMetadataXMPReaderWriter::HrEnsurePrependedXMLEncoding(ulong)

- ea: `0x180017840`
- end: `0x180017ae1`
- name: `?HrEnsurePrependedXMLEncoding@CMetadataXMPReaderWriter@@MEAAJK@Z`
- size: `673`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180004500`
- `0x1800171c4`
- `0x180017840`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180017917`
- `OLEAUT32!__imp_SysAllocString` at `0x180017940`
- `OLEAUT32!__imp_SysAllocString` at `0x180017917`
- `OLEAUT32!__imp_SysAllocString` at `0x180017940`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::HrEnsurePrependedXMLEncoding(CMetadataXMPReaderWriter *this, char a2)
{
  _QWORD *v2; // r14
  __int64 v4; // rdx
  int v6; // ebx
  unsigned __int16 *v7; // rbx
  const OLECHAR *v8; // rcx
  unsigned __int16 *v9; // rax
  int v10; // ecx
  int v11; // eax
  int v12; // eax
  int v13; // ecx
  __int64 v14; // rcx
  unsigned __int16 *v16; // [rsp+30h] [rbp-30h] BYREF
  __int64 v17; // [rsp+38h] [rbp-28h] BYREF
  __int128 v18; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19; // [rsp+50h] [rbp-10h]
  unsigned __int16 *v20; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v21; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v22; // [rsp+B8h] [rbp+58h] BYREF

  v2 = (_QWORD *)((char *)this + 248);
  v22 = 0;
  v4 = *((_QWORD *)this + 31);
  v17 = 0;
  v21 = 0;
  v6 = 0;
  v18 = 0;
  if ( !v4 )
    goto LABEL_12;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 23) + 160LL))(
         *((_QWORD *)this + 23),
         v4,
         &v21);
  if ( v6 >= 0 )
  {
    if ( v6 )
    {
      v6 = -2147467259;
      if ( !g_doStackCaptures )
        goto LABEL_43;
      goto LABEL_7;
    }
    if ( *v2 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
      *v2 = 0;
    }
    if ( v21 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v21 = 0;
    }
LABEL_12:
    if ( (a2 & 1) != 0 )
      goto LABEL_43;
    v20 = SysAllocString(L"xml");
    v7 = v20;
    if ( !v20 )
    {
      v6 = -2147024882;
      goto LABEL_39;
    }
    if ( (a2 & 2) != 0 )
    {
      v8 = L"version='1.0' encoding='UTF-16'";
    }
    else
    {
      if ( (a2 & 4) == 0 )
        goto LABEL_38;
      v8 = L"version='1.0' encoding='UTF-32'";
    }
    v9 = SysAllocString(v8);
    v16 = v9;
    if ( !v9 )
    {
      v6 = -2147024882;
LABEL_19:
      if ( !g_doStackCaptures )
      {
LABEL_22:
        FreeBSTR(&v16);
        goto LABEL_42;
      }
      v10 = v6;
LABEL_21:
      DoStackCapture(v10);
      goto LABEL_22;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, unsigned __int16 *, __int64 *))(**((_QWORD **)this + 23)
                                                                                               + 416LL))(
            *((_QWORD *)this + 23),
            v7,
            v9,
            &v22);
    v6 = v11;
    if ( v11 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_22;
      v10 = v11;
      goto LABEL_21;
    }
    if ( v11 )
    {
      v6 = -2147467259;
      goto LABEL_19;
    }
    FreeBSTR(&v16);
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 23) + 104LL))(
            *((_QWORD *)this + 23),
            &v17);
    v6 = v12;
    if ( v12 < 0 )
    {
LABEL_31:
      if ( g_doStackCaptures )
      {
        v13 = v12;
LABEL_41:
        DoStackCapture(v13);
      }
LABEL_42:
      FreeBSTR(&v20);
      goto LABEL_43;
    }
    if ( !v12 )
    {
      v14 = *((_QWORD *)this + 23);
      v19 = 0;
      LOWORD(v18) = 13;
      *((_QWORD *)&v18 + 1) = v17;
      v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, __int64 *))(*(_QWORD *)v14 + 144LL))(
              v14,
              v22,
              &v18,
              &v21);
      v6 = v12;
      if ( v12 < 0 )
        goto LABEL_31;
      if ( !v12 )
      {
        v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v21)(v21, &IID_IXMLDOMProcessingInstruction, v2);
        v6 = v12;
        if ( v12 >= 0 )
          goto LABEL_42;
        goto LABEL_31;
      }
    }
LABEL_38:
    v6 = -2147467259;
LABEL_39:
    if ( g_doStackCaptures )
    {
      v13 = v6;
      goto LABEL_41;
    }
    goto LABEL_42;
  }
  if ( g_doStackCaptures )
LABEL_7:
    DoStackCapture(v6);
LABEL_43:
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180017840  push    rbp
0x180017842  push    rbx
0x180017843  push    rsi
0x180017844  push    rdi
0x180017845  push    r12
0x180017847  push    r14
0x180017849  push    r15
0x18001784b  mov     rbp, rsp
0x18001784e  sub     rsp, 60h
0x180017852  xor     r15d, r15d
0x180017855  lea     r14, [rcx+0F8h]
0x18001785c  mov     edi, edx
0x18001785e  mov     [rbp+arg_18], r15
0x180017862  mov     rdx, [r14]
0x180017865  xor     r12d, r12d
0x180017868  mov     [rbp+var_28], r15
0x18001786c  xorps   xmm0, xmm0
0x18001786f  mov     [rbp+arg_10], r15
0x180017873  mov     rsi, rcx
0x180017876  mov     ebx, r15d
0x180017879  movups  [rbp+var_20], xmm0
0x18001787d  test    rdx, rdx
0x180017880  jz      loc_180017906
0x180017886  mov     rcx, [rcx+0B8h]
0x18001788d  lea     r8, [rbp+arg_10]
0x180017891  mov     rax, [rcx]
0x180017894  mov     rax, [rax+0A0h]
0x18001789b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178a0  mov     ebx, eax
0x1800178a2  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800178a8  test    ebx, ebx
0x1800178aa  jns     short loc_1800178B8
0x1800178ac  test    eax, eax
0x1800178ae  jnz     short loc_1800178C7
0x1800178b0  test    ebx, ebx
0x1800178b2  js      loc_180017A86
0x1800178b8  jz      short loc_1800178D3
0x1800178ba  mov     ebx, 80004005h
0x1800178bf  test    eax, eax
0x1800178c1  jz      loc_180017A86
0x1800178c7  mov     ecx, ebx; int
0x1800178c9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800178ce  jmp     loc_180017A86
0x1800178d3  mov     rcx, [r14]
0x1800178d6  test    rcx, rcx
0x1800178d9  jz      short loc_1800178EA
0x1800178db  mov     rax, [rcx]
0x1800178de  mov     rax, [rax+10h]
0x1800178e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178e7  mov     [r14], r15
0x1800178ea  mov     rdx, [rbp+arg_10]
0x1800178ee  test    rdx, rdx
0x1800178f1  jz      short loc_180017906
0x1800178f3  mov     rax, [rdx]
0x1800178f6  mov     rcx, rdx
0x1800178f9  mov     rax, [rax+10h]
0x1800178fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017902  mov     [rbp+arg_10], r15
0x180017906  test    dil, 1
0x18001790a  jnz     loc_180017A86
0x180017910  lea     rcx, aXml; "xml"
0x180017917  call    cs:__imp_SysAllocString
0x18001791d  mov     [rbp+arg_0], rax
0x180017921  mov     rbx, rax
0x180017924  test    rax, rax
0x180017927  jnz     short loc_180017933
0x180017929  mov     ebx, 8007000Eh
0x18001792e  jmp     loc_180017A6D
0x180017933  test    dil, 2
0x180017937  jz      short loc_1800179B1
0x180017939  lea     rcx, aVersion10Encod_0; "version='1.0' encoding='UTF-16'"
0x180017940  call    cs:__imp_SysAllocString
0x180017946  mov     [rbp+var_30], rax
0x18001794a  test    rax, rax
0x18001794d  jnz     short loc_180017972
0x18001794f  mov     ebx, 8007000Eh
0x180017954  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18001795b  jz      short loc_180017964
0x18001795d  mov     ecx, ebx; int
0x18001795f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180017964  lea     rcx, [rbp+var_30]; unsigned __int16 **
0x180017968  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x18001796d  jmp     loc_180017A7D
0x180017972  mov     rcx, [rsi+0B8h]
0x180017979  lea     r9, [rbp+arg_18]
0x18001797d  mov     r8, rax
0x180017980  mov     rdx, [rcx]
0x180017983  mov     r10, [rdx+1A0h]
0x18001798a  mov     rdx, rbx
0x18001798d  mov     rax, r10
0x180017990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017995  mov     ebx, eax
0x180017997  test    eax, eax
0x180017999  jns     short loc_1800179A8
0x18001799b  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800179a2  jz      short loc_180017964
0x1800179a4  mov     ecx, eax
0x1800179a6  jmp     short loc_18001795F
0x1800179a8  jz      short loc_1800179C7
0x1800179aa  mov     ebx, 80004005h
0x1800179af  jmp     short loc_180017954
0x1800179b1  test    dil, 4
0x1800179b5  jz      loc_180017A68
0x1800179bb  lea     rcx, aVersion10Encod; "version='1.0' encoding='UTF-32'"
0x1800179c2  jmp     loc_180017940
0x1800179c7  lea     rcx, [rbp+var_30]; unsigned __int16 **
0x1800179cb  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x1800179d0  mov     rcx, [rsi+0B8h]
0x1800179d7  lea     rdx, [rbp+var_28]
0x1800179db  mov     rax, [rcx]
0x1800179de  mov     rax, [rax+68h]
0x1800179e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179e7  mov     ebx, eax
0x1800179e9  test    eax, eax
0x1800179eb  jns     short loc_1800179FE
0x1800179ed  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800179f4  jz      loc_180017A7D
0x1800179fa  mov     ecx, eax
0x1800179fc  jmp     short loc_180017A78
0x1800179fe  jnz     short loc_180017A68
0x180017a00  mov     rcx, [rsi+0B8h]
0x180017a07  lea     r9, [rbp+arg_10]
0x180017a0b  mov     rdx, [rbp+arg_18]
0x180017a0f  lea     r8, [rbp+var_20]
0x180017a13  mov     eax, 0Dh
0x180017a18  mov     [rbp+var_10], r12
0x180017a1c  mov     word ptr [rbp+var_20], ax
0x180017a20  mov     rax, [rbp+var_28]
0x180017a24  mov     qword ptr [rbp+var_20+8], rax
0x180017a28  mov     rax, [rcx]
0x180017a2b  movups  xmm0, [rbp+var_20]
0x180017a2f  mov     rax, [rax+90h]
0x180017a36  movaps  [rbp+var_20], xmm0
0x180017a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a3f  mov     ebx, eax
0x180017a41  test    eax, eax
0x180017a43  js      short loc_1800179ED
0x180017a45  jnz     short loc_180017A68
0x180017a47  mov     rcx, [rbp+arg_10]
0x180017a4b  lea     rdx, IID_IXMLDOMProcessingInstruction
0x180017a52  mov     r8, r14
0x180017a55  mov     rax, [rcx]
0x180017a58  mov     rax, [rax]
0x180017a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a60  mov     ebx, eax
0x180017a62  test    eax, eax
0x180017a64  jns     short loc_180017A7D
0x180017a66  jmp     short loc_1800179ED
0x180017a68  mov     ebx, 80004005h
0x180017a6d  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180017a74  jz      short loc_180017A7D
0x180017a76  mov     ecx, ebx; int
0x180017a78  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180017a7d  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x180017a81  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180017a86  mov     rcx, [rbp+arg_18]
0x180017a8a  test    rcx, rcx
0x180017a8d  jz      short loc_180017A9F
0x180017a8f  mov     rax, [rcx]
0x180017a92  mov     rax, [rax+10h]
0x180017a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a9b  mov     [rbp+arg_18], r15
0x180017a9f  mov     rcx, [rbp+var_28]
0x180017aa3  test    rcx, rcx
0x180017aa6  jz      short loc_180017AB8
0x180017aa8  mov     rax, [rcx]
0x180017aab  mov     rax, [rax+10h]
0x180017aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ab4  mov     [rbp+var_28], r15
0x180017ab8  mov     rdx, [rbp+arg_10]
0x180017abc  test    rdx, rdx
0x180017abf  jz      short loc_180017AD0
0x180017ac1  mov     rcx, [rdx]
0x180017ac4  mov     rax, [rcx+10h]
0x180017ac8  mov     rcx, rdx
0x180017acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ad0  mov     eax, ebx
0x180017ad2  add     rsp, 60h
0x180017ad6  pop     r15
0x180017ad8  pop     r14
0x180017ada  pop     r12
0x180017adc  pop     rdi
0x180017add  pop     rsi
0x180017ade  pop     rbx
0x180017adf  pop     rbp
0x180017ae0  retn
```
