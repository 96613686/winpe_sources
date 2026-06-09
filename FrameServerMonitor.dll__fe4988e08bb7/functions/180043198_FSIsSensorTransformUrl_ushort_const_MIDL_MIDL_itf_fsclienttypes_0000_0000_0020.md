# FSIsSensorTransformUrl(ushort const *,__MIDL___MIDL_itf_fsclienttypes_0000_0000_0020 *)

- ea: `0x180043198`
- end: `0x1800434d4`
- name: `?FSIsSensorTransformUrl@@YA_NPEBGPEAU__MIDL___MIDL_itf_fsclienttypes_0000_0000_0020@@@Z`
- size: `828`
- prototype: `bool __fastcall(const unsigned __int16 *, struct __MIDL___MIDL_itf_fsclienttypes_0000_0000_0020 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180015e38`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180004f34`
- `0x180006a98`
- `0x18000cadc`
- `0x18000d498`
- `0x180043198`
- `0x1800434dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004321d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180043333`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800433c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004321d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180043333`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800433c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043441`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800432d2`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800432fc`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180043380`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800432d2`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800432fc`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180043380`

## pseudocode

```c
bool __fastcall FSIsSensorTransformUrl(
        const unsigned __int16 *a1,
        struct __MIDL___MIDL_itf_fsclienttypes_0000_0000_0020 *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  HRESULT v6; // eax
  __int64 v7; // rdx
  OLECHAR v8; // ax
  OLECHAR *v9; // rcx
  const OLECHAR *v10; // rbp
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  unsigned __int64 v14; // [rsp+30h] [rbp-248h] BYREF
  unsigned __int16 v15[18]; // [rsp+40h] [rbp-238h] BYREF
  OLECHAR sz[246]; // [rsp+64h] [rbp-214h] BYREF

  if ( !a2 )
  {
    v4 = -2147467261;
    if ( g_wppLevels )
    {
      v5 = 11;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_142e5d19e4cc32e2432bc9bbd66f9d63_Traceguids, 0, v4);
      return v4 >= 0;
    }
    return v4 >= 0;
  }
  *(_OWORD *)a2 = 0;
  *((_OWORD *)a2 + 1) = 0;
  *((_OWORD *)a2 + 2) = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    if ( !g_wppLevels )
      return v4 >= 0;
    v5 = 12;
    goto LABEL_4;
  }
  if ( !(unsigned int)_o__wcsnicmp(a1, L"sensortransform://", 18) )
  {
    memset_0(v15, 0, 0x208u);
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 13, WPP_142e5d19e4cc32e2432bc9bbd66f9d63_Traceguids, a1);
    v6 = StringCchCopyW(v15, 0x104u, a1);
    v4 = v6;
    if ( v6 >= 0 )
    {
      v8 = sz[0];
      v9 = sz;
      v10 = 0;
      while ( v8 && v8 != 58 )
        v8 = *++v9;
      if ( *v9 )
      {
        v10 = v9 + 1;
        *v9 = 0;
      }
      *(_DWORD *)a2 = 0;
      v6 = IIDFromString(sz, (LPIID)a2 + 1);
      v4 = v6;
      if ( v6 >= 0 )
      {
        v6 = IIDFromString(v10, (LPIID)a2 + 2);
        v4 = v6;
        if ( v6 >= 0 || !g_wppLevels )
          return v4 >= 0;
        v7 = 16;
      }
      else
      {
        if ( !g_wppLevels )
          return v4 >= 0;
        v7 = 15;
      }
    }
    else
    {
      if ( !g_wppLevels )
        return v4 >= 0;
      v7 = 14;
    }
    goto LABEL_45;
  }
  if ( !(unsigned int)_o__wcsnicmp(a1, L"sensortransformbuiltin://", 25) )
  {
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 17, WPP_142e5d19e4cc32e2432bc9bbd66f9d63_Traceguids, a1);
    *(_DWORD *)a2 = 1;
    *((_OWORD *)a2 + 1) = MF_SENSORTRANSFORM_BUILTIN_FACTORYCLSID;
    v6 = IIDFromString(a1 + 25, (LPIID)a2 + 2);
    v4 = v6;
    if ( v6 >= 0 || !g_wppLevels )
      return v4 >= 0;
    v7 = 18;
