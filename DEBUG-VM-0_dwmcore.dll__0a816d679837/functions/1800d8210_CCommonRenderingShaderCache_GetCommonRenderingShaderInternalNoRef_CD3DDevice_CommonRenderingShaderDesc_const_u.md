# CCommonRenderingShaderCache::GetCommonRenderingShaderInternalNoRef(CD3DDevice *,CommonRenderingShaderDesc const &,uint *,ID3D11PixelShader * *)

- ea: `0x1800d8210`
- end: `0x1800d89a3`
- name: `?GetCommonRenderingShaderInternalNoRef@CCommonRenderingShaderCache@@AEAAJPEAVCD3DDevice@@AEBUCommonRenderingShaderDesc@@PEAIPEAPEAUID3D11PixelShader@@@Z`
- size: `1939`
- prototype: `__int64 __fastcall(CCommonRenderingShaderCache *__hidden this, struct CD3DDevice *, const struct CommonRenderingShaderDesc *, unsigned int *, struct ID3D11PixelShader **)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003743c`
- `0x1800d7640`

## callees

- `0x18000a254`
- `0x180042de0`
- `0x18005d700`
- `0x18005d940`
- `0x180079f2c`
- `0x1800d8210`
- `0x1800d89b0`
- `0x1800d8ed4`
- `0x1800d8f74`
- `0x1800d9310`
- `0x1800d9388`
- `0x1800dcdcc`
- `0x180202b60`
- `0x180228490`
- `0x180229424`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d8700`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d8700`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d8711`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d8711`
- `D3DCOMPILER_47!D3DCreateBlob` at `0x1800d854c`
- `D3DCOMPILER_47!D3DCreateBlob` at `0x1800d854c`

## string_xrefs

