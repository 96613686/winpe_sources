# ShellExecUnelevated(ushort const *,ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800286e0`
- end: `0x180028be6`
- name: `?ShellExecUnelevated@@YAJPEBG000H@Z`
- size: `1286`
- prototype: `__int64 __usercall@<rax>(OLECHAR *psz@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800270a0`

## callees

- `0x180008cf8`
- `0x18001f6ec`
- `0x1800227c8`
- `0x180022e20`
- `0x1800286e0`
- `0x180059010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180028987`
- `OLEAUT32!__imp_SysAllocString` at `0x1800289ca`
- `OLEAUT32!__imp_SysAllocString` at `0x180028a10`
- `OLEAUT32!__imp_SysAllocString` at `0x180028a3c`
- `OLEAUT32!__imp_SysAllocString` at `0x180028987`
- `OLEAUT32!__imp_SysAllocString` at `0x1800289ca`
- `OLEAUT32!__imp_SysAllocString` at `0x180028a10`
- `OLEAUT32!__imp_SysAllocString` at `0x180028a3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180028aa7`
- `OLEAUT32!__imp_SysFreeString` at `0x180028aa7`
- `OLEAUT32!__imp_VariantClear` at `0x180028975`
- `OLEAUT32!__imp_VariantClear` at `0x1800289b8`
- `OLEAUT32!__imp_VariantClear` at `0x1800289fd`
- `OLEAUT32!__imp_VariantClear` at `0x180028ab2`
- `OLEAUT32!__imp_VariantClear` at `0x180028abc`
- `OLEAUT32!__imp_VariantClear` at `0x180028ac6`
- `OLEAUT32!__imp_VariantClear` at `0x180028ad0`
- `OLEAUT32!__imp_VariantClear` at `0x180028b39`
- `OLEAUT32!__imp_VariantClear` at `0x180028b43`
- `OLEAUT32!__imp_VariantClear` at `0x180028975`
- `OLEAUT32!__imp_VariantClear` at `0x1800289b8`
- `OLEAUT32!__imp_VariantClear` at `0x1800289fd`
- `OLEAUT32!__imp_VariantClear` at `0x180028ab2`
- `OLEAUT32!__imp_VariantClear` at `0x180028abc`
- `OLEAUT32!__imp_VariantClear` at `0x180028ac6`
- `OLEAUT32!__imp_VariantClear` at `0x180028ad0`
- `OLEAUT32!__imp_VariantClear` at `0x180028b39`
- `OLEAUT32!__imp_VariantClear` at `0x180028b43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800287ca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800287ca`

## pseudocode

