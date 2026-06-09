# CDevice::ValidateCommandSignature(D3D12_COMMAND_SIGNATURE_DESC const *,CRootSignature *,uint &)

- ea: `0x180073360`
- end: `0x180073909`
- name: `?ValidateCommandSignature@CDevice@@IEAAXPEBUD3D12_COMMAND_SIGNATURE_DESC@@PEAVCRootSignature@@AEAI@Z`
- size: `1449`
- prototype: `void __fastcall(CDevice *__hidden this, const struct D3D12_COMMAND_SIGNATURE_DESC *, struct CRootSignature *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180073250`

## callees

- `0x18000b010`
- `0x180073360`
- `0x1800a07a8`
- `0x1800a09c0`
- `0x1800fd9a8`
- `0x1800fdf4c`
- `0x180262020`

## string_xrefs

- `0x180073447`: `A command signature must contain 1 Draw/Dispatch/DispatchMesh/DispatchRay command.`
- `0x1800733d5`: `A command signature must contain exactly 1 Draw/Dispatch/DispatchMesh/DispatchRays command.  That command must come last.`
- `0x1800735e5`: `D3D12_INDIRECT_ARGUMENT_TYPE_DISPATCH_RAYS can't be used in a command signature unless the device supports D3D12_RAYTRACING_TIER_1_1+.`
- `0x180073703`: `Index buffer changes are only allowed when the command signature contains a parameter of type D3D12_INDIRECT_ARGUMENT_TYPE_DRAW_INDEXED.`
- `0x180073768`: `Vertex buffer changes are disallowed when the command signature contains a parameter of type D3D12_INDIRECT_ARGUMENT_TYPE_DISPATCH/DISPATCH_RAYS.`
- `0x18007347b`: `A root signature should be specified if and only if the command signature indicates that root arguments will be changed.`
- `0x180073628`: `unordered access view`
- `0x18007380f`: `Command signature byte stride must be a multiple of 4 bytes.`
- `0x1800738b1`: `Command signature byte stride (%u bytes) is not large enough.  Required size is (%u bytes).`
- `0x1800738d4`: `Command signature byte stride (%u bytes) must be a multiple of 4.`

## pseudocode

