# ProcessNewXmlElement(IXmlReader *,MasterDatastoreContext *)

- ea: `0x18000b8f8`
- end: `0x18000bdea`
- name: `?ProcessNewXmlElement@@YAJPEAUIXmlReader@@PEAUMasterDatastoreContext@@@Z`
- size: `1266`
- prototype: `__int64 __fastcall(struct IXmlReader *, struct MasterDatastoreContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b31c`

## callees

- `0x180001118`
- `0x180001264`
- `0x1800018f4`
- `0x180009068`
- `0x18000a65c`
- `0x18000b8f8`
- `0x18000c070`
- `0x18000c22c`
- `0x18000fa60`
- `0x180010d44`
- `0x180010f80`
- `0x180012010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ba32`
- `msvcrt!_wcsicmp` at `0x18000bd59`
- `msvcrt!_wcsicmp` at `0x18000ba32`
- `msvcrt!_wcsicmp` at `0x18000bd59`

## string_xrefs

- `0x18000bd0d`: `ConfigurationSourceList`
- `0x18000baf0`: `ConfigurationSource`

## pseudocode

```c
__int64 __fastcall ProcessNewXmlElement(struct IXmlReader *a1, struct MasterDatastoreContext *a2)
{
  int XmlAttribute; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  int *v7; // rax
  int v8; // edx
  __int64 v9; // rbx
  wchar_t *v10; // r15
  unsigned int v11; // esi
  unsigned int v12; // ecx
  __int64 v13; // rdx
  int *v14; // rax
  int v15; // edx
  _DWORD **v16; // r15
  int *v17; // rax
  int v18; // ecx
  __int64 v19; // rcx
  char *v20; // rax
  char *v21; // rsi
  volatile signed __int32 *v22; // rbx
  __int64 v23; // rcx
  int *v24; // rax
  int v25; // edx
  int *v26; // rcx
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  int *v29; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v30; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v32; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v33; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v34; // [rsp+70h] [rbp-90h] BYREF
  volatile signed __int32 *v35; // [rsp+78h] [rbp-88h]
  unsigned __int16 v36[264]; // [rsp+80h] [rbp-80h] BYREF

  v28 = 0;
  v29 = 0;
  v33 = 0;
  String1 = 0;
  v32 = 0;
  XmlAttribute = ((__int64 (__fastcall *)(struct IXmlReader *, int **, _QWORD))a1->lpVtbl->GetLocalName)(a1, &v29, 0);
  if ( XmlAttribute < 0 )
    goto LABEL_62;
  switch ( *((_DWORD *)a2 + 2) )
  {
    case 1:
      v24 = v29;
      do
      {
        v5 = *(unsigned __int16 *)((char *)v24 + (char *)L"ConfigurationSourceList" - (char *)v29);
        v25 = *(unsigned __int16 *)v24 - (_DWORD)v5;
        if ( v25 )
          break;
        v24 = (int *)((char *)v24 + 2);
      }
      while ( (_DWORD)v5 );
      if ( !v25 && (int)GetXmlAttribute((__int64)a1, (__int64)L"Version", 1, &v33) >= 0 && !_wcsicmp(v33, L"1.0") )
      {
        *((_DWORD *)a2 + 2) = 2;
        return 0;
      }
      goto LABEL_61;
    case 2:
      v16 = (_DWORD **)((char *)a2 + 16);
      if ( *((_QWORD *)a2 + 2) )
        MicrosoftTelemetryAssertTriggeredNoArgs((unsigned int)(*((_DWORD *)a2 + 2) - 2));
      v17 = v29;
      do
      {
        v5 = *(unsigned __int16 *)((char *)v17 + (char *)L"ConfigurationSource" - (char *)v29);
        v18 = *(unsigned __int16 *)v17 - (_DWORD)v5;
        if ( v18 )
          break;
        v17 = (int *)((char *)v17 + 2);
      }
      while ( (_DWORD)v5 );
      if ( !v18 && ((unsigned int (__fastcall *)(struct IXmlReader *))a1->lpVtbl->IsEmptyElement)(a1) != 1 )
      {
        XmlAttribute = GetXmlAttribute((__int64)a1, (__int64)L"Name", 1, &String1);
        if ( XmlAttribute >= 0 )
        {
          XmlAttribute = GetXmlAttribute((__int64)a1, (__int64)L"Path", 1, &v32);
          if ( XmlAttribute >= 0 )
          {
            XmlAttribute = TranslatePath(v32, v36, v5);
            if ( XmlAttribute >= 0 )
            {
              if ( *v16 )
                MicrosoftTelemetryAssertTriggeredNoArgs(v19);
              v20 = (char *)operator new(0x4A0u);
              v21 = v20;
              v30 = (wchar_t *)v20;
              if ( v20 )
              {
                *((_DWORD *)v20 + 2) = 1;
                *((_DWORD *)v20 + 3) = 1;
                *(_QWORD *)v20 = &std::_Ref_count_obj<CConfigSource>::`vftable';
                *((_DWORD *)v20 + 4) = 0;
                *(_QWORD *)(v20 + 1060) = 0;
                *((_QWORD *)v20 + 134) = 0;
                *((_QWORD *)v20 + 135) = 0;
                *((_QWORD *)v20 + 134) = std::_Tree_alloc<0,std::_Tree_base_types<std::wstring>>::_Buyheadnode();
                *((_QWORD *)v21 + 136) = 0;
                *((_QWORD *)v21 + 137) = 0;
                *((_QWORD *)v21 + 136) = std::_Tree_alloc<0,std::_Tree_base_types<std::wstring>>::_Buyheadnode();
                *((_DWORD *)v21 + 294) = 0;
                *((_WORD *)v21 + 270) = 0;
                *((_WORD *)v21 + 10) = 0;
              }
              else
              {
                v21 = 0;
              }
              v35 = (volatile signed __int32 *)v21;
              v34 = (unsigned __int16 *)(v21 + 16);
              std::shared_ptr<CConfigSet>::operator=((_QWORD *)a2 + 2, (__int64 *)&v34);
              v22 = v35;
              if ( v35 )
              {
                if ( _InterlockedExchangeAdd(v35 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
                  if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
                }
              }
              if ( *v16 )
              {
                XmlAttribute = CConfigSource::InitializeConfigSource(
                                 *v16,
                                 *((_DWORD *)a2 + 1),
                                 *(_DWORD *)a2,
                                 String1,
                                 v36);
                if ( XmlAttribute >= 0 )
                {
                  if ( (unsigned int)dword_180019000 > 4 )
                  {
                    v28 = *((_DWORD *)a2 + 1);
                    v34 = v36;
                    v30 = String1;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                      v23,
                      (__int64)&byte_180015577,
                      v5,
                      v6,
                      (int **)&v30,
                      (int **)&v34,
                      (__int64)&v28);
                  }
                  *((_DWORD *)a2 + 2) = 3;
                  return 0;
                }
              }
              else
              {
                XmlAttribute = -2147024882;
              }
            }
          }
        }
        goto LABEL_62;
      }