```c
__int64 __fastcall ShellExecUnelevated(
        OLECHAR *psz,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  unsigned int v6; // ebx
  __int64 v7; // rcx
  HRESULT Instance; // eax
  int v9; // eax
  _QWORD *v10; // rsi
  IRecordInfo *pRecInfo; // xmm13_8
  __int64 v12; // r14
  __int128 v13; // xmm12
  __int128 v14; // xmm10
  IRecordInfo *v15; // xmm11_8
  __int128 v16; // xmm8
  IRecordInfo *v17; // xmm9_8
  __int128 v18; // xmm6
  __int64 v19; // xmm7_8
  OLECHAR *v20; // rdi
  void (__fastcall *v21)(_QWORD *, OLECHAR *, __int128 *, __int128 *, __int128 *, __int128 *); // rax
  __int64 v23; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+58h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG ppv; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+80h] [rbp-88h]
  VARIANTARG v29; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG v31; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v32; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG v33; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v34; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v35; // [rsp+118h] [rbp+10h]
  __int128 v36; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v37; // [rsp+138h] [rbp+30h]
  __int128 v38; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v39; // [rsp+158h] [rbp+50h]
  __int128 v40; // [rsp+168h] [rbp+60h] BYREF
  __int64 v41; // [rsp+178h] [rbp+70h]
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+248h] [rbp+140h] BYREF
  __int64 v43; // [rsp+250h] [rbp+148h] BYREF
  __int64 (__fastcall ***v44)(_QWORD, GUID *, _QWORD **); // [rsp+258h] [rbp+150h] BYREF
  _QWORD *v45; // [rsp+260h] [rbp+158h] BYREF

  v33.vt = 3;
  *(_QWORD *)&ppv.vt = 0;
  v33.lVal = 0;
  a5 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  memset(&v32, 0, sizeof(v32));
  if ( !psz )
  {
    v6 = -2147024809;
LABEL_3:
    v7 = v6;
LABEL_4:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_22;
  }
  Instance = CoCreateInstance(&CLSID_ShellWindows, 0, 0x17u, &GUID_85cb6900_4d95_11cf_960c_0080c7f4ee85, (LPVOID *)&ppv);
  v6 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  v9 = (*(__int64 (__fastcall **)(_QWORD, VARIANTARG *, VARIANTARG *, __int64, int *, int, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(**(_QWORD **)&ppv.vt + 120LL))(
         *(_QWORD *)&ppv.vt,
         &v33,
         &v32,
         8,
         &a5,
         1,
         &v26);
  v6 = v9;
  if ( v9 == 1 )
  {
    v6 = -2147023728;
    goto LABEL_3;
  }
  if ( v9 < 0 )
    goto LABEL_3;
  Instance = (**v26)(v26, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v25);
  v6 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  Instance = (*(__int64 (__fastcall **)(__int64, SID *, GUID *, __int64 *))(*(_QWORD *)v25 + 24LL))(
               v25,
               &SID_STopLevelBrowser,
               &GUID_000214e2_0000_0000_c000_000000000046,
               &v24);
  v6 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  Instance = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 120LL))(v24, &v23);
  v6 = Instance;
  if ( Instance < 0 )
    goto LABEL_6;
  Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v23 + 120LL))(
               v23,
               0,
               &GUID_00020400_0000_0000_c000_000000000046,
               &v42);
  v6 = Instance;
  if ( Instance < 0
    || (Instance = (**v42)(v42, &GUID_e7a1af80_4d96_11cf_960c_0080c7f4ee85, &v43), v6 = Instance, Instance < 0)
    || (Instance = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD **)))(*(_QWORD *)v43 + 56LL))(
                     v43,
                     &v44),
        v6 = Instance,
        Instance < 0)
    || (Instance = (**v44)(v44, &GUID_a4c6892c_3ba9_11d2_9dea_00c04fb16162, &v45), v6 = Instance, Instance < 0) )
  {
LABEL_6:
    v7 = (unsigned int)Instance;
    goto LABEL_4;
  }
  v10 = v45;
  pRecInfo = v31.pRecInfo;
  v12 = *v45;
  v31.vt = 3;
  v31.lVal = 1;
  v13 = *(_OWORD *)&v31.vt;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"open");
  if ( !pvarg.llVal )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v14 = *(_OWORD *)&pvarg.vt;
  v15 = pvarg.pRecInfo;
  v29.vt = 0;
  VariantClear(&v29);
  v29.vt = 8;
  v29.llVal = (LONGLONG)SysAllocString(&WindowName);
  if ( !v29.llVal )
  {
    v29.vt = 10;
    v29.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v16 = *(_OWORD *)&v29.vt;
  v17 = v29.pRecInfo;
  ppv.iVal = 0;
  VariantClear((VARIANTARG *)&ppv.decVal.8);
  ppv.iVal = 8;
  ppv.pRecInfo = (IRecordInfo *)SysAllocString(&WindowName);
  if ( !ppv.pRecInfo )
  {
    ppv.iVal = 10;
    *((_DWORD *)&ppv.decVal + 4) = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v18 = *(_OWORD *)&ppv.decVal.Lo32;
  v19 = v28;
  v20 = SysAllocString(psz);
  if ( !v20 )
    ATL::AtlThrowImpl(-2147024882);
  v34 = v13;
  v35 = pRecInfo;
  v21 = *(void (__fastcall **)(_QWORD *, OLECHAR *, __int128 *, __int128 *, __int128 *, __int128 *))(v12 + 248);
  v36 = v14;
  v37 = v15;
  v38 = v16;
  v39 = v17;
  v40 = v18;
  v41 = v19;
  v21(v10, v20, &v40, &v38, &v36, &v34);
  SysFreeString(v20);
  VariantClear((VARIANTARG *)&ppv.decVal.8);
  VariantClear(&v29);
  VariantClear(&pvarg);
  VariantClear(&v31);
LABEL_22:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  VariantClear(&v32);
  VariantClear(&v33);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v6;
}

```

