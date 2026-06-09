# CCreateComputeShaderValidator::ValidateShader(void)

- ea: `0x180018518`
- end: `0x180018808`
- name: `?ValidateShader@CCreateComputeShaderValidator@@IEAAXXZ`
- size: `752`
- prototype: `void __fastcall(CCreateComputeShaderValidator *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017d84`

## callees

- `0x18000663c`
- `0x18000b010`
- `0x180018518`
- `0x18001a12c`
- `0x18001a488`
- `0x18001a6ac`
- `0x18001a900`
- `0x18002ef50`
- `0x18009b0b4`
- `0x1800a4f88`
- `0x18017acc0`
- `0x180262020`

## string_xrefs

- `0x180018759`: `Shader uses 11_1 double precision extensions which are not supported on the current device.`
- `0x1800187ea`: `Compute shader version not supported.`
- `0x1800186ba`: `ThreadedCommandAllocatorReset`
- `0x18001865f`: `Compute Shader is corrupt or in an unrecognized format.`
- `0x180018656`: `Compute Shader is unsigned or a preview shader and experimental shader models are not enabled, or shader is otherwise corrupt.`
- `0x180018584`: `Encoded Compute Shader size doesn't match specified size.`

## pseudocode

```c
void __fastcall CCreateComputeShaderValidator::ValidateShader(const void **this)
{
  CCreateComputeShaderValidator *v1; // rsi
  _DWORD *v2; // rdi
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 v7; // rcx
  unsigned int v8; // eax
  void (__fastcall *v9)(const unsigned __int8 *, unsigned int, unsigned __int8 *); // rdx
  unsigned __int64 v10; // rcx
  unsigned int v11; // r9d
  int v12; // eax
  const char *v13; // r8
  int v14; // eax
  __int16 v15; // bx
  unsigned int v16; // eax
  const unsigned int *ShaderBytecode; // rax
  unsigned int VersionFromShaderBytecodeWrapper; // eax
  _com_error *v19; // [rsp+30h] [rbp-48h] BYREF
  __int128 v20; // [rsp+38h] [rbp-40h] BYREF
  __int64 v21; // [rsp+48h] [rbp-30h]
  const unsigned int *v23; // [rsp+88h] [rbp+10h] BYREF
  const unsigned int *v24; // [rsp+90h] [rbp+18h]
  _DWORD *v25; // [rsp+98h] [rbp+20h]

  v1 = (CCreateComputeShaderValidator *)this;
  v2 = this + 4;
  if ( *((_DWORD *)this + 9) == 256 )
  {
    ++*v2;
    TDebugOutputFunctor::operator()(
      &g_coreRuntimeTallyErrorOutputFunctor,
      1381,
      "Shaders not supported in D3D_FEATURE_LEVEL_1_0_GENERIC");
    ThrowFailure(-2147024809);
  }
  v25 = v2;
  CCreateShaderValidator::ValidateShader(v1);
  v3 = sqlite3_str_length(*((_QWORD *)v1 + 2));
  if ( !v3 || v3 != *((_QWORD *)v1 + 3) )
  {
    ++*v2;
    TDebugOutputFunctor::operator()(
      &g_coreRuntimeTallyErrorOutputFunctor,
      322,
      "Encoded Compute Shader size doesn't match specified size.");
    ThrowFailure(-2147024809);
  }
  v4 = 0;
  LODWORD(v23) = 0;
  v5 = *((_QWORD *)v1 + 1);
  if ( v5 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 24LL))(v5, 0);
  v6 = *((_BYTE *)v1 + 68) != 0 ? 14 : 2;
  v7 = *((_QWORD *)v1 + 2);
  v20 = 0;
  v21 = 0;
  if ( v7 )
  {
    v8 = sqlite3_str_length(v7);
    v12 = CDXBCParser::ReadDXBC((unsigned __int64 *)&v20, v10, v8, v11, &v23, v9);
    if ( v12 == -2147024882 )
    {
      ++*v2;
      TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 1266, "Out of memory parsing bytecode.");
      ThrowFailure(-2147024882);
    }
    else if ( v12 >= 0 )
    {
      goto LABEL_19;
    }
    v4 = (int)v23;
  }
  if ( !*((_BYTE *)v1 + 68) && (v4 == 4 || v4 == 1) )
    v13 = "Compute Shader is unsigned or a preview shader and experimental shader models are not enabled, or shader is ot"
          "herwise corrupt.";
  else
    v13 = "Compute Shader is corrupt or in an unrecognized format.";
  ++*v2;
  TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 322, v13, v6);
LABEL_19:
  v24 = 0;
  v23 = 0;
  if ( (int)DXBCGetNamedBlob(*((_QWORD *)v1 + 2), 1162036809, &v23, 0) >= 0 && v23[3] )
  {
    ++*v2;
    TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 292, "ThreadedCommandAllocatorReset");
  }
  v23 = 0;
  v14 = DXBCGetShaderFeatureInfo(*((const void **)v1 + 2), (struct SShaderFeatureInfo *)&v23);
  if ( v14 >= 0 )
  {
    v15 = (__int16)v23;
    if ( ((unsigned __int8)v23 & 8) != 0 && *((_DWORD *)v1 + 10) == 1 )
    {
      v16 = *((_DWORD *)v1 + 9) - 4097;
      if ( v16 <= 0xA0FE )
      {
        ++*v2;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          431,
          "Shader uses UAV bind slots after the first 8, which are not supported with Resource Binding Tier 1 when Featur"
          "e Level < D3D_FEATURE_LEVEL_11_1.");
      }
    }
    if ( (v15 & 1) != 0 && !*((_BYTE *)v1 + 76) )
    {
      ++*v2;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        337,
        "Shader uses double precision float ops which are not supported on the current device.");
    }
    if ( (v15 & 0x20) != 0 && !*((_BYTE *)v1 + 76) )
    {
      ++*v2;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        422,
        "Shader uses 11_1 double precision extensions which are not supported on the current device.");
    }
    if ( (v15 & 0x100) != 0 && !*((_BYTE *)v1 + 77) )
    {
      ++*v2;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        322,
        "Shader uses tiled resources shader ops, but the device does not support this. To check for support, check device"
        " caps via the CheckFeatureSupport() API");
    }
  }
  try
  {
    ShaderBytecode = VersionedDeviceData::GetShaderBytecode(*(VersionedDeviceData **)v1, *((const void **)v1 + 2));
    v24 = ShaderBytecode;
  }
  catch ( _com_error *v19 )
  {
    if ( *((_DWORD *)v19 + 2) == -2147024882 )
    {
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 321, "Out of memory parsing bytecode.");
      ThrowFailure(-2147024882);
      return;
    }
    if ( *((int *)v19 + 2) < 0 )
    {
      v23 = 0;
      if ( *((int *)this + 13) < 96
        && (int)DXBCGetDxilShaderCode(this[2], &v23) >= 0
        && (int)DXBCGetDriverShaderCode(this[2], &v23) < 0 )
      {
        ++*((_DWORD *)this + 8);
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          322,
          "Shader is corrupt or in an unrecognized format. Current device only supports DXBC and the shader blob only contains DXIL.");
        return;
      }
      ++*((_DWORD *)this + 8);
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        322,
        "Shader is corrupt or in an unrecognized format.");
      return;
    }
    v1 = (CCreateComputeShaderValidator *)this;
    ShaderBytecode = v24;
    v2 = v25;
  }
  VersionFromShaderBytecodeWrapper = GetVersionFromShaderBytecodeWrapper(ShaderBytecode);
  if ( !(unsigned __int8)ShaderVersionSupported(*((unsigned int *)v1 + 13), 5, VersionFromShaderBytecodeWrapper) )
  {
    ++*v2;
    TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 881, "Compute shader version not supported.");
  }
}

```

