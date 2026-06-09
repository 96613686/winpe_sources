# RdVhd::Util::CVhdCreator::InitializeVds(IVdsService * *)

- ea: `0x180059dd8`
- end: `0x18005a0e6`
- name: `?InitializeVds@CVhdCreator@Util@RdVhd@@AEAAJPEAPEAUIVdsService@@@Z`
- size: `782`
- prototype: `__int64 __fastcall(RdVhd::Util::CVhdCreator *__hidden this, struct IVdsService **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180057f00`

## callees

- `0x180012d7c`
- `0x18001a280`
- `0x180032ae8`
- `0x1800488e4`
- `0x180048b28`
- `0x180059dd8`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180059f79`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180059f79`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180059ea4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180059ea4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005a0b4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005a0b4`

## string_xrefs

- `0x180059e7c`: `ppVdsService`

## pseudocode

```c
__int64 __fastcall RdVhd::Util::CVhdCreator::InitializeVds(RdVhd::Util::CVhdCreator *this, struct IUnknown **a2)
{
  HRESULT hr; // ebx
  unsigned int v4; // edi
  struct IUnknown *v5; // rdx
  RdVhd::Uvhd::CUvhdDiskManager *v6; // rcx
  __int64 v7; // rdx
  IUnknown *pItf; // rbx
  struct IUnknown *v10; // [rsp+30h] [rbp-59h] BYREF
  IUnknown *v11; // [rsp+38h] [rbp-51h] BYREF
  __int128 v12; // [rsp+40h] [rbp-49h] BYREF
  __int128 v13; // [rsp+50h] [rbp-39h]
  __int64 v14; // [rsp+60h] [rbp-29h]
  MULTI_QI pResults; // [rsp+68h] [rbp-21h] BYREF
  COSERVERINFO pServerInfo; // [rsp+80h] [rbp-9h] BYREF
  __int128 v17; // [rsp+A0h] [rbp+17h] BYREF
  int v18; // [rsp+B0h] [rbp+27h]

  v11 = 0;
  v14 = 0;
  v18 = *(_DWORD *)L"t";
  pResults.pIID = &IID_IVdsServiceLoader;
  v10 = 0;
  v12 = 0;
  pResults.pItf = 0;
  v13 = 0;
  pResults.hr = 0;
  memset(&pServerInfo, 0, sizeof(pServerInfo));
  v17 = *(_OWORD *)L"localhost";
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids,
        L"ppVdsService");
    }
    hr = -2147024809;
    goto LABEL_39;
  }
  *a2 = 0;
  v4 = CoInitializeEx(0, 0);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147417850 )
  {
    hr = v4;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids, v4);
    }
    goto LABEL_39;
  }
  v13 = 0x300000006uLL;
  *(_QWORD *)&v12 = -1;
  *((_QWORD *)&v12 + 1) = &v17;
  pServerInfo.pwszName = (LPWSTR)&v17;
  LODWORD(v14) = 0;
  pServerInfo.pAuthInfo = (COAUTHINFO *)&v12;
  pServerInfo.dwReserved1 = 0;
  pServerInfo.dwReserved2 = 0;
  hr = CoCreateInstanceEx(&Clsid, 0, 0x10004u, &pServerInfo, 1u, &pResults);
  if ( hr >= 0 )
  {
    hr = pResults.hr;
    if ( pResults.hr >= 0 )
    {
      pItf = pResults.pItf;
      v11 = pResults.pItf;
      if ( v10 )
        ATL::AtlComPtrAssign(&v10, v5);
      hr = ((__int64 (__fastcall *)(IUnknown *, _QWORD, struct IUnknown **))pItf->lpVtbl[1].QueryInterface)(
             pItf,
             0,
             &v10);
      if ( hr >= 0 )
      {
        hr = ((__int64 (__fastcall *)(struct IUnknown *))v10->lpVtbl[1].AddRef)(v10);
        if ( hr >= 0 )
        {
          *a2 = v10;
          v10 = 0;
        }
        else
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v7 = 23;
            goto LABEL_18;
          }
        }
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 22;
          goto LABEL_18;
        }
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 21;
        goto LABEL_18;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 20;
LABEL_18:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids, (unsigned int)hr);
    }
  }
  if ( !v4 )
    CoUninitialize();
LABEL_39:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
  return (unsigned int)hr;
}

