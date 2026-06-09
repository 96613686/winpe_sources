# Windows::Internal::Storage::Cloud::CloudStoreCache::Save(ushort const *,ushort const *,ushort const *,uchar *,ulong,unsigned __int64)

- ea: `0x18007e130`
- end: `0x18007e428`
- name: `?Save@CloudStoreCache@Cloud@Storage@Internal@Windows@@UEAAJPEBG00PEAEK_K@Z`
- size: `760`
- prototype: `__int64 __fastcall(__int64 **this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, size_t, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180047904`
- `0x180062040`
- `0x18007e130`
- `0x18007e430`
- `0x18007e570`
- `0x1800c8458`
- `0x1800e93e0`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e250`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e277`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e250`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e277`

## string_xrefs

- `0x18007e235`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`
- `0x18007e2c1`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`
- `0x18007e2da`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`
- `0x18007e30f`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`
- `0x18007e3d7`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`
- `0x18007e411`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStoreCache::Save(
        __int64 **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int8 *a5,
        size_t a6,
        unsigned __int8 *a7)
{
  unsigned __int8 *Src; // r13
  unsigned int v12; // edi
  unsigned __int64 i; // rcx
  char v14; // al
  int CurrentBulkLocation; // eax
  int v16; // eax
  unsigned int v17; // ebx
  void *v19; // rcx
  int v20; // eax
  int v21; // eax
  __int64 *v22; // rcx
  __int64 v23; // rax
  unsigned __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rcx
  int v27; // eax
  int v28; // [rsp+20h] [rbp-58h]
  int v29; // [rsp+20h] [rbp-58h]
  int v30; // [rsp+20h] [rbp-58h]
  int v31; // [rsp+20h] [rbp-58h]
  int v32; // [rsp+20h] [rbp-58h]
  size_t Size; // [rsp+30h] [rbp-48h]
  __int64 *Sizea; // [rsp+30h] [rbp-48h]
  __int128 v35; // [rsp+40h] [rbp-38h] BYREF
  char v36; // [rsp+50h] [rbp-28h]
  unsigned __int8 **v37; // [rsp+58h] [rbp-20h] BYREF
  __int64 v38; // [rsp+60h] [rbp-18h] BYREF
  char v39; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  LPVOID pv; // [rsp+C0h] [rbp+48h] BYREF

  Src = a5;
  v12 = a6;
  if ( !(_DWORD)a6 )
  {
LABEL_7:
    v14 = 0;
    goto LABEL_8;
  }
  if ( (unsigned int)a6 >= 4 )
  {
    for ( i = 0; i < 4; ++i )
    {
      if ( a5[i] != *((_BYTE *)&qword_18022A7F0 + i) )
        goto LABEL_21;
    }
    goto LABEL_7;
  }
LABEL_21:
  v14 = 1;
LABEL_8:
  if ( v14 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
      (const char *)0x80070570LL,
      v28);
  pv = 0;
  *(_QWORD *)&v35 = &pv;
  *((_QWORD *)&v35 + 1) = 0;
  v36 = 1;
  CurrentBulkLocation = Windows::Internal::Storage::Cloud::CloudStoreCache::GetCurrentBulkLocation(
                          (Windows::Internal::Storage::Cloud::CloudStoreCache *)this,
                          a2,
                          a3,
                          a4,
                          (unsigned __int16 **)&v35 + 1);
  if ( CurrentBulkLocation < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
      (const char *)(unsigned int)CurrentBulkLocation,
      v29);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v35);
  LODWORD(v35) = 2;
  *(_QWORD *)((char *)&v35 + 4) = a7;
  HIDWORD(v35) = 0;
  if ( (*(int (__fastcall **)(__int64 *, _QWORD))(*this[2] + 24))(this[2], v12 + 16) < 0 )
  {
    v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*this[3] + 24))(this[3], v12);
    v17 = v21;
    if ( v21 >= 0 )
    {
      a7 = 0;
      v22 = this[3];
      v23 = *v22;
      v37 = &a7;
      v38 = 0;
      v39 = 1;
      Sizea = &v38;
      v32 = (int)Src;
      v17 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(v23 + 48))(
              v22,
              a2,
              a3,
              a4);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v37);
      if ( (v17 & 0x80000000) == 0 )
      {
        HIDWORD(v35) = 1;
        v26 = -1;
        do
          ++v26;
        while ( *(_WORD *)&a7[2 * v26] );
        LODWORD(Sizea) = 2 * v26 + 2;
        v27 = Windows::Internal::Storage::Cloud::CloudStoreCache::SaveToDefaultLocalStorage(
                (Windows::Internal::Storage::Cloud::CloudStoreCache *)this,
                a2,
                a3,
                a4,
                (struct Windows::Internal::Storage::Cloud::CloudStoreMetadata *)&v35,
                a7,
                (size_t)Sizea);
        v17 = v27;
        if ( v27 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&a7);
          goto LABEL_17;
        }
        v24 = (unsigned int)v27;
        v25 = 150;
      }
      else
      {
        v24 = v17;
        v25 = 144;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
        (const char *)v24,
        v32);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&a7);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
        (const char *)(unsigned int)v21,
        v29);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
    return v17;
  }
  LODWORD(Size) = v12;
  v16 = Windows::Internal::Storage::Cloud::CloudStoreCache::SaveToDefaultLocalStorage(
          (Windows::Internal::Storage::Cloud::CloudStoreCache *)this,
          a2,
          a3,
          a4,
          (struct Windows::Internal::Storage::Cloud::CloudStoreMetadata *)&v35,
          Src,
          Size);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
      (const char *)(unsigned int)v16,
      v30);
    if ( pv )
      CoTaskMemFree(pv);
    return v17;
  }
LABEL_17:
  v19 = pv;
  if ( pv )
  {
    v31 = (int)pv;
    v20 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*this[3] + 56))(
            this[3],
            a2,
            a3,
            a4);
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
        (const char *)(unsigned int)v20,
        v31);
    v19 = pv;
  }
  if ( v19 )
    CoTaskMemFree(v19);
  return 0;
}

```

