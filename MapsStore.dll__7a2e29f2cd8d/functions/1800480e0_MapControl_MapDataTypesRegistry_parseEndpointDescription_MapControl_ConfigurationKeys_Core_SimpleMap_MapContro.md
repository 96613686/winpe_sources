# MapControl::MapDataTypesRegistry::parseEndpointDescription(MapControl::ConfigurationKeys,Core::SimpleMap<MapControl::ConfigurationKeys,std::shared_ptr<MapControl::EndpointDescription>> *)

- ea: `0x1800480e0`
- end: `0x1800485c4`
- name: `?parseEndpointDescription@MapDataTypesRegistry@MapControl@@AEAA?AV?$Result@UError@MapDataTypesRegistry@MapControl@@V?$shared_ptr@VEndpointDescription@MapControl@@@std@@@Core@@W4ConfigurationKeys@2@PEAV?$SimpleMap@W4ConfigurationKeys@MapControl@@V?$shared_ptr@VEndpointDescription@MapControl@@@std@@@4@@Z`
- size: `1252`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800480e0`
- `0x1800488c8`

## callees

- `0x18000d090`
- `0x18000d49c`
- `0x180012720`
- `0x180013420`
- `0x1800161b0`
- `0x180016548`
- `0x180016d58`
- `0x180017aa8`
- `0x18001b9e0`
- `0x18003dbbc`
- `0x18003eab8`
- `0x18003eb00`
- `0x18003edd0`
- `0x18003ee4c`
- `0x18003ee8c`
- `0x18003ef20`
- `0x1800415b8`
- `0x18004161c`
- `0x180041794`
- `0x1800442c0`
- `0x1800444b8`
- `0x1800457c0`
- `0x180045884`
- `0x180046f3c`
- `0x180047038`
- `0x1800480e0`
- `0x18008d060`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180048136`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180048136`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall MapControl::MapDataTypesRegistry::parseEndpointDescription(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  char isEndpointKey; // di
  unsigned int v9; // r8d
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  std::_Ref_count_base *v14; // rcx
  __int64 v15; // rbx
  unsigned int *Value; // rax
  _DWORD *v17; // rdi
  std::_Ref_count_base *v18; // r14
  unsigned int *v19; // rax
  _QWORD *v20; // r15
  unsigned int *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  std::_Ref_count_base *v25; // r15
  __int64 v26; // rdi
  std::_Ref_count_base *v27; // rcx
  std::_Ref_count_base *v28; // rcx
  std::_Ref_count_base *v29; // rcx
  std::_Ref_count_base *v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v32[2]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v33; // [rsp+50h] [rbp-B0h]
  __int128 v34; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v35[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v36[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v37[24]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v38[32]; // [rsp+C8h] [rbp-38h] BYREF
  char v39; // [rsp+E8h] [rbp-18h]
  _BYTE v40[40]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v41[4]; // [rsp+118h] [rbp+18h] BYREF
  char v42; // [rsp+11Ch] [rbp+1Ch]
  _BYTE v43[8]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v44[4]; // [rsp+128h] [rbp+28h] BYREF
  char v45; // [rsp+12Ch] [rbp+2Ch]
  _BYTE v46[4]; // [rsp+130h] [rbp+30h] BYREF
  char v47; // [rsp+134h] [rbp+34h]
  _BYTE v48[4]; // [rsp+138h] [rbp+38h] BYREF
  char v49; // [rsp+13Ch] [rbp+3Ch]

  v33 = (std::_Ref_count_base *)a2;
  isEndpointKey = MapControl::EndpointDescriptionFormat::isEndpointKey(a3);
  if ( !isEndpointKey && !(unsigned __int8)MapControl::EndpointDescriptionFormat::isOdvsEndpointKey(v9) )
  {
    _o_terminate(v11, v10, v12, v13);
    __debugbreak();
  }
  *(_OWORD *)v31 = 0;
  if ( !(unsigned __int8)Core::SimpleMap<enum MapControl::ConfigurationKeys,std::shared_ptr<MapControl::EndpointDescription>>::getCopy(
                           a4,
                           a3,
                           v31) )
  {
    *(_OWORD *)v32 = 0;
    Core::SimpleMap<enum MapControl::ConfigurationKeys,std::shared_ptr<MapControl::EndpointDescription>>::add(
      a4,
      a3,
      v32);
    if ( v32[1] )
      std::_Ref_count_base::_Decref(v32[1]);
    std::wstring::wstring(v36);
    if ( !(unsigned __int8)MapControl::LocaleMapConfiguration::getValueString(*(_QWORD *)(a1 + 376), a3, v36) )
    {
      *(_BYTE *)(a2 + 16) = 0;
      goto LABEL_9;
    }
    v39 = 0;
    v40[32] = 0;
    v42 = 0;
    v43[4] = 0;
    v45 = 0;
    v47 = 0;
    v49 = 0;
    if ( isEndpointKey )
    {
      if ( (unsigned __int8)MapControl::EndpointDescriptionFormat::tryParseEndpoint(v36, v38) && v39 )
      {
        if ( v45 )
        {
          std::wstring::wstring(v35);
          v15 = *(_QWORD *)(a1 + 376);
          Value = (unsigned int *)Core::Optional<unsigned int>::getValue(v44);
          if ( (unsigned __int8)MapControl::LocaleMapConfiguration::getValueString(v15, *Value, v35) )
            Core::Optional<std::wstring>::operator=(v40, v35);
          std::wstring::_Tidy_deallocate(v35);
        }
        v17 = operator new(0x70u);
        v33 = (std::_Ref_count_base *)v17;
        *(_OWORD *)v17 = 0;
        v17[2] = 1;
        v17[3] = 1;
        *(_QWORD *)v17 = &std::_Ref_count_obj2<MapControl::EndpointDescription>::`vftable';
        std::_Construct_in_place<MapControl::EndpointDescription,Core::Optional<std::wstring> &,Core::Optional<std::wstring> &,Core::Optional<unsigned int> &>(
          v17 + 4,
          v38,
          v40,
          v41);
        v32[0] = (std::_Ref_count_base *)(v17 + 4);
        v32[1] = (std::_Ref_count_base *)v17;
        std::shared_ptr<MapControl::LocalIndex>::operator=(v31, v32);
        if ( v32[1] )
          std::_Ref_count_base::_Decref(v32[1]);
        v18 = v31[1];
