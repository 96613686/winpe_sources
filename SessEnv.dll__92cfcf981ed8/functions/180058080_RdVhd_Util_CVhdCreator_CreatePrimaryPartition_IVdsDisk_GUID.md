# RdVhd::Util::CVhdCreator::CreatePrimaryPartition(IVdsDisk *,_GUID *)

- ea: `0x180058080`
- end: `0x1800585bc`
- name: `?CreatePrimaryPartition@CVhdCreator@Util@RdVhd@@QEAAJPEAUIVdsDisk@@PEAU_GUID@@@Z`
- size: `1340`
- prototype: `__int64 __fastcall(RdVhd::Util::CVhdCreator *this, struct IVdsDisk *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180051560`

## callees

- `0x180012d7c`
- `0x18001a280`
- `0x18001ad5c`
- `0x180032ae8`
- `0x1800488e4`
- `0x180048b28`
- `0x180058080`
- `0x180058dcc`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005852d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005853c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005854b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005855a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005856c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005857e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005852d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005853c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005854b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005855a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005856c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005857e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18005831d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18005831d`

## pseudocode

```c
__int64 __fastcall RdVhd::Util::CVhdCreator::CreatePrimaryPartition(
        RdVhd::Util::CVhdCreator *this,
        struct IVdsDisk *a2,
        struct _GUID *a3)
{
  RdVhd::Uvhd::CUvhdDiskManager *v5; // rcx
  __int64 v6; // rdx
  const wchar_t *v7; // r9
  HRESULT LargestFreeExtent; // ebx
  RdVhd::Util::CVhdCreator *v9; // rcx
  RdVhd::Uvhd::CUvhdDiskManager *v10; // rcx
  __int64 v11; // rdx
  struct IUnknown *v12; // rdx
  int i; // ecx
  IUnknown *pProxy; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+4Ch] [rbp-B4h] BYREF
  struct IUnknown *v18; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v22[2]; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+90h] [rbp-70h] BYREF
  __int16 v24; // [rsp+98h] [rbp-68h]
  _BYTE v25[68]; // [rsp+110h] [rbp+10h] BYREF
  int v26; // [rsp+154h] [rbp+54h]
  LPVOID v27; // [rsp+168h] [rbp+68h]
  LPVOID v28; // [rsp+170h] [rbp+70h]
  LPVOID v29; // [rsp+178h] [rbp+78h]
  LPVOID v30; // [rsp+180h] [rbp+80h]
  LPVOID v31; // [rsp+188h] [rbp+88h]

  v16 = 0;
  pProxy = 0;
  v18 = 0;
  memset(v22, 0, sizeof(v22));
  memset_0(v25, 0, 0x80u);
  memset_0(&v23, 0, 0x78u);
  pv = 0;
  v17 = 0;
  v21 = 0;
  v20 = 0;
  if ( !a2 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 98;
    v7 = L"pDisk";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v5 + 2), v6, WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids, v7);