LABEL_45:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_142e5d19e4cc32e2432bc9bbd66f9d63_Traceguids, 0, v6);
    return v4 >= 0;
  }
  v4 = -2147024846;
  if ( !IsSensorTransformModuleEnabled() || (unsigned int)_o__wcsnicmp(a1, L"sensortransformmodule://", 24) )
    return v4 >= 0;
  v14 = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 19, WPP_142e5d19e4cc32e2432bc9bbd66f9d63_Traceguids, a1);
  *(_DWORD *)a2 = 2;
  v6 = StringCchLengthW(a1 + 24, 0x7FFFFFFFu, &v14);
  v4 = v6;
  if ( v6 < 0 )
  {
    if ( !g_wppLevels )
      return v4 >= 0;
    v7 = 20;
    goto LABEL_45;
  }
  v11 = v14;
  v12 = (unsigned __int16 *)CoTaskMemAlloc(2 * v14 + 2);
  *((_QWORD *)a2 + 4) = v12;
  if ( !v12 )
  {
    v4 = -2147024882;
    if ( !g_wppLevels )
      return v4 >= 0;
    v5 = 21;
    goto LABEL_4;
  }
  v6 = StringCchCopyW(v12, v11 + 1, a1 + 24);
  v4 = v6;
  if ( v6 < 0 && g_wppLevels )
  {
    v7 = 22;
    goto LABEL_45;
  }
  return v4 >= 0;
}

