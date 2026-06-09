# MediaObjectInfo::Initialize(ISmMessage *,ISmAttachment *)

- ea: `0x18000af00`
- end: `0x18000b411`
- name: `?Initialize@MediaObjectInfo@@UEAAJPEAUISmMessage@@PEAUISmAttachment@@@Z`
- size: `1297`
- prototype: `int(MediaObjectInfo *__hidden this, struct ISmMessage *, struct ISmAttachment *)`
- caller_count: `0`
- callee_count: `18`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x1800065c8`
- `0x180008870`
- `0x18000a730`
- `0x18000a754`
- `0x18000a7f0`
- `0x18000a8f0`
- `0x18000af00`
- `0x18000b418`
- `0x18000b448`
- `0x18000b6d4`
- `0x18000b7d4`
- `0x18000b7fc`
- `0x18000bae4`
- `0x18002c5a8`
- `0x1800c50ec`
- `0x1800c6902`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000b27d`
- `msvcrt!_wcsnicmp` at `0x18000b29d`
- `msvcrt!_wcsnicmp` at `0x18000b27d`
- `msvcrt!_wcsnicmp` at `0x18000b29d`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b117`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b166`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b117`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b166`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18000b221`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18000b221`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18000b348`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18000b348`

## pseudocode

```c
__int64 __fastcall MediaObjectInfo::Initialize(struct IUnknown **this, struct ISmMessage *a2, struct IUnknown *a3)
{
  struct IUnknown **v3; // r14
  int v6; // eax
  unsigned int v7; // ebx
  struct IUnknown *v8; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  _QWORD *v10; // rax
  int v11; // eax
  int v12; // ecx
  int MediaTypeFromMimeType; // eax
  struct IUnknown *v14; // rdi
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  _QWORD *v16; // rax
  int v17; // eax
  int v18; // ecx
  struct IUnknown *v19; // rdi
  HRESULT (__stdcall *v20)(IUnknown *, const IID *const, void **); // rbx
  _QWORD *v21; // rax
  int v22; // eax
  int v23; // ecx
  struct IUnknown *v24; // rdi
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  _QWORD *v26; // rax
  char *v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // rcx
  int DefaultFileNameFromMediaType; // eax
  unsigned int v31; // edi
  LPWSTR ExtensionW; // rax
  const wchar_t *v33; // r15
  __int64 v34; // rdi
  size_t v35; // r8
  int v36; // eax
  size_t v37; // r8
  int v38; // r12d
  int v39; // eax
  HRESULT v40; // r15d
  size_t v41; // r11
  struct IUnknown *v42; // rcx
  BSTR v44; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v45; // [rsp+38h] [rbp-C8h] BYREF
  BSTR pbstr; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-B8h] BYREF
  int v48; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszExt[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v50; // [rsp+68h] [rbp-98h]
  wchar_t pszDest[264]; // [rsp+80h] [rbp-80h] BYREF

  v3 = this + 9;
  if ( this[9] )
    ATL::AtlComPtrAssign(this + 9, 0);
  if ( *v3 != a3 )
    ATL::AtlComPtrAssign(v3, a3);
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, char *))a3->lpVtbl[6].QueryInterface)(a3, (char *)this + 216);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = *v3;
    String1 = 0;
    QueryInterface = v8->lpVtbl[2].QueryInterface;
    v10 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&String1);
    v11 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD *))QueryInterface)(v8, v10);
    v7 = v11;
    if ( v11 < 0 )
    {
      v12 = v11;
LABEL_11:
      Log_HREvent_0(v12);
LABEL_57:
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&String1);
      return v7;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             this + 23,
                             String1) )
    {
      v7 = -2147024882;
      v12 = -2147024882;
      goto LABEL_11;
    }
    MediaTypeFromMimeType = GetMediaTypeFromMimeType(String1);
    v14 = *v3;
    *((_DWORD *)this + 20) = MediaTypeFromMimeType;
    v45 = 0;
    Release = v14->lpVtbl[2].Release;
    v16 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v45);
    v17 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD *))Release)(v14, v16);
    v7 = v17;
    if ( v17 < 0 )
    {
      v18 = v17;
LABEL_14:
      Log_HREvent_0(v18);
LABEL_15:
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v45);
      goto LABEL_57;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             this + 15,
                             v45) )
    {
      v7 = -2147024882;
      v18 = -2147024882;
      goto LABEL_14;
    }
    v19 = *v3;
    v44 = 0;
    v20 = v19->lpVtbl[3].QueryInterface;
    v21 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v44);
    v22 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD *))v20)(v19, v21);
    v7 = v22;
    if ( v22 < 0 )
    {
      v23 = v22;
LABEL_20:
      Log_HREvent_0(v23);
LABEL_21:
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v44);
      goto LABEL_15;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             this + 19,
                             v44) )
    {
      v7 = -2147024882;
      v23 = -2147024882;
      goto LABEL_20;
    }
    v24 = *v3;
    pbstr = 0;
    AddRef = v24->lpVtbl[3].AddRef;
    v26 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&pbstr);
    if ( ((int (__fastcall *)(struct IUnknown *, _QWORD *))AddRef)(v24, v26) >= 0 && SysStringLen(pbstr) )
    {
      v27 = (char *)(this + 11);
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               this + 11,
                               pbstr) )
      {
LABEL_27:
        v7 = -2147024882;
        Log_HREvent_0(-2147024882);
LABEL_28:
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&pbstr);
        goto LABEL_21;
      }
    }
    else
    {
      v27 = (char *)(this + 11);
      if ( SysStringLen(v44) )
      {
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 this + 11,
                                 v44) )
          goto LABEL_27;
      }
      else
      {
        DefaultFileNameFromMediaType = GetDefaultFileNameFromMediaType(*((unsigned int *)this + 20), this + 11);
        v31 = DefaultFileNameFromMediaType;
        if ( DefaultFileNameFromMediaType < 0 )
        {
          Log_HREvent_0(DefaultFileNameFromMediaType);
          tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&pbstr);
          tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v44);
          tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v45);
          v7 = v31;
          goto LABEL_57;
        }
      }
    }
    if ( *(_QWORD *)v27 == *((_QWORD *)v27 + 1) )
    {
      Log_AssertionEvent_0(v29, v28, 154);
      if ( *(_QWORD *)v27 == *((_QWORD *)v27 + 1) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    if ( *((_DWORD *)this + 20) && *((_DWORD *)this + 20) != 6 )
    {
      *(_OWORD *)pszExt = 0;
      v50 = 0;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(pszExt);
      ExtensionW = PathFindExtensionW(*(LPCWSTR *)v27);
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               pszExt,
                               ExtensionW) )
        goto LABEL_40;
      v33 = pszExt[0];
      v34 = -1;
      v35 = -1;
      do
        ++v35;
      while ( c_mimeTypesFileExtionsions[v35] );
      v36 = _wcsnicmp(String1, c_mimeTypesFileExtionsions, v35);
      v37 = -1;
      v38 = v36;
      do
        ++v37;
      while ( aJpg[v37] );
      v39 = _wcsnicmp(v33, L".jpg", v37);
      if ( v38 || v39 )
      {
        v40 = AdjustFileExtension(String1, pszExt);
        if ( v40 < 0
          || (memset_0(pszDest, 0, 0x208u), v40 = StringCchCopyW(pszDest, 0x104u, *(STRSAFE_LPCWSTR *)v27), v40 < 0)
          || (v40 = PathCchRenameExtension(pszDest, v41, pszExt[0]), v40 < 0) )
        {
          Log_HREvent_0(v40);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(pszExt);
          tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&pbstr);
          tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v44);
          tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v45);
          v7 = v40;
          goto LABEL_57;
        }
        do
          ++v34;
        while ( pszDest[v34] );
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 v27,
                                 pszDest,
                                 v34) )
        {
LABEL_40:
          v7 = -2147024882;
          Log_HREvent_0(-2147024882);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(pszExt);
          goto LABEL_28;
        }
      }
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(pszExt);
    }
    v42 = *v3;
    v48 = 0;
    if ( ((int (__fastcall *)(struct IUnknown *, int *))v42->lpVtbl[1].AddRef)(v42, &v48) >= 0 )
      *((_DWORD *)this + 16) = v48;
    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&pbstr);
    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v44);
    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v45);
    v7 = 0;
    goto LABEL_57;
  }
  Log_HREvent_0(v6);
  return v7;
}

```

