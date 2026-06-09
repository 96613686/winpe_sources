# CFilterMapiFps::GetChunk(tagSTAT_CHUNK *)

- ea: `0x18001dba0`
- end: `0x18001de6b`
- name: `?GetChunk@CFilterMapiFps@@UEAAJPEAUtagSTAT_CHUNK@@@Z`
- size: `715`
- prototype: `__int64 __fastcall(CFilterMapiFps *this, struct tagSTAT_CHUNK *, const struct _tagpropertykey *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180017870`
- `0x1800186e8`
- `0x18001bd9c`
- `0x18001dba0`
- `0x18001e5d8`
- `0x18001e608`
- `0x1800206b0`
- `0x180020768`
- `0x180022690`
- `0x180022888`
- `0x18003a0d8`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001dd95`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001dda8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001dd95`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001dda8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dde8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dde8`

## pseudocode

```c
__int64 __fastcall CFilterMapiFps::GetChunk(
        CFilterMapiFps *this,
        struct tagSTAT_CHUNK *a2,
        const struct _tagpropertykey *a3)
{
  struct IFilter **v5; // r12
  __int64 v6; // rsi
  __int64 (__fastcall *v7)(__int64, unsigned __int64, _QWORD, _QWORD, struct IFilter **); // rdi
  unsigned __int64 v8; // rbx
  int v9; // eax
  HRESULT v10; // edi
  int v12; // esi
  __int64 v13; // rax
  __int64 v14; // rax
  struct IFilter *v15; // rcx
  struct IFilterVtbl *lpVtbl; // rax
  int v17; // ebx
  PROPVARIANT *v18; // rcx
  PROPID propid; // rcx
  PROPVARIANT **p_pvar; // [rsp+30h] [rbp-20h] BYREF
  __int64 v21; // [rsp+38h] [rbp-18h] BYREF
  char v22; // [rsp+40h] [rbp-10h]
  PROPVARIANT *pvar; // [rsp+80h] [rbp+30h] BYREF

  v5 = (struct IFilter **)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
  {
    v10 = 0;
  }
  else
  {
    if ( !*((_QWORD *)this + 4) || !*((_QWORD *)this + 5) )
      return 2147549183LL;
    v6 = *((_QWORD *)this + 5);
    v7 = *(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, _QWORD, struct IFilter **))(*(_QWORD *)v6 + 24LL);
    v8 = (unsigned __int64)this + 88;
    v9 = memcmp_0((char *)this + 88, &GUID_NULL, 0x10u);
    v10 = v7(v6, v8 & -(__int64)(v9 != 0), 0, *((_QWORD *)this + 8), v5);
    if ( v10 < 0 )
      goto LABEL_11;
    v10 = InitializeFilterWithStream(*v5, *((struct IStream **)this + 4));
    if ( v10 < 0 )
      goto LABEL_11;
  }
  if ( !*((_DWORD *)this + 20) )
  {
    LODWORD(pvar) = 0;
    v10 = ((__int64 (__fastcall *)(struct IFilter *, _QWORD, _QWORD, _QWORD, PROPVARIANT **))(*v5)->lpVtbl->Init)(
            *v5,
            *((unsigned int *)this + 14),
            0,
            0,
            &pvar);
    *((_DWORD *)this + 20) = 1;
  }
