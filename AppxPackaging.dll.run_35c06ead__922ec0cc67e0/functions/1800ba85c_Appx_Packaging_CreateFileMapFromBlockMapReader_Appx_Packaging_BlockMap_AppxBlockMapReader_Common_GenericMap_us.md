# Appx::Packaging::CreateFileMapFromBlockMapReader(Appx::Packaging::BlockMap::AppxBlockMapReader *,Common::GenericMap<ushort const *,ushort const *> * *)

- ea: `0x1800ba85c`
- end: `0x1800baa3a`
- name: `?CreateFileMapFromBlockMapReader@Packaging@Appx@@YAJPEAVAppxBlockMapReader@BlockMap@12@PEAPEAV?$GenericMap@PEBGPEBG@Common@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c021c`
- `0x1800c0f54`

## callees

- `0x1800133fc`
- `0x18004a064`
- `0x18004ccd0`
- `0x18004cf84`
- `0x18004ec7c`
- `0x180074678`
- `0x1800992d0`
- `0x1800ac590`
- `0x1800ac600`
- `0x1800b7234`
- `0x1800ba85c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba980`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba9c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba980`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba9c2`

## string_xrefs

- `0x1800ba8ea`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800ba969`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800ba9aa`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800baa0b`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::CreateFileMapFromBlockMapReader(__int64 a1, _QWORD *a2)
{
  void *v4; // rax
  __int64 v5; // rdx
  void *v6; // rdi
  unsigned int FilesInternal; // ebx
  __int64 v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  void *v11; // rbx
  int v12; // eax
  unsigned int v13; // esi
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 *v17; // [rsp+20h] [rbp-20h] BYREF
  __int64 v18; // [rsp+28h] [rbp-18h] BYREF
  char v19; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v21; // [rsp+70h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF

  v4 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4
    || (v6 = (void *)Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMap<unsigned short const *,unsigned short const *>(
                       v4,
                       v5,
                       Appx::Packaging::SafeCoTaskMemFree<unsigned char>,
                       0)) == 0 )
  {
    FilesInternal = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x624,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)0x8007000ELL,
      (int)v17);
    return FilesInternal;
  }
  v21 = 0;
  v17 = &v21;
  v18 = 0;
  v19 = 1;
  FilesInternal = Appx::Packaging::BlockMap::AppxBlockMapReader::GetFilesInternal(a1, &v18);
  wil::details::out_param_t<wistd::unique_ptr<Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>,wistd::default_delete<Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>>>::~out_param_t<wistd::unique_ptr<Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>,wistd::default_delete<Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>>>(&v17);
  if ( (FilesInternal & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x627,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)FilesInternal,
      (int)v17);
LABEL_13:
    v15 = v21;
    v21 = 0;
    if ( v15 )
      Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'(v15);
LABEL_15:
    Common::GenericMap<unsigned short const *,unsigned short const *>::`scalar deleting destructor'(v6);
    return FilesInternal;
  }
  while ( 1 )
  {
    v8 = v21;
    if ( !*(_BYTE *)(v21 + 24) )
      break;
    v9 = *(_QWORD *)(v21 + 16);
    pv = 0;
    v10 = Appx::Packaging::CoTaskMemHelper::CopyString(
            *(const unsigned __int16 **)(*(_QWORD *)(v9 + 8) + 56LL),
            (unsigned __int16 **)&pv);
    FilesInternal = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v10,
        (int)v17);
      CoTaskMemFree(pv);
      goto LABEL_13;
    }
    v11 = pv;
    v12 = Common::GenericMap<unsigned short const *,unsigned short const *>::Insert(v6, pv, pv);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62E,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v12,
        (int)v17);
      CoTaskMemFree(v11);
      v14 = v21;
      v21 = 0;
      if ( v14 )
        Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'(v14);
      FilesInternal = v13;
      goto LABEL_15;
    }
    Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::MoveNext(v21);
    CoTaskMemFree(0);
  }
  *a2 = v6;
  v21 = 0;
  if ( v8 )
    Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'(v8);
  return 0;
}