- `0x1800d83ae`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800d83f1`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800d85b9`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800d85dc`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800d85ff`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`

## pseudocode

```c
__int64 __fastcall CCommonRenderingShaderCache::GetCommonRenderingShaderInternalNoRef(
        CCommonRenderingShaderCache *this,
        struct CD3DDevice *a2,
        const struct CommonRenderingShaderDesc *a3,
        unsigned int *a4,
        struct ID3D11PixelShader **a5)
{
  int v5; // r14d
  volatile signed __int32 *v6; // rsi
  bool v8; // cc
  char v9; // al
  char v10; // al
  __int128 v11; // xmm0
  unsigned __int8 v12; // r12
  bool v13; // al
  unsigned int v14; // r14d
  unsigned int v15; // r15d
  struct CD3DPixelShader *v16; // r9
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // rdx
  int v20; // edi
  int v21; // edi
  struct CD3DDevice *v22; // r12
  __int64 i; // rdi
  __int64 v24; // rcx
  struct CD3DPixelShader *v25; // rdi
  unsigned int v26; // r14d
  volatile signed __int32 *v28; // rax
  SIZE_T v29; // rdi
  const void *v30; // rsi
  HRESULT v31; // eax
  unsigned int v32; // ebx
  CLinkedShader *v33; // rcx
  int Resource; // eax
  void *v35; // rax
  HANDLE ProcessHeap; // rax
  char *v37; // rax
  ID3DBlob *v38; // rdx
  ID3DBlob **v39; // rcx
  int v40; // ebx
  int v41; // eax
  unsigned int v42; // ebx
  _OWORD *ShaderLinkingBody; // rax
  int LinkedShader; // eax
  unsigned int v45; // ebx
  __int64 v46; // rdx
  int v47; // [rsp+20h] [rbp-E0h]
  struct CD3DPixelShader *v48[2]; // [rsp+30h] [rbp-D0h] BYREF
  ID3DBlob *ppBlob[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct CD3DDevice *v50; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v51; // [rsp+58h] [rbp-A8h]
  struct ID3D11PixelShader **v52; // [rsp+60h] [rbp-A0h]
  _OWORD v53[3]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v54[56]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v55; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v56; // [rsp+E0h] [rbp-20h]
  __int128 v57; // [rsp+F0h] [rbp-10h]
  __int128 v58; // [rsp+100h] [rbp+0h]
  __int128 v59; // [rsp+110h] [rbp+10h]
  __int128 v60; // [rsp+120h] [rbp+20h]
  __int128 v61; // [rsp+130h] [rbp+30h]
  __int128 v62; // [rsp+140h] [rbp+40h]
  int v63; // [rsp+150h] [rbp+50h]
  __int64 v64; // [rsp+154h] [rbp+54h]
  int v65; // [rsp+15Ch] [rbp+5Ch]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v5 = *(_DWORD *)a3;
  v52 = a5;
  v6 = 0;
  v51 = a4;
  v64 = 0;
  v65 = 0;
  v56 = 0;
  *(_DWORD *)((char *)&v56 + 10) = 0;
  HIWORD(v56) = 0;
  v58 = 0;
  *(_DWORD *)((char *)&v58 + 10) = 0;
  HIWORD(v58) = 0;
  v60 = 0;
  *(_DWORD *)((char *)&v60 + 10) = 0;
  HIWORD(v60) = 0;
  v62 = 0;
  *(_DWORD *)((char *)&v62 + 10) = 0;
  HIWORD(v62) = 0;
  v50 = a2;
  BYTE8(v56) = (v5 & 4) != 0;
  v63 = -1;
  *(_DWORD *)((char *)&v64 + 1) = (v5 & 0x10) != 0;
  v8 = *((_DWORD *)a2 + 156) < 37632;
  v57 = 0;
  LOBYTE(v64) = (v5 & 8) != 0;
  v9 = *((_BYTE *)a3 + 28);
  v59 = 0;
  BYTE4(v64) = v9;
  v10 = *((_BYTE *)a3 + 29);
  v61 = 0;
  BYTE5(v64) = v10;
  v11 = *(_OWORD *)((char *)a3 + 8);
  *(_QWORD *)&v57 = "NoOp";
  DWORD2(v57) = 0;
  *(_QWORD *)&v59 = "NoOp";
  DWORD2(v59) = 0;
  *(_QWORD *)&v61 = "NoOp";
  DWORD2(v61) = 0;
  v55 = v11;
  if ( v8 )
  {
    v15 = v5 & 3;
    v14 = v15 | 4;
    v12 = 0;
  }
  else
  {
    v12 = 1;
    v63 = *((_DWORD *)a3 + 6);
    v13 = (v5 & 0x20) != 0;
    v14 = v5 & 3;
    BYTE5(v56) = v13;
    v15 = v14;
  }
  ShaderLinkingConfig::GetLookupKey(&v55, v48, v14);
  v16 = v48[0];
  v17 = 0;
  v18 = qword_1803B99E0;
  while ( 1 )
  {
    if ( v17 >= (int)qword_1803B99E0 )
      goto LABEL_30;
    v19 = v17;
    if ( *(struct CD3DPixelShader **)(g_commonRenderingShaderCache + 16LL * v17) == v48[0]
      && *(_DWORD *)(g_commonRenderingShaderCache + 16LL * v17 + 8) == LODWORD(v48[1]) )
    {
      break;
    }
    ++v17;
  }
  if ( v17 == -1 )
  {
LABEL_30:
    v48[0] = 0;
    v28 = 0;
    goto LABEL_31;
  }
  v6 = *(volatile signed __int32 **)(qword_1803B99D8 + 8LL * v17);
  if ( !v6 )
    goto LABEL_45;
  if ( _InterlockedAdd(v6 + 2, 1u) <= 0 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v47);
  v20 = _InterlockedDecrement(v6 + 2);
  if ( v20 < -1 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v47);
  if ( v20 )
    goto LABEL_45;
  if ( _InterlockedAdd(v6 + 2, 1u) <= 0 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v47);
  (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, struct CD3DPixelShader *))(*(_QWORD *)v6 + 24LL))(
    v6,
    v19,
    v18,
    v16);
  v21 = _InterlockedDecrement(v6 + 2);
  if ( v21 < -1 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v47);
  if ( v21 )
  {
LABEL_45:
    v48[0] = (struct CD3DPixelShader *)v6;
    if ( v6 )
      goto LABEL_23;
    v28 = 0;
LABEL_31:
    if ( *((_DWORD *)a3 + 4) <= 1u && *((_DWORD *)a3 + 6) == -1 && !*((_BYTE *)a3 + 29) )
    {
      switch ( *(_DWORD *)a3 )
      {
        case 5:
          v29 = 856;
          v30 = &unk_1802D5DD0;
LABEL_36:
          v48[0] = 0;
          ppBlob[0] = 0;
          v31 = D3DCreateBlob(v29, ppBlob);
          v32 = v31;
          if ( v31 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v31, 0x47u, 0);
            if ( ppBlob[0] )
              ((void (__fastcall *)(ID3DBlob *))ppBlob[0]->lpVtbl->Release)(ppBlob[0]);
            return v32;
          }
          v35 = (void *)((__int64 (__fastcall *)(ID3DBlob *))ppBlob[0]->lpVtbl->GetBufferPointer)(ppBlob[0]);
          memcpy_0(v35, v30, v29);
          ProcessHeap = GetProcessHeap();
          v37 = (char *)HeapAlloc(ProcessHeap, 0, 0x58u);
          v6 = (volatile signed __int32 *)v37;
          if ( !v37 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x4Du, 0);
            if ( ppBlob[0] )
              ((void (__fastcall *)(ID3DBlob *))ppBlob[0]->lpVtbl->Release)(ppBlob[0]);
            return 2147942414LL;
          }
          v38 = ppBlob[0];
          v39 = (ID3DBlob **)(v37 + 16);
          *((_DWORD *)v37 + 2) = 0;
          v40 = 0;
          if ( BYTE2(v48[0]) )
            v40 = 2;
          *(_QWORD *)v37 = &CLinkedShader::`vftable';
          *v39 = v38;
          Microsoft::WRL::ComPtr<IMessageCallSendHost>::InternalAddRef(v39);
          *((_DWORD *)v6 + 6) = v40;
          *((_QWORD *)v6 + 4) = &CDeviceResourceTable<CD3DPixelShader,CLinkedShader>::`vftable';
          *((_QWORD *)v6 + 5) = v6;
          *((_QWORD *)v6 + 6) = v6 + 18;
          *((_QWORD *)v6 + 7) = v6 + 18;
          *((_QWORD *)v6 + 8) = v6 + 22;
          CMILRefCountImpl::AddReference((CMILRefCountImpl *)(v6 + 2));
          ShaderLinkingConfig::GetLookupKey(&v55, v48, v14);
          v41 = CShaderCache::AddLinkedShader(&g_commonRenderingShaderCache, v48, v6);
          v42 = v41;
          if ( v41 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v41, 0x50u, 0);
            CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>::Release(v6);
            wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(ppBlob);
            return v42;
          }
          v48[0] = (struct CD3DPixelShader *)v6;
          CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>::Release(v6);
          if ( ppBlob[0] )
            ((void (__fastcall *)(ID3DBlob *))ppBlob[0]->lpVtbl->Release)(ppBlob[0]);
          v28 = v6;
          break;
        case 1:
          v29 = 800;
          v30 = &unk_180361D00;
          goto LABEL_36;
        case 2:
          v29 = 824;
          v30 = &unk_180360D90;
          goto LABEL_36;
      }
    }
    if ( !v28 )
    {
      ShaderLinkingBody = (_OWORD *)CommonRenderingShaderBody::GetShaderLinkingBody(v54, v15, v12, v16);
      ppBlob[0] = 0;
      ppBlob[1] = 0;
      v53[0] = *ShaderLinkingBody;
      v53[1] = ShaderLinkingBody[1];
      v53[2] = ShaderLinkingBody[2];
      LinkedShader = CShaderCache::CreateLinkedShader(
                       (unsigned int)&g_commonRenderingShaderCache,
                       v14,
                       (unsigned int)&v55,
                       (unsigned int)v53,
                       (__int64)ppBlob,
                       (__int64)v48);
      v45 = LinkedShader;
      if ( LinkedShader < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, LinkedShader, 0x61u, 0);
        return v45;
      }
      v6 = (volatile signed __int32 *)v48[0];
    }
    goto LABEL_23;
  }
  if ( _InterlockedDecrement(v6 + 2) < -1 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v47);
  (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v6 + 16LL))(v6, 1);
