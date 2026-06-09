# ConfirmUninstall(HWND__ *,IShellItem2 *,HICON__ *)

- ea: `0x180006fd8`
- end: `0x18000742b`
- name: `?ConfirmUninstall@@YAJPEAUHWND__@@PEAUIShellItem2@@PEAUHICON__@@@Z`
- size: `1107`
- prototype: `__int64 __fastcall(HWND, struct IShellItem2 *, HICON)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180007a10`
- `0x18000a2b0`

## callees

- `0x180006fd8`
- `0x18000836c`
- `0x18000bcf4`
- `0x18000bdec`
- `0x18000be1c`
- `0x18000c966`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800071e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800072cd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000733b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007346`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800071e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800072cd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000733b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007346`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071f6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000710e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000710e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800073ab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800073cd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800073ab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800073cd`

## pseudocode

```c
__int64 __fastcall ConfirmUninstall(HWND a1, struct IShellItem2 *a2, HICON a3)
{
  int v6; // eax
  struct IShellItem2Vtbl *lpVtbl; // rax
  int v8; // ebx
  struct IShellItem2Vtbl *v9; // rax
  char *v10; // rax
  struct IShellItem2Vtbl *v11; // rax
  int v12; // ebx
  __int64 v13; // r8
  _QWORD *v14; // rcx
  int v15; // ebx
  __int64 v16; // r8
  BYTE *pData; // r15
  unsigned int ulVal; // esi
  int v20; // edi
  const WCHAR *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  PROPVARIANT v24; // [rsp+30h] [rbp-D0h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp-B8h] BYREF
  PROPVARIANT v26; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT v27; // [rsp+78h] [rbp-88h] BYREF
  int v28; // [rsp+90h] [rbp-70h] BYREF
  HWND v29; // [rsp+94h] [rbp-6Ch]
  HINSTANCE v30; // [rsp+9Ch] [rbp-64h]
  int v31; // [rsp+A4h] [rbp-5Ch]
  int v32; // [rsp+A8h] [rbp-58h]
  __int64 v33; // [rsp+ACh] [rbp-54h]
  HICON v34; // [rsp+B4h] [rbp-4Ch]
  __int64 v35; // [rsp+BCh] [rbp-44h]
  LARGE_INTEGER hVal; // [rsp+C4h] [rbp-3Ch]
  int v37; // [rsp+D8h] [rbp-28h]
  __int64 v38; // [rsp+10Ch] [rbp+Ch]
  __int64 v39; // [rsp+114h] [rbp+14h]
  int v40; // [rsp+12Ch] [rbp+2Ch]
  int v41; // [rsp+180h] [rbp+80h] BYREF
  LPVOID pv; // [rsp+188h] [rbp+88h] BYREF
  __int64 v43; // [rsp+190h] [rbp+90h] BYREF
  LPVOID ppv; // [rsp+198h] [rbp+98h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26);
  memset_0(&v28, 0, 0xA0u);
  v30 = g_hinst;
  v6 = v31;
  v28 = 160;
  v29 = a1;
  v32 = 6;
  v37 = 7;
  if ( a3 )
    v6 = 2;
  v34 = a3;
  v31 = v6;
  v33 = 1001;
  lpVtbl = a2->lpVtbl;
  v35 = 1003;
  v40 = 200;
  memset(&v26, 0, sizeof(v26));
  if ( ((int (__fastcall *)(struct IShellItem2 *, const PROPERTYKEY *, PROPVARIANT *))lpVtbl->GetProperty)(
         a2,
         &PKEY_NAME,
         &v26) >= 0
    && v26.vt == 31 )
  {
    hVal = v26.hVal;
  }
  else
  {
    hVal.QuadPart = 1004;
  }
  ppv = 0;
  v8 = 0;
  memset(&v27, 0, sizeof(v27));
  if ( CoCreateInstance(&rclsid, 0, 1u, &GUID_2972cef7_7f0f_41db_926f_d2ee5fca715b, &ppv) >= 0 )
  {
    v43 = 0;
    if ( (*(int (__fastcall **)(LPVOID, __int64 *, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, qword_1800102C8, &v43) >= 0 )
    {
      pv = 0;
      if ( (*(int (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v43 + 40LL))(v43, 0, &pv) >= 0 )
      {
        *(_OWORD *)&v24.vt = 0;
        if ( (int)InterfaceIDToContainerID((const unsigned __int16 *)pv, (struct _GUID *)&v24) >= 0 )
        {
          v9 = a2->lpVtbl;
          memset(&pvar, 0, sizeof(pvar));
          if ( ((int (__fastcall *)(struct IShellItem2 *, const PROPERTYKEY *, PROPVARIANT *))v9->GetProperty)(
                 a2,
                 &PKEY_Device_ContainerId,
                 &pvar) >= 0
            && pvar.vt == 72 )
          {
            v10 = (char *)*pvar.pbstrVal - *(_QWORD *)&v24.vt;
            if ( *pvar.pbstrVal == *(BSTR *)&v24.vt )
              v10 = (char *)(*(_QWORD *)(pvar.hVal.QuadPart + 8) - v24.hVal.QuadPart);
            if ( !v10 )
              v8 = 1;
          }
          PropVariantClear(&pvar);
        }
      }
      CoTaskMemFree(pv);
    }
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v8 )
  {
    v39 = 1007;
    v38 = 0xFFFF;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28);
  v11 = a2->lpVtbl;
  memset(&v24, 0, sizeof(v24));
  v12 = ((__int64 (__fastcall *)(struct IShellItem2 *, const PROPERTYKEY *, PROPVARIANT *))v11->GetProperty)(
          a2,
          &PKEY_Devices_InterfacePaths,
          &v24);
  if ( v12 < 0 )
    goto LABEL_34;
  if ( v24.vt != 4127 )
  {
    v12 = -2147418113;
LABEL_34:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_35;
  }
  pData = v24.bstrblobVal.pData;
  v12 = 1;
  ulVal = v24.ulVal;
  v20 = 0;
  if ( !v24.lVal )
    goto LABEL_34;
  while ( 1 )
  {
    v21 = *(const WCHAR **)&pData[8 * v20];
    if ( !v21 )
      goto LABEL_54;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    if ( (unsigned int)v22 <= 0x26 )
      goto LABEL_54;
    if ( CompareStringOrdinal(v21, 38, L"{884b96c3-56ef-11d1-bc8c-00a0c91405dd}", 38, 1) == 2 )
      break;
    if ( CompareStringOrdinal(*(LPCWCH *)&pData[8 * v20], 38, L"{378DE44C-56EF-11D1-BC8C-00A0C91405DD}", 38, 1) == 2 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v23 = 30;
LABEL_59:
        WPP_SF_(v14[2], v23);
        v14 = WPP_GLOBAL_Control;
        goto LABEL_60;
      }
      goto LABEL_60;
    }
LABEL_54:
    if ( ++v20 >= ulVal )
      goto LABEL_34;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v23 = 29;
    goto LABEL_59;
  }
LABEL_60:
  v12 = 0;
LABEL_35:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x20) != 0 )
    WPP_SF_d(v14[2], 31, v13, (unsigned int)v12);
  PropVariantClear(&v24);
  if ( !v12 )
  {
    v39 = 1006;
    v38 = 0xFFFF;
  }
  v41 = 0;
  v15 = IsolationAwareTaskDialogIndirect(&v28, &v41);
  if ( v15 >= 0 && v41 == 7 )
    v15 = -2147023673;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v16, (unsigned int)v15);
  PropVariantClear(&v27);
  PropVariantClear(&v26);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180006fd8  push    rbp