LABEL_7:
    LargestFreeExtent = -2147024809;
    goto LABEL_66;
  }
  if ( !a3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 99;
    v7 = L"pguidVolume";
    goto LABEL_6;
  }
  LargestFreeExtent = ((__int64 (__fastcall *)(struct IVdsDisk *, _BYTE *))a2->lpVtbl->GetProperties)(a2, v25);
  if ( LargestFreeExtent < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v11 = 100;
    goto LABEL_18;
  }
  if ( v26 != 1 )
  {
    LargestFreeExtent = -2147467259;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v11 = 101;
    goto LABEL_18;
  }
  v23 = 1;
  v24 = 6;
  LargestFreeExtent = RdVhd::Util::CVhdCreator::FindLargestFreeExtent(v9, a2, &v21, &v20);
  if ( LargestFreeExtent < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v11 = 102;
    goto LABEL_18;
  }
  LargestFreeExtent = ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, IUnknown **))a2->lpVtbl->QueryInterface)(
                        a2,
                        &IID_IVdsCreatePartitionEx,
                        &pProxy);
  if ( LargestFreeExtent < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v11 = 103;
    goto LABEL_18;
  }
  LargestFreeExtent = CoSetProxyBlanket(pProxy, 0xAu, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 6u, 3u, 0, 0x40u);
  if ( LargestFreeExtent < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v11 = 104;
    goto LABEL_18;
  }
  if ( v18 )
    ATL::AtlComPtrAssign(&v18, v12);
  LargestFreeExtent = ((__int64 (__fastcall *)(IUnknown *, unsigned __int64, unsigned __int64, _QWORD, int *, struct IUnknown **))pProxy->lpVtbl[1].QueryInterface)(
                        pProxy,
                        v21,
                        v20,
                        0,
                        &v23,
                        &v18);
  if ( LargestFreeExtent < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v11 = 105;
    goto LABEL_18;
  }
  LargestFreeExtent = ((__int64 (__fastcall *)(struct IUnknown *, int *, _OWORD *))v18->lpVtbl[1].AddRef)(
                        v18,
                        &v16,
                        v22);
  if ( LargestFreeExtent < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v11 = 106;
    goto LABEL_18;
  }
  LargestFreeExtent = v16;
  if ( v16 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v11 = 107;
    goto LABEL_18;
  }
  LargestFreeExtent = ((__int64 (__fastcall *)(struct IVdsDisk *, LPVOID *, int *))a2->lpVtbl->QueryExtents)(
                        a2,
                        &pv,
                        &v17);
  if ( LargestFreeExtent < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v11 = 108;
LABEL_18:
    WPP_SF_d(
      *((_QWORD *)v10 + 2),
      v11,
      WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids,
      (unsigned int)LargestFreeExtent);
    goto LABEL_66;
  }
  for ( i = 0; i < v17; ++i )
  {
    if ( *((_QWORD *)pv + 10 * i + 3) == *((_QWORD *)&v22[0] + 1) )
    {
      *a3 = *(struct _GUID *)((char *)pv + 80 * i + 40);
      break;
    }
  }
LABEL_66:
  if ( (LODWORD(v22[0]) == 1
     || LODWORD(v22[0]) == 5
     || LODWORD(v22[0]) == 50
     || LODWORD(v22[0]) == 62
     || LODWORD(v22[0]) == 63
     || LODWORD(v22[0]) == 200)
    && *((_QWORD *)&v22[0] + 1) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22[0] + 1) + 16LL))(*((_QWORD *)&v22[0] + 1));
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v27 )
    CoTaskMemFree(v27);
  if ( v28 )
    CoTaskMemFree(v28);
  if ( v29 )
    CoTaskMemFree(v29);
  if ( v30 )
    CoTaskMemFree(v30);
  if ( v31 )
    CoTaskMemFree(v31);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v18);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pProxy);
  return (unsigned int)LargestFreeExtent;
}

