# RfbShellFolderBase::GetDisplayNameOf(_ITEMID_CHILD const *,ulong,_STRRET *)

- ea: `0x180015660`
- end: `0x180015b42`
- name: `?GetDisplayNameOf@RfbShellFolderBase@@UEAAJPEFBU_ITEMID_CHILD@@KPEAU_STRRET@@@Z`
- size: `1250`
- prototype: `__int64 __fastcall(RfbShellFolderBase *this, const ITEMIDLIST *, __int64, struct _STRRET *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002030`
- `0x180002dc4`
- `0x18000591c`
- `0x1800070cc`
- `0x1800078ec`
- `0x1800092f0`
- `0x18000937c`
- `0x180015660`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001589e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001594e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800159ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800159f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015a8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001589e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001594e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800159ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800159f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015a8c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180015acf`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180015acf`
- `SHELL32!__imp_ILCloneFirst` at `0x18001581d`
- `SHELL32!__imp_ILCloneFirst` at `0x18001581d`
- `SHELL32!__imp_ILGetNext` at `0x1800157fe`
- `SHELL32!__imp_ILGetNext` at `0x1800157fe`
- `SHLWAPI!StrRetToStrW` at `0x180015997`
- `SHLWAPI!StrRetToStrW` at `0x180015997`

## pseudocode

