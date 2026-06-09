# InstalledFontFileEnumerator::EnumerateRegistry(std::vector<InstalledFontFileEnumerator::LocalFileInfo,std::allocator<InstalledFontFileEnumerator::LocalFileInfo>> &,std::vector<DWrite::RefString,std::allocator<DWrite::RefString>> &,InstalledFontChangeInfo *)

- ea: `0x180069df8`
- end: `0x18006a1b9`
- name: `?EnumerateRegistry@InstalledFontFileEnumerator@@AEAAXAEAV?$vector@ULocalFileInfo@InstalledFontFileEnumerator@@V?$allocator@ULocalFileInfo@InstalledFontFileEnumerator@@@std@@@std@@AEAV?$vector@VRefString@DWrite@@V?$allocator@VRefString@DWrite@@@std@@@3@PEAUInstalledFontChangeInfo@@@Z`
- size: `961`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update`

## callers

- `0x18000fb80`

## callees

- `0x1800092f8`
- `0x180009784`
- `0x18000aca0`
- `0x180024c5c`
- `0x180024ca0`
- `0x180028c50`
- `0x18002bf90`
- `0x180069df8`
- `0x18006a1c0`
- `0x18006a274`
- `0x18006ab30`
- `0x18006ab6c`
- `0x18009732c`
- `0x18009b3d8`
- `0x18009d96c`
- `0x1800a33f4`
- `0x1800aa650`
- `0x1800b6398`
- `0x1800b8918`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a009`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a0d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a0e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a009`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a0d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a0e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall InstalledFontFileEnumerator::EnumerateRegistry(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  __int64 v8; // rbx
  HKEY v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  HKEY v12; // rcx
  __int64 v13; // rax
  const wchar_t *v14; // rcx
  unsigned __int64 v15; // rdx
  struct DWrite::RefString::Data *v16; // rsi
  HKEY v17; // rax
  void **v18; // rbx
  _QWORD *v19; // rdx
  const WCHAR *v20; // r10
  void *v21; // r8
  unsigned __int64 v22; // rdx
  __int64 v23; // rax
  _QWORD *v24; // rdx
  HKEY v25; // rcx
  int v26; // [rsp+30h] [rbp-79h]
  HKEY v27; // [rsp+40h] [rbp-69h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-61h] BYREF
  struct DWrite::RefString::Data *v29; // [rsp+50h] [rbp-59h] BYREF
  __int128 v30; // [rsp+58h] [rbp-51h] BYREF
  __int128 v31; // [rsp+68h] [rbp-41h]
  _BYTE v32[16]; // [rsp+78h] [rbp-31h] BYREF
  _QWORD v33[4]; // [rsp+88h] [rbp-21h] BYREF
  _BYTE v34[32]; // [rsp+A8h] [rbp-1h] BYREF

  v8 = *(_QWORD *)(a1 + 40);
  hKey = 0;
  v9 = (HKEY)RegistryKey::RegistryHiveToHkey(*(unsigned int *)(a1 + 32));
  OpenKey(v9, (const WCHAR *)(v8 + 8), 1, &hKey);
  v12 = hKey;
  if ( !hKey )
  {
    if ( !a4 )
      goto LABEL_10;
    v13 = *(_QWORD *)(a1 + 40);
    v14 = (const wchar_t *)(v13 + 8);
    v15 = *(unsigned int *)(v13 + 4);
    do
    {
      if ( !v15 )
        break;
      --v15;
    }
    while ( v14[v15] != 92 );
    v16 = DWrite::RefString::NewData(v14, v15, v10, v11);
    v29 = v16;
    v27 = 0;
    v17 = (HKEY)RegistryKey::RegistryHiveToHkey(*(unsigned int *)(a1 + 32));
    OpenKey(v17, (const WCHAR *)v16 + 4, 1, &v27);
    RegistryKey::operator=(a4, &v27);
    if ( v27 )
    {
      RegCloseKey(v27);
      v27 = 0;
    }
    DWrite::RefString::DecrementRef(v16);
    if ( *(_QWORD *)a4 )
      RegistryKey::ListenForChanges((RegistryKey *)a4, (const struct Event *)(a4 + 8));
    goto LABEL_9;
  }
  if ( a4 )
  {
    RegistryKey::ListenForChanges((RegistryKey *)&hKey, (const struct Event *)(a4 + 8));
    v23 = *(_QWORD *)(a1 + 56);
    if ( *(_DWORD *)(v23 + 4) )
    {
      v24 = (_QWORD *)a3[1];
      if ( v24 == (_QWORD *)a3[2] )
      {
        std::vector<DWrite::RefString>::_Emplace_reallocate<DWrite::RefString>(
          a3,
          (__int64)v24,
          (volatile signed __int32 **)(a1 + 56));
      }
      else
      {
        *v24 = v23;
        _InterlockedIncrement((volatile signed __int32 *)v23);
        a3[1] += 8LL;
      }
    }
  }
  v27 = (HKEY)&DWrite::RefString::empty_;
  InstalledFontFileEnumerator::EnumKey(a1, (unsigned int)&hKey, (unsigned int)&v27, a2, (__int64)a3, a4);
  DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)v27);
  if ( *(_BYTE *)(a1 + 48) )
  {
    RegistryKeyIterator::RegistryKeyIterator((RegistryKeyIterator *)v32, (const struct RegistryKey *)&hKey);
    while ( RegistryKeyIterator::Advance((RegistryKeyIterator *)v32) )
    {
      v30 = 0;
      v31 = 0;
      v19 = v33;
      if ( v33[3] > 7u )
        v19 = (_QWORD *)v33[0];
      std::wstring::_Construct<2,wchar_t const *>(&v30, v19, v33[2]);
      v20 = (const WCHAR *)&v30;
      v21 = (void *)v30;
      v22 = *((_QWORD *)&v31 + 1);
      if ( *((_QWORD *)&v31 + 1) > 7u )
        v20 = (const WCHAR *)v30;
      v25 = 0;
      v27 = 0;
      if ( hKey )
      {
        OpenKey(hKey, v20, 1, &v27);
        v25 = v27;
        v22 = *((_QWORD *)&v31 + 1);
        v21 = (void *)v30;
      }
      if ( v22 > 7 )
      {
        std::_Deallocate<16>(v21, 2 * v22 + 2);
        v25 = v27;
      }
      if ( v25 )
      {
        std::wstring::wstring(v34, v33);
        DWrite::RefString::RefString(&v29, v34);
        InstalledFontFileEnumerator::EnumKey(a1, (unsigned int)&v27, (unsigned int)&v29, a2, (__int64)a3, a4);
        DWrite::RefString::DecrementRef(v29);
        std::wstring::_Tidy_deallocate(v34);
        v25 = v27;
      }
      if ( v25 )
      {
        RegCloseKey(v25);
        v27 = 0;
      }
    }
    std::wstring::_Tidy_deallocate(v33);
  }
  else if ( *(_DWORD *)(*(_QWORD *)(a1 + 56) + 4LL) )
  {
    v29 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
    InstalledFontFileEnumerator::AddFileInfo(a1, &v29, L"MARLETT.TTF", a2, a3, a4, 0);
    DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)&DWrite::RefString::empty_);
    v18 = (void **)off_1800E81E0;
    do
    {
      v29 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
      LOBYTE(v26) = 1;
      InstalledFontFileEnumerator::AddFileInfo(a1, &v29, *v18, a2, a3, a4, v26);
      DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)&DWrite::RefString::empty_);
      ++v18;
    }
    while ( v18 != &SessionFontSetManager::`vftable' );
  }
  if ( !a4 || &hKey == (HKEY *)a4 )
  {
LABEL_9:
    v12 = hKey;
    goto LABEL_10;
  }
  RegistryKey::Close((RegistryKey *)a4);
  *(_QWORD *)a4 = hKey;
  v12 = 0;
  hKey = 0;