## disassembly

```asm
0x18007e130  push    rbp
0x18007e132  push    rbx
0x18007e133  push    rsi
0x18007e134  push    rdi
0x18007e135  push    r12
0x18007e137  push    r13
0x18007e139  push    r14
0x18007e13b  push    r15
0x18007e13d  mov     rbp, rsp
0x18007e140  sub     rsp, 78h
0x18007e144  mov     r14, r9
0x18007e147  mov     r15, r8
0x18007e14a  mov     r12, rdx
0x18007e14d  mov     rsi, rcx
0x18007e150  mov     r13, [rbp+arg_20]
0x18007e154  mov     edi, dword ptr [rbp+arg_28]
0x18007e157  xor     ebx, ebx
0x18007e159  test    edi, edi
0x18007e15b  jz      short loc_18007E187
0x18007e15d  cmp     edi, 4
0x18007e160  jb      loc_18007E281
0x18007e166  mov     ecx, ebx
0x18007e168  cmp     rcx, 4
0x18007e16c  jnb     short loc_18007E187
0x18007e16e  lea     rax, qword_18022A7F0
0x18007e175  mov     al, [rcx+rax]
0x18007e178  cmp     [rcx+r13], al
0x18007e17c  jnz     loc_18007E281
0x18007e182  inc     rcx
0x18007e185  jmp     short loc_18007E168
0x18007e187  mov     al, bl
0x18007e189  mov     rcx, [rbp+40h]; this
0x18007e18d  test    al, al
0x18007e18f  jnz     loc_18007E2BB
0x18007e195  mov     [rbp+pv], rbx
0x18007e199  lea     rax, [rbp+pv]
0x18007e19d  mov     qword ptr [rbp+var_38], rax
0x18007e1a1  mov     [rbp+var_30], rbx
0x18007e1a5  mov     [rbp+var_28], 1
0x18007e1a9  lea     rax, [rbp+var_30]
0x18007e1ad  mov     [rsp+78h+var_58], rax; int
0x18007e1b2  mov     r9, r14; unsigned __int16 *
0x18007e1b5  mov     r8, r15; unsigned __int16 *
0x18007e1b8  mov     rdx, r12; unsigned __int16 *
0x18007e1bb  mov     rcx, rsi; this
0x18007e1be  call    ?GetCurrentBulkLocation@CloudStoreCache@Cloud@Storage@Internal@Windows@@AEAAJPEBG00PEAPEAG@Z; Windows::Internal::Storage::Cloud::CloudStoreCache::GetCurrentBulkLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18007e1c3  mov     rcx, [rbp+40h]; this
0x18007e1c7  test    eax, eax
0x18007e1c9  js      loc_18007E2D7
0x18007e1cf  lea     rcx, [rbp+var_38]
0x18007e1d3  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18007e1d8  mov     [rbp+var_38], 2
0x18007e1df  mov     rax, [rbp+arg_30]
0x18007e1e3  mov     qword ptr [rbp+var_38+4], rax
0x18007e1e7  mov     dword ptr [rbp+var_30+4], ebx
0x18007e1ea  mov     rcx, [rsi+10h]
0x18007e1ee  mov     rax, [rcx]
0x18007e1f1  lea     edx, [rdi+10h]
0x18007e1f4  mov     rax, [rax+18h]
0x18007e1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e1fd  test    eax, eax
0x18007e1ff  js      loc_18007E2F0
0x18007e205  mov     dword ptr [rsp+78h+Size], edi; Size
0x18007e209  mov     [rsp+78h+Src], r13; Src
0x18007e20e  lea     rax, [rbp+var_38]
0x18007e212  mov     [rsp+78h+var_58], rax; int
0x18007e217  mov     r9, r14; unsigned __int16 *
0x18007e21a  mov     r8, r15; unsigned __int16 *
0x18007e21d  mov     rdx, r12; unsigned __int16 *
0x18007e220  mov     rcx, rsi; this
0x18007e223  call    ?SaveToDefaultLocalStorage@CloudStoreCache@Cloud@Storage@Internal@Windows@@AEAAJPEBG00PEAVCloudStoreMetadata@2345@PEAEK@Z; Windows::Internal::Storage::Cloud::CloudStoreCache::SaveToDefaultLocalStorage(ushort const *,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreMetadata *,uchar *,ulong)
0x18007e228  mov     ebx, eax
0x18007e22a  test    eax, eax
0x18007e22c  jns     short loc_18007E269
0x18007e22e  mov     rcx, [rbp+40h]; this
0x18007e232  mov     r9d, eax; char *
0x18007e235  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007e23c  mov     edx, 85h; void *
0x18007e241  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e246  nop
0x18007e247  mov     rcx, [rbp+pv]; pv
0x18007e24b  test    rcx, rcx
0x18007e24e  jz      short loc_18007E256
0x18007e250  call    cs:__imp_CoTaskMemFree
0x18007e256  mov     eax, ebx
0x18007e258  add     rsp, 78h
0x18007e25c  pop     r15
0x18007e25e  pop     r14
0x18007e260  pop     r13
0x18007e262  pop     r12
0x18007e264  pop     rdi
0x18007e265  pop     rsi
0x18007e266  pop     rbx
0x18007e267  pop     rbp
0x18007e268  retn
0x18007e269  mov     rcx, [rbp+pv]; pv
0x18007e26d  test    rcx, rcx
0x18007e270  jnz     short loc_18007E288
0x18007e272  test    rcx, rcx
0x18007e275  jz      short loc_18007E27D
0x18007e277  call    cs:__imp_CoTaskMemFree
0x18007e27d  xor     eax, eax
0x18007e27f  jmp     short loc_18007E258
0x18007e281  mov     al, 1
0x18007e283  jmp     loc_18007E189
0x18007e288  mov     r10, [rsi+18h]
0x18007e28c  mov     rax, [r10]
0x18007e28f  mov     [rsp+78h+var_58], rcx; int
0x18007e294  mov     r9, r14
0x18007e297  mov     r8, r15
0x18007e29a  mov     rdx, r12
0x18007e29d  mov     rcx, r10
0x18007e2a0  mov     rax, [rax+38h]
0x18007e2a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e2a9  mov     rcx, [rbp+40h]; this
0x18007e2ad  test    eax, eax
0x18007e2af  js      loc_18007E40E
0x18007e2b5  mov     rcx, [rbp+pv]
0x18007e2b9  jmp     short loc_18007E272
0x18007e2bb  mov     r9d, 80070570h; char *
0x18007e2c1  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007e2c8  mov     edx, 74h ; 't'; void *
0x18007e2cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007e2d2  jmp     loc_18007E195
0x18007e2d7  mov     r9d, eax; char *
0x18007e2da  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007e2e1  mov     edx, 79h ; 'y'; void *
0x18007e2e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007e2eb  jmp     loc_18007E1CF
0x18007e2f0  mov     rcx, [rsi+18h]
0x18007e2f4  mov     rax, [rcx]
0x18007e2f7  mov     edx, edi
0x18007e2f9  mov     rax, [rax+18h]
0x18007e2fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e302  mov     ebx, eax
0x18007e304  test    eax, eax
0x18007e306  jns     short loc_18007E325
0x18007e308  mov     rcx, [rbp+40h]; this
0x18007e30c  mov     r9d, eax; char *
0x18007e30f  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007e316  mov     edx, 8Ah; void *
0x18007e31b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e320  jmp     loc_18007E3F2
0x18007e325  mov     [rbp+arg_30], 0
0x18007e32d  mov     rcx, [rsi+18h]
0x18007e331  mov     rax, [rcx]
0x18007e334  lea     rdx, [rbp+arg_30]
0x18007e338  mov     [rbp+var_20], rdx
0x18007e33c  mov     [rbp+var_18], 0
0x18007e344  mov     [rbp+var_10], 1
0x18007e348  lea     rdx, [rbp+var_18]
0x18007e34c  mov     [rsp+78h+Size], rdx
0x18007e351  mov     dword ptr [rsp+78h+Src], edi
0x18007e355  mov     [rsp+78h+var_58], r13
0x18007e35a  mov     r9, r14
0x18007e35d  mov     r8, r15
0x18007e360  mov     rdx, r12
0x18007e363  mov     rax, [rax+30h]
0x18007e367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e36c  mov     ebx, eax
0x18007e36e  lea     rcx, [rbp+var_20]
0x18007e372  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18007e377  xor     edi, edi
0x18007e379  test    ebx, ebx
0x18007e37b  jns     short loc_18007E387
0x18007e37d  mov     r9d, ebx
0x18007e380  mov     edx, 90h
0x18007e385  jmp     short loc_18007E3D7
0x18007e387  mov     dword ptr [rbp+var_30+4], 1
0x18007e38e  mov     rax, [rbp+arg_30]
0x18007e392  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007e396  inc     rcx
0x18007e399  cmp     [rax+rcx*2], di
0x18007e39d  jnz     short loc_18007E396
0x18007e39f  lea     ecx, ds:2[rcx*2]
0x18007e3a6  mov     dword ptr [rsp+78h+Size], ecx; Size
0x18007e3aa  mov     [rsp+78h+Src], rax; Src
0x18007e3af  lea     rax, [rbp+var_38]
0x18007e3b3  mov     [rsp+78h+var_58], rax; int
0x18007e3b8  mov     r9, r14; unsigned __int16 *
0x18007e3bb  mov     r8, r15; unsigned __int16 *
0x18007e3be  mov     rdx, r12; unsigned __int16 *
0x18007e3c1  mov     rcx, rsi; this
0x18007e3c4  call    ?SaveToDefaultLocalStorage@CloudStoreCache@Cloud@Storage@Internal@Windows@@AEAAJPEBG00PEAVCloudStoreMetadata@2345@PEAEK@Z; Windows::Internal::Storage::Cloud::CloudStoreCache::SaveToDefaultLocalStorage(ushort const *,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreMetadata *,uchar *,ulong)
0x18007e3c9  mov     ebx, eax
0x18007e3cb  test    eax, eax
0x18007e3cd  jns     short loc_18007E400
0x18007e3cf  mov     r9d, eax; char *
0x18007e3d2  mov     edx, 96h; void *
0x18007e3d7  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007e3de  mov     rcx, [rbp+40h]; this
0x18007e3e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e3e7  nop
0x18007e3e8  lea     rcx, [rbp+arg_30]
0x18007e3ec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007e3f1  nop
0x18007e3f2  lea     rcx, [rbp+pv]
0x18007e3f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007e3fb  jmp     loc_18007E256
0x18007e400  lea     rcx, [rbp+arg_30]
0x18007e404  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007e409  jmp     loc_18007E269
0x18007e40e  mov     r9d, eax; char *
0x18007e411  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18007e418  mov     edx, 9Ch; void *
0x18007e41d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007e422  jmp     loc_18007E2B5
```