```c
void __fastcall CDevice::ValidateCommandSignature(
        CDevice *this,
        const struct D3D12_COMMAND_SIGNATURE_DESC *a2,
        struct CRootSignature *a3,
        unsigned int *a4)
{
  CDevice *v4; // r14
  unsigned int *v5; // rbx
  char v8; // di
  const D3D12_INDIRECT_ARGUMENT_DESC **p_pArgumentDescs; // r12
  char v10; // bp
  UINT v11; // esi
  int Type; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  const D3D12_INDIRECT_ARGUMENT_DESC *v17; // rax
  int v18; // r10d
  UINT NumArgumentDescs; // edx
  int v20; // r9d
  int v21; // edi
  int v22; // r12d
  D3D12_INDIRECT_ARGUMENT_TYPE v23; // r8d
  const D3D12_INDIRECT_ARGUMENT_DESC **v24; // rbx
  const D3D12_INDIRECT_ARGUMENT_DESC *v25; // rbp
  int v26; // edx
  int v27; // edx
  int v28; // edx
  int v29; // edx
  const char *v30; // rax
  enum D3D12_ROOT_PARAMETER_TYPE v31; // r9d
  UINT Slot; // ecx
  int v33; // esi
  UINT v34; // edx
  const D3D12_INDIRECT_ARGUMENT_DESC **v35; // r9
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  D3D12_INDIRECT_ARGUMENT_TYPE v43; // [rsp+30h] [rbp-68h]
  _DWORD v44[2]; // [rsp+38h] [rbp-60h] BYREF
  const D3D12_INDIRECT_ARGUMENT_DESC **v45; // [rsp+40h] [rbp-58h]
  int v46; // [rsp+A0h] [rbp+8h]
  int v47; // [rsp+A8h] [rbp+10h]

  v4 = (CDevice *)((char *)this + 288);
  v5 = a4;
  if ( *((_DWORD *)this + 76) == 256 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 97) + 32LL))(*((_QWORD *)this + 97), 1381, 0);
    ThrowFailure(-2147024809);
  }
  v8 = 0;
  p_pArgumentDescs = &a2->pArgumentDescs;
  v10 = 0;
  v11 = 0;
  if ( !a2->NumArgumentDescs )
  {
LABEL_18:
    CDevice::ReportRetailValidationErrorF(
      v4,
      D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
      "A command signature must contain 1 Draw/Dispatch/DispatchMesh/DispatchRay command.");
    ThrowFailure(-2147024809);
    v45 = &a2->pArgumentDescs;
    goto LABEL_19;
  }
  v45 = &a2->pArgumentDescs;
  do
  {
    if ( v8 )
    {
      CDevice::ReportRetailValidationErrorF(
        v4,
        D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
        "A command signature must contain exactly 1 Draw/Dispatch/DispatchMesh/DispatchRays command.  That command must come last.");
      ThrowFailure(-2147024809);
    }
    Type = (*p_pArgumentDescs)[v11].Type;
    if ( Type > 6 )
    {
      v26 = Type - 7;
      if ( !v26 || (v27 = v26 - 1) == 0 )
      {
LABEL_15:
        v10 = 1;
        goto LABEL_16;
      }
      v28 = v27 - 1;
      if ( !v28 )
      {
        if ( *((int *)this + 106) < 11 )
        {
          CDevice::ReportRetailValidationErrorF(
            v4,
            D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
            "D3D12_INDIRECT_ARGUMENT_TYPE_DISPATCH_RAYS can't be used in a command signature unless the device supports D"
            "3D12_RAYTRACING_TIER_1_1+.");
          ThrowFailure(-2147024809);
        }
LABEL_43:
        v8 = 1;
        goto LABEL_16;
      }
      v29 = v28 - 1;
      if ( !v29 )
        goto LABEL_43;
      if ( v29 != 1 )
        goto LABEL_37;
      v10 = 1;
      if ( *((int *)this + 135) < 11 )
      {
        CDevice::ReportRetailValidationErrorF(
          v4,
          D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
          "Incrementing constant not supported; device doesn't support D3D12_EXECUTE_INDIRECT_TIER_1_1.");
        goto LABEL_38;
      }
    }
    else
    {
      if ( Type == 6 )
        goto LABEL_15;
      if ( !Type )
        goto LABEL_43;
      v13 = Type - 1;
      if ( !v13 )
        goto LABEL_43;
      v14 = v13 - 1;
      if ( !v14 )
        goto LABEL_43;
      v15 = v14 - 1;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( v16 )
        {
          if ( v16 == 1 )
            goto LABEL_15;
LABEL_37:
          CDevice::ReportRetailValidationErrorF(
            v4,
            D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
            "Unexpected parameter type.");
LABEL_38:
          ThrowFailure(-2147024809);
        }
      }
    }
LABEL_16:
    ++v11;
  }
  while ( v11 < a2->NumArgumentDescs );
  if ( !v8 )
    goto LABEL_18;
LABEL_19:
  if ( v10 != (a3 != 0) )
  {
    CDevice::ReportRetailValidationErrorF(
      v4,
      D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
      "A root signature should be specified if and only if the command signature indicates that root arguments will be changed.");
    ThrowFailure(-2147024809);
  }
  v17 = *p_pArgumentDescs;
  v18 = 0;
  NumArgumentDescs = a2->NumArgumentDescs;
  v20 = 0;
  v21 = 0;
  v46 = 0;
  v22 = 0;
  v47 = 0;
  v23 = v17[NumArgumentDescs - 1].Type;
  v43 = v23;
  v44[0] = -1;
  v44[1] = -1;
  if ( NumArgumentDescs )
  {
    v24 = v45;
    while ( 1 )
    {
      v25 = *v24;
      if ( (*v24)[v22].Type == D3D12_INDIRECT_ARGUMENT_TYPE_VERTEX_BUFFER_VIEW )
      {
        if ( v23 == D3D12_INDIRECT_ARGUMENT_TYPE_DISPATCH || v23 == D3D12_INDIRECT_ARGUMENT_TYPE_DISPATCH_RAYS )
        {
          CDevice::ReportRetailValidationErrorF(
            v4,
            D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
            "Vertex buffer changes are disallowed when the command signature contains a parameter of type D3D12_INDIRECT_"
            "ARGUMENT_TYPE_DISPATCH/DISPATCH_RAYS.");
          v18 = v46;
          ++v21;
        }
        if ( v25[v22].VertexBuffer.Slot >= 0x20 )
        {
          CDevice::ReportRetailValidationErrorF(
            v4,
            D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
            "Invalid vertex buffer slot.");
          v18 = v46;
          ++v21;
        }
        Slot = v25[v22].VertexBuffer.Slot;
        v33 = 1 << Slot;
        if ( ((1 << Slot) & v18) != 0 )
        {
          CDevice::ReportRetailValidationErrorF(
            v4,
            D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
            "Vertex buffer slot %u is defined more than once.",
            Slot);
          v18 = v46;
          ++v21;
        }
        v18 |= v33;
        v46 = v18;
        goto LABEL_64;
      }
      if ( (*v24)[v22].Type == D3D12_INDIRECT_ARGUMENT_TYPE_INDEX_BUFFER_VIEW )
        break;
      switch ( (*v24)[v22].Type )
      {
        case D3D12_INDIRECT_ARGUMENT_TYPE_CONSTANT:
          if ( !v25[v22].Constant.Num32BitValuesToSet )
          {
            CDevice::ReportRetailValidationErrorF(
              v4,
              D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
              "Root constant changes must change at least 1 value.");
            ThrowFailure(-2147024809);
          }
          CDevice::ValidateIncreasingRootParameterIndex(
            this,
            (struct RootParameterIndexAndOffset *)v44,
            v25[v22].VertexBuffer.Slot,
            v25[v22].Constant.DestOffsetIn32BitValues,
            v25[v22].Constant.Num32BitValuesToSet);
          CDevice::ValidateCompatibleRootConstantChange(
            this,
            a3,
            v25[v22].VertexBuffer.Slot,
            v25[v22].Constant.DestOffsetIn32BitValues,
            v25[v22].Constant.Num32BitValuesToSet);
          goto LABEL_31;
        case D3D12_INDIRECT_ARGUMENT_TYPE_CONSTANT_BUFFER_VIEW:
          CDevice::ValidateIncreasingRootParameterIndex(
            this,
            (struct RootParameterIndexAndOffset *)v44,
            v25[v22].VertexBuffer.Slot,
            0,
            1);
          v30 = "constant buffer view";
          v31 = D3D12_ROOT_PARAMETER_TYPE_CBV;
LABEL_45:
          CDevice::ValidateCompatibleRootViewChange(this, a3, v25[v22].VertexBuffer.Slot, v31, v30);
LABEL_31:
          v18 = v46;
LABEL_64:
          v20 = v47;
LABEL_65:
          v23 = v43;
          break;
        case D3D12_INDIRECT_ARGUMENT_TYPE_SHADER_RESOURCE_VIEW:
          CDevice::ValidateIncreasingRootParameterIndex(
            this,
            (struct RootParameterIndexAndOffset *)v44,
            v25[v22].VertexBuffer.Slot,
            0,
            1);
          v30 = "shader resource view";
          v31 = D3D12_ROOT_PARAMETER_TYPE_SRV;
          goto LABEL_45;
        case D3D12_INDIRECT_ARGUMENT_TYPE_UNORDERED_ACCESS_VIEW:
          CDevice::ValidateIncreasingRootParameterIndex(
            this,
            (struct RootParameterIndexAndOffset *)v44,
            v25[v22].VertexBuffer.Slot,
            0,
            1);
          v30 = "unordered access view";
          v31 = D3D12_ROOT_PARAMETER_TYPE_UAV;
          goto LABEL_45;
        case D3D12_INDIRECT_ARGUMENT_TYPE_INCREMENTING_CONSTANT:
          CDevice::ValidateIncreasingRootParameterIndex(
            this,
            (struct RootParameterIndexAndOffset *)v44,
            v25[v22].VertexBuffer.Slot,
            v25[v22].Constant.DestOffsetIn32BitValues,
            1);
          CDevice::ValidateCompatibleRootConstantChange(
            this,
            a3,
            v25[v22].VertexBuffer.Slot,
            v25[v22].Constant.DestOffsetIn32BitValues,
            1u);
          goto LABEL_31;
      }
      if ( ++v22 >= a2->NumArgumentDescs )
      {
        v5 = a4;
        goto LABEL_68;
      }
    }
    if ( v23 != D3D12_INDIRECT_ARGUMENT_TYPE_DRAW_INDEXED )
    {
      CDevice::ReportRetailValidationErrorF(
        v4,
        D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
        "Index buffer changes are only allowed when the command signature contains a parameter of type D3D12_INDIRECT_ARG"
        "UMENT_TYPE_DRAW_INDEXED.");
      v20 = v47;
      ++v21;
    }
    if ( v20 )
    {
      CDevice::ReportRetailValidationErrorF(
        v4,
        D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
        "Index buffer cannot be defined more than once.");
      v20 = v47;
      ++v21;
    }
    v18 = v46;
    v47 = ++v20;
    goto LABEL_65;
  }
LABEL_68:
  if ( (a2->ByteStride & 3) != 0 )
  {
    CDevice::ReportRetailValidationErrorF(
      v4,
      D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
      "Command signature byte stride must be a multiple of 4 bytes.");
    ++v21;
  }
  v34 = 0;
  *v5 = 0;
  if ( a2->NumArgumentDescs )
  {
    v35 = v45;
    do
    {
      v36 = (*v35)[v34].Type;
      if ( v36 > 5 )
      {
        v39 = v36 - 6;
        if ( !v39 || (v40 = v39 - 1) == 0 || (v41 = v40 - 1) == 0 )
        {
          *v5 += 8;
          goto LABEL_89;
        }
        v42 = v41 - 1;
        if ( !v42 )
        {
          *v5 += 104;
          goto LABEL_89;
        }
        if ( v42 == 1 )
LABEL_86:
          *v5 += 12;
      }
      else
      {
        if ( v36 == 5 )
        {
          *v5 += 4 * (*v35)[v34].Constant.Num32BitValuesToSet;
          goto LABEL_89;
        }
        if ( !v36 )
          goto LABEL_78;
        v37 = v36 - 1;
        if ( !v37 )
        {
          *v5 += 20;
          goto LABEL_89;
        }
        v38 = v37 - 1;
        if ( !v38 )
          goto LABEL_86;
        if ( (unsigned int)(v38 - 1) <= 1 )
LABEL_78:
          *v5 += 16;
      }
LABEL_89:
      ++v34;
    }
    while ( v34 < a2->NumArgumentDescs );
  }
  if ( a2->ByteStride < *v5 )
  {
    CDevice::ReportRetailValidationErrorF(
      v4,
      D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
      "Command signature byte stride (%u bytes) is not large enough.  Required size is (%u bytes).",
      a2->ByteStride,
      *v5);
    ++v21;
  }
  if ( (a2->ByteStride & 3) != 0 )
  {
    CDevice::ReportRetailValidationErrorF(
      v4,
      D3D12_MESSAGE_ID_CREATECOMMANDSIGNATURE_INVALID,
      "Command signature byte stride (%u bytes) must be a multiple of 4.",
      a2->ByteStride);
    ++v21;
  }
  if ( v21 )
    ThrowFailure(-2147024809);
}

```

