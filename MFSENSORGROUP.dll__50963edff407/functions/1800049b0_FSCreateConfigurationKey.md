# FSCreateConfigurationKey

- ea: `0x1800049b0`
- end: `0x180004dba`
- name: `FSCreateConfigurationKey`
- size: `1034`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config`

## callers

- `0x18003c55c`
- `0x180070948`
- `0x180071e68`

## callees

- `0x1800049b0`
- `0x180005b90`
- `0x180005fa0`
- `0x180005ff0`
- `0x180010218`
- `0x180016328`
- `0x18001635c`
- `0x180035a1c`
- `0x180044b28`
- `0x180045300`
- `0x180045900`
- `0x18006eb24`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b77`

## pseudocode

```c
__int64 __fastcall FSCreateConfigurationKey(
        LPCWSTR pszDeviceInterface,
        __int64 a2,
        const unsigned __int16 *a3,
        struct IFSConfigurationKey **a4)
{
  unsigned __int16 *v6; // rbx
  unsigned __int16 *v7; // r14
  int Key; // eax
  unsigned int v9; // edi
  size_t v10; // rdi
  unsigned __int16 *v11; // rax
  __int64 v12; // rdx
  const unsigned __int16 *v13; // rax
  const unsigned __int16 *v14; // r13
  __int64 v15; // rcx
  unsigned int v16; // eax
  _WORD *v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // edi
  __int64 v21; // rdx
  void **unique; // rax
  void *v23; // rcx
  int v24; // [rsp+20h] [rbp-40h]
  unsigned int v25; // [rsp+40h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-18h] BYREF
  void *Block; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-8h] BYREF
  unsigned int v29; // [rsp+A8h] [rbp+48h] BYREF
  int v30; // [rsp+ACh] [rbp+4Ch]
  struct IFSConfigurationKey **v31; // [rsp+B8h] [rbp+58h]

  v31 = a4;
  v30 = HIDWORD(a2);
  v25 = 0;
  v28 = 0;
  v6 = 0;
  v29 = 0;
  v7 = 0;
  hMem = 0;
  if ( !a4 )
  {
    v9 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_25;
    v21 = 40;
    goto LABEL_33;
  }
  *a4 = 0;
  if ( !pszDeviceInterface )
  {
    v9 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_25;
    v21 = 41;
    v24 = -2147024809;
    goto LABEL_42;
  }
  Key = FSGetUniqueSymbolicName(pszDeviceInterface, 0, 0, &v25);
  v9 = Key;
  if ( Key < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_23;
    v21 = 43;
    goto LABEL_41;
  }
  v10 = 2LL * v25;
  if ( !is_mul_ok(v25, 2u) )
    v10 = -1;
  v11 = (unsigned __int16 *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v11;
  if ( !v11 )
  {
    v9 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
        0,
        -2147024882);
    v6 = 0;
    goto LABEL_23;
  }
  memset_0(v11, 0, v10);
  Key = FSGetUniqueSymbolicName(pszDeviceInterface, v6, v25, &v25);
  v9 = Key;
  if ( Key < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_23;
    v21 = 45;
    goto LABEL_41;
  }
  if ( !a3 )
  {
    Key = FSGetCurrentProcessConfigurationInfo(0, 0, &v29);
    v9 = Key;
    if ( Key >= 0 )
    {
      unique = (void **)wil::make_unique_nothrow<unsigned short [0]>(&Block, v29);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v28, unique);
      v23 = Block;
      Block = 0;
      if ( v23 )
        operator delete(v23);
      v7 = v28;
      if ( !v28 )
      {
        Key = -2147024882;
        v9 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_23;
        v21 = (unsigned int)((_DWORD)v28 + 47);
        goto LABEL_41;
      }
      Key = FSGetCurrentProcessConfigurationInfo(v28, v29, &v29);
      v9 = Key;
      if ( Key >= 0 )
      {
        v16 = v29;
        a3 = v7;
        v14 = v6;
        goto LABEL_14;
      }
      if ( !g_wppLevels )
        goto LABEL_23;
      v21 = 48;
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_23;
      v21 = 46;
    }
LABEL_41:
    v24 = Key;
    goto LABEL_42;
  }
  v12 = 0x7FFFFFFF;
  v13 = a3;
  v14 = v6;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  v15 = 0x7FFFFFFF - v12;
  v9 = v12 == 0 ? 0x80070057 : 0;
  if ( !v12 )
  {
    if ( g_wppLevels )
    {
      v21 = 49;
      v24 = v9;
      goto LABEL_42;
    }
    goto LABEL_23;
  }
  v16 = v12 != 0 ? 0x7FFFFFFF - v12 + 1 : 1;
LABEL_14:
  v29 = v16;
  Key = FSGetUserSidString(v15, (LPWSTR *)&hMem);
  v9 = Key;
  if ( Key >= 0 )
  {
    v17 = hMem;
    if ( hMem )
    {
      v18 = 0x7FFFFFFF;
      do
      {
        if ( !*v17 )
          break;
        ++v17;
        --v18;
      }
      while ( v18 );
      v9 = v18 == 0 ? 0x80070057 : 0;
      if ( v18 )
      {
        v19 = ((0x7FFFFFFF - v18) & ((unsigned __int128)-(__int128)(unsigned __int64)v18 >> 64)) + 1;
        if ( (unsigned __int8)byte_18008D62D >= 8u )
          WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v14, (__int64)a3);
        Key = FSConfigurationKey::CreateKey(v14, v25, a3, v29, (const unsigned __int16 *)hMem, v19, v31);
        v9 = Key;
        if ( Key >= 0 || !g_wppLevels )
          goto LABEL_23;
        v21 = 57;
        goto LABEL_41;
      }
    }
    else
    {
      v9 = -2147024809;
    }
    if ( !g_wppLevels )
      goto LABEL_23;
    v21 = 55;
LABEL_33:
    v24 = v9;
LABEL_42:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v24);
    goto LABEL_23;
  }
  if ( g_wppLevels )
  {
    v21 = 54;
    goto LABEL_41;
  }
LABEL_23:
  if ( hMem )
    LocalFree(hMem);
LABEL_25:
  if ( v7 )
    operator delete(v7);
  if ( v6 )
    operator delete(v6);
  return v9;
}

```

