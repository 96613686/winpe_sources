# D3DXShader::CShaderProgram::GenerateCode(ID3DXBuffer * *)

- ea: `0x140106890`
- end: `0x1401077dd`
- name: `?GenerateCode@CShaderProgram@D3DXShader@@UEAAJPEAPEAUID3DXBuffer@@@Z`
- size: `3917`
- prototype: `__int64 __fastcall(D3DXShader::CShaderProgram *__hidden this, struct ID3DXBuffer **)`
- caller_count: `4`
- callee_count: `20`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400cbff0`
- `0x1400d49a0`
- `0x1400ddb90`
- `0x1400e1410`

## callees

- `0x140001abc`
- `0x140003560`
- `0x140003611`
- `0x14008c0e0`
- `0x1400aafa0`
- `0x1400c4b68`
- `0x1400e9364`
- `0x1400e9440`
- `0x1400f8eb8`
- `0x1400f9308`
- `0x1400feeec`
- `0x14010076c`
- `0x14010135c`
- `0x14010368c`
- `0x140103a08`
- `0x140106890`
- `0x14010f8ac`
- `0x140110954`
- `0x140111f84`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1401069b3`
- `KERNEL32!GetProcAddress` at `0x1401069b3`
- `KERNEL32!LoadLibraryA` at `0x14010699e`
- `KERNEL32!LoadLibraryA` at `0x14010699e`
- `KERNEL32!GetModuleHandleA` at `0x14010698c`
- `KERNEL32!GetModuleHandleA` at `0x14010698c`

## string_xrefs

- `0x140106985`: `d3d9.dll`
- `0x140106997`: `d3d9.dll`
- `0x1401069a9`: `Direct3DShaderValidatorCreate9`

## pseudocode

