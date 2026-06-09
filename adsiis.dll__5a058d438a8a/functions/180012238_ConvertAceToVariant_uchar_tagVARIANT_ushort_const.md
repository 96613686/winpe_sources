# ConvertAceToVariant(uchar *,tagVARIANT *,ushort const *)

- ea: `0x180012238`
- end: `0x18001256e`
- name: `?ConvertAceToVariant@@YAJPEAEPEAUtagVARIANT@@PEBG@Z`
- size: `822`
- prototype: `int(unsigned __int8 *, struct tagVARIANT *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180012084`

## callees

- `0x180012238`
- `0x18001297c`
- `0x18001d6c0`
- `0x18001e010`

## import_xrefs

- `ole32!StringFromGUID2` at `0x180012351`
- `ole32!StringFromGUID2` at `0x180012379`
- `ole32!StringFromGUID2` at `0x180012351`
- `ole32!StringFromGUID2` at `0x180012379`
- `ole32!CoCreateInstance` at `0x1800122cf`
- `ole32!CoCreateInstance` at `0x1800122cf`
- `OLEAUT32!__imp_SysAllocString` at `0x18001241a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800124c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800124fd`
- `OLEAUT32!__imp_SysAllocString` at `0x18001241a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800124c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800124fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001242f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124f4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001252e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001242f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124f4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001252e`
- `OLEAUT32!__imp_VariantInit` at `0x1800122ab`
- `OLEAUT32!__imp_VariantInit` at `0x1800122ab`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800123b0`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800123b0`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180012453`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180012453`

## pseudocode