LABEL_11:
  v12 = 1;
  *((_DWORD *)this + 21) = 0;
  while ( v10 != -2147215616 )
  {
    if ( v10 < 0 )
      return (unsigned int)v10;
    v10 = ((__int64 (__fastcall *)(struct IFilter *, struct tagSTAT_CHUNK *))(*v5)->lpVtbl->GetChunk)(*v5, a2);
    if ( v10 )
      goto LABEL_38;
    v13 = *(_QWORD *)&a2->attribute.guidPropSet.Data1 - 0x11CFC0B3D1B5D3F0LL;
    if ( *(_QWORD *)&a2->attribute.guidPropSet.Data1 == 0x11CFC0B3D1B5D3F0LL )
      v13 = *(_QWORD *)a2->attribute.guidPropSet.Data4 + 0xE24F7365FFF6D66LL;
    if ( !v13 )
      goto LABEL_47;
    v14 = *(_QWORD *)&a2->attribute.guidPropSet.Data1 - 0x11D0B831C82BF596LL;
    if ( *(_QWORD *)&a2->attribute.guidPropSet.Data1 == 0x11D0B831C82BF596LL )
      v14 = *(_QWORD *)a2->attribute.guidPropSet.Data4 + 0x2D145EFF55FFCC49LL;
    if ( !v14 )
    {
LABEL_47:
      if ( !a2->attribute.psProperty.ulKind )
      {
        propid = a2->attribute.psProperty.propid;
        if ( propid )
        {
          CoTaskMemFree(propid);
          a2->attribute.psProperty.propid = 0;
        }
      }
      goto LABEL_38;
    }
    pvar = 0;
    if ( a2->flags == CHUNK_TEXT )
      goto LABEL_33;
    if ( a2->flags != CHUNK_VALUE )
    {
      if ( a2->flags == CHUNK_FILTER_OWNED_VALUE )
        CLogger::Warning(L"Skipping CHUNK_FILTER_OWNED_VALUE");
      else
        CLogger::Error(L"Skipping unsupported CHUNK");
      goto LABEL_34;
    }
    v15 = *v5;
    lpVtbl = (*v5)->lpVtbl;
    p_pvar = &pvar;
    v21 = 0;
    v22 = 1;
    v17 = ((__int64 (__fastcall *)(struct IFilter *, __int64 *))lpVtbl->GetValue)(v15, &v21);
    wil::details::out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pvar);
    if ( v17 >= 0 )
    {
      if ( (*(_WORD *)pvar & 0xFFF) == 8 || (*(_WORD *)pvar & 0xFFFu) - 30 < 2 )
      {
        v18 = (PROPVARIANT *)*((_QWORD *)this + 9);
        if ( v18 )
        {
          v10 = PropVariantClear(v18);
          if ( v10 < 0 )
            goto LABEL_34;
        }
        wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::swap(
          (char *)this + 72,
          &pvar);
        *((_DWORD *)this + 21) = 1;
LABEL_33:
        v12 = 0;
        goto LABEL_34;
      }
      v10 = PropVariantClear(pvar);
    }
LABEL_34:
    wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &pvar,
      0);