```c
__int64 __fastcall D3DXShader::CShaderProgram::GenerateCode(D3DXShader::CShaderProgram *this, struct ID3DXBuffer **a2)
{
  struct D3DXCore::CBuffer *v2; // rsi
  int Code; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  HMODULE ModuleHandleA; // rax
  __int64 (*ProcAddress)(void); // rax
  __int64 v10; // rax
  unsigned __int128 v11; // rax
  void *v12; // rax
  int v13; // eax
  unsigned int v14; // r8d
  __int64 v15; // rcx
  unsigned int v16; // edi
  unsigned int v17; // ebx
  _DWORD *v18; // r9
  __int64 v19; // rsi
  __int64 v20; // rcx
  int v21; // r10d
  struct D3DXCore::CBuffer *v22; // rbp
  unsigned int v23; // r15d
  unsigned int v24; // r12d
  unsigned int v25; // r13d
  unsigned int v26; // r8d
  unsigned int v27; // r9d
  _DWORD *v28; // rdx
  __int64 v29; // rcx
  unsigned __int128 v30; // rax
  unsigned __int128 v31; // rax
  unsigned __int128 v32; // rax
  unsigned __int128 v33; // rax
  unsigned __int128 v34; // rax
  _QWORD *v35; // rbx
  __int64 i; // r8
  _DWORD *v37; // rdx
  int v38; // eax
  unsigned int v39; // esi
  unsigned int j; // edx
  _DWORD *v41; // r9
  unsigned int k; // ecx
  __int64 v43; // rax
  unsigned int m; // edx
  __int64 v45; // r8
  unsigned int v46; // ebp
  unsigned int n; // ecx
  _DWORD *v48; // rdx
  unsigned int v49; // esi
  __int64 ii; // rdi
  unsigned int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rax
  unsigned __int64 v54; // rbx
  unsigned int v55; // edx
  __int64 v56; // r8
  __int64 v57; // rcx
  unsigned __int128 v58; // rax
  unsigned __int128 v59; // rax
  size_t v60; // r8
  unsigned int *v61; // rbx
  __int64 jj; // r9
  __int64 v63; // r8
  __int64 v64; // rcx
  __int64 v65; // rdx
  __int64 kk; // rdi
  unsigned int v67; // esi
  unsigned __int64 v68; // rbx
  unsigned int v69; // edx
  __int64 v70; // r8
  unsigned __int128 v71; // rax
  unsigned __int128 v72; // rax
  size_t v73; // r8
  unsigned int *v74; // rbx
  __int64 mm; // r10
  __int64 v76; // r9
  __int64 v77; // rcx
  __int64 v78; // r8
  __int64 nn; // rdi
  int v80; // edi
  __int64 i1; // rbx
  _DWORD *v82; // rdx
  int v83; // eax
  __int64 i4; // rdx
  __int64 v85; // r8
  __int64 v86; // rbx
  __int64 i2; // r9
  int v88; // eax
  _QWORD *v89; // r15
  __int64 v90; // rbx
  int v91; // eax
  int v92; // eax
  unsigned int i3; // ecx
  __int64 v94; // r10
  __int64 v95; // rcx
  unsigned int v96; // ecx
  struct D3DXCore::CBuffer *v97; // rdi
  const void *v98; // rbx
  size_t v99; // rsi
  void *v100; // rax
  void *v101; // rcx
  __int64 v102; // rcx
  unsigned int v104; // [rsp+20h] [rbp-98h]
  unsigned int v105; // [rsp+20h] [rbp-98h]
  void *Block; // [rsp+30h] [rbp-88h]
  void *v107; // [rsp+38h] [rbp-80h]
  unsigned int *v108; // [rsp+40h] [rbp-78h]
  void *v109; // [rsp+48h] [rbp-70h]
  unsigned int *v110; // [rsp+50h] [rbp-68h]
  void *v111; // [rsp+58h] [rbp-60h]
  __int128 v112[5]; // [rsp+60h] [rbp-58h] BYREF
  struct D3DXCore::CBuffer *v113; // [rsp+C0h] [rbp+8h]
  struct D3DXCore::CBuffer *v115; // [rsp+D0h] [rbp+18h] BYREF
  void *v116; // [rsp+D8h] [rbp+20h]

  v2 = 0;
  *((_QWORD *)this + 42) = 0;
  v108 = 0;
  v110 = 0;
  Block = 0;
  v116 = 0;
  v115 = 0;
  v111 = 0;
  v113 = 0;
  v107 = 0;
  v109 = 0;
  Code = D3DXShader::CProgram::GenerateCode(this, a2);
  if ( Code < 0 )
    goto LABEL_245;
  v5 = D3DXShader::CBaseProgram::AddPool(this, "i", 0x40311u, 0xFFFFFFFF, v104);
  *((_DWORD *)this + 122) = v5;
  if ( v5 != -1 )
  {
    if ( (*(int (__fastcall **)(D3DXShader::CShaderProgram *))(*(_QWORD *)this + 320LL))(this) < 0 )
    {
LABEL_86:
      v22 = v2;
      goto LABEL_36;
    }
    v7 = *((_QWORD *)this + 67);
    *((_QWORD *)this + 44) = 0;
    *((_QWORD *)this + 45) = 0;
    *(_QWORD *)((char *)this + 372) = 0;
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      *((_QWORD *)this + 67) = 0;
    }
    if ( (*((_BYTE *)this + 244) & 2) == 0 )
    {
      ModuleHandleA = GetModuleHandleA("d3d9.dll");
      if ( ModuleHandleA || (ModuleHandleA = LoadLibraryA("d3d9.dll")) != 0 )
      {
        ProcAddress = GetProcAddress(ModuleHandleA, "Direct3DShaderValidatorCreate9");
        if ( ProcAddress )
        {
          v10 = ProcAddress();
          *((_QWORD *)this + 67) = v10;
          if ( v10 )
          {
            Code = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(const char *, unsigned int, unsigned int, unsigned int, const char *, void *), D3DXShader::CShaderProgram *, __int64))(*(_QWORD *)v10 + 24LL))(
                     v10,
                     D3DXShader::CShaderProgram::ValidationError,
                     this,
                     1);
            if ( Code < 0 )
              goto LABEL_245;
          }
        }
      }
    }
    if ( (*((_BYTE *)this + 244) & 1) != 0 )
    {
      v11 = (unsigned int)(2 * *((_DWORD *)this + 4)) * (unsigned __int128)0x20u;
      if ( !is_mul_ok((unsigned int)(2 * *((_DWORD *)this + 4)), 0x20u) )
        *(_QWORD *)&v11 = -1;
      v12 = operator new(v11, *((const struct D3DX9MEMORY::CD3DXNEW **)&v11 + 1));
      *((_QWORD *)this + 48) = v12;
      if ( !v12 )
        goto LABEL_242;
      v13 = 2 * *((_DWORD *)this + 4);
      *((_DWORD *)this + 98) = 0;
      *((_DWORD *)this + 99) = v13;
    }
    v14 = 0;
    *((_DWORD *)this + 103) = -1;
    *((_DWORD *)this + 108) = 0;
    if ( *((_DWORD *)this + 3) )
    {
      do
      {
        v15 = v14++;
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 8 * v15) + 48LL) = 0;
        v6 = *((unsigned int *)this + 3);
      }
      while ( v14 < (unsigned int)v6 );
      v16 = 0;
      if ( (_DWORD)v6 )
      {
        v17 = 0;
        do
        {
          v18 = *(_DWORD **)(*((_QWORD *)this + 4) + 8LL * v17);
          if ( (*v18 & 0x10000000) == 0 )
          {
            v19 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * (unsigned int)v18[1]);
            if ( (*(_DWORD *)(v19 + 8) & 0x210) == 0x10 || (*(_BYTE *)(v19 + 8) & 0x20) != 0 )
            {
              (*(void (__fastcall **)(D3DXShader::CShaderProgram *, _DWORD *, _QWORD))(*(_QWORD *)this + 8LL))(
                this,
                v18,
                0);
              v6 = *((unsigned int *)this + 3);
            }
            if ( *(char *)(v19 + 8) < 0 )
              ++v16;
          }
          ++v17;
        }
        while ( v17 < (unsigned int)v6 );
      }
    }
    else
    {
      v16 = 0;
    }
    v20 = *((unsigned int *)this + 60);
    if ( v16 > *((_DWORD *)this + 25) )
    {
      v112[0] = 0;
      if ( (int)D3DXGetTargetDescByVersion(v20, v6, v112) >= 0 )
      {
        if ( v21 )
          D3DXShader::CProgram::Error(
            this,
            0,
            0x119Eu,
            "maximum number of samplers exceeded. %s target can have a maximum of %i samplers",
            *(const char **)&v112[0],
            v21);
        else
          D3DXShader::CProgram::Error(
            this,
            0,
            0x11C1u,
            "%s target does not support texture lookups",
            *(const char **)&v112[0]);
      }
LABEL_35:
      v22 = v115;
LABEL_36:
      Code = -2147467259;
LABEL_241:
      v2 = v113;
      goto LABEL_246;
    }
    if ( (v20 & 0xFFFF0000) == 0xFFFE0000
      && (Code = D3DXShader::CShaderProgram::CombineConstants(
                   this,
                   *((_DWORD *)this + 38),
                   *((_DWORD *)this + 16),
                   0x10u,
                   0x204u,
                   118),
          Code < 0)
      || (*((_DWORD *)this + 60) & 0xFFFF0000) == 0xFFFF0000
      && (Code = D3DXShader::CShaderProgram::CombineConstants(this, 0xFFFFFFFF, *((_DWORD *)this + 25), 0x80u, 0, 115),
          Code < 0) )
    {
      v2 = 0;
      goto LABEL_245;
    }
    v23 = 0;
    v24 = 0;
    v25 = 0;
    if ( *((_DWORD *)this + 3) )
    {
      v26 = 0;
      v27 = 0;
      do
      {
        v28 = *(_DWORD **)(*((_QWORD *)this + 4) + 8LL * v26);
        if ( (*v28 & 0x10000000) == 0 )
        {
          v29 = (unsigned int)v28[1];
          if ( *((_DWORD *)this + 40) == (_DWORD)v29 && v28[3] + 1 > v27 )
          {
            v27 = v28[3] + 1;
          }
          else if ( *((_DWORD *)this + 38) == (_DWORD)v29 && v28[3] + 1 > v23 )
          {
            v23 = v28[3] + 1;
          }
          else if ( *((_DWORD *)this + 39) == (_DWORD)v29 && v28[3] + 1 > v24 )
          {
            v24 = v28[3] + 1;
          }
          else if ( *(char *)(*(_QWORD *)(*((_QWORD *)this + 3) + 8 * v29) + 8LL) < 0 && v28[3] + 1 > v25 )
          {
            v25 = v28[3] + 1;
          }
        }
        ++v26;
      }
      while ( v26 < *((_DWORD *)this + 3) );
    }
    v30 = v23 * (unsigned __int128)8uLL;
    if ( !is_mul_ok(v23, 8u) )
      *(_QWORD *)&v30 = -1;
    Block = operator new(v30, *((const struct D3DX9MEMORY::CD3DXNEW **)&v30 + 1));
    if ( !Block )
      goto LABEL_242;
    v31 = v24 * (unsigned __int128)8uLL;
    if ( !is_mul_ok(v24, 8u) )
      *(_QWORD *)&v31 = -1;
    v116 = operator new(v31, *((const struct D3DX9MEMORY::CD3DXNEW **)&v31 + 1));
    if ( !v116 )
      goto LABEL_242;
    v32 = v25 * (unsigned __int128)8uLL;
    if ( !is_mul_ok(v25, 8u) )
      *(_QWORD *)&v32 = -1;
    v115 = (struct D3DXCore::CBuffer *)operator new(v32, *((const struct D3DX9MEMORY::CD3DXNEW **)&v32 + 1));
    if ( !v115 )
      goto LABEL_242;
    v33 = v23 * (unsigned __int128)4uLL;
    if ( !is_mul_ok(v23, 4u) )
      *(_QWORD *)&v33 = -1;
    v111 = operator new(v33, *((const struct D3DX9MEMORY::CD3DXNEW **)&v33 + 1));
    if ( !v111 )
      goto LABEL_242;
    v34 = v24 * (unsigned __int128)4uLL;
    if ( !is_mul_ok(v24, 4u) )
      *(_QWORD *)&v34 = -1;
    v113 = (struct D3DXCore::CBuffer *)operator new(v34, *((const struct D3DX9MEMORY::CD3DXNEW **)&v34 + 1));
    if ( !v113 )
      goto LABEL_242;
    memset_0(Block, 0, 8LL * v23);
    v35 = v116;
    memset_0(v116, 0, 8LL * v24);
    v2 = v115;
    memset_0(v115, 0, 8LL * v25);
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 3); i = (unsigned int)(i + 1) )
    {
      v37 = *(_DWORD **)(*((_QWORD *)this + 4) + 8 * i);
      if ( (*v37 & 0x10000000) == 0 )
      {
        v38 = v37[1];
        if ( *((_DWORD *)this + 39) == v38 )
        {
          if ( v37[30] == -1 )
          {
            D3DXShader::CProgram::Error(this, 0, 0, "internal error: output register missing semantic");
            goto LABEL_86;
          }
          v35[v37[3]] = v37;
        }
        else if ( *((_DWORD *)this + 38) == v38 )
        {
          if ( v37[30] == -1 )
          {
            D3DXShader::CProgram::Error(this, 0, 0, "internal error: input register missing semantic");
            goto LABEL_86;
          }
          *((_QWORD *)Block + (unsigned int)v37[3]) = v37;
        }
        else if ( *(char *)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL * (unsigned int)v37[1]) + 8LL) < 0 )
        {
          *((_QWORD *)v2 + (unsigned int)v37[3]) = v37;
        }
      }
    }
    v39 = 0;
    for ( j = 0; j < *((_DWORD *)this + 3); ++j )
    {
      v41 = *(_DWORD **)(*((_QWORD *)this + 4) + 8LL * j);
      if ( *((_DWORD *)this + 38) == v41[1] && v23 )
      {
        for ( k = 0; k < v23; ++k )
        {
          v43 = *((_QWORD *)Block + k);
          if ( v43 && v41[30] == *(_DWORD *)(v43 + 120) )
            v41[3] = k;
        }
      }
    }
    memset_0(Block, 0, 8LL * v23);
    for ( m = 0; m < *((_DWORD *)this + 3); ++m )
    {
      v45 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * m);
      if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL * *(unsigned int *)(v45 + 4)) + 8LL) & 0x214) == 0x10 )
        *((_QWORD *)Block + *(unsigned int *)(v45 + 12)) = v45;
    }
    v46 = 0;
    for ( n = 0; n < v23; ++n )
    {
      v48 = (_DWORD *)*((_QWORD *)Block + n);
      if ( v48 && (*v48 & 0x10000000) == 0 )
        ++v46;
    }
    Code = D3DXShader::CShaderProgram::PortConstraints(this);
    if ( Code < 0 )
      goto LABEL_243;
    Code = (*(__int64 (__fastcall **)(D3DXShader::CShaderProgram *))(*(_QWORD *)this + 88LL))(this);
    if ( Code < 0 )
      goto LABEL_243;
    if ( (*((_BYTE *)this + 244) & 4) == 0 || (*((_DWORD *)this + 33) & 0x200000) != 0 )
    {
      Code = D3DXShader::CShaderProgram::Reset(this);
      if ( Code < 0 )
        goto LABEL_243;
      Code = (*(__int64 (__fastcall **)(D3DXShader::CShaderProgram *))(*(_QWORD *)this + 80LL))(this);
      if ( Code < 0 )
        goto LABEL_243;
    }
    if ( *((_DWORD *)this + 124) )
    {
      v49 = D3DXShader::CBaseProgram::AddPool(this, "l", 0x351u, 0xFFFFFFFF, v105);
      if ( v49 == -1 )
        goto LABEL_242;
      for ( ii = 0; (unsigned int)ii < 8; ii = (unsigned int)(ii + 1) )
      {
        v51 = D3DXShader::CBaseProgram::AddArgument(
                this,
                v49,
                (unsigned int)ii >> 2,
                ii & 3,
                *(double *)&qword_140152AA0[ii]);
        *((_DWORD *)this + ii + 125) = v51;
        if ( v51 == -1 )
          goto LABEL_242;
      }
      v39 = 0;
    }
    Code = D3DXShader::CShaderProgram::CombineConstants(
             this,
             *((_DWORD *)this + 37),
             *((_DWORD *)this + 20),
             0x200u,
             0x42080u,
             99);
    if ( Code < 0 )
      goto LABEL_243;
    Code = D3DXShader::CShaderProgram::CombineConstants(
             this,
             *((_DWORD *)this + 45),
             *((_DWORD *)this + 30),
             0x2200u,
             0x80u,
             98);
    if ( Code < 0 )
      goto LABEL_243;
    Code = D3DXShader::CShaderProgram::CombineConstants(
             this,
             *((_DWORD *)this + 50),
             *((_DWORD *)this + 22),
             0x40200u,
             0x80u,
             105);
    if ( Code < 0 )
      goto LABEL_243;
    *((_QWORD *)this + 42) = 0;
    v52 = *((_DWORD *)this + 4) ? **((_QWORD **)this + 5) : 0LL;
    v53 = *(_QWORD *)this;
    *((_QWORD *)this + 41) = v52;
    *((_DWORD *)this + 80) = 0;
    Code = (*(__int64 (__fastcall **)(D3DXShader::CShaderProgram *))(v53 + 112))(this);
    if ( Code < 0 )
      goto LABEL_243;
    v54 = 0;
    if ( *((_DWORD *)this + 3) )
    {
      v55 = 0;
      do
      {
        v56 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * v55);
        v57 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * *(unsigned int *)(v56 + 4));
        if ( (*(_DWORD *)(v57 + 8) & 0x100) != 0
          && *(_DWORD *)(v56 + 8) == -1
          && ((*(_DWORD *)(v57 + 8) & 0x800) == 0 || *((_DWORD *)this + 111)) )
        {
          v54 = (unsigned int)(v54 + 1);
        }
        ++v55;
      }
      while ( v55 < *((_DWORD *)this + 3) );
    }
    v58 = (unsigned int)(4 * v54) * (unsigned __int128)4uLL;
    if ( !is_mul_ok((unsigned int)(4 * v54), 4u) )
      *(_QWORD *)&v58 = -1;
    v107 = operator new(v58, *((const struct D3DX9MEMORY::CD3DXNEW **)&v58 + 1));
    if ( v107 )
    {
      v59 = v54 * (unsigned __int128)4uLL;
      if ( !is_mul_ok(v54, 4u) )
        *(_QWORD *)&v59 = -1;
      v108 = (unsigned int *)operator new(v59, *((const struct D3DX9MEMORY::CD3DXNEW **)&v59 + 1));
      if ( !v108 )
        goto LABEL_35;
      memset_0(v107, 0, 4LL * (unsigned int)(4 * v54));
      v60 = 4 * v54;
      v61 = v108;
      memset_0(v108, 0, v60);
      for ( jj = 0; (unsigned int)jj < *((_DWORD *)this + 3); jj = (unsigned int)(jj + 1) )
      {
        v63 = *(_QWORD *)(*((_QWORD *)this + 4) + 8 * jj);
        v64 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * *(unsigned int *)(v63 + 4));
        if ( (*(_DWORD *)(v64 + 8) & 0x100) != 0
          && *(_DWORD *)(v63 + 8) == -1
          && *(_DWORD *)(v63 + 56) == -1
          && (*(_DWORD *)(v64 + 8) & 0x40000) == 0
          && ((*(_DWORD *)(v64 + 8) & 0x800) == 0 || *((_DWORD *)this + 111)) )
        {
          v65 = 0;
          if ( v39 )
          {
            while ( v108[v65] != *(_DWORD *)(v63 + 12) )
            {
              v65 = (unsigned int)(v65 + 1);
              if ( (unsigned int)v65 >= v39 )
                goto LABEL_150;
            }
          }
          else
          {
LABEL_150:
            if ( (_DWORD)v65 == v39 )
            {
              ++v39;
              v108[v65] = *(_DWORD *)(v63 + 12);
            }
          }
          *((float *)v107 + (unsigned int)(*(_DWORD *)(v63 + 16) + 4 * v65)) = *(double *)(v63 + 32);
        }
      }
      for ( kk = 0; (unsigned int)kk < v39; kk = (unsigned int)(kk + 1) )
      {
        Code = (*(__int64 (__fastcall **)(D3DXShader::CShaderProgram *, _QWORD, __int64))(*(_QWORD *)this + 120LL))(
                 this,
                 v61[kk],
                 (__int64)v107 + 4 * (unsigned int)(4 * kk));
        if ( Code < 0 )
          goto LABEL_243;
        v61 = v108;
      }
      v67 = 0;
      v68 = 0;
      if ( *((_DWORD *)this + 3) )
      {
        v69 = 0;
        do
        {
          v70 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * v69);
          if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL * *(unsigned int *)(v70 + 4)) + 8LL) & 0x100) != 0
            && *(_DWORD *)(v70 + 8) == -1 )
          {
            v68 = (unsigned int)(v68 + 1);
          }
          ++v69;
        }
        while ( v69 < *((_DWORD *)this + 3) );
      }
      v71 = (unsigned int)(4 * v68) * (unsigned __int128)4uLL;
      if ( !is_mul_ok((unsigned int)(4 * v68), 4u) )
        *(_QWORD *)&v71 = -1;
      v109 = operator new(v71, *((const struct D3DX9MEMORY::CD3DXNEW **)&v71 + 1));
      if ( v109 )
      {
        v72 = v68 * (unsigned __int128)4uLL;
        if ( !is_mul_ok(v68, 4u) )
          *(_QWORD *)&v72 = -1;
        v110 = (unsigned int *)operator new(v72, *((const struct D3DX9MEMORY::CD3DXNEW **)&v72 + 1));
        if ( v110 )
        {
          memset_0(v109, 0, 4LL * (unsigned int)(4 * v68));
          v73 = 4 * v68;
          v74 = v110;
          memset_0(v110, 0, v73);
          for ( mm = 0; (unsigned int)mm < *((_DWORD *)this + 3); mm = (unsigned int)(mm + 1) )
          {
            v76 = *(_QWORD *)(*((_QWORD *)this + 4) + 8 * mm);
            v77 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * *(unsigned int *)(v76 + 4));
            if ( (*(_DWORD *)(v77 + 8) & 0x100) != 0
              && *(_DWORD *)(v76 + 8) == -1
              && *(_DWORD *)(v76 + 56) == -1
              && (*(_DWORD *)(v77 + 8) & 0x40000) != 0 )
            {
              v78 = 0;
              if ( v67 )
              {
                while ( v110[v78] != *(_DWORD *)(v76 + 12) )
                {
                  v78 = (unsigned int)(v78 + 1);
                  if ( (unsigned int)v78 >= v67 )
                    goto LABEL_178;
                }
              }
              else
              {
LABEL_178:
                if ( (_DWORD)v78 == v67 )
                {
                  ++v67;
                  v110[v78] = *(_DWORD *)(v76 + 12);
                }
              }
              *((_DWORD *)v109 + (unsigned int)(*(_DWORD *)(v76 + 16) + 4 * v78)) = (int)*(double *)(v76 + 32);
            }
          }
          for ( nn = 0; (unsigned int)nn < v67; nn = (unsigned int)(nn + 1) )
          {
            Code = (*(__int64 (__fastcall **)(D3DXShader::CShaderProgram *, _QWORD, __int64))(*(_QWORD *)this + 128LL))(
                     this,
                     v74[nn],
                     (__int64)v109 + 4 * (unsigned int)(4 * nn));
            if ( Code < 0 )
              goto LABEL_243;
            v74 = v110;
          }
          if ( v46 <= *((_DWORD *)this + 23) )
          {
            v80 = 0;
            for ( i1 = 0; (unsigned int)i1 < v23; i1 = (unsigned int)(i1 + 1) )
            {
              v82 = (_DWORD *)*((_QWORD *)Block + i1);
              if ( v82
                && (*v82 & 0x10000000) == 0
                && (*(int (__fastcall **)(D3DXShader::CShaderProgram *, _DWORD *, __int64))(*(_QWORD *)this + 136LL))(
                     this,
                     v82,
                     (__int64)v111 + 4 * i1) < 0 )
              {
                v80 = 1;
              }
            }
            v83 = (*(__int64 (__fastcall **)(D3DXShader::CShaderProgram *))(*(_QWORD *)this + 152LL))(this);
            v22 = v115;
            Code = v83;
            if ( v83 < 0 )
              goto LABEL_241;
            v86 = 0;
            for ( i2 = 1; (unsigned int)v86 < v25; v86 = (unsigned int)(v86 + 1) )
            {
              i4 = *((_QWORD *)v22 + v86);
              if ( i4 )
              {
                v88 = (*(__int64 (__fastcall **)(D3DXShader::CShaderProgram *, __int64, __int64, __int64))(*(_QWORD *)this + 144LL))(
                        this,
                        i4,
                        v85,
                        1);
                i2 = 1;
                if ( v88 < 0 )
                  v80 = 1;
              }
            }
            v89 = v116;
            v90 = 0;
            v2 = v113;
            if ( *((char *)this + 136) >= 0 )
            {
              if ( v24 )
              {
                do
                {
                  i4 = v89[v90];
                  if ( i4 )
                  {
                    v92 = (*(__int64 (__fastcall **)(D3DXShader::CShaderProgram *, __int64, __int64, _QWORD, _QWORD))(*(_QWORD *)this + 216LL))(
                            this,
                            i4,
                            (__int64)v113 + 4 * v90,
                            0,
                            0);
                    i2 = 1;
                    if ( v92 < 0 )
                      v80 = 1;
                  }
                  v90 = (unsigned int)(v90 + 1);
                }
                while ( (unsigned int)v90 < v24 );
              }
            }
            else if ( v24 )
            {
              do
              {
                i4 = v89[v90];
                if ( i4 )
                {
                  v91 = (*(__int64 (__fastcall **)(D3DXShader::CShaderProgram *, __int64, __int64, __int64))(*(_QWORD *)this + 136LL))(
                          this,
                          i4,
                          (__int64)v113 + 4 * v90,
                          1);
                  i2 = 1;
                  if ( v91 < 0 )
                    v80 = 1;
                }
                v90 = (unsigned int)(v90 + 1);
              }
              while ( (unsigned int)v90 < v24 );
            }
            if ( v80 )
            {
              Code = -2147467259;
              goto LABEL_246;
            }
            for ( i3 = 0; i3 < v24; ++i3 )
            {
              v85 = i3;
              v94 = v89[i3];
              if ( v94 )
              {
                for ( i4 = 0; (unsigned int)i4 < i3; i4 = (unsigned int)(i4 + 1) )
                {
                  if ( v89[(unsigned int)i4] && *((_DWORD *)v113 + i3) == *((_DWORD *)v113 + (unsigned int)i4) )
                  {
                    D3DXShader::CProgram::Error(
                      this,
                      *(struct D3DXShader::CNode **)(v94 + 112),
                      0x1198u,
                      "overlapping output semantics");
                    goto LABEL_36;
                  }
                }
              }
            }
            if ( (*((_DWORD *)this + 33) & 0x400000) == 0 )
            {
              Code = D3DXShader::CShaderProgram::Reset(this);
              if ( Code < 0 )
                goto LABEL_241;
            }
            Code = (*(__int64 (__fastcall **)(D3DXShader::CShaderProgram *, __int64, __int64, __int64))(*(_QWORD *)this + 72LL))(
                     this,
                     i4,
                     v85,
                     i2);
            if ( Code < 0 )
              goto LABEL_241;
            if ( *((_QWORD *)this + 34) )
            {
              Code = D3DXShader::CShaderProgram::EmitPreShader(this);
              if ( Code < 0 )
                goto LABEL_241;
            }
            Code = D3DXShader::CShaderProgram::EmitSymbolTable(this);
            if ( Code < 0 )
              goto LABEL_241;
            if ( (*((_BYTE *)this + 244) & 1) != 0 )
            {
              Code = D3DXShader::CShaderProgram::EmitDebugInfo(this);
              if ( Code < 0 )
                goto LABEL_241;
            }
            Code = D3DXShader::CShaderProgram::Emit(this, 0xFFFFu);
            if ( Code < 0 )
              goto LABEL_241;
            Code = D3DXShader::CShaderProgram::ValidateInst(this);
            if ( Code < 0 )
              goto LABEL_241;
            v95 = *((_QWORD *)this + 67);
            if ( v95 )
            {
              if ( !*((_DWORD *)this + 64) )
              {
                Code = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v95 + 40LL))(v95);
                if ( Code < 0 )
                  goto LABEL_241;
              }
            }
            if ( a2 )
            {
              v96 = 4 * *((_DWORD *)this + 90);
              v115 = 0;
              Code = D3DXCore::CBuffer::Create(v96, &v115);
              if ( Code < 0 )
                goto LABEL_241;
              v97 = v115;
              v98 = (const void *)*((_QWORD *)this + 44);
              v99 = 4LL * *((unsigned int *)this + 90);
              v100 = (void *)(*(__int64 (__fastcall **)(struct D3DXCore::CBuffer *))(*(_QWORD *)v115 + 24LL))(v115);
              memcpy_0(v100, v98, v99);
              *a2 = v97;
            }
            Code = 0;
            goto LABEL_241;
          }
          D3DXShader::CProgram::Error(this, 0, 0x119Au, "maximum number of inputs exceeded");
        }
        goto LABEL_35;
      }
    }
LABEL_242:
    Code = -2147024882;
LABEL_243:
    v2 = v113;
    v22 = v115;
    goto LABEL_246;
  }
  Code = -2147024882;
LABEL_245:
  v22 = 0;
LABEL_246:
  operator delete(Block);
  operator delete(v116);
  operator delete(v111);
  operator delete(v2);
  operator delete(0);
  operator delete(v107);
  operator delete(v108);
  operator delete(v22);
  operator delete(v109);
  operator delete(v110);
  operator delete(*((void **)this + 44));
  v101 = (void *)*((_QWORD *)this + 48);
  *((_QWORD *)this + 44) = 0;
  operator delete(v101);
  v102 = *((_QWORD *)this + 67);
  *((_QWORD *)this + 48) = 0;
  if ( v102 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
    *((_QWORD *)this + 67) = 0;
  }
  return (unsigned int)Code;
}

```

