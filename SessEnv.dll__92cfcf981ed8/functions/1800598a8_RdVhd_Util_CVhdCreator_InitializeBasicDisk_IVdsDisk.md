# RdVhd::Util::CVhdCreator::InitializeBasicDisk(IVdsDisk *)

- ea: `0x1800598a8`
- end: `0x180059dd0`
- name: `?InitializeBasicDisk@CVhdCreator@Util@RdVhd@@QEAAJPEAUIVdsDisk@@@Z`
- size: `1320`
- prototype: `__int64 __fastcall(RdVhd::Util::CVhdCreator *__hidden this, struct IVdsDisk *)`
- caller_count: `1`
- callee_count: `8`
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
- `0x1800598a8`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059d36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059d45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059d54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059d63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059d72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059d36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059d45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059d54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059d63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059d72`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180059b7d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180059b7d`

## pseudocode

```c
__int64 __fastcall RdVhd::Util::CVhdCreator::InitializeBasicDisk(RdVhd::Util::CVhdCreator *this, struct IVdsDisk *a2)
{
  HRESULT v4; // ebx
  struct IUnknown *v5; // rdx
  __int64 v6; // r9
  RdVhd::Uvhd::CUvhdDiskManager *v7; // rcx
  __int64 v8; // rdx
  struct IUnknown *v9; // rdx
  int v10; // eax
  struct IUnknown *v11; // rdx
  struct IUnknown *v12; // rdx
  struct IUnknown *v14; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v15; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown *v16; // [rsp+50h] [rbp-B0h] BYREF
  struct IUnknown *v17; // [rsp+58h] [rbp-A8h] BYREF
  IUnknown *pProxy; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+68h] [rbp-98h] BYREF
  __int128 v20; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v21[5]; // [rsp+80h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+D8h] [rbp-28h]
  LPVOID v23; // [rsp+E0h] [rbp-20h]
  LPVOID v24; // [rsp+E8h] [rbp-18h]
  LPVOID v25; // [rsp+F0h] [rbp-10h]
  LPVOID v26; // [rsp+F8h] [rbp-8h]
  _BYTE v27[64]; // [rsp+100h] [rbp+0h] BYREF

  v14 = 0;
  v17 = 0;
  v16 = 0;
  v15 = 0;
  pProxy = 0;
  memset_0(v27, 0, sizeof(v27));
  memset_0(v21, 0, 0x80u);
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids,
        L"pDiskToInitialize");
    }
    v4 = -2147024809;
    goto LABEL_71;
  }
  v4 = ((__int64 (__fastcall *)(struct IVdsDisk *, struct IUnknown **))a2->lpVtbl->GetPack)(a2, &v14);
  if ( v4 < 0 )
  {
    if ( v4 != -2147212265 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_71;
      }
      v8 = 71;
      goto LABEL_18;
    }
  }
  else if ( v14 )
  {
    v6 = 2147500037LL;
    v4 = -2147467259;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_71;
    }
    v8 = 70;
LABEL_70:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids, v6);
    goto LABEL_71;
  }
  if ( v17 )
    ATL::AtlComPtrAssign(&v17, v5);
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct IUnknown **))(**((_QWORD **)this + 1) + 48LL))(
         *((_QWORD *)this + 1),
         1,
         &v17);
  if ( v4 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_71;
    }
    v8 = 72;
LABEL_18:
    v6 = (unsigned int)v4;
    goto LABEL_70;
  }
  while ( 1 )
  {
    v19 = 0;
    if ( v16 )
      ATL::AtlComPtrAssign(&v16, v9);
    v10 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **, int *))v17->lpVtbl[1].QueryInterface)(
            v17,
            1,
            &v16,
            &v19);
    v4 = v10;
    if ( v10 == 1 )
      break;
    if ( v10 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 74;
        goto LABEL_18;
      }
      goto LABEL_71;
    }
    if ( v15 )
      ATL::AtlComPtrAssign(&v15, v11);
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v16->lpVtbl->QueryInterface)(
           v16,
           &IID_IVdsProvider,
           &v15) >= 0
      && ((int (__fastcall *)(struct IUnknown *, _BYTE *))v15->lpVtbl[1].QueryInterface)(v15, v27) >= 0
      && (v27[52] & 4) != 0 )
    {
      v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, IUnknown **))v15->lpVtbl->QueryInterface)(
             v15,
             &IID_IVdsSwProvider,
             &pProxy);
      if ( v4 >= 0 )
      {
        v4 = CoSetProxyBlanket(pProxy, 0xAu, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 6u, 3u, 0, 0x40u);
        if ( v4 >= 0 )
        {
          if ( v14 )
            ATL::AtlComPtrAssign(&v14, v12);
          v4 = ((__int64 (__fastcall *)(IUnknown *, struct IUnknown **))pProxy->lpVtbl[1].AddRef)(pProxy, &v14);
          if ( v4 >= 0 )
          {
            v4 = ((__int64 (__fastcall *)(struct IVdsDisk *, _OWORD *))a2->lpVtbl->GetProperties)(a2, v21);
            if ( v4 >= 0 )
            {
              v20 = v21[0];
              v4 = ((__int64 (__fastcall *)(struct IUnknown *, __int128 *, __int64, _QWORD))v14->lpVtbl[2].Release)(
                     v14,
                     &v20,
                     1,
                     0);
              if ( v4 < 0 )
              {
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v8 = 79;
                  goto LABEL_18;
                }
              }
            }
            else
            {
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v8 = 78;
                goto LABEL_18;
              }
            }
          }
          else
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v8 = 77;
              goto LABEL_18;
            }
          }
        }
        else
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = 76;
            goto LABEL_18;
          }
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 75;
          goto LABEL_18;
        }
      }
      goto LABEL_71;
    }
  }
  v6 = 2147500037LL;
  v4 = -2147467259;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = 73;
    goto LABEL_70;
  }
LABEL_71:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v23 )
    CoTaskMemFree(v23);
  if ( v24 )
    CoTaskMemFree(v24);
  if ( v25 )
    CoTaskMemFree(v25);
  if ( v26 )
    CoTaskMemFree(v26);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pProxy);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v15);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800598a8  mov     [rsp-8+arg_10], rbx
0x1800598ad  mov     [rsp-8+arg_18], rsi
0x1800598b2  push    rbp
0x1800598b3  push    rdi
0x1800598b4  push    r14
0x1800598b6  lea     rbp, [rsp-50h]
0x1800598bb  sub     rsp, 150h
0x1800598c2  mov     rax, cs:__security_cookie
0x1800598c9  xor     rax, rsp
0x1800598cc  mov     [rbp+60h+var_20], rax
0x1800598d0  xor     r14d, r14d
0x1800598d3  mov     rdi, rdx
0x1800598d6  mov     rsi, rcx
0x1800598d9  mov     [rsp+160h+var_120], r14
0x1800598de  xor     edx, edx; Val
0x1800598e0  mov     [rsp+160h+var_108], r14
0x1800598e5  lea     rcx, [rbp+60h+var_60]; void *
0x1800598e9  mov     [rsp+160h+var_110], r14
0x1800598ee  lea     r8d, [r14+40h]; Size
0x1800598f2  mov     [rsp+160h+var_118], r14
0x1800598f7  mov     [rsp+160h+pProxy], r14
0x1800598fc  call    memset_0
0x180059901  xor     edx, edx; Val
0x180059903  lea     rcx, [rbp+60h+var_E0]; void *
0x180059907  mov     r8d, 80h; Size
0x18005990d  call    memset_0
0x180059912  test    rdi, rdi
0x180059915  jnz     short loc_18005995A
0x180059917  mov     rcx, cs:WPP_GLOBAL_Control
0x18005991e  lea     rax, WPP_GLOBAL_Control
0x180059925  cmp     rcx, rax
0x180059928  jz      short loc_180059950
0x18005992a  test    byte ptr [rcx+1Ch], 2
0x18005992e  jz      short loc_180059950
0x180059930  cmp     byte ptr [rcx+19h], 2
0x180059934  jb      short loc_180059950
0x180059936  mov     rcx, [rcx+10h]
0x18005993a  lea     edx, [rdi+45h]
0x18005993d  lea     r9, aPdisktoinitial; "pDiskToInitialize"
0x180059944  lea     r8, WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids
0x18005994b  call    WPP_SF_S
0x180059950  mov     ebx, 80070057h
0x180059955  jmp     loc_180059D2D
0x18005995a  mov     rax, [rdi]
0x18005995d  lea     rdx, [rsp+160h+var_120]
0x180059962  mov     rcx, rdi
0x180059965  mov     rax, [rax+20h]
0x180059969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005996e  mov     ebx, eax
0x180059970  test    eax, eax
0x180059972  js      short loc_1800599B9
0x180059974  cmp     [rsp+160h+var_120], r14
0x180059979  jz      short loc_1800599F9
0x18005997b  mov     r9d, 80004005h
0x180059981  mov     ebx, r9d
0x180059984  mov     rcx, cs:WPP_GLOBAL_Control
0x18005998b  lea     rax, WPP_GLOBAL_Control
0x180059992  cmp     rcx, rax
0x180059995  jz      loc_180059D2D
0x18005999b  test    byte ptr [rcx+1Ch], 2
0x18005999f  jz      loc_180059D2D
0x1800599a5  cmp     byte ptr [rcx+19h], 2
0x1800599a9  jb      loc_180059D2D
0x1800599af  mov     edx, 46h ; 'F'
0x1800599b4  jmp     loc_180059D1D
0x1800599b9  cmp     ebx, 80042417h
0x1800599bf  jz      short loc_1800599F9
0x1800599c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800599c8  lea     rax, WPP_GLOBAL_Control
0x1800599cf  cmp     rcx, rax
0x1800599d2  jz      loc_180059D2D
0x1800599d8  test    byte ptr [rcx+1Ch], 2
0x1800599dc  jz      loc_180059D2D
0x1800599e2  cmp     byte ptr [rcx+19h], 2
0x1800599e6  jb      loc_180059D2D
0x1800599ec  mov     edx, 47h ; 'G'
0x1800599f1  mov     r9d, ebx
0x1800599f4  jmp     loc_180059D1D
0x1800599f9  cmp     [rsp+160h+var_108], r14
0x1800599fe  jz      short loc_180059A0A
0x180059a00  lea     rcx, [rsp+160h+var_108]; struct IUnknown **
0x180059a05  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180059a0a  mov     rcx, [rsi+8]
0x180059a0e  lea     r8, [rsp+160h+var_108]
0x180059a13  mov     esi, 1
0x180059a18  mov     edx, esi
0x180059a1a  mov     rax, [rcx]
0x180059a1d  mov     rax, [rax+30h]
0x180059a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a26  mov     ebx, eax
0x180059a28  test    eax, eax
0x180059a2a  jns     short loc_180059A5C
0x180059a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180059a33  lea     rax, WPP_GLOBAL_Control
0x180059a3a  cmp     rcx, rax
0x180059a3d  jz      loc_180059D2D
0x180059a43  test    byte ptr [rcx+1Ch], 2
0x180059a47  jz      loc_180059D2D
0x180059a4d  cmp     byte ptr [rcx+19h], 2
0x180059a51  jb      loc_180059D2D
0x180059a57  lea     edx, [rsi+47h]
0x180059a5a  jmp     short loc_1800599F1
0x180059a5c  mov     [rsp+160h+var_F8], r14d
0x180059a61  cmp     [rsp+160h+var_110], r14
0x180059a66  jz      short loc_180059A72
0x180059a68  lea     rcx, [rsp+160h+var_110]; struct IUnknown **
0x180059a6d  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180059a72  mov     rcx, [rsp+160h+var_108]
0x180059a77  lea     r9, [rsp+160h+var_F8]
0x180059a7c  lea     r8, [rsp+160h+var_110]
0x180059a81  mov     edx, esi
0x180059a83  mov     rax, [rcx]
0x180059a86  mov     rax, [rax+18h]
0x180059a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a8f  mov     ebx, eax
0x180059a91  cmp     eax, esi
0x180059a93  jz      loc_180059CF0
0x180059a99  test    eax, eax
0x180059a9b  js      loc_180059CC7
0x180059aa1  cmp     [rsp+160h+var_118], r14
0x180059aa6  jz      short loc_180059AB2
0x180059aa8  lea     rcx, [rsp+160h+var_118]; struct IUnknown **
0x180059aad  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180059ab2  mov     rcx, [rsp+160h+var_110]
0x180059ab7  lea     r8, [rsp+160h+var_118]
0x180059abc  lea     rdx, IID_IVdsProvider
0x180059ac3  mov     rax, [rcx]
0x180059ac6  mov     rax, [rax]
0x180059ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ace  test    eax, eax
0x180059ad0  js      short loc_180059A5C
0x180059ad2  mov     rcx, [rsp+160h+var_118]
0x180059ad7  lea     rdx, [rbp+60h+var_60]
0x180059adb  mov     rax, [rcx]
0x180059ade  mov     rax, [rax+18h]
0x180059ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ae7  test    eax, eax
0x180059ae9  js      loc_180059A5C
0x180059aef  test    [rbp+60h+var_2C], 4
0x180059af3  jz      loc_180059A5C
0x180059af9  mov     rcx, [rsp+160h+var_118]
0x180059afe  lea     r8, [rsp+160h+pProxy]
0x180059b03  lea     rdx, IID_IVdsSwProvider
0x180059b0a  mov     rax, [rcx]
0x180059b0d  mov     rax, [rax]
0x180059b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b15  mov     ebx, eax
0x180059b17  test    eax, eax
0x180059b19  jns     short loc_180059B50
0x180059b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180059b22  lea     rax, WPP_GLOBAL_Control
0x180059b29  cmp     rcx, rax
0x180059b2c  jz      loc_180059D2D
0x180059b32  test    byte ptr [rcx+1Ch], 2
0x180059b36  jz      loc_180059D2D
0x180059b3c  cmp     byte ptr [rcx+19h], 2
0x180059b40  jb      loc_180059D2D
0x180059b46  mov     edx, 4Bh ; 'K'
0x180059b4b  jmp     loc_1800599F1
0x180059b50  mov     rcx, [rsp+160h+pProxy]; pProxy
0x180059b55  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180059b59  mov     [rsp+160h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180059b61  xor     r8d, r8d; dwAuthzSvc
0x180059b64  mov     [rsp+160h+pAuthInfo], r14; pAuthInfo
0x180059b69  mov     [rsp+160h+dwImpLevel], 3; dwImpLevel
0x180059b71  lea     edx, [r9+0Bh]; dwAuthnSvc
0x180059b75  mov     [rsp+160h+dwAuthnLevel], 6; dwAuthnLevel
0x180059b7d  call    cs:__imp_CoSetProxyBlanket
0x180059b83  mov     ebx, eax
0x180059b85  test    eax, eax
0x180059b87  jns     short loc_180059BBE
0x180059b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180059b90  lea     rax, WPP_GLOBAL_Control
0x180059b97  cmp     rcx, rax
0x180059b9a  jz      loc_180059D2D
0x180059ba0  test    byte ptr [rcx+1Ch], 2
0x180059ba4  jz      loc_180059D2D
0x180059baa  cmp     byte ptr [rcx+19h], 2
0x180059bae  jb      loc_180059D2D
0x180059bb4  mov     edx, 4Ch ; 'L'
0x180059bb9  jmp     loc_1800599F1
0x180059bbe  cmp     [rsp+160h+var_120], r14
0x180059bc3  jz      short loc_180059BCF
0x180059bc5  lea     rcx, [rsp+160h+var_120]; struct IUnknown **
0x180059bca  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180059bcf  mov     rcx, [rsp+160h+pProxy]
0x180059bd4  lea     rdx, [rsp+160h+var_120]
0x180059bd9  mov     rax, [rcx]
0x180059bdc  mov     rax, [rax+20h]
0x180059be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059be5  mov     ebx, eax
0x180059be7  test    eax, eax
0x180059be9  jns     short loc_180059C20
0x180059beb  mov     rcx, cs:WPP_GLOBAL_Control
0x180059bf2  lea     rax, WPP_GLOBAL_Control
0x180059bf9  cmp     rcx, rax
0x180059bfc  jz      loc_180059D2D
0x180059c02  test    byte ptr [rcx+1Ch], 2
0x180059c06  jz      loc_180059D2D
0x180059c0c  cmp     byte ptr [rcx+19h], 2
0x180059c10  jb      loc_180059D2D
0x180059c16  mov     edx, 4Dh ; 'M'
0x180059c1b  jmp     loc_1800599F1
0x180059c20  mov     rax, [rdi]
0x180059c23  lea     rdx, [rbp+60h+var_E0]
0x180059c27  mov     rcx, rdi
0x180059c2a  mov     rax, [rax+18h]
0x180059c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c33  mov     ebx, eax
0x180059c35  test    eax, eax
0x180059c37  jns     short loc_180059C6E
0x180059c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180059c40  lea     rax, WPP_GLOBAL_Control
0x180059c47  cmp     rcx, rax
0x180059c4a  jz      loc_180059D2D
0x180059c50  test    byte ptr [rcx+1Ch], 2
0x180059c54  jz      loc_180059D2D
0x180059c5a  cmp     byte ptr [rcx+19h], 2
0x180059c5e  jb      loc_180059D2D
0x180059c64  mov     edx, 4Eh ; 'N'
0x180059c69  jmp     loc_1800599F1
0x180059c6e  mov     rcx, [rsp+160h+var_120]
0x180059c73  lea     rdx, [rsp+160h+var_F0]
0x180059c78  movaps  xmm0, [rbp+60h+var_E0]
0x180059c7c  xor     r9d, r9d
0x180059c7f  mov     r8d, esi
0x180059c82  movdqu  [rsp+160h+var_F0], xmm0
0x180059c88  mov     rax, [rcx]
0x180059c8b  mov     rax, [rax+40h]
0x180059c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c94  mov     ebx, eax
0x180059c96  test    eax, eax
0x180059c98  jns     loc_180059D2D
0x180059c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180059ca5  lea     rax, WPP_GLOBAL_Control
0x180059cac  cmp     rcx, rax
0x180059caf  jz      short loc_180059D2D
0x180059cb1  test    byte ptr [rcx+1Ch], 2
0x180059cb5  jz      short loc_180059D2D
0x180059cb7  cmp     byte ptr [rcx+19h], 2
0x180059cbb  jb      short loc_180059D2D
0x180059cbd  mov     edx, 4Fh ; 'O'
0x180059cc2  jmp     loc_1800599F1
0x180059cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180059cce  lea     rax, WPP_GLOBAL_Control
0x180059cd5  cmp     rcx, rax
0x180059cd8  jz      short loc_180059D2D
0x180059cda  test    byte ptr [rcx+1Ch], 2
0x180059cde  jz      short loc_180059D2D
0x180059ce0  cmp     byte ptr [rcx+19h], 2
0x180059ce4  jb      short loc_180059D2D
0x180059ce6  mov     edx, 4Ah ; 'J'
0x180059ceb  jmp     loc_1800599F1
0x180059cf0  mov     r9d, 80004005h
0x180059cf6  mov     ebx, r9d
0x180059cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180059d00  lea     rax, WPP_GLOBAL_Control
0x180059d07  cmp     rcx, rax
0x180059d0a  jz      short loc_180059D2D
0x180059d0c  test    byte ptr [rcx+1Ch], 2
0x180059d10  jz      short loc_180059D2D
0x180059d12  cmp     byte ptr [rcx+19h], 2
0x180059d16  jb      short loc_180059D2D
0x180059d18  mov     edx, 49h ; 'I'
0x180059d1d  mov     rcx, [rcx+10h]
0x180059d21  lea     r8, WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids
0x180059d28  call    WPP_SF_d
0x180059d2d  mov     rcx, [rbp+60h+pv]; pv
0x180059d31  test    rcx, rcx
0x180059d34  jz      short loc_180059D3C
0x180059d36  call    cs:__imp_CoTaskMemFree
0x180059d3c  mov     rcx, [rbp+60h+var_80]; pv
0x180059d40  test    rcx, rcx
0x180059d43  jz      short loc_180059D4B
0x180059d45  call    cs:__imp_CoTaskMemFree
0x180059d4b  mov     rcx, [rbp+60h+var_78]; pv
0x180059d4f  test    rcx, rcx
0x180059d52  jz      short loc_180059D5A
0x180059d54  call    cs:__imp_CoTaskMemFree
0x180059d5a  mov     rcx, [rbp+60h+var_70]; pv
0x180059d5e  test    rcx, rcx
0x180059d61  jz      short loc_180059D69
0x180059d63  call    cs:__imp_CoTaskMemFree
0x180059d69  mov     rcx, [rbp+60h+var_68]; pv
0x180059d6d  test    rcx, rcx
0x180059d70  jz      short loc_180059D78
0x180059d72  call    cs:__imp_CoTaskMemFree
0x180059d78  lea     rcx, [rsp+160h+pProxy]
0x180059d7d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180059d82  lea     rcx, [rsp+160h+var_118]
0x180059d87  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180059d8c  lea     rcx, [rsp+160h+var_110]
0x180059d91  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180059d96  lea     rcx, [rsp+160h+var_108]
0x180059d9b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180059da0  lea     rcx, [rsp+160h+var_120]
0x180059da5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180059daa  mov     eax, ebx
0x180059dac  mov     rcx, [rbp+60h+var_20]
0x180059db0  xor     rcx, rsp; StackCookie
  ... truncated ...
```