```c
__int64 __fastcall RfbShellFolderBase::GetDisplayNameOf(
        RfbShellFolderBase *this,
        const ITEMIDLIST *a2,
        __int64 a3,
        struct _STRRET *a4)
{
  int v5; // r14d
  char *v9; // rdi
  __int64 v10; // rax
  LPITEMIDLIST v11; // rax
  const ITEMIDLIST *v12; // rsi
  LPITEMIDLIST v13; // rbx
  int v14; // eax
  unsigned int v15; // edi
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  HRESULT v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  const WCHAR *v22; // rcx
  HRESULT v23; // eax
  unsigned int v24; // ebx
  int *v25; // [rsp+20h] [rbp-1E8h]
  int v26[2]; // [rsp+30h] [rbp-1D8h] BYREF
  LPWSTR ppsz[3]; // [rsp+38h] [rbp-1D0h] BYREF
  STRRET pstr; // [rsp+50h] [rbp-1B8h] BYREF
  LPCWSTR psz[2]; // [rsp+160h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+170h] [rbp-98h]
  unsigned __int64 v31; // [rsp+178h] [rbp-90h]
  __int128 v32; // [rsp+180h] [rbp-88h] BYREF
  __m128i si128; // [rsp+190h] [rbp-78h]
  _OWORD v34[2]; // [rsp+1A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v5 = a3;
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x344,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
      (const char *)0x80070057LL,
      (int)v25);
    return 2147942487LL;
  }
  *(_OWORD *)psz = 0;
  v30 = 0;
  v31 = 7;
  LOWORD(psz[0]) = 0;
  v9 = (char *)this - 8;
  if ( (a3 & 0x8000) != 0 )
  {
    LOBYTE(a3) = 1;
    v10 = (*(__int64 (__fastcall **)(char *, __int128 *, __int64))(*(_QWORD *)v9 + 48LL))((char *)this - 8, &v32, a3);
    std::wstring::operator=(psz, v10);
    std::wstring::~wstring((char **)&v32);
  }
  if ( a2 && a2->mkid.cb )
  {
    v32 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v32) = 0;
    v34[0] = 0;
    v34[1] = si128;
    LOWORD(v34[0]) = 0;
    (*(void (__fastcall **)(char *, const ITEMIDLIST *, __int128 *, _OWORD *))(*(_QWORD *)v9 + 88LL))(v9, a2, &v32, v34);
    if ( v30 )
      std::wstring::append(psz, L"\\");
    if ( (v5 & 0x4001) == 1 )
      std::wstring::append(psz, &v32);
    else
      std::wstring::append(psz, v34);
    if ( (v5 & 0xC000) != 0 )
    {
      v11 = ILGetNext(a2);
      v12 = v11;
      if ( v11 )
      {
        if ( v11->mkid.cb )
        {
          v13 = ILCloneFirst(a2);
          ppsz[1] = &v13->mkid.cb;
          *(_QWORD *)v26 = 0;
          v25 = v26;
          v14 = (*(__int64 (__fastcall **)(RfbShellFolderBase *, LPITEMIDLIST, _QWORD, GUID *))(*(_QWORD *)this + 40LL))(
                  this,
                  v13,
                  0,
                  &GUID_000214e6_0000_0000_c000_000000000046);
          v15 = v14;
          if ( v14 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x376,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
              (const char *)(unsigned int)v14,
              (int)v26);
            v16 = *(_QWORD *)v26;
            if ( *(_QWORD *)v26 )
            {
              *(_QWORD *)v26 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
            }
            if ( !v13 )
              goto LABEL_32;
            goto LABEL_31;
          }
          memset_0(&pstr, 0, sizeof(pstr));
          v17 = (*(__int64 (__fastcall **)(_QWORD, const ITEMIDLIST *, _QWORD, STRRET *))(**(_QWORD **)v26 + 88LL))(
                  *(_QWORD *)v26,
                  v12,
                  v5 | 1u,
                  &pstr);
          v15 = v17;
          if ( v17 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x379,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
              (const char *)(unsigned int)v17,
              (int)v26);
            v18 = *(_QWORD *)v26;
            if ( *(_QWORD *)v26 )
            {
              *(_QWORD *)v26 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            }
            if ( !v13 )
              goto LABEL_32;
            goto LABEL_31;
          }
          ppsz[0] = 0;
          v19 = StrRetToStrW(&pstr, v12, ppsz);
          v15 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x37B,
              (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
              (const char *)(unsigned int)v19,
              (int)v26);
            if ( ppsz[0] )
              CoTaskMemFree(ppsz[0]);
            v20 = *(_QWORD *)v26;
            if ( *(_QWORD *)v26 )
            {
              *(_QWORD *)v26 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            }
            if ( !v13 )
              goto LABEL_32;
LABEL_31:
            CoTaskMemFree(v13);
LABEL_32:
            std::wstring::~wstring((char **)v34);
            std::wstring::~wstring((char **)&v32);
            std::wstring::~wstring((char **)psz);
            return v15;
          }
          std::wstring::append(psz, L"\\");
          std::wstring::append(psz, ppsz[0]);
          if ( ppsz[0] )
            CoTaskMemFree(ppsz[0]);
          v21 = *(_QWORD *)v26;
          if ( *(_QWORD *)v26 )
          {
            *(_QWORD *)v26 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          }
          if ( v13 )
            CoTaskMemFree(v13);
        }
      }
    }
    std::wstring::~wstring((char **)v34);
    std::wstring::~wstring((char **)&v32);
  }
  v22 = (const WCHAR *)psz;
  if ( v31 > 7 )
    v22 = psz[0];
  a4->uType = 0;
  v23 = SHStrDupW(v22, &a4->pOleStr);
  v24 = v23;
  if ( v23 >= 0 )
  {
    std::wstring::~wstring((char **)psz);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x382,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
      (const char *)(unsigned int)v23,
      (int)v25);
    std::wstring::~wstring((char **)psz);
    return v24;
  }
}

```

## disassembly

