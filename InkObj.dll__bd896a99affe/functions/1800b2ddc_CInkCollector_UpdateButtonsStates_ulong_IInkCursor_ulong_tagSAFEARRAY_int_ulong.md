# CInkCollector::_UpdateButtonsStates(ulong,IInkCursor *,ulong,tagSAFEARRAY * *,int,ulong *)

- ea: `0x1800b2ddc`
- end: `0x1800b32c7`
- name: `?_UpdateButtonsStates@CInkCollector@@AEAAJKPEAUIInkCursor@@KPEAPEAUtagSAFEARRAY@@HPEAK@Z`
- size: `1259`
- prototype: `__int64 __fastcall(CInkCollector *__hidden this, unsigned int, struct IInkCursor *, unsigned int, struct tagSAFEARRAY **, int, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800aab90`
- `0x1800b1154`
- `0x1800b1740`

## callees

- `0x180001c20`
- `0x1800365f8`
- `0x180036824`
- `0x1800a9ecc`
- `0x1800a9f00`
- `0x1800ac084`
- `0x1800ac134`
- `0x1800b2ddc`
- `0x18010c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800b2fca`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b2fca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b3013`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b3013`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800b327c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800b327c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800b30f7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800b30f7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800b326f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800b326f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800b30dd`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800b30dd`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800b2fab`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800b2fab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3025`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3025`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInkCollector::_UpdateButtonsStates(
        CInkCollector *this,
        int a2,
        struct IInkCursor *a3,
        unsigned int a4,
        struct tagSAFEARRAY **a5,
        int a6,
        unsigned int *a7)
{
  HRESULT v9; // ebx
  __int64 v10; // rax
  int v11; // r14d
  int v12; // esi
  struct tagSAFEARRAY **v13; // rdi
  __int64 v14; // rax
  signed int v15; // r14d
  __int64 v16; // xmm6_8
  const IID *v17; // rdi
  int v18; // r8d
  __int64 v19; // r9
  OLECHAR *v20; // rdi
  int v21; // esi
  struct IInkCursor *v22; // rcx
  int v23; // eax
  SAFEARRAY *Vector; // rax
  signed int v25; // esi
  unsigned int *v26; // r12
  __int64 v27; // xmm6_8
  int v28; // r14d
  LPOLESTR v29; // rcx
  int v30; // eax
  LPOLESTR v31; // rcx
  int v32; // eax
  LPOLESTR lpsz; // [rsp+20h] [rbp-B8h] BYREF
  ULONG cElements; // [rsp+28h] [rbp-B0h] BYREF
  unsigned int v36; // [rsp+2Ch] [rbp-ACh]
  __int64 v37; // [rsp+30h] [rbp-A8h] BYREF
  __int128 v38; // [rsp+38h] [rbp-A0h]
  __int64 v39; // [rsp+48h] [rbp-90h]
  void *ppvData[2]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v41[16]; // [rsp+60h] [rbp-78h] BYREF
  __int128 v42; // [rsp+70h] [rbp-68h] BYREF
  __int64 v43; // [rsp+80h] [rbp-58h]
  struct IInkCursor *v45; // [rsp+F0h] [rbp+18h] BYREF
  unsigned int v46; // [rsp+F8h] [rbp+20h]

  v46 = a4;
  v45 = a3;
  v9 = 0;
  v10 = (__int64)&a3[6].lpVtbl + 4;
  if ( !a3 )
    v10 = 60;
  v11 = *(_DWORD *)v10 ^ a4;
  v36 = v11;
  v12 = a6;
  v13 = a5;
  if ( a6 != 1 || a5 || v11 )
  {
    v14 = (__int64)&a3[6].lpVtbl + 4;
    if ( !a3 )
      v14 = 60;
    try
    {
      *(_DWORD *)v14 = a4;
      cElements = 0;
      v37 = 0;
      v9 = ((__int64 (__fastcall *)(struct IInkCursor *, __int64 *))a3->lpVtbl->get_Buttons)(a3, &v37);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, ULONG *))(*(_QWORD *)v37 + 56LL))(v37, &cElements);
        if ( v9 >= 0 )
        {
          v38 = 0;
          v39 = 0;
          LOWORD(v38) = 3;
          if ( v12 && !v13 )
          {
            v15 = 0;
            v16 = v39;
            while ( v15 < (int)cElements )
            {
              if ( ((1 << v15) & v36) != 0 )
              {
                v45 = 0;
                v17 = 0;
                CInkAutoDataLock::CInkAutoDataLock(
                  (CInkAutoDataLock *)ppvData,
                  (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
                if ( *((_WORD *)this + 192) == 0xFFFF )
                {
                  v18 = 0;
                  v19 = *((_QWORD *)this + 72);
                  while ( v18 < (unsigned __int64)((*((_QWORD *)this + 73) - v19) / 24) )
                  {
                    if ( a2 == *(_DWORD *)(v19 + 24LL * v18 + 8) )
                    {
                      v17 = (const IID *)(*(_QWORD *)(v19 + 24LL * v18 + 16) + 16LL * (unsigned int)v15);
                      break;
                    }
                    ++v18;
                  }
                }
                CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)ppvData);
                if ( !v17 )
                {
                  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v45);
                  goto LABEL_68;
                }
                lpsz = 0;
                v9 = StringFromCLSID(v17, &lpsz);
                if ( v9 >= 0 )
                {
                  LOWORD(v38) = 8;
                  v20 = SysAllocString(lpsz);
                  *((_QWORD *)&v38 + 1) = v20;
                  if ( v20 )
                  {
                    v42 = v38;
                    v43 = v16;
                    v9 = (*(__int64 (__fastcall **)(__int64, __int128 *, struct IInkCursor **))(*(_QWORD *)v37 + 72LL))(
                           v37,
                           &v42,
                           &v45);
                    SysFreeString(v20);
                  }
                  else
                  {
                    v9 = -2147024882;
                  }
                  CoTaskMemFree(lpsz);
                  if ( v9 >= 0 )
                  {
                    v21 = v46 & (1 << v15);
                    if ( v45 )
                      v22 = v45 - 1;
                    else
                      v22 = 0;
                    CThreadSafeLong::operator=((LPCRITICAL_SECTION)&v22[8]);
                    CInkAutoDataLock::CInkAutoDataLock(
                      (CInkAutoDataLock *)v41,
                      (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
                    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v41);
                    v23 = *((_DWORD *)this + 113);
                    if ( v21 )
                    {
                      if ( (v23 & 0x10) != 0 )
                        CProxy_IInkCollectorEvents<CInkCollector>::Fire_CursorButtonDown((char *)this + 112, a3, v45);
                    }
                    else if ( (v23 & 0x20) != 0 )
                    {
                      CProxy_IInkCollectorEvents<CInkCollector>::Fire_CursorButtonUp((char *)this + 112, a3, v45);
                    }
                  }
                }
                ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v45);
              }
              ++v15;
            }
            goto LABEL_68;
          }
          ppvData[0] = 0;
          if ( !v13 )
            goto LABEL_41;
          Vector = SafeArrayCreateVector(3u, 0, cElements);
          *v13 = Vector;
          if ( Vector )
          {
            v9 = SafeArrayAccessData(Vector, ppvData);
            if ( v9 >= 0 )
            {
LABEL_41:
              v25 = 0;
              v26 = a7;
              v27 = v39;
              while ( v9 >= 0 && v25 < (int)cElements )
              {
                lpsz = 0;
                DWORD2(v38) = v25;
                v42 = v38;
                v43 = v27;
                v9 = (*(__int64 (__fastcall **)(__int64, __int128 *, LPOLESTR *))(*(_QWORD *)v37 + 72LL))(
                       v37,
                       &v42,
                       &lpsz);
                if ( v9 >= 0 )
                {
                  v28 = v46 & (1 << v25);
                  if ( lpsz )
                    v29 = lpsz - 4;
                  else
                    v29 = 0;
                  CThreadSafeLong::operator=((LPCRITICAL_SECTION)(v29 + 32));
                  CInkAutoDataLock::CInkAutoDataLock(
                    (CInkAutoDataLock *)v41,
                    (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
                  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v41);
                  if ( !v26 && ((1 << v25) & v36) != 0 )
                  {
                    v30 = *((_DWORD *)this + 113);
                    if ( v28 )
                    {
                      if ( (v30 & 0x10) != 0 )
                        CProxy_IInkCollectorEvents<CInkCollector>::Fire_CursorButtonDown((char *)this + 112, v45, lpsz);
                    }
                    else if ( (v30 & 0x20) != 0 )
                    {
                      CProxy_IInkCollectorEvents<CInkCollector>::Fire_CursorButtonUp((char *)this + 112, v45, lpsz);
                    }
                  }
                  if ( v13 )
                  {
                    if ( lpsz )
                      v31 = lpsz - 4;
                    else
                      v31 = 0;
                    v32 = CThreadSafeLong::operator long((LPCRITICAL_SECTION)(v31 + 32));
                    *((_DWORD *)ppvData[0] + v25) = v32;
                  }
                }
                ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&lpsz);
                ++v25;
              }
              if ( v13 )
              {
                SafeArrayUnaccessData(*v13);
                if ( v9 < 0 )
                {
                  SafeArrayDestroy(*v13);
                  *v13 = 0;
                }
              }
              if ( v26 )
                *v26 = v36;
            }
          }
          else
          {
            v9 = -2147024882;
          }
        }
      }
LABEL_68:
      ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v37);
    }
    catch ( ... )
    {
      v46 = ReportWispException();
      return v46;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800b2ddc  mov     rax, rsp
0x1800b2ddf  mov     [rax+20h], r9d
0x1800b2de3  mov     [rax+18h], r8
0x1800b2de7  mov     [rax+10h], edx
0x1800b2dea  push    rbx
0x1800b2deb  push    rsi
0x1800b2dec  push    rdi
0x1800b2ded  push    r12
0x1800b2def  push    r13
0x1800b2df1  push    r14
0x1800b2df3  push    r15
0x1800b2df5  sub     rsp, 0A0h
0x1800b2dfc  movaps  xmmword ptr [rax-48h], xmm6
0x1800b2e00  mov     r15, r8
0x1800b2e03  mov     r13, rcx
0x1800b2e06  xor     ebx, ebx
0x1800b2e08  lea     rax, [r8+34h]
0x1800b2e0c  lea     ecx, [rbx+3Ch]
0x1800b2e0f  test    r8, r8
0x1800b2e12  cmovz   rax, rcx
0x1800b2e16  mov     r14d, r9d
0x1800b2e19  xor     r14d, [rax]
0x1800b2e1c  mov     [rsp+0D8h+var_AC], r14d
0x1800b2e21  mov     esi, [rsp+0D8h+arg_28]
0x1800b2e28  mov     rdi, [rsp+0D8h+arg_20]
0x1800b2e30  cmp     esi, 1
0x1800b2e33  jnz     short loc_1800B2E43
0x1800b2e35  test    rdi, rdi
0x1800b2e38  jnz     short loc_1800B2E43
0x1800b2e3a  test    r14d, r14d
0x1800b2e3d  jz      loc_1800B32A1
0x1800b2e43  lea     rax, [r8+34h]
0x1800b2e47  test    r15, r15
0x1800b2e4a  cmovz   rax, rcx
0x1800b2e4e  mov     [rax], r9d
0x1800b2e51  mov     [rsp+0D8h+cElements], 0
0x1800b2e59  mov     [rsp+0D8h+var_A8], 0
0x1800b2e62  mov     rax, [r8]
0x1800b2e65  lea     rdx, [rsp+0D8h+var_A8]
0x1800b2e6a  mov     rcx, r15
0x1800b2e6d  mov     rax, [rax+68h]
0x1800b2e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2e76  mov     ebx, eax
0x1800b2e78  test    eax, eax
0x1800b2e7a  js      loc_1800B3296
0x1800b2e80  mov     rcx, [rsp+0D8h+var_A8]
0x1800b2e85  mov     rax, [rcx]
0x1800b2e88  lea     rdx, [rsp+0D8h+cElements]
0x1800b2e8d  mov     rax, [rax+38h]
0x1800b2e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2e96  mov     ebx, eax
0x1800b2e98  test    eax, eax
0x1800b2e9a  js      loc_1800B3296
0x1800b2ea0  xorps   xmm0, xmm0
0x1800b2ea3  xor     eax, eax
0x1800b2ea5  movups  [rsp+0D8h+var_A0], xmm0
0x1800b2eaa  mov     [rsp+0D8h+var_90], rax
0x1800b2eaf  lea     ecx, [rax+3]; vt
0x1800b2eb2  mov     word ptr [rsp+0D8h+var_A0], cx
0x1800b2eb7  test    esi, esi
0x1800b2eb9  jz      loc_1800B30CC
0x1800b2ebf  test    rdi, rdi
0x1800b2ec2  jnz     loc_1800B30CC
0x1800b2ec8  xor     r14d, r14d
0x1800b2ecb  movsd   xmm6, [rsp+0D8h+var_90]
0x1800b2ed1  cmp     r14d, [rsp+0D8h+cElements]
0x1800b2ed6  jge     loc_1800B3296
0x1800b2edc  mov     ecx, r14d
0x1800b2edf  mov     esi, 1
0x1800b2ee4  shl     esi, cl
0x1800b2ee6  test    [rsp+0D8h+var_AC], esi
0x1800b2eea  jz      loc_1800B30C4
0x1800b2ef0  mov     [rsp+0D8h+arg_10], 0
0x1800b2efc  xor     edi, edi
0x1800b2efe  lea     r12, [r13+110h]
0x1800b2f05  mov     rdx, r12; struct _RTL_CRITICAL_SECTION *
0x1800b2f08  lea     rcx, [rsp+0D8h+ppvData]; this
0x1800b2f0d  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800b2f12  or      eax, 0FFFFFFFFh
0x1800b2f15  cmp     ax, [r13+180h]
0x1800b2f1d  jnz     short loc_1800B2F79
0x1800b2f1f  xor     r8d, r8d
0x1800b2f22  mov     r9, [r13+240h]
0x1800b2f29  mov     rcx, [r13+248h]
0x1800b2f30  sub     rcx, r9
0x1800b2f33  mov     rax, 2AAAAAAAAAAAAAABh
0x1800b2f3d  imul    rcx
0x1800b2f40  sar     rdx, 2
0x1800b2f44  mov     rax, rdx
0x1800b2f47  shr     rax, 3Fh
0x1800b2f4b  add     rdx, rax
0x1800b2f4e  movsxd  rax, r8d
0x1800b2f51  cmp     rax, rdx
0x1800b2f54  jnb     short loc_1800B2F79
0x1800b2f56  lea     rcx, [rax+rax*2]
0x1800b2f5a  mov     eax, [rsp+0D8h+arg_8]
0x1800b2f61  cmp     eax, [r9+rcx*8+8]
0x1800b2f66  jz      short loc_1800B2F6D
0x1800b2f68  inc     r8d
0x1800b2f6b  jmp     short loc_1800B2F4E
0x1800b2f6d  mov     edi, r14d
0x1800b2f70  shl     rdi, 4
0x1800b2f74  add     rdi, [r9+rcx*8+10h]
0x1800b2f79  lea     rcx, [rsp+0D8h+ppvData]; this
0x1800b2f7e  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800b2f83  test    rdi, rdi
0x1800b2f86  jnz     short loc_1800B2F9A
0x1800b2f88  lea     rcx, [rsp+0D8h+arg_10]; void *
0x1800b2f90  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800b2f95  jmp     loc_1800B3296
0x1800b2f9a  mov     [rsp+0D8h+lpsz], 0
0x1800b2fa3  lea     rdx, [rsp+0D8h+lpsz]; lplpsz
0x1800b2fa8  mov     rcx, rdi; rclsid
0x1800b2fab  call    cs:__imp_StringFromCLSID
0x1800b2fb1  mov     ebx, eax
0x1800b2fb3  test    eax, eax
0x1800b2fb5  js      loc_1800B30B7
0x1800b2fbb  mov     eax, 8
0x1800b2fc0  mov     word ptr [rsp+0D8h+var_A0], ax
0x1800b2fc5  mov     rcx, [rsp+0D8h+lpsz]; psz
0x1800b2fca  call    cs:__imp_SysAllocString
0x1800b2fd0  mov     rdi, rax
0x1800b2fd3  mov     qword ptr [rsp+0D8h+var_A0+8], rax
0x1800b2fd8  test    rax, rax
0x1800b2fdb  jz      short loc_1800B301B
0x1800b2fdd  mov     rcx, [rsp+0D8h+var_A8]
0x1800b2fe2  movups  xmm0, [rsp+0D8h+var_A0]
0x1800b2fe7  movaps  [rsp+0D8h+var_68], xmm0
0x1800b2fec  movsd   [rsp+0D8h+var_58], xmm6
0x1800b2ff5  mov     rax, [rcx]
0x1800b2ff8  lea     r8, [rsp+0D8h+arg_10]
0x1800b3000  lea     rdx, [rsp+0D8h+var_68]
0x1800b3005  mov     rax, [rax+48h]
0x1800b3009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b300e  mov     ebx, eax
0x1800b3010  mov     rcx, rdi; bstrString
0x1800b3013  call    cs:__imp_SysFreeString
0x1800b3019  jmp     short loc_1800B3020
0x1800b301b  mov     ebx, 8007000Eh
0x1800b3020  mov     rcx, [rsp+0D8h+lpsz]; pv
0x1800b3025  call    cs:__imp_CoTaskMemFree
0x1800b302b  test    ebx, ebx
0x1800b302d  js      loc_1800B30B7
0x1800b3033  and     esi, [rsp+0D8h+arg_18]
0x1800b303a  mov     eax, esi
0x1800b303c  neg     eax
0x1800b303e  sbb     edx, edx
0x1800b3040  neg     edx
0x1800b3042  inc     edx
0x1800b3044  mov     rax, [rsp+0D8h+arg_10]
0x1800b304c  test    rax, rax
0x1800b304f  jz      short loc_1800B3057
0x1800b3051  lea     rcx, [rax-8]
0x1800b3055  jmp     short loc_1800B3059
0x1800b3057  xor     ecx, ecx
0x1800b3059  add     rcx, 40h ; '@'; lpCriticalSection
0x1800b305d  call    ??4CThreadSafeLong@@QEAAJJ@Z; CThreadSafeLong::operator=(long)
0x1800b3062  mov     rdx, r12; struct _RTL_CRITICAL_SECTION *
0x1800b3065  lea     rcx, [rsp+0D8h+var_78]; this
0x1800b306a  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800b306f  lea     rcx, [rsp+0D8h+var_78]; this
0x1800b3074  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800b3079  mov     eax, [r13+1C4h]
0x1800b3080  test    esi, esi
0x1800b3082  jz      short loc_1800B309E
0x1800b3084  test    al, 10h
0x1800b3086  jz      short loc_1800B30B7
0x1800b3088  lea     rcx, [r13+70h]
0x1800b308c  mov     r8, [rsp+0D8h+arg_10]
0x1800b3094  mov     rdx, r15
0x1800b3097  call    ?Fire_CursorButtonDown@?$CProxy_IInkCollectorEvents@VCInkCollector@@@@QEAAJPEAUIInkCursor@@PEAUIInkCursorButton@@@Z; CProxy_IInkCollectorEvents<CInkCollector>::Fire_CursorButtonDown(IInkCursor *,IInkCursorButton *)
0x1800b309c  jmp     short loc_1800B30B7
0x1800b309e  test    al, 20h
0x1800b30a0  jz      short loc_1800B30B7
0x1800b30a2  lea     rcx, [r13+70h]
0x1800b30a6  mov     r8, [rsp+0D8h+arg_10]
0x1800b30ae  mov     rdx, r15
0x1800b30b1  call    ?Fire_CursorButtonUp@?$CProxy_IInkCollectorEvents@VCInkCollector@@@@QEAAJPEAUIInkCursor@@PEAUIInkCursorButton@@@Z; CProxy_IInkCollectorEvents<CInkCollector>::Fire_CursorButtonUp(IInkCursor *,IInkCursorButton *)
0x1800b30b6  nop
0x1800b30b7  lea     rcx, [rsp+0D8h+arg_10]; void *
0x1800b30bf  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800b30c4  inc     r14d
0x1800b30c7  jmp     loc_1800B2ED1
0x1800b30cc  mov     [rsp+0D8h+ppvData], rax
0x1800b30d1  test    rdi, rdi
0x1800b30d4  jz      short loc_1800B3107
0x1800b30d6  mov     r8d, [rsp+0D8h+cElements]; cElements
0x1800b30db  xor     edx, edx; lLbound
0x1800b30dd  call    cs:__imp_SafeArrayCreateVector
0x1800b30e3  mov     [rdi], rax
0x1800b30e6  test    rax, rax
0x1800b30e9  jz      loc_1800B319B
0x1800b30ef  lea     rdx, [rsp+0D8h+ppvData]; ppvData
0x1800b30f4  mov     rcx, rax; psa
0x1800b30f7  call    cs:__imp_SafeArrayAccessData
0x1800b30fd  mov     ebx, eax
0x1800b30ff  test    eax, eax
0x1800b3101  js      loc_1800B3296
0x1800b3107  xor     esi, esi
0x1800b3109  mov     r12, [rsp+0D8h+arg_30]
0x1800b3111  movsd   xmm6, [rsp+0D8h+var_90]
0x1800b3117  test    ebx, ebx
0x1800b3119  js      loc_1800B3267
0x1800b311f  cmp     esi, [rsp+0D8h+cElements]
0x1800b3123  jge     loc_1800B3267
0x1800b3129  mov     [rsp+0D8h+lpsz], 0
0x1800b3132  mov     dword ptr [rsp+0D8h+var_A0+8], esi
0x1800b3136  mov     rcx, [rsp+0D8h+var_A8]
0x1800b313b  movups  xmm0, [rsp+0D8h+var_A0]
0x1800b3140  movaps  [rsp+0D8h+var_68], xmm0
0x1800b3145  movsd   [rsp+0D8h+var_58], xmm6
0x1800b314e  mov     rax, [rcx]
0x1800b3151  lea     r8, [rsp+0D8h+lpsz]
0x1800b3156  lea     rdx, [rsp+0D8h+var_68]
0x1800b315b  mov     rax, [rax+48h]
0x1800b315f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3164  mov     ebx, eax
0x1800b3166  test    eax, eax
0x1800b3168  js      loc_1800B3256
0x1800b316e  mov     ecx, esi
0x1800b3170  mov     r15d, 1
0x1800b3176  shl     r15d, cl
0x1800b3179  mov     r14d, r15d
0x1800b317c  and     r14d, [rsp+0D8h+arg_18]
0x1800b3184  cmp     [rsp+0D8h+arg_28], 0
0x1800b318c  jz      short loc_1800B31A5
0x1800b318e  mov     eax, r14d
0x1800b3191  neg     eax
0x1800b3193  sbb     edx, edx
0x1800b3195  neg     edx
0x1800b3197  inc     edx
0x1800b3199  jmp     short loc_1800B31A7
0x1800b319b  mov     ebx, 8007000Eh
0x1800b31a0  jmp     loc_1800B3296
0x1800b31a5  xor     edx, edx
0x1800b31a7  mov     rax, [rsp+0D8h+lpsz]
0x1800b31ac  test    rax, rax
0x1800b31af  jz      short loc_1800B31B7
0x1800b31b1  lea     rcx, [rax-8]
0x1800b31b5  jmp     short loc_1800B31B9
0x1800b31b7  xor     ecx, ecx
0x1800b31b9  add     rcx, 40h ; '@'; lpCriticalSection
0x1800b31bd  call    ??4CThreadSafeLong@@QEAAJJ@Z; CThreadSafeLong::operator=(long)
0x1800b31c2  lea     rdx, [r13+110h]; struct _RTL_CRITICAL_SECTION *
0x1800b31c9  lea     rcx, [rsp+0D8h+var_78]; this
0x1800b31ce  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800b31d3  lea     rcx, [rsp+0D8h+var_78]; this
0x1800b31d8  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800b31dd  test    r12, r12
0x1800b31e0  jnz     short loc_1800B322B
0x1800b31e2  test    [rsp+0D8h+var_AC], r15d
0x1800b31e7  jz      short loc_1800B322B
0x1800b31e9  mov     eax, [r13+1C4h]
0x1800b31f0  test    r14d, r14d
0x1800b31f3  jz      short loc_1800B3211
0x1800b31f5  test    al, 10h
0x1800b31f7  jz      short loc_1800B322B
0x1800b31f9  lea     rcx, [r13+70h]
0x1800b31fd  mov     r8, [rsp+0D8h+lpsz]
0x1800b3202  mov     rdx, [rsp+0D8h+arg_10]
0x1800b320a  call    ?Fire_CursorButtonDown@?$CProxy_IInkCollectorEvents@VCInkCollector@@@@QEAAJPEAUIInkCursor@@PEAUIInkCursorButton@@@Z; CProxy_IInkCollectorEvents<CInkCollector>::Fire_CursorButtonDown(IInkCursor *,IInkCursorButton *)
0x1800b320f  jmp     short loc_1800B322B
0x1800b3211  test    al, 20h
0x1800b3213  jz      short loc_1800B322B
0x1800b3215  lea     rcx, [r13+70h]
0x1800b3219  mov     r8, [rsp+0D8h+lpsz]
0x1800b321e  mov     rdx, [rsp+0D8h+arg_10]
0x1800b3226  call    ?Fire_CursorButtonUp@?$CProxy_IInkCollectorEvents@VCInkCollector@@@@QEAAJPEAUIInkCursor@@PEAUIInkCursorButton@@@Z; CProxy_IInkCollectorEvents<CInkCollector>::Fire_CursorButtonUp(IInkCursor *,IInkCursorButton *)
0x1800b322b  test    rdi, rdi
0x1800b322e  jz      short loc_1800B3256
0x1800b3230  mov     rax, [rsp+0D8h+lpsz]
0x1800b3235  test    rax, rax
0x1800b3238  jz      short loc_1800B3240
0x1800b323a  lea     rcx, [rax-8]
0x1800b323e  jmp     short loc_1800B3242
0x1800b3240  xor     ecx, ecx
0x1800b3242  add     rcx, 40h ; '@'; lpCriticalSection
0x1800b3246  call    ??BCThreadSafeLong@@QEAAJXZ; CThreadSafeLong::operator long(void)
0x1800b324b  movsxd  rdx, esi
0x1800b324e  mov     rcx, [rsp+0D8h+ppvData]
0x1800b3253  mov     [rcx+rdx*4], eax
0x1800b3256  lea     rcx, [rsp+0D8h+lpsz]; void *
0x1800b325b  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800b3260  inc     esi
0x1800b3262  jmp     loc_1800B3117
0x1800b3267  test    rdi, rdi
0x1800b326a  jz      short loc_1800B3289
0x1800b326c  mov     rcx, [rdi]; psa
0x1800b326f  call    cs:__imp_SafeArrayUnaccessData
0x1800b3275  test    ebx, ebx
0x1800b3277  jns     short loc_1800B3289
0x1800b3279  mov     rcx, [rdi]; psa
0x1800b327c  call    cs:__imp_SafeArrayDestroy
0x1800b3282  mov     qword ptr [rdi], 0
0x1800b3289  test    r12, r12
0x1800b328c  jz      short loc_1800B3296
0x1800b328e  mov     eax, [rsp+0D8h+var_AC]
0x1800b3292  mov     [r12], eax
0x1800b3296  lea     rcx, [rsp+0D8h+var_A8]; void *
0x1800b329b  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
  ... truncated ...
```