```

## disassembly

```asm
0x1800ba85c  mov     [rsp-18h+arg_0], rbx
0x1800ba861  mov     [rsp-18h+arg_8], rsi
0x1800ba866  push    rbp
0x1800ba867  push    rdi
0x1800ba868  push    r14
0x1800ba86a  mov     rbp, rsp
0x1800ba86d  sub     rsp, 40h
0x1800ba871  mov     r14, rdx
0x1800ba874  mov     rbx, rcx
0x1800ba877  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ba87e  mov     ecx, 78h ; 'x'; unsigned __int64
0x1800ba883  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ba888  test    rax, rax
0x1800ba88b  jz      loc_1800BAA07
0x1800ba891  xor     r9d, r9d
0x1800ba894  lea     r8, ??$SafeCoTaskMemFree@E@Packaging@Appx@@YAXPEAE@Z; Appx::Packaging::SafeCoTaskMemFree<uchar>(uchar *)
0x1800ba89b  mov     rcx, rax
0x1800ba89e  call    ??0?$GenericMap@PEBGPEBG@Common@@QEAA@P6A?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@ZP6AXPEBG@Z4@Z; Common::GenericMap<ushort const *,ushort const *>::GenericMap<ushort const *,ushort const *>(_RTL_GENERIC_COMPARE_RESULTS (*)(_RTL_AVL_TABLE *,void *,void *),void (*)(ushort const *),void (*)(ushort const *))
0x1800ba8a3  mov     rdi, rax
0x1800ba8a6  test    rax, rax
0x1800ba8a9  jz      loc_1800BAA07
0x1800ba8af  lea     rax, [rbp+arg_10]
0x1800ba8b3  mov     [rbp+arg_10], 0
0x1800ba8bb  lea     rdx, [rbp+var_18]
0x1800ba8bf  mov     [rbp+var_20], rax
0x1800ba8c3  mov     rcx, rbx
0x1800ba8c6  mov     [rbp+var_18], 0
0x1800ba8ce  mov     [rbp+var_10], 1
0x1800ba8d2  call    ?GetFilesInternal@AppxBlockMapReader@BlockMap@Packaging@Appx@@QEAAJPEAPEAV?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@34@@Z; Appx::Packaging::BlockMap::AppxBlockMapReader::GetFilesInternal(Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *> * *)
0x1800ba8d7  lea     rcx, [rbp+var_20]
0x1800ba8db  mov     ebx, eax
0x1800ba8dd  call    ??1?$out_param_t@V?$unique_ptr@V?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@Packaging@Appx@@U?$default_delete@V?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@Packaging@Appx@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>,wistd::default_delete<Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>>>::~out_param_t<wistd::unique_ptr<Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>,wistd::default_delete<Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>>>(void)
0x1800ba8e2  test    ebx, ebx
0x1800ba8e4  jns     short loc_1800BA903
0x1800ba8e6  mov     rcx, [rbp+18h]; this
0x1800ba8ea  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800ba8f1  mov     r9d, ebx; char *
0x1800ba8f4  mov     edx, 627h; void *
0x1800ba8f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba8fe  jmp     loc_1800BA9CE
0x1800ba903  mov     rcx, [rbp+arg_10]
0x1800ba907  cmp     byte ptr [rcx+18h], 0
0x1800ba90b  jz      loc_1800BA9EE
0x1800ba911  mov     rax, [rcx+10h]
0x1800ba915  lea     rdx, [rbp+pv]; unsigned __int16 **
0x1800ba919  mov     [rbp+pv], 0
0x1800ba921  mov     rcx, [rax+8]
0x1800ba925  mov     rcx, [rcx+38h]; Src
0x1800ba929  call    ?CopyString@CoTaskMemHelper@Packaging@Appx@@SAJPEBGPEAPEAG@Z; Appx::Packaging::CoTaskMemHelper::CopyString(ushort const *,ushort * *)
0x1800ba92e  mov     ebx, eax
0x1800ba930  test    eax, eax
0x1800ba932  js      short loc_1800BA9A6
0x1800ba934  mov     rbx, [rbp+pv]
0x1800ba938  mov     rcx, rdi
0x1800ba93b  mov     r8, rbx
0x1800ba93e  mov     rdx, rbx
0x1800ba941  call    ?Insert@?$GenericMap@PEBGPEBG@Common@@QEAAJPEBG0@Z; Common::GenericMap<ushort const *,ushort const *>::Insert(ushort const *,ushort const *)
0x1800ba946  mov     esi, eax
0x1800ba948  test    eax, eax
0x1800ba94a  js      short loc_1800BA965
0x1800ba94c  mov     rcx, [rbp+arg_10]
0x1800ba950  call    ?MoveNext@?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@Packaging@Appx@@QEAA_NXZ; Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::MoveNext(void)
0x1800ba955  xor     ecx, ecx; pv
0x1800ba957  call    cs:__imp_CoTaskMemFree
0x1800ba95e  nop     dword ptr [rax+rax+00h]
0x1800ba963  jmp     short loc_1800BA903
0x1800ba965  mov     rcx, [rbp+18h]; this
0x1800ba969  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800ba970  mov     r9d, esi; char *
0x1800ba973  mov     edx, 62Eh; void *
0x1800ba978  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba97d  mov     rcx, rbx; pv
0x1800ba980  call    cs:__imp_CoTaskMemFree
0x1800ba987  nop     dword ptr [rax+rax+00h]
0x1800ba98c  mov     rcx, [rbp+arg_10]
0x1800ba990  mov     [rbp+arg_10], 0
0x1800ba998  test    rcx, rcx
0x1800ba99b  jz      short loc_1800BA9A2
0x1800ba99d  call    ??_G?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'(uint)
0x1800ba9a2  mov     ebx, esi
0x1800ba9a4  jmp     short loc_1800BA9E4
0x1800ba9a6  mov     rcx, [rbp+18h]; this
0x1800ba9aa  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800ba9b1  mov     r9d, eax; char *
0x1800ba9b4  mov     edx, 62Dh; void *
0x1800ba9b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba9be  mov     rcx, [rbp+pv]; pv
0x1800ba9c2  call    cs:__imp_CoTaskMemFree
0x1800ba9c9  nop     dword ptr [rax+rax+00h]
0x1800ba9ce  mov     rcx, [rbp+arg_10]
0x1800ba9d2  mov     [rbp+arg_10], 0
0x1800ba9da  test    rcx, rcx
0x1800ba9dd  jz      short loc_1800BA9E4
0x1800ba9df  call    ??_G?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'(uint)
0x1800ba9e4  mov     rcx, rdi; void *
0x1800ba9e7  call    ??_G?$GenericMap@PEBGPEBG@Common@@QEAAPEAXI@Z; Common::GenericMap<ushort const *,ushort const *>::`scalar deleting destructor'(uint)
0x1800ba9ec  jmp     short loc_1800BAA24
0x1800ba9ee  mov     [r14], rdi
0x1800ba9f1  mov     [rbp+arg_10], 0
0x1800ba9f9  test    rcx, rcx
0x1800ba9fc  jz      short loc_1800BAA03
0x1800ba9fe  call    ??_G?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'(uint)
0x1800baa03  xor     eax, eax
0x1800baa05  jmp     short loc_1800BAA26
0x1800baa07  mov     rcx, [rbp+18h]; this
0x1800baa0b  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800baa12  mov     ebx, 8007000Eh
0x1800baa17  mov     edx, 624h; void *
0x1800baa1c  mov     r9d, ebx; char *
0x1800baa1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800baa24  mov     eax, ebx
0x1800baa26  mov     rbx, [rsp+40h+arg_0]
0x1800baa2b  mov     rsi, [rsp+40h+arg_8]
0x1800baa30  add     rsp, 40h
0x1800baa34  pop     r14
0x1800baa36  pop     rdi
0x1800baa37  pop     rbp
0x1800baa38  retn
```