```asm
0x180015660  push    rbx
0x180015662  push    rsi
0x180015663  push    rdi
0x180015664  push    r12
0x180015666  push    r13
0x180015668  push    r14
0x18001566a  push    r15
0x18001566c  sub     rsp, 1D0h
0x180015673  mov     rax, cs:__security_cookie
0x18001567a  xor     rax, rsp
0x18001567d  mov     [rsp+208h+var_48], rax
0x180015685  mov     r15, r9
0x180015688  mov     r14d, r8d
0x18001568b  mov     rbx, rdx
0x18001568e  mov     r12, rcx
0x180015691  xor     r13d, r13d
0x180015694  test    r9, r9
0x180015697  jnz     short loc_1800156C1
0x180015699  mov     rcx, [rsp+208h]; this
0x1800156a1  mov     ebx, 80070057h
0x1800156a6  mov     r9d, ebx; char *
0x1800156a9  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x1800156b0  mov     edx, 344h; void *
0x1800156b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800156ba  mov     eax, ebx
0x1800156bc  jmp     loc_180015B1E
0x1800156c1  xorps   xmm0, xmm0
0x1800156c4  movups  xmmword ptr [rsp+208h+psz], xmm0
0x1800156cc  mov     [rsp+208h+var_98], r13
0x1800156d4  mov     [rsp+208h+var_90], 7
0x1800156e0  mov     word ptr [rsp+208h+psz], r13w
0x1800156e9  lea     rdi, [rcx-8]
0x1800156ed  bt      r14d, 0Fh
0x1800156f2  jnb     short loc_18001572B
0x1800156f4  mov     rax, [rdi]
0x1800156f7  mov     r8b, 1
0x1800156fa  lea     rdx, [rsp+208h+var_88]
0x180015702  mov     rcx, rdi
0x180015705  mov     rax, [rax+30h]
0x180015709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001570e  mov     rdx, rax
0x180015711  lea     rcx, [rsp+208h+psz]
0x180015719  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001571e  lea     rcx, [rsp+208h+var_88]
0x180015726  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001572b  test    rbx, rbx
0x18001572e  jz      loc_180015AAE
0x180015734  cmp     [rbx], r13w
0x180015738  jbe     loc_180015AAE
0x18001573e  xorps   xmm0, xmm0
0x180015741  movups  [rsp+208h+var_88], xmm0
0x180015749  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180015751  movdqu  [rsp+208h+var_78], xmm1
0x18001575a  mov     word ptr [rsp+208h+var_88], r13w
0x180015763  movups  [rsp+208h+var_68], xmm0
0x18001576b  movdqu  [rsp+208h+var_58], xmm1
0x180015774  mov     word ptr [rsp+208h+var_68], r13w
0x18001577d  mov     rax, [rdi]
0x180015780  lea     r9, [rsp+208h+var_68]
0x180015788  lea     r8, [rsp+208h+var_88]
0x180015790  mov     rdx, rbx
0x180015793  mov     rcx, rdi
0x180015796  mov     rax, [rax+58h]
0x18001579a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001579f  cmp     [rsp+208h+var_98], r13
0x1800157a7  jz      short loc_1800157BD
0x1800157a9  lea     rdx, asc_18001C4FC; "\\"
0x1800157b0  lea     rcx, [rsp+208h+psz]; Src
0x1800157b8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800157bd  mov     eax, r14d
0x1800157c0  and     eax, 4001h
0x1800157c5  lea     rcx, [rsp+208h+psz]; Src
0x1800157cd  cmp     eax, 1
0x1800157d0  jnz     short loc_1800157E1
0x1800157d2  lea     rdx, [rsp+208h+var_88]
0x1800157da  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800157df  jmp     short loc_1800157EE
0x1800157e1  lea     rdx, [rsp+208h+var_68]
0x1800157e9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800157ee  test    r14d, 0C000h
0x1800157f5  jz      loc_180015A93
0x1800157fb  mov     rcx, rbx; pidl
0x1800157fe  call    cs:__imp_ILGetNext
0x180015804  mov     rsi, rax
0x180015807  test    rax, rax
0x18001580a  jz      loc_180015A93
0x180015810  cmp     [rax], r13w
0x180015814  jbe     loc_180015A93
0x18001581a  mov     rcx, rbx; pidl
0x18001581d  call    cs:__imp_ILCloneFirst
0x180015823  mov     rbx, rax
0x180015826  mov     [rsp+208h+var_1C8], rax
0x18001582b  mov     qword ptr [rsp+208h+var_1D8], r13
0x180015830  mov     rdx, [r12]
0x180015834  mov     rax, [rdx+28h]
0x180015838  lea     rcx, [rsp+208h+var_1D8]
0x18001583d  mov     qword ptr [rsp+208h+var_1E8], rcx; int
0x180015842  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x180015849  xor     r8d, r8d
0x18001584c  mov     rdx, rbx
0x18001584f  mov     rcx, r12
0x180015852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015857  mov     edi, eax
0x180015859  test    eax, eax
0x18001585b  jns     short loc_1800158D5
0x18001585d  mov     rcx, [rsp+208h]; this
0x180015865  mov     r9d, eax; char *
0x180015868  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x18001586f  mov     edx, 376h; void *
0x180015874  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015879  nop
0x18001587a  mov     rcx, qword ptr [rsp+208h+var_1D8]
0x18001587f  test    rcx, rcx
0x180015882  jz      short loc_180015896
0x180015884  mov     qword ptr [rsp+208h+var_1D8], r13
0x180015889  mov     rax, [rcx]
0x18001588c  mov     rax, [rax+10h]
0x180015890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015895  nop
0x180015896  test    rbx, rbx
0x180015899  jz      short loc_1800158A5
0x18001589b  mov     rcx, rbx; pv
0x18001589e  call    cs:__imp_CoTaskMemFree
0x1800158a4  nop
0x1800158a5  lea     rcx, [rsp+208h+var_68]
0x1800158ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800158b2  nop
0x1800158b3  lea     rcx, [rsp+208h+var_88]
0x1800158bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800158c0  nop
0x1800158c1  lea     rcx, [rsp+208h+psz]
0x1800158c9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800158ce  mov     eax, edi
0x1800158d0  jmp     loc_180015B1E
0x1800158d5  xor     edx, edx; Val
0x1800158d7  mov     r8d, 110h; Size
0x1800158dd  lea     rcx, [rsp+208h+pstr]; void *
0x1800158e2  call    memset_0
0x1800158e7  mov     rcx, qword ptr [rsp+208h+var_1D8]
0x1800158ec  mov     rax, [rcx]
0x1800158ef  or      r14d, 1
0x1800158f3  lea     r9, [rsp+208h+pstr]
0x1800158f8  mov     r8d, r14d
0x1800158fb  mov     rdx, rsi
0x1800158fe  mov     rax, [rax+58h]
0x180015902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015907  mov     edi, eax
0x180015909  test    eax, eax
0x18001590b  jns     short loc_180015985
0x18001590d  mov     rcx, [rsp+208h]; this
0x180015915  mov     r9d, eax; char *
0x180015918  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x18001591f  mov     edx, 379h; void *
0x180015924  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015929  nop
0x18001592a  mov     rcx, qword ptr [rsp+208h+var_1D8]
0x18001592f  test    rcx, rcx
0x180015932  jz      short loc_180015946
0x180015934  mov     qword ptr [rsp+208h+var_1D8], r13
0x180015939  mov     rax, [rcx]
0x18001593c  mov     rax, [rax+10h]
0x180015940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015945  nop
0x180015946  test    rbx, rbx
0x180015949  jz      short loc_180015955
0x18001594b  mov     rcx, rbx; pv
0x18001594e  call    cs:__imp_CoTaskMemFree
0x180015954  nop
0x180015955  lea     rcx, [rsp+208h+var_68]
0x18001595d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015962  nop
0x180015963  lea     rcx, [rsp+208h+var_88]
0x18001596b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015970  nop
0x180015971  lea     rcx, [rsp+208h+psz]
0x180015979  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001597e  mov     eax, edi
0x180015980  jmp     loc_180015B1E
0x180015985  mov     [rsp+208h+ppsz], r13
0x18001598a  lea     r8, [rsp+208h+ppsz]; ppsz
0x18001598f  mov     rdx, rsi; pidl
0x180015992  lea     rcx, [rsp+208h+pstr]; pstr
0x180015997  call    cs:__imp_StrRetToStrW
0x18001599d  mov     edi, eax
0x18001599f  test    eax, eax
0x1800159a1  jns     loc_180015A30
0x1800159a7  mov     rcx, [rsp+208h]; this
0x1800159af  mov     r9d, eax; char *
0x1800159b2  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x1800159b9  mov     edx, 37Bh; void *
0x1800159be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800159c3  nop
0x1800159c4  mov     rcx, [rsp+208h+ppsz]; pv
0x1800159c9  test    rcx, rcx
0x1800159cc  jz      short loc_1800159D5
0x1800159ce  call    cs:__imp_CoTaskMemFree
0x1800159d4  nop
0x1800159d5  mov     rcx, qword ptr [rsp+208h+var_1D8]
0x1800159da  test    rcx, rcx
0x1800159dd  jz      short loc_1800159F1
0x1800159df  mov     qword ptr [rsp+208h+var_1D8], r13
0x1800159e4  mov     rax, [rcx]
0x1800159e7  mov     rax, [rax+10h]
0x1800159eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159f0  nop
0x1800159f1  test    rbx, rbx
0x1800159f4  jz      short loc_180015A00
0x1800159f6  mov     rcx, rbx; pv
0x1800159f9  call    cs:__imp_CoTaskMemFree
0x1800159ff  nop
0x180015a00  lea     rcx, [rsp+208h+var_68]
0x180015a08  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015a0d  nop
0x180015a0e  lea     rcx, [rsp+208h+var_88]
0x180015a16  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015a1b  nop
0x180015a1c  lea     rcx, [rsp+208h+psz]
0x180015a24  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015a29  mov     eax, edi
0x180015a2b  jmp     loc_180015B1E
0x180015a30  lea     rdx, asc_18001C4FC; "\\"
0x180015a37  lea     rcx, [rsp+208h+psz]; Src
0x180015a3f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180015a44  mov     rdx, [rsp+208h+ppsz]; void *
0x180015a49  lea     rcx, [rsp+208h+psz]; Src
0x180015a51  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180015a56  nop
0x180015a57  mov     rcx, [rsp+208h+ppsz]; pv
0x180015a5c  test    rcx, rcx
0x180015a5f  jz      short loc_180015A68
0x180015a61  call    cs:__imp_CoTaskMemFree
0x180015a67  nop
0x180015a68  mov     rcx, qword ptr [rsp+208h+var_1D8]
0x180015a6d  test    rcx, rcx
0x180015a70  jz      short loc_180015A84
0x180015a72  mov     qword ptr [rsp+208h+var_1D8], r13
0x180015a77  mov     rax, [rcx]
0x180015a7a  mov     rax, [rax+10h]
0x180015a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a83  nop
0x180015a84  test    rbx, rbx
0x180015a87  jz      short loc_180015A93
0x180015a89  mov     rcx, rbx; pv
0x180015a8c  call    cs:__imp_CoTaskMemFree
0x180015a92  nop
0x180015a93  lea     rcx, [rsp+208h+var_68]
0x180015a9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015aa0  nop
0x180015aa1  lea     rcx, [rsp+208h+var_88]
0x180015aa9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015aae  lea     rcx, [rsp+208h+psz]
0x180015ab6  cmp     [rsp+208h+var_90], 7
0x180015abf  cmova   rcx, [rsp+208h+psz]; psz
0x180015ac8  mov     [r15], r13d
0x180015acb  lea     rdx, [r15+8]; ppwsz
0x180015acf  call    cs:__imp_SHStrDupW
0x180015ad5  mov     ebx, eax
0x180015ad7  test    eax, eax
0x180015ad9  jns     short loc_180015B09
0x180015adb  mov     rcx, [rsp+208h]; this
0x180015ae3  mov     r9d, eax; char *
0x180015ae6  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x180015aed  mov     edx, 382h; void *
0x180015af2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015af7  nop
0x180015af8  lea     rcx, [rsp+208h+psz]
0x180015b00  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015b05  mov     eax, ebx
0x180015b07  jmp     short loc_180015B1E
0x180015b09  lea     rcx, [rsp+208h+psz]
0x180015b11  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015b16  xor     eax, eax
0x180015b18  jmp     short loc_180015B1E
0x180015b1a  mov     eax, [rsp+208h+var_1D8]
0x180015b1e  mov     rcx, [rsp+208h+var_48]
0x180015b26  xor     rcx, rsp; StackCookie
0x180015b29  call    __security_check_cookie
0x180015b2e  add     rsp, 1D0h
0x180015b35  pop     r15
0x180015b37  pop     r14
0x180015b39  pop     r13
0x180015b3b  pop     r12
0x180015b3d  pop     rdi
0x180015b3e  pop     rsi
0x180015b3f  pop     rbx
0x180015b40  retn
```