0x180006fda  push    rbx
0x180006fdb  push    rsi
0x180006fdc  push    rdi
0x180006fdd  push    r12
0x180006fdf  push    r13
0x180006fe1  push    r14
0x180006fe3  push    r15
0x180006fe5  lea     rbp, [rsp-38h]
0x180006fea  sub     rsp, 138h
0x180006ff1  mov     rbx, r8
0x180006ff4  mov     rdi, rdx
0x180006ff7  mov     rsi, rcx
0x180006ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x180007001  lea     r13, WPP_GLOBAL_Control
0x180007008  cmp     rcx, r13
0x18000700b  jz      short loc_180007021
0x18000700d  test    byte ptr [rcx+1Ch], 20h
0x180007011  jz      short loc_180007021
0x180007013  mov     rcx, [rcx+10h]
0x180007017  mov     edx, 1Ah
0x18000701c  call    WPP_SF_
0x180007021  mov     r14d, 0A0h
0x180007027  lea     rcx, [rbp+70h+var_E0]; void *
0x18000702b  mov     r8d, r14d; Size
0x18000702e  xor     edx, edx; Val
0x180007030  call    memset_0
0x180007035  mov     rax, cs:g_hinst
0x18000703c  lea     r8, [rsp+170h+var_110]
0x180007041  mov     [rbp+70h+var_D4], rax
0x180007045  lea     rdx, PKEY_NAME
0x18000704c  mov     eax, [rbp+70h+var_CC]
0x18000704f  mov     ecx, 2
0x180007054  xorps   xmm0, xmm0
0x180007057  mov     [rbp+70h+var_E0], r14d
0x18000705b  xor     r12d, r12d
0x18000705e  mov     [rbp+70h+var_DC], rsi
0x180007062  test    rbx, rbx
0x180007065  mov     [rbp+70h+var_C8], 6
0x18000706c  mov     [rbp+70h+var_98], 7
0x180007073  cmovnz  eax, ecx
0x180007076  mov     [rbp+70h+var_BC], rbx
0x18000707a  mov     [rbp+70h+var_CC], eax
0x18000707d  mov     rcx, rdi
0x180007080  xor     eax, eax
0x180007082  mov     [rbp+70h+var_C4], 3E9h
0x18000708a  mov     qword ptr [rsp+170h+var_110+10h], rax
0x18000708f  mov     rax, [rdi]
0x180007092  mov     [rbp+70h+var_B4], 3EBh
0x18000709a  mov     [rbp+70h+var_44], 0C8h
0x1800070a1  movups  xmmword ptr [rsp+170h+var_110], xmm0
0x1800070a6  mov     rax, [rax+68h]
0x1800070aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070af  lea     ecx, [r12+1Fh]
0x1800070b4  test    eax, eax
0x1800070b6  js      short loc_1800070CA
0x1800070b8  cmp     word ptr [rsp+170h+var_110], cx
0x1800070bd  jnz     short loc_1800070CA
0x1800070bf  mov     rax, qword ptr [rsp+170h+var_110+8]
0x1800070c4  mov     [rbp+70h+var_AC], rax
0x1800070c8  jmp     short loc_1800070D2
0x1800070ca  mov     [rbp+70h+var_AC], 3ECh
0x1800070d2  xor     eax, eax
0x1800070d4  mov     [rbp+70h+arg_18], r12
0x1800070db  mov     qword ptr [rbp+70h+var_F8+10h], rax
0x1800070df  lea     r9, _GUID_2972cef7_7f0f_41db_926f_d2ee5fca715b; riid
0x1800070e6  lea     rax, [rbp+70h+arg_18]
0x1800070ed  xorps   xmm0, xmm0
0x1800070f0  mov     esi, 1
0x1800070f5  mov     [rsp+170h+ppv], rax; ppv
0x1800070fa  mov     r8d, esi; dwClsContext
0x1800070fd  lea     rcx, rclsid; rclsid
0x180007104  xor     edx, edx; pUnkOuter
0x180007106  mov     ebx, r12d
0x180007109  movups  xmmword ptr [rsp+170h+var_F8], xmm0
0x18000710e  call    cs:__imp_CoCreateInstance
0x180007114  test    eax, eax
0x180007116  js      loc_180007214
0x18000711c  mov     rcx, [rbp+70h+arg_18]
0x180007123  lea     r8, [rbp+70h+arg_10]
0x18000712a  mov     [rbp+70h+arg_10], r12
0x180007131  lea     rdx, qword_1800102C8
0x180007138  mov     rax, [rcx]
0x18000713b  mov     rax, [rax+18h]
0x18000713f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007144  test    eax, eax
0x180007146  js      loc_1800071FC
0x18000714c  mov     rcx, [rbp+70h+arg_10]
0x180007153  lea     r8, [rbp+70h+pv]
0x18000715a  mov     [rbp+70h+pv], r12
0x180007161  xor     edx, edx
0x180007163  mov     rax, [rcx]
0x180007166  mov     rax, [rax+28h]
0x18000716a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000716f  test    eax, eax
0x180007171  js      short loc_1800071EF
0x180007173  mov     rcx, [rbp+70h+pv]; unsigned __int16 *
0x18000717a  lea     rdx, [rsp+170h+var_140]; struct _GUID *
0x18000717f  xorps   xmm0, xmm0
0x180007182  movups  xmmword ptr [rsp+170h+var_140], xmm0
0x180007187  call    ?InterfaceIDToContainerID@@YAJPEBGPEAU_GUID@@@Z; InterfaceIDToContainerID(ushort const *,_GUID *)
0x18000718c  test    eax, eax
0x18000718e  js      short loc_1800071EF
0x180007190  xor     eax, eax
0x180007192  lea     r8, [rsp+170h+pvar]
0x180007197  mov     qword ptr [rsp+170h+pvar+10h], rax
0x18000719c  lea     rdx, PKEY_Device_ContainerId
0x1800071a3  mov     rax, [rdi]
0x1800071a6  xorps   xmm0, xmm0
0x1800071a9  mov     rcx, rdi
0x1800071ac  movups  xmmword ptr [rsp+170h+pvar], xmm0
0x1800071b1  mov     rax, [rax+68h]
0x1800071b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071ba  test    eax, eax
0x1800071bc  js      short loc_1800071E4
0x1800071be  cmp     word ptr [rsp+170h+pvar], 48h ; 'H'
0x1800071c4  jnz     short loc_1800071E4
0x1800071c6  mov     rcx, qword ptr [rsp+170h+pvar+8]
0x1800071cb  mov     rax, [rcx]
0x1800071ce  sub     rax, qword ptr [rsp+170h+var_140]
0x1800071d3  jnz     short loc_1800071DE
0x1800071d5  mov     rax, [rcx+8]
0x1800071d9  sub     rax, qword ptr [rsp+170h+var_140+8]
0x1800071de  test    rax, rax
0x1800071e1  cmovz   ebx, esi
0x1800071e4  lea     rcx, [rsp+170h+pvar]; pvar
0x1800071e9  call    cs:__imp_PropVariantClear
0x1800071ef  mov     rcx, [rbp+70h+pv]; pv
0x1800071f6  call    cs:__imp_CoTaskMemFree
0x1800071fc  mov     rcx, [rbp+70h+arg_10]
0x180007203  test    rcx, rcx
0x180007206  jz      short loc_180007214
0x180007208  mov     rax, [rcx]
0x18000720b  mov     rax, [rax+10h]
0x18000720f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007214  mov     rcx, [rbp+70h+arg_18]
0x18000721b  test    rcx, rcx
0x18000721e  jz      short loc_18000722C
0x180007220  mov     rax, [rcx]
0x180007223  mov     rax, [rax+10h]
0x180007227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000722c  test    ebx, ebx
0x18000722e  jz      short loc_180007240
0x180007230  mov     [rbp+70h+var_5C], 3EFh
0x180007238  mov     [rbp+70h+var_64], 0FFFFh
0x180007240  mov     rcx, cs:WPP_GLOBAL_Control
0x180007247  cmp     rcx, r13
0x18000724a  jz      short loc_180007260
0x18000724c  test    byte ptr [rcx+1Ch], 20h
0x180007250  jz      short loc_180007260
0x180007252  mov     rcx, [rcx+10h]
0x180007256  mov     edx, 1Ch
0x18000725b  call    WPP_SF_
0x180007260  xor     eax, eax
0x180007262  lea     r8, [rsp+170h+var_140]
0x180007267  mov     qword ptr [rsp+170h+var_140+10h], rax
0x18000726c  lea     rdx, PKEY_Devices_InterfacePaths
0x180007273  mov     rax, [rdi]
0x180007276  xorps   xmm0, xmm0
0x180007279  mov     rcx, rdi
0x18000727c  movups  xmmword ptr [rsp+170h+var_140], xmm0
0x180007281  mov     rax, [rax+68h]
0x180007285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000728a  mov     ebx, eax
0x18000728c  test    eax, eax
0x18000728e  js      short loc_1800072A5
0x180007290  mov     eax, 101Fh
0x180007295  cmp     word ptr [rsp+170h+var_140], ax
0x18000729a  jz      loc_180007362
0x1800072a0  mov     ebx, 8000FFFFh
0x1800072a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072ac  cmp     rcx, r13
0x1800072af  jz      short loc_1800072C8
0x1800072b1  test    byte ptr [rcx+1Ch], 20h
0x1800072b5  jz      short loc_1800072C8
0x1800072b7  mov     rcx, [rcx+10h]
0x1800072bb  mov     edx, 1Fh
0x1800072c0  mov     r9d, ebx
0x1800072c3  call    WPP_SF_d
0x1800072c8  lea     rcx, [rsp+170h+var_140]; pvar
0x1800072cd  call    cs:__imp_PropVariantClear
0x1800072d3  test    ebx, ebx
0x1800072d5  jnz     short loc_1800072E7
0x1800072d7  mov     [rbp+70h+var_5C], 3EEh
0x1800072df  mov     [rbp+70h+var_64], 0FFFFh
0x1800072e7  lea     rdx, [rbp+70h+arg_0]
0x1800072ee  mov     [rbp+70h+arg_0], r12d
0x1800072f5  lea     rcx, [rbp+70h+var_E0]
0x1800072f9  call    IsolationAwareTaskDialogIndirect
0x1800072fe  mov     ebx, eax
0x180007300  test    eax, eax
0x180007302  js      short loc_180007313
0x180007304  cmp     [rbp+70h+arg_0], 7
0x18000730b  mov     eax, 800704C7h
0x180007310  cmovz   ebx, eax
0x180007313  mov     rcx, cs:WPP_GLOBAL_Control
0x18000731a  cmp     rcx, r13
0x18000731d  jz      short loc_180007336
0x18000731f  test    byte ptr [rcx+1Ch], 20h
0x180007323  jz      short loc_180007336
0x180007325  mov     rcx, [rcx+10h]
0x180007329  mov     edx, 1Bh
0x18000732e  mov     r9d, ebx
0x180007331  call    WPP_SF_d
0x180007336  lea     rcx, [rsp+170h+var_F8]; pvar
0x18000733b  call    cs:__imp_PropVariantClear
0x180007341  lea     rcx, [rsp+170h+var_110]; pvar
0x180007346  call    cs:__imp_PropVariantClear
0x18000734c  mov     eax, ebx
0x18000734e  add     rsp, 138h
0x180007355  pop     r15
0x180007357  pop     r14
0x180007359  pop     r13
0x18000735b  pop     r12
0x18000735d  pop     rdi
0x18000735e  pop     rsi
0x18000735f  pop     rbx
0x180007360  pop     rbp
0x180007361  retn
0x180007362  mov     r15, qword ptr [rsp+170h+var_140+10h]
0x180007367  mov     ebx, esi
0x180007369  mov     esi, dword ptr [rsp+170h+var_140+8]
0x18000736d  mov     edi, r12d
0x180007370  test    esi, esi
0x180007372  jz      loc_1800072A5
0x180007378  mov     r14d, edi
0x18000737b  mov     rcx, [r15+r14*8]; lpString1
0x18000737f  test    rcx, rcx
0x180007382  jz      short loc_1800073D8
0x180007384  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007388  inc     rax
0x18000738b  cmp     [rcx+rax*2], r12w
0x180007390  jnz     short loc_180007388
0x180007392  cmp     eax, 26h ; '&'
0x180007395  jbe     short loc_1800073D8
0x180007397  mov     r9d, 26h ; '&'; cchCount2
0x18000739d  mov     dword ptr [rsp+170h+ppv], ebx; bIgnoreCase
0x1800073a1  mov     edx, r9d; cchCount1
0x1800073a4  lea     r8, String2; "{884b96c3-56ef-11d1-bc8c-00a0c91405dd}"
0x1800073ab  call    cs:__imp_CompareStringOrdinal
0x1800073b1  cmp     eax, 2
0x1800073b4  jz      short loc_180007412
0x1800073b6  mov     rcx, [r15+r14*8]; lpString1
0x1800073ba  lea     r8, a378de44c56ef11; "{378DE44C-56EF-11D1-BC8C-00A0C91405DD}"
0x1800073c1  mov     edx, 26h ; '&'; cchCount1
0x1800073c6  mov     dword ptr [rsp+170h+ppv], ebx; bIgnoreCase
0x1800073ca  mov     r9d, edx; cchCount2
0x1800073cd  call    cs:__imp_CompareStringOrdinal
0x1800073d3  cmp     eax, 2
0x1800073d6  jz      short loc_1800073E3
0x1800073d8  inc     edi
0x1800073da  cmp     edi, esi
0x1800073dc  jb      short loc_180007378
0x1800073de  jmp     loc_1800072A5
0x1800073e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073ea  cmp     rcx, r13
0x1800073ed  jz      short loc_18000740A
0x1800073ef  test    byte ptr [rcx+1Ch], 8
0x1800073f3  jz      short loc_18000740A
0x1800073f5  mov     edx, 1Eh
0x1800073fa  mov     rcx, [rcx+10h]
0x1800073fe  call    WPP_SF_
0x180007403  mov     rcx, cs:WPP_GLOBAL_Control
0x18000740a  mov     ebx, r12d
0x18000740d  jmp     loc_1800072AC
0x180007412  mov     rcx, cs:WPP_GLOBAL_Control
0x180007419  cmp     rcx, r13
0x18000741c  jz      short loc_18000740A
0x18000741e  test    byte ptr [rcx+1Ch], 8
0x180007422  jz      short loc_18000740A
0x180007424  mov     edx, 1Dh
0x180007429  jmp     short loc_1800073FA
```