LABEL_23:
  v22 = v50;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v24 = *((_QWORD *)v6 + 6);
    if ( (unsigned int)i >= (unsigned __int64)((*((_QWORD *)v6 + 7) - v24) >> 3) )
      goto LABEL_41;
    if ( v22 == (struct CD3DDevice *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(8 * i + v24) + 40LL))(*(_QWORD *)(8 * i + v24)) )
      break;
  }
  v25 = *(struct CD3DPixelShader **)(8 * i + *((_QWORD *)v6 + 6));
  if ( v25 )
  {
    v26 = 0;
LABEL_28:
    *v51 = *((_DWORD *)v6 + 6);
    *v52 = (struct ID3D11PixelShader *)*((_QWORD *)v25 + 15);
    return v26;
  }
LABEL_41:
  v33 = (CLinkedShader *)*((_QWORD *)v6 + 5);
  v48[0] = 0;
  Resource = CLinkedShader::CreateResource(v33, v22, v48);
  v26 = Resource;
  if ( Resource >= 0 )
  {
    v25 = v48[0];
    (*(void (__fastcall **)(struct CD3DPixelShader *, volatile signed __int32 *))(*(_QWORD *)v48[0] + 72LL))(
      v48[0],
      v6 + 8);
    v46 = (__int64)(*((_QWORD *)v6 + 7) - *((_QWORD *)v6 + 6)) >> 3;
    v48[0] = 0;
    v50 = 0;
    *(_QWORD *)detail::vector_facade<wil::com_ptr_t<CD3DPixelShader,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<CD3DPixelShader,wil::err_returncode_policy>,2,1,detail::liberal_expansion_policy>>::reserve_region(
                 v6 + 12,
                 v46) = v25;
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v50);
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(v48);
    goto LABEL_28;
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, Resource, 0x52u, 0);
  if ( v48[0] )
    (*(void (__fastcall **)(struct CD3DPixelShader *))(*(_QWORD *)v48[0] + 16LL))(v48[0]);
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v26, 0x11u, 0);
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v26, 0x65u, 0);
  return v26;
}