## disassembly

```asm
0x1800286e0  mov     rax, rsp
0x1800286e3  mov     [rax+20h], r9
0x1800286e7  mov     [rax+18h], r8
0x1800286eb  mov     [rax+10h], rdx
0x1800286ef  push    rbp
0x1800286f0  push    rbx
0x1800286f1  push    rsi
0x1800286f2  push    rdi
0x1800286f3  push    r12
0x1800286f5  push    r14
0x1800286f7  lea     rbp, [rax-138h]
0x1800286fe  sub     rsp, 208h
0x180028705  movaps  xmmword ptr [rax-48h], xmm6
0x180028709  xorps   xmm0, xmm0
0x18002870c  movaps  xmmword ptr [rax-58h], xmm7
0x180028710  mov     rdi, rcx
0x180028713  movaps  xmmword ptr [rax-68h], xmm8
0x180028718  movaps  xmmword ptr [rax-78h], xmm9
0x18002871d  movaps  xmmword ptr [rax-88h], xmm10
0x180028725  movaps  xmmword ptr [rax-98h], xmm11
0x18002872d  movaps  xmmword ptr [rax-0A8h], xmm12
0x180028735  movaps  xmmword ptr [rax-0B8h], xmm13
0x18002873d  mov     eax, 3
0x180028742  mov     word ptr [rbp+130h+var_150], ax
0x180028746  xor     eax, eax
0x180028748  mov     qword ptr [rsp+230h+var_1D0], 0
0x180028751  mov     dword ptr [rbp+130h+var_150+8], 0
0x180028758  mov     qword ptr [rbp+130h+var_168+10h], rax
0x18002875c  mov     [rbp+130h+arg_20], eax
0x180028762  mov     [rsp+230h+var_1D8], rax
0x180028767  mov     [rsp+230h+var_1E0], rax
0x18002876c  mov     [rsp+230h+var_1E8], rax
0x180028771  mov     [rsp+230h+var_1F0], rax
0x180028776  mov     [rbp+130h+arg_0], rax
0x18002877d  mov     [rbp+130h+arg_8], rax
0x180028784  mov     [rbp+130h+arg_10], rax
0x18002878b  mov     [rbp+130h+arg_18], rax
0x180028792  movups  xmmword ptr [rbp+130h+var_168], xmm0
0x180028796  test    rcx, rcx
0x180028799  jnz     short loc_1800287AC
0x18002879b  mov     ebx, 80070057h
0x1800287a0  mov     ecx, ebx
0x1800287a2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800287a7  jmp     loc_180028AD6
0x1800287ac  xor     edx, edx; pUnkOuter
0x1800287ae  lea     rax, [rsp+230h+var_1D0]
0x1800287b3  lea     r9, _GUID_85cb6900_4d95_11cf_960c_0080c7f4ee85; riid
0x1800287ba  mov     [rsp+230h+ppv], rax; ppv
0x1800287bf  lea     rcx, CLSID_ShellWindows; rclsid
0x1800287c6  lea     r8d, [rdx+17h]; dwClsContext
0x1800287ca  call    cs:__imp_CoCreateInstance
0x1800287d0  mov     ebx, eax
0x1800287d2  test    eax, eax
0x1800287d4  jns     short loc_1800287DA
0x1800287d6  mov     ecx, eax
0x1800287d8  jmp     short loc_1800287A2
0x1800287da  mov     rcx, qword ptr [rsp+230h+var_1D0]
0x1800287df  lea     rdx, [rsp+230h+var_1D8]
0x1800287e4  mov     [rsp+230h+var_200], rdx
0x1800287e9  lea     r8, [rbp+130h+var_168]
0x1800287ed  lea     rdx, [rbp+130h+arg_20]
0x1800287f4  mov     dword ptr [rsp+230h+var_208], 1
0x1800287fc  mov     [rsp+230h+ppv], rdx
0x180028801  mov     r12d, 8
0x180028807  mov     rax, [rcx]
0x18002880a  lea     rdx, [rbp+130h+var_150]
0x18002880e  mov     r9d, r12d
0x180028811  mov     rax, [rax+78h]
0x180028815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002881a  mov     ebx, eax
0x18002881c  cmp     eax, 1
0x18002881f  jnz     short loc_18002882B
0x180028821  mov     ebx, 80070490h
0x180028826  jmp     loc_1800287A0
0x18002882b  test    eax, eax
0x18002882d  js      loc_1800287A0
0x180028833  mov     rcx, [rsp+230h+var_1D8]
0x180028838  lea     r8, [rsp+230h+var_1E0]
0x18002883d  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x180028844  mov     rax, [rcx]
0x180028847  mov     rax, [rax]
0x18002884a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002884f  mov     ebx, eax
0x180028851  test    eax, eax
0x180028853  js      short loc_1800287D6
0x180028855  mov     rcx, [rsp+230h+var_1E0]
0x18002885a  lea     r9, [rsp+230h+var_1E8]
0x18002885f  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046
0x180028866  lea     rdx, SID_STopLevelBrowser
0x18002886d  mov     rax, [rcx]
0x180028870  mov     rax, [rax+18h]
0x180028874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028879  mov     ebx, eax
0x18002887b  test    eax, eax
0x18002887d  js      loc_1800287D6
0x180028883  mov     rcx, [rsp+230h+var_1E8]
0x180028888  lea     rdx, [rsp+230h+var_1F0]
0x18002888d  mov     rax, [rcx]
0x180028890  mov     rax, [rax+78h]
0x180028894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028899  mov     ebx, eax
0x18002889b  test    eax, eax
0x18002889d  js      loc_1800287D6
0x1800288a3  mov     rcx, [rsp+230h+var_1F0]
0x1800288a8  lea     r9, [rbp+130h+arg_0]
0x1800288af  lea     r8, _GUID_00020400_0000_0000_c000_000000000046
0x1800288b6  xor     edx, edx
0x1800288b8  mov     rax, [rcx]
0x1800288bb  mov     rax, [rax+78h]
0x1800288bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288c4  mov     ebx, eax
0x1800288c6  test    eax, eax
0x1800288c8  js      loc_1800287D6
0x1800288ce  mov     rcx, [rbp+130h+arg_0]
0x1800288d5  lea     r8, [rbp+130h+arg_8]
0x1800288dc  lea     rdx, _GUID_e7a1af80_4d96_11cf_960c_0080c7f4ee85
0x1800288e3  mov     rax, [rcx]
0x1800288e6  mov     rax, [rax]
0x1800288e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288ee  mov     ebx, eax
0x1800288f0  test    eax, eax
0x1800288f2  js      loc_1800287D6
0x1800288f8  mov     rcx, [rbp+130h+arg_8]
0x1800288ff  lea     rdx, [rbp+130h+arg_10]
0x180028906  mov     rax, [rcx]
0x180028909  mov     rax, [rax+38h]
0x18002890d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028912  mov     ebx, eax
0x180028914  test    eax, eax
0x180028916  js      loc_1800287D6
0x18002891c  mov     rcx, [rbp+130h+arg_10]
0x180028923  lea     r8, [rbp+130h+arg_18]
0x18002892a  lea     rdx, _GUID_a4c6892c_3ba9_11d2_9dea_00c04fb16162
0x180028931  mov     rax, [rcx]
0x180028934  mov     rax, [rax]
0x180028937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002893c  mov     ebx, eax
0x18002893e  test    eax, eax
0x180028940  js      loc_1800287D6
0x180028946  mov     rsi, [rbp+130h+arg_18]
0x18002894d  lea     rcx, [rbp+130h+pvarg]; pvarg
0x180028951  movsd   xmm13, qword ptr [rbp+130h+var_180+10h]
0x180028957  mov     eax, 3
0x18002895c  mov     r14, [rsi]
0x18002895f  mov     word ptr [rbp+130h+var_180], ax
0x180028963  xor     eax, eax
0x180028965  mov     dword ptr [rbp+130h+var_180+8], 1
0x18002896c  movups  xmm12, xmmword ptr [rbp+130h+var_180]
0x180028971  mov     word ptr [rbp+130h+pvarg], ax
0x180028975  call    cs:__imp_VariantClear
0x18002897b  lea     rcx, aOpen; "open"
0x180028982  mov     word ptr [rbp+130h+pvarg], r12w
0x180028987  call    cs:__imp_SysAllocString
0x18002898d  mov     rcx, rax
0x180028990  mov     dword ptr [rbp+130h+pvarg+8], eax
0x180028993  sar     rcx, 20h
0x180028997  mov     dword ptr [rbp+130h+pvarg+0Ch], ecx
0x18002899a  test    rax, rax
0x18002899d  jz      loc_180028B9F
0x1800289a3  movups  xmm10, xmmword ptr [rbp+130h+pvarg]
0x1800289a8  lea     rcx, [rbp+130h+var_1B0]; pvarg
0x1800289ac  xor     eax, eax
0x1800289ae  movsd   xmm11, qword ptr [rbp+130h+pvarg+10h]
0x1800289b4  mov     word ptr [rbp+130h+var_1B0], ax
0x1800289b8  call    cs:__imp_VariantClear
0x1800289be  lea     rcx, WindowName; psz
0x1800289c5  mov     word ptr [rbp+130h+var_1B0], r12w
0x1800289ca  call    cs:__imp_SysAllocString
0x1800289d0  mov     rcx, rax
0x1800289d3  mov     dword ptr [rbp+130h+var_1B0+8], eax
0x1800289d6  sar     rcx, 20h
0x1800289da  mov     dword ptr [rbp+130h+var_1B0+0Ch], ecx
0x1800289dd  test    rax, rax
0x1800289e0  jz      loc_180028BB6
0x1800289e6  movups  xmm8, xmmword ptr [rbp+130h+var_1B0]
0x1800289eb  lea     rcx, [rsp+230h+var_1D0+8]; pvarg
0x1800289f0  xor     eax, eax
0x1800289f2  movsd   xmm9, qword ptr [rbp+130h+var_1B0+10h]
0x1800289f8  mov     word ptr [rsp+230h+var_1D0+8], ax
0x1800289fd  call    cs:__imp_VariantClear
0x180028a03  lea     rcx, WindowName; psz
0x180028a0a  mov     word ptr [rsp+230h+var_1D0+8], r12w
0x180028a10  call    cs:__imp_SysAllocString
0x180028a16  mov     rcx, rax
0x180028a19  mov     dword ptr [rsp+230h+var_1D0+10h], eax
0x180028a1d  sar     rcx, 20h
0x180028a21  mov     dword ptr [rsp+230h+var_1D0+14h], ecx
0x180028a25  test    rax, rax
0x180028a28  jz      loc_180028BCD
0x180028a2e  movups  xmm6, xmmword ptr [rsp+230h+var_1D0+8]
0x180028a33  mov     rcx, rdi; psz
0x180028a36  movsd   xmm7, [rsp+230h+var_1B8]
0x180028a3c  call    cs:__imp_SysAllocString
0x180028a42  mov     rdi, rax
0x180028a45  test    rax, rax
0x180028a48  jz      loc_180028B94
0x180028a4e  lea     rax, [rbp+130h+var_130]
0x180028a52  movaps  [rbp+130h+var_130], xmm12
0x180028a57  mov     [rsp+230h+var_208], rax
0x180028a5c  lea     r9, [rbp+130h+var_F0]
0x180028a60  lea     rax, [rbp+130h+var_110]
0x180028a64  movsd   [rbp+130h+var_120], xmm13
0x180028a6a  mov     [rsp+230h+ppv], rax
0x180028a6f  lea     r8, [rbp+130h+var_D0]
0x180028a73  mov     rax, [r14+0F8h]
0x180028a7a  mov     rdx, rdi
0x180028a7d  mov     rcx, rsi
0x180028a80  movaps  [rbp+130h+var_110], xmm10
0x180028a85  movsd   [rbp+130h+var_100], xmm11
0x180028a8b  movaps  [rbp+130h+var_F0], xmm8
0x180028a90  movsd   [rbp+130h+var_E0], xmm9
0x180028a96  movaps  [rbp+130h+var_D0], xmm6
0x180028a9a  movsd   [rbp+130h+var_C0], xmm7
0x180028a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028aa4  mov     rcx, rdi; bstrString
0x180028aa7  call    cs:__imp_SysFreeString
0x180028aad  lea     rcx, [rsp+230h+var_1D0+8]; pvarg
0x180028ab2  call    cs:__imp_VariantClear
0x180028ab8  lea     rcx, [rbp+130h+var_1B0]; pvarg
0x180028abc  call    cs:__imp_VariantClear
0x180028ac2  lea     rcx, [rbp+130h+pvarg]; pvarg
0x180028ac6  call    cs:__imp_VariantClear
0x180028acc  lea     rcx, [rbp+130h+var_180]; pvarg
0x180028ad0  call    cs:__imp_VariantClear
0x180028ad6  mov     ecx, ebx
0x180028ad8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028add  lea     rcx, [rbp+130h+arg_18]
0x180028ae4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028ae9  lea     rcx, [rbp+130h+arg_10]
0x180028af0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028af5  lea     rcx, [rbp+130h+arg_8]
0x180028afc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028b01  lea     rcx, [rbp+130h+arg_0]
0x180028b08  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028b0d  lea     rcx, [rsp+230h+var_1F0]
0x180028b12  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028b17  lea     rcx, [rsp+230h+var_1E8]
0x180028b1c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028b21  lea     rcx, [rsp+230h+var_1E0]
0x180028b26  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028b2b  lea     rcx, [rsp+230h+var_1D8]
0x180028b30  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028b35  lea     rcx, [rbp+130h+var_168]; pvarg
0x180028b39  call    cs:__imp_VariantClear
0x180028b3f  lea     rcx, [rbp+130h+var_150]; pvarg
0x180028b43  call    cs:__imp_VariantClear
0x180028b49  lea     rcx, [rsp+230h+var_1D0]
0x180028b4e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028b53  lea     r11, [rsp+230h+var_28]
0x180028b5b  mov     eax, ebx
0x180028b5d  movaps  xmm6, xmmword ptr [r11-18h]
0x180028b62  movaps  xmm7, xmmword ptr [r11-28h]
0x180028b67  movaps  xmm8, xmmword ptr [r11-38h]
0x180028b6c  movaps  xmm9, xmmword ptr [r11-48h]
0x180028b71  movaps  xmm10, xmmword ptr [r11-58h]
0x180028b76  movaps  xmm11, xmmword ptr [r11-68h]
0x180028b7b  movaps  xmm12, xmmword ptr [r11-78h]
0x180028b80  movaps  xmm13, xmmword ptr [r11-88h]
0x180028b88  mov     rsp, r11
0x180028b8b  pop     r14
0x180028b8d  pop     r12
0x180028b8f  pop     rdi
0x180028b90  pop     rsi
0x180028b91  pop     rbx
0x180028b92  pop     rbp
0x180028b93  retn
0x180028b94  mov     ecx, 8007000Eh; int
0x180028b99  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180028b9f  mov     eax, 0Ah
0x180028ba4  mov     ecx, 8007000Eh; int
0x180028ba9  mov     word ptr [rbp+130h+pvarg], ax
0x180028bad  mov     dword ptr [rbp+130h+pvarg+8], ecx
0x180028bb0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180028bb6  mov     eax, 0Ah
0x180028bbb  mov     ecx, 8007000Eh; int
0x180028bc0  mov     word ptr [rbp+130h+var_1B0], ax
0x180028bc4  mov     dword ptr [rbp+130h+var_1B0+8], ecx
0x180028bc7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180028bcd  mov     eax, 0Ah
0x180028bd2  mov     ecx, 8007000Eh; int
0x180028bd7  mov     word ptr [rsp+230h+var_1D0+8], ax
0x180028bdc  mov     dword ptr [rsp+230h+var_1D0+10h], ecx
0x180028be0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
