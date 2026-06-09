# CDevice::CreateDefaults(ID3DShaderCacheApplication *)

- ea: `0x18008d1ec`
- end: `0x18008d6b9`
- name: `?CreateDefaults@CDevice@@QEAAXPEAUID3DShaderCacheApplication@@@Z`
- size: `1229`
- prototype: `void __fastcall(struct ID3D12Device *this, struct ID3DShaderCacheApplication *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18006f4a0`

## callees

- `0x18000b010`
- `0x18000d770`
- `0x180029b30`
- `0x18003b824`
- `0x180058e9c`
- `0x180059bb0`
- `0x18008d1ec`
- `0x18008d6c0`
- `0x1800bb480`
- `0x1800bc094`
- `0x1800f1028`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008d2a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008d2a9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18008d279`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18008d279`

## string_xrefs

- `0x18008d272`: `dxilconv.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CDevice::CreateDefaults(struct ID3D12Device *this, struct ID3DShaderCacheApplication *a2)
{
  __int64 v3; // rdi
  struct ID3D12Device *v4; // rbx
  const unsigned __int16 *v5; // r9
  int EmptyRootSignature; // eax
  bool v7; // cc
  _OWORD *v8; // rax
  char *v9; // rcx
  struct ID3D12RootSignature *v10; // rbx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  bool v14; // cc
  int v15; // eax
  int v16; // eax
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  struct ID3D12RootSignature *LibraryA; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID v20; // [rsp+48h] [rbp-B8h]
  _BYTE v21[28]; // [rsp+58h] [rbp-A8h] BYREF
  int v22; // [rsp+74h] [rbp-8Ch]
  struct ID3D12RootSignature *v23; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v24; // [rsp+88h] [rbp-78h]
  __int64 v25; // [rsp+90h] [rbp-70h]
  char v26; // [rsp+F8h] [rbp-8h] BYREF
  int v27; // [rsp+244h] [rbp+144h]
  __int64 v28; // [rsp+248h] [rbp+148h]
  __int64 v29; // [rsp+250h] [rbp+150h]
  int v30; // [rsp+258h] [rbp+158h]
  __int64 v31; // [rsp+25Ch] [rbp+15Ch]
  __int64 v32; // [rsp+264h] [rbp+164h]
  __int64 v33; // [rsp+26Ch] [rbp+16Ch]
  int v34; // [rsp+274h] [rbp+174h]
  __int64 v35; // [rsp+278h] [rbp+178h]
  __int16 v36; // [rsp+280h] [rbp+180h]
  __int16 v37; // [rsp+282h] [rbp+182h]
  int v38; // [rsp+284h] [rbp+184h]
  int v39; // [rsp+288h] [rbp+188h]
  int v40; // [rsp+28Ch] [rbp+18Ch]
  __m128i si128; // [rsp+290h] [rbp+190h]
  int v42; // [rsp+2A0h] [rbp+1A0h]
  int v43; // [rsp+2BCh] [rbp+1BCh]
  int v44; // [rsp+2F0h] [rbp+1F0h]
  WCHAR Filename[264]; // [rsp+310h] [rbp+210h] BYREF

  LODWORD(this[1013].lpVtbl) = 1;
  CDevice::CreateDefaultShaderCacheSessions((CDevice *)this, a2);
  v3 = 2;
  if ( SLODWORD(this[70].lpVtbl) > 95 )
  {
    v19 = 1;
    *(_OWORD *)v21 = 0;
    v20 = stru_1802B6388;
    LibraryA = (struct ID3D12RootSignature *)LoadLibraryA("dxilconv.dll");
    memset_0(Filename, 0, 0x208u);
    GetModuleFileNameW((HMODULE)LibraryA, Filename, 0x104u);
    *(_QWORD *)&v21[16] = CShaderCacheAdapter::GetFileUniquenessValue(Filename);
    v4 = this + 94;
    if ( (int)CDevice::CreateShaderCacheSessionImpl(
                (CDevice *)this,
                (const struct D3D12_SHADER_CACHE_SESSION_DESC1 *)&v19,
                D3D12_SHADER_CACHE_KIND_FLAG_IMPLICIT_D3D_CONVERSIONS,
                v5,
                &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
                (void **)&this[94].lpVtbl) >= 0 )
    {
      CLockOwnerChild<CDevice,0>::UCAddUse(&v4->lpVtbl->CreateShaderResourceView);
      (*((void (__fastcall **)(struct ID3D12DeviceVtbl *))v4->lpVtbl->QueryInterface + 2))(v4->lpVtbl);
    }
    D3DXPlat::unique_module::reset((D3DXPlat::unique_module *)&LibraryA, 0);
  }
  if ( LODWORD(this[38].lpVtbl) != 256 )
  {
    LibraryA = 0;
    EmptyRootSignature = MakeEmptyRootSignature(
                           this,
                           (unsigned int)(1LL << ((__int64)(unsigned int)(LODWORD(this[701].lpVtbl)
                                                                        - LODWORD(this[700].lpVtbl)) >> 2))
                         - 1,
                           &LibraryA);
    ThrowFailure(EmptyRootSignature);
    memset_0(&v23, 0, 0x290u);
    v43 = 1;
    v7 = SLODWORD(this[70].lpVtbl) < 96;
    if ( SLODWORD(this[70].lpVtbl) < 96 )
    {
      v24 = qword_1802A3190;
      if ( v7 )
      {
        v25 = 396;
        goto LABEL_11;
      }
    }
    else
    {
      v24 = qword_1802AFCB0;
    }
    v25 = 1304;
LABEL_11:
    v27 = 3;
    v28 = 3;
    v29 = 0;
    v30 = 0;
    v31 = 1;
    v32 = 0;
    v33 = 0;
    v34 = 1;
    v35 = 2;
    v36 = -1;
    v37 = *(_WORD *)&v20.Data4[2];
    v38 = 1;
    v39 = 1;
    v40 = 1;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v42 = 8;
    v8 = (_OWORD *)CD3DX12_BLEND_DESC::CD3DX12_BLEND_DESC(Filename);
    v9 = &v26;
    do
    {
      *(_OWORD *)v9 = *v8;
      *((_OWORD *)v9 + 1) = v8[1];
      *((_OWORD *)v9 + 2) = v8[2];
      *((_OWORD *)v9 + 3) = v8[3];
      *((_OWORD *)v9 + 4) = v8[4];
      *((_OWORD *)v9 + 5) = v8[5];
      *((_OWORD *)v9 + 6) = v8[6];
      *((_OWORD *)v9 + 7) = v8[7];
      v9 += 128;
      v8 += 8;
      --v3;
    }
    while ( v3 );
    *(_OWORD *)v9 = *v8;
    *((_OWORD *)v9 + 1) = v8[1];
    *((_OWORD *)v9 + 2) = v8[2];
    *((_OWORD *)v9 + 3) = v8[3];
    *((_QWORD *)v9 + 8) = *((_QWORD *)v8 + 8);
    v10 = LibraryA;
    v23 = LibraryA;
    v44 = (1LL << ((__int64)(unsigned int)(LODWORD(this[701].lpVtbl) - LODWORD(this[700].lpVtbl)) >> 2)) - 1;
    v11 = 0;
    v17 = 0;
    if ( LODWORD(this[38].lpVtbl) != 4096 )
    {
      v12 = (*((__int64 (__fastcall **)(struct ID3D12DeviceVtbl *, struct ID3D12RootSignature **, GUID *, __int64 *))this[96].lpVtbl->QueryInterface
             + 10))(
              this[96].lpVtbl,
              &v23,
              &GUID_765a30f3_f624_4c6f_a828_ace948622445,
              &v17);
      ThrowFailure(v12);
      v13 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ID3D12Device *))v17)(
              v17,
              &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
              this + 90);
      ThrowFailure(v13);
      CLockOwnerChild<CDevice,0>::UCAddUse(&this[90].lpVtbl->CreateShaderResourceView);
      (*((void (__fastcall **)(struct ID3D12DeviceVtbl *))this[90].lpVtbl->QueryInterface + 2))(this[90].lpVtbl);
      v11 = v17;
    }
    memset(&v21[4], 0, 24);
    v22 = 0;
    v14 = SLODWORD(this[70].lpVtbl) < 96;
    if ( SLODWORD(this[70].lpVtbl) < 96 )
    {
      *(_QWORD *)&v20.Data1 = qword_1802A3000;
      if ( v14 )
      {
        *(_QWORD *)v20.Data4 = 396;
        goto LABEL_20;
      }
    }
    else
    {
      *(_QWORD *)&v20.Data1 = qword_1802B01D0;
    }
    *(_QWORD *)v20.Data4 = 1020;
LABEL_20:
    v19 = (__int64)v10;
    *(_DWORD *)v21 = (1LL << ((__int64)(unsigned int)(LODWORD(this[701].lpVtbl) - LODWORD(this[700].lpVtbl)) >> 2)) - 1;
    if ( v11 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      v17 = 0;
    }
    v15 = (*((__int64 (__fastcall **)(struct ID3D12DeviceVtbl *, __int64 *, GUID *, __int64 *))this[96].lpVtbl->QueryInterface
           + 11))(
            this[96].lpVtbl,
            &v19,
            &GUID_765a30f3_f624_4c6f_a828_ace948622445,
            &v17);
    ThrowFailure(v15);
    v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ID3D12Device *))v17)(
            v17,
            &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
            this + 91);
    ThrowFailure(v16);
    CLockOwnerChild<CDevice,0>::UCAddUse(&this[91].lpVtbl->CreateShaderResourceView);
    (*((void (__fastcall **)(struct ID3D12DeviceVtbl *))this[91].lpVtbl->QueryInterface + 2))(this[91].lpVtbl);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v10 )
      v10->Release(v10);
  }
  LODWORD(this[1013].lpVtbl) = 0;
  LOBYTE(this[1028].lpVtbl) = 0;
}

```

