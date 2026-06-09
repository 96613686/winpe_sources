# RfbShellFolderBase::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x180015e20`
- end: `0x18001611e`
- name: `?ParseDisplayName@RfbShellFolderBase@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `766`
- prototype: `__int64 __fastcall(RfbShellFolderBase *this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008d90`

## callees

- `0x180002030`
- `0x180002db8`
- `0x1800054a4`
- `0x18000591c`
- `0x180015e20`
- `0x180019010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180015e8e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180015e8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016066`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800160d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016066`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800160d7`
- `SHELL32!__imp_ILClone` at `0x180016090`
- `SHELL32!__imp_ILClone` at `0x180016090`
- `SHELL32!__imp_ILCombine` at `0x180016037`
- `SHELL32!__imp_ILCombine` at `0x180016037`

## pseudocode

```c
__int64 __fastcall RfbShellFolderBase::ParseDisplayName(
        RfbShellFolderBase *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  int v8; // esi
  wchar_t *v9; // rax
  __int64 v10; // r8
  wchar_t *v11; // r15
  unsigned __int64 v12; // rdx
  __int64 v13; // rbx
  RfbShellFolderBase *v14; // rdi
  ITEMIDLIST *v15; // rcx
  __int64 v16; // rax
  ITEMIDLIST *v17; // rcx
  ITEMIDLIST *v18; // rcx
  RfbShellFolderBase *v19; // rcx
  __int64 result; // rax
  int v21; // [rsp+40h] [rbp-A8h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+48h] [rbp-A0h] BYREF
  RfbShellFolderBase *v23; // [rsp+50h] [rbp-98h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+58h] [rbp-90h] BYREF
  LPCITEMIDLIST *p_pidl2; // [rsp+60h] [rbp-88h]
  const ITEMIDLIST *v26; // [rsp+68h] [rbp-80h] BYREF
  char v27; // [rsp+70h] [rbp-78h]
  struct IBindCtx *v28; // [rsp+78h] [rbp-70h]
  HWND v29; // [rsp+80h] [rbp-68h]
  __int128 v30; // [rsp+88h] [rbp-60h] BYREF
  unsigned __int64 v31; // [rsp+98h] [rbp-50h]
  __int64 v32; // [rsp+A0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  try
  {
    v28 = a3;
    v29 = a2;
    v23 = this;
    if ( !a4 || !a6 )
      return 2147942487LL;
    v8 = 0;
    v9 = wcschr(a4, 0x5Cu);
    v11 = v9;
    v30 = 0;
    v31 = 0;
    v32 = 7;
    LOWORD(v30) = 0;
    if ( v9 )
    {
      v12 = v9 - a4;
      if ( v12 > 7 )
      {
LABEL_11:
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)&v30,
          v12,
          v10,
          a4);
        goto LABEL_12;
      }
    }
    else
    {
      v12 = -1;
      do
        ++v12;
      while ( a4[v12] );
      if ( v12 > 7 )
        goto LABEL_11;
    }
    v31 = v12;
    v13 = 2 * v12;
    memmove_0(&v30, a4, 2 * v12);
    *(_WORD *)((char *)&v30 + v13) = 0;
LABEL_12:
    pidl1 = 0;
    v14 = v23;
    (*(void (__fastcall **)(_QWORD, __int128 *, LPCITEMIDLIST *))(**((_QWORD **)v23 + 9) + 16LL))(
      *((_QWORD *)v23 + 9),
      &v30,
      &pidl1);
    v15 = (ITEMIDLIST *)pidl1;
    if ( pidl1 )
    {
      if ( v11 && v11[1] )
      {
        v23 = 0;
        v8 = (*(__int64 (__fastcall **)(RfbShellFolderBase *, LPCITEMIDLIST, _QWORD, GUID *, RfbShellFolderBase **))(*(_QWORD *)v14 + 40LL))(
               v14,
               pidl1,
               0,
               &GUID_000214e6_0000_0000_c000_000000000046,
               &v23);
        if ( v8 >= 0 )
        {
          v21 = 0;
          pidl2 = 0;
          v16 = *(_QWORD *)v23;
          p_pidl2 = &pidl2;
          v26 = 0;
          v27 = 1;
          v8 = (*(__int64 (__fastcall **)(RfbShellFolderBase *, HWND, struct IBindCtx *, wchar_t *, int *, const ITEMIDLIST **, unsigned int *))(v16 + 24))(
                 v23,
                 v29,
                 v28,
                 v11 + 1,
                 &v21,
                 &v26,
                 a7);
          if ( v27 )
          {
            v17 = (ITEMIDLIST *)*p_pidl2;
            *p_pidl2 = v26;
            if ( v17 )
              CoTaskMemFree(v17);
          }
          if ( v8 >= 0 )
          {
            *a6 = (struct _ITEMIDLIST_RELATIVE *)ILCombine(pidl1, pidl2);
            if ( a5 )
              *a5 = v31 + v21 + 1;
          }
          v18 = (ITEMIDLIST *)pidl2;
          pidl2 = 0;
          if ( v18 )
            CoTaskMemFree(v18);
        }
        v19 = v23;
        if ( v23 )
        {
          v23 = 0;
          (*(void (__fastcall **)(RfbShellFolderBase *))(*(_QWORD *)v19 + 16LL))(v19);
        }
        v15 = (ITEMIDLIST *)pidl1;
      }
      else
      {
        *a6 = (struct _ITEMIDLIST_RELATIVE *)ILClone(pidl1);
        if ( a7 && *a7 )
          *a7 = (*(__int64 (__fastcall **)(__int64, LPCITEMIDLIST))(*((_QWORD *)v14 - 1) + 80LL))(
                  (__int64)v14 - 8,
                  pidl1);
        v15 = (ITEMIDLIST *)pidl1;
      }
    }
    else
    {
      v8 = -2147024894;
    }
    pidl1 = 0;
    if ( v15 )
      CoTaskMemFree(v15);
    std::wstring::~wstring((char **)&v30);
    result = (unsigned int)v8;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x168,
                           (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
                           (const char *)a4);
  }
  return result;
}

