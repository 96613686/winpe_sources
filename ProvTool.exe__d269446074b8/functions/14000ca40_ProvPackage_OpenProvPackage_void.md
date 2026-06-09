# ProvPackage::OpenProvPackage(void)

- ea: `0x14000ca40`
- end: `0x14000cd1f`
- name: `?OpenProvPackage@ProvPackage@@UEAA_NXZ`
- size: `735`
- prototype: `char __fastcall(ProvPackage *this, __int64, int, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting`

## callees

- `0x140001008`
- `0x140001098`
- `0x1400010f4`
- `0x140001104`
- `0x140001130`
- `0x140001424`
- `0x1400032e8`
- `0x140008b88`
- `0x140008e50`
- `0x140008f60`
- `0x14000ca40`
- `0x14000dc24`
- `0x14000ded0`
- `0x140010010`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x14000cb08`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x14000cb08`

## pseudocode

```c
char __fastcall ProvPackage::OpenProvPackage(ProvPackage *this, __int64 a2, int a3, int a4)
{
  _QWORD *v5; // rbx
  char *v6; // rax
  _QWORD *v7; // rcx
  int v8; // esi
  _QWORD *v9; // rcx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v14; // ecx
  int v15; // ebx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rcx
  int v21; // r9d
  unsigned int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // r8d
  int v26; // r9d
  unsigned int v27; // eax
  int v28; // [rsp+20h] [rbp-E0h]
  int v29[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  _WORD *v31; // [rsp+40h] [rbp-C0h] BYREF
  _WORD Src[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v5 = (_QWORD *)((char *)this + 8);
  if ( (unsigned int)dword_140017048 > 5 )
  {
    if ( *((_QWORD *)this + 4) < 8u )
      v6 = (char *)this + 8;
    else
      v6 = (char *)*v5;
    *(_QWORD *)v29 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)this,
      (unsigned int)word_14001398A,
      a3,
      a4,
      (__int64)v29);
  }
  if ( !v5[2] )
  {
    if ( (unsigned int)dword_140017048 > 3 )
      tlgWriteTransfer_EventWriteTransfer(&dword_140017048, qword_140013968, 0, 0);
    return 0;
  }
  v30 = 0;
  if ( v5[3] < 8u )
    v7 = v5;
  else
    v7 = (_QWORD *)*v5;
  v8 = OpenProvisioningPackageForRead(v7, &v30);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140017048 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140017048, 0) )
    {
      v29[0] = v8;
      v23 = std::wstring::c_str(v5);
      v24 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v31, v23);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)v29,
        (unsigned int)&dword_14001392C,
        v25,
        v26,
        v24,
        (__int64)v29);
    }
    v27 = wil::verify_hresult<long>((unsigned int)v8);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)v27,
      v28);
  }
  if ( v5[3] < 8u )
    v9 = v5;
  else
    v9 = (_QWORD *)*v5;
  if ( !(unsigned __int8)Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(
                           v9,
                           (char *)this + 112) )
  {
    if ( (unsigned int)dword_140017048 > 2 )
    {
      if ( v5[3] >= 8u )
        v5 = (_QWORD *)*v5;
      *(_QWORD *)v29 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v10,
        (unsigned int)word_1400138EA,
        v11,
        v12,
        (__int64)v29);
    }
    return 0;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, _WORD *, __int64))(*(_QWORD *)v30 + 8LL))(v30, Src, 260);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_140017048 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140017048, 0) )
    {
      v29[0] = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_140017048,
        (unsigned int)&dword_1400138B4,
        0,
        v21,
        (__int64)v29);
    }
    v22 = wil::verify_hresult<long>((unsigned int)v15);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)v22,
      v28);
  }
  if ( (unsigned int)dword_140017048 > 4 )
  {
    v29[0] = v15;
    v31 = Src;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v14,
      (unsigned int)byte_14001387D,
      v16,
      v17,
      (__int64)&v31,
      (__int64)v29);
  }
  if ( Src[0] )
  {
    v18 = -1;
    do
      ++v18;
    while ( Src[v18] );
  }
  std::wstring::assign((char *)this + 72, Src);
  v19 = v30;
  v20 = *((_QWORD *)this + 13);
  if ( v30 != v20 )
  {
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 128LL))(v20);
    *((_QWORD *)this + 13) = v19;
  }
  return 1;
}

```

## disassembly