```

## disassembly

```asm
0x1800d8210  push    rbp
0x1800d8212  push    rsi
0x1800d8213  push    r12
0x1800d8215  push    r13
0x1800d8217  push    r14
0x1800d8219  push    r15
0x1800d821b  lea     rbp, [rsp-78h]
0x1800d8220  sub     rsp, 178h
0x1800d8227  mov     rax, cs:__security_cookie
0x1800d822e  xor     rax, rsp
0x1800d8231  mov     [rbp+0A0h+var_40], rax
0x1800d8235  mov     r14d, [r8]
0x1800d8238  lea     rcx, aNoop; "NoOp"
0x1800d823f  mov     rax, [rbp+0A0h+arg_20]
0x1800d8246  xorps   xmm0, xmm0
0x1800d8249  mov     [rsp+1A0h+var_140], rax
0x1800d824e  xor     esi, esi
0x1800d8250  xor     eax, eax
0x1800d8252  mov     [rsp+1A0h+var_148], r9
0x1800d8257  mov     dword ptr [rbp+0A0h+var_46], eax
0x1800d825a  mov     r13, r8
0x1800d825d  mov     [rbp+54h], rax
0x1800d8261  mov     dword ptr [rbp+0A0h+var_46+2], eax
0x1800d8264  movups  [rbp+0A0h+var_C0], xmm0
0x1800d8268  mov     dword ptr [rbp+0A0h+var_C0+0Ah], eax
0x1800d826b  mov     word ptr [rbp+0A0h+var_C0+0Eh], ax
0x1800d826f  movups  [rbp+0A0h+var_A0], xmm0
0x1800d8273  mov     dword ptr [rbp+0A0h+var_A0+0Ah], eax
0x1800d8276  mov     word ptr [rbp+0A0h+var_A0+0Eh], ax
0x1800d827a  movups  [rbp+0A0h+var_80], xmm0
0x1800d827e  mov     dword ptr [rbp+0A0h+var_80+0Ah], eax
0x1800d8281  mov     word ptr [rbp+0A0h+var_80+0Eh], ax
0x1800d8285  movups  [rbp+0A0h+var_60], xmm0
0x1800d8289  mov     dword ptr [rbp+0A0h+var_60+0Ah], eax
0x1800d828c  mov     word ptr [rbp+0A0h+var_60+0Eh], ax
0x1800d8290  mov     eax, r14d
0x1800d8293  shr     eax, 2
0x1800d8296  and     al, 1
0x1800d8298  mov     [rsp+1A0h+var_150], rdx
0x1800d829d  mov     byte ptr [rbp+0A0h+var_C0+8], al
0x1800d82a0  movzx   eax, r14b
0x1800d82a4  shr     al, 4
0x1800d82a7  and     al, 1
0x1800d82a9  mov     [rbp+0A0h+var_50], 0FFFFFFFFh
0x1800d82b0  mov     byte ptr [rbp+0A0h+var_4B], al
0x1800d82b3  movzx   eax, r14b
0x1800d82b7  shr     al, 3
0x1800d82ba  and     al, 1
0x1800d82bc  cmp     dword ptr [rdx+270h], 9300h
0x1800d82c6  movups  [rbp+0A0h+var_B0], xmm0
0x1800d82ca  mov     [rbp+0A0h+var_4C], al
0x1800d82cd  movzx   eax, byte ptr [r8+1Ch]
0x1800d82d2  movups  [rbp+0A0h+var_90], xmm0
0x1800d82d6  mov     byte ptr [rbp+0A0h+var_4B+3], al
0x1800d82d9  movzx   eax, byte ptr [r8+1Dh]
0x1800d82de  movups  [rbp+0A0h+var_70], xmm0
0x1800d82e2  mov     [rbp+0A0h+var_47], al
0x1800d82e5  movups  xmm0, xmmword ptr [r8+8]
0x1800d82ea  mov     qword ptr [rbp+0A0h+var_B0], rcx
0x1800d82ee  mov     dword ptr [rbp+0A0h+var_B0+8], esi
0x1800d82f1  mov     qword ptr [rbp+0A0h+var_90], rcx
0x1800d82f5  mov     dword ptr [rbp+0A0h+var_90+8], esi
0x1800d82f8  mov     qword ptr [rbp+0A0h+var_70], rcx
0x1800d82fc  mov     dword ptr [rbp+0A0h+var_70+8], esi
0x1800d82ff  movaps  [rbp+0A0h+var_D0], xmm0
0x1800d8303  jl      loc_1800D859C
0x1800d8309  mov     eax, [r8+18h]
0x1800d830d  mov     r12b, 1
0x1800d8310  mov     [rbp+0A0h+var_50], eax
0x1800d8313  mov     eax, r14d
0x1800d8316  shr     eax, 5
0x1800d8319  and     al, 1
0x1800d831b  and     r14d, 3
0x1800d831f  mov     byte ptr [rbp+0A0h+var_C0+5], al
0x1800d8322  mov     r15d, r14d
0x1800d8325  mov     r8d, r14d
0x1800d8328  lea     rdx, [rsp+1A0h+var_170]
0x1800d832d  lea     rcx, [rbp+0A0h+var_D0]
0x1800d8331  call    ?GetLookupKey@ShaderLinkingConfig@@QEBA?AULookupKey@1@I@Z; ShaderLinkingConfig::GetLookupKey(uint)
0x1800d8336  mov     r9, [rsp+1A0h+var_170]
0x1800d833b  mov     eax, esi
0x1800d833d  mov     r11d, dword ptr [rsp+1A0h+var_170+8]
0x1800d8342  mov     r8, cs:qword_1803B99E0
0x1800d8349  mov     r10, cs:?g_commonRenderingShaderCache@@3VCCommonRenderingShaderCache@@A; CCommonRenderingShaderCache g_commonRenderingShaderCache
0x1800d8350  mov     [rsp+1A0h+arg_0], rbx
0x1800d8358  mov     [rsp+1A0h+var_30], rdi
0x1800d8360  cmp     eax, r8d
0x1800d8363  jge     loc_1800D84F1
0x1800d8369  movsxd  rdx, eax
0x1800d836c  mov     rcx, rdx
0x1800d836f  add     rcx, rcx
0x1800d8372  cmp     [r10+rcx*8], r9
0x1800d8376  jz      short loc_1800D837C
0x1800d8378  inc     eax
0x1800d837a  jmp     short loc_1800D8360
0x1800d837c  cmp     [r10+rcx*8+8], r11d
0x1800d8381  jnz     short loc_1800D8378
0x1800d8383  cmp     eax, 0FFFFFFFFh
0x1800d8386  jz      loc_1800D84F1
0x1800d838c  mov     rax, cs:qword_1803B99D8
0x1800d8393  mov     rsi, [rax+rdx*8]
0x1800d8397  test    rsi, rsi
0x1800d839a  jz      loc_1800D86C4
0x1800d83a0  lock add dword ptr [rsi+8], 1
0x1800d83a5  jg      short loc_1800D83C5
0x1800d83a7  mov     rcx, [rbp+0A8h]; this
0x1800d83ae  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800d83b5  mov     r9d, 8007029Ch; char *
0x1800d83bb  mov     edx, 18h; void *
0x1800d83c0  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800d83c5  mov     ebx, 0FFFFFFFFh
0x1800d83ca  mov     edi, ebx
0x1800d83cc  lock xadd [rsi+8], edi
0x1800d83d1  dec     edi
0x1800d83d3  cmp     edi, ebx
0x1800d83d5  jl      loc_1800D85B2
0x1800d83db  test    edi, edi
0x1800d83dd  jnz     loc_1800D86C4
0x1800d83e3  lock add dword ptr [rsi+8], 1
0x1800d83e8  jg      short loc_1800D8408
0x1800d83ea  mov     rcx, [rbp+0A8h]; this
0x1800d83f1  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800d83f8  mov     r9d, 8007029Ch; char *
0x1800d83fe  mov     edx, 18h; void *
0x1800d8403  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800d8408  mov     rax, [rsi]
0x1800d840b  mov     rcx, rsi
0x1800d840e  mov     rax, [rax+18h]
0x1800d8412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8417  mov     edi, ebx
0x1800d8419  lock xadd [rsi+8], edi
0x1800d841e  dec     edi
0x1800d8420  cmp     edi, ebx
0x1800d8422  jl      loc_1800D85D5
0x1800d8428  test    edi, edi
0x1800d842a  jnz     loc_1800D86C4
0x1800d8430  lock xadd [rsi+8], ebx
0x1800d8435  dec     ebx
0x1800d8437  cmp     ebx, 0FFFFFFFFh
0x1800d843a  jl      loc_1800D85F8
0x1800d8440  mov     rax, [rsi]
0x1800d8443  mov     edx, 1
0x1800d8448  mov     rcx, rsi
0x1800d844b  mov     rax, [rax+10h]
0x1800d844f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8454  mov     r12, [rsp+1A0h+var_150]
0x1800d8459  xor     edi, edi
0x1800d845b  mov     rcx, [rsi+30h]
0x1800d845f  mov     rax, [rsi+38h]
0x1800d8463  sub     rax, rcx
0x1800d8466  mov     edx, edi
0x1800d8468  sar     rax, 3
0x1800d846c  cmp     rdx, rax
0x1800d846f  jnb     loc_1800D861B
0x1800d8475  lea     r14, ds:0[rdi*8]
0x1800d847d  mov     rcx, [r14+rcx]
0x1800d8481  mov     rax, [rcx]
0x1800d8484  mov     rax, [rax+28h]
0x1800d8488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d848d  cmp     r12, rax
0x1800d8490  jnz     loc_1800D86DA
0x1800d8496  mov     rax, [rsi+30h]
0x1800d849a  mov     rdi, [r14+rax]
0x1800d849e  test    rdi, rdi
0x1800d84a1  jz      loc_1800D861B
0x1800d84a7  xor     r14d, r14d
0x1800d84aa  mov     eax, [rsi+18h]
0x1800d84ad  mov     rcx, [rsp+1A0h+var_148]
0x1800d84b2  mov     [rcx], eax
0x1800d84b4  mov     rcx, [rsp+1A0h+var_140]
0x1800d84b9  mov     rax, [rdi+78h]
0x1800d84bd  mov     [rcx], rax
0x1800d84c0  mov     eax, r14d
0x1800d84c3  mov     rdi, [rsp+1A0h+var_30]
0x1800d84cb  mov     rbx, [rsp+1A0h+arg_0]
0x1800d84d3  mov     rcx, [rbp+0A0h+var_40]
0x1800d84d7  xor     rcx, rsp; StackCookie
0x1800d84da  call    __security_check_cookie
0x1800d84df  add     rsp, 178h
0x1800d84e6  pop     r15
0x1800d84e8  pop     r14
0x1800d84ea  pop     r13
0x1800d84ec  pop     r12
0x1800d84ee  pop     rsi
0x1800d84ef  pop     rbp
0x1800d84f0  retn
0x1800d84f1  mov     [rsp+1A0h+var_170], rsi
0x1800d84f6  xor     eax, eax
0x1800d84f8  cmp     dword ptr [r13+10h], 1
0x1800d84fd  ja      loc_1800D87F6
0x1800d8503  cmp     dword ptr [r13+18h], 0FFFFFFFFh
0x1800d8508  jnz     loc_1800D87F6
0x1800d850e  cmp     byte ptr [r13+1Dh], 0
0x1800d8513  jnz     loc_1800D87F6
0x1800d8519  mov     ecx, [r13+0]
0x1800d851d  cmp     ecx, 5
0x1800d8520  jnz     loc_1800D87E4
0x1800d8526  mov     edi, 358h
0x1800d852b  lea     rsi, unk_1802D5DD0
0x1800d8532  lea     rdx, [rsp+1A0h+ppBlob]; ppBlob
0x1800d8537  mov     [rsp+1A0h+var_170], 0
0x1800d8540  mov     rcx, rdi; Size
0x1800d8543  mov     [rsp+1A0h+ppBlob], 0
0x1800d854c  call    cs:__imp_D3DCreateBlob
0x1800d8552  mov     ebx, eax
0x1800d8554  test    eax, eax
0x1800d8556  jns     loc_1800D86E1
0x1800d855c  mov     [rsp+1A0h+var_178], 0; void *
0x1800d8565  mov     r9d, eax; int
0x1800d8568  xor     r8d, r8d; unsigned int
0x1800d856b  mov     [rsp+1A0h+var_180], 47h ; 'G'; unsigned int
0x1800d8573  xor     edx, edx; int *
0x1800d8575  mov     ecx, 14h; unsigned int
0x1800d857a  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800d857f  mov     rcx, [rsp+1A0h+ppBlob]
0x1800d8584  test    rcx, rcx
0x1800d8587  jz      short loc_1800D8595
0x1800d8589  mov     rax, [rcx]
0x1800d858c  mov     rax, [rax+10h]
0x1800d8590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8595  mov     eax, ebx
0x1800d8597  jmp     loc_1800D84C3
0x1800d859c  mov     r15d, r14d
0x1800d859f  and     r15d, 3
0x1800d85a3  mov     r14d, r15d
0x1800d85a6  or      r14d, 4
0x1800d85aa  xor     r12b, r12b
0x1800d85ad  jmp     loc_1800D8325
0x1800d85b2  mov     rcx, [rbp+0A8h]; this
0x1800d85b9  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800d85c0  mov     r9d, 8007029Ch; char *
0x1800d85c6  mov     edx, 26h ; '&'; void *
0x1800d85cb  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800d85d0  jmp     loc_1800D83DB
0x1800d85d5  mov     rcx, [rbp+0A8h]; this
0x1800d85dc  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800d85e3  mov     r9d, 8007029Ch; char *
0x1800d85e9  mov     edx, 26h ; '&'; void *
0x1800d85ee  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800d85f3  jmp     loc_1800D8428
0x1800d85f8  mov     rcx, [rbp+0A8h]; this
0x1800d85ff  lea     r8, aOnecoreuapWind_58; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800d8606  mov     r9d, 8007029Ch; char *
0x1800d860c  mov     edx, 26h ; '&'; void *
0x1800d8611  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800d8616  jmp     loc_1800D8440
0x1800d861b  mov     rcx, [rsi+28h]; this
0x1800d861f  lea     r8, [rsp+1A0h+var_170]; struct CD3DPixelShader **
0x1800d8624  mov     rdx, r12; struct CD3DDevice *
0x1800d8627  mov     [rsp+1A0h+var_170], 0
0x1800d8630  call    ?CreateResource@CLinkedShader@@QEAAJPEAVCD3DDevice@@PEAPEAVCD3DPixelShader@@@Z; CLinkedShader::CreateResource(CD3DDevice *,CD3DPixelShader * *)
0x1800d8635  mov     r14d, eax
0x1800d8638  test    eax, eax
0x1800d863a  jns     loc_1800D88C0
0x1800d8640  mov     [rsp+1A0h+var_178], 0; void *
0x1800d8649  mov     r9d, eax; int
0x1800d864c  xor     r8d, r8d; unsigned int
0x1800d864f  mov     [rsp+1A0h+var_180], 52h ; 'R'; unsigned int
0x1800d8657  xor     edx, edx; int *
0x1800d8659  mov     ecx, 14h; unsigned int
0x1800d865e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800d8663  mov     rcx, [rsp+1A0h+var_170]
0x1800d8668  test    rcx, rcx
0x1800d866b  jz      short loc_1800D8679
0x1800d866d  mov     rax, [rcx]
0x1800d8670  mov     rax, [rax+10h]
0x1800d8674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8679  mov     [rsp+1A0h+var_178], 0; void *
0x1800d8682  mov     r9d, r14d; int
0x1800d8685  xor     r8d, r8d; unsigned int
0x1800d8688  mov     [rsp+1A0h+var_180], 11h; unsigned int
0x1800d8690  xor     edx, edx; int *
0x1800d8692  mov     ecx, 14h; unsigned int
0x1800d8697  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800d869c  mov     r9d, r14d; int
0x1800d869f  mov     [rsp+1A0h+var_178], 0; void *
0x1800d86a8  xor     r8d, r8d; unsigned int
0x1800d86ab  mov     [rsp+1A0h+var_180], 65h ; 'e'; unsigned int
0x1800d86b3  xor     edx, edx; int *
0x1800d86b5  mov     ecx, 14h; unsigned int
0x1800d86ba  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800d86bf  jmp     loc_1800D84C0
0x1800d86c4  mov     [rsp+1A0h+var_170], rsi
0x1800d86c9  test    rsi, rsi
0x1800d86cc  jnz     loc_1800D8454
0x1800d86d2  mov     rax, rsi
0x1800d86d5  jmp     loc_1800D84F8
0x1800d86da  inc     edi
0x1800d86dc  jmp     loc_1800D845B
0x1800d86e1  mov     rcx, [rsp+1A0h+ppBlob]
0x1800d86e6  mov     rax, [rcx]
0x1800d86e9  mov     rax, [rax+18h]
0x1800d86ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d86f2  mov     r8, rdi; Size
0x1800d86f5  mov     rdx, rsi; Src
0x1800d86f8  mov     rcx, rax; void *
0x1800d86fb  call    memcpy_0
0x1800d8700  call    cs:__imp_GetProcessHeap
0x1800d8706  xor     edx, edx; dwFlags
0x1800d8708  mov     r8d, 58h ; 'X'; dwBytes
  ... truncated ...
```
