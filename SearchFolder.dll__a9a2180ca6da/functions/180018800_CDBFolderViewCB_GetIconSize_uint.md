# CDBFolderViewCB::GetIconSize(uint *)

- ea: `0x180018800`
- end: `0x1800189f1`
- name: `?GetIconSize@CDBFolderViewCB@@UEAAJPEAI@Z`
- size: `497`
- prototype: `__int64 __fastcall(CDBFolderViewCB *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004a50`
- `0x1800054dc`
- `0x180006900`
- `0x180006da4`
- `0x180006f6c`
- `0x180006fd4`
- `0x180012a94`
- `0x180014b78`
- `0x180018800`
- `0x18004fb0c`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800188e1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800188e1`
- `SHELL32!__imp_ILIsEqual` at `0x1800188b9`
- `SHELL32!__imp_ILIsEqual` at `0x1800188b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDBFolderViewCB::GetIconSize(CDBFolderViewCB *this, unsigned int *a2)
{
  const ITEMIDLIST *v4; // rbx
  signed int v6; // ebx
  int v7; // eax
  int v8; // ebx
  unsigned int v9; // eax
  int v10; // [rsp+20h] [rbp-30h] BYREF
  int v11; // [rsp+24h] [rbp-2Ch] BYREF
  void *ppvOut; // [rsp+28h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+30h] [rbp-20h] BYREF
  int v14; // [rsp+40h] [rbp-10h]

  *a2 = 96;
  v11 = 0;
  if ( CDBFolderViewCB::GetAutoListFlags((CDBFolderViewCB *)((char *)this - 16), (enum AUTOLISTFLAGS *)&v11) >= 0
    && (v11 & 0x800) != 0 )
  {
    *a2 = 96;
    v4 = (const ITEMIDLIST *)*((_QWORD *)this + 7);
    if ( dword_18006A724 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_18006A724);
      if ( dword_18006A724 == -1 )
      {
        lambda_8a9c95522d0320a256a7c22ff7515249_::operator()();
        atexit(GetGalleryPidl_::_2_::_dynamic_atexit_destructor_for__s_galleryPidl__);
        Init_thread_footer(&dword_18006A724);
      }
    }
    if ( ILIsEqual(pidl1, v4) )
    {
      ppvOut = 0;
      if ( IUnknown_QueryService(
             *((IUnknown **)this + 4),
             &GUID_9ea5491c_89c8_4bef_93d3_7f665fb82a33,
             &GUID_42f85136_db7e_439c_85f1_e4075d135fc8,
             &ppvOut) < 0 )
        *a2 = 48;
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>((__int64 *)&ppvOut);
    }
    return 0;
  }
  else
  {
    Buf1 = 0;
    v14 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 11) + 200LL))(
           *((_QWORD *)this + 11),
           &Buf1);
    if ( v6 >= 0 )
    {
      ppvOut = 0;
      v6 = IUnknown_QueryObject(
             *((struct IUnknown **)this + 11),
             &GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82,
             &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
             &ppvOut);
      if ( v6 >= 0 )
      {
        v10 = 0;
        if ( v14 == PKEY_Null.pid && !memcmp_0(&Buf1, &PKEY_Null, 0x10u) )
          v7 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvOut + 72LL))(ppvOut, &v10);
        else
          v7 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvOut + 144LL))(ppvOut, &v10);
        v6 = v7;
        if ( v7 >= 0 )
        {
          v8 = v10;
          v9 = -1;
          if ( v10 >= 0 )
            v9 = v10;
          *a2 = v9;
          v6 = (v8 >> 31) & 0x80070216;
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      }
    }
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x180018800  mov     [rsp-18h+arg_10], rbx
0x180018805  push    rbp
0x180018806  push    rsi
0x180018807  push    rdi
0x180018808  mov     rbp, rsp
0x18001880b  sub     rsp, 50h
0x18001880f  mov     rax, cs:__security_cookie
0x180018816  xor     rax, rsp
0x180018819  mov     [rbp+var_8], rax
0x18001881d  mov     rsi, rdx
0x180018820  mov     rdi, rcx
0x180018823  mov     ebx, 60h ; '`'
0x180018828  mov     [rdx], ebx
0x18001882a  mov     [rbp+var_2C], 0
0x180018831  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x180018835  lea     rdx, [rbp+var_2C]; enum AUTOLISTFLAGS *
0x180018839  call    ?GetAutoListFlags@CDBFolderViewCB@@AEAAJPEAW4AUTOLISTFLAGS@@@Z; CDBFolderViewCB::GetAutoListFlags(AUTOLISTFLAGS *)
0x18001883e  test    eax, eax
0x180018840  js      loc_180018901
0x180018846  test    [rbp+var_2C], 800h
0x18001884d  jz      loc_180018901
0x180018853  mov     [rsi], ebx
0x180018855  mov     rbx, [rdi+38h]
0x180018859  mov     ecx, cs:_tls_index
0x18001885f  mov     rax, gs:58h
0x180018868  mov     edx, 4
0x18001886d  mov     rax, [rax+rcx*8]
0x180018871  mov     ecx, [rdx+rax]
0x180018874  cmp     cs:dword_18006A724, ecx
0x18001887a  jle     short loc_1800188AF
0x18001887c  lea     rcx, dword_18006A724
0x180018883  call    _Init_thread_header
0x180018888  cmp     cs:dword_18006A724, 0FFFFFFFFh
0x18001888f  jnz     short loc_1800188AF
0x180018891  call    _lambda_8a9c95522d0320a256a7c22ff7515249___operator__
0x180018896  lea     rcx, _GetGalleryPidl____2____dynamic_atexit_destructor_for__s_galleryPidl__; void (__cdecl *)()
0x18001889d  call    atexit
0x1800188a2  nop
0x1800188a3  lea     rcx, dword_18006A724
0x1800188aa  call    _Init_thread_footer
0x1800188af  mov     rdx, rbx; pidl2
0x1800188b2  mov     rcx, cs:pidl1; pidl1
0x1800188b9  call    cs:__imp_ILIsEqual
0x1800188bf  test    eax, eax
0x1800188c1  jz      short loc_1800188FA
0x1800188c3  mov     [rbp+ppvOut], 0
0x1800188cb  lea     r9, [rbp+ppvOut]; ppvOut
0x1800188cf  lea     r8, _GUID_42f85136_db7e_439c_85f1_e4075d135fc8; riid
0x1800188d6  lea     rdx, _GUID_9ea5491c_89c8_4bef_93d3_7f665fb82a33; guidService
0x1800188dd  mov     rcx, [rdi+20h]; punk
0x1800188e1  call    cs:__imp_IUnknown_QueryService
0x1800188e7  test    eax, eax
0x1800188e9  jns     short loc_1800188F1
0x1800188eb  mov     dword ptr [rsi], 30h ; '0'
0x1800188f1  lea     rcx, [rbp+ppvOut]
0x1800188f5  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x1800188fa  xor     eax, eax
0x1800188fc  jmp     loc_1800189D5
0x180018901  xorps   xmm0, xmm0
0x180018904  xor     eax, eax
0x180018906  movups  [rbp+Buf1], xmm0
0x18001890a  mov     [rbp+var_10], eax
0x18001890d  mov     rcx, [rdi+58h]
0x180018911  mov     rax, [rcx]
0x180018914  lea     rdx, [rbp+Buf1]
0x180018918  mov     rax, [rax+0C8h]
0x18001891f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018924  mov     ebx, eax
0x180018926  test    eax, eax
0x180018928  js      loc_1800189D3
0x18001892e  mov     [rbp+ppvOut], 0
0x180018936  lea     r9, [rbp+ppvOut]; void **
0x18001893a  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456; struct _GUID *
0x180018941  lea     rdx, _GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82; struct _GUID *
0x180018948  mov     rcx, [rdi+58h]; struct IUnknown *
0x18001894c  call    ?IUnknown_QueryObject@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; IUnknown_QueryObject(IUnknown *,_GUID const &,_GUID const &,void * *)
0x180018951  mov     ebx, eax
0x180018953  test    eax, eax
0x180018955  js      short loc_1800189D3
0x180018957  mov     [rbp+var_30], 0
0x18001895e  mov     eax, cs:PKEY_Null.pid
0x180018964  cmp     [rbp+var_10], eax
0x180018967  jnz     short loc_180018990
0x180018969  mov     r8d, 10h; Size
0x18001896f  lea     rdx, PKEY_Null; Buf2
0x180018976  lea     rcx, [rbp+Buf1]; Buf1
0x18001897a  call    memcmp_0
0x18001897f  test    eax, eax
0x180018981  jnz     short loc_180018990
0x180018983  mov     rcx, [rbp+ppvOut]
0x180018987  mov     rax, [rcx]
0x18001898a  mov     rax, [rax+48h]
0x18001898e  jmp     short loc_18001899E
0x180018990  mov     rcx, [rbp+ppvOut]
0x180018994  mov     rax, [rcx]
0x180018997  mov     rax, [rax+90h]
0x18001899e  lea     rdx, [rbp+var_30]
0x1800189a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189a7  mov     ebx, eax
0x1800189a9  test    eax, eax
0x1800189ab  js      short loc_1800189C3
0x1800189ad  mov     ebx, [rbp+var_30]
0x1800189b0  or      eax, 0FFFFFFFFh
0x1800189b3  test    ebx, ebx
0x1800189b5  cmovns  eax, ebx
0x1800189b8  mov     [rsi], eax
0x1800189ba  sar     ebx, 1Fh
0x1800189bd  and     ebx, 80070216h
0x1800189c3  mov     rcx, [rbp+ppvOut]
0x1800189c7  mov     rax, [rcx]
0x1800189ca  mov     rax, [rax+10h]
0x1800189ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189d3  mov     eax, ebx
0x1800189d5  mov     rcx, [rbp+var_8]
0x1800189d9  xor     rcx, rsp; StackCookie
0x1800189dc  call    __security_check_cookie
0x1800189e1  mov     rbx, [rsp+50h+arg_10]
0x1800189e9  add     rsp, 50h
0x1800189ed  pop     rdi
0x1800189ee  pop     rsi
0x1800189ef  pop     rbp
0x1800189f0  retn
```