LABEL_61:
      XmlAttribute = -2147024809;
      goto LABEL_62;
    case 3:
      v14 = v29;
      do
      {
        v5 = *(unsigned __int16 *)((char *)v14 + (char *)L"EventList" - (char *)v29);
        v15 = *(unsigned __int16 *)v14 - (_DWORD)v5;
        if ( v15 )
          break;
        v14 = (int *)((char *)v14 + 2);
      }
      while ( (_DWORD)v5 );
      if ( !v15 && ((unsigned int (__fastcall *)(struct IXmlReader *))a1->lpVtbl->IsEmptyElement)(a1) != 1 )
      {
        *((_DWORD *)a2 + 2) = 4;
        return 0;
      }
      goto LABEL_61;
  }
  if ( *((_DWORD *)a2 + 2) != 4 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs((unsigned int)(*((_DWORD *)a2 + 2) - 3));
    return 0;
  }
  v7 = v29;
  do
  {
    v5 = *(unsigned __int16 *)((char *)v7 + (char *)L"Event" - (char *)v29);
    v8 = *(unsigned __int16 *)v7 - (_DWORD)v5;
    if ( v8 )
      break;
    v7 = (int *)((char *)v7 + 2);
  }
  while ( (_DWORD)v5 );
  if ( v8 || !((unsigned int (__fastcall *)(struct IXmlReader *))a1->lpVtbl->IsEmptyElement)(a1) )
    goto LABEL_61;
  XmlAttribute = GetXmlAttribute((__int64)a1, (__int64)L"Name", 1, &String1);
  if ( XmlAttribute >= 0 )
  {
    v9 = *((_QWORD *)a2 + 2);
    if ( *(_DWORD *)(v9 + 1160) != 18 )
    {
      v10 = String1;
      v11 = 0;
      while ( _wcsicmp(v10, (&off_1800134F0)[2 * v11]) )
      {
        if ( ++v11 >= 0x12 )
        {
          XmlAttribute = -2147023728;
          goto LABEL_62;
        }
      }
      v5 = *((unsigned int *)&off_1800134F0 + 4 * v11 + 2);
      v12 = 0;
      v13 = *(unsigned int *)(v9 + 1160);
      if ( !(_DWORD)v13 )
      {
LABEL_21:
        *(_DWORD *)(v9 + 4 * v13 + 1088) = v5;
        ++*(_DWORD *)(v9 + 1160);
        return 0;
      }
      while ( *(_DWORD *)(v9 + 4LL * v12 + 1088) != (_DWORD)v5 )
      {
        if ( ++v12 >= (unsigned int)v13 )
          goto LABEL_21;
      }
    }
    goto LABEL_61;
  }
