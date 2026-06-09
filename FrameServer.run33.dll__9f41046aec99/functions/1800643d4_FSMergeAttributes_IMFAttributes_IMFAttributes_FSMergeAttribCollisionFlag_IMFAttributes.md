# FSMergeAttributes(IMFAttributes *,IMFAttributes *,FSMergeAttribCollisionFlag,IMFAttributes * *)

- ea: `0x1800643d4`
- end: `0x180064643`
- name: `?FSMergeAttributes@@YAJPEAUIMFAttributes@@0W4FSMergeAttribCollisionFlag@@PEAPEAU1@@Z`
- size: `623`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, IMFAttributes **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800852c4`
- `0x1800859d8`

## callees

- `0x180003e20`
- `0x180008cf0`
- `0x180009608`
- `0x180062430`
- `0x1800643d4`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800645dc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800645dc`
- `MFPlat!MFCreateAttributes` at `0x180064511`
- `MFPlat!MFCreateAttributes` at `0x180064511`

## pseudocode

```c
__int64 __fastcall FSMergeAttributes(__int64 a1, __int64 a2, __int64 a3, IMFAttributes **a4)
{
  HRESULT v7; // eax
  int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // rdx
  unsigned int v11; // r15d
  unsigned int v12; // esi
  __int64 v13; // rbx
  unsigned int v15; // [rsp+30h] [rbp-50h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+38h] [rbp-48h] BYREF
  int v17; // [rsp+40h] [rbp-40h] BYREF
  __int64 v18; // [rsp+48h] [rbp-38h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v20; // [rsp+60h] [rbp-20h]
  GUID v21; // [rsp+68h] [rbp-18h] BYREF

  v17 = 0;
  v15 = 0;
  ppMFAttributes = 0;
  v18 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a4 )
      {
        *a4 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 240LL))(a1, &v17);
        v8 = v7;
        if ( v7 < 0 )
        {
          if ( g_wppLevels )
          {
            v9 = 13;
            goto LABEL_4;
          }
          goto LABEL_33;
        }
        v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 240LL))(a2, &v15);
        v8 = v7;
        if ( v7 < 0 )
        {
          if ( g_wppLevels )
          {
            v9 = 14;
            goto LABEL_4;
          }
          goto LABEL_33;
        }
        v7 = MFCreateAttributes(&ppMFAttributes, v17 + v15);
        v8 = v7;
        if ( v7 < 0 )
        {
          if ( g_wppLevels )
          {
            v9 = 15;
            goto LABEL_4;
          }
          goto LABEL_33;
        }
        v7 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)a1 + 256LL))(a1, ppMFAttributes);
        v8 = v7;
        if ( v7 < 0 )
        {
          if ( g_wppLevels )
          {
            v9 = 16;
            goto LABEL_4;
          }
          goto LABEL_33;
        }
        ComSmartPtr<FSMuxMediaType>::operator=(&v18, a2);
        v11 = v15;
        v12 = 0;
        v13 = v18;
        while ( 1 )
        {
          if ( v12 >= v11 )
          {
            *a4 = ppMFAttributes;
            ppMFAttributes = 0;
            goto LABEL_33;
          }
          v20 = 0;
          v21 = GUID_00000000_0000_0000_0000_000000000000;
          *(_OWORD *)pvar = 0;
          if ( (*(int (__fastcall **)(__int64, _QWORD, GUID *, PROPVARIANT *))(*(_QWORD *)v13 + 248LL))(
                 v13,
                 v12,
                 &v21,
                 pvar) >= 0 )
          {
            v8 = ((__int64 (__fastcall *)(IMFAttributes *, GUID *, PROPVARIANT *))ppMFAttributes->lpVtbl->SetItem)(
                   ppMFAttributes,
                   &v21,
                   pvar);
            PropVariantClear(pvar);
            if ( v8 < 0 )
              break;
          }
          ++v12;
        }
        if ( !g_wppLevels )
          goto LABEL_33;
        v10 = 18;
      }
      else
      {
        v8 = -2147467261;
        if ( !g_wppLevels )
          goto LABEL_33;
        v10 = 12;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_c1837c1b3daa34ac5f75181a09a83354_Traceguids, 0, v8);
      goto LABEL_33;
    }
    v7 = -2147024809;
    v8 = -2147024809;
    if ( g_wppLevels )
    {
      v9 = 11;
      goto LABEL_4;
    }
  }
  else
  {
    v7 = -2147024809;
    v8 = -2147024809;
    if ( g_wppLevels )
    {
      v9 = 10;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_c1837c1b3daa34ac5f75181a09a83354_Traceguids, 0, v7);
    }
  }
LABEL_33:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v18);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800643d4  mov     [rsp-28h+arg_10], rbx
0x1800643d9  push    rbp
0x1800643da  push    rsi
0x1800643db  push    rdi
0x1800643dc  push    r14
0x1800643de  push    r15
0x1800643e0  mov     rbp, rsp
0x1800643e3  sub     rsp, 80h
0x1800643ea  mov     rax, cs:__security_cookie
0x1800643f1  xor     rax, rsp
0x1800643f4  mov     [rbp+var_8], rax
0x1800643f8  mov     [rbp+var_40], 0
0x1800643ff  mov     r14, r9
0x180064402  mov     [rbp+var_50], 0
0x180064409  mov     rsi, rdx
0x18006440c  mov     [rbp+ppMFAttributes], 0
0x180064414  mov     rbx, rcx
0x180064417  mov     [rbp+var_38], 0
0x18006441f  test    rcx, rcx
0x180064422  jnz     short loc_18006445E
0x180064424  mov     eax, 80070057h
0x180064429  mov     edi, eax
0x18006442b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180064432  jb      loc_18006460C
0x180064438  lea     edx, [rcx+0Ah]
0x18006443b  mov     [rsp+80h+var_60], eax
0x18006443f  mov     rcx, cs:WPP_GLOBAL_Control
0x180064446  lea     r8, WPP_c1837c1b3daa34ac5f75181a09a83354_Traceguids
0x18006444d  xor     r9d, r9d
0x180064450  mov     rcx, [rcx+10h]
0x180064454  call    WPP_SF_qD
0x180064459  jmp     loc_18006460C
0x18006445e  test    rsi, rsi
0x180064461  jnz     short loc_18006447C
0x180064463  mov     eax, 80070057h
0x180064468  mov     edi, eax
0x18006446a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180064471  jb      loc_18006460C
0x180064477  lea     edx, [rsi+0Bh]
0x18006447a  jmp     short loc_18006443B
0x18006447c  test    r14, r14
0x18006447f  jnz     short loc_18006449D
0x180064481  mov     edi, 80004003h
0x180064486  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006448d  jb      loc_18006460C
0x180064493  lea     edx, [r14+0Ch]
0x180064497  mov     [rsp+80h+var_60], edi
0x18006449b  jmp     short loc_18006443F
0x18006449d  mov     qword ptr [r9], 0
0x1800644a4  lea     rdx, [rbp+var_40]
0x1800644a8  mov     rax, [rcx]
0x1800644ab  mov     rax, [rax+0F0h]
0x1800644b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644b7  mov     edi, eax
0x1800644b9  test    eax, eax
0x1800644bb  jns     short loc_1800644D4
0x1800644bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800644c4  jb      loc_18006460C
0x1800644ca  mov     edx, 0Dh
0x1800644cf  jmp     loc_18006443B
0x1800644d4  mov     rax, [rsi]
0x1800644d7  lea     rdx, [rbp+var_50]
0x1800644db  mov     rcx, rsi
0x1800644de  mov     rax, [rax+0F0h]
0x1800644e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644ea  mov     edi, eax
0x1800644ec  test    eax, eax
0x1800644ee  jns     short loc_180064507
0x1800644f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800644f7  jb      loc_18006460C
0x1800644fd  mov     edx, 0Eh
0x180064502  jmp     loc_18006443B
0x180064507  mov     edx, [rbp+var_50]
0x18006450a  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18006450e  add     edx, [rbp+var_40]; cInitialSize
0x180064511  call    cs:__imp_MFCreateAttributes
0x180064517  mov     edi, eax
0x180064519  test    eax, eax
0x18006451b  jns     short loc_180064534
0x18006451d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180064524  jb      loc_18006460C
0x18006452a  mov     edx, 0Fh
0x18006452f  jmp     loc_18006443B
0x180064534  mov     rax, [rbx]
0x180064537  mov     rcx, rbx
0x18006453a  mov     rdx, [rbp+ppMFAttributes]
0x18006453e  mov     rax, [rax+100h]
0x180064545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006454a  mov     edi, eax
0x18006454c  test    eax, eax
0x18006454e  jns     short loc_180064567
0x180064550  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180064557  jb      loc_18006460C
0x18006455d  mov     edx, 10h
0x180064562  jmp     loc_18006443B
0x180064567  mov     rdx, rsi
0x18006456a  lea     rcx, [rbp+var_38]
0x18006456e  call    ??4?$ComSmartPtr@VFSMuxMediaType@@@@QEAAPEAVFSMuxMediaType@@PEAV1@@Z; ComSmartPtr<FSMuxMediaType>::operator=(FSMuxMediaType *)
0x180064573  mov     r15d, [rbp+var_50]
0x180064577  xor     esi, esi
0x180064579  mov     rbx, [rbp+var_38]
0x18006457d  cmp     esi, r15d
0x180064580  jnb     short loc_1800645FD
0x180064582  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180064589  lea     r9, [rbp+pvar]
0x18006458d  xor     eax, eax
0x18006458f  lea     r8, [rbp+var_18]
0x180064593  mov     [rbp+var_20], rax
0x180064597  xorps   xmm1, xmm1
0x18006459a  movdqu  [rbp+var_18], xmm0
0x18006459f  mov     edx, esi
0x1800645a1  mov     rcx, rbx
0x1800645a4  movups  xmmword ptr [rbp+pvar], xmm1
0x1800645a8  mov     rax, [rbx]
0x1800645ab  mov     rax, [rax+0F8h]
0x1800645b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800645b7  test    eax, eax
0x1800645b9  js      short loc_1800645E6
0x1800645bb  mov     rcx, [rbp+ppMFAttributes]
0x1800645bf  lea     r8, [rbp+pvar]
0x1800645c3  lea     rdx, [rbp+var_18]
0x1800645c7  mov     rax, [rcx]
0x1800645ca  mov     rax, [rax+90h]
0x1800645d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800645d6  lea     rcx, [rbp+pvar]; pvar
0x1800645da  mov     edi, eax
0x1800645dc  call    cs:__imp_PropVariantClear
0x1800645e2  test    edi, edi
0x1800645e4  js      short loc_1800645EA
0x1800645e6  inc     esi
0x1800645e8  jmp     short loc_18006457D
0x1800645ea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800645f1  jb      short loc_18006460C
0x1800645f3  mov     edx, 12h
0x1800645f8  jmp     loc_180064497
0x1800645fd  mov     rax, [rbp+ppMFAttributes]
0x180064601  mov     [r14], rax
0x180064604  mov     [rbp+ppMFAttributes], 0
0x18006460c  lea     rcx, [rbp+var_38]; void *
0x180064610  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180064615  lea     rcx, [rbp+ppMFAttributes]; void *
0x180064619  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18006461e  mov     eax, edi
0x180064620  mov     rcx, [rbp+var_8]
0x180064624  xor     rcx, rsp; StackCookie
0x180064627  call    __security_check_cookie
0x18006462c  mov     rbx, [rsp+80h+arg_10]
0x180064634  add     rsp, 80h
0x18006463b  pop     r15
0x18006463d  pop     r14
0x18006463f  pop     rdi
0x180064640  pop     rsi
0x180064641  pop     rbp
0x180064642  retn
```