```

## disassembly

```asm
0x180058080  mov     [rsp-8+arg_0], rbx
0x180058085  push    rbp
0x180058086  push    rsi
0x180058087  push    rdi
0x180058088  lea     rbp, [rsp-0A0h]
0x180058090  sub     rsp, 1A0h
0x180058097  mov     rax, cs:__security_cookie
0x18005809e  xor     rax, rsp
0x1800580a1  mov     [rbp+0B0h+var_20], rax
0x1800580a8  xorps   xmm0, xmm0
0x1800580ab  mov     [rsp+1B0h+var_168], 0
0x1800580b3  mov     rsi, r8
0x1800580b6  mov     [rsp+1B0h+pProxy], 0
0x1800580bf  mov     rdi, rdx
0x1800580c2  mov     [rsp+1B0h+var_160], 0
0x1800580cb  xor     edx, edx; Val
0x1800580cd  lea     rcx, [rbp+0B0h+var_A0]; void *
0x1800580d1  mov     r8d, 80h; Size
0x1800580d7  movups  [rsp+1B0h+var_140], xmm0
0x1800580dc  movups  [rbp+0B0h+var_130], xmm0
0x1800580e0  call    memset_0
0x1800580e5  xor     edx, edx; Val
0x1800580e7  lea     rcx, [rbp+0B0h+var_120]; void *
0x1800580eb  lea     r8d, [rdx+78h]; Size
0x1800580ef  call    memset_0
0x1800580f4  mov     [rsp+1B0h+pv], 0
0x1800580fd  mov     [rsp+1B0h+var_164], 0
0x180058105  mov     [rsp+1B0h+var_148], 0
0x18005810e  mov     [rsp+1B0h+var_150], 0
0x180058117  test    rdi, rdi
0x18005811a  jnz     short loc_18005815F
0x18005811c  mov     rcx, cs:WPP_GLOBAL_Control
0x180058123  lea     rax, WPP_GLOBAL_Control
0x18005812a  cmp     rcx, rax
0x18005812d  jz      short loc_180058155
0x18005812f  test    byte ptr [rcx+1Ch], 2
0x180058133  jz      short loc_180058155
0x180058135  cmp     byte ptr [rcx+19h], 2
0x180058139  jb      short loc_180058155
0x18005813b  lea     edx, [rdi+62h]
0x18005813e  lea     r9, aPdisk; "pDisk"
0x180058145  mov     rcx, [rcx+10h]
0x180058149  lea     r8, WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids
0x180058150  call    WPP_SF_S
0x180058155  mov     ebx, 80070057h
0x18005815a  jmp     loc_1800584E8
0x18005815f  test    rsi, rsi
0x180058162  jnz     short loc_18005818F
0x180058164  mov     rcx, cs:WPP_GLOBAL_Control
0x18005816b  lea     rax, WPP_GLOBAL_Control
0x180058172  cmp     rcx, rax
0x180058175  jz      short loc_180058155
0x180058177  test    byte ptr [rcx+1Ch], 2
0x18005817b  jz      short loc_180058155
0x18005817d  cmp     byte ptr [rcx+19h], 2
0x180058181  jb      short loc_180058155
0x180058183  lea     edx, [rsi+63h]
0x180058186  lea     r9, aPguidvolume; "pguidVolume"
0x18005818d  jmp     short loc_180058145
0x18005818f  mov     rax, [rdi]
0x180058192  lea     rdx, [rbp+0B0h+var_A0]
0x180058196  mov     rcx, rdi
0x180058199  mov     rax, [rax+18h]
0x18005819d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581a2  mov     ebx, eax
0x1800581a4  test    eax, eax
0x1800581a6  jns     short loc_1800581F0
0x1800581a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800581af  lea     rax, WPP_GLOBAL_Control
0x1800581b6  cmp     rcx, rax
0x1800581b9  jz      loc_1800584E8
0x1800581bf  test    byte ptr [rcx+1Ch], 2
0x1800581c3  jz      loc_1800584E8
0x1800581c9  cmp     byte ptr [rcx+19h], 2
0x1800581cd  jb      loc_1800584E8
0x1800581d3  mov     edx, 64h ; 'd'
0x1800581d8  mov     rcx, [rcx+10h]
0x1800581dc  lea     r8, WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids
0x1800581e3  mov     r9d, ebx
0x1800581e6  call    WPP_SF_d
0x1800581eb  jmp     loc_1800584E8
0x1800581f0  mov     eax, [rbp+0B0h+var_5C]
0x1800581f3  cmp     eax, 1
0x1800581f6  jz      short loc_18005822F
0x1800581f8  mov     ebx, 80004005h
0x1800581fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180058204  lea     rax, WPP_GLOBAL_Control
0x18005820b  cmp     rcx, rax
0x18005820e  jz      loc_1800584E8
0x180058214  test    byte ptr [rcx+1Ch], 2
0x180058218  jz      loc_1800584E8
0x18005821e  cmp     byte ptr [rcx+19h], 2
0x180058222  jb      loc_1800584E8
0x180058228  mov     edx, 65h ; 'e'
0x18005822d  jmp     short loc_1800581D8
0x18005822f  lea     r9, [rsp+1B0h+var_150]; unsigned __int64 *
0x180058234  mov     [rbp+0B0h+var_120], eax
0x180058237  lea     r8, [rsp+1B0h+var_148]; unsigned __int64 *
0x18005823c  mov     [rbp+0B0h+var_118], 6
0x180058242  mov     rdx, rdi; struct IVdsDisk *
0x180058245  call    ?FindLargestFreeExtent@CVhdCreator@Util@RdVhd@@AEAAJPEAUIVdsDisk@@PEA_K1@Z; RdVhd::Util::CVhdCreator::FindLargestFreeExtent(IVdsDisk *,unsigned __int64 *,unsigned __int64 *)
0x18005824a  mov     ebx, eax
0x18005824c  test    eax, eax
0x18005824e  jns     short loc_180058285
0x180058250  mov     rcx, cs:WPP_GLOBAL_Control
0x180058257  lea     rax, WPP_GLOBAL_Control
0x18005825e  cmp     rcx, rax
0x180058261  jz      loc_1800584E8
0x180058267  test    byte ptr [rcx+1Ch], 2
0x18005826b  jz      loc_1800584E8
0x180058271  cmp     byte ptr [rcx+19h], 2
0x180058275  jb      loc_1800584E8
0x18005827b  mov     edx, 66h ; 'f'
0x180058280  jmp     loc_1800581D8
0x180058285  cmp     [rsp+1B0h+pProxy], 0
0x18005828b  jz      short loc_180058297
0x18005828d  lea     rcx, [rsp+1B0h+pProxy]; struct IUnknown **
0x180058292  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180058297  mov     rax, [rdi]
0x18005829a  lea     r8, [rsp+1B0h+pProxy]
0x18005829f  lea     rdx, IID_IVdsCreatePartitionEx
0x1800582a6  mov     rcx, rdi
0x1800582a9  mov     rax, [rax]
0x1800582ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800582b1  mov     ebx, eax
0x1800582b3  test    eax, eax
0x1800582b5  jns     short loc_1800582EC
0x1800582b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800582be  lea     rax, WPP_GLOBAL_Control
0x1800582c5  cmp     rcx, rax
0x1800582c8  jz      loc_1800584E8
0x1800582ce  test    byte ptr [rcx+1Ch], 2
0x1800582d2  jz      loc_1800584E8
0x1800582d8  cmp     byte ptr [rcx+19h], 2
0x1800582dc  jb      loc_1800584E8
0x1800582e2  mov     edx, 67h ; 'g'
0x1800582e7  jmp     loc_1800581D8
0x1800582ec  mov     rcx, [rsp+1B0h+pProxy]; pProxy
0x1800582f1  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800582f5  mov     [rsp+1B0h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1800582fd  xor     r8d, r8d; dwAuthzSvc
0x180058300  mov     [rsp+1B0h+pAuthInfo], 0; pAuthInfo
0x180058309  mov     [rsp+1B0h+dwImpLevel], 3; dwImpLevel
0x180058311  lea     edx, [r9+0Bh]; dwAuthnSvc
0x180058315  mov     [rsp+1B0h+dwAuthnLevel], 6; dwAuthnLevel
0x18005831d  call    cs:__imp_CoSetProxyBlanket
0x180058323  mov     ebx, eax
0x180058325  test    eax, eax
0x180058327  jns     short loc_18005835E
0x180058329  mov     rcx, cs:WPP_GLOBAL_Control
0x180058330  lea     rax, WPP_GLOBAL_Control
0x180058337  cmp     rcx, rax
0x18005833a  jz      loc_1800584E8
0x180058340  test    byte ptr [rcx+1Ch], 2
0x180058344  jz      loc_1800584E8
0x18005834a  cmp     byte ptr [rcx+19h], 2
0x18005834e  jb      loc_1800584E8
0x180058354  mov     edx, 68h ; 'h'
0x180058359  jmp     loc_1800581D8
0x18005835e  cmp     [rsp+1B0h+var_160], 0
0x180058364  jz      short loc_180058370
0x180058366  lea     rcx, [rsp+1B0h+var_160]; struct IUnknown **
0x18005836b  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180058370  mov     rcx, [rsp+1B0h+pProxy]
0x180058375  lea     rdx, [rsp+1B0h+var_160]
0x18005837a  mov     r8, [rsp+1B0h+var_150]
0x18005837f  xor     r9d, r9d
0x180058382  mov     qword ptr [rsp+1B0h+dwImpLevel], rdx
0x180058387  lea     rdx, [rbp+0B0h+var_120]
0x18005838b  mov     qword ptr [rsp+1B0h+dwAuthnLevel], rdx
0x180058390  mov     rax, [rcx]
0x180058393  mov     rdx, [rsp+1B0h+var_148]
0x180058398  mov     rax, [rax+18h]
0x18005839c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583a1  mov     ebx, eax
0x1800583a3  test    eax, eax
0x1800583a5  jns     short loc_1800583DC
0x1800583a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800583ae  lea     rax, WPP_GLOBAL_Control
0x1800583b5  cmp     rcx, rax
0x1800583b8  jz      loc_1800584E8
0x1800583be  test    byte ptr [rcx+1Ch], 2
0x1800583c2  jz      loc_1800584E8
0x1800583c8  cmp     byte ptr [rcx+19h], 2
0x1800583cc  jb      loc_1800584E8
0x1800583d2  mov     edx, 69h ; 'i'
0x1800583d7  jmp     loc_1800581D8
0x1800583dc  mov     rcx, [rsp+1B0h+var_160]
0x1800583e1  lea     r8, [rsp+1B0h+var_140]
0x1800583e6  lea     rdx, [rsp+1B0h+var_168]
0x1800583eb  mov     rax, [rcx]
0x1800583ee  mov     rax, [rax+20h]
0x1800583f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583f7  mov     ebx, eax
0x1800583f9  test    eax, eax
0x1800583fb  jns     short loc_180058432
0x1800583fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180058404  lea     rax, WPP_GLOBAL_Control
0x18005840b  cmp     rcx, rax
0x18005840e  jz      loc_1800584E8
0x180058414  test    byte ptr [rcx+1Ch], 2
0x180058418  jz      loc_1800584E8
0x18005841e  cmp     byte ptr [rcx+19h], 2
0x180058422  jb      loc_1800584E8
0x180058428  mov     edx, 6Ah ; 'j'
0x18005842d  jmp     loc_1800581D8
0x180058432  mov     ebx, [rsp+1B0h+var_168]
0x180058436  test    ebx, ebx
0x180058438  jns     short loc_18005846F
0x18005843a  mov     rcx, cs:WPP_GLOBAL_Control
0x180058441  lea     rax, WPP_GLOBAL_Control
0x180058448  cmp     rcx, rax
0x18005844b  jz      loc_1800584E8
0x180058451  test    byte ptr [rcx+1Ch], 2
0x180058455  jz      loc_1800584E8
0x18005845b  cmp     byte ptr [rcx+19h], 2
0x18005845f  jb      loc_1800584E8
0x180058465  mov     edx, 6Bh ; 'k'
0x18005846a  jmp     loc_1800581D8
0x18005846f  mov     rax, [rdi]
0x180058472  lea     r8, [rsp+1B0h+var_164]
0x180058477  lea     rdx, [rsp+1B0h+pv]
0x18005847c  mov     rcx, rdi
0x18005847f  mov     rax, [rax+30h]
0x180058483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058488  mov     ebx, eax
0x18005848a  test    eax, eax
0x18005848c  jns     short loc_1800584B7
0x18005848e  mov     rcx, cs:WPP_GLOBAL_Control
0x180058495  lea     rax, WPP_GLOBAL_Control
0x18005849c  cmp     rcx, rax
0x18005849f  jz      short loc_1800584E8
0x1800584a1  test    byte ptr [rcx+1Ch], 2
0x1800584a5  jz      short loc_1800584E8
0x1800584a7  cmp     byte ptr [rcx+19h], 2
0x1800584ab  jb      short loc_1800584E8
0x1800584ad  mov     edx, 6Ch ; 'l'
0x1800584b2  jmp     loc_1800581D8
0x1800584b7  xor     ecx, ecx
0x1800584b9  cmp     ecx, [rsp+1B0h+var_164]
0x1800584bd  jge     short loc_1800584E8
0x1800584bf  mov     r8, [rsp+1B0h+pv]
0x1800584c4  movsxd  rax, ecx
0x1800584c7  lea     rdx, [rax+rax*4]
0x1800584cb  mov     rax, qword ptr [rsp+1B0h+var_140+8]
0x1800584d0  add     rdx, rdx
0x1800584d3  cmp     [r8+rdx*8+18h], rax
0x1800584d8  jz      short loc_1800584DE
0x1800584da  inc     ecx
0x1800584dc  jmp     short loc_1800584B9
0x1800584de  movups  xmm0, xmmword ptr [r8+rdx*8+28h]
0x1800584e4  movdqu  xmmword ptr [rsi], xmm0
0x1800584e8  mov     ecx, dword ptr [rsp+1B0h+var_140]
0x1800584ec  sub     ecx, 1
0x1800584ef  jz      short loc_18005850D
0x1800584f1  sub     ecx, 4
0x1800584f4  jz      short loc_18005850D
0x1800584f6  sub     ecx, 2Dh ; '-'
0x1800584f9  jz      short loc_18005850D
0x1800584fb  sub     ecx, 0Ch
0x1800584fe  jz      short loc_18005850D
0x180058500  sub     ecx, 1
0x180058503  jz      short loc_18005850D
0x180058505  cmp     ecx, 89h
0x18005850b  jnz     short loc_180058523
0x18005850d  mov     rcx, qword ptr [rsp+1B0h+var_140+8]
0x180058512  test    rcx, rcx
0x180058515  jz      short loc_180058523
0x180058517  mov     rax, [rcx]
0x18005851a  mov     rax, [rax+10h]
0x18005851e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058523  mov     rcx, [rsp+1B0h+pv]; pv
0x180058528  test    rcx, rcx
0x18005852b  jz      short loc_180058533
0x18005852d  call    cs:__imp_CoTaskMemFree
0x180058533  mov     rcx, [rbp+0B0h+var_48]; pv
0x180058537  test    rcx, rcx
0x18005853a  jz      short loc_180058542
0x18005853c  call    cs:__imp_CoTaskMemFree
0x180058542  mov     rcx, [rbp+0B0h+var_40]; pv
0x180058546  test    rcx, rcx
0x180058549  jz      short loc_180058551
0x18005854b  call    cs:__imp_CoTaskMemFree
0x180058551  mov     rcx, [rbp+0B0h+var_38]; pv
0x180058555  test    rcx, rcx
0x180058558  jz      short loc_180058560
0x18005855a  call    cs:__imp_CoTaskMemFree
0x180058560  mov     rcx, [rbp+0B0h+var_30]; pv
0x180058567  test    rcx, rcx
0x18005856a  jz      short loc_180058572
0x18005856c  call    cs:__imp_CoTaskMemFree
0x180058572  mov     rcx, [rbp+0B0h+var_28]; pv
0x180058579  test    rcx, rcx
0x18005857c  jz      short loc_180058584
0x18005857e  call    cs:__imp_CoTaskMemFree
0x180058584  lea     rcx, [rsp+1B0h+var_160]
0x180058589  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005858e  lea     rcx, [rsp+1B0h+pProxy]
0x180058593  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180058598  mov     eax, ebx
  ... truncated ...
```