LABEL_62:
  v26 = (int *)L"Unknown";
  if ( v29 )
    v26 = v29;
  if ( (unsigned int)dword_180019000 > 2 )
  {
    v30 = (wchar_t *)v26;
    v28 = XmlAttribute;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)v26,
      (__int64)word_1800155AA,
      v5,
      v6,
      (__int64)&v28,
      (int **)&v30);
  }
  return (unsigned int)XmlAttribute;
}

```

## disassembly

```asm
0x18000b8f8  mov     [rsp-8+arg_10], rbx
0x18000b8fd  mov     [rsp-8+arg_18], rsi
0x18000b902  push    rbp
0x18000b903  push    r12
0x18000b905  push    r13
0x18000b907  push    r14
0x18000b909  push    r15
0x18000b90b  lea     rbp, [rsp-1A0h]
0x18000b913  sub     rsp, 2A0h
0x18000b91a  mov     rax, cs:__security_cookie
0x18000b921  xor     rax, rsp
0x18000b924  mov     [rbp+1C0h+var_30], rax
0x18000b92b  mov     r14, rdx
0x18000b92e  mov     rsi, rcx
0x18000b931  xor     r12d, r12d
0x18000b934  mov     [rsp+2C0h+var_280], r12d
0x18000b939  mov     [rsp+2C0h+var_278], r12
0x18000b93e  mov     [rsp+2C0h+var_258], r12
0x18000b943  mov     [rsp+2C0h+String1], r12
0x18000b948  mov     [rsp+2C0h+var_260], r12
0x18000b94d  mov     rax, [rcx]
0x18000b950  xor     r8d, r8d
0x18000b953  lea     rdx, [rsp+2C0h+var_278]
0x18000b958  mov     rax, [rax+70h]
0x18000b95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b961  mov     ebx, eax
0x18000b963  test    eax, eax
0x18000b965  js      loc_18000BD75
0x18000b96b  mov     ecx, [r14+8]
0x18000b96f  sub     ecx, 1
0x18000b972  jz      loc_18000BD08
0x18000b978  sub     ecx, 1
0x18000b97b  jz      loc_18000BADD
0x18000b981  sub     ecx, 1
0x18000b984  jz      loc_18000BA88
0x18000b98a  cmp     ecx, 1
0x18000b98d  jz      short loc_18000B999
0x18000b98f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b994  jmp     loc_18000BD6B
0x18000b999  mov     rax, [rsp+2C0h+var_278]
0x18000b99e  lea     rcx, aEvent; "Event"
0x18000b9a5  sub     rcx, rax
0x18000b9a8  movzx   edx, word ptr [rax]
0x18000b9ab  movzx   r8d, word ptr [rax+rcx]
0x18000b9b0  sub     edx, r8d
0x18000b9b3  jnz     short loc_18000B9BE
0x18000b9b5  add     rax, 2
0x18000b9b9  test    r8d, r8d
0x18000b9bc  jnz     short loc_18000B9A8
0x18000b9be  test    edx, edx
0x18000b9c0  jnz     loc_18000BD70
0x18000b9c6  mov     rax, [rsi]
0x18000b9c9  mov     rcx, rsi
0x18000b9cc  mov     rax, [rax+0A0h]
0x18000b9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9d8  test    eax, eax
0x18000b9da  jz      loc_18000BD70
0x18000b9e0  lea     r9, [rsp+2C0h+String1]
0x18000b9e5  mov     r8d, 1
0x18000b9eb  lea     rdx, aName; "Name"
0x18000b9f2  mov     rcx, rsi
0x18000b9f5  call    ?GetXmlAttribute@@YAJPEAUIXmlReader@@PEBGW4AttributePresence@@PEAPEBG@Z; GetXmlAttribute(IXmlReader *,ushort const *,AttributePresence,ushort const * *)
0x18000b9fa  mov     ebx, eax
0x18000b9fc  test    eax, eax
0x18000b9fe  js      loc_18000BD75
0x18000ba04  mov     rbx, [r14+10h]
0x18000ba08  cmp     dword ptr [rbx+488h], 12h
0x18000ba0f  jz      loc_18000BD70
0x18000ba15  mov     r15, [rsp+2C0h+String1]
0x18000ba1a  mov     esi, r12d
0x18000ba1d  lea     r13, off_1800134F0; "Uicc_Language"
0x18000ba24  mov     r14d, esi
0x18000ba27  add     r14, r14
0x18000ba2a  mov     rdx, [r13+r14*8+0]; String2
0x18000ba2f  mov     rcx, r15; String1
0x18000ba32  call    cs:__imp__wcsicmp
0x18000ba38  test    eax, eax
0x18000ba3a  jz      short loc_18000BA4D
0x18000ba3c  inc     esi
0x18000ba3e  cmp     esi, 12h
0x18000ba41  jb      short loc_18000BA24
0x18000ba43  mov     ebx, 80070490h
0x18000ba48  jmp     loc_18000BD75
0x18000ba4d  mov     r8d, [r13+r14*8+8]
0x18000ba52  mov     ecx, r12d
0x18000ba55  mov     edx, [rbx+488h]
0x18000ba5b  test    edx, edx
0x18000ba5d  jz      short loc_18000BA75
0x18000ba5f  mov     eax, ecx
0x18000ba61  cmp     [rbx+rax*4+440h], r8d
0x18000ba69  jz      loc_18000BD70
0x18000ba6f  inc     ecx
0x18000ba71  cmp     ecx, edx
0x18000ba73  jb      short loc_18000BA5F
0x18000ba75  mov     [rbx+rdx*4+440h], r8d
0x18000ba7d  inc     dword ptr [rbx+488h]
0x18000ba83  jmp     loc_18000BD6B
0x18000ba88  mov     rax, [rsp+2C0h+var_278]
0x18000ba8d  lea     rcx, aEventlist; "EventList"
0x18000ba94  sub     rcx, rax
0x18000ba97  movzx   edx, word ptr [rax]
0x18000ba9a  movzx   r8d, word ptr [rax+rcx]
0x18000ba9f  sub     edx, r8d
0x18000baa2  jnz     short loc_18000BAAD
0x18000baa4  add     rax, 2
0x18000baa8  test    r8d, r8d
0x18000baab  jnz     short loc_18000BA97
0x18000baad  test    edx, edx
0x18000baaf  jnz     loc_18000BD70
0x18000bab5  mov     rax, [rsi]
0x18000bab8  mov     rcx, rsi
0x18000babb  mov     rax, [rax+0A0h]
0x18000bac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bac7  cmp     eax, 1
0x18000baca  jz      loc_18000BD70
0x18000bad0  mov     dword ptr [r14+8], 4
0x18000bad8  jmp     loc_18000BD6B
0x18000badd  lea     r15, [r14+10h]
0x18000bae1  cmp     [r15], r12
0x18000bae4  jz      short loc_18000BAEB
0x18000bae6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000baeb  mov     rax, [rsp+2C0h+var_278]
0x18000baf0  lea     rdx, aConfigurations; "ConfigurationSource"
0x18000baf7  sub     rdx, rax
0x18000bafa  movzx   ecx, word ptr [rax]
0x18000bafd  movzx   r8d, word ptr [rax+rdx]
0x18000bb02  sub     ecx, r8d
0x18000bb05  jnz     short loc_18000BB10
0x18000bb07  add     rax, 2
0x18000bb0b  test    r8d, r8d
0x18000bb0e  jnz     short loc_18000BAFA
0x18000bb10  test    ecx, ecx
0x18000bb12  jnz     loc_18000BD70
0x18000bb18  mov     rax, [rsi]
0x18000bb1b  mov     rcx, rsi
0x18000bb1e  mov     rax, [rax+0A0h]
0x18000bb25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb2a  cmp     eax, 1
0x18000bb2d  jz      loc_18000BD70
0x18000bb33  lea     r9, [rsp+2C0h+String1]
0x18000bb38  mov     r8d, 1
0x18000bb3e  lea     rdx, aName; "Name"
0x18000bb45  mov     rcx, rsi
0x18000bb48  call    ?GetXmlAttribute@@YAJPEAUIXmlReader@@PEBGW4AttributePresence@@PEAPEBG@Z; GetXmlAttribute(IXmlReader *,ushort const *,AttributePresence,ushort const * *)
0x18000bb4d  mov     ebx, eax
0x18000bb4f  test    eax, eax
0x18000bb51  js      loc_18000BD75
0x18000bb57  lea     r9, [rsp+2C0h+var_260]
0x18000bb5c  mov     r8d, 1
0x18000bb62  lea     rdx, aPath; "Path"
0x18000bb69  mov     rcx, rsi
0x18000bb6c  call    ?GetXmlAttribute@@YAJPEAUIXmlReader@@PEBGW4AttributePresence@@PEAPEBG@Z; GetXmlAttribute(IXmlReader *,ushort const *,AttributePresence,ushort const * *)
0x18000bb71  mov     ebx, eax
0x18000bb73  test    eax, eax
0x18000bb75  js      loc_18000BD75
0x18000bb7b  lea     rdx, [rbp+1C0h+var_240]; unsigned __int16 *
0x18000bb7f  mov     rcx, [rsp+2C0h+var_260]; unsigned __int16 *
0x18000bb84  call    ?TranslatePath@@YAJPEBGPEAGK@Z; TranslatePath(ushort const *,ushort *,ulong)
0x18000bb89  mov     ebx, eax
0x18000bb8b  test    eax, eax
0x18000bb8d  js      loc_18000BD75
0x18000bb93  cmp     [r15], r12
0x18000bb96  jz      short loc_18000BB9E
0x18000bb98  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000bb9d  nop
0x18000bb9e  mov     ecx, 4A0h; Size
0x18000bba3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bba8  mov     rsi, rax
0x18000bbab  mov     [rsp+2C0h+var_270], rax
0x18000bbb0  test    rax, rax
0x18000bbb3  jz      short loc_18000BC1A
0x18000bbb5  mov     dword ptr [rax+8], 1
0x18000bbbc  mov     dword ptr [rax+0Ch], 1
0x18000bbc3  lea     rax, ??_7?$_Ref_count_obj@VCConfigSource@@@std@@6B@; const std::_Ref_count_obj<CConfigSource>::`vftable'
0x18000bbca  mov     [rsi], rax
0x18000bbcd  mov     [rsi+10h], r12d
0x18000bbd1  mov     [rsi+424h], r12
0x18000bbd8  lea     rbx, [rsi+430h]
0x18000bbdf  mov     [rbx], r12
0x18000bbe2  mov     [rbx+8], r12
0x18000bbe6  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::wstring>>::_Buyheadnode(void)
0x18000bbeb  mov     [rbx], rax
0x18000bbee  lea     rbx, [rsi+440h]
0x18000bbf5  mov     [rbx], r12
0x18000bbf8  mov     [rbx+8], r12
0x18000bbfc  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::wstring>>::_Buyheadnode(void)
0x18000bc01  mov     [rbx], rax
0x18000bc04  mov     [rsi+498h], r12d
0x18000bc0b  mov     [rsi+21Ch], r12w
0x18000bc13  mov     [rsi+14h], r12w
0x18000bc18  jmp     short loc_18000BC1D
0x18000bc1a  mov     rsi, r12
0x18000bc1d  mov     [rsp+2C0h+var_248], rsi
0x18000bc22  lea     rax, [rsi+10h]
0x18000bc26  mov     [rsp+2C0h+var_250], rax
0x18000bc2b  lea     rdx, [rsp+2C0h+var_250]
0x18000bc30  mov     rcx, r15
0x18000bc33  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000bc38  nop
0x18000bc39  mov     rbx, [rsp+2C0h+var_248]
0x18000bc3e  test    rbx, rbx
0x18000bc41  jz      short loc_18000BC7B
0x18000bc43  or      eax, 0FFFFFFFFh
0x18000bc46  lock xadd [rbx+8], eax
0x18000bc4b  cmp     eax, 1
0x18000bc4e  jnz     short loc_18000BC7B
0x18000bc50  mov     rax, [rbx]
0x18000bc53  mov     rcx, rbx
0x18000bc56  mov     rax, [rax]
0x18000bc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc5e  or      eax, 0FFFFFFFFh
0x18000bc61  lock xadd [rbx+0Ch], eax
0x18000bc66  cmp     eax, 1
0x18000bc69  jnz     short loc_18000BC7B
0x18000bc6b  mov     rax, [rbx]
0x18000bc6e  mov     rcx, rbx
0x18000bc71  mov     rax, [rax+8]
0x18000bc75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc7a  nop
0x18000bc7b  mov     rcx, [r15]
0x18000bc7e  test    rcx, rcx
0x18000bc81  jz      short loc_18000BD01
0x18000bc83  lea     rax, [rbp+1C0h+var_240]
0x18000bc87  mov     [rsp+2C0h+var_2A0], rax
0x18000bc8c  mov     r9, [rsp+2C0h+String1]
0x18000bc91  mov     r8d, [r14]
0x18000bc94  mov     edx, [r14+4]
0x18000bc98  call    ?InitializeConfigSource@CConfigSource@@QEAAJKW4__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0003@@PEBG1@Z; CConfigSource::InitializeConfigSource(ulong,__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0003,ushort const *,ushort const *)
0x18000bc9d  mov     ebx, eax
0x18000bc9f  test    eax, eax
0x18000bca1  js      loc_18000BD75
0x18000bca7  mov     eax, cs:dword_180019000
0x18000bcad  cmp     eax, 4
0x18000bcb0  jbe     short loc_18000BCF7
0x18000bcb2  mov     eax, [r14+4]
0x18000bcb6  mov     [rsp+2C0h+var_280], eax
0x18000bcba  lea     rax, [rbp+1C0h+var_240]
0x18000bcbe  mov     [rsp+2C0h+var_250], rax
0x18000bcc3  mov     rax, [rsp+2C0h+String1]
0x18000bcc8  mov     [rsp+2C0h+var_270], rax
0x18000bccd  lea     rax, [rsp+2C0h+var_280]
0x18000bcd2  mov     [rsp+2C0h+var_290], rax
0x18000bcd7  lea     rax, [rsp+2C0h+var_250]
0x18000bcdc  mov     [rsp+2C0h+var_298], rax
0x18000bce1  lea     rax, [rsp+2C0h+var_270]
0x18000bce6  mov     [rsp+2C0h+var_2A0], rax
0x18000bceb  lea     rdx, byte_180015577
0x18000bcf2  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000bcf7  mov     dword ptr [r14+8], 3
0x18000bcff  jmp     short loc_18000BD6B
0x18000bd01  mov     ebx, 8007000Eh
0x18000bd06  jmp     short loc_18000BD75
0x18000bd08  mov     rax, [rsp+2C0h+var_278]
0x18000bd0d  lea     rcx, aConfigurations_0; "ConfigurationSourceList"
0x18000bd14  sub     rcx, rax
0x18000bd17  movzx   edx, word ptr [rax]
0x18000bd1a  movzx   r8d, word ptr [rax+rcx]
0x18000bd1f  sub     edx, r8d
0x18000bd22  jnz     short loc_18000BD2D
0x18000bd24  add     rax, 2
0x18000bd28  test    r8d, r8d
0x18000bd2b  jnz     short loc_18000BD17
0x18000bd2d  test    edx, edx
0x18000bd2f  jnz     short loc_18000BD70
0x18000bd31  lea     r9, [rsp+2C0h+var_258]
0x18000bd36  lea     r8d, [rdx+1]
0x18000bd3a  lea     rdx, aVersion; "Version"
0x18000bd41  mov     rcx, rsi
0x18000bd44  call    ?GetXmlAttribute@@YAJPEAUIXmlReader@@PEBGW4AttributePresence@@PEAPEBG@Z; GetXmlAttribute(IXmlReader *,ushort const *,AttributePresence,ushort const * *)
0x18000bd49  test    eax, eax
0x18000bd4b  js      short loc_18000BD70
0x18000bd4d  lea     rdx, a10; "1.0"
0x18000bd54  mov     rcx, [rsp+2C0h+var_258]; String1
0x18000bd59  call    cs:__imp__wcsicmp
0x18000bd5f  test    eax, eax
0x18000bd61  jnz     short loc_18000BD70
0x18000bd63  mov     dword ptr [r14+8], 2
0x18000bd6b  mov     ebx, r12d
0x18000bd6e  jmp     short loc_18000BDBC
0x18000bd70  mov     ebx, 80070057h
0x18000bd75  lea     rcx, aUnknown; "Unknown"
0x18000bd7c  mov     rax, [rsp+2C0h+var_278]
0x18000bd81  test    rax, rax
0x18000bd84  cmovnz  rcx, rax
0x18000bd88  mov     eax, cs:dword_180019000
0x18000bd8e  cmp     eax, 2
0x18000bd91  jbe     short loc_18000BDBC
0x18000bd93  mov     [rsp+2C0h+var_270], rcx
0x18000bd98  mov     [rsp+2C0h+var_280], ebx
0x18000bd9c  lea     rax, [rsp+2C0h+var_270]
0x18000bda1  mov     [rsp+2C0h+var_298], rax
0x18000bda6  lea     rax, [rsp+2C0h+var_280]
0x18000bdab  mov     [rsp+2C0h+var_2A0], rax
0x18000bdb0  lea     rdx, word_1800155AA
0x18000bdb7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18000bdbc  mov     eax, ebx
0x18000bdbe  mov     rcx, [rbp+1C0h+var_30]
0x18000bdc5  xor     rcx, rsp; StackCookie
0x18000bdc8  call    __security_check_cookie
0x18000bdcd  lea     r11, [rsp+2C0h+var_20]
  ... truncated ...
```