```

## disassembly

```asm
0x180059dd8  push    rbp
0x180059dda  push    rbx
0x180059ddb  push    rsi
0x180059ddc  push    rdi
0x180059ddd  lea     rbp, [rsp-3Fh]
0x180059de2  sub     rsp, 0C8h
0x180059de9  mov     rax, cs:__security_cookie
0x180059df0  xor     rax, rsp
0x180059df3  mov     [rbp+57h+var_28], rax
0x180059df7  movups  xmm1, xmmword ptr cs:aLocalhost; "localhost"
0x180059dfe  mov     [rbp+57h+var_A8], 0
0x180059e06  xor     eax, eax
0x180059e08  xorps   xmm0, xmm0
0x180059e0b  mov     [rbp+57h+var_80], rax
0x180059e0f  mov     eax, dword ptr cs:aLocalhost+10h; "t"
0x180059e15  mov     rsi, rdx
0x180059e18  mov     [rbp+57h+var_30], eax
0x180059e1b  lea     rax, IID_IVdsServiceLoader
0x180059e22  mov     [rbp+57h+var_78.pIID], rax
0x180059e26  mov     [rbp+57h+var_B0], 0
0x180059e2e  movups  [rbp+57h+var_A0], xmm0
0x180059e32  mov     [rbp+57h+var_78.pItf], 0
0x180059e3a  movups  [rbp+57h+var_90], xmm0
0x180059e3e  mov     [rbp+57h+var_78.hr], 0
0x180059e45  movups  xmmword ptr [rbp+57h+pServerInfo.dwReserved1], xmm0
0x180059e49  movups  xmmword ptr [rbp+57h+pServerInfo.pAuthInfo], xmm0
0x180059e4d  movups  [rbp+57h+var_40], xmm1
0x180059e51  test    rdx, rdx
0x180059e54  jnz     short loc_180059E99
0x180059e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180059e5d  lea     rax, WPP_GLOBAL_Control
0x180059e64  cmp     rcx, rax
0x180059e67  jz      short loc_180059E8F
0x180059e69  test    byte ptr [rcx+1Ch], 2
0x180059e6d  jz      short loc_180059E8F
0x180059e6f  cmp     byte ptr [rcx+19h], 2
0x180059e73  jb      short loc_180059E8F
0x180059e75  mov     rcx, [rcx+10h]
0x180059e79  lea     edx, [rsi+12h]
0x180059e7c  lea     r9, aPpvdsservice; "ppVdsService"
0x180059e83  lea     r8, WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids
0x180059e8a  call    WPP_SF_S
0x180059e8f  mov     ebx, 80070057h
0x180059e94  jmp     loc_18005A0BA
0x180059e99  mov     qword ptr [rdx], 0
0x180059ea0  xor     ecx, ecx; pvReserved
0x180059ea2  xor     edx, edx; dwCoInit
0x180059ea4  call    cs:__imp_CoInitializeEx
0x180059eaa  mov     ecx, 80000000h
0x180059eaf  mov     edi, eax
0x180059eb1  add     eax, ecx
0x180059eb3  test    ecx, eax
0x180059eb5  jnz     short loc_180059F09
0x180059eb7  cmp     edi, 80010106h
0x180059ebd  jz      short loc_180059F09
0x180059ebf  mov     ebx, edi
0x180059ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x180059ec8  lea     rax, WPP_GLOBAL_Control
0x180059ecf  cmp     rcx, rax
0x180059ed2  jz      loc_18005A0BA
0x180059ed8  test    byte ptr [rcx+1Ch], 2
0x180059edc  jz      loc_18005A0BA
0x180059ee2  cmp     byte ptr [rcx+19h], 2
0x180059ee6  jb      loc_18005A0BA
0x180059eec  mov     rcx, [rcx+10h]
0x180059ef0  lea     r8, WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids
0x180059ef7  mov     edx, 13h
0x180059efc  mov     r9d, edi
0x180059eff  call    WPP_SF_d
0x180059f04  jmp     loc_18005A0BA
0x180059f09  or      eax, 0FFFFFFFFh
0x180059f0c  mov     dword ptr [rbp+57h+var_90], 6
0x180059f13  mov     dword ptr [rbp+57h+var_A0], eax
0x180059f16  lea     r9, [rbp+57h+pServerInfo]; pServerInfo
0x180059f1a  mov     dword ptr [rbp+57h+var_A0+4], eax
0x180059f1d  lea     rcx, Clsid; Clsid
0x180059f24  lea     rax, [rbp+57h+var_40]
0x180059f28  mov     dword ptr [rbp+57h+var_90+4], 3
0x180059f2f  mov     qword ptr [rbp+57h+var_A0+8], rax
0x180059f33  xor     edx, edx; punkOuter
0x180059f35  lea     rax, [rbp+57h+var_40]
0x180059f39  mov     qword ptr [rbp+57h+var_90+8], 0
0x180059f41  mov     [rbp+57h+pServerInfo.pwszName], rax
0x180059f45  mov     r8d, 10004h; dwClsCtx
0x180059f4b  lea     rax, [rbp+57h+var_A0]
0x180059f4f  mov     dword ptr [rbp+57h+var_80], 0
0x180059f56  mov     [rbp+57h+pServerInfo.pAuthInfo], rax
0x180059f5a  lea     rax, [rbp+57h+var_78]
0x180059f5e  mov     [rsp+0E0h+pResults], rax; pResults
0x180059f63  mov     [rsp+0E0h+dwCount], 1; dwCount
0x180059f6b  mov     [rbp+57h+pServerInfo.dwReserved1], 0
0x180059f72  mov     [rbp+57h+pServerInfo.dwReserved2], 0
0x180059f79  call    cs:__imp_CoCreateInstanceEx
0x180059f7f  mov     ebx, eax
0x180059f81  test    eax, eax
0x180059f83  jns     short loc_180059FCD
0x180059f85  mov     rcx, cs:WPP_GLOBAL_Control
0x180059f8c  lea     rax, WPP_GLOBAL_Control
0x180059f93  cmp     rcx, rax
0x180059f96  jz      loc_18005A0B0
0x180059f9c  test    byte ptr [rcx+1Ch], 2
0x180059fa0  jz      loc_18005A0B0
0x180059fa6  cmp     byte ptr [rcx+19h], 2
0x180059faa  jb      loc_18005A0B0
0x180059fb0  mov     edx, 14h
0x180059fb5  mov     rcx, [rcx+10h]
0x180059fb9  lea     r8, WPP_817a646ab31c3ab858ae8a1f78623f18_Traceguids
0x180059fc0  mov     r9d, ebx
0x180059fc3  call    WPP_SF_d
0x180059fc8  jmp     loc_18005A0B0
0x180059fcd  mov     ebx, [rbp+57h+var_78.hr]
0x180059fd0  test    ebx, ebx
0x180059fd2  jns     short loc_18005A006
0x180059fd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180059fdb  lea     rax, WPP_GLOBAL_Control
0x180059fe2  cmp     rcx, rax
0x180059fe5  jz      loc_18005A0B0
0x180059feb  test    byte ptr [rcx+1Ch], 2
0x180059fef  jz      loc_18005A0B0
0x180059ff5  cmp     byte ptr [rcx+19h], 2
0x180059ff9  jb      loc_18005A0B0
0x180059fff  mov     edx, 15h
0x18005a004  jmp     short loc_180059FB5
0x18005a006  cmp     [rbp+57h+var_B0], 0
0x18005a00b  mov     rbx, [rbp+57h+var_78.pItf]
0x18005a00f  mov     [rbp+57h+var_A8], rbx
0x18005a013  jz      short loc_18005A01E
0x18005a015  lea     rcx, [rbp+57h+var_B0]; struct IUnknown **
0x18005a019  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18005a01e  mov     rax, [rbx]
0x18005a021  lea     r8, [rbp+57h+var_B0]
0x18005a025  xor     edx, edx
0x18005a027  mov     rcx, rbx
0x18005a02a  mov     rax, [rax+18h]
0x18005a02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a033  mov     ebx, eax
0x18005a035  test    eax, eax
0x18005a037  jns     short loc_18005A062
0x18005a039  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a040  lea     rax, WPP_GLOBAL_Control
0x18005a047  cmp     rcx, rax
0x18005a04a  jz      short loc_18005A0B0
0x18005a04c  test    byte ptr [rcx+1Ch], 2
0x18005a050  jz      short loc_18005A0B0
0x18005a052  cmp     byte ptr [rcx+19h], 2
0x18005a056  jb      short loc_18005A0B0
0x18005a058  mov     edx, 16h
0x18005a05d  jmp     loc_180059FB5
0x18005a062  mov     rcx, [rbp+57h+var_B0]
0x18005a066  mov     rax, [rcx]
0x18005a069  mov     rax, [rax+20h]
0x18005a06d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a072  mov     ebx, eax
0x18005a074  test    eax, eax
0x18005a076  jns     short loc_18005A0A1
0x18005a078  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a07f  lea     rax, WPP_GLOBAL_Control
0x18005a086  cmp     rcx, rax
0x18005a089  jz      short loc_18005A0B0
0x18005a08b  test    byte ptr [rcx+1Ch], 2
0x18005a08f  jz      short loc_18005A0B0
0x18005a091  cmp     byte ptr [rcx+19h], 2
0x18005a095  jb      short loc_18005A0B0
0x18005a097  mov     edx, 17h
0x18005a09c  jmp     loc_180059FB5
0x18005a0a1  mov     rax, [rbp+57h+var_B0]
0x18005a0a5  mov     [rsi], rax
0x18005a0a8  mov     [rbp+57h+var_B0], 0
0x18005a0b0  test    edi, edi
0x18005a0b2  jnz     short loc_18005A0BA
0x18005a0b4  call    cs:__imp_CoUninitialize
0x18005a0ba  lea     rcx, [rbp+57h+var_B0]
0x18005a0be  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a0c3  lea     rcx, [rbp+57h+var_A8]
0x18005a0c7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a0cc  mov     eax, ebx
0x18005a0ce  mov     rcx, [rbp+57h+var_28]
0x18005a0d2  xor     rcx, rsp; StackCookie
0x18005a0d5  call    __security_check_cookie
0x18005a0da  add     rsp, 0C8h
0x18005a0e1  pop     rdi
0x18005a0e2  pop     rsi
0x18005a0e3  pop     rbx
0x18005a0e4  pop     rbp
0x18005a0e5  retn
```