```c
__int64 __fastcall ConvertAceToVariant(unsigned __int8 *a1, struct tagVARIANT *a2, const unsigned __int16 *a3)
{
  OLECHAR *v4; // rdi
  HRESULT v7; // ebx
  unsigned int v8; // r14d
  unsigned int v9; // r12d
  unsigned __int8 *v10; // rbx
  BSTR v11; // rax
  OLECHAR *v12; // rbx
  BSTR v14; // rax
  OLECHAR *v15; // rbx
  BSTR v16; // rax
  OLECHAR *v17; // rbx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v19; // [rsp+38h] [rbp-C8h]
  unsigned int v20; // [rsp+3Ch] [rbp-C4h]
  LONGLONG v21; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR *v22; // [rsp+48h] [rbp-B8h] BYREF
  GUID rguid; // [rsp+50h] [rbp-B0h] BYREF
  GUID v24; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[264]; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR psz[264]; // [rsp+280h] [rbp+180h] BYREF

  ppv = 0;
  sz[0] = 0;
  psz[0] = 0;
  v21 = 0;
  v4 = 0;
  v22 = 0;
  rguid = 0;
  v24 = 0;
  VariantInit(a2);
  v7 = CoCreateInstance(&CLSID_AccessControlEntry, 0, 1u, &IID_IADsAccessControlEntry, &ppv);
  if ( v7 < 0 )
    goto LABEL_18;
  v8 = 0;
  v9 = *a1;
  v20 = a1[1];
  v19 = *((_DWORD *)a1 + 1);
  if ( v9 < 4 )
  {
    v10 = a1 + 8;
  }
  else
  {
    if ( v9 != 5 && v9 != 6 && v9 - 7 > 1 )
      goto LABEL_14;
    v8 = *((_DWORD *)a1 + 2);
    v10 = a1 + 12;
    if ( (v8 & 1) != 0 )
    {
      rguid = *(GUID *)v10;
      StringFromGUID2(&rguid, sz, 260);
      v10 = a1 + 28;
    }
    if ( (v8 & 2) != 0 )
    {
      v24 = *(GUID *)v10;
      StringFromGUID2(&v24, psz, 260);
      v10 += 16;
    }
  }
  if ( !v10 || (int)ConvertSidToFriendlyName(v10, &v22, a3) < 0 )
  {
LABEL_14:
    v4 = AllocADsStr(L"Unknown Trustee");
    goto LABEL_15;
  }
  v4 = v22;
LABEL_15:
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 64LL))(ppv, v19);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 96LL))(ppv, v20);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 80LL))(ppv, v9);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 112LL))(ppv, v8);
  if ( (v8 & 1) != 0 )
  {
    v11 = SysAllocString(sz);
    v12 = v11;
    if ( !v11 )
    {
LABEL_17:
      v7 = -2147024882;
      SysFreeString(0);
      goto LABEL_18;
    }
    (*(void (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 128LL))(ppv, v11);
    SysFreeString(v12);
  }
  if ( (v8 & 2) != 0 )
  {
    v14 = SysAllocString(psz);
    v15 = v14;
    if ( !v14 )
      goto LABEL_17;
    (*(void (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 144LL))(ppv, v14);
    SysFreeString(v15);
  }
  v16 = SysAllocString(v4);
  v17 = v16;
  if ( v4 && !v16 )
    goto LABEL_17;
  (*(void (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 160LL))(ppv, v16);
  SysFreeString(v17);
  v7 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, LONGLONG *))ppv)(ppv, &IID_IDispatch, &v21);
  if ( v7 >= 0 )
  {
    a2->llVal = v21;
    a2->vt = 9;
    goto LABEL_20;
  }
LABEL_18:
  if ( v21 )
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_20:
  if ( v4 )
    FreeADsStr(v4);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180012238  mov     [rsp-8+arg_18], rbx
0x18001223d  push    rbp
0x18001223e  push    rsi
0x18001223f  push    rdi
0x180012240  push    r12
0x180012242  push    r13
0x180012244  push    r14
0x180012246  push    r15
0x180012248  lea     rbp, [rsp-3A0h]
0x180012250  sub     rsp, 4A0h
0x180012257  mov     rax, cs:__security_cookie
0x18001225e  xor     rax, rsp
0x180012261  mov     [rbp+3D0h+var_40], rax
0x180012268  xor     eax, eax
0x18001226a  mov     [rsp+4D0h+var_4A0], 0
0x180012273  mov     rsi, rcx
0x180012276  mov     [rsp+4D0h+sz], ax
0x18001227b  xorps   xmm0, xmm0
0x18001227e  mov     [rbp+3D0h+psz], ax
0x180012285  xorps   xmm1, xmm1
0x180012288  mov     [rsp+4D0h+var_490], 0
0x180012291  xor     edi, edi
0x180012293  mov     rcx, rdx; pvarg
0x180012296  mov     [rsp+4D0h+var_488], rdi
0x18001229b  mov     r13, r8
0x18001229e  movups  xmmword ptr [rsp+4D0h+rguid.Data1], xmm0
0x1800122a3  mov     r15, rdx
0x1800122a6  movups  xmmword ptr [rsp+4D0h+var_470.Data1], xmm1
0x1800122ab  call    cs:__imp_VariantInit
0x1800122b1  lea     rax, [rsp+4D0h+var_4A0]
0x1800122b6  xor     edx, edx; pUnkOuter
0x1800122b8  lea     r9, IID_IADsAccessControlEntry; riid
0x1800122bf  mov     [rsp+4D0h+ppv], rax; ppv
0x1800122c4  lea     r8d, [rdi+1]; dwClsContext
0x1800122c8  lea     rcx, CLSID_AccessControlEntry; rclsid
0x1800122cf  call    cs:__imp_CoCreateInstance
0x1800122d5  mov     ebx, eax
0x1800122d7  test    eax, eax
0x1800122d9  js      loc_180012435
0x1800122df  movzx   eax, byte ptr [rsi+1]
0x1800122e3  xor     r14d, r14d
0x1800122e6  movzx   r12d, byte ptr [rsi]
0x1800122ea  mov     [rsp+4D0h+var_494], eax
0x1800122ee  mov     eax, [rsi+4]
0x1800122f1  mov     [rsp+4D0h+var_498], eax
0x1800122f5  mov     eax, r12d
0x1800122f8  test    r12d, r12d
0x1800122fb  jz      loc_180012385
0x180012301  sub     eax, 1
0x180012304  jz      short loc_180012385
0x180012306  sub     eax, 1
0x180012309  jz      short loc_180012385
0x18001230b  sub     eax, 1
0x18001230e  jz      short loc_180012385
0x180012310  sub     eax, 2
0x180012313  jz      short loc_180012328
0x180012315  sub     eax, 1
0x180012318  jz      short loc_180012328
0x18001231a  sub     eax, 1
0x18001231d  jz      short loc_180012328
0x18001231f  cmp     eax, 1
0x180012322  jnz     loc_1800123A9
0x180012328  mov     r14d, [rsi+8]
0x18001232c  lea     rbx, [rsi+0Ch]
0x180012330  mov     edi, 104h
0x180012335  test    r14b, 1
0x180012339  jz      short loc_18001235B
0x18001233b  movups  xmm0, xmmword ptr [rbx]
0x18001233e  mov     r8d, edi; cchMax
0x180012341  lea     rdx, [rsp+4D0h+sz]; lpsz
0x180012346  lea     rcx, [rsp+4D0h+rguid]; rguid
0x18001234b  movdqu  xmmword ptr [rsp+4D0h+rguid.Data1], xmm0
0x180012351  call    cs:__imp_StringFromGUID2
0x180012357  add     rbx, 10h
0x18001235b  test    r14b, 2
0x18001235f  jz      short loc_180012389
0x180012361  movups  xmm0, xmmword ptr [rbx]
0x180012364  mov     r8d, edi; cchMax
0x180012367  lea     rdx, [rbp+3D0h+psz]; lpsz
0x18001236e  lea     rcx, [rsp+4D0h+var_470]; rguid
0x180012373  movdqu  xmmword ptr [rsp+4D0h+var_470.Data1], xmm0
0x180012379  call    cs:__imp_StringFromGUID2
0x18001237f  add     rbx, 10h
0x180012383  jmp     short loc_180012389
0x180012385  lea     rbx, [rsi+8]
0x180012389  test    rbx, rbx
0x18001238c  jz      short loc_1800123A9
0x18001238e  mov     r8, r13; unsigned __int16 *
0x180012391  lea     rdx, [rsp+4D0h+var_488]; unsigned __int16 **
0x180012396  mov     rcx, rbx; pSid
0x180012399  call    ?ConvertSidToFriendlyName@@YAJPEAXPEAPEAGPEBG@Z; ConvertSidToFriendlyName(void *,ushort * *,ushort const *)
0x18001239e  test    eax, eax
0x1800123a0  js      short loc_1800123A9
0x1800123a2  mov     rdi, [rsp+4D0h+var_488]
0x1800123a7  jmp     short loc_1800123B9
0x1800123a9  lea     rcx, pStr; "Unknown Trustee"
0x1800123b0  call    cs:__imp_AllocADsStr
0x1800123b6  mov     rdi, rax
0x1800123b9  mov     rcx, [rsp+4D0h+var_4A0]
0x1800123be  mov     edx, [rsp+4D0h+var_498]
0x1800123c2  mov     r8, [rcx]
0x1800123c5  mov     rax, [r8+40h]
0x1800123c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123ce  mov     rcx, [rsp+4D0h+var_4A0]
0x1800123d3  mov     edx, [rsp+4D0h+var_494]
0x1800123d7  mov     r8, [rcx]
0x1800123da  mov     rax, [r8+60h]
0x1800123de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123e3  mov     rcx, [rsp+4D0h+var_4A0]
0x1800123e8  mov     edx, r12d
0x1800123eb  mov     rax, [rcx]
0x1800123ee  mov     rax, [rax+50h]
0x1800123f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123f7  mov     rcx, [rsp+4D0h+var_4A0]
0x1800123fc  mov     edx, r14d
0x1800123ff  mov     rax, [rcx]
0x180012402  mov     rax, [rax+70h]
0x180012406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001240b  test    r14b, 1
0x18001240f  jz      loc_1800124BB
0x180012415  lea     rcx, [rsp+4D0h+sz]; psz
0x18001241a  call    cs:__imp_SysAllocString
0x180012420  mov     rbx, rax
0x180012423  test    rax, rax
0x180012426  jnz     short loc_18001249B
0x180012428  xor     ecx, ecx; bstrString
0x18001242a  mov     ebx, 8007000Eh
0x18001242f  call    cs:__imp_SysFreeString
0x180012435  mov     rcx, [rsp+4D0h+var_490]
0x18001243a  test    rcx, rcx
0x18001243d  jz      short loc_18001244B
0x18001243f  mov     rax, [rcx]
0x180012442  mov     rax, [rax+10h]
0x180012446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001244b  test    rdi, rdi
0x18001244e  jz      short loc_180012459
0x180012450  mov     rcx, rdi; pStr
0x180012453  call    cs:__imp_FreeADsStr
0x180012459  mov     rcx, [rsp+4D0h+var_4A0]
0x18001245e  test    rcx, rcx
0x180012461  jz      short loc_18001246F
0x180012463  mov     rax, [rcx]
0x180012466  mov     rax, [rax+10h]
0x18001246a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001246f  mov     eax, ebx
0x180012471  mov     rcx, [rbp+3D0h+var_40]
0x180012478  xor     rcx, rsp; StackCookie
0x18001247b  call    __security_check_cookie
0x180012480  mov     rbx, [rsp+4D0h+arg_18]
0x180012488  add     rsp, 4A0h
0x18001248f  pop     r15
0x180012491  pop     r14
0x180012493  pop     r13
0x180012495  pop     r12
0x180012497  pop     rdi
0x180012498  pop     rsi
0x180012499  pop     rbp
0x18001249a  retn
0x18001249b  mov     rcx, [rsp+4D0h+var_4A0]
0x1800124a0  mov     rdx, rbx
0x1800124a3  mov     rax, [rcx]
0x1800124a6  mov     rax, [rax+80h]
0x1800124ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124b2  mov     rcx, rbx; bstrString
0x1800124b5  call    cs:__imp_SysFreeString
0x1800124bb  test    r14b, 2
0x1800124bf  jz      short loc_1800124FA
0x1800124c1  lea     rcx, [rbp+3D0h+psz]; psz
0x1800124c8  call    cs:__imp_SysAllocString
0x1800124ce  mov     rbx, rax
0x1800124d1  test    rax, rax
0x1800124d4  jz      loc_180012428
0x1800124da  mov     rcx, [rsp+4D0h+var_4A0]
0x1800124df  mov     rdx, rbx
0x1800124e2  mov     rax, [rcx]
0x1800124e5  mov     rax, [rax+90h]
0x1800124ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124f1  mov     rcx, rbx; bstrString
0x1800124f4  call    cs:__imp_SysFreeString
0x1800124fa  mov     rcx, rdi; psz
0x1800124fd  call    cs:__imp_SysAllocString
0x180012503  mov     rbx, rax
0x180012506  test    rdi, rdi
0x180012509  jz      short loc_180012514
0x18001250b  test    rax, rax
0x18001250e  jz      loc_180012428
0x180012514  mov     rcx, [rsp+4D0h+var_4A0]
0x180012519  mov     rdx, rbx
0x18001251c  mov     rax, [rcx]
0x18001251f  mov     rax, [rax+0A0h]
0x180012526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001252b  mov     rcx, rbx; bstrString
0x18001252e  call    cs:__imp_SysFreeString
0x180012534  mov     rcx, [rsp+4D0h+var_4A0]
0x180012539  lea     r8, [rsp+4D0h+var_490]
0x18001253e  lea     rdx, IID_IDispatch
0x180012545  mov     rax, [rcx]
0x180012548  mov     rax, [rax]
0x18001254b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012550  mov     ebx, eax
0x180012552  test    eax, eax
0x180012554  js      loc_180012435
0x18001255a  mov     rax, [rsp+4D0h+var_490]
0x18001255f  mov     [r15+8], rax
0x180012563  mov     word ptr [r15], 9
0x180012569  jmp     loc_18001244B
```