```

## disassembly

```asm
0x180043198  mov     [rsp+arg_10], rbx
0x18004319d  push    rbp
0x18004319e  push    rsi
0x18004319f  push    r14
0x1800431a1  sub     rsp, 260h
0x1800431a8  mov     rax, cs:__security_cookie
0x1800431af  xor     rax, rsp
0x1800431b2  mov     [rsp+278h+var_28], rax
0x1800431ba  xor     r14d, r14d
0x1800431bd  mov     rsi, rdx
0x1800431c0  mov     rbp, rcx
0x1800431c3  test    rdx, rdx
0x1800431c6  jnz     short loc_1800431E6
0x1800431c8  mov     ebx, 80004003h
0x1800431cd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800431d4  jb      loc_1800434A8
0x1800431da  lea     edx, [rsi+0Bh]
0x1800431dd  mov     [rsp+278h+var_258], ebx
0x1800431e1  jmp     loc_18004348E
0x1800431e6  xorps   xmm0, xmm0
0x1800431e9  movups  xmmword ptr [rdx], xmm0
0x1800431ec  movups  xmmword ptr [rdx+10h], xmm0
0x1800431f0  movups  xmmword ptr [rdx+20h], xmm0
0x1800431f4  test    rbp, rbp
0x1800431f7  jnz     short loc_180043210
0x1800431f9  mov     ebx, 80070057h
0x1800431fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043205  jb      loc_1800434A8
0x18004320b  lea     edx, [rbp+0Ch]
0x18004320e  jmp     short loc_1800431DD
0x180043210  mov     r8d, 12h
0x180043216  lea     rdx, aSensortransfor; "sensortransform://"
0x18004321d  call    cs:__imp__o__wcsnicmp
0x180043223  test    eax, eax
0x180043225  jnz     loc_180043323
0x18004322b  xor     edx, edx; Val
0x18004322d  lea     rcx, [rsp+278h+var_238]; void *
0x180043232  mov     r8d, 208h; Size
0x180043238  call    memset_0
0x18004323d  cmp     cs:byte_18005E5A5, 8
0x180043244  jb      short loc_180043268
0x180043246  mov     rcx, cs:WPP_GLOBAL_Control
0x18004324d  lea     r8, WPP_142e5d19e4cc32e2432bc9bbd66f9d63_Traceguids
0x180043254  mov     edx, 0Dh
0x180043259  mov     r9, rbp
0x18004325c  mov     rcx, [rcx+0D8h]
0x180043263  call    WPP_SF_S
0x180043268  mov     r8, rbp; unsigned __int16 *
0x18004326b  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180043270  mov     edx, 104h; unsigned __int64
0x180043275  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004327a  mov     ebx, eax
0x18004327c  test    eax, eax
0x18004327e  jns     short loc_180043297
0x180043280  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043287  jb      loc_1800434A8
0x18004328d  mov     edx, 0Eh
0x180043292  jmp     loc_18004348A
0x180043297  movzx   eax, [rsp+278h+sz]
0x18004329c  lea     rcx, [rsp+278h+sz]
0x1800432a1  mov     rbp, r14
0x1800432a4  jmp     short loc_1800432B3
0x1800432a6  cmp     ax, 3Ah ; ':'
0x1800432aa  jz      short loc_1800432B8
0x1800432ac  add     rcx, 2
0x1800432b0  movzx   eax, word ptr [rcx]
0x1800432b3  test    ax, ax
0x1800432b6  jnz     short loc_1800432A6
0x1800432b8  cmp     [rcx], r14w
0x1800432bc  jz      short loc_1800432C6
0x1800432be  lea     rbp, [rcx+2]
0x1800432c2  mov     [rcx], r14w
0x1800432c6  lea     rdx, [rsi+10h]; lpiid
0x1800432ca  mov     [rsi], r14d
0x1800432cd  lea     rcx, [rsp+278h+sz]; lpsz
0x1800432d2  call    cs:__imp_IIDFromString
0x1800432d8  mov     ebx, eax
0x1800432da  test    eax, eax
0x1800432dc  jns     short loc_1800432F5
0x1800432de  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800432e5  jb      loc_1800434A8
0x1800432eb  mov     edx, 0Fh
0x1800432f0  jmp     loc_18004348A
0x1800432f5  lea     rdx, [rsi+20h]; lpiid
0x1800432f9  mov     rcx, rbp; lpsz
0x1800432fc  call    cs:__imp_IIDFromString
0x180043302  mov     ebx, eax
0x180043304  test    eax, eax
0x180043306  jns     loc_1800434A8
0x18004330c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043313  jb      loc_1800434A8
0x180043319  mov     edx, 10h
0x18004331e  jmp     loc_18004348A
0x180043323  mov     r8d, 19h
0x180043329  lea     rdx, aSensortransfor_1; "sensortransformbuiltin://"
0x180043330  mov     rcx, rbp
0x180043333  call    cs:__imp__o__wcsnicmp
0x180043339  test    eax, eax
0x18004333b  jnz     short loc_1800433A7
0x18004333d  cmp     cs:byte_18005E5A5, 8
0x180043344  jb      short loc_180043366
0x180043346  mov     rcx, cs:WPP_GLOBAL_Control
0x18004334d  lea     edx, [rax+11h]
0x180043350  mov     r9, rbp
0x180043353  lea     r8, WPP_142e5d19e4cc32e2432bc9bbd66f9d63_Traceguids
0x18004335a  mov     rcx, [rcx+0D8h]
0x180043361  call    WPP_SF_S
0x180043366  mov     dword ptr [rsi], 1
0x18004336c  lea     rdx, [rsi+20h]; lpiid
0x180043370  movups  xmm0, cs:MF_SENSORTRANSFORM_BUILTIN_FACTORYCLSID
0x180043377  lea     rcx, [rbp+32h]; lpsz
0x18004337b  movdqu  xmmword ptr [rsi+10h], xmm0
0x180043380  call    cs:__imp_IIDFromString
0x180043386  mov     ebx, eax
0x180043388  test    eax, eax
0x18004338a  jns     loc_1800434A8
0x180043390  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043397  jb      loc_1800434A8
0x18004339d  mov     edx, 12h
0x1800433a2  jmp     loc_18004348A
0x1800433a7  mov     ebx, 80070032h
0x1800433ac  call    ?IsSensorTransformModuleEnabled@@YA_NXZ; IsSensorTransformModuleEnabled(void)
0x1800433b1  test    al, al
0x1800433b3  jz      loc_1800434A8
0x1800433b9  mov     r8d, 18h
0x1800433bf  lea     rdx, aSensortransfor_0; "sensortransformmodule://"
0x1800433c6  mov     rcx, rbp
0x1800433c9  call    cs:__imp__o__wcsnicmp
0x1800433cf  test    eax, eax
0x1800433d1  jnz     loc_1800434A8
0x1800433d7  mov     [rsp+278h+var_248], r14
0x1800433dc  cmp     cs:byte_18005E5A5, 8
0x1800433e3  jb      short loc_180043405
0x1800433e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800433ec  lea     edx, [rax+13h]
0x1800433ef  mov     r9, rbp
0x1800433f2  lea     r8, WPP_142e5d19e4cc32e2432bc9bbd66f9d63_Traceguids
0x1800433f9  mov     rcx, [rcx+0D8h]
0x180043400  call    WPP_SF_S
0x180043405  lea     r8, [rsp+278h+var_248]; unsigned __int64 *
0x18004340a  mov     dword ptr [rsi], 2
0x180043410  mov     edx, 7FFFFFFFh; unsigned __int64
0x180043415  lea     rcx, [rbp+30h]; unsigned __int16 *
0x180043419  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004341e  mov     ebx, eax
0x180043420  test    eax, eax
0x180043422  jns     short loc_180043434
0x180043424  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004342b  jb      short loc_1800434A8
0x18004342d  mov     edx, 14h
0x180043432  jmp     short loc_18004348A
0x180043434  mov     rbx, [rsp+278h+var_248]
0x180043439  lea     rcx, ds:2[rbx*2]; cb
0x180043441  call    cs:__imp_CoTaskMemAlloc
0x180043447  mov     [rsi+20h], rax
0x18004344b  test    rax, rax
0x18004344e  jnz     short loc_180043466
0x180043450  mov     ebx, 8007000Eh
0x180043455  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004345c  jb      short loc_1800434A8
0x18004345e  lea     edx, [rax+15h]
0x180043461  jmp     loc_1800431DD
0x180043466  lea     rdx, [rbx+1]; unsigned __int64
0x18004346a  mov     rcx, rax; unsigned __int16 *
0x18004346d  lea     r8, [rbp+30h]; unsigned __int16 *
0x180043471  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180043476  mov     ebx, eax
0x180043478  test    eax, eax
0x18004347a  jns     short loc_1800434A8
0x18004347c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043483  jb      short loc_1800434A8
0x180043485  mov     edx, 16h
0x18004348a  mov     [rsp+278h+var_258], eax
0x18004348e  mov     rcx, cs:WPP_GLOBAL_Control
0x180043495  lea     r8, WPP_142e5d19e4cc32e2432bc9bbd66f9d63_Traceguids
0x18004349c  xor     r9d, r9d
0x18004349f  mov     rcx, [rcx+10h]
0x1800434a3  call    WPP_SF_qD
0x1800434a8  shr     ebx, 1Fh
0x1800434ab  xor     bl, 1
0x1800434ae  mov     al, bl
0x1800434b0  mov     rcx, [rsp+278h+var_28]
0x1800434b8  xor     rcx, rsp; StackCookie
0x1800434bb  call    __security_check_cookie
0x1800434c0  mov     rbx, [rsp+278h+arg_10]
0x1800434c8  add     rsp, 260h
0x1800434cf  pop     r14
0x1800434d1  pop     rsi
0x1800434d2  pop     rbp
0x1800434d3  retn
```