## disassembly

```asm
0x1800049b0  mov     [rsp-38h+arg_0], rbx
0x1800049b5  mov     [rsp-38h+arg_18], r9
0x1800049ba  mov     qword ptr [rsp-38h+arg_8], rdx
0x1800049bf  push    rbp
0x1800049c0  push    rsi
0x1800049c1  push    rdi
0x1800049c2  push    r12
0x1800049c4  push    r13
0x1800049c6  push    r14
0x1800049c8  push    r15
0x1800049ca  mov     rbp, rsp
0x1800049cd  sub     rsp, 60h
0x1800049d1  xor     r13d, r13d
0x1800049d4  mov     r12, r8
0x1800049d7  mov     [rbp+var_20], r13d
0x1800049db  mov     rsi, rcx
0x1800049de  mov     [rbp+var_8], r13
0x1800049e2  mov     ebx, r13d
0x1800049e5  mov     [rbp+arg_8], r13d
0x1800049e9  mov     r14d, r13d
0x1800049ec  mov     [rbp+hMem], r13
0x1800049f0  test    r9, r9
0x1800049f3  jz      loc_180004C3C
0x1800049f9  mov     [r9], r13
0x1800049fc  test    rcx, rcx
0x1800049ff  jz      loc_180004C88
0x180004a05  lea     r9, [rbp+var_20]; unsigned int *
0x180004a09  xor     r8d, r8d; unsigned int
0x180004a0c  xor     edx, edx; unsigned __int16 *
0x180004a0e  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x180004a13  mov     edi, eax
0x180004a15  test    eax, eax
0x180004a17  js      loc_180004CA7
0x180004a1d  mov     ecx, [rbp+var_20]
0x180004a20  lea     eax, [r13+2]
0x180004a24  mul     rcx
0x180004a27  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004a2e  mov     rdi, rax
0x180004a31  lea     rax, [r13-1]
0x180004a35  cmovb   rdi, rax
0x180004a39  mov     rcx, rdi; unsigned __int64
0x180004a3c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004a41  mov     rbx, rax
0x180004a44  test    rax, rax
0x180004a47  jz      loc_180004D72
0x180004a4d  mov     r8, rdi; Size
0x180004a50  xor     edx, edx; Val
0x180004a52  mov     rcx, rax; void *
0x180004a55  call    memset_0
0x180004a5a  mov     r8d, [rbp+var_20]; unsigned int
0x180004a5e  lea     r9, [rbp+var_20]; unsigned int *
0x180004a62  mov     rdx, rbx; unsigned __int16 *
0x180004a65  mov     rcx, rsi; pszDeviceInterface
0x180004a68  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x180004a6d  mov     edi, eax
0x180004a6f  test    eax, eax
0x180004a71  js      loc_180004CB6
0x180004a77  mov     esi, 80070057h
0x180004a7c  mov     r15d, 7FFFFFFFh
0x180004a82  test    r12, r12
0x180004a85  jz      loc_180004CCA
0x180004a8b  mov     edx, r15d
0x180004a8e  mov     rax, r12
0x180004a91  mov     r13, rbx
0x180004a94  xor     r9d, r9d
0x180004a97  cmp     [rax], r9w
0x180004a9b  jz      short loc_180004AA7
0x180004a9d  add     rax, 2
0x180004aa1  sub     rdx, 1
0x180004aa5  jnz     short loc_180004A97
0x180004aa7  mov     rax, rdx
0x180004aaa  mov     rcx, r15
0x180004aad  neg     rax
0x180004ab0  mov     rax, rdx
0x180004ab3  sbb     edi, edi
0x180004ab5  sub     rcx, rdx
0x180004ab8  not     edi
0x180004aba  and     edi, esi
0x180004abc  neg     rax
0x180004abf  sbb     r8, r8
0x180004ac2  and     r8, rcx
0x180004ac5  test    rdx, rdx
0x180004ac8  jz      loc_180004D32
0x180004ace  lea     eax, [r8+1]
0x180004ad2  lea     rdx, [rbp+hMem]
0x180004ad6  mov     [rbp+arg_8], eax
0x180004ad9  call    ?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180004ade  xor     r8d, r8d
0x180004ae1  mov     edi, eax
0x180004ae3  test    eax, eax
0x180004ae5  js      loc_180004D44
0x180004aeb  mov     rax, [rbp+hMem]
0x180004aef  test    rax, rax
0x180004af2  jz      loc_180004BD5
0x180004af8  mov     rcx, r15
0x180004afb  cmp     [rax], r8w
0x180004aff  jz      short loc_180004B0B
0x180004b01  add     rax, 2
0x180004b05  sub     rcx, 1
0x180004b09  jnz     short loc_180004AFB
0x180004b0b  mov     rax, rcx
0x180004b0e  neg     rax
0x180004b11  mov     rax, rcx
0x180004b14  sbb     edi, edi
0x180004b16  sub     r15, rcx
0x180004b19  not     edi
0x180004b1b  and     edi, esi
0x180004b1d  neg     rax
0x180004b20  sbb     rdx, rdx
0x180004b23  and     rdx, r15
0x180004b26  test    rcx, rcx
0x180004b29  jz      loc_180004BD7
0x180004b2f  lea     rdi, [rdx+1]
0x180004b33  cmp     cs:byte_18008D62D, 8
0x180004b3a  jnb     short loc_180004BAF
0x180004b3c  mov     rcx, [rbp+arg_18]
0x180004b40  mov     r8, r12; unsigned __int16 *
0x180004b43  mov     rax, [rbp+hMem]
0x180004b47  mov     r9d, [rbp+arg_8]; unsigned int
0x180004b4b  mov     edx, [rbp+var_20]; unsigned int
0x180004b4e  mov     [rsp+60h+var_30], rcx; struct IFSConfigurationKey **
0x180004b53  mov     rcx, r13; unsigned __int16 *
0x180004b56  mov     [rsp+60h+var_38], edi; unsigned int
0x180004b5a  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x180004b5f  call    ?CreateKey@FSConfigurationKey@@SAJPEBGK0K0KPEAPEAUIFSConfigurationKey@@@Z; FSConfigurationKey::CreateKey(ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,IFSConfigurationKey * *)
0x180004b64  mov     edi, eax
0x180004b66  test    eax, eax
0x180004b68  js      loc_180004D5B
0x180004b6e  mov     rcx, [rbp+hMem]; hMem
0x180004b72  test    rcx, rcx
0x180004b75  jz      short loc_180004B7D
0x180004b77  call    cs:__imp_LocalFree
0x180004b7d  test    r14, r14
0x180004b80  jnz     short loc_180004BA5
0x180004b82  test    rbx, rbx
0x180004b85  jnz     loc_180004DAD
0x180004b8b  mov     rbx, [rsp+60h+arg_0]
0x180004b93  mov     eax, edi
0x180004b95  add     rsp, 60h
0x180004b99  pop     r15
0x180004b9b  pop     r14
0x180004b9d  pop     r13
0x180004b9f  pop     r12
0x180004ba1  pop     rdi
0x180004ba2  pop     rsi
0x180004ba3  pop     rbp
0x180004ba4  retn
0x180004ba5  mov     rcx, r14; Block
0x180004ba8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004bad  jmp     short loc_180004B82
0x180004baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bb6  mov     r9, [rbp+hMem]
0x180004bba  mov     qword ptr [rsp+60h+var_38], r12; __int64
0x180004bbf  mov     [rsp+60h+var_40], r13; __int64
0x180004bc4  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180004bcb  call    WPP_SF_SSS
0x180004bd0  jmp     loc_180004B3C
0x180004bd5  mov     edi, esi
0x180004bd7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004bde  jb      short loc_180004B6E
0x180004be0  mov     edx, 37h ; '7'
0x180004be5  mov     dword ptr [rsp+60h+var_40], edi
0x180004be9  jmp     short loc_180004C5E
0x180004beb  mov     edx, [rbp+arg_8]
0x180004bee  lea     rcx, [rbp+Block]
0x180004bf2  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180004bf7  mov     rdx, rax
0x180004bfa  lea     rcx, [rbp+var_8]
0x180004bfe  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180004c03  mov     rcx, [rbp+Block]; Block
0x180004c07  mov     [rbp+Block], r13
0x180004c0b  test    rcx, rcx
0x180004c0e  jz      short loc_180004C15
0x180004c10  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004c15  mov     r14, [rbp+var_8]
0x180004c19  test    r14, r14
0x180004c1c  jnz     loc_180004CF8
0x180004c22  mov     eax, 8007000Eh
0x180004c27  mov     edi, eax
0x180004c29  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004c30  jb      loc_180004B6E
0x180004c36  lea     edx, [r14+2Fh]
0x180004c3a  jmp     short loc_180004C5A
0x180004c3c  mov     edi, 80004003h
0x180004c41  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004c48  jb      loc_180004B7D
0x180004c4e  mov     edx, 28h ; '('
0x180004c53  jmp     short loc_180004BE5
0x180004c55  mov     edx, 2Bh ; '+'
0x180004c5a  mov     dword ptr [rsp+60h+var_40], eax
0x180004c5e  xor     r9d, r9d
0x180004c61  jmp     short loc_180004C6C
0x180004c63  mov     edx, 31h ; '1'
0x180004c68  mov     dword ptr [rsp+60h+var_40], edi
0x180004c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c73  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180004c7a  mov     rcx, [rcx+10h]
0x180004c7e  call    WPP_SF_qD
0x180004c83  jmp     loc_180004B6E
0x180004c88  mov     esi, 80070057h
0x180004c8d  mov     edi, esi
0x180004c8f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004c96  jb      loc_180004B7D
0x180004c9c  mov     edx, 29h ; ')'
0x180004ca1  mov     dword ptr [rsp+60h+var_40], esi
0x180004ca5  jmp     short loc_180004C5E
0x180004ca7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004cae  jb      loc_180004B6E
0x180004cb4  jmp     short loc_180004C55
0x180004cb6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004cbd  jb      loc_180004B6E
0x180004cc3  mov     edx, 2Dh ; '-'
0x180004cc8  jmp     short loc_180004C5A
0x180004cca  lea     r8, [rbp+arg_8]; unsigned int *
0x180004cce  xor     edx, edx; unsigned int
0x180004cd0  xor     ecx, ecx; unsigned __int16 *
0x180004cd2  call    ?FSGetCurrentProcessConfigurationInfo@@YAJPEAGKPEAK@Z; FSGetCurrentProcessConfigurationInfo(ushort *,ulong,ulong *)
0x180004cd7  mov     edi, eax
0x180004cd9  test    eax, eax
0x180004cdb  jns     loc_180004BEB
0x180004ce1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004ce8  jb      loc_180004B6E
0x180004cee  mov     edx, 2Eh ; '.'
0x180004cf3  jmp     loc_180004C5A
0x180004cf8  mov     edx, [rbp+arg_8]; unsigned int
0x180004cfb  lea     r8, [rbp+arg_8]; unsigned int *
0x180004cff  mov     rcx, r14; unsigned __int16 *
0x180004d02  call    ?FSGetCurrentProcessConfigurationInfo@@YAJPEAGKPEAK@Z; FSGetCurrentProcessConfigurationInfo(ushort *,ulong,ulong *)
0x180004d07  mov     edi, eax
0x180004d09  test    eax, eax
0x180004d0b  jns     short loc_180004D24
0x180004d0d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004d14  jb      loc_180004B6E
0x180004d1a  mov     edx, 30h ; '0'
0x180004d1f  jmp     loc_180004C5A
0x180004d24  mov     eax, [rbp+arg_8]
0x180004d27  mov     r12, r14
0x180004d2a  mov     r13, rbx
0x180004d2d  jmp     loc_180004AD2
0x180004d32  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004d39  jb      loc_180004B6E
0x180004d3f  jmp     loc_180004C63
0x180004d44  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004d4b  jb      loc_180004B6E
0x180004d51  mov     edx, 36h ; '6'
0x180004d56  jmp     loc_180004C5A
0x180004d5b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004d62  jb      loc_180004B6E
0x180004d68  mov     edx, 39h ; '9'
0x180004d6d  jmp     loc_180004C5A
0x180004d72  mov     eax, 8007000Eh
0x180004d77  mov     edi, eax
0x180004d79  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180004d80  jb      short loc_180004DA5
0x180004d82  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d89  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180004d90  mov     edx, 2Ch ; ','
0x180004d95  mov     dword ptr [rsp+60h+var_40], eax
0x180004d99  xor     r9d, r9d
0x180004d9c  mov     rcx, [rcx+10h]
0x180004da0  call    WPP_SF_qD
0x180004da5  mov     rbx, r13
0x180004da8  jmp     loc_180004B6E
0x180004dad  mov     rcx, rbx; Block
0x180004db0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004db5  jmp     loc_180004B8B
```