## disassembly

```asm
0x180073360  mov     [rsp+arg_18], r9
0x180073365  mov     [rsp+arg_10], r8
0x18007336a  push    rbx
0x18007336b  push    rbp
0x18007336c  push    rsi
0x18007336d  push    rdi
0x18007336e  push    r12
0x180073370  push    r13
0x180073372  push    r14
0x180073374  push    r15
0x180073376  sub     rsp, 58h
0x18007337a  lea     r14, [rcx+120h]
0x180073381  mov     rbx, r9
0x180073384  cmp     dword ptr [r14+10h], 100h
0x18007338c  mov     r15, rdx
0x18007338f  mov     r13, rcx
0x180073392  jnz     short loc_1800733B9
0x180073394  mov     rcx, [rcx+308h]
0x18007339b  xor     r8d, r8d
0x18007339e  mov     edx, 565h
0x1800733a3  mov     rax, [rcx]
0x1800733a6  mov     rax, [rax+20h]
0x1800733aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800733af  mov     ecx, 80070057h; int
0x1800733b4  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800733b9  xor     dil, dil
0x1800733bc  lea     r12, [r15+8]
0x1800733c0  xor     bpl, bpl
0x1800733c3  xor     esi, esi
0x1800733c5  cmp     [r15+4], esi
0x1800733c9  jbe     short loc_180073447
0x1800733cb  mov     [rsp+98h+var_58], r12
0x1800733d0  test    dil, dil
0x1800733d3  jz      short loc_1800733F3
0x1800733d5  lea     r8, aACommandSignat; "A command signature must contain exactl"...
0x1800733dc  mov     edx, 2E7h; enum D3D12_MESSAGE_ID
0x1800733e1  mov     rcx, r14; this
0x1800733e4  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x1800733e9  mov     ecx, 80070057h; int
0x1800733ee  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800733f3  mov     rax, [r12]
0x1800733f7  mov     ecx, esi
0x1800733f9  add     rcx, rcx
0x1800733fc  mov     edx, [rax+rcx*8]
0x1800733ff  cmp     edx, 6
0x180073402  jg      loc_18007357D
0x180073408  jz      short loc_180073437
0x18007340a  test    edx, edx
0x18007340c  jz      loc_180073603
0x180073412  sub     edx, 1
0x180073415  jz      loc_180073603
0x18007341b  sub     edx, 1
0x18007341e  jz      loc_180073603
0x180073424  sub     edx, 1
0x180073427  jz      short loc_18007343A
0x180073429  sub     edx, 1
0x18007342c  jz      short loc_18007343A
0x18007342e  cmp     edx, 1
0x180073431  jnz     loc_18007359E
0x180073437  mov     bpl, 1
0x18007343a  inc     esi
0x18007343c  cmp     esi, [r15+4]
0x180073440  jb      short loc_1800733D0
0x180073442  test    dil, dil
0x180073445  jnz     short loc_18007346A
0x180073447  lea     r8, aACommandSignat_0; "A command signature must contain 1 Draw"...
0x18007344e  mov     edx, 2E7h; enum D3D12_MESSAGE_ID
0x180073453  mov     rcx, r14; this
0x180073456  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x18007345b  mov     ecx, 80070057h; int
0x180073460  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180073465  mov     [rsp+98h+var_58], r12
0x18007346a  cmp     [rsp+98h+arg_10], 0
0x180073473  setnz   al
0x180073476  cmp     bpl, al
0x180073479  jz      short loc_180073499
0x18007347b  lea     r8, aARootSignature; "A root signature should be specified if"...
0x180073482  mov     edx, 2E7h; enum D3D12_MESSAGE_ID
0x180073487  mov     rcx, r14; this
0x18007348a  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x18007348f  mov     ecx, 80070057h; int
0x180073494  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180073499  mov     rax, [r12]
0x18007349d  xor     r10d, r10d
0x1800734a0  mov     edx, [r15+4]
0x1800734a4  xor     r9d, r9d
0x1800734a7  xor     edi, edi
0x1800734a9  mov     [rsp+98h+arg_0], r10d
0x1800734b1  xor     r12d, r12d
0x1800734b4  mov     [rsp+98h+arg_8], r9d
0x1800734bc  lea     ecx, [rdx-1]
0x1800734bf  add     rcx, rcx
0x1800734c2  mov     r8d, [rax+rcx*8]
0x1800734c6  or      eax, 0FFFFFFFFh
0x1800734c9  mov     [rsp+98h+var_68], r8d
0x1800734ce  mov     [rsp+98h+var_60], eax
0x1800734d2  mov     [rsp+98h+var_5C], eax
0x1800734d6  test    edx, edx
0x1800734d8  jz      loc_180073809
0x1800734de  mov     rbx, [rsp+98h+var_58]
0x1800734e3  mov     rbp, [rbx]
0x1800734e6  mov     esi, r12d
0x1800734e9  add     rsi, rsi
0x1800734ec  mov     ecx, [rbp+rsi*8+0]
0x1800734f0  sub     ecx, 3
0x1800734f3  jz      loc_18007375C
0x1800734f9  sub     ecx, 1
0x1800734fc  jz      loc_1800736FD
0x180073502  sub     ecx, 1
0x180073505  jz      loc_1800736AC
0x18007350b  sub     ecx, 1
0x18007350e  jz      loc_180073680
0x180073514  sub     ecx, 1
0x180073517  jz      loc_180073654
0x18007351d  sub     ecx, 1
0x180073520  jz      loc_18007360B
0x180073526  cmp     ecx, 3
0x180073529  jnz     loc_1800737F4
0x18007352f  mov     r9d, [rbp+rsi*8+8]; int
0x180073534  lea     rdx, [rsp+98h+var_60]; struct RootParameterIndexAndOffset *
0x180073539  mov     r8d, [rbp+rsi*8+4]; int
0x18007353e  mov     rcx, r13; this
0x180073541  mov     dword ptr [rsp+98h+var_78], 1; int
0x180073549  call    ?ValidateIncreasingRootParameterIndex@CDevice@@IEAAXAEAURootParameterIndexAndOffset@@HHH@Z; CDevice::ValidateIncreasingRootParameterIndex(RootParameterIndexAndOffset &,int,int,int)
0x18007354e  mov     dword ptr [rsp+98h+var_78], 1; unsigned int
0x180073556  mov     r9d, [rbp+rsi*8+8]; unsigned int
0x18007355b  mov     rcx, r13; this
0x18007355e  mov     r8d, [rbp+rsi*8+4]; unsigned int
0x180073563  mov     rdx, [rsp+98h+arg_10]; struct CRootSignature *
0x18007356b  call    ?ValidateCompatibleRootConstantChange@CDevice@@IEAAXPEAVCRootSignature@@III@Z; CDevice::ValidateCompatibleRootConstantChange(CRootSignature *,uint,uint,uint)
0x180073570  mov     r10d, [rsp+98h+arg_0]
0x180073578  jmp     loc_1800737E7
0x18007357d  sub     edx, 7
0x180073580  jz      loc_180073437
0x180073586  sub     edx, 1
0x180073589  jz      loc_180073437
0x18007358f  sub     edx, 1
0x180073592  jz      short loc_1800735DB
0x180073594  sub     edx, 1
0x180073597  jz      short loc_180073603
0x180073599  cmp     edx, 1
0x18007359c  jz      short loc_1800735C1
0x18007359e  lea     r8, aUnexpectedPara; "Unexpected parameter type."
0x1800735a5  mov     edx, 2E7h; enum D3D12_MESSAGE_ID
0x1800735aa  mov     rcx, r14; this
0x1800735ad  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x1800735b2  mov     ecx, 80070057h; int
0x1800735b7  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800735bc  jmp     loc_18007343A
0x1800735c1  cmp     dword ptr [r13+21Ch], 0Bh
0x1800735c9  mov     bpl, 1
0x1800735cc  jge     loc_18007343A
0x1800735d2  lea     r8, aIncrementingCo; "Incrementing constant not supported; de"...
0x1800735d9  jmp     short loc_1800735A5
0x1800735db  cmp     dword ptr [r13+1A8h], 0Bh
0x1800735e3  jge     short loc_180073603
0x1800735e5  lea     r8, aD3d12IndirectA; "D3D12_INDIRECT_ARGUMENT_TYPE_DISPATCH_R"...
0x1800735ec  mov     edx, 2E7h; enum D3D12_MESSAGE_ID
0x1800735f1  mov     rcx, r14; this
0x1800735f4  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x1800735f9  mov     ecx, 80070057h; int
0x1800735fe  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180073603  mov     dil, 1
0x180073606  jmp     loc_18007343A
0x18007360b  mov     r8d, [rbp+rsi*8+4]; int
0x180073610  lea     rdx, [rsp+98h+var_60]; struct RootParameterIndexAndOffset *
0x180073615  xor     r9d, r9d; int
0x180073618  mov     dword ptr [rsp+98h+var_78], 1; int
0x180073620  mov     rcx, r13; this
0x180073623  call    ?ValidateIncreasingRootParameterIndex@CDevice@@IEAAXAEAURootParameterIndexAndOffset@@HHH@Z; CDevice::ValidateIncreasingRootParameterIndex(RootParameterIndexAndOffset &,int,int,int)
0x180073628  lea     rax, aUnorderedAcces; "unordered access view"
0x18007362f  mov     r9d, 4; enum D3D12_ROOT_PARAMETER_TYPE
0x180073635  mov     r8d, [rbp+rsi*8+4]; unsigned int
0x18007363a  mov     rcx, r13; this
0x18007363d  mov     rdx, [rsp+98h+arg_10]; struct CRootSignature *
0x180073645  mov     [rsp+98h+var_78], rax; char *
0x18007364a  call    ?ValidateCompatibleRootViewChange@CDevice@@IEAAXPEAVCRootSignature@@IW4D3D12_ROOT_PARAMETER_TYPE@@PEBD@Z; CDevice::ValidateCompatibleRootViewChange(CRootSignature *,uint,D3D12_ROOT_PARAMETER_TYPE,char const *)
0x18007364f  jmp     loc_180073570
0x180073654  mov     r8d, [rbp+rsi*8+4]; int
0x180073659  lea     rdx, [rsp+98h+var_60]; struct RootParameterIndexAndOffset *
0x18007365e  xor     r9d, r9d; int
0x180073661  mov     dword ptr [rsp+98h+var_78], 1; int
0x180073669  mov     rcx, r13; this
0x18007366c  call    ?ValidateIncreasingRootParameterIndex@CDevice@@IEAAXAEAURootParameterIndexAndOffset@@HHH@Z; CDevice::ValidateIncreasingRootParameterIndex(RootParameterIndexAndOffset &,int,int,int)
0x180073671  lea     rax, aShaderResource; "shader resource view"
0x180073678  mov     r9d, 3
0x18007367e  jmp     short loc_180073635
0x180073680  mov     r8d, [rbp+rsi*8+4]; int
0x180073685  lea     rdx, [rsp+98h+var_60]; struct RootParameterIndexAndOffset *
0x18007368a  xor     r9d, r9d; int
0x18007368d  mov     dword ptr [rsp+98h+var_78], 1; int
0x180073695  mov     rcx, r13; this
0x180073698  call    ?ValidateIncreasingRootParameterIndex@CDevice@@IEAAXAEAURootParameterIndexAndOffset@@HHH@Z; CDevice::ValidateIncreasingRootParameterIndex(RootParameterIndexAndOffset &,int,int,int)
0x18007369d  lea     rax, aConstantBuffer; "constant buffer view"
0x1800736a4  mov     r9d, 2
0x1800736aa  jmp     short loc_180073635
0x1800736ac  cmp     dword ptr [rbp+rsi*8+0Ch], 0
0x1800736b1  jnz     short loc_1800736D1
0x1800736b3  lea     r8, aRootConstantCh; "Root constant changes must change at le"...
0x1800736ba  mov     edx, 2E7h; enum D3D12_MESSAGE_ID
0x1800736bf  mov     rcx, r14; this
0x1800736c2  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x1800736c7  mov     ecx, 80070057h; int
0x1800736cc  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800736d1  mov     eax, [rbp+rsi*8+0Ch]
0x1800736d5  lea     rdx, [rsp+98h+var_60]; struct RootParameterIndexAndOffset *
0x1800736da  mov     r9d, [rbp+rsi*8+8]; int
0x1800736df  mov     rcx, r13; this
0x1800736e2  mov     r8d, [rbp+rsi*8+4]; int
0x1800736e7  mov     dword ptr [rsp+98h+var_78], eax; int
0x1800736eb  call    ?ValidateIncreasingRootParameterIndex@CDevice@@IEAAXAEAURootParameterIndexAndOffset@@HHH@Z; CDevice::ValidateIncreasingRootParameterIndex(RootParameterIndexAndOffset &,int,int,int)
0x1800736f0  mov     eax, [rbp+rsi*8+0Ch]
0x1800736f4  mov     dword ptr [rsp+98h+var_78], eax
0x1800736f8  jmp     loc_180073556
0x1800736fd  cmp     r8d, 1
0x180073701  jz      short loc_180073721
0x180073703  lea     r8, aIndexBufferCha; "Index buffer changes are only allowed w"...
0x18007370a  mov     edx, 2E7h; enum D3D12_MESSAGE_ID
0x18007370f  mov     rcx, r14; this
0x180073712  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x180073717  mov     r9d, [rsp+98h+arg_8]
0x18007371f  inc     edi
0x180073721  test    r9d, r9d
0x180073724  jz      short loc_180073744
0x180073726  lea     r8, aIndexBufferCan; "Index buffer cannot be defined more tha"...
0x18007372d  mov     edx, 2E7h; enum D3D12_MESSAGE_ID
0x180073732  mov     rcx, r14; this
0x180073735  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x18007373a  mov     r9d, [rsp+98h+arg_8]
0x180073742  inc     edi
0x180073744  mov     r10d, [rsp+98h+arg_0]
0x18007374c  inc     r9d
0x18007374f  mov     [rsp+98h+arg_8], r9d
0x180073757  jmp     loc_1800737EF
0x18007375c  cmp     r8d, 2
0x180073760  jz      short loc_180073768
0x180073762  cmp     r8d, 9
0x180073766  jnz     short loc_180073786
0x180073768  lea     r8, aVertexBufferCh; "Vertex buffer changes are disallowed wh"...
0x18007376f  mov     edx, 2E7h; enum D3D12_MESSAGE_ID
0x180073774  mov     rcx, r14; this
0x180073777  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x18007377c  mov     r10d, [rsp+98h+arg_0]
0x180073784  inc     edi
0x180073786  cmp     dword ptr [rbp+rsi*8+4], 20h ; ' '
0x18007378b  jb      short loc_1800737AB
0x18007378d  lea     r8, aInvalidVertexB; "Invalid vertex buffer slot."
0x180073794  mov     edx, 2E7h; enum D3D12_MESSAGE_ID
0x180073799  mov     rcx, r14; this
0x18007379c  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x1800737a1  mov     r10d, [rsp+98h+arg_0]
0x1800737a9  inc     edi
0x1800737ab  mov     ecx, [rbp+rsi*8+4]
0x1800737af  mov     esi, 1
0x1800737b4  shl     esi, cl
0x1800737b6  test    r10d, esi
0x1800737b9  jz      short loc_1800737DC
0x1800737bb  mov     r9d, ecx
0x1800737be  lea     r8, aVertexBufferSl; "Vertex buffer slot %u is defined more t"...
0x1800737c5  mov     rcx, r14; this
0x1800737c8  mov     edx, 2E7h; enum D3D12_MESSAGE_ID
0x1800737cd  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x1800737d2  mov     r10d, [rsp+98h+arg_0]
0x1800737da  inc     edi
0x1800737dc  or      r10d, esi
0x1800737df  mov     [rsp+98h+arg_0], r10d
0x1800737e7  mov     r9d, [rsp+98h+arg_8]
0x1800737ef  mov     r8d, [rsp+98h+var_68]
0x1800737f4  inc     r12d
0x1800737f7  cmp     r12d, [r15+4]
0x1800737fb  jb      loc_1800734E3
0x180073801  mov     rbx, [rsp+98h+arg_18]
0x180073809  test    byte ptr [r15], 3
0x18007380d  jz      short loc_180073825
0x18007380f  lea     r8, aCommandSignatu_0; "Command signature byte stride must be a"...
0x180073816  mov     edx, 2E7h; enum D3D12_MESSAGE_ID
0x18007381b  mov     rcx, r14; this
0x18007381e  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x180073823  inc     edi
0x180073825  xor     edx, edx
0x180073827  mov     dword ptr [rbx], 0
0x18007382d  cmp     [r15+4], edx
0x180073831  jbe     short loc_1800738A7
0x180073833  mov     r9, [rsp+98h+var_58]
0x180073838  mov     r8, [r9]
0x18007383b  mov     eax, edx
0x18007383d  add     rax, rax
0x180073840  mov     ecx, [r8+rax*8]
0x180073844  cmp     ecx, 5
0x180073847  jg      short loc_180073879
0x180073849  jz      short loc_18007386D
0x18007384b  test    ecx, ecx
0x18007384d  jz      short loc_180073863
0x18007384f  sub     ecx, 1
0x180073852  jz      short loc_180073868
0x180073854  sub     ecx, 1
0x180073857  jz      short loc_180073892
0x180073859  sub     ecx, 1
0x18007385c  jz      short loc_180073863
0x18007385e  cmp     ecx, 1
  ... truncated ...
```
