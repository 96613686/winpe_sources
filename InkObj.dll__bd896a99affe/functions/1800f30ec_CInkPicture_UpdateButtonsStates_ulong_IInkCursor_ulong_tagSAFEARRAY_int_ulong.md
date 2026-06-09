# CInkPicture::_UpdateButtonsStates(ulong,IInkCursor *,ulong,tagSAFEARRAY * *,int,ulong *)

- ea: `0x1800f30ec`
- end: `0x1800f35e3`
- name: `?_UpdateButtonsStates@CInkPicture@@AEAAJKPEAUIInkCursor@@KPEAPEAUtagSAFEARRAY@@HPEAK@Z`
- size: `1271`
- prototype: `__int64 __fastcall(CInkPicture *__hidden this, unsigned int, struct IInkCursor *, unsigned int, struct tagSAFEARRAY **, int, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e6dd0`
- `0x1800f0988`
- `0x1800f0fb4`

## callees

- `0x180001c20`
- `0x1800365f8`
- `0x180036824`
- `0x1800a9ecc`
- `0x1800a9f00`
- `0x1800e8dbc`
- `0x1800e8e6c`
- `0x1800f30ec`
- `0x18010c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800f32da`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f32da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f3323`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f3323`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f3598`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f3598`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f340d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f340d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f358b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f358b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800f33f3`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800f33f3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800f32bb`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800f32bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f3335`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f3335`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInkPicture::_UpdateButtonsStates(
        CInkPicture *this,
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
                  (struct _RTL_CRITICAL_SECTION *)((char *)this + 496));
                if ( *((_WORD *)this + 304) == 0xFFFF )
                {
                  v18 = 0;
                  v19 = *((_QWORD *)this + 102);
                  while ( v18 < (unsigned __int64)((*((_QWORD *)this + 103) - v19) / 24) )
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
                      (struct _RTL_CRITICAL_SECTION *)((char *)this + 496));
                    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v41);
                    v23 = *((_DWORD *)this + 169);
                    if ( v21 )
                    {
                      if ( (v23 & 0x10) != 0 )
                        CProxy_IInkPictureEvents<CInkPicture>::Fire_CursorButtonDown((char *)this + 336, a3, v45);
                    }
                    else if ( (v23 & 0x20) != 0 )
                    {
                      CProxy_IInkPictureEvents<CInkPicture>::Fire_CursorButtonUp((char *)this + 336, a3, v45);
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
                    (struct _RTL_CRITICAL_SECTION *)((char *)this + 496));
                  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v41);
                  if ( !v26 && ((1 << v25) & v36) != 0 )
                  {
                    v30 = *((_DWORD *)this + 169);
                    if ( v28 )
                    {
                      if ( (v30 & 0x10) != 0 )
                        CProxy_IInkPictureEvents<CInkPicture>::Fire_CursorButtonDown((char *)this + 336, v45, lpsz);
                    }
                    else if ( (v30 & 0x20) != 0 )
                    {
                      CProxy_IInkPictureEvents<CInkPicture>::Fire_CursorButtonUp((char *)this + 336, v45, lpsz);
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
0x1800f30ec  mov     rax, rsp
0x1800f30ef  mov     [rax+20h], r9d
0x1800f30f3  mov     [rax+18h], r8
0x1800f30f7  mov     [rax+10h], edx
0x1800f30fa  push    rbx
0x1800f30fb  push    rsi
0x1800f30fc  push    rdi
0x1800f30fd  push    r12
0x1800f30ff  push    r13
0x1800f3101  push    r14
0x1800f3103  push    r15
0x1800f3105  sub     rsp, 0A0h
0x1800f310c  movaps  xmmword ptr [rax-48h], xmm6
0x1800f3110  mov     r15, r8
0x1800f3113  mov     r13, rcx
0x1800f3116  xor     ebx, ebx
0x1800f3118  lea     rax, [r8+34h]
0x1800f311c  lea     ecx, [rbx+3Ch]
0x1800f311f  test    r8, r8
0x1800f3122  cmovz   rax, rcx
0x1800f3126  mov     r14d, r9d
0x1800f3129  xor     r14d, [rax]
0x1800f312c  mov     [rsp+0D8h+var_AC], r14d
0x1800f3131  mov     esi, [rsp+0D8h+arg_28]
0x1800f3138  mov     rdi, [rsp+0D8h+arg_20]
0x1800f3140  cmp     esi, 1
0x1800f3143  jnz     short loc_1800F3153
0x1800f3145  test    rdi, rdi
0x1800f3148  jnz     short loc_1800F3153
0x1800f314a  test    r14d, r14d
0x1800f314d  jz      loc_1800F35BD
0x1800f3153  lea     rax, [r8+34h]
0x1800f3157  test    r15, r15
0x1800f315a  cmovz   rax, rcx
0x1800f315e  mov     [rax], r9d
0x1800f3161  mov     [rsp+0D8h+cElements], 0
0x1800f3169  mov     [rsp+0D8h+var_A8], 0
0x1800f3172  mov     rax, [r8]
0x1800f3175  lea     rdx, [rsp+0D8h+var_A8]
0x1800f317a  mov     rcx, r15
0x1800f317d  mov     rax, [rax+68h]
0x1800f3181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3186  mov     ebx, eax
0x1800f3188  test    eax, eax
0x1800f318a  js      loc_1800F35B2
0x1800f3190  mov     rcx, [rsp+0D8h+var_A8]
0x1800f3195  mov     rax, [rcx]
0x1800f3198  lea     rdx, [rsp+0D8h+cElements]
0x1800f319d  mov     rax, [rax+38h]
0x1800f31a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f31a6  mov     ebx, eax
0x1800f31a8  test    eax, eax
0x1800f31aa  js      loc_1800F35B2
0x1800f31b0  xorps   xmm0, xmm0
0x1800f31b3  xor     eax, eax
0x1800f31b5  movups  [rsp+0D8h+var_A0], xmm0
0x1800f31ba  mov     [rsp+0D8h+var_90], rax
0x1800f31bf  lea     ecx, [rax+3]; vt
0x1800f31c2  mov     word ptr [rsp+0D8h+var_A0], cx
0x1800f31c7  test    esi, esi
0x1800f31c9  jz      loc_1800F33E2
0x1800f31cf  test    rdi, rdi
0x1800f31d2  jnz     loc_1800F33E2
0x1800f31d8  xor     r14d, r14d
0x1800f31db  movsd   xmm6, [rsp+0D8h+var_90]
0x1800f31e1  cmp     r14d, [rsp+0D8h+cElements]
0x1800f31e6  jge     loc_1800F35B2
0x1800f31ec  mov     ecx, r14d
0x1800f31ef  mov     esi, 1
0x1800f31f4  shl     esi, cl
0x1800f31f6  test    [rsp+0D8h+var_AC], esi
0x1800f31fa  jz      loc_1800F33DA
0x1800f3200  mov     [rsp+0D8h+arg_10], 0
0x1800f320c  xor     edi, edi
0x1800f320e  lea     r12, [r13+1F0h]
0x1800f3215  mov     rdx, r12; struct _RTL_CRITICAL_SECTION *
0x1800f3218  lea     rcx, [rsp+0D8h+ppvData]; this
0x1800f321d  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800f3222  or      eax, 0FFFFFFFFh
0x1800f3225  cmp     ax, [r13+260h]
0x1800f322d  jnz     short loc_1800F3289
0x1800f322f  xor     r8d, r8d
0x1800f3232  mov     r9, [r13+330h]
0x1800f3239  mov     rcx, [r13+338h]
0x1800f3240  sub     rcx, r9
0x1800f3243  mov     rax, 2AAAAAAAAAAAAAABh
0x1800f324d  imul    rcx
0x1800f3250  sar     rdx, 2
0x1800f3254  mov     rax, rdx
0x1800f3257  shr     rax, 3Fh
0x1800f325b  add     rdx, rax
0x1800f325e  movsxd  rax, r8d
0x1800f3261  cmp     rax, rdx
0x1800f3264  jnb     short loc_1800F3289
0x1800f3266  lea     rcx, [rax+rax*2]
0x1800f326a  mov     eax, [rsp+0D8h+arg_8]
0x1800f3271  cmp     eax, [r9+rcx*8+8]
0x1800f3276  jz      short loc_1800F327D
0x1800f3278  inc     r8d
0x1800f327b  jmp     short loc_1800F325E
0x1800f327d  mov     edi, r14d
0x1800f3280  shl     rdi, 4
0x1800f3284  add     rdi, [r9+rcx*8+10h]
0x1800f3289  lea     rcx, [rsp+0D8h+ppvData]; this
0x1800f328e  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800f3293  test    rdi, rdi
0x1800f3296  jnz     short loc_1800F32AA
0x1800f3298  lea     rcx, [rsp+0D8h+arg_10]; void *
0x1800f32a0  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800f32a5  jmp     loc_1800F35B2
0x1800f32aa  mov     [rsp+0D8h+lpsz], 0
0x1800f32b3  lea     rdx, [rsp+0D8h+lpsz]; lplpsz
0x1800f32b8  mov     rcx, rdi; rclsid
0x1800f32bb  call    cs:__imp_StringFromCLSID
0x1800f32c1  mov     ebx, eax
0x1800f32c3  test    eax, eax
0x1800f32c5  js      loc_1800F33CD
0x1800f32cb  mov     eax, 8
0x1800f32d0  mov     word ptr [rsp+0D8h+var_A0], ax
0x1800f32d5  mov     rcx, [rsp+0D8h+lpsz]; psz
0x1800f32da  call    cs:__imp_SysAllocString
0x1800f32e0  mov     rdi, rax
0x1800f32e3  mov     qword ptr [rsp+0D8h+var_A0+8], rax
0x1800f32e8  test    rax, rax
0x1800f32eb  jz      short loc_1800F332B
0x1800f32ed  mov     rcx, [rsp+0D8h+var_A8]
0x1800f32f2  movups  xmm0, [rsp+0D8h+var_A0]
0x1800f32f7  movaps  [rsp+0D8h+var_68], xmm0
0x1800f32fc  movsd   [rsp+0D8h+var_58], xmm6
0x1800f3305  mov     rax, [rcx]
0x1800f3308  lea     r8, [rsp+0D8h+arg_10]
0x1800f3310  lea     rdx, [rsp+0D8h+var_68]
0x1800f3315  mov     rax, [rax+48h]
0x1800f3319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f331e  mov     ebx, eax
0x1800f3320  mov     rcx, rdi; bstrString
0x1800f3323  call    cs:__imp_SysFreeString
0x1800f3329  jmp     short loc_1800F3330
0x1800f332b  mov     ebx, 8007000Eh
0x1800f3330  mov     rcx, [rsp+0D8h+lpsz]; pv
0x1800f3335  call    cs:__imp_CoTaskMemFree
0x1800f333b  test    ebx, ebx
0x1800f333d  js      loc_1800F33CD
0x1800f3343  and     esi, [rsp+0D8h+arg_18]
0x1800f334a  mov     eax, esi
0x1800f334c  neg     eax
0x1800f334e  sbb     edx, edx
0x1800f3350  neg     edx
0x1800f3352  inc     edx
0x1800f3354  mov     rax, [rsp+0D8h+arg_10]
0x1800f335c  test    rax, rax
0x1800f335f  jz      short loc_1800F3367
0x1800f3361  lea     rcx, [rax-8]
0x1800f3365  jmp     short loc_1800F3369
0x1800f3367  xor     ecx, ecx
0x1800f3369  add     rcx, 40h ; '@'; lpCriticalSection
0x1800f336d  call    ??4CThreadSafeLong@@QEAAJJ@Z; CThreadSafeLong::operator=(long)
0x1800f3372  mov     rdx, r12; struct _RTL_CRITICAL_SECTION *
0x1800f3375  lea     rcx, [rsp+0D8h+var_78]; this
0x1800f337a  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800f337f  lea     rcx, [rsp+0D8h+var_78]; this
0x1800f3384  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800f3389  mov     eax, [r13+2A4h]
0x1800f3390  test    esi, esi
0x1800f3392  jz      short loc_1800F33B1
0x1800f3394  test    al, 10h
0x1800f3396  jz      short loc_1800F33CD
0x1800f3398  lea     rcx, [r13+150h]
0x1800f339f  mov     r8, [rsp+0D8h+arg_10]
0x1800f33a7  mov     rdx, r15
0x1800f33aa  call    ?Fire_CursorButtonDown@?$CProxy_IInkPictureEvents@VCInkPicture@@@@QEAAJPEAUIInkCursor@@PEAUIInkCursorButton@@@Z; CProxy_IInkPictureEvents<CInkPicture>::Fire_CursorButtonDown(IInkCursor *,IInkCursorButton *)
0x1800f33af  jmp     short loc_1800F33CD
0x1800f33b1  test    al, 20h
0x1800f33b3  jz      short loc_1800F33CD
0x1800f33b5  lea     rcx, [r13+150h]
0x1800f33bc  mov     r8, [rsp+0D8h+arg_10]
0x1800f33c4  mov     rdx, r15
0x1800f33c7  call    ?Fire_CursorButtonUp@?$CProxy_IInkPictureEvents@VCInkPicture@@@@QEAAJPEAUIInkCursor@@PEAUIInkCursorButton@@@Z; CProxy_IInkPictureEvents<CInkPicture>::Fire_CursorButtonUp(IInkCursor *,IInkCursorButton *)
0x1800f33cc  nop
0x1800f33cd  lea     rcx, [rsp+0D8h+arg_10]; void *
0x1800f33d5  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800f33da  inc     r14d
0x1800f33dd  jmp     loc_1800F31E1
0x1800f33e2  mov     [rsp+0D8h+ppvData], rax
0x1800f33e7  test    rdi, rdi
0x1800f33ea  jz      short loc_1800F341D
0x1800f33ec  mov     r8d, [rsp+0D8h+cElements]; cElements
0x1800f33f1  xor     edx, edx; lLbound
0x1800f33f3  call    cs:__imp_SafeArrayCreateVector
0x1800f33f9  mov     [rdi], rax
0x1800f33fc  test    rax, rax
0x1800f33ff  jz      loc_1800F34B1
0x1800f3405  lea     rdx, [rsp+0D8h+ppvData]; ppvData
0x1800f340a  mov     rcx, rax; psa
0x1800f340d  call    cs:__imp_SafeArrayAccessData
0x1800f3413  mov     ebx, eax
0x1800f3415  test    eax, eax
0x1800f3417  js      loc_1800F35B2
0x1800f341d  xor     esi, esi
0x1800f341f  mov     r12, [rsp+0D8h+arg_30]
0x1800f3427  movsd   xmm6, [rsp+0D8h+var_90]
0x1800f342d  test    ebx, ebx
0x1800f342f  js      loc_1800F3583
0x1800f3435  cmp     esi, [rsp+0D8h+cElements]
0x1800f3439  jge     loc_1800F3583
0x1800f343f  mov     [rsp+0D8h+lpsz], 0
0x1800f3448  mov     dword ptr [rsp+0D8h+var_A0+8], esi
0x1800f344c  mov     rcx, [rsp+0D8h+var_A8]
0x1800f3451  movups  xmm0, [rsp+0D8h+var_A0]
0x1800f3456  movaps  [rsp+0D8h+var_68], xmm0
0x1800f345b  movsd   [rsp+0D8h+var_58], xmm6
0x1800f3464  mov     rax, [rcx]
0x1800f3467  lea     r8, [rsp+0D8h+lpsz]
0x1800f346c  lea     rdx, [rsp+0D8h+var_68]
0x1800f3471  mov     rax, [rax+48h]
0x1800f3475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f347a  mov     ebx, eax
0x1800f347c  test    eax, eax
0x1800f347e  js      loc_1800F3572
0x1800f3484  mov     ecx, esi
0x1800f3486  mov     r15d, 1
0x1800f348c  shl     r15d, cl
0x1800f348f  mov     r14d, r15d
0x1800f3492  and     r14d, [rsp+0D8h+arg_18]
0x1800f349a  cmp     [rsp+0D8h+arg_28], 0
0x1800f34a2  jz      short loc_1800F34BB
0x1800f34a4  mov     eax, r14d
0x1800f34a7  neg     eax
0x1800f34a9  sbb     edx, edx
0x1800f34ab  neg     edx
0x1800f34ad  inc     edx
0x1800f34af  jmp     short loc_1800F34BD
0x1800f34b1  mov     ebx, 8007000Eh
0x1800f34b6  jmp     loc_1800F35B2
0x1800f34bb  xor     edx, edx
0x1800f34bd  mov     rax, [rsp+0D8h+lpsz]
0x1800f34c2  test    rax, rax
0x1800f34c5  jz      short loc_1800F34CD
0x1800f34c7  lea     rcx, [rax-8]
0x1800f34cb  jmp     short loc_1800F34CF
0x1800f34cd  xor     ecx, ecx
0x1800f34cf  add     rcx, 40h ; '@'; lpCriticalSection
0x1800f34d3  call    ??4CThreadSafeLong@@QEAAJJ@Z; CThreadSafeLong::operator=(long)
0x1800f34d8  lea     rdx, [r13+1F0h]; struct _RTL_CRITICAL_SECTION *
0x1800f34df  lea     rcx, [rsp+0D8h+var_78]; this
0x1800f34e4  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800f34e9  lea     rcx, [rsp+0D8h+var_78]; this
0x1800f34ee  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800f34f3  test    r12, r12
0x1800f34f6  jnz     short loc_1800F3547
0x1800f34f8  test    [rsp+0D8h+var_AC], r15d
0x1800f34fd  jz      short loc_1800F3547
0x1800f34ff  mov     eax, [r13+2A4h]
0x1800f3506  test    r14d, r14d
0x1800f3509  jz      short loc_1800F352A
0x1800f350b  test    al, 10h
0x1800f350d  jz      short loc_1800F3547
0x1800f350f  lea     rcx, [r13+150h]
0x1800f3516  mov     r8, [rsp+0D8h+lpsz]
0x1800f351b  mov     rdx, [rsp+0D8h+arg_10]
0x1800f3523  call    ?Fire_CursorButtonDown@?$CProxy_IInkPictureEvents@VCInkPicture@@@@QEAAJPEAUIInkCursor@@PEAUIInkCursorButton@@@Z; CProxy_IInkPictureEvents<CInkPicture>::Fire_CursorButtonDown(IInkCursor *,IInkCursorButton *)
0x1800f3528  jmp     short loc_1800F3547
0x1800f352a  test    al, 20h
0x1800f352c  jz      short loc_1800F3547
0x1800f352e  lea     rcx, [r13+150h]
0x1800f3535  mov     r8, [rsp+0D8h+lpsz]
0x1800f353a  mov     rdx, [rsp+0D8h+arg_10]
0x1800f3542  call    ?Fire_CursorButtonUp@?$CProxy_IInkPictureEvents@VCInkPicture@@@@QEAAJPEAUIInkCursor@@PEAUIInkCursorButton@@@Z; CProxy_IInkPictureEvents<CInkPicture>::Fire_CursorButtonUp(IInkCursor *,IInkCursorButton *)
0x1800f3547  test    rdi, rdi
0x1800f354a  jz      short loc_1800F3572
0x1800f354c  mov     rax, [rsp+0D8h+lpsz]
0x1800f3551  test    rax, rax
0x1800f3554  jz      short loc_1800F355C
0x1800f3556  lea     rcx, [rax-8]
0x1800f355a  jmp     short loc_1800F355E
0x1800f355c  xor     ecx, ecx
0x1800f355e  add     rcx, 40h ; '@'; lpCriticalSection
0x1800f3562  call    ??BCThreadSafeLong@@QEAAJXZ; CThreadSafeLong::operator long(void)
0x1800f3567  movsxd  rdx, esi
0x1800f356a  mov     rcx, [rsp+0D8h+ppvData]
0x1800f356f  mov     [rcx+rdx*4], eax
0x1800f3572  lea     rcx, [rsp+0D8h+lpsz]; void *
0x1800f3577  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800f357c  inc     esi
0x1800f357e  jmp     loc_1800F342D
0x1800f3583  test    rdi, rdi
0x1800f3586  jz      short loc_1800F35A5
0x1800f3588  mov     rcx, [rdi]; psa
0x1800f358b  call    cs:__imp_SafeArrayUnaccessData
0x1800f3591  test    ebx, ebx
0x1800f3593  jns     short loc_1800F35A5
0x1800f3595  mov     rcx, [rdi]; psa
0x1800f3598  call    cs:__imp_SafeArrayDestroy
0x1800f359e  mov     qword ptr [rdi], 0
0x1800f35a5  test    r12, r12
0x1800f35a8  jz      short loc_1800F35B2
0x1800f35aa  mov     eax, [rsp+0D8h+var_AC]
0x1800f35ae  mov     [r12], eax
0x1800f35b2  lea     rcx, [rsp+0D8h+var_A8]; void *
0x1800f35b7  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
  ... truncated ...
```