## disassembly

```asm
0x18008d1ec  mov     [rsp-8+arg_10], rbx
0x18008d1f1  push    rbp
0x18008d1f2  push    rsi
0x18008d1f3  push    rdi
0x18008d1f4  push    r12
0x18008d1f6  push    r13
0x18008d1f8  push    r14
0x18008d1fa  push    r15
0x18008d1fc  lea     rbp, [rsp-430h]
0x18008d204  sub     rsp, 530h
0x18008d20b  mov     rax, cs:__security_cookie
0x18008d212  xor     rax, rsp
0x18008d215  mov     [rbp+460h+var_40], rax
0x18008d21c  mov     rsi, rcx
0x18008d21f  mov     r15d, 1
0x18008d225  mov     [rcx+1FA8h], r15d
0x18008d22c  call    ?CreateDefaultShaderCacheSessions@CDevice@@QEAAXPEAUID3DShaderCacheApplication@@@Z; CDevice::CreateDefaultShaderCacheSessions(ID3DShaderCacheApplication *)
0x18008d231  xor     r14d, r14d
0x18008d234  lea     r12, _GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae
0x18008d23b  lea     edi, [r15+1]
0x18008d23f  mov     r13d, 90h
0x18008d245  cmp     dword ptr [rsi+230h], 5Fh ; '_'
0x18008d24c  jle     loc_18008D30C
0x18008d252  mov     [rsp+560h+var_520], r15
0x18008d257  xorps   xmm0, xmm0
0x18008d25a  movdqu  [rsp+560h+var_508], xmm0
0x18008d260  mov     [rsp+560h+var_4F8], r14
0x18008d265  movups  xmm0, xmmword ptr cs:stru_1802B6388.Data1
0x18008d26c  movdqu  [rsp+560h+var_518], xmm0
0x18008d272  lea     rcx, aDxilconvDll_0; "dxilconv.dll"
0x18008d279  call    cs:__imp_LoadLibraryA
0x18008d27f  mov     rbx, rax
0x18008d282  mov     [rsp+560h+var_528], rax
0x18008d287  xor     edx, edx; Val
0x18008d289  mov     r8d, 208h; Size
0x18008d28f  lea     rcx, [rbp+460h+Filename]; void *
0x18008d296  call    memset_0
0x18008d29b  lea     r8d, [r13+74h]; nSize
0x18008d29f  lea     rdx, [rbp+460h+Filename]; lpFilename
0x18008d2a6  mov     rcx, rbx; hModule
0x18008d2a9  call    cs:__imp_GetModuleFileNameW
0x18008d2af  lea     rcx, [rbp+460h+Filename]; lpwstrFilename
0x18008d2b6  call    ?GetFileUniquenessValue@CShaderCacheAdapter@@SA_KPEBG@Z; CShaderCacheAdapter::GetFileUniquenessValue(ushort const *)
0x18008d2bb  mov     [rsp+560h+var_4F8], rax
0x18008d2c0  lea     rbx, [rsi+2F0h]
0x18008d2c7  mov     [rsp+560h+var_538], rbx; void **
0x18008d2cc  mov     [rsp+560h+var_540], r12; struct _GUID *
0x18008d2d1  mov     r8d, edi; enum D3D12_SHADER_CACHE_KIND_FLAGS
0x18008d2d4  lea     rdx, [rsp+560h+var_520]; struct D3D12_SHADER_CACHE_SESSION_DESC1 *
0x18008d2d9  mov     rcx, rsi; this
0x18008d2dc  call    ?CreateShaderCacheSessionImpl@CDevice@@QEAAJPEBUD3D12_SHADER_CACHE_SESSION_DESC1@@W4D3D12_SHADER_CACHE_KIND_FLAGS@@PEBGAEBU_GUID@@PEAPEAX@Z; CDevice::CreateShaderCacheSessionImpl(D3D12_SHADER_CACHE_SESSION_DESC1 const *,D3D12_SHADER_CACHE_KIND_FLAGS,ushort const *,_GUID const &,void * *)
0x18008d2e1  test    eax, eax
0x18008d2e3  js      short loc_18008D300
0x18008d2e5  mov     rcx, [rbx]
0x18008d2e8  add     rcx, r13
0x18008d2eb  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x18008d2f0  mov     rcx, [rbx]
0x18008d2f3  mov     rax, [rcx]
0x18008d2f6  mov     rax, [rax+10h]
0x18008d2fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d2ff  nop
0x18008d300  xor     edx, edx; HINSTANCE
0x18008d302  lea     rcx, [rsp+560h+var_528]; this
0x18008d307  call    ?reset@unique_module@D3DXPlat@@QEAAXPEAUHINSTANCE__@@@Z; D3DXPlat::unique_module::reset(HINSTANCE__ *)
0x18008d30c  cmp     dword ptr [rsi+130h], 100h
0x18008d316  jz      loc_18008D681
0x18008d31c  mov     [rsp+560h+var_528], r14
0x18008d321  mov     ecx, [rsi+15E8h]
0x18008d327  sub     ecx, [rsi+15E0h]
0x18008d32d  sar     rcx, 2
0x18008d331  mov     rdx, r15
0x18008d334  shl     rdx, cl
0x18008d337  sub     edx, r15d; unsigned int
0x18008d33a  lea     r8, [rsp+560h+var_528]; struct ID3D12RootSignature **
0x18008d33f  mov     rcx, rsi; struct ID3D12Device *
0x18008d342  call    ?MakeEmptyRootSignature@@YAJPEAUID3D12Device@@IPEAPEAUID3D12RootSignature@@@Z; MakeEmptyRootSignature(ID3D12Device *,uint,ID3D12RootSignature * *)
0x18008d347  mov     ecx, eax; int
0x18008d349  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18008d34e  xor     edx, edx; Val
0x18008d350  mov     r8d, 290h; Size
0x18008d356  lea     rcx, [rbp+460h+var_4E0]; void *
0x18008d35a  call    memset_0
0x18008d35f  mov     [rbp+460h+var_2A4], r15d
0x18008d366  mov     r12d, 18Ch
0x18008d36c  cmp     dword ptr [rsi+230h], 60h ; '`'
0x18008d373  jl      short loc_18008D382
0x18008d375  lea     rax, qword_1802AFCB0
0x18008d37c  mov     [rbp+460h+var_4D8], rax
0x18008d380  jmp     short loc_18008D38F
0x18008d382  lea     rcx, qword_1802A3190
0x18008d389  mov     [rbp+460h+var_4D8], rcx
0x18008d38d  jl      short loc_18008D399
0x18008d38f  mov     [rbp+460h+var_4D0], 518h
0x18008d397  jmp     short loc_18008D39D
0x18008d399  mov     [rbp+460h+var_4D0], r12
0x18008d39d  mov     eax, 3
0x18008d3a2  mov     [rbp+460h+var_31C], eax
0x18008d3a8  mov     [rbp+460h+var_318], rax
0x18008d3af  mov     [rbp+460h+var_310], r14
0x18008d3b6  mov     [rbp+460h+var_308], 0
0x18008d3c0  mov     [rbp+460h+var_304], 1
0x18008d3cb  mov     [rbp+460h+var_2FC], r14
0x18008d3d2  mov     [rbp+460h+var_2F4], r14
0x18008d3d9  mov     [rbp+460h+var_2EC], r15d
0x18008d3e0  mov     [rbp+460h+var_2E8], 2
0x18008d3eb  mov     [rbp+460h+var_2E0], 0FFFFh
0x18008d3f4  movzx   eax, word ptr [rsp+560h+var_518+0Ah]
0x18008d3f9  mov     [rbp+460h+var_2DE], ax
0x18008d400  mov     [rbp+460h+var_2DC], r15d
0x18008d407  mov     [rbp+460h+var_2D8], r15d
0x18008d40e  mov     [rbp+460h+var_2D4], r15d
0x18008d415  movdqa  xmm0, cs:__xmm@00000001000000010000000100000008
0x18008d41d  movdqa  [rbp+460h+var_2D0], xmm0
0x18008d425  mov     [rbp+460h+var_2C0], 8
0x18008d42f  lea     rcx, [rbp+460h+Filename]
0x18008d436  call    ??0CD3DX12_BLEND_DESC@@QEAA@UCD3DX12_DEFAULT@@@Z; CD3DX12_BLEND_DESC::CD3DX12_BLEND_DESC(CD3DX12_DEFAULT)
0x18008d43b  lea     rcx, [rbp+460h+var_468]
0x18008d43f  mov     edx, 80h
0x18008d444  movups  xmm0, xmmword ptr [rax]
0x18008d447  movups  xmmword ptr [rcx], xmm0
0x18008d44a  movups  xmm1, xmmword ptr [rax+10h]
0x18008d44e  movups  xmmword ptr [rcx+10h], xmm1
0x18008d452  movups  xmm0, xmmword ptr [rax+20h]
0x18008d456  movups  xmmword ptr [rcx+20h], xmm0
0x18008d45a  movups  xmm1, xmmword ptr [rax+30h]
0x18008d45e  movups  xmmword ptr [rcx+30h], xmm1
0x18008d462  movups  xmm0, xmmword ptr [rax+40h]
0x18008d466  movups  xmmword ptr [rcx+40h], xmm0
0x18008d46a  movups  xmm1, xmmword ptr [rax+50h]
0x18008d46e  movups  xmmword ptr [rcx+50h], xmm1
0x18008d472  movups  xmm0, xmmword ptr [rax+60h]
0x18008d476  movups  xmmword ptr [rcx+60h], xmm0
0x18008d47a  movups  xmm1, xmmword ptr [rax+70h]
0x18008d47e  movups  xmmword ptr [rcx+70h], xmm1
0x18008d482  add     rcx, rdx
0x18008d485  add     rax, rdx
0x18008d488  sub     rdi, 1
0x18008d48c  jnz     short loc_18008D444
0x18008d48e  movups  xmm0, xmmword ptr [rax]
0x18008d491  movups  xmmword ptr [rcx], xmm0
0x18008d494  movups  xmm1, xmmword ptr [rax+10h]
0x18008d498  movups  xmmword ptr [rcx+10h], xmm1
0x18008d49c  movups  xmm0, xmmword ptr [rax+20h]
0x18008d4a0  movups  xmmword ptr [rcx+20h], xmm0
0x18008d4a4  movups  xmm1, xmmword ptr [rax+30h]
0x18008d4a8  movups  xmmword ptr [rcx+30h], xmm1
0x18008d4ac  mov     rax, [rax+40h]
0x18008d4b0  mov     [rcx+40h], rax
0x18008d4b4  mov     rbx, [rsp+560h+var_528]
0x18008d4b9  mov     [rbp+460h+var_4E0], rbx
0x18008d4bd  mov     ecx, [rsi+15E8h]
0x18008d4c3  sub     ecx, [rsi+15E0h]
0x18008d4c9  sar     rcx, 2
0x18008d4cd  mov     rax, r15
0x18008d4d0  shl     rax, cl
0x18008d4d3  sub     eax, r15d
0x18008d4d6  mov     [rbp+460h+var_270], eax
0x18008d4dc  mov     rax, r14
0x18008d4df  mov     [rsp+560h+var_530], rax
0x18008d4e4  cmp     dword ptr [rsi+130h], 1000h
0x18008d4ee  jz      short loc_18008D561
0x18008d4f0  mov     rcx, [rsi+300h]
0x18008d4f7  mov     rax, [rcx]
0x18008d4fa  lea     r9, [rsp+560h+var_530]
0x18008d4ff  lea     r8, _GUID_765a30f3_f624_4c6f_a828_ace948622445
0x18008d506  lea     rdx, [rbp+460h+var_4E0]
0x18008d50a  mov     rax, [rax+50h]
0x18008d50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d513  mov     ecx, eax; int
0x18008d515  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18008d51a  mov     rcx, [rsp+560h+var_530]
0x18008d51f  lea     rdi, [rsi+2D0h]
0x18008d526  mov     rax, [rcx]
0x18008d529  mov     r8, rdi
0x18008d52c  lea     rdx, _GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae
0x18008d533  mov     rax, [rax]
0x18008d536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d53b  mov     ecx, eax; int
0x18008d53d  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18008d542  mov     rcx, [rdi]
0x18008d545  add     rcx, r13
0x18008d548  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x18008d54d  mov     rcx, [rdi]
0x18008d550  mov     rax, [rcx]
0x18008d553  mov     rax, [rax+10h]
0x18008d557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d55c  mov     rax, [rsp+560h+var_530]
0x18008d561  xorps   xmm0, xmm0
0x18008d564  movdqu  [rsp+560h+var_508+4], xmm0
0x18008d56a  mov     [rsp+560h+var_4F8+4], r14
0x18008d56f  mov     [rsp+560h+var_4EC], r14d
0x18008d574  cmp     dword ptr [rsi+230h], 60h ; '`'
0x18008d57b  jl      short loc_18008D58B
0x18008d57d  lea     rcx, qword_1802B01D0
0x18008d584  mov     qword ptr [rsp+560h+var_518], rcx
0x18008d589  jmp     short loc_18008D599
0x18008d58b  lea     rdx, qword_1802A3000
0x18008d592  mov     qword ptr [rsp+560h+var_518], rdx
0x18008d597  jl      short loc_18008D5A4
0x18008d599  mov     qword ptr [rsp+560h+var_518+8], 3FCh
0x18008d5a2  jmp     short loc_18008D5A9
0x18008d5a4  mov     qword ptr [rsp+560h+var_518+8], r12
0x18008d5a9  mov     [rsp+560h+var_520], rbx
0x18008d5ae  mov     ecx, [rsi+15E8h]
0x18008d5b4  sub     ecx, [rsi+15E0h]
0x18008d5ba  sar     rcx, 2
0x18008d5be  mov     rdx, r15
0x18008d5c1  shl     rdx, cl
0x18008d5c4  sub     edx, r15d
0x18008d5c7  mov     dword ptr [rsp+560h+var_508], edx
0x18008d5cb  test    rax, rax
0x18008d5ce  jz      short loc_18008D5E7
0x18008d5d0  mov     rcx, [rax]
0x18008d5d3  mov     rdx, [rcx+10h]
0x18008d5d7  mov     rcx, rax
0x18008d5da  mov     rax, rdx
0x18008d5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d5e2  mov     [rsp+560h+var_530], r14
0x18008d5e7  mov     rcx, [rsi+300h]
0x18008d5ee  mov     rax, [rcx]
0x18008d5f1  lea     r9, [rsp+560h+var_530]
0x18008d5f6  lea     r8, _GUID_765a30f3_f624_4c6f_a828_ace948622445
0x18008d5fd  lea     rdx, [rsp+560h+var_520]
0x18008d602  mov     rax, [rax+58h]
0x18008d606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d60b  mov     ecx, eax; int
0x18008d60d  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18008d612  mov     rcx, [rsp+560h+var_530]
0x18008d617  lea     rdi, [rsi+2D8h]
0x18008d61e  mov     rax, [rcx]
0x18008d621  mov     r8, rdi
0x18008d624  lea     rdx, _GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae
0x18008d62b  mov     rax, [rax]
0x18008d62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d633  mov     ecx, eax; int
0x18008d635  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18008d63a  mov     rcx, [rdi]
0x18008d63d  add     rcx, r13
0x18008d640  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x18008d645  mov     rcx, [rdi]
0x18008d648  mov     rax, [rcx]
0x18008d64b  mov     rax, [rax+10h]
0x18008d64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d654  nop
0x18008d655  mov     rcx, [rsp+560h+var_530]
0x18008d65a  test    rcx, rcx
0x18008d65d  jz      short loc_18008D66C
0x18008d65f  mov     rax, [rcx]
0x18008d662  mov     rax, [rax+10h]
0x18008d666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d66b  nop
0x18008d66c  test    rbx, rbx
0x18008d66f  jz      short loc_18008D681
0x18008d671  mov     rax, [rbx]
0x18008d674  mov     rcx, rbx
0x18008d677  mov     rax, [rax+10h]
0x18008d67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d680  nop
0x18008d681  mov     [rsi+1FA8h], r14d
0x18008d688  mov     [rsi+2020h], r14b
0x18008d68f  mov     rcx, [rbp+460h+var_40]
0x18008d696  xor     rcx, rsp; StackCookie
0x18008d699  call    __security_check_cookie
0x18008d69e  mov     rbx, [rsp+560h+arg_10]
0x18008d6a6  add     rsp, 530h
0x18008d6ad  pop     r15
0x18008d6af  pop     r14
0x18008d6b1  pop     r13
0x18008d6b3  pop     r12
0x18008d6b5  pop     rdi
0x18008d6b6  pop     rsi
0x18008d6b7  pop     rbp
0x18008d6b8  retn
```
