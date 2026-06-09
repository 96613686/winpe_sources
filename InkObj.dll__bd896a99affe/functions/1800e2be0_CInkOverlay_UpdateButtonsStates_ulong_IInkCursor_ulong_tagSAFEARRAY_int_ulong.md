# CInkOverlay::_UpdateButtonsStates(ulong,IInkCursor *,ulong,tagSAFEARRAY * *,int,ulong *)

- ea: `0x1800e2be0`
- end: `0x1800e30cb`
- name: `?_UpdateButtonsStates@CInkOverlay@@AEAAJKPEAUIInkCursor@@KPEAPEAUtagSAFEARRAY@@HPEAK@Z`
- size: `1259`
- prototype: `__int64 __fastcall(CInkOverlay *__hidden this, unsigned int, struct IInkCursor *, unsigned int, struct tagSAFEARRAY **, int, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d8a30`
- `0x1800e0668`
- `0x1800e09e0`

## callees

- `0x180001c20`
- `0x1800365f8`
- `0x180036824`
- `0x1800a9ecc`
- `0x1800a9f00`
- `0x1800da92c`
- `0x1800da9dc`
- `0x1800e2be0`
- `0x18010c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800e2dce`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e2dce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e2e17`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e2e17`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800e3080`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800e3080`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800e2efb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800e2efb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800e3073`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800e3073`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800e2ee1`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800e2ee1`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800e2daf`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800e2daf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e2e29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e2e29`

## pseudocode

