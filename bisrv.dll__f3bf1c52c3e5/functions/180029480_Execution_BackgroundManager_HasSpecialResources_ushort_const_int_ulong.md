# Execution::BackgroundManager::HasSpecialResources(ushort const *,int *,ulong *)

- ea: `0x180029480`
- end: `0x1800296f6`
- name: `?HasSpecialResources@BackgroundManager@Execution@@MEAAJPEBGPEAHPEAK@Z`
- size: `630`
- prototype: `__int64 __fastcall(Execution::BackgroundManager *__hidden this, const unsigned __int16 *, int *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180029480`
- `0x1800296fc`
- `0x180029be0`
- `0x180029fcc`
- `0x180070eec`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x180029515`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x180029515`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002956f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002956f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029582`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800295b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029582`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800295b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800295f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800295f0`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180029533`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180029533`

## pseudocode

```c
__int64 __fastcall Execution::BackgroundManager::HasSpecialResources(
        Execution::BackgroundManager *this,
        const unsigned __int16 *a2,
        int *a3,
        unsigned int *a4)
{
  HSTRING v5; // rbx
  int PackageFullNameFromKey; // edi
  LONG v9; // eax
  int v10; // edi
  unsigned __int64 v11; // rdx
  char *v12; // rsi
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v15; // r8
  char *v16; // r15
  __int64 v17; // r14
  signed __int64 v18; // r12
  unsigned __int64 v19; // r10
  char *v20; // rcx
  _WORD *v21; // r8
  __int64 v22; // rdx
  char *v23; // r9
  int v24; // [rsp+20h] [rbp-E0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+24h] [rbp-DCh] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int *v27; // [rsp+30h] [rbp-D0h]
  void *Block[2]; // [rsp+38h] [rbp-C8h] BYREF
  char v29; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR packageFullName[128]; // [rsp+F0h] [rbp-10h] BYREF

  v27 = a4;
  *a3 = 0;
  v5 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(Block);
  memset_0(packageFullName, 0, sizeof(packageFullName));
  v24 = 256;
  memset_0(packageFamilyName, 0, 0x82u);
  packageFamilyNameLength = 65;
  if ( !a2 )
  {
    v10 = -2147024809;
LABEL_10:
    v12 = (char *)Block[0];
    goto LABEL_11;
  }
  PackageFullNameFromKey = PsmGetPackageFullNameFromKey(a2, packageFullName, &v24);
  if ( PackageFullNameFromKey < 0 )
  {
    v10 = PackageFullNameFromKey | 0x10000000;
  }
  else
  {
    v9 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
    v10 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      string = 0;
      v11 = -1;
      do
        ++v11;
      while ( packageFamilyName[v11] );
      if ( v11 > 0xFFFFFFFF )
      {
        v10 = -2147024362;
      }
      else
      {
        v10 = WindowsCreateString(packageFamilyName, v11, &string);
        if ( v10 >= 0 )
        {
          v5 = string;
          WindowsDeleteString(0);
        }
      }
    }
  }
  if ( v10 < 0 )
    goto LABEL_10;
  StringRawBuffer = WindowsGetStringRawBuffer(v5, 0);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
    Block,
    StringRawBuffer);
  v16 = (char *)this + 408;
  v17 = *((_QWORD *)v16 + 2);
  if ( !v17 )
    goto LABEL_10;
  v12 = (char *)Block[0];
  v18 = ((char *)Block[1] - (char *)Block[0]) >> 1;
  v19 = utl::_HashBytes((utl *)Block[0], (const void *)(2 * v18), v15);
  v20 = *(char **)(v17 + 16 * (v19 & ((8LL << v16[32]) - 1)));
  if ( v20 )
  {
    while ( v20 != **(char ***)(v17 + 16 * (v19 & ((8LL << v16[32]) - 1)) + 8) )
    {
      if ( *((_QWORD *)v20 + 2) >= v19 )
      {
        if ( *((_QWORD *)v20 + 2) > v19 )
          break;
        v21 = (_WORD *)*((_QWORD *)v20 + 3);
        v22 = (__int64)(*((_QWORD *)v20 + 4) - (_QWORD)v21) >> 1;
        if ( v22 == v18 )
        {
          v23 = v12;
          while ( v22 )
          {
            if ( *(_WORD *)v23 != *v21 )
              goto LABEL_33;
            --v22;
            v23 += 2;
            ++v21;
          }
          if ( v20 != v16 )
          {
            *a3 = 1;
            *v27 = *((_DWORD *)v20 + 14);
          }
          break;
        }
      }
LABEL_33:
      v20 = *(char **)v20;
    }
  }