## disassembly

```asm
0x180018518  mov     [rsp+arg_0], rcx
0x18001851d  push    rbx
0x18001851e  push    rsi
0x18001851f  push    rdi
0x180018520  push    r15
0x180018522  sub     rsp, 58h
0x180018526  mov     rsi, rcx
0x180018529  lea     rdi, [rcx+20h]
0x18001852d  lea     r15, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180018534  cmp     dword ptr [rcx+24h], 100h
0x18001853b  jnz     short loc_18001855D
0x18001853d  inc     dword ptr [rdi]
0x18001853f  lea     r8, aShadersNotSupp; "Shaders not supported in D3D_FEATURE_LE"...
0x180018546  mov     edx, 565h
0x18001854b  mov     rcx, r15
0x18001854e  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180018553  mov     ecx, 80070057h; int
0x180018558  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18001855d  mov     [rsp+78h+arg_18], rdi
0x180018565  mov     rcx, rsi; this
0x180018568  call    ?ValidateShader@CCreateShaderValidator@@IEAAXXZ; CCreateShaderValidator::ValidateShader(void)
0x18001856d  mov     rcx, [rsi+10h]
0x180018571  call    sqlite3_str_length
0x180018576  mov     ecx, eax
0x180018578  test    eax, eax
0x18001857a  jz      short loc_180018582
0x18001857c  cmp     rcx, [rsi+18h]
0x180018580  jz      short loc_1800185A2
0x180018582  inc     dword ptr [rdi]
0x180018584  lea     r8, aEncodedCompute; "Encoded Compute Shader size doesn't mat"...
0x18001858b  mov     edx, 142h
0x180018590  mov     rcx, r15
0x180018593  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180018598  mov     ecx, 80070057h; int
0x18001859d  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800185a2  xor     ebx, ebx
0x1800185a4  mov     dword ptr [rsp+78h+arg_8], ebx
0x1800185ab  xor     edx, edx
0x1800185ad  mov     rcx, [rsi+8]
0x1800185b1  test    rcx, rcx
0x1800185b4  jz      short loc_1800185C5
0x1800185b6  mov     rax, [rcx]
0x1800185b9  mov     rax, [rax+18h]
0x1800185bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185c2  mov     rdx, rax
0x1800185c5  mov     cl, [rsi+44h]
0x1800185c8  neg     cl
0x1800185ca  sbb     r9d, r9d
0x1800185cd  and     r9d, 0Ch
0x1800185d1  add     r9d, 2
0x1800185d5  mov     rcx, [rsi+10h]
0x1800185d9  xorps   xmm0, xmm0
0x1800185dc  movdqu  [rsp+78h+var_40], xmm0
0x1800185e2  mov     [rsp+78h+var_30], rbx
0x1800185e7  test    rcx, rcx
0x1800185ea  jz      short loc_180018646
0x1800185ec  call    sqlite3_str_length
0x1800185f1  mov     r8d, eax
0x1800185f4  mov     [rsp+78h+var_50], rdx
0x1800185f9  lea     rax, [rsp+78h+arg_8]
0x180018601  mov     [rsp+78h+var_58], rax
0x180018606  mov     rdx, rcx
0x180018609  lea     rcx, [rsp+78h+var_40]
0x18001860e  call    ?ReadDXBC@CDXBCParser@@QEAAJPEBXIW4DXBCParserHashFlags@@PEAW4DXBCParserHashType@@P6AXPEBEIPEAE@Z@Z; CDXBCParser::ReadDXBC(void const *,uint,DXBCParserHashFlags,DXBCParserHashType *,void (*)(uchar const *,uint,uchar *))
0x180018613  mov     ebx, 8007000Eh
0x180018618  cmp     eax, ebx
0x18001861a  jnz     short loc_18001863B
0x18001861c  inc     dword ptr [rdi]
0x18001861e  lea     r8, aOutOfMemoryPar; "Out of memory parsing bytecode."
0x180018625  mov     edx, 4F2h
0x18001862a  mov     rcx, r15
0x18001862d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180018632  mov     ecx, ebx; int
0x180018634  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180018639  jmp     short loc_18001863F
0x18001863b  test    eax, eax
0x18001863d  jns     short loc_180018675
0x18001863f  mov     ebx, dword ptr [rsp+78h+arg_8]
0x180018646  cmp     byte ptr [rsi+44h], 0
0x18001864a  jnz     short loc_18001865F
0x18001864c  cmp     ebx, 4
0x18001864f  jz      short loc_180018656
0x180018651  cmp     ebx, 1
0x180018654  jnz     short loc_18001865F
0x180018656  lea     r8, aComputeShaderI_0; "Compute Shader is unsigned or a preview"...
0x18001865d  jmp     short loc_180018666
0x18001865f  lea     r8, aComputeShaderI; "Compute Shader is corrupt or in an unre"...
0x180018666  inc     dword ptr [rdi]
0x180018668  mov     edx, 142h
0x18001866d  mov     rcx, r15
0x180018670  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180018675  mov     [rsp+78h+arg_10], 0
0x180018681  mov     [rsp+78h+arg_8], 0
0x18001868d  xor     r9d, r9d
0x180018690  lea     r8, [rsp+78h+arg_8]
0x180018698  mov     edx, 45434649h
0x18001869d  mov     rcx, [rsi+10h]
0x1800186a1  call    ?DXBCGetNamedBlob@@YAJPEBXW4DXBCFourCC@@PEAPEBIPEAI@Z; DXBCGetNamedBlob(void const *,DXBCFourCC,uint const * *,uint *)
0x1800186a6  test    eax, eax
0x1800186a8  js      short loc_1800186CE
0x1800186aa  mov     rax, [rsp+78h+arg_8]
0x1800186b2  cmp     dword ptr [rax+0Ch], 0
0x1800186b6  jz      short loc_1800186CE
0x1800186b8  inc     dword ptr [rdi]
0x1800186ba  lea     r8, aThreadedcomman; "ThreadedCommandAllocatorReset"
0x1800186c1  mov     edx, 124h
0x1800186c6  mov     rcx, r15
0x1800186c9  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800186ce  mov     [rsp+78h+arg_8], 0
0x1800186da  lea     rdx, [rsp+78h+arg_8]; struct SShaderFeatureInfo *
0x1800186e2  mov     rcx, [rsi+10h]; void *
0x1800186e6  call    ?DXBCGetShaderFeatureInfo@@YAJPEBXPEAUSShaderFeatureInfo@@@Z; DXBCGetShaderFeatureInfo(void const *,SShaderFeatureInfo *)
0x1800186eb  test    eax, eax
0x1800186ed  js      loc_180018791
0x1800186f3  mov     rbx, [rsp+78h+arg_8]
0x1800186fb  test    bl, 8
0x1800186fe  jz      short loc_18001872B
0x180018700  cmp     dword ptr [rsi+28h], 1
0x180018704  jnz     short loc_18001872B
0x180018706  mov     eax, [rsi+24h]
0x180018709  sub     eax, 1001h
0x18001870e  cmp     eax, 0A0FEh
0x180018713  ja      short loc_18001872B
0x180018715  inc     dword ptr [rdi]
0x180018717  lea     r8, aShaderUsesUavB; "Shader uses UAV bind slots after the fi"...
0x18001871e  mov     edx, 1AFh
0x180018723  mov     rcx, r15
0x180018726  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18001872b  test    bl, 1
0x18001872e  jz      short loc_18001874C
0x180018730  cmp     byte ptr [rsi+4Ch], 0
0x180018734  jnz     short loc_18001874C
0x180018736  inc     dword ptr [rdi]
0x180018738  lea     r8, aShaderUsesDoub; "Shader uses double precision float ops "...
0x18001873f  mov     edx, 151h
0x180018744  mov     rcx, r15
0x180018747  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18001874c  test    bl, 20h
0x18001874f  jz      short loc_18001876D
0x180018751  cmp     byte ptr [rsi+4Ch], 0
0x180018755  jnz     short loc_18001876D
0x180018757  inc     dword ptr [rdi]
0x180018759  lea     r8, aShaderUses111D; "Shader uses 11_1 double precision exten"...
0x180018760  mov     edx, 1A6h
0x180018765  mov     rcx, r15
0x180018768  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18001876d  bt      rbx, 8
0x180018772  jnb     short loc_180018791
0x180018774  cmp     byte ptr [rsi+4Dh], 0
0x180018778  jnz     short loc_180018791
0x18001877a  inc     dword ptr [rdi]
0x18001877c  lea     r8, aShaderUsesTile; "Shader uses tiled resources shader ops,"...
0x180018783  mov     edx, 142h
0x180018788  mov     rcx, r15
0x18001878b  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180018790  nop
0x180018791  mov     rdx, [rsi+10h]; void *
0x180018795  mov     rcx, [rsi]; this
0x180018798  call    ?GetShaderBytecode@VersionedDeviceData@@QEBAPEBIPEBX@Z; VersionedDeviceData::GetShaderBytecode(void const *)
0x18001879d  mov     [rsp+78h+arg_10], rax
0x1800187a5  jmp     short loc_1800187CC
0x1800187a7  jmp     short loc_1800187FE
0x1800187a9  jmp     short loc_1800187FE
0x1800187ab  jmp     short loc_1800187FE
0x1800187ad  lea     r15, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x1800187b4  mov     rsi, [rsp+78h+arg_0]
0x1800187bc  mov     rax, [rsp+78h+arg_10]
0x1800187c4  mov     rdi, [rsp+78h+arg_18]
0x1800187cc  mov     rcx, rax; unsigned int *
0x1800187cf  call    ?GetVersionFromShaderBytecodeWrapper@@YAIPEBI@Z; GetVersionFromShaderBytecodeWrapper(uint const *)
0x1800187d4  mov     r8d, eax
0x1800187d7  mov     edx, 5
0x1800187dc  mov     ecx, [rsi+34h]
0x1800187df  call    ?ShaderVersionSupported@@YA_NW4D3D_SHADER_MODEL@@W4D3D10_SB_TOKENIZED_PROGRAM_TYPE@@I@Z; ShaderVersionSupported(D3D_SHADER_MODEL,D3D10_SB_TOKENIZED_PROGRAM_TYPE,uint)
0x1800187e4  test    al, al
0x1800187e6  jnz     short loc_1800187FE
0x1800187e8  inc     dword ptr [rdi]
0x1800187ea  lea     r8, aComputeShaderV; "Compute shader version not supported."
0x1800187f1  mov     edx, 371h
0x1800187f6  mov     rcx, r15
0x1800187f9  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800187fe  add     rsp, 58h
0x180018802  pop     r15
0x180018804  pop     rdi
0x180018805  pop     rsi
0x180018806  pop     rbx
0x180018807  retn
```