## disassembly

```asm
0x18000af00  mov     [rsp-8+arg_8], rbx
0x18000af05  push    rbp
0x18000af06  push    rsi
0x18000af07  push    rdi
0x18000af08  push    r12
0x18000af0a  push    r13
0x18000af0c  push    r14
0x18000af0e  push    r15
0x18000af10  lea     rbp, [rsp-1A0h]
0x18000af18  sub     rsp, 2A0h
0x18000af1f  mov     rax, cs:__security_cookie
0x18000af26  xor     rax, rsp
0x18000af29  mov     [rbp+1D0h+var_40], rax
0x18000af30  lea     r14, [rcx+48h]
0x18000af34  xor     r13d, r13d
0x18000af37  mov     rbx, r8
0x18000af3a  mov     rsi, rcx
0x18000af3d  cmp     [r14], r13
0x18000af40  jz      short loc_18000AF4C
0x18000af42  xor     edx, edx; struct IUnknown *
0x18000af44  mov     rcx, r14; struct IUnknown **
0x18000af47  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000af4c  cmp     [r14], rbx
0x18000af4f  jz      short loc_18000AF5C
0x18000af51  mov     rdx, rbx; struct IUnknown *
0x18000af54  mov     rcx, r14; struct IUnknown **
0x18000af57  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000af5c  mov     rax, [rbx]
0x18000af5f  lea     rdx, [rsi+0D8h]
0x18000af66  mov     rcx, rbx
0x18000af69  mov     rax, [rax+90h]
0x18000af70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af75  mov     ebx, eax
0x18000af77  test    eax, eax
0x18000af79  jns     short loc_18000AF90
0x18000af7b  mov     edx, 1
0x18000af80  mov     ecx, eax; int
0x18000af82  lea     r9d, [rdx+7Ch]
0x18000af86  call    Log_HREvent_0
0x18000af8b  jmp     loc_18000B3E5
0x18000af90  mov     rdi, [r14]
0x18000af93  lea     rcx, [rsp+2D0h+String1]
0x18000af98  mov     [rsp+2D0h+String1], r13
0x18000af9d  mov     rax, [rdi]
0x18000afa0  mov     rbx, [rax+30h]
0x18000afa4  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x18000afa9  mov     rdx, rax
0x18000afac  mov     rcx, rdi
0x18000afaf  mov     rax, rbx
0x18000afb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afb7  mov     ebx, eax
0x18000afb9  test    eax, eax
0x18000afbb  jns     short loc_18000AFCA
0x18000afbd  mov     edx, 1
0x18000afc2  mov     ecx, eax
0x18000afc4  lea     r9d, [rdx+7Fh]
0x18000afc8  jmp     short loc_18000AFEE
0x18000afca  mov     rdx, [rsp+2D0h+String1]
0x18000afcf  lea     rcx, [rsi+0B8h]
0x18000afd6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000afdb  test    al, al
0x18000afdd  jnz     short loc_18000AFF8
0x18000afdf  mov     ebx, 8007000Eh
0x18000afe4  xor     edx, edx
0x18000afe6  mov     ecx, ebx; int
0x18000afe8  mov     r9d, 81h
0x18000afee  call    Log_HREvent_0
0x18000aff3  jmp     loc_18000B3DB
0x18000aff8  mov     rcx, [rsp+2D0h+String1]; String1
0x18000affd  call    _GetMediaTypeFromMimeType
0x18000b002  mov     rdi, [r14]
0x18000b005  lea     rcx, [rsp+2D0h+var_298]
0x18000b00a  mov     [rsi+50h], eax
0x18000b00d  mov     [rsp+2D0h+var_298], r13
0x18000b012  mov     rax, [rdi]
0x18000b015  mov     rbx, [rax+40h]
0x18000b019  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x18000b01e  mov     rdx, rax
0x18000b021  mov     rcx, rdi
0x18000b024  mov     rax, rbx
0x18000b027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b02c  mov     ebx, eax
0x18000b02e  test    eax, eax
0x18000b030  jns     short loc_18000B053
0x18000b032  mov     edx, 1
0x18000b037  mov     r9d, 85h
0x18000b03d  mov     ecx, eax; int
0x18000b03f  call    Log_HREvent_0
0x18000b044  lea     rcx, [rsp+2D0h+var_298]
0x18000b049  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18000b04e  jmp     loc_18000B3DB
0x18000b053  mov     rdx, [rsp+2D0h+var_298]
0x18000b058  lea     rcx, [rsi+78h]
0x18000b05c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000b061  test    al, al
0x18000b063  jnz     short loc_18000B076
0x18000b065  mov     ebx, 8007000Eh
0x18000b06a  xor     edx, edx
0x18000b06c  mov     ecx, ebx
0x18000b06e  mov     r9d, 86h
0x18000b074  jmp     short loc_18000B03F
0x18000b076  mov     rdi, [r14]
0x18000b079  lea     rcx, [rsp+2D0h+var_2A0]
0x18000b07e  mov     [rsp+2D0h+var_2A0], r13
0x18000b083  mov     rax, [rdi]
0x18000b086  mov     rbx, [rax+48h]
0x18000b08a  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x18000b08f  mov     rdx, rax
0x18000b092  mov     rcx, rdi
0x18000b095  mov     rax, rbx
0x18000b098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b09d  mov     ebx, eax
0x18000b09f  test    eax, eax
0x18000b0a1  jns     short loc_18000B0C1
0x18000b0a3  mov     edx, 1
0x18000b0a8  mov     r9d, 89h
0x18000b0ae  mov     ecx, eax; int
0x18000b0b0  call    Log_HREvent_0
0x18000b0b5  lea     rcx, [rsp+2D0h+var_2A0]
0x18000b0ba  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18000b0bf  jmp     short loc_18000B044
0x18000b0c1  mov     rdx, [rsp+2D0h+var_2A0]
0x18000b0c6  lea     rcx, [rsi+98h]
0x18000b0cd  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000b0d2  test    al, al
0x18000b0d4  jnz     short loc_18000B0E7
0x18000b0d6  mov     ebx, 8007000Eh
0x18000b0db  xor     edx, edx
0x18000b0dd  mov     ecx, ebx
0x18000b0df  mov     r9d, 8Ah
0x18000b0e5  jmp     short loc_18000B0B0
0x18000b0e7  mov     rdi, [r14]
0x18000b0ea  lea     rcx, [rsp+2D0h+pbstr]
0x18000b0ef  mov     [rsp+2D0h+pbstr], r13
0x18000b0f4  mov     rax, [rdi]
0x18000b0f7  mov     rbx, [rax+50h]
0x18000b0fb  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x18000b100  mov     rdx, rax
0x18000b103  mov     rcx, rdi
0x18000b106  mov     rax, rbx
0x18000b109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b10e  test    eax, eax
0x18000b110  js      short loc_18000B15D
0x18000b112  mov     rcx, [rsp+2D0h+pbstr]; pbstr
0x18000b117  call    cs:__imp_SysStringLen
0x18000b11d  test    eax, eax
0x18000b11f  jz      short loc_18000B15D
0x18000b121  mov     rdx, [rsp+2D0h+pbstr]
0x18000b126  lea     rbx, [rsi+58h]
0x18000b12a  mov     rcx, rbx
0x18000b12d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000b132  test    al, al
0x18000b134  jnz     loc_18000B1D1
0x18000b13a  mov     r9d, 8Fh
0x18000b140  mov     ebx, 8007000Eh
0x18000b145  xor     edx, edx
0x18000b147  mov     ecx, ebx; int
0x18000b149  call    Log_HREvent_0
0x18000b14e  lea     rcx, [rsp+2D0h+pbstr]
0x18000b153  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18000b158  jmp     loc_18000B0B5
0x18000b15d  mov     rcx, [rsp+2D0h+var_2A0]; pbstr
0x18000b162  lea     rbx, [rsi+58h]
0x18000b166  call    cs:__imp_SysStringLen
0x18000b16c  test    eax, eax
0x18000b16e  jz      short loc_18000B189
0x18000b170  mov     rdx, [rsp+2D0h+var_2A0]
0x18000b175  mov     rcx, rbx
0x18000b178  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000b17d  test    al, al
0x18000b17f  jnz     short loc_18000B1D1
0x18000b181  mov     r9d, 93h
0x18000b187  jmp     short loc_18000B140
0x18000b189  mov     ecx, [rsi+50h]
0x18000b18c  mov     rdx, rbx
0x18000b18f  call    GetDefaultFileNameFromMediaType
0x18000b194  mov     edi, eax
0x18000b196  test    eax, eax
0x18000b198  jns     short loc_18000B1D1
0x18000b19a  mov     edx, 1
0x18000b19f  mov     r9d, 97h
0x18000b1a5  mov     ecx, eax; int
0x18000b1a7  call    Log_HREvent_0
0x18000b1ac  lea     rcx, [rsp+2D0h+pbstr]
0x18000b1b1  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18000b1b6  lea     rcx, [rsp+2D0h+var_2A0]
0x18000b1bb  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18000b1c0  lea     rcx, [rsp+2D0h+var_298]
0x18000b1c5  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18000b1ca  mov     ebx, edi
0x18000b1cc  jmp     loc_18000B3DB
0x18000b1d1  mov     rax, [rbx+8]
0x18000b1d5  cmp     [rbx], rax
0x18000b1d8  jnz     short loc_18000B1F3
0x18000b1da  mov     r8d, 9Ah
0x18000b1e0  call    Log_AssertionEvent_0
0x18000b1e5  mov     rax, [rbx+8]
0x18000b1e9  cmp     [rbx], rax
0x18000b1ec  jnz     short loc_18000B1F3
0x18000b1ee  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b1f3  cmp     [rsi+50h], r13d
0x18000b1f7  jz      loc_18000B396
0x18000b1fd  cmp     dword ptr [rsi+50h], 6
0x18000b201  jz      loc_18000B396
0x18000b207  xorps   xmm0, xmm0
0x18000b20a  lea     rcx, [rsp+2D0h+pszExt]
0x18000b20f  movups  xmmword ptr [rsp+2D0h+pszExt], xmm0
0x18000b214  movups  [rsp+2D0h+var_268], xmm0
0x18000b219  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000b21e  mov     rcx, [rbx]; pszPath
0x18000b221  call    cs:__imp_PathFindExtensionW
0x18000b227  mov     rdx, rax
0x18000b22a  lea     rcx, [rsp+2D0h+pszExt]
0x18000b22f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000b234  test    al, al
0x18000b236  jnz     short loc_18000B25B
0x18000b238  mov     r9d, 0A0h
0x18000b23e  mov     ebx, 8007000Eh
0x18000b243  xor     edx, edx
0x18000b245  mov     ecx, ebx; int
0x18000b247  call    Log_HREvent_0
0x18000b24c  lea     rcx, [rsp+2D0h+pszExt]
0x18000b251  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000b256  jmp     loc_18000B14E
0x18000b25b  mov     r15, [rsp+2D0h+pszExt]
0x18000b260  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b264  mov     rdx, cs:?c_mimeTypesFileExtionsions@@3QBUMimeTypeFileExtension@@B; String2
0x18000b26b  mov     r8, rdi
0x18000b26e  inc     r8; MaxCount
0x18000b271  cmp     [rdx+r8*2], r13w
0x18000b276  jnz     short loc_18000B26E
0x18000b278  mov     rcx, [rsp+2D0h+String1]; String1
0x18000b27d  call    cs:__imp__wcsnicmp
0x18000b283  mov     rdx, cs:String2; String2
0x18000b28a  mov     r8, rdi
0x18000b28d  mov     r12d, eax
0x18000b290  inc     r8; MaxCount
0x18000b293  cmp     [rdx+r8*2], r13w
0x18000b298  jnz     short loc_18000B290
0x18000b29a  mov     rcx, r15; String1
0x18000b29d  call    cs:__imp__wcsnicmp
0x18000b2a3  test    r12d, r12d
0x18000b2a6  jnz     short loc_18000B2B0
0x18000b2a8  test    eax, eax
0x18000b2aa  jz      loc_18000B38C
0x18000b2b0  mov     rcx, [rsp+2D0h+String1]
0x18000b2b5  lea     rdx, [rsp+2D0h+pszExt]
0x18000b2ba  call    AdjustFileExtension
0x18000b2bf  mov     r15d, eax
0x18000b2c2  test    eax, eax
0x18000b2c4  jns     short loc_18000B309
0x18000b2c6  mov     r9d, 0A4h
0x18000b2cc  mov     edx, 1
0x18000b2d1  mov     ecx, r15d; int
0x18000b2d4  call    Log_HREvent_0
0x18000b2d9  lea     rcx, [rsp+2D0h+pszExt]
0x18000b2de  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000b2e3  lea     rcx, [rsp+2D0h+pbstr]
0x18000b2e8  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18000b2ed  lea     rcx, [rsp+2D0h+var_2A0]
0x18000b2f2  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18000b2f7  lea     rcx, [rsp+2D0h+var_298]
0x18000b2fc  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18000b301  mov     ebx, r15d
0x18000b304  jmp     loc_18000B3DB
0x18000b309  xor     edx, edx; Val
0x18000b30b  lea     rcx, [rbp+1D0h+pszDest]; void *
0x18000b30f  mov     r8d, 208h; Size
0x18000b315  call    memset_0
0x18000b31a  mov     r8, [rbx]; pszSrc
0x18000b31d  lea     rcx, [rbp+1D0h+pszDest]; pszDest
0x18000b321  mov     r11d, 104h
0x18000b327  mov     edx, r11d; cchDest
0x18000b32a  call    StringCchCopyW
0x18000b32f  mov     r15d, eax
0x18000b332  test    eax, eax
0x18000b334  jns     short loc_18000B33C
0x18000b336  lea     r9d, [r11-5Dh]
0x18000b33a  jmp     short loc_18000B2CC
0x18000b33c  mov     r8, [rsp+2D0h+pszExt]; pszExt
0x18000b341  lea     rcx, [rbp+1D0h+pszDest]; pszPath
0x18000b345  mov     rdx, r11; cchPath
0x18000b348  call    cs:__imp_PathCchRenameExtension
0x18000b34e  mov     r15d, eax
0x18000b351  test    eax, eax
0x18000b353  jns     short loc_18000B360
0x18000b355  mov     r9d, 0A8h
0x18000b35b  jmp     loc_18000B2CC
0x18000b360  lea     rax, [rbp+1D0h+pszDest]
0x18000b364  inc     rdi
0x18000b367  cmp     [rax+rdi*2], r13w
0x18000b36c  jnz     short loc_18000B364
0x18000b36e  mov     r8, rdi
0x18000b371  lea     rdx, [rbp+1D0h+pszDest]
0x18000b375  mov     rcx, rbx
0x18000b378  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000b37d  test    al, al
0x18000b37f  jnz     short loc_18000B38C
0x18000b381  mov     r9d, 0A9h
0x18000b387  jmp     loc_18000B23E
  ... truncated ...
```