LABEL_53:
        Core::SimpleMap<enum MapControl::ConfigurationKeys,std::shared_ptr<MapControl::EndpointDescription>>::add(
          a4,
          a3,
          v31);
        MapControl::EndpointDescriptionFields::~EndpointDescriptionFields((MapControl::EndpointDescriptionFields *)v38);
        std::wstring::_Tidy_deallocate(v36);
        goto LABEL_55;
      }
      goto LABEL_21;
    }
    if ( (unsigned __int8)MapControl::EndpointDescriptionFormat::tryParseOdvsEndpoint(v36, v38) && v39 )
    {
      if ( v47 )
      {
        v19 = (unsigned int *)Core::Optional<unsigned int>::getValue(v46);
        MapControl::MapDataTypesRegistry::parseEndpointDescription(a1, v35, *v19, a4);
        if ( !v35[16] )
        {
          Core::Result<MapControl::MapDataTypesRegistry::Error,std::shared_ptr<MapControl::EndpointDescription>>::getError(v35);
          *(_BYTE *)(a2 + 16) = 0;
LABEL_28:
          Core::Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>::~Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>(v35);
          goto LABEL_22;
        }
        v20 = (_QWORD *)Core::Optional<Core::PresentSharedPtr<MapControl::VersionSnapshot>>::getValue(v35);
        *(_OWORD *)v32 = 0;
        if ( v49 )
        {
          v21 = (unsigned int *)Core::Optional<unsigned int>::getValue(v48);
          MapControl::MapDataTypesRegistry::parseEndpointDescription(a1, v37, *v21, a4);
          if ( !v37[16] )
          {
            Core::Result<MapControl::MapDataTypesRegistry::Error,std::shared_ptr<MapControl::EndpointDescription>>::getError(v37);
            *(_BYTE *)(a2 + 16) = 0;
            Core::Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>::~Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>(v37);
            goto LABEL_28;
          }
          v22 = Core::Optional<Core::PresentSharedPtr<MapControl::VersionSnapshot>>::getValue(v37);
          std::shared_ptr<MapControl::LocalIndex>::operator=(v32, v22);
          Core::Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>::~Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>(v37);
        }
        v23 = _RTDynamicCast_0(
                *v20,
                0,
                &MapControl::EndpointDescription `RTTI Type Descriptor',
                &MapControl::OdvsIndexEndpointDescription `RTTI Type Descriptor',
                0);
        if ( v23 )
        {
          v24 = v20[1];
          if ( v24 )
            _InterlockedIncrement((volatile signed __int32 *)(v24 + 8));
          *(_QWORD *)&v34 = v23;
          v25 = (std::_Ref_count_base *)v20[1];
          *((_QWORD *)&v34 + 1) = v25;
        }
        else
        {
          v34 = 0;
          v25 = (std::_Ref_count_base *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
          v23 = 0;
        }
        if ( v23 )
        {
          v26 = Core::requirePresent<Pal::Stream>(v37, &v34);
          v18 = (std::_Ref_count_base *)operator new(0x90u);
          v33 = v18;
          *(_OWORD *)v18 = 0;
          *((_DWORD *)v18 + 2) = 1;
          *((_DWORD *)v18 + 3) = 1;
          *(_QWORD *)v18 = &std::_Ref_count_obj2<MapControl::OdvsDataEndpointDescription>::`vftable';
          std::_Construct_in_place<MapControl::OdvsDataEndpointDescription,Core::Optional<std::wstring> &,Core::PresentSharedPtr<MapControl::OdvsIndexEndpointDescription>,std::shared_ptr<MapControl::EndpointDescription> &>(
            (char *)v18 + 16,
            v38,
            v26,
            v32);
          v31[0] = (std::_Ref_count_base *)((char *)v18 + 16);
          v27 = v31[1];
          v31[1] = v18;
          if ( v27 )
            std::_Ref_count_base::_Decref(v27);
          Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v37);
          if ( v25 )
            std::_Ref_count_base::_Decref(v25);
          if ( v32[1] )
            std::_Ref_count_base::_Decref(v32[1]);
          Core::Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>::~Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>(v35);
          goto LABEL_53;
        }
        *(_BYTE *)(a2 + 16) = 0;
        if ( v25 )
          std::_Ref_count_base::_Decref(v25);
        if ( v32[1] )
          std::_Ref_count_base::_Decref(v32[1]);
        goto LABEL_28;
      }
      if ( v42 )
      {
        v18 = (std::_Ref_count_base *)operator new(0x78u);
        v33 = v18;
        *(_OWORD *)v18 = 0;
        *((_DWORD *)v18 + 2) = 1;
        *((_DWORD *)v18 + 3) = 1;
        *(_QWORD *)v18 = &std::_Ref_count_obj2<MapControl::OdvsIndexEndpointDescription>::`vftable';
        std::_Construct_in_place<MapControl::OdvsIndexEndpointDescription,Core::Optional<std::wstring> &,Core::Optional<unsigned int> &,Core::Optional<unsigned int> &>(
          (char *)v18 + 16,
          v38,
          v41,
          v43);
        v31[0] = (std::_Ref_count_base *)((char *)v18 + 16);
        v28 = v31[1];
        v31[1] = v18;
        if ( v28 )
          std::_Ref_count_base::_Decref(v28);
        goto LABEL_53;
      }
    }
LABEL_21:
    *(_BYTE *)(a2 + 16) = 0;
LABEL_22:
    MapControl::EndpointDescriptionFields::~EndpointDescriptionFields((MapControl::EndpointDescriptionFields *)v38);
LABEL_9:
    std::wstring::_Tidy_deallocate(v36);
    v14 = v31[1];
    if ( v31[1] )
      goto LABEL_59;
    return a2;
  }
  v18 = v31[1];
LABEL_55:
  v29 = v31[0];
  if ( v31[0] )
  {
    *(_BYTE *)(a2 + 16) = 1;
    *(_QWORD *)a2 = v29;
    *(_QWORD *)(a2 + 8) = v18;
  }
  else
  {
    *(_BYTE *)(a2 + 16) = 0;
    if ( v18 )
    {
      v14 = v18;
LABEL_59:
      std::_Ref_count_base::_Decref(v14);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800480e0  push    rbp
0x1800480e2  push    rbx
0x1800480e3  push    rsi
0x1800480e4  push    rdi
0x1800480e5  push    r12
0x1800480e7  push    r13
0x1800480e9  push    r14
0x1800480eb  push    r15
0x1800480ed  lea     rbp, [rsp-58h]
0x1800480f2  sub     rsp, 158h
0x1800480f9  mov     rax, cs:__security_cookie
0x180048100  xor     rax, rsp
0x180048103  mov     [rbp+90h+var_50], rax
0x180048107  mov     r13, r9
0x18004810a  mov     r12d, r8d
0x18004810d  mov     rsi, rdx
0x180048110  mov     rbx, rcx
0x180048113  mov     [rsp+190h+var_140], rdx
0x180048118  xor     r14d, r14d
0x18004811b  mov     ecx, r8d
0x18004811e  call    ?isEndpointKey@EndpointDescriptionFormat@MapControl@@SA_NW4ConfigurationKeys@2@@Z; MapControl::EndpointDescriptionFormat::isEndpointKey(MapControl::ConfigurationKeys)
0x180048123  mov     dil, al
0x180048126  test    al, al
0x180048128  jnz     short loc_18004813D
0x18004812a  mov     ecx, r8d
0x18004812d  call    ?isOdvsEndpointKey@EndpointDescriptionFormat@MapControl@@SA_NW4ConfigurationKeys@2@@Z; MapControl::EndpointDescriptionFormat::isOdvsEndpointKey(MapControl::ConfigurationKeys)
0x180048132  test    al, al
0x180048134  jnz     short loc_18004813D
0x180048136  call    cs:__imp__o_terminate
0x18004813c  int     3; Trap to Debugger
0x18004813d  xorps   xmm0, xmm0
0x180048140  movdqu  xmmword ptr [rsp+190h+var_160], xmm0
0x180048146  lea     r8, [rsp+190h+var_160]
0x18004814b  mov     edx, r12d
0x18004814e  mov     rcx, r13
0x180048151  call    ?getCopy@?$SimpleMap@W4ConfigurationKeys@MapControl@@V?$shared_ptr@VEndpointDescription@MapControl@@@std@@@Core@@QEBA_NW4ConfigurationKeys@MapControl@@PEAV?$shared_ptr@VEndpointDescription@MapControl@@@std@@@Z; Core::SimpleMap<MapControl::ConfigurationKeys,std::shared_ptr<MapControl::EndpointDescription>>::getCopy(MapControl::ConfigurationKeys,std::shared_ptr<MapControl::EndpointDescription> *)
0x180048156  mov     r15d, 1
0x18004815c  test    al, al
0x18004815e  jnz     loc_180048574
0x180048164  xorps   xmm0, xmm0
0x180048167  movdqu  xmmword ptr [rsp+190h+var_150], xmm0
0x18004816d  lea     r8, [rsp+190h+var_150]
0x180048172  mov     edx, r12d
0x180048175  mov     rcx, r13
0x180048178  call    ?add@?$SimpleMap@W4ConfigurationKeys@MapControl@@V?$shared_ptr@VEndpointDescription@MapControl@@@std@@@Core@@QEAAXW4ConfigurationKeys@MapControl@@$$QEAV?$shared_ptr@VEndpointDescription@MapControl@@@std@@@Z; Core::SimpleMap<MapControl::ConfigurationKeys,std::shared_ptr<MapControl::EndpointDescription>>::add(MapControl::ConfigurationKeys,std::shared_ptr<MapControl::EndpointDescription> &&)
0x18004817d  nop
0x18004817e  mov     rcx, [rsp+190h+var_150+8]; this
0x180048183  test    rcx, rcx
0x180048186  jz      short loc_18004818D
0x180048188  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004818d  lea     rcx, [rbp+90h+var_100]
0x180048191  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180048196  nop
0x180048197  lea     r8, [rbp+90h+var_100]
0x18004819b  mov     edx, r12d
0x18004819e  mov     rcx, [rbx+178h]
0x1800481a5  call    ?getValueString@LocaleMapConfiguration@MapControl@@QEBA_NW4ConfigurationKeys@2@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapControl::LocaleMapConfiguration::getValueString(MapControl::ConfigurationKeys,std::wstring *)
0x1800481aa  test    al, al
0x1800481ac  jnz     short loc_1800481CF
0x1800481ae  mov     [rsi+10h], r14b
0x1800481b2  lea     rcx, [rbp+90h+var_100]
0x1800481b6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800481bb  nop
0x1800481bc  mov     rcx, [rsp+190h+var_160+8]
0x1800481c1  test    rcx, rcx
0x1800481c4  jz      loc_1800485A1
0x1800481ca  jmp     loc_18004859C
0x1800481cf  mov     [rbp+90h+var_A8], r14b
0x1800481d3  mov     [rbp+90h+var_80], r14b
0x1800481d7  mov     [rbp+90h+var_74], r14b
0x1800481db  mov     [rbp+90h+var_6C], r14b
0x1800481df  mov     [rbp+90h+var_64], r14b
0x1800481e3  mov     [rbp+90h+var_5C], r14b
0x1800481e7  mov     [rbp+90h+var_54], r14b
0x1800481eb  lea     rdx, [rbp+90h+var_C8]
0x1800481ef  lea     rcx, [rbp+90h+var_100]
0x1800481f3  test    dil, dil
0x1800481f6  jz      loc_1800482E7
0x1800481fc  call    ?tryParseEndpoint@EndpointDescriptionFormat@MapControl@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUEndpointDescriptionFields@2@@Z; MapControl::EndpointDescriptionFormat::tryParseEndpoint(std::wstring const &,MapControl::EndpointDescriptionFields *)
0x180048201  test    al, al
0x180048203  jz      loc_1800482D5
0x180048209  cmp     [rbp+90h+var_A8], r14b
0x18004820d  jz      loc_1800482D5
0x180048213  cmp     [rbp+90h+var_64], r14b
0x180048217  jz      short loc_180048260
0x180048219  lea     rcx, [rsp+190h+var_120]
0x18004821e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180048223  nop
0x180048224  mov     rbx, [rbx+178h]
0x18004822b  lea     rcx, [rbp+90h+var_68]
0x18004822f  call    ?getValue@?$Optional@I@Core@@QEBAAEBIXZ; Core::Optional<uint>::getValue(void)
0x180048234  lea     r8, [rsp+190h+var_120]
0x180048239  mov     edx, [rax]
0x18004823b  mov     rcx, rbx
0x18004823e  call    ?getValueString@LocaleMapConfiguration@MapControl@@QEBA_NW4ConfigurationKeys@2@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapControl::LocaleMapConfiguration::getValueString(MapControl::ConfigurationKeys,std::wstring *)
0x180048243  test    al, al
0x180048245  jz      short loc_180048256
0x180048247  lea     rdx, [rsp+190h+var_120]
0x18004824c  lea     rcx, [rbp+90h+var_A0]
0x180048250  call    ??4?$Optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Core@@QEAAAEAV01@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Core::Optional<std::wstring>::operator=(std::wstring &&)
0x180048255  nop
0x180048256  lea     rcx, [rsp+190h+var_120]
0x18004825b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048260  mov     ecx, 70h ; 'p'; Size
0x180048265  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004826a  mov     rdi, rax
0x18004826d  mov     [rsp+190h+var_140], rax
0x180048272  xorps   xmm0, xmm0
0x180048275  movups  xmmword ptr [rax], xmm0
0x180048278  mov     [rax+8], r15d
0x18004827c  mov     [rax+0Ch], r15d
0x180048280  lea     rax, ??_7?$_Ref_count_obj2@VEndpointDescription@MapControl@@@std@@6B@; const std::_Ref_count_obj2<MapControl::EndpointDescription>::`vftable'
0x180048287  mov     [rdi], rax
0x18004828a  lea     rbx, [rdi+10h]
0x18004828e  lea     r9, [rbp+90h+var_78]
0x180048292  lea     r8, [rbp+90h+var_A0]
0x180048296  lea     rdx, [rbp+90h+var_C8]
0x18004829a  mov     rcx, rbx
0x18004829d  call    ??$_Construct_in_place@VEndpointDescription@MapControl@@AEAV?$Optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Core@@AEAV34@AEAV?$Optional@I@4@@std@@YAXAEAVEndpointDescription@MapControl@@AEAV?$Optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Core@@1AEAV?$Optional@I@4@@Z; std::_Construct_in_place<MapControl::EndpointDescription,Core::Optional<std::wstring> &,Core::Optional<std::wstring> &,Core::Optional<uint> &>(MapControl::EndpointDescription &,Core::Optional<std::wstring> &,Core::Optional<std::wstring> &,Core::Optional<uint> &)
0x1800482a2  nop
0x1800482a3  mov     [rsp+190h+var_150], rbx
0x1800482a8  mov     [rsp+190h+var_150+8], rdi
0x1800482ad  lea     rdx, [rsp+190h+var_150]
0x1800482b2  lea     rcx, [rsp+190h+var_160]
0x1800482b7  call    ??4?$shared_ptr@VLocalIndex@MapControl@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<MapControl::LocalIndex>::operator=(std::shared_ptr<MapControl::LocalIndex> &&)
0x1800482bc  mov     rcx, [rsp+190h+var_150+8]; this
0x1800482c1  test    rcx, rcx
0x1800482c4  jz      short loc_1800482CB
0x1800482c6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800482cb  mov     r14, [rsp+190h+var_160+8]
0x1800482d0  jmp     loc_18004854E
0x1800482d5  mov     [rsi+10h], r14b
0x1800482d9  lea     rcx, [rbp+90h+var_C8]; this
0x1800482dd  call    ??1EndpointDescriptionFields@MapControl@@QEAA@XZ; MapControl::EndpointDescriptionFields::~EndpointDescriptionFields(void)
0x1800482e2  jmp     loc_1800481B2
0x1800482e7  call    ?tryParseOdvsEndpoint@EndpointDescriptionFormat@MapControl@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUEndpointDescriptionFields@2@@Z; MapControl::EndpointDescriptionFormat::tryParseOdvsEndpoint(std::wstring const &,MapControl::EndpointDescriptionFields *)
0x1800482ec  test    al, al
0x1800482ee  jz      short loc_1800482D5
0x1800482f0  cmp     [rbp+90h+var_A8], r14b
0x1800482f4  jz      short loc_1800482D5
0x1800482f6  cmp     [rbp+90h+var_5C], r14b
0x1800482fa  jz      loc_1800484E8
0x180048300  lea     rcx, [rbp+90h+var_60]
0x180048304  call    ?getValue@?$Optional@I@Core@@QEBAAEBIXZ; Core::Optional<uint>::getValue(void)
0x180048309  mov     r9, r13
0x18004830c  mov     r8d, [rax]
0x18004830f  lea     rdx, [rsp+190h+var_120]
0x180048314  mov     rcx, rbx
0x180048317  call    ?parseEndpointDescription@MapDataTypesRegistry@MapControl@@AEAA?AV?$Result@UError@MapDataTypesRegistry@MapControl@@V?$shared_ptr@VEndpointDescription@MapControl@@@std@@@Core@@W4ConfigurationKeys@2@PEAV?$SimpleMap@W4ConfigurationKeys@MapControl@@V?$shared_ptr@VEndpointDescription@MapControl@@@std@@@4@@Z; MapControl::MapDataTypesRegistry::parseEndpointDescription(MapControl::ConfigurationKeys,Core::SimpleMap<MapControl::ConfigurationKeys,std::shared_ptr<MapControl::EndpointDescription>> *)
0x18004831c  nop
0x18004831d  lea     rcx, [rsp+190h+var_120]
0x180048322  cmp     [rbp+90h+var_110], r14b
0x180048326  jnz     short loc_18004833D
0x180048328  call    ?getError@?$Result@UError@MapDataTypesRegistry@MapControl@@V?$shared_ptr@VEndpointDescription@MapControl@@@std@@@Core@@QEAAAEAUError@MapDataTypesRegistry@MapControl@@XZ; Core::Result<MapControl::MapDataTypesRegistry::Error,std::shared_ptr<MapControl::EndpointDescription>>::getError(void)
0x18004832d  mov     [rsi+10h], r14b
0x180048331  lea     rcx, [rsp+190h+var_120]
0x180048336  call    ??1?$Result@VDecodeError@MapControl@@V?$shared_ptr@VRegionDefinition@MapControl@@@std@@@Core@@QEAA@XZ; Core::Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>::~Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>(void)
0x18004833b  jmp     short loc_1800482D9
0x18004833d  call    ?getValue@?$Optional@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@Core@@QEAAAEAV?$PresentSharedPtr@VVersionSnapshot@MapControl@@@2@XZ; Core::Optional<Core::PresentSharedPtr<MapControl::VersionSnapshot>>::getValue(void)
0x180048342  mov     r15, rax
0x180048345  xorps   xmm0, xmm0
0x180048348  movdqu  xmmword ptr [rsp+190h+var_150], xmm0
0x18004834e  cmp     [rbp+90h+var_54], r14b
0x180048352  jz      short loc_1800483AA
0x180048354  lea     rcx, [rbp+90h+var_58]
0x180048358  call    ?getValue@?$Optional@I@Core@@QEBAAEBIXZ; Core::Optional<uint>::getValue(void)
0x18004835d  mov     r9, r13
0x180048360  mov     r8d, [rax]
0x180048363  lea     rdx, [rbp+90h+var_E0]
0x180048367  mov     rcx, rbx
0x18004836a  call    ?parseEndpointDescription@MapDataTypesRegistry@MapControl@@AEAA?AV?$Result@UError@MapDataTypesRegistry@MapControl@@V?$shared_ptr@VEndpointDescription@MapControl@@@std@@@Core@@W4ConfigurationKeys@2@PEAV?$SimpleMap@W4ConfigurationKeys@MapControl@@V?$shared_ptr@VEndpointDescription@MapControl@@@std@@@4@@Z; MapControl::MapDataTypesRegistry::parseEndpointDescription(MapControl::ConfigurationKeys,Core::SimpleMap<MapControl::ConfigurationKeys,std::shared_ptr<MapControl::EndpointDescription>> *)
0x18004836f  lea     rcx, [rbp+90h+var_E0]
0x180048373  cmp     [rbp+90h+var_D0], r14b
0x180048377  jnz     short loc_18004838E
0x180048379  call    ?getError@?$Result@UError@MapDataTypesRegistry@MapControl@@V?$shared_ptr@VEndpointDescription@MapControl@@@std@@@Core@@QEAAAEAUError@MapDataTypesRegistry@MapControl@@XZ; Core::Result<MapControl::MapDataTypesRegistry::Error,std::shared_ptr<MapControl::EndpointDescription>>::getError(void)
0x18004837e  mov     [rsi+10h], r14b
0x180048382  lea     rcx, [rbp+90h+var_E0]
0x180048386  call    ??1?$Result@VDecodeError@MapControl@@V?$shared_ptr@VRegionDefinition@MapControl@@@std@@@Core@@QEAA@XZ; Core::Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>::~Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>(void)
0x18004838b  nop
0x18004838c  jmp     short loc_180048331
0x18004838e  call    ?getValue@?$Optional@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@Core@@QEAAAEAV?$PresentSharedPtr@VVersionSnapshot@MapControl@@@2@XZ; Core::Optional<Core::PresentSharedPtr<MapControl::VersionSnapshot>>::getValue(void)
0x180048393  mov     rdx, rax
0x180048396  lea     rcx, [rsp+190h+var_150]
0x18004839b  call    ??4?$shared_ptr@VLocalIndex@MapControl@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<MapControl::LocalIndex>::operator=(std::shared_ptr<MapControl::LocalIndex> &&)
0x1800483a0  lea     rcx, [rbp+90h+var_E0]
0x1800483a4  call    ??1?$Result@VDecodeError@MapControl@@V?$shared_ptr@VRegionDefinition@MapControl@@@std@@@Core@@QEAA@XZ; Core::Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>::~Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>(void)
0x1800483a9  nop
0x1800483aa  mov     [rsp+190h+var_170], r14d
0x1800483af  lea     r9, ??_R0?AVOdvsIndexEndpointDescription@MapControl@@@8; MapControl::OdvsIndexEndpointDescription `RTTI Type Descriptor'
0x1800483b6  lea     r8, ??_R0?AVEndpointDescription@MapControl@@@8; MapControl::EndpointDescription `RTTI Type Descriptor'
0x1800483bd  xor     edx, edx
0x1800483bf  mov     rcx, [r15]
0x1800483c2  call    __RTDynamicCast_0
0x1800483c7  test    rax, rax
0x1800483ca  jz      short loc_1800483E9
0x1800483cc  mov     rcx, [r15+8]
0x1800483d0  test    rcx, rcx
0x1800483d3  jz      short loc_1800483D9
0x1800483d5  lock inc dword ptr [rcx+8]
0x1800483d9  mov     qword ptr [rsp+190h+var_138], rax
0x1800483de  mov     r15, [r15+8]
0x1800483e2  mov     qword ptr [rsp+190h+var_138+8], r15
0x1800483e7  jmp     short loc_180048404
0x1800483e9  xorps   xmm0, xmm0
0x1800483ec  xorps   xmm1, xmm1
0x1800483ef  movdqu  [rsp+190h+var_138], xmm1
0x1800483f5  psrldq  xmm0, 8
0x1800483fa  movq    r15, xmm0
0x1800483ff  movq    rax, xmm1
0x180048404  test    rax, rax
0x180048407  jz      loc_1800484BE
0x18004840d  lea     rdx, [rsp+190h+var_138]
0x180048412  lea     rcx, [rbp+90h+var_E0]
0x180048416  call    ??$requirePresent@VStream@Pal@@@Core@@YA?AV?$PresentSharedPtr@VStream@Pal@@@0@AEBV?$shared_ptr@VStream@Pal@@@std@@@Z; Core::requirePresent<Pal::Stream>(std::shared_ptr<Pal::Stream> const &)
0x18004841b  mov     rdi, rax
0x18004841e  mov     ecx, 90h; Size
0x180048423  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048428  mov     r14, rax
0x18004842b  mov     [rsp+190h+var_140], rax
0x180048430  xorps   xmm0, xmm0
0x180048433  movups  xmmword ptr [rax], xmm0
0x180048436  mov     dword ptr [rax+8], 1
0x18004843d  mov     dword ptr [rax+0Ch], 1
0x180048444  lea     rax, ??_7?$_Ref_count_obj2@VOdvsDataEndpointDescription@MapControl@@@std@@6B@; const std::_Ref_count_obj2<MapControl::OdvsDataEndpointDescription>::`vftable'
0x18004844b  mov     [r14], rax
0x18004844e  lea     rbx, [r14+10h]
0x180048452  lea     r9, [rsp+190h+var_150]
0x180048457  mov     r8, rdi
0x18004845a  lea     rdx, [rbp+90h+var_C8]
0x18004845e  mov     rcx, rbx
0x180048461  call    ??$_Construct_in_place@VOdvsDataEndpointDescription@MapControl@@AEAV?$Optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Core@@V?$PresentSharedPtr@VOdvsIndexEndpointDescription@MapControl@@@4@AEAV?$shared_ptr@VEndpointDescription@MapControl@@@std@@@std@@YAXAEAVOdvsDataEndpointDescription@MapControl@@AEAV?$Optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Core@@$$QEAV?$PresentSharedPtr@VOdvsIndexEndpointDescription@MapControl@@@4@AEAV?$shared_ptr@VEndpointDescription@MapControl@@@0@@Z; std::_Construct_in_place<MapControl::OdvsDataEndpointDescription,Core::Optional<std::wstring> &,Core::PresentSharedPtr<MapControl::OdvsIndexEndpointDescription>,std::shared_ptr<MapControl::EndpointDescription> &>(MapControl::OdvsDataEndpointDescription &,Core::Optional<std::wstring> &,Core::PresentSharedPtr<MapControl::OdvsIndexEndpointDescription> &&,std::shared_ptr<MapControl::EndpointDescription> &)
0x180048466  nop
0x180048467  mov     [rsp+190h+var_160], rbx
0x18004846c  mov     rcx, [rsp+190h+var_160+8]; this
0x180048471  mov     [rsp+190h+var_160+8], r14
0x180048476  test    rcx, rcx
0x180048479  jz      short loc_180048481
0x18004847b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180048480  nop
0x180048481  lea     rcx, [rbp+90h+var_E0]
0x180048485  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x18004848a  nop
0x18004848b  test    r15, r15
0x18004848e  jz      short loc_180048499
0x180048490  mov     rcx, r15; this
0x180048493  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180048498  nop
0x180048499  mov     rcx, [rsp+190h+var_150+8]; this
0x18004849e  test    rcx, rcx
0x1800484a1  jz      short loc_1800484A9
0x1800484a3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800484a8  nop
0x1800484a9  lea     rcx, [rsp+190h+var_120]
0x1800484ae  call    ??1?$Result@VDecodeError@MapControl@@V?$shared_ptr@VRegionDefinition@MapControl@@@std@@@Core@@QEAA@XZ; Core::Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>::~Result<MapControl::DecodeError,std::shared_ptr<MapControl::RegionDefinition>>(void)
0x1800484b3  mov     r15d, 1
0x1800484b9  jmp     loc_18004854E
0x1800484be  mov     [rsi+10h], r14b
0x1800484c2  test    r15, r15
0x1800484c5  jz      short loc_1800484D0
0x1800484c7  mov     rcx, r15; this
0x1800484ca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800484cf  nop
0x1800484d0  mov     rcx, [rsp+190h+var_150+8]; this
0x1800484d5  test    rcx, rcx
0x1800484d8  jz      loc_180048331
0x1800484de  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800484e3  jmp     loc_180048331
0x1800484e8  cmp     [rbp+90h+var_74], r14b
0x1800484ec  jz      loc_1800482D5
0x1800484f2  mov     ecx, 78h ; 'x'; Size
0x1800484f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800484fc  mov     r14, rax
0x1800484ff  mov     [rsp+190h+var_140], rax
0x180048504  xorps   xmm0, xmm0
0x180048507  movups  xmmword ptr [rax], xmm0
0x18004850a  mov     [rax+8], r15d
0x18004850e  mov     [rax+0Ch], r15d
0x180048512  lea     rax, ??_7?$_Ref_count_obj2@VOdvsIndexEndpointDescription@MapControl@@@std@@6B@; const std::_Ref_count_obj2<MapControl::OdvsIndexEndpointDescription>::`vftable'
0x180048519  mov     [r14], rax
0x18004851c  lea     rbx, [r14+10h]
0x180048520  lea     r9, [rbp+90h+var_70]
0x180048524  lea     r8, [rbp+90h+var_78]
0x180048528  lea     rdx, [rbp+90h+var_C8]
0x18004852c  mov     rcx, rbx
0x18004852f  call    ??$_Construct_in_place@VOdvsIndexEndpointDescription@MapControl@@AEAV?$Optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Core@@AEAV?$Optional@I@4@AEAV54@@std@@YAXAEAVOdvsIndexEndpointDescription@MapControl@@AEAV?$Optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Core@@AEAV?$Optional@I@4@2@Z; std::_Construct_in_place<MapControl::OdvsIndexEndpointDescription,Core::Optional<std::wstring> &,Core::Optional<uint> &,Core::Optional<uint> &>(MapControl::OdvsIndexEndpointDescription &,Core::Optional<std::wstring> &,Core::Optional<uint> &,Core::Optional<uint> &)
0x180048534  nop
0x180048535  mov     [rsp+190h+var_160], rbx
0x18004853a  mov     rcx, [rsp+190h+var_160+8]; this
0x18004853f  mov     [rsp+190h+var_160+8], r14
0x180048544  test    rcx, rcx
0x180048547  jz      short loc_18004854E
0x180048549  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004854e  lea     r8, [rsp+190h+var_160]
0x180048553  mov     edx, r12d
0x180048556  mov     rcx, r13
0x180048559  call    ?add@?$SimpleMap@W4ConfigurationKeys@MapControl@@V?$shared_ptr@VEndpointDescription@MapControl@@@std@@@Core@@QEAAXW4ConfigurationKeys@MapControl@@AEBV?$shared_ptr@VEndpointDescription@MapControl@@@std@@@Z; Core::SimpleMap<MapControl::ConfigurationKeys,std::shared_ptr<MapControl::EndpointDescription>>::add(MapControl::ConfigurationKeys,std::shared_ptr<MapControl::EndpointDescription> const &)
0x18004855e  nop
0x18004855f  lea     rcx, [rbp+90h+var_C8]; this
0x180048563  call    ??1EndpointDescriptionFields@MapControl@@QEAA@XZ; MapControl::EndpointDescriptionFields::~EndpointDescriptionFields(void)
0x180048568  nop
  ... truncated ...
```