LABEL_38:
    if ( !v12 )
      break;
  }
  if ( v10 >= 0 )
  {
    if ( *((_DWORD *)this + 30) )
    {
      if ( (unsigned int)InlineIsEqualPKEY(
                           &a2->attribute.guidPropSet,
                           (unsigned int)a2->attribute.psProperty.propid,
                           a3) )
        *((_DWORD *)this + 28) = 1;
    }
    a2->attribute.guidPropSet = *CMapi2FullPropSpec::GetPropGuid(*((CMapi2FullPropSpec **)this + 6));
    a2->attribute.psProperty.ulKind = 1;
    LODWORD(a2->attribute.psProperty.propid) = CMapi2FullPropSpec::GetPropId(*((CMapi2FullPropSpec **)this + 6));
    a2->flags = CHUNK_TEXT;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001dba0  mov     [rsp-28h+arg_8], rbx
0x18001dba5  mov     [rsp-28h+arg_10], rsi
0x18001dbaa  push    rbp
0x18001dbab  push    rdi
0x18001dbac  push    r12
0x18001dbae  push    r14
0x18001dbb0  push    r15
0x18001dbb2  mov     rbp, rsp
0x18001dbb5  sub     rsp, 50h
0x18001dbb9  mov     r15, rdx
0x18001dbbc  mov     r14, rcx
0x18001dbbf  lea     r12, [rcx+18h]
0x18001dbc3  cmp     qword ptr [r12], 0
0x18001dbc8  jnz     short loc_18001DC40
0x18001dbca  cmp     qword ptr [rcx+20h], 0
0x18001dbcf  jz      short loc_18001DC36
0x18001dbd1  cmp     qword ptr [rcx+28h], 0
0x18001dbd6  jz      short loc_18001DC36
0x18001dbd8  mov     rsi, [rcx+28h]
0x18001dbdc  mov     rax, [rsi]
0x18001dbdf  mov     rdi, [rax+18h]
0x18001dbe3  lea     rbx, [rcx+58h]
0x18001dbe7  mov     r8d, 10h; Size
0x18001dbed  lea     rdx, GUID_NULL; Buf2
0x18001dbf4  mov     rcx, rbx; Buf1
0x18001dbf7  call    memcmp_0
0x18001dbfc  neg     eax
0x18001dbfe  sbb     rdx, rdx
0x18001dc01  and     rdx, rbx
0x18001dc04  mov     [rsp+50h+var_30], r12
0x18001dc09  mov     r9, [r14+40h]
0x18001dc0d  xor     r8d, r8d
0x18001dc10  mov     rcx, rsi
0x18001dc13  mov     rax, rdi
0x18001dc16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc1b  mov     edi, eax
0x18001dc1d  test    eax, eax
0x18001dc1f  js      short loc_18001DC7D
0x18001dc21  mov     rdx, [r14+20h]; struct IStream *
0x18001dc25  mov     rcx, [r12]; struct IFilter *
0x18001dc29  call    ?InitializeFilterWithStream@@YAJPEAUIFilter@@PEAUIStream@@@Z; InitializeFilterWithStream(IFilter *,IStream *)
0x18001dc2e  mov     edi, eax
0x18001dc30  test    eax, eax
0x18001dc32  js      short loc_18001DC7D
0x18001dc34  jmp     short loc_18001DC42
0x18001dc36  mov     eax, 8000FFFFh
0x18001dc3b  jmp     loc_18001DE52
0x18001dc40  xor     edi, edi
0x18001dc42  cmp     dword ptr [r14+50h], 0
0x18001dc47  jnz     short loc_18001DC7D
0x18001dc49  mov     dword ptr [rbp+pvar], 0
0x18001dc50  mov     rcx, [r12]
0x18001dc54  mov     rax, [rcx]
0x18001dc57  lea     rdx, [rbp+pvar]
0x18001dc5b  mov     [rsp+50h+var_30], rdx
0x18001dc60  xor     r9d, r9d
0x18001dc63  xor     r8d, r8d
0x18001dc66  mov     edx, [r14+38h]
0x18001dc6a  mov     rax, [rax+18h]
0x18001dc6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc73  mov     edi, eax
0x18001dc75  mov     dword ptr [r14+50h], 1
0x18001dc7d  mov     esi, 1
0x18001dc82  mov     dword ptr [r14+54h], 0
0x18001dc8a  cmp     edi, 80041700h
0x18001dc90  jz      loc_18001DDFE
0x18001dc96  test    edi, edi
0x18001dc98  js      loc_18001DE50
0x18001dc9e  mov     rcx, [r12]
0x18001dca2  mov     rax, [rcx]
0x18001dca5  mov     rdx, r15
0x18001dca8  mov     rax, [rax+20h]
0x18001dcac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcb1  mov     edi, eax
0x18001dcb3  test    eax, eax
0x18001dcb5  jnz     loc_18001DDF6
0x18001dcbb  mov     rax, [r15+10h]
0x18001dcbf  sub     rax, cs:qword_180047E60
0x18001dcc6  jnz     short loc_18001DCD3
0x18001dcc8  mov     rax, [r15+18h]
0x18001dccc  sub     rax, cs:qword_180047E68
0x18001dcd3  test    rax, rax
0x18001dcd6  jz      loc_18001DDD8
0x18001dcdc  mov     rax, [r15+10h]
0x18001dce0  sub     rax, cs:qword_180047E50
0x18001dce7  jnz     short loc_18001DCF4
0x18001dce9  mov     rax, [r15+18h]
0x18001dced  sub     rax, cs:qword_180047E58
0x18001dcf4  test    rax, rax
0x18001dcf7  jz      loc_18001DDD8
0x18001dcfd  mov     [rbp+pvar], 0
0x18001dd05  mov     ecx, [r15+8]
0x18001dd09  sub     ecx, 1
0x18001dd0c  jz      loc_18001DDC9
0x18001dd12  sub     ecx, 1
0x18001dd15  jz      short loc_18001DD3E
0x18001dd17  cmp     ecx, 2
0x18001dd1a  jz      short loc_18001DD2D
0x18001dd1c  lea     rcx, aSkippingUnsupp; "Skipping unsupported CHUNK"
0x18001dd23  call    ?Error@CLogger@@SAXPEB_WZZ; CLogger::Error(wchar_t const *,...)
0x18001dd28  jmp     loc_18001DDCB
0x18001dd2d  lea     rcx, aSkippingChunkF; "Skipping CHUNK_FILTER_OWNED_VALUE"
0x18001dd34  call    ?Warning@CLogger@@SAXPEB_WZZ; CLogger::Warning(wchar_t const *,...)
0x18001dd39  jmp     loc_18001DDCB
0x18001dd3e  mov     rcx, [r12]
0x18001dd42  mov     rax, [rcx]
0x18001dd45  lea     rdx, [rbp+pvar]
0x18001dd49  mov     [rbp+var_20], rdx
0x18001dd4d  mov     [rbp+var_18], 0
0x18001dd55  mov     [rbp+var_10], 1
0x18001dd59  lea     rdx, [rbp+var_18]
0x18001dd5d  mov     rax, [rax+30h]
0x18001dd61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd66  mov     ebx, eax
0x18001dd68  lea     rcx, [rbp+var_20]
0x18001dd6c  call    ??1?$out_param_t@V?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001dd71  shr     ebx, 1Fh
0x18001dd74  xor     bl, 1
0x18001dd77  jz      short loc_18001DDCB
0x18001dd79  mov     rcx, [rbp+pvar]; pvar
0x18001dd7d  movzx   edx, word ptr [rcx]
0x18001dd80  and     edx, 0FFFh
0x18001dd86  sub     edx, 8
0x18001dd89  jz      short loc_18001DD9F
0x18001dd8b  sub     edx, 16h
0x18001dd8e  jz      short loc_18001DD9F
0x18001dd90  cmp     edx, 1
0x18001dd93  jz      short loc_18001DD9F
0x18001dd95  call    cs:__imp_PropVariantClear
0x18001dd9b  mov     edi, eax
0x18001dd9d  jmp     short loc_18001DDCB
0x18001dd9f  mov     rcx, [r14+48h]; pvar
0x18001dda3  test    rcx, rcx
0x18001dda6  jz      short loc_18001DDB4
0x18001dda8  call    cs:__imp_PropVariantClear
0x18001ddae  mov     edi, eax
0x18001ddb0  test    eax, eax
0x18001ddb2  js      short loc_18001DDCB
0x18001ddb4  lea     rdx, [rbp+pvar]
0x18001ddb8  lea     rcx, [r14+48h]
0x18001ddbc  call    ?swap@?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXAEAV12@@Z; wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::swap(wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x18001ddc1  mov     dword ptr [r14+54h], 1
0x18001ddc9  xor     esi, esi
0x18001ddcb  xor     edx, edx
0x18001ddcd  lea     rcx, [rbp+pvar]
0x18001ddd1  call    ?reset@?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagPROPVARIANT@@@Z; wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tagPROPVARIANT *)
0x18001ddd6  jmp     short loc_18001DDF6
0x18001ddd8  cmp     dword ptr [r15+20h], 0
0x18001dddd  jnz     short loc_18001DDF6
0x18001dddf  mov     rcx, [r15+28h]; pv
0x18001dde3  test    rcx, rcx
0x18001dde6  jz      short loc_18001DDF6
0x18001dde8  call    cs:__imp_CoTaskMemFree
0x18001ddee  mov     qword ptr [r15+28h], 0
0x18001ddf6  test    esi, esi
0x18001ddf8  jnz     loc_18001DC8A
0x18001ddfe  test    edi, edi
0x18001de00  js      short loc_18001DE50
0x18001de02  cmp     dword ptr [r14+78h], 0
0x18001de07  jz      short loc_18001DE21
0x18001de09  lea     rcx, [r15+10h]; struct _GUID *
0x18001de0d  mov     edx, [rcx+18h]; unsigned int
0x18001de10  call    ?InlineIsEqualPKEY@@YAHAEBU_GUID@@KAEBU_tagpropertykey@@@Z; InlineIsEqualPKEY(_GUID const &,ulong,_tagpropertykey const &)
0x18001de15  test    eax, eax
0x18001de17  jz      short loc_18001DE21
0x18001de19  mov     dword ptr [r14+70h], 1
0x18001de21  mov     rcx, [r14+30h]; this
0x18001de25  call    ?GetPropGuid@CMapi2FullPropSpec@@QEBAAEBU_GUID@@XZ; CMapi2FullPropSpec::GetPropGuid(void)
0x18001de2a  movups  xmm0, xmmword ptr [rax]
0x18001de2d  movdqu  xmmword ptr [r15+10h], xmm0
0x18001de33  mov     dword ptr [r15+20h], 1
0x18001de3b  mov     rcx, [r14+30h]; this
0x18001de3f  call    ?GetPropId@CMapi2FullPropSpec@@QEBAKXZ; CMapi2FullPropSpec::GetPropId(void)
0x18001de44  mov     [r15+28h], eax
0x18001de48  mov     dword ptr [r15+8], 1
0x18001de50  mov     eax, edi
0x18001de52  lea     r11, [rsp+50h+var_s0]
0x18001de57  mov     rbx, [r11+38h]
0x18001de5b  mov     rsi, [r11+40h]
0x18001de5f  mov     rsp, r11
0x18001de62  pop     r15
0x18001de64  pop     r14
0x18001de66  pop     r12
0x18001de68  pop     rdi
0x18001de69  pop     rbp
0x18001de6a  retn
```