## disassembly

```asm
0x140106890  mov     [rsp+arg_8], rdx
0x140106895  push    rbx
0x140106896  push    rbp
0x140106897  push    rsi
0x140106898  push    rdi
0x140106899  push    r12
0x14010689b  push    r13
0x14010689d  push    r14
0x14010689f  push    r15
0x1401068a1  sub     rsp, 78h
0x1401068a5  xor     esi, esi
0x1401068a7  mov     r14, rcx
0x1401068aa  mov     [rcx+150h], rsi
0x1401068b1  mov     [rsp+0B8h+var_78], rsi
0x1401068b6  mov     [rsp+0B8h+var_68], rsi
0x1401068bb  mov     [rsp+0B8h+Block], rsi
0x1401068c0  mov     [rsp+0B8h+arg_18], rsi
0x1401068c8  mov     [rsp+0B8h+arg_10], rsi
0x1401068d0  mov     [rsp+0B8h+var_60], rsi
0x1401068d5  mov     [rsp+0B8h+arg_0], rsi
0x1401068dd  mov     [rsp+0B8h+var_80], rsi
0x1401068e2  mov     [rsp+0B8h+var_70], rsi
0x1401068e7  call    ?GenerateCode@CProgram@D3DXShader@@UEAAJPEAPEAUID3DXBuffer@@@Z; D3DXShader::CProgram::GenerateCode(ID3DXBuffer * *)
0x1401068ec  mov     ebx, eax
0x1401068ee  test    eax, eax
0x1401068f0  js      loc_140107720
0x1401068f6  or      r15d, 0FFFFFFFFh
0x1401068fa  lea     rdx, aI; "i"
0x140106901  mov     r9d, r15d; unsigned int
0x140106904  mov     r8d, 40311h; unsigned int
0x14010690a  mov     rcx, r14; this
0x14010690d  call    ?AddPool@CBaseProgram@D3DXShader@@QEAAIPEBDKII@Z; D3DXShader::CBaseProgram::AddPool(char const *,ulong,uint,uint)
0x140106912  mov     [r14+1E8h], eax
0x140106919  cmp     eax, r15d
0x14010691c  jnz     short loc_140106928
0x14010691e  mov     ebx, 8007000Eh
0x140106923  jmp     loc_140107720
0x140106928  mov     rax, [r14]
0x14010692b  mov     rcx, r14
0x14010692e  mov     rax, [rax+140h]
0x140106935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010693a  test    eax, eax
0x14010693c  js      loc_140106E0F
0x140106942  mov     rcx, [r14+218h]
0x140106949  mov     [r14+160h], rsi
0x140106950  mov     [r14+168h], rsi
0x140106957  mov     [r14+174h], rsi
0x14010695e  test    rcx, rcx
0x140106961  jz      short loc_140106976
0x140106963  mov     rax, [rcx]
0x140106966  mov     rax, [rax+10h]
0x14010696a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010696f  mov     [r14+218h], rsi
0x140106976  test    byte ptr [r14+0F4h], 2
0x14010697e  mov     ebp, 1
0x140106983  jnz     short loc_1401069F5
0x140106985  lea     rcx, aD3d9Dll; "d3d9.dll"
0x14010698c  call    cs:__imp_GetModuleHandleA
0x140106992  test    rax, rax
0x140106995  jnz     short loc_1401069A9
0x140106997  lea     rcx, aD3d9Dll; "d3d9.dll"
0x14010699e  call    cs:__imp_LoadLibraryA
0x1401069a4  test    rax, rax
0x1401069a7  jz      short loc_1401069F5
0x1401069a9  lea     rdx, aDirect3dshader; "Direct3DShaderValidatorCreate9"
0x1401069b0  mov     rcx, rax; hModule
0x1401069b3  call    cs:__imp_GetProcAddress
0x1401069b9  test    rax, rax
0x1401069bc  jz      short loc_1401069F5
0x1401069be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401069c3  mov     [r14+218h], rax
0x1401069ca  mov     rcx, rax
0x1401069cd  test    rax, rax
0x1401069d0  jz      short loc_1401069F5
0x1401069d2  mov     rax, [rax]
0x1401069d5  lea     rdx, ?ValidationError@CShaderProgram@D3DXShader@@KAJPEBDIKI0PEAX@Z; D3DXShader::CShaderProgram::ValidationError(char const *,uint,ulong,uint,char const *,void *)
0x1401069dc  mov     r9d, ebp
0x1401069df  mov     r8, r14
0x1401069e2  mov     rax, [rax+18h]
0x1401069e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401069eb  mov     ebx, eax
0x1401069ed  test    eax, eax
0x1401069ef  js      loc_140107720
0x1401069f5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1401069f9  test    [r14+0F4h], bpl
0x140106a00  jz      short loc_140106A40
0x140106a02  mov     eax, [r14+10h]
0x140106a06  lea     ecx, [rax+rax]
0x140106a09  lea     eax, [r8+21h]
0x140106a0d  mul     rcx
0x140106a10  cmovb   rax, r8
0x140106a14  mov     rcx, rax; unsigned __int64
0x140106a17  call    ??2@YAPEAX_KAEBVCD3DXNEW@D3DX9MEMORY@@@Z; operator new(unsigned __int64,D3DX9MEMORY::CD3DXNEW const &)
0x140106a1c  mov     [r14+180h], rax
0x140106a23  test    rax, rax
0x140106a26  jz      loc_140107701
0x140106a2c  mov     eax, [r14+10h]
0x140106a30  add     eax, eax
0x140106a32  mov     [r14+188h], esi
0x140106a39  mov     [r14+18Ch], eax
0x140106a40  mov     r8d, esi
0x140106a43  mov     [r14+19Ch], r15d
0x140106a4a  mov     [r14+1B0h], esi
0x140106a51  cmp     [r14+0Ch], esi
0x140106a55  jbe     short loc_140106AD6
0x140106a57  mov     rax, [r14+20h]
0x140106a5b  mov     ecx, r8d
0x140106a5e  add     r8d, ebp
0x140106a61  mov     rcx, [rax+rcx*8]
0x140106a65  mov     [rcx+30h], esi
0x140106a68  mov     edx, [r14+0Ch]
0x140106a6c  cmp     r8d, edx
0x140106a6f  jb      short loc_140106A57
0x140106a71  mov     edi, esi
0x140106a73  test    edx, edx
0x140106a75  jz      short loc_140106AD8
0x140106a77  mov     ebx, esi
0x140106a79  mov     rax, [r14+20h]
0x140106a7d  mov     ecx, ebx
0x140106a7f  mov     r9, [rax+rcx*8]
0x140106a83  test    dword ptr [r9], 10000000h
0x140106a8a  jnz     short loc_140106ACC
0x140106a8c  mov     rax, [r14+18h]
0x140106a90  mov     ecx, [r9+4]
0x140106a94  mov     rsi, [rax+rcx*8]
0x140106a98  mov     eax, [rsi+8]
0x140106a9b  and     eax, 210h
0x140106aa0  cmp     eax, 10h
0x140106aa3  jz      short loc_140106AAB
0x140106aa5  test    byte ptr [rsi+8], 20h
0x140106aa9  jz      short loc_140106AC4
0x140106aab  mov     rax, [r14]
0x140106aae  xor     r8d, r8d
0x140106ab1  mov     rdx, r9
0x140106ab4  mov     rcx, r14
0x140106ab7  mov     rax, [rax+8]
0x140106abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140106ac0  mov     edx, [r14+0Ch]
0x140106ac4  test    byte ptr [rsi+8], 80h
0x140106ac8  jz      short loc_140106ACC
0x140106aca  add     edi, ebp
0x140106acc  add     ebx, ebp
0x140106ace  cmp     ebx, edx
0x140106ad0  jb      short loc_140106A79
0x140106ad2  xor     esi, esi
0x140106ad4  jmp     short loc_140106AD8
0x140106ad6  mov     edi, esi
0x140106ad8  mov     r10d, [r14+64h]
0x140106adc  mov     ecx, [r14+0F0h]
0x140106ae3  cmp     edi, r10d
0x140106ae6  jbe     short loc_140106B54
0x140106ae8  xorps   xmm0, xmm0
0x140106aeb  lea     r8, [rsp+0B8h+var_58]
0x140106af0  movups  [rsp+0B8h+var_58], xmm0
0x140106af5  call    D3DXGetTargetDescByVersion
0x140106afa  test    eax, eax
0x140106afc  js      short loc_140106B29
0x140106afe  mov     rax, qword ptr [rsp+0B8h+var_58]
0x140106b03  xor     edx, edx; struct D3DXShader::CNode *
0x140106b05  mov     rcx, r14; this
0x140106b08  test    r10d, r10d
0x140106b0b  jz      short loc_140106B3B
0x140106b0d  mov     dword ptr [rsp+0B8h+var_90], r10d
0x140106b12  lea     r9, aMaximumNumberO; "maximum number of samplers exceeded. %s"...
0x140106b19  mov     r8d, 119Eh; unsigned int
0x140106b1f  mov     qword ptr [rsp+0B8h+var_98], rax
0x140106b24  call    ?Error@CProgram@D3DXShader@@IEAAJPEAVCNode@2@IPEBDZZ; D3DXShader::CProgram::Error(D3DXShader::CNode *,uint,char const *,...)
0x140106b29  mov     rbp, [rsp+0B8h+arg_10]
0x140106b31  mov     ebx, 80004005h
0x140106b36  jmp     loc_1401076F7
0x140106b3b  lea     r9, aSTargetDoesNot; "%s target does not support texture look"...
0x140106b42  mov     qword ptr [rsp+0B8h+var_98], rax
0x140106b47  mov     r8d, 11C1h; unsigned int
0x140106b4d  call    ?Error@CProgram@D3DXShader@@IEAAJPEAVCNode@2@IPEBDZZ; D3DXShader::CProgram::Error(D3DXShader::CNode *,uint,char const *,...)
0x140106b52  jmp     short loc_140106B29
0x140106b54  mov     edi, 0FFFF0000h
0x140106b59  and     ecx, edi
0x140106b5b  cmp     ecx, 0FFFE0000h
0x140106b61  jnz     short loc_140106B93
0x140106b63  mov     r8d, [r14+40h]; unsigned int
0x140106b67  mov     r9d, 10h; unsigned int
0x140106b6d  mov     edx, [r14+98h]; unsigned int
0x140106b74  mov     rcx, r14; this
0x140106b77  mov     [rsp+0B8h+var_90], 76h ; 'v'; char
0x140106b7c  mov     [rsp+0B8h+var_98], 204h; unsigned int
0x140106b84  call    ?CombineConstants@CShaderProgram@D3DXShader@@IEAAJIIKKD@Z; D3DXShader::CShaderProgram::CombineConstants(uint,uint,ulong,ulong,char)
0x140106b89  mov     ebx, eax
0x140106b8b  test    eax, eax
0x140106b8d  js      loc_140107718
0x140106b93  mov     eax, [r14+0F0h]
0x140106b9a  and     eax, edi
0x140106b9c  cmp     eax, edi
0x140106b9e  jnz     short loc_140106BC8
0x140106ba0  mov     r8d, [r14+64h]; unsigned int
0x140106ba4  mov     r9d, 80h; unsigned int
0x140106baa  mov     [rsp+0B8h+var_90], 73h ; 's'; char
0x140106baf  mov     edx, r15d; unsigned int
0x140106bb2  mov     rcx, r14; this
0x140106bb5  mov     [rsp+0B8h+var_98], esi; unsigned int
0x140106bb9  call    ?CombineConstants@CShaderProgram@D3DXShader@@IEAAJIIKKD@Z; D3DXShader::CShaderProgram::CombineConstants(uint,uint,ulong,ulong,char)
0x140106bbe  mov     ebx, eax
0x140106bc0  test    eax, eax
0x140106bc2  js      loc_140107718
0x140106bc8  mov     r15d, esi
0x140106bcb  mov     r12d, esi
0x140106bce  mov     r13d, esi
0x140106bd1  cmp     [r14+0Ch], esi
0x140106bd5  jbe     loc_140106C62
0x140106bdb  mov     r10, [r14+20h]
0x140106bdf  mov     r8d, esi
0x140106be2  mov     r9d, esi
0x140106be5  mov     eax, r8d
0x140106be8  mov     rdx, [r10+rax*8]; struct D3DX9MEMORY::CD3DXNEW *
0x140106bec  test    dword ptr [rdx], 10000000h
0x140106bf2  jnz     short loc_140106C59
0x140106bf4  mov     ecx, [rdx+4]
0x140106bf7  cmp     [r14+0A0h], ecx
0x140106bfe  jnz     short loc_140106C0F
0x140106c00  mov     eax, [rdx+0Ch]
0x140106c03  inc     eax
0x140106c05  cmp     eax, r9d
0x140106c08  jbe     short loc_140106C0F
0x140106c0a  mov     r9d, eax
0x140106c0d  jmp     short loc_140106C59
0x140106c0f  cmp     [r14+98h], ecx
0x140106c16  jnz     short loc_140106C27
0x140106c18  mov     eax, [rdx+0Ch]
0x140106c1b  inc     eax
0x140106c1d  cmp     eax, r15d
0x140106c20  jbe     short loc_140106C27
0x140106c22  mov     r15d, eax
0x140106c25  jmp     short loc_140106C59
0x140106c27  cmp     [r14+9Ch], ecx
0x140106c2e  jnz     short loc_140106C3F
0x140106c30  mov     eax, [rdx+0Ch]
0x140106c33  inc     eax
0x140106c35  cmp     eax, r12d
0x140106c38  jbe     short loc_140106C3F
0x140106c3a  mov     r12d, eax
0x140106c3d  jmp     short loc_140106C59
0x140106c3f  mov     rax, [r14+18h]
0x140106c43  mov     rcx, [rax+rcx*8]
0x140106c47  test    byte ptr [rcx+8], 80h
0x140106c4b  jz      short loc_140106C59
0x140106c4d  mov     eax, [rdx+0Ch]
0x140106c50  inc     eax
0x140106c52  cmp     eax, r13d
0x140106c55  cmova   r13d, eax
0x140106c59  add     r8d, ebp
0x140106c5c  cmp     r8d, [r14+0Ch]
0x140106c60  jb      short loc_140106BE5
0x140106c62  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140106c69  mov     edi, r15d
0x140106c6c  mov     eax, 8
0x140106c71  mul     rdi
0x140106c74  cmovb   rax, rcx
0x140106c78  mov     rcx, rax; unsigned __int64
0x140106c7b  call    ??2@YAPEAX_KAEBVCD3DXNEW@D3DX9MEMORY@@@Z; operator new(unsigned __int64,D3DX9MEMORY::CD3DXNEW const &)
0x140106c80  mov     [rsp+0B8h+Block], rax
0x140106c85  mov     rbp, rax
0x140106c88  test    rax, rax
0x140106c8b  jz      loc_140107701
0x140106c91  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140106c98  mov     ebx, r12d
0x140106c9b  mov     eax, 8
0x140106ca0  mul     rbx
0x140106ca3  cmovb   rax, rcx
0x140106ca7  mov     rcx, rax; unsigned __int64
0x140106caa  call    ??2@YAPEAX_KAEBVCD3DXNEW@D3DX9MEMORY@@@Z; operator new(unsigned __int64,D3DX9MEMORY::CD3DXNEW const &)
0x140106caf  mov     [rsp+0B8h+arg_18], rax
0x140106cb7  test    rax, rax
0x140106cba  jz      loc_140107701
0x140106cc0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140106cc7  mov     esi, r13d
0x140106cca  mov     eax, 8
0x140106ccf  mul     rsi
0x140106cd2  cmovb   rax, rcx
0x140106cd6  mov     rcx, rax; unsigned __int64
0x140106cd9  call    ??2@YAPEAX_KAEBVCD3DXNEW@D3DX9MEMORY@@@Z; operator new(unsigned __int64,D3DX9MEMORY::CD3DXNEW const &)
0x140106cde  mov     [rsp+0B8h+arg_10], rax
0x140106ce6  test    rax, rax
0x140106ce9  jz      loc_140107701
0x140106cef  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140106cf6  mov     eax, 4
0x140106cfb  mul     rdi
0x140106cfe  cmovb   rax, rcx
0x140106d02  mov     rcx, rax; unsigned __int64
0x140106d05  call    ??2@YAPEAX_KAEBVCD3DXNEW@D3DX9MEMORY@@@Z; operator new(unsigned __int64,D3DX9MEMORY::CD3DXNEW const &)
0x140106d0a  mov     [rsp+0B8h+var_60], rax
0x140106d0f  test    rax, rax
0x140106d12  jz      loc_140107701
0x140106d18  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140106d1f  mov     eax, 4
0x140106d24  mul     rbx
0x140106d27  cmovb   rax, rcx
0x140106d2b  mov     rcx, rax; unsigned __int64
0x140106d2e  call    ??2@YAPEAX_KAEBVCD3DXNEW@D3DX9MEMORY@@@Z; operator new(unsigned __int64,D3DX9MEMORY::CD3DXNEW const &)
0x140106d33  mov     [rsp+0B8h+arg_0], rax
0x140106d3b  test    rax, rax
0x140106d3e  jz      loc_140107701
  ... truncated ...
```