```

## disassembly

```asm
0x180015e20  push    rbx
0x180015e22  push    rsi
0x180015e23  push    rdi
0x180015e24  push    r12
0x180015e26  push    r13
0x180015e28  push    r14
0x180015e2a  push    r15
0x180015e2c  sub     rsp, 0B0h
0x180015e33  mov     rax, cs:__security_cookie
0x180015e3a  xor     rax, rsp
0x180015e3d  mov     [rsp+0E8h+var_40], rax
0x180015e45  mov     rdi, r9
0x180015e48  mov     [rsp+0E8h+var_70], r8
0x180015e4d  mov     [rsp+0E8h+var_68], rdx
0x180015e55  mov     [rsp+0E8h+var_98], rcx
0x180015e5a  mov     r13, [rsp+0E8h+arg_20]
0x180015e62  mov     r12, [rsp+0E8h+arg_28]
0x180015e6a  mov     r14, [rsp+0E8h+arg_30]
0x180015e72  xor     ebx, ebx
0x180015e74  test    r9, r9
0x180015e77  jz      loc_1800160F6
0x180015e7d  test    r12, r12
0x180015e80  jz      loc_1800160F6
0x180015e86  mov     esi, ebx
0x180015e88  lea     edx, [rbx+5Ch]; Ch
0x180015e8b  mov     rcx, r9; Str
0x180015e8e  call    cs:__imp_wcschr
0x180015e94  mov     r15, rax
0x180015e97  xorps   xmm0, xmm0
0x180015e9a  movups  [rsp+0E8h+var_60], xmm0
0x180015ea2  mov     [rsp+0E8h+var_50], rbx
0x180015eaa  mov     [rsp+0E8h+var_48], 7
0x180015eb6  mov     word ptr [rsp+0E8h+var_60], bx
0x180015ebe  test    rax, rax
0x180015ec1  jz      short loc_180015EE4
0x180015ec3  mov     rdx, rax
0x180015ec6  sub     rdx, rdi
0x180015ec9  sar     rdx, 1
0x180015ecc  lea     rcx, [rsp+0E8h+var_60]
0x180015ed4  cmp     rdx, 7
0x180015ed8  jbe     short loc_180015EFF
0x180015eda  mov     r9, rdi
0x180015edd  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015ee2  jmp     short loc_180015F2C
0x180015ee4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015ee8  inc     rdx
0x180015eeb  cmp     [rdi+rdx*2], bx
0x180015eef  jnz     short loc_180015EE8
0x180015ef1  lea     rcx, [rsp+0E8h+var_60]; void *
0x180015ef9  cmp     rdx, 7
0x180015efd  ja      short loc_180015F24
0x180015eff  mov     [rsp+0E8h+var_50], rdx
0x180015f07  lea     rbx, [rdx+rdx]
0x180015f0b  mov     r8, rbx; Size
0x180015f0e  mov     rdx, rdi; Src
0x180015f11  call    memmove_0
0x180015f16  xor     ecx, ecx
0x180015f18  mov     word ptr [rsp+rbx+0E8h+var_60], cx
0x180015f20  xor     ebx, ebx
0x180015f22  jmp     short loc_180015F2C
0x180015f24  mov     r9, rdi
0x180015f27  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015f2c  mov     [rsp+0E8h+pidl1], rbx
0x180015f31  mov     rdi, [rsp+0E8h+var_98]
0x180015f36  mov     rcx, [rdi+48h]
0x180015f3a  mov     rax, [rcx]
0x180015f3d  lea     r8, [rsp+0E8h+pidl1]
0x180015f42  lea     rdx, [rsp+0E8h+var_60]
0x180015f4a  mov     rax, [rax+10h]
0x180015f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f53  mov     rcx, [rsp+0E8h+pidl1]; pv
0x180015f58  xor     eax, eax
0x180015f5a  test    rcx, rcx
0x180015f5d  jz      loc_1800160C6
0x180015f63  test    r15, r15
0x180015f66  jz      loc_180016090
0x180015f6c  cmp     [r15+2], ax
0x180015f71  jz      loc_180016090
0x180015f77  xor     ebx, ebx
0x180015f79  mov     [rsp+0E8h+var_98], rbx
0x180015f7e  mov     rax, [rdi]
0x180015f81  lea     rdx, [rsp+0E8h+var_98]
0x180015f86  mov     [rsp+0E8h+var_C8], rdx
0x180015f8b  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x180015f92  xor     r8d, r8d
0x180015f95  mov     rdx, rcx
0x180015f98  mov     rcx, rdi
0x180015f9b  mov     rax, [rax+28h]
0x180015f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fa4  mov     esi, eax
0x180015fa6  test    eax, eax
0x180015fa8  js      loc_18001606D
0x180015fae  mov     [rsp+0E8h+var_A8], ebx
0x180015fb2  mov     [rsp+0E8h+pidl2], rbx
0x180015fb7  mov     rcx, [rsp+0E8h+var_98]
0x180015fbc  mov     rax, [rcx]
0x180015fbf  lea     rdx, [rsp+0E8h+pidl2]
0x180015fc4  mov     [rsp+0E8h+var_88], rdx
0x180015fc9  mov     [rsp+0E8h+var_80], rbx
0x180015fce  mov     [rsp+0E8h+var_78], 1
0x180015fd3  mov     [rsp+0E8h+var_B8], r14
0x180015fd8  lea     rdx, [rsp+0E8h+var_80]
0x180015fdd  mov     [rsp+0E8h+var_C0], rdx
0x180015fe2  lea     rdx, [rsp+0E8h+var_A8]
0x180015fe7  mov     [rsp+0E8h+var_C8], rdx
0x180015fec  lea     r9, [r15+2]
0x180015ff0  mov     r8, [rsp+0E8h+var_70]
0x180015ff5  mov     rdx, [rsp+0E8h+var_68]
0x180015ffd  mov     rax, [rax+18h]
0x180016001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016006  mov     esi, eax
0x180016008  cmp     [rsp+0E8h+var_78], bl
0x18001600c  jz      short loc_180016029
0x18001600e  mov     rdx, [rsp+0E8h+var_88]
0x180016013  mov     rcx, [rdx]; pv
0x180016016  mov     rax, [rsp+0E8h+var_80]
0x18001601b  mov     [rdx], rax
0x18001601e  test    rcx, rcx
0x180016021  jz      short loc_180016029
0x180016023  call    cs:__imp_CoTaskMemFree
0x180016029  test    esi, esi
0x18001602b  js      short loc_180016057
0x18001602d  mov     rdx, [rsp+0E8h+pidl2]; pidl2
0x180016032  mov     rcx, [rsp+0E8h+pidl1]; pidl1
0x180016037  call    cs:__imp_ILCombine
0x18001603d  mov     [r12], rax
0x180016041  test    r13, r13
0x180016044  jz      short loc_180016057
0x180016046  mov     ecx, [rsp+0E8h+var_A8]
0x18001604a  inc     ecx
0x18001604c  add     ecx, dword ptr [rsp+0E8h+var_50]
0x180016053  mov     [r13+0], ecx
0x180016057  mov     rcx, [rsp+0E8h+pidl2]; pv
0x18001605c  mov     [rsp+0E8h+pidl2], rbx
0x180016061  test    rcx, rcx
0x180016064  jz      short loc_18001606D
0x180016066  call    cs:__imp_CoTaskMemFree
0x18001606c  nop
0x18001606d  mov     rcx, [rsp+0E8h+var_98]
0x180016072  test    rcx, rcx
0x180016075  jz      short loc_180016089
0x180016077  mov     [rsp+0E8h+var_98], rbx
0x18001607c  mov     rax, [rcx]
0x18001607f  mov     rax, [rax+10h]
0x180016083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016088  nop
0x180016089  mov     rcx, [rsp+0E8h+pidl1]
0x18001608e  jmp     short loc_1800160CD
0x180016090  call    cs:__imp_ILClone
0x180016096  mov     [r12], rax
0x18001609a  xor     ecx, ecx
0x18001609c  test    r14, r14
0x18001609f  jz      short loc_1800160BF
0x1800160a1  cmp     [r14], ecx
0x1800160a4  jz      short loc_1800160BF
0x1800160a6  mov     rax, [rdi-8]
0x1800160aa  mov     rdx, [rsp+0E8h+pidl1]
0x1800160af  lea     rcx, [rdi-8]
0x1800160b3  mov     rax, [rax+50h]
0x1800160b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160bc  mov     [r14], eax
0x1800160bf  mov     rcx, [rsp+0E8h+pidl1]
0x1800160c4  jmp     short loc_1800160CB
0x1800160c6  mov     esi, 80070002h
0x1800160cb  xor     ebx, ebx
0x1800160cd  mov     [rsp+0E8h+pidl1], rbx
0x1800160d2  test    rcx, rcx
0x1800160d5  jz      short loc_1800160DE
0x1800160d7  call    cs:__imp_CoTaskMemFree
0x1800160dd  nop
0x1800160de  lea     rcx, [rsp+0E8h+var_60]
0x1800160e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800160eb  nop
0x1800160ec  mov     eax, esi
0x1800160ee  jmp     short loc_1800160FB
0x1800160f0  mov     eax, [rsp+0E8h+var_A8]
0x1800160f4  jmp     short loc_1800160FB
0x1800160f6  mov     eax, 80070057h
0x1800160fb  mov     rcx, [rsp+0E8h+var_40]
0x180016103  xor     rcx, rsp; StackCookie
0x180016106  call    __security_check_cookie
0x18001610b  add     rsp, 0B0h
0x180016112  pop     r15
0x180016114  pop     r14
0x180016116  pop     r13
0x180016118  pop     r12
0x18001611a  pop     rdi
0x18001611b  pop     rsi
0x18001611c  pop     rbx
0x18001611d  retn
```