LABEL_10:
  if ( v12 )
    RegCloseKey(v12);
}

```

## disassembly

```asm
0x180069df8  push    rbp
0x180069dfa  push    rbx
0x180069dfb  push    rsi
0x180069dfc  push    rdi
0x180069dfd  push    r13
0x180069dff  push    r14
0x180069e01  push    r15
0x180069e03  lea     rbp, [rsp-27h]
0x180069e08  sub     rsp, 0D0h
0x180069e0f  mov     rax, cs:__security_cookie
0x180069e16  xor     rax, rsp
0x180069e19  mov     [rbp+57h+var_38], rax
0x180069e1d  mov     rdi, r9
0x180069e20  mov     rsi, r8
0x180069e23  mov     r15, rdx
0x180069e26  mov     r14, rcx
0x180069e29  mov     rbx, [rcx+28h]
0x180069e2d  mov     [rbp+57h+hKey], 0
0x180069e35  mov     ecx, [rcx+20h]
0x180069e38  call    ?RegistryHiveToHkey@RegistryKey@@SAPEAUHKEY__@@W4RegistryHive@@@Z; RegistryKey::RegistryHiveToHkey(RegistryHive)
0x180069e3d  mov     rcx, rax
0x180069e40  lea     r9, [rbp+57h+hKey]
0x180069e44  mov     r8d, 1
0x180069e4a  lea     rdx, [rbx+8]
0x180069e4e  call    ?OpenKey@@YAJPEAUHKEY__@@PEB_WW4Allow@RegistryKey@@PEAPEAU1@@Z; OpenKey(HKEY__ *,wchar_t const *,RegistryKey::Allow,HKEY__ * *)
0x180069e53  nop
0x180069e54  mov     rcx, [rbp+57h+hKey]
0x180069e58  test    rcx, rcx
0x180069e5b  jnz     loc_180069F03
0x180069e61  test    rdi, rdi
0x180069e64  jz      short loc_180069EDC
0x180069e66  mov     rax, [r14+28h]
0x180069e6a  lea     rcx, [rax+8]; Src
0x180069e6e  mov     edx, [rax+4]; unsigned __int64
0x180069e71  test    rdx, rdx
0x180069e74  jnz     loc_18006A131
0x180069e7a  call    ?NewData@RefString@DWrite@@CAPEAUData@12@PEB_W_K@Z; DWrite::RefString::NewData(wchar_t const *,unsigned __int64)
0x180069e7f  mov     rsi, rax
0x180069e82  mov     [rbp+57h+var_B0], rax
0x180069e86  mov     [rbp+57h+var_C0], 0
0x180069e8e  mov     ecx, [r14+20h]
0x180069e92  call    ?RegistryHiveToHkey@RegistryKey@@SAPEAUHKEY__@@W4RegistryHive@@@Z; RegistryKey::RegistryHiveToHkey(RegistryHive)
0x180069e97  mov     rcx, rax
0x180069e9a  lea     r9, [rbp+57h+var_C0]
0x180069e9e  mov     r8d, 1
0x180069ea4  lea     rdx, [rsi+8]
0x180069ea8  call    ?OpenKey@@YAJPEAUHKEY__@@PEB_WW4Allow@RegistryKey@@PEAPEAU1@@Z; OpenKey(HKEY__ *,wchar_t const *,RegistryKey::Allow,HKEY__ * *)
0x180069ead  lea     rdx, [rbp+57h+var_C0]
0x180069eb1  mov     rcx, rdi
0x180069eb4  call    ??4RegistryKey@@QEAAAEAV0@$$QEAV0@@Z; RegistryKey::operator=(RegistryKey &&)
0x180069eb9  mov     rcx, [rbp+57h+var_C0]; hKey
0x180069ebd  test    rcx, rcx
0x180069ec0  jnz     loc_18006A0D3
0x180069ec6  mov     rcx, rsi; struct DWrite::RefString::Data *
0x180069ec9  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180069ece  cmp     qword ptr [rdi], 0
0x180069ed2  jnz     loc_18006A144
0x180069ed8  mov     rcx, [rbp+57h+hKey]; hKey
0x180069edc  test    rcx, rcx
0x180069edf  jnz     loc_18006A009
0x180069ee5  mov     rcx, [rbp+57h+var_38]
0x180069ee9  xor     rcx, rsp; StackCookie
0x180069eec  call    __security_check_cookie
0x180069ef1  add     rsp, 0D0h
0x180069ef8  pop     r15
0x180069efa  pop     r14
0x180069efc  pop     r13
0x180069efe  pop     rdi
0x180069eff  pop     rsi
0x180069f00  pop     rbx
0x180069f01  pop     rbp
0x180069f02  retn
0x180069f03  test    rdi, rdi
0x180069f06  jnz     loc_18006A0F9
0x180069f0c  lea     r13, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x180069f13  mov     [rbp+57h+var_C0], r13
0x180069f17  mov     [rsp+100h+var_D8], rdi
0x180069f1c  mov     [rsp+100h+var_E0], rsi
0x180069f21  mov     r9, r15
0x180069f24  lea     r8, [rbp+57h+var_C0]
0x180069f28  lea     rdx, [rbp+57h+hKey]
0x180069f2c  mov     rcx, r14
0x180069f2f  call    ?EnumKey@InstalledFontFileEnumerator@@AEAAXAEBVRegistryKey@@AEBVRefString@DWrite@@AEAV?$vector@ULocalFileInfo@InstalledFontFileEnumerator@@V?$allocator@ULocalFileInfo@InstalledFontFileEnumerator@@@std@@@std@@AEAV?$vector@VRefString@DWrite@@V?$allocator@VRefString@DWrite@@@std@@@6@PEAUInstalledFontChangeInfo@@@Z; InstalledFontFileEnumerator::EnumKey(RegistryKey const &,DWrite::RefString const &,std::vector<InstalledFontFileEnumerator::LocalFileInfo> &,std::vector<DWrite::RefString> &,InstalledFontChangeInfo *)
0x180069f34  nop
0x180069f35  mov     rcx, [rbp+57h+var_C0]; struct DWrite::RefString::Data *
0x180069f39  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180069f3e  cmp     byte ptr [r14+30h], 0
0x180069f43  jnz     loc_18006A014
0x180069f49  mov     rax, [r14+38h]
0x180069f4d  cmp     dword ptr [rax+4], 0
0x180069f51  jz      loc_180069FD9
0x180069f57  mov     [rbp+57h+var_B0], r13
0x180069f5b  mov     byte ptr [rsp+100h+var_D0], 0
0x180069f60  mov     [rsp+100h+var_D8], rdi
0x180069f65  mov     [rsp+100h+var_E0], rsi
0x180069f6a  mov     r9, r15
0x180069f6d  lea     r8, aMarlettTtf; "MARLETT.TTF"
0x180069f74  lea     rdx, [rbp+57h+var_B0]
0x180069f78  mov     rcx, r14
0x180069f7b  call    ?AddFileInfo@InstalledFontFileEnumerator@@AEAAXAEBVRefString@DWrite@@PEB_WAEAV?$vector@ULocalFileInfo@InstalledFontFileEnumerator@@V?$allocator@ULocalFileInfo@InstalledFontFileEnumerator@@@std@@@std@@AEAV?$vector@VRefString@DWrite@@V?$allocator@VRefString@DWrite@@@std@@@5@PEAUInstalledFontChangeInfo@@_N@Z; InstalledFontFileEnumerator::AddFileInfo(DWrite::RefString const &,wchar_t const *,std::vector<InstalledFontFileEnumerator::LocalFileInfo> &,std::vector<DWrite::RefString> &,InstalledFontChangeInfo *,bool)
0x180069f80  nop
0x180069f81  mov     rcx, r13; struct DWrite::RefString::Data *
0x180069f84  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180069f89  lea     rbx, off_1800E81E0; "ARIAL.TTF"
0x180069f90  mov     [rbp+57h+var_B0], r13
0x180069f94  mov     byte ptr [rsp+100h+var_D0], 1
0x180069f99  mov     [rsp+100h+var_D8], rdi
0x180069f9e  mov     [rsp+100h+var_E0], rsi
0x180069fa3  mov     r9, r15
0x180069fa6  mov     r8, [rbx]
0x180069fa9  lea     rdx, [rbp+57h+var_B0]
0x180069fad  mov     rcx, r14
0x180069fb0  call    ?AddFileInfo@InstalledFontFileEnumerator@@AEAAXAEBVRefString@DWrite@@PEB_WAEAV?$vector@ULocalFileInfo@InstalledFontFileEnumerator@@V?$allocator@ULocalFileInfo@InstalledFontFileEnumerator@@@std@@@std@@AEAV?$vector@VRefString@DWrite@@V?$allocator@VRefString@DWrite@@@std@@@5@PEAUInstalledFontChangeInfo@@_N@Z; InstalledFontFileEnumerator::AddFileInfo(DWrite::RefString const &,wchar_t const *,std::vector<InstalledFontFileEnumerator::LocalFileInfo> &,std::vector<DWrite::RefString> &,InstalledFontChangeInfo *,bool)
0x180069fb5  nop
0x180069fb6  mov     rcx, r13; struct DWrite::RefString::Data *
0x180069fb9  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180069fbe  add     rbx, 8
0x180069fc2  lea     rax, ??_7SessionFontSetManager@@6B@; const SessionFontSetManager::`vftable'
0x180069fc9  cmp     rbx, rax
0x180069fcc  jnz     short loc_180069F90
0x180069fce  jmp     short loc_180069FD9
0x180069fd0  lea     rcx, [rbp+57h+var_78]; void *
0x180069fd4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180069fd9  test    rdi, rdi
0x180069fdc  jz      loc_180069ED8
0x180069fe2  lea     rax, [rbp+57h+hKey]
0x180069fe6  cmp     rax, rdi
0x180069fe9  jz      loc_180069ED8
0x180069fef  mov     rcx, rdi; this
0x180069ff2  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x180069ff7  mov     rax, [rbp+57h+hKey]
0x180069ffb  mov     [rdi], rax
0x180069ffe  xor     ecx, ecx
0x18006a000  mov     [rbp+57h+hKey], rcx
0x18006a004  jmp     loc_180069EDC
0x18006a009  call    cs:__imp_RegCloseKey
0x18006a00f  jmp     loc_180069EE5
0x18006a014  lea     rdx, [rbp+57h+hKey]; struct RegistryKey *
0x18006a018  lea     rcx, [rbp+57h+var_88]; this
0x18006a01c  call    ??0RegistryKeyIterator@@QEAA@AEBVRegistryKey@@@Z; RegistryKeyIterator::RegistryKeyIterator(RegistryKey const &)
0x18006a021  nop
0x18006a022  jmp     short loc_18006A036
0x18006a024  test    rcx, rcx
0x18006a027  jnz     loc_18006A162
0x18006a02d  test    rcx, rcx
0x18006a030  jnz     loc_18006A0E6
0x18006a036  lea     rcx, [rbp+57h+var_88]; this
0x18006a03a  call    ?Advance@RegistryKeyIterator@@QEAA_NXZ; RegistryKeyIterator::Advance(void)
0x18006a03f  test    al, al
0x18006a041  jz      short loc_180069FD0
0x18006a043  xorps   xmm0, xmm0
0x18006a046  movups  [rbp+57h+var_A8], xmm0
0x18006a04a  xorps   xmm1, xmm1
0x18006a04d  movdqu  [rbp+57h+var_98], xmm1
0x18006a052  lea     rdx, [rbp+57h+var_78]
0x18006a056  cmp     [rbp+57h+var_60], 7
0x18006a05b  cmova   rdx, [rbp+57h+var_78]
0x18006a060  mov     r8, [rbp+57h+var_68]
0x18006a064  lea     rcx, [rbp+57h+var_A8]
0x18006a068  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18006a06d  nop
0x18006a06e  lea     r10, [rbp+57h+var_A8]
0x18006a072  mov     r8, qword ptr [rbp+57h+var_A8]
0x18006a076  mov     rdx, qword ptr [rbp+57h+var_98+8]
0x18006a07a  cmp     rdx, 7
0x18006a07e  cmova   r10, r8
0x18006a082  xor     ecx, ecx
0x18006a084  mov     [rbp+57h+var_C0], rcx
0x18006a088  mov     rax, [rbp+57h+hKey]
0x18006a08c  test    rax, rax
0x18006a08f  jz      short loc_18006A0B0
0x18006a091  lea     r9, [rbp+57h+var_C0]
0x18006a095  lea     r8d, [rcx+1]
0x18006a099  mov     rdx, r10
0x18006a09c  mov     rcx, rax
0x18006a09f  call    ?OpenKey@@YAJPEAUHKEY__@@PEB_WW4Allow@RegistryKey@@PEAPEAU1@@Z; OpenKey(HKEY__ *,wchar_t const *,RegistryKey::Allow,HKEY__ * *)
0x18006a0a4  mov     rcx, [rbp+57h+var_C0]; hKey
0x18006a0a8  mov     rdx, qword ptr [rbp+57h+var_98+8]
0x18006a0ac  mov     r8, qword ptr [rbp+57h+var_A8]
0x18006a0b0  cmp     rdx, 7
0x18006a0b4  jbe     loc_18006A024
0x18006a0ba  lea     rdx, ds:2[rdx*2]
0x18006a0c2  mov     rcx, r8
0x18006a0c5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18006a0ca  mov     rcx, [rbp+57h+var_C0]
0x18006a0ce  jmp     loc_18006A024
0x18006a0d3  call    cs:__imp_RegCloseKey
0x18006a0d9  mov     [rbp+57h+var_C0], 0
0x18006a0e1  jmp     loc_180069EC6
0x18006a0e6  call    cs:__imp_RegCloseKey
0x18006a0ec  mov     [rbp+57h+var_C0], 0
0x18006a0f4  jmp     loc_18006A036
0x18006a0f9  lea     rdx, [rdi+8]; struct Event *
0x18006a0fd  lea     rcx, [rbp+57h+hKey]; this
0x18006a101  call    ?ListenForChanges@RegistryKey@@QEBAXAEBVEvent@@@Z; RegistryKey::ListenForChanges(Event const &)
0x18006a106  lea     r8, [r14+38h]
0x18006a10a  mov     rax, [r8]
0x18006a10d  cmp     dword ptr [rax+4], 0
0x18006a111  jz      loc_180069F0C
0x18006a117  mov     rdx, [rsi+8]
0x18006a11b  cmp     rdx, [rsi+10h]
0x18006a11f  jz      short loc_18006A155
0x18006a121  mov     [rdx], rax
0x18006a124  lock inc dword ptr [rax]
0x18006a127  add     qword ptr [rsi+8], 8
0x18006a12c  jmp     loc_180069F0C
0x18006a131  dec     rdx
0x18006a134  cmp     word ptr [rcx+rdx*2], 5Ch ; '\'
0x18006a139  jnz     loc_180069E71
0x18006a13f  jmp     loc_180069E7A
0x18006a144  lea     rdx, [rdi+8]; struct Event *
0x18006a148  mov     rcx, rdi; this
0x18006a14b  call    ?ListenForChanges@RegistryKey@@QEBAXAEBVEvent@@@Z; RegistryKey::ListenForChanges(Event const &)
0x18006a150  jmp     loc_180069ED8
0x18006a155  mov     rcx, rsi
0x18006a158  call    ??$_Emplace_reallocate@VRefString@DWrite@@@?$vector@VRefString@DWrite@@V?$allocator@VRefString@DWrite@@@std@@@std@@AEAAPEAVRefString@DWrite@@QEAV23@$$QEAV23@@Z; std::vector<DWrite::RefString>::_Emplace_reallocate<DWrite::RefString>(DWrite::RefString * const,DWrite::RefString &&)
0x18006a15d  jmp     loc_180069F0C
0x18006a162  lea     rdx, [rbp+57h+var_78]
0x18006a166  lea     rcx, [rbp+57h+var_58]
0x18006a16a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006a16f  nop
0x18006a170  lea     rdx, [rbp+57h+var_58]
0x18006a174  lea     rcx, [rbp+57h+var_B0]
0x18006a178  call    ??0RefString@DWrite@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; DWrite::RefString::RefString(std::wstring const &)
0x18006a17d  nop
0x18006a17e  mov     [rsp+100h+var_D8], rdi
0x18006a183  mov     [rsp+100h+var_E0], rsi
0x18006a188  mov     r9, r15
0x18006a18b  lea     r8, [rbp+57h+var_B0]
0x18006a18f  lea     rdx, [rbp+57h+var_C0]
0x18006a193  mov     rcx, r14
0x18006a196  call    ?EnumKey@InstalledFontFileEnumerator@@AEAAXAEBVRegistryKey@@AEBVRefString@DWrite@@AEAV?$vector@ULocalFileInfo@InstalledFontFileEnumerator@@V?$allocator@ULocalFileInfo@InstalledFontFileEnumerator@@@std@@@std@@AEAV?$vector@VRefString@DWrite@@V?$allocator@VRefString@DWrite@@@std@@@6@PEAUInstalledFontChangeInfo@@@Z; InstalledFontFileEnumerator::EnumKey(RegistryKey const &,DWrite::RefString const &,std::vector<InstalledFontFileEnumerator::LocalFileInfo> &,std::vector<DWrite::RefString> &,InstalledFontChangeInfo *)
0x18006a19b  nop
0x18006a19c  mov     rcx, [rbp+57h+var_B0]; struct DWrite::RefString::Data *
0x18006a1a0  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18006a1a5  nop
0x18006a1a6  lea     rcx, [rbp+57h+var_58]; void *
0x18006a1aa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006a1af  mov     rcx, [rbp+57h+var_C0]
0x18006a1b3  jmp     loc_18006A02D
```