```c
__int64 __fastcall CInkOverlay::_UpdateButtonsStates(
        CInkOverlay *this,
        int a2,
        struct IInkCursor *a3,
        int a4,
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
  int v46; // [rsp+F8h] [rbp+20h]

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
    *(_DWORD *)v14 = a4;
    cElements = 0;
    v37 = 0;
    v9 = ((__int64 (__fastcall *)(struct IInkCursor *, __int64 *))a3->lpVtbl->get_Buttons)(a3, &v37);
    if ( v9 < 0 )
      goto LABEL_68;
    v9 = (*(__int64 (__fastcall **)(__int64, ULONG *))(*(_QWORD *)v37 + 56LL))(v37, &cElements);
    if ( v9 < 0 )
      goto LABEL_68;
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
            v19 = *((_QWORD *)this + 74);
            while ( v18 < (unsigned __int64)((*((_QWORD *)this + 75) - v19) / 24) )
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
                  CProxy_IInkOverlayEvents<CInkOverlay>::Fire_CursorButtonDown((char *)this + 112, a3, v45);
              }
              else if ( (v23 & 0x20) != 0 )
              {
                CProxy_IInkOverlayEvents<CInkOverlay>::Fire_CursorButtonUp((char *)this + 112, a3, v45);
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
          v9 = (*(__int64 (__fastcall **)(__int64, __int128 *, LPOLESTR *))(*(_QWORD *)v37 + 72LL))(v37, &v42, &lpsz);
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
                  CProxy_IInkOverlayEvents<CInkOverlay>::Fire_CursorButtonDown((char *)this + 112, v45, lpsz);
              }
              else if ( (v30 & 0x20) != 0 )
              {
                CProxy_IInkOverlayEvents<CInkOverlay>::Fire_CursorButtonUp((char *)this + 112, v45, lpsz);
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
LABEL_68:
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v37);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800e2be0  mov     rax, rsp
0x1800e2be3  mov     [rax+20h], r9d
0x1800e2be7  mov     [rax+18h], r8
0x1800e2beb  mov     [rax+10h], edx
0x1800e2bee  push    rbx
0x1800e2bef  push    rsi
0x1800e2bf0  push    rdi
0x1800e2bf1  push    r12
0x1800e2bf3  push    r13
0x1800e2bf5  push    r14
0x1800e2bf7  push    r15
0x1800e2bf9  sub     rsp, 0A0h
0x1800e2c00  movaps  xmmword ptr [rax-48h], xmm6
0x1800e2c04  mov     r15, r8
0x1800e2c07  mov     r13, rcx
0x1800e2c0a  xor     ebx, ebx
0x1800e2c0c  lea     rax, [r8+34h]
0x1800e2c10  lea     ecx, [rbx+3Ch]
0x1800e2c13  test    r8, r8
0x1800e2c16  cmovz   rax, rcx
0x1800e2c1a  mov     r14d, r9d
0x1800e2c1d  xor     r14d, [rax]
0x1800e2c20  mov     [rsp+0D8h+var_AC], r14d
0x1800e2c25  mov     esi, [rsp+0D8h+arg_28]
0x1800e2c2c  mov     rdi, [rsp+0D8h+arg_20]
0x1800e2c34  cmp     esi, 1
0x1800e2c37  jnz     short loc_1800E2C47
0x1800e2c39  test    rdi, rdi
0x1800e2c3c  jnz     short loc_1800E2C47
0x1800e2c3e  test    r14d, r14d
0x1800e2c41  jz      loc_1800E30A5
0x1800e2c47  lea     rax, [r8+34h]
0x1800e2c4b  test    r15, r15
0x1800e2c4e  cmovz   rax, rcx
0x1800e2c52  mov     [rax], r9d
0x1800e2c55  mov     [rsp+0D8h+cElements], 0
0x1800e2c5d  mov     [rsp+0D8h+var_A8], 0
0x1800e2c66  mov     rax, [r8]
0x1800e2c69  lea     rdx, [rsp+0D8h+var_A8]
0x1800e2c6e  mov     rcx, r15
0x1800e2c71  mov     rax, [rax+68h]
0x1800e2c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2c7a  mov     ebx, eax
0x1800e2c7c  test    eax, eax
0x1800e2c7e  js      loc_1800E309A
0x1800e2c84  mov     rcx, [rsp+0D8h+var_A8]
0x1800e2c89  mov     rax, [rcx]
0x1800e2c8c  lea     rdx, [rsp+0D8h+cElements]
0x1800e2c91  mov     rax, [rax+38h]
0x1800e2c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2c9a  mov     ebx, eax
0x1800e2c9c  test    eax, eax
0x1800e2c9e  js      loc_1800E309A
0x1800e2ca4  xorps   xmm0, xmm0
0x1800e2ca7  xor     eax, eax
0x1800e2ca9  movups  [rsp+0D8h+var_A0], xmm0
0x1800e2cae  mov     [rsp+0D8h+var_90], rax
0x1800e2cb3  lea     ecx, [rax+3]; vt
0x1800e2cb6  mov     word ptr [rsp+0D8h+var_A0], cx
0x1800e2cbb  test    esi, esi
0x1800e2cbd  jz      loc_1800E2ED0
0x1800e2cc3  test    rdi, rdi
0x1800e2cc6  jnz     loc_1800E2ED0
0x1800e2ccc  xor     r14d, r14d
0x1800e2ccf  movsd   xmm6, [rsp+0D8h+var_90]
0x1800e2cd5  cmp     r14d, [rsp+0D8h+cElements]
0x1800e2cda  jge     loc_1800E309A
0x1800e2ce0  mov     ecx, r14d
0x1800e2ce3  mov     esi, 1
0x1800e2ce8  shl     esi, cl
0x1800e2cea  test    [rsp+0D8h+var_AC], esi
0x1800e2cee  jz      loc_1800E2EC8
0x1800e2cf4  mov     [rsp+0D8h+arg_10], 0
0x1800e2d00  xor     edi, edi
0x1800e2d02  lea     r12, [r13+110h]
0x1800e2d09  mov     rdx, r12; struct _RTL_CRITICAL_SECTION *
0x1800e2d0c  lea     rcx, [rsp+0D8h+ppvData]; this
0x1800e2d11  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800e2d16  or      eax, 0FFFFFFFFh
0x1800e2d19  cmp     ax, [r13+180h]
0x1800e2d21  jnz     short loc_1800E2D7D
0x1800e2d23  xor     r8d, r8d
0x1800e2d26  mov     r9, [r13+250h]
0x1800e2d2d  mov     rcx, [r13+258h]
0x1800e2d34  sub     rcx, r9
0x1800e2d37  mov     rax, 2AAAAAAAAAAAAAABh
0x1800e2d41  imul    rcx
0x1800e2d44  sar     rdx, 2
0x1800e2d48  mov     rax, rdx
0x1800e2d4b  shr     rax, 3Fh
0x1800e2d4f  add     rdx, rax
0x1800e2d52  movsxd  rax, r8d
0x1800e2d55  cmp     rax, rdx
0x1800e2d58  jnb     short loc_1800E2D7D
0x1800e2d5a  lea     rcx, [rax+rax*2]
0x1800e2d5e  mov     eax, [rsp+0D8h+arg_8]
0x1800e2d65  cmp     eax, [r9+rcx*8+8]
0x1800e2d6a  jz      short loc_1800E2D71
0x1800e2d6c  inc     r8d
0x1800e2d6f  jmp     short loc_1800E2D52
0x1800e2d71  mov     edi, r14d
0x1800e2d74  shl     rdi, 4
0x1800e2d78  add     rdi, [r9+rcx*8+10h]
0x1800e2d7d  lea     rcx, [rsp+0D8h+ppvData]; this
0x1800e2d82  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800e2d87  test    rdi, rdi
0x1800e2d8a  jnz     short loc_1800E2D9E
0x1800e2d8c  lea     rcx, [rsp+0D8h+arg_10]; void *
0x1800e2d94  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800e2d99  jmp     loc_1800E309A
0x1800e2d9e  mov     [rsp+0D8h+lpsz], 0
0x1800e2da7  lea     rdx, [rsp+0D8h+lpsz]; lplpsz
0x1800e2dac  mov     rcx, rdi; rclsid
0x1800e2daf  call    cs:__imp_StringFromCLSID
0x1800e2db5  mov     ebx, eax
0x1800e2db7  test    eax, eax
0x1800e2db9  js      loc_1800E2EBB
0x1800e2dbf  mov     eax, 8
0x1800e2dc4  mov     word ptr [rsp+0D8h+var_A0], ax
0x1800e2dc9  mov     rcx, [rsp+0D8h+lpsz]; psz
0x1800e2dce  call    cs:__imp_SysAllocString
0x1800e2dd4  mov     rdi, rax
0x1800e2dd7  mov     qword ptr [rsp+0D8h+var_A0+8], rax
0x1800e2ddc  test    rax, rax
0x1800e2ddf  jz      short loc_1800E2E1F
0x1800e2de1  mov     rcx, [rsp+0D8h+var_A8]
0x1800e2de6  movups  xmm0, [rsp+0D8h+var_A0]
0x1800e2deb  movaps  [rsp+0D8h+var_68], xmm0
0x1800e2df0  movsd   [rsp+0D8h+var_58], xmm6
0x1800e2df9  mov     rax, [rcx]
0x1800e2dfc  lea     r8, [rsp+0D8h+arg_10]
0x1800e2e04  lea     rdx, [rsp+0D8h+var_68]
0x1800e2e09  mov     rax, [rax+48h]
0x1800e2e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2e12  mov     ebx, eax
0x1800e2e14  mov     rcx, rdi; bstrString
0x1800e2e17  call    cs:__imp_SysFreeString
0x1800e2e1d  jmp     short loc_1800E2E24
0x1800e2e1f  mov     ebx, 8007000Eh
0x1800e2e24  mov     rcx, [rsp+0D8h+lpsz]; pv
0x1800e2e29  call    cs:__imp_CoTaskMemFree
0x1800e2e2f  test    ebx, ebx
0x1800e2e31  js      loc_1800E2EBB
0x1800e2e37  and     esi, [rsp+0D8h+arg_18]
0x1800e2e3e  mov     eax, esi
0x1800e2e40  neg     eax
0x1800e2e42  sbb     edx, edx
0x1800e2e44  neg     edx
0x1800e2e46  inc     edx
0x1800e2e48  mov     rax, [rsp+0D8h+arg_10]
0x1800e2e50  test    rax, rax
0x1800e2e53  jz      short loc_1800E2E5B
0x1800e2e55  lea     rcx, [rax-8]
0x1800e2e59  jmp     short loc_1800E2E5D
0x1800e2e5b  xor     ecx, ecx
0x1800e2e5d  add     rcx, 40h ; '@'; lpCriticalSection
0x1800e2e61  call    ??4CThreadSafeLong@@QEAAJJ@Z; CThreadSafeLong::operator=(long)
0x1800e2e66  mov     rdx, r12; struct _RTL_CRITICAL_SECTION *
0x1800e2e69  lea     rcx, [rsp+0D8h+var_78]; this
0x1800e2e6e  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800e2e73  lea     rcx, [rsp+0D8h+var_78]; this
0x1800e2e78  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800e2e7d  mov     eax, [r13+1C4h]
0x1800e2e84  test    esi, esi
0x1800e2e86  jz      short loc_1800E2EA2
0x1800e2e88  test    al, 10h
0x1800e2e8a  jz      short loc_1800E2EBB
0x1800e2e8c  lea     rcx, [r13+70h]
0x1800e2e90  mov     r8, [rsp+0D8h+arg_10]
0x1800e2e98  mov     rdx, r15
0x1800e2e9b  call    ?Fire_CursorButtonDown@?$CProxy_IInkOverlayEvents@VCInkOverlay@@@@QEAAJPEAUIInkCursor@@PEAUIInkCursorButton@@@Z; CProxy_IInkOverlayEvents<CInkOverlay>::Fire_CursorButtonDown(IInkCursor *,IInkCursorButton *)
0x1800e2ea0  jmp     short loc_1800E2EBB
0x1800e2ea2  test    al, 20h
0x1800e2ea4  jz      short loc_1800E2EBB
0x1800e2ea6  lea     rcx, [r13+70h]
0x1800e2eaa  mov     r8, [rsp+0D8h+arg_10]
0x1800e2eb2  mov     rdx, r15
0x1800e2eb5  call    ?Fire_CursorButtonUp@?$CProxy_IInkOverlayEvents@VCInkOverlay@@@@QEAAJPEAUIInkCursor@@PEAUIInkCursorButton@@@Z; CProxy_IInkOverlayEvents<CInkOverlay>::Fire_CursorButtonUp(IInkCursor *,IInkCursorButton *)
0x1800e2eba  nop
0x1800e2ebb  lea     rcx, [rsp+0D8h+arg_10]; void *
0x1800e2ec3  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800e2ec8  inc     r14d
0x1800e2ecb  jmp     loc_1800E2CD5
0x1800e2ed0  mov     [rsp+0D8h+ppvData], rax
0x1800e2ed5  test    rdi, rdi
0x1800e2ed8  jz      short loc_1800E2F0B
0x1800e2eda  mov     r8d, [rsp+0D8h+cElements]; cElements
0x1800e2edf  xor     edx, edx; lLbound
0x1800e2ee1  call    cs:__imp_SafeArrayCreateVector
0x1800e2ee7  mov     [rdi], rax
0x1800e2eea  test    rax, rax
0x1800e2eed  jz      loc_1800E2F9F
0x1800e2ef3  lea     rdx, [rsp+0D8h+ppvData]; ppvData
0x1800e2ef8  mov     rcx, rax; psa
0x1800e2efb  call    cs:__imp_SafeArrayAccessData
0x1800e2f01  mov     ebx, eax
0x1800e2f03  test    eax, eax
0x1800e2f05  js      loc_1800E309A
0x1800e2f0b  xor     esi, esi
0x1800e2f0d  mov     r12, [rsp+0D8h+arg_30]
0x1800e2f15  movsd   xmm6, [rsp+0D8h+var_90]
0x1800e2f1b  test    ebx, ebx
0x1800e2f1d  js      loc_1800E306B
0x1800e2f23  cmp     esi, [rsp+0D8h+cElements]
0x1800e2f27  jge     loc_1800E306B
0x1800e2f2d  mov     [rsp+0D8h+lpsz], 0
0x1800e2f36  mov     dword ptr [rsp+0D8h+var_A0+8], esi
0x1800e2f3a  mov     rcx, [rsp+0D8h+var_A8]
0x1800e2f3f  movups  xmm0, [rsp+0D8h+var_A0]
0x1800e2f44  movaps  [rsp+0D8h+var_68], xmm0
0x1800e2f49  movsd   [rsp+0D8h+var_58], xmm6
0x1800e2f52  mov     rax, [rcx]
0x1800e2f55  lea     r8, [rsp+0D8h+lpsz]
0x1800e2f5a  lea     rdx, [rsp+0D8h+var_68]
0x1800e2f5f  mov     rax, [rax+48h]
0x1800e2f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2f68  mov     ebx, eax
0x1800e2f6a  test    eax, eax
0x1800e2f6c  js      loc_1800E305A
0x1800e2f72  mov     ecx, esi
0x1800e2f74  mov     r15d, 1
0x1800e2f7a  shl     r15d, cl
0x1800e2f7d  mov     r14d, r15d
0x1800e2f80  and     r14d, [rsp+0D8h+arg_18]
0x1800e2f88  cmp     [rsp+0D8h+arg_28], 0
0x1800e2f90  jz      short loc_1800E2FA9
0x1800e2f92  mov     eax, r14d
0x1800e2f95  neg     eax
0x1800e2f97  sbb     edx, edx
0x1800e2f99  neg     edx
0x1800e2f9b  inc     edx
0x1800e2f9d  jmp     short loc_1800E2FAB
0x1800e2f9f  mov     ebx, 8007000Eh
0x1800e2fa4  jmp     loc_1800E309A
0x1800e2fa9  xor     edx, edx
0x1800e2fab  mov     rax, [rsp+0D8h+lpsz]
0x1800e2fb0  test    rax, rax
0x1800e2fb3  jz      short loc_1800E2FBB
0x1800e2fb5  lea     rcx, [rax-8]
0x1800e2fb9  jmp     short loc_1800E2FBD
0x1800e2fbb  xor     ecx, ecx
0x1800e2fbd  add     rcx, 40h ; '@'; lpCriticalSection
0x1800e2fc1  call    ??4CThreadSafeLong@@QEAAJJ@Z; CThreadSafeLong::operator=(long)
0x1800e2fc6  lea     rdx, [r13+110h]; struct _RTL_CRITICAL_SECTION *
0x1800e2fcd  lea     rcx, [rsp+0D8h+var_78]; this
0x1800e2fd2  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800e2fd7  lea     rcx, [rsp+0D8h+var_78]; this
0x1800e2fdc  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800e2fe1  test    r12, r12
0x1800e2fe4  jnz     short loc_1800E302F
0x1800e2fe6  test    [rsp+0D8h+var_AC], r15d
0x1800e2feb  jz      short loc_1800E302F
0x1800e2fed  mov     eax, [r13+1C4h]
0x1800e2ff4  test    r14d, r14d
0x1800e2ff7  jz      short loc_1800E3015
0x1800e2ff9  test    al, 10h
0x1800e2ffb  jz      short loc_1800E302F
0x1800e2ffd  lea     rcx, [r13+70h]
0x1800e3001  mov     r8, [rsp+0D8h+lpsz]
0x1800e3006  mov     rdx, [rsp+0D8h+arg_10]
0x1800e300e  call    ?Fire_CursorButtonDown@?$CProxy_IInkOverlayEvents@VCInkOverlay@@@@QEAAJPEAUIInkCursor@@PEAUIInkCursorButton@@@Z; CProxy_IInkOverlayEvents<CInkOverlay>::Fire_CursorButtonDown(IInkCursor *,IInkCursorButton *)
0x1800e3013  jmp     short loc_1800E302F
0x1800e3015  test    al, 20h
0x1800e3017  jz      short loc_1800E302F
0x1800e3019  lea     rcx, [r13+70h]
0x1800e301d  mov     r8, [rsp+0D8h+lpsz]
0x1800e3022  mov     rdx, [rsp+0D8h+arg_10]
0x1800e302a  call    ?Fire_CursorButtonUp@?$CProxy_IInkOverlayEvents@VCInkOverlay@@@@QEAAJPEAUIInkCursor@@PEAUIInkCursorButton@@@Z; CProxy_IInkOverlayEvents<CInkOverlay>::Fire_CursorButtonUp(IInkCursor *,IInkCursorButton *)
0x1800e302f  test    rdi, rdi
0x1800e3032  jz      short loc_1800E305A
0x1800e3034  mov     rax, [rsp+0D8h+lpsz]
0x1800e3039  test    rax, rax
0x1800e303c  jz      short loc_1800E3044
0x1800e303e  lea     rcx, [rax-8]
0x1800e3042  jmp     short loc_1800E3046
0x1800e3044  xor     ecx, ecx
0x1800e3046  add     rcx, 40h ; '@'; lpCriticalSection
0x1800e304a  call    ??BCThreadSafeLong@@QEAAJXZ; CThreadSafeLong::operator long(void)
0x1800e304f  movsxd  rdx, esi
0x1800e3052  mov     rcx, [rsp+0D8h+ppvData]
0x1800e3057  mov     [rcx+rdx*4], eax
0x1800e305a  lea     rcx, [rsp+0D8h+lpsz]; void *
0x1800e305f  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800e3064  inc     esi
0x1800e3066  jmp     loc_1800E2F1B
0x1800e306b  test    rdi, rdi
0x1800e306e  jz      short loc_1800E308D
0x1800e3070  mov     rcx, [rdi]; psa
0x1800e3073  call    cs:__imp_SafeArrayUnaccessData
0x1800e3079  test    ebx, ebx
0x1800e307b  jns     short loc_1800E308D
0x1800e307d  mov     rcx, [rdi]; psa
0x1800e3080  call    cs:__imp_SafeArrayDestroy
0x1800e3086  mov     qword ptr [rdi], 0
0x1800e308d  test    r12, r12
0x1800e3090  jz      short loc_1800E309A
0x1800e3092  mov     eax, [rsp+0D8h+var_AC]
0x1800e3096  mov     [r12], eax
0x1800e309a  lea     rcx, [rsp+0D8h+var_A8]; void *
0x1800e309f  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
  ... truncated ...
```