LABEL_11:
  if ( v12 != &v29 )
    operator delete(v12);
  if ( v5 )
    WindowsDeleteString(v5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180029480  mov     [rsp-8+arg_0], rbx
0x180029485  push    rbp
0x180029486  push    rsi
0x180029487  push    rdi
0x180029488  push    r12
0x18002948a  push    r13
0x18002948c  push    r14
0x18002948e  push    r15
0x180029490  lea     rbp, [rsp-100h]
0x180029498  sub     rsp, 200h
0x18002949f  mov     rax, cs:__security_cookie
0x1800294a6  xor     rax, rsp
0x1800294a9  mov     [rbp+130h+var_40], rax
0x1800294b0  xor     r12d, r12d
0x1800294b3  mov     [rsp+230h+var_200], r9
0x1800294b8  mov     r15, rcx
0x1800294bb  mov     [r8], r12d
0x1800294be  lea     rcx, [rsp+230h+Block]
0x1800294c3  mov     ebx, r12d
0x1800294c6  mov     r13, r8
0x1800294c9  mov     rdi, rdx
0x1800294cc  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800294d1  mov     esi, 100h
0x1800294d6  lea     rcx, [rbp+130h+packageFullName]; void *
0x1800294da  mov     r8d, esi; Size
0x1800294dd  xor     edx, edx; Val
0x1800294df  call    memset_0
0x1800294e4  xor     edx, edx; Val
0x1800294e6  mov     [rsp+230h+var_210], esi
0x1800294ea  lea     r8d, [rsi-7Eh]; Size
0x1800294ee  lea     rcx, [rsp+230h+packageFamilyName]; void *
0x1800294f3  call    memset_0
0x1800294f8  mov     [rsp+230h+packageFamilyNameLength], 41h ; 'A'
0x180029500  test    rdi, rdi
0x180029503  jz      loc_1800296DB
0x180029509  lea     r8, [rsp+230h+var_210]
0x18002950e  mov     rcx, rdi
0x180029511  lea     rdx, [rbp+130h+packageFullName]
0x180029515  call    cs:__imp_PsmGetPackageFullNameFromKey
0x18002951b  mov     edi, eax
0x18002951d  test    eax, eax
0x18002951f  js      loc_1800296E5
0x180029525  lea     r8, [rsp+230h+packageFamilyName]; packageFamilyName
0x18002952a  lea     rdx, [rsp+230h+packageFamilyNameLength]; packageFamilyNameLength
0x18002952f  lea     rcx, [rbp+130h+packageFullName]; packageFullName
0x180029533  call    cs:__imp_PackageFamilyNameFromFullName
0x180029539  mov     edi, eax
0x18002953b  test    eax, eax
0x18002953d  jnz     loc_1800296C7
0x180029543  mov     [rsp+230h+string], r12
0x180029548  lea     rax, [rsp+230h+packageFamilyName]
0x18002954d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180029551  inc     rdx; length
0x180029554  cmp     [rax+rdx*2], r12w
0x180029559  jnz     short loc_180029551
0x18002955b  mov     eax, 0FFFFFFFFh
0x180029560  cmp     rdx, rax
0x180029563  ja      short loc_1800295E4
0x180029565  lea     r8, [rsp+230h+string]; string
0x18002956a  lea     rcx, [rsp+230h+packageFamilyName]; sourceString
0x18002956f  call    cs:__imp_WindowsCreateString
0x180029575  mov     edi, eax
0x180029577  test    eax, eax
0x180029579  js      short loc_180029588
0x18002957b  mov     rbx, [rsp+230h+string]
0x180029580  xor     ecx, ecx; string
0x180029582  call    cs:__imp_WindowsDeleteString
0x180029588  test    edi, edi
0x18002958a  jns     short loc_1800295EB
0x18002958c  mov     rsi, [rsp+230h+Block]
0x180029591  lea     rax, [rsp+230h+var_1E8]
0x180029596  cmp     rsi, rax
0x180029599  jz      short loc_1800295AA
0x18002959b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800295a2  mov     rcx, rsi; Block
0x1800295a5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800295aa  test    rbx, rbx
0x1800295ad  jz      short loc_1800295B8
0x1800295af  mov     rcx, rbx; string
0x1800295b2  call    cs:__imp_WindowsDeleteString
0x1800295b8  mov     eax, edi
0x1800295ba  mov     rcx, [rbp+130h+var_40]
0x1800295c1  xor     rcx, rsp; StackCookie
0x1800295c4  call    __security_check_cookie
0x1800295c9  mov     rbx, [rsp+230h+arg_0]
0x1800295d1  add     rsp, 200h
0x1800295d8  pop     r15
0x1800295da  pop     r14
0x1800295dc  pop     r13
0x1800295de  pop     r12
0x1800295e0  pop     rdi
0x1800295e1  pop     rsi
0x1800295e2  pop     rbp
0x1800295e3  retn
0x1800295e4  mov     edi, 80070216h
0x1800295e9  jmp     short loc_180029588
0x1800295eb  xor     edx, edx; length
0x1800295ed  mov     rcx, rbx; string
0x1800295f0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800295f6  mov     rdx, rax
0x1800295f9  lea     rcx, [rsp+230h+Block]
0x1800295fe  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180029603  add     r15, 198h
0x18002960a  mov     r14, [r15+10h]
0x18002960e  test    r14, r14
0x180029611  jz      loc_18002958C
0x180029617  mov     rsi, [rsp+230h+Block]
0x18002961c  mov     r12, [rsp+230h+var_1F0]
0x180029621  mov     rcx, rsi; this
0x180029624  sub     r12, rsi
0x180029627  sar     r12, 1
0x18002962a  lea     rdx, [r12+r12]; void *
0x18002962e  call    ?_HashBytes@utl@@YA_KPEBX_K@Z; utl::_HashBytes(void const *,unsigned __int64)
0x180029633  mov     cl, [r15+20h]
0x180029637  mov     r10, rax
0x18002963a  mov     eax, 8
0x18002963f  shl     rax, cl
0x180029642  dec     rax
0x180029645  and     rax, r10
0x180029648  add     rax, rax
0x18002964b  mov     rcx, [r14+rax*8]
0x18002964f  test    rcx, rcx
0x180029652  jz      loc_180029591
0x180029658  mov     rax, [r14+rax*8+8]
0x18002965d  mov     r11, [rax]
0x180029660  cmp     rcx, r11
0x180029663  jz      loc_180029591
0x180029669  cmp     [rcx+10h], r10
0x18002966d  jb      short loc_1800296EE
0x18002966f  ja      loc_180029591
0x180029675  mov     r8, [rcx+18h]
0x180029679  mov     rdx, [rcx+20h]
0x18002967d  sub     rdx, r8
0x180029680  sar     rdx, 1
0x180029683  cmp     rdx, r12
0x180029686  jnz     short loc_1800296EE
0x180029688  mov     r9, rsi
0x18002968b  test    rdx, rdx
0x18002968e  jz      short loc_1800296A7
0x180029690  movzx   eax, word ptr [r8]
0x180029694  cmp     [r9], ax
0x180029698  jnz     short loc_1800296EE
0x18002969a  dec     rdx
0x18002969d  add     r9, 2
0x1800296a1  add     r8, 2
0x1800296a5  jmp     short loc_18002968B
0x1800296a7  cmp     rcx, r15
0x1800296aa  jz      loc_180029591
0x1800296b0  mov     dword ptr [r13+0], 1
0x1800296b8  mov     eax, [rcx+38h]
0x1800296bb  mov     rcx, [rsp+230h+var_200]
0x1800296c0  mov     [rcx], eax
0x1800296c2  jmp     loc_180029591
0x1800296c7  jle     loc_180029588
0x1800296cd  movzx   edi, ax
0x1800296d0  or      edi, 80070000h
0x1800296d6  jmp     loc_180029588
0x1800296db  mov     edi, 80070057h
0x1800296e0  jmp     loc_18002958C
0x1800296e5  bts     edi, 1Ch
0x1800296e9  jmp     loc_180029588
0x1800296ee  mov     rcx, [rcx]
0x1800296f1  jmp     loc_180029660
```