```asm
0x14000ca40  mov     [rsp-8+arg_8], rbx
0x14000ca45  mov     [rsp-8+arg_10], rsi
0x14000ca4a  push    rbp
0x14000ca4b  push    rdi
0x14000ca4c  push    r14
0x14000ca4e  lea     rbp, [rsp-190h]
0x14000ca56  sub     rsp, 290h
0x14000ca5d  mov     rax, cs:__security_cookie
0x14000ca64  xor     rax, rsp
0x14000ca67  mov     [rbp+1A0h+var_20], rax
0x14000ca6e  mov     rdi, rcx
0x14000ca71  mov     eax, cs:dword_140017048
0x14000ca77  lea     rbx, [rcx+8]
0x14000ca7b  cmp     eax, 5
0x14000ca7e  jbe     short loc_14000CAAA
0x14000ca80  cmp     qword ptr [rbx+18h], 8
0x14000ca85  jb      short loc_14000CA8C
0x14000ca87  mov     rax, [rbx]
0x14000ca8a  jmp     short loc_14000CA8F
0x14000ca8c  mov     rax, rbx
0x14000ca8f  mov     qword ptr [rsp+2A0h+var_270], rax
0x14000ca94  lea     rax, [rsp+2A0h+var_270]
0x14000ca99  mov     qword ptr [rsp+2A0h+var_280], rax
0x14000ca9e  lea     rdx, word_14001398A
0x14000caa5  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14000caaa  xor     r14d, r14d
0x14000caad  cmp     [rbx+10h], r14
0x14000cab1  jnz     short loc_14000CAEF
0x14000cab3  mov     eax, cs:dword_140017048
0x14000cab9  cmp     eax, 3
0x14000cabc  jbe     loc_14000CB64
0x14000cac2  lea     rax, [rsp+2A0h+var_258]
0x14000cac7  mov     [rsp+2A0h+var_278], rax
0x14000cacc  mov     [rsp+2A0h+var_280], 2
0x14000cad4  xor     r9d, r9d
0x14000cad7  xor     r8d, r8d
0x14000cada  lea     rdx, qword_140013968
0x14000cae1  lea     rcx, dword_140017048
0x14000cae8  call    _tlgWriteTransfer_EventWriteTransfer
0x14000caed  jmp     short loc_14000CB64
0x14000caef  mov     [rsp+2A0h+var_268], r14
0x14000caf4  cmp     qword ptr [rbx+18h], 8
0x14000caf9  jb      short loc_14000CB00
0x14000cafb  mov     rcx, [rbx]
0x14000cafe  jmp     short loc_14000CB03
0x14000cb00  mov     rcx, rbx
0x14000cb03  lea     rdx, [rsp+2A0h+var_268]
0x14000cb08  call    cs:__imp_OpenProvisioningPackageForRead
0x14000cb0e  mov     esi, eax
0x14000cb10  test    eax, eax
0x14000cb12  js      loc_14000CCAB
0x14000cb18  cmp     qword ptr [rbx+18h], 8
0x14000cb1d  jb      short loc_14000CB24
0x14000cb1f  mov     rcx, [rbx]
0x14000cb22  jmp     short loc_14000CB27
0x14000cb24  mov     rcx, rbx
0x14000cb27  lea     rdx, [rdi+70h]
0x14000cb2b  call    ?TryCreateProvisioningFileManagerOnPPKG@Provisioning@Management@Internal@Windows@@YA_NPEBGAEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@std@@@Z; Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(ushort const *,std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager> &)
0x14000cb30  test    al, al
0x14000cb32  jnz     short loc_14000CB6B
0x14000cb34  mov     eax, cs:dword_140017048
0x14000cb3a  cmp     eax, 2
0x14000cb3d  jbe     short loc_14000CB64
0x14000cb3f  cmp     qword ptr [rbx+18h], 8
0x14000cb44  jb      short loc_14000CB49
0x14000cb46  mov     rbx, [rbx]
0x14000cb49  mov     qword ptr [rsp+2A0h+var_270], rbx
0x14000cb4e  lea     rax, [rsp+2A0h+var_270]
0x14000cb53  mov     qword ptr [rsp+2A0h+var_280], rax
0x14000cb58  lea     rdx, word_1400138EA
0x14000cb5f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14000cb64  xor     al, al
0x14000cb66  jmp     loc_14000CC20
0x14000cb6b  mov     rcx, [rsp+2A0h+var_268]
0x14000cb70  mov     rax, [rcx]
0x14000cb73  mov     r8d, 104h
0x14000cb79  lea     rdx, [rsp+2A0h+Src]
0x14000cb7e  mov     rax, [rax+8]
0x14000cb82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb87  mov     ebx, eax
0x14000cb89  test    eax, eax
0x14000cb8b  js      loc_14000CC47
0x14000cb91  mov     eax, cs:dword_140017048
0x14000cb97  cmp     eax, 4
0x14000cb9a  jbe     short loc_14000CBCA
0x14000cb9c  mov     [rsp+2A0h+var_270], ebx
0x14000cba0  lea     rax, [rsp+2A0h+Src]
0x14000cba5  mov     [rsp+2A0h+var_260], rax
0x14000cbaa  lea     rax, [rsp+2A0h+var_270]
0x14000cbaf  mov     [rsp+2A0h+var_278], rax
0x14000cbb4  lea     rax, [rsp+2A0h+var_260]
0x14000cbb9  mov     qword ptr [rsp+2A0h+var_280], rax
0x14000cbbe  lea     rdx, byte_14001387D
0x14000cbc5  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14000cbca  cmp     [rsp+2A0h+Src], r14w
0x14000cbd0  jnz     short loc_14000CBD7
0x14000cbd2  mov     r8, r14
0x14000cbd5  jmp     short loc_14000CBEA
0x14000cbd7  lea     rax, [rsp+2A0h+Src]
0x14000cbdc  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000cbe0  inc     r8
0x14000cbe3  cmp     [rax+r8*2], r14w
0x14000cbe8  jnz     short loc_14000CBE0
0x14000cbea  lea     rcx, [rdi+48h]; void *
0x14000cbee  lea     rdx, [rsp+2A0h+Src]; Src
0x14000cbf3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14000cbf8  mov     rbx, [rsp+2A0h+var_268]
0x14000cbfd  mov     rcx, [rdi+68h]
0x14000cc01  cmp     rbx, rcx
0x14000cc04  jz      short loc_14000CC1E
0x14000cc06  test    rcx, rcx
0x14000cc09  jz      short loc_14000CC1A
0x14000cc0b  mov     rax, [rcx]
0x14000cc0e  mov     rax, [rax+80h]
0x14000cc15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc1a  mov     [rdi+68h], rbx
0x14000cc1e  mov     al, 1
0x14000cc20  mov     rcx, [rbp+1A0h+var_20]
0x14000cc27  xor     rcx, rsp; StackCookie
0x14000cc2a  call    __security_check_cookie
0x14000cc2f  lea     r11, [rsp+2A0h+var_10]
0x14000cc37  mov     rbx, [r11+28h]
0x14000cc3b  mov     rsi, [r11+30h]
0x14000cc3f  mov     rsp, r11
0x14000cc42  pop     r14
0x14000cc44  pop     rdi
0x14000cc45  pop     rbp
0x14000cc46  retn
0x14000cc47  mov     ecx, cs:dword_140017048
0x14000cc4d  cmp     ecx, 2
0x14000cc50  jbe     short loc_14000CC88
0x14000cc52  xor     edx, edx
0x14000cc54  lea     rcx, dword_140017048
0x14000cc5b  call    _tlgKeywordOn
0x14000cc60  test    al, al
0x14000cc62  jz      short loc_14000CC88
0x14000cc64  mov     [rsp+2A0h+var_270], ebx
0x14000cc68  lea     rax, [rsp+2A0h+var_270]
0x14000cc6d  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x14000cc72  xor     r8d, r8d
0x14000cc75  lea     rdx, dword_1400138B4
0x14000cc7c  lea     rcx, dword_140017048
0x14000cc83  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x14000cc88  mov     ecx, ebx
0x14000cc8a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x14000cc8f  mov     r9d, eax; char *
0x14000cc92  mov     rcx, [rbp+1A8h]; this
0x14000cc99  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x14000cca0  mov     edx, 83h; void *
0x14000cca5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000ccab  mov     edx, cs:dword_140017048
0x14000ccb1  cmp     edx, 2
0x14000ccb4  jbe     short loc_14000CCFC
0x14000ccb6  xor     edx, edx
0x14000ccb8  lea     rcx, dword_140017048
0x14000ccbf  call    _tlgKeywordOn
0x14000ccc4  test    al, al
0x14000ccc6  jz      short loc_14000CCFC
0x14000ccc8  mov     [rsp+2A0h+var_270], esi
0x14000cccc  mov     rcx, rbx
0x14000cccf  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x14000ccd4  mov     rdx, rax
0x14000ccd7  lea     rcx, [rsp+2A0h+var_260]
0x14000ccdc  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x14000cce1  lea     rcx, [rsp+2A0h+var_270]
0x14000cce6  mov     [rsp+2A0h+var_278], rcx
0x14000cceb  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x14000ccf0  lea     rdx, dword_14001392C
0x14000ccf7  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14000ccfc  mov     ecx, esi
0x14000ccfe  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x14000cd03  mov     r9d, eax; char *
0x14000cd06  mov     rcx, [rbp+1A8h]; this
0x14000cd0d  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x14000cd14  mov     edx, 71h ; 'q'; void *
0x14000cd19  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
