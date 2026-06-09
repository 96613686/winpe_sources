# MIXmlSerializer::ConvertXmlObjectToCim(uint,_FWXML_ELEMENT *,_MI_Instance * &)

- ea: `0x18000d7c8`
- end: `0x18000ea62`
- name: `?ConvertXmlObjectToCim@MIXmlSerializer@@QEAA_NIPEAU_FWXML_ELEMENT@@AEAPEAU_MI_Instance@@@Z`
- size: `4762`
- prototype: `char __fastcall(MIXmlSerializer *this, char, struct _FWXML_ELEMENT *, struct _MI_Instance **)`
- caller_count: `4`
- callee_count: `28`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000b510`
- `0x18000eae0`
- `0x1800cffe0`
- `0x180140470`

## callees

- `0x180005d10`
- `0x1800089e0`
- `0x18000d7c8`
- `0x18000ea70`
- `0x18000eae0`
- `0x18000f37c`
- `0x18000f700`
- `0x18000f7a0`
- `0x18000f994`
- `0x18000fb60`
- `0x18000fc1c`
- `0x180034f60`
- `0x180035ee0`
- `0x18003a610`
- `0x18003c640`
- `0x18005d800`
- `0x18005f000`
- `0x1800621e0`
- `0x1800f0df0`
- `0x18010d8c6`
- `0x18011a6d4`
- `0x18011d96c`
- `0x180123604`
- `0x180150ec0`
- `0x1801ba176`
- `0x1801ba182`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!wcschr` at `0x18000da20`
- `msvcrt!wcschr` at `0x18000da20`
- `msvcrt!_wcsicmp` at `0x18000e052`
- `msvcrt!_wcsicmp` at `0x18000e052`
- `miutils!OSC_Batch_Get` at `0x18000de83`
- `miutils!OSC_Batch_Get` at `0x18000e989`
- `miutils!OSC_Batch_Get` at `0x18000de83`
- `miutils!OSC_Batch_Get` at `0x18000e989`
- `miutils!Instance_InitDynamic` at `0x18000d8ba`
- `miutils!Instance_InitDynamic` at `0x18000e31a`
- `miutils!Instance_InitDynamic` at `0x18000d8ba`
- `miutils!Instance_InitDynamic` at `0x18000e31a`
- `miutils!Instance_New` at `0x18000e369`
- `miutils!Instance_New` at `0x18000e369`

## string_xrefs

- `0x18000e8d5`: `xmlns`
- `0x18000e8e9`: `xmlns`
- `0x18000dbb1`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000e183`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000e23b`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000e2e5`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000e43e`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000e461`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000e484`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000d9b1`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x18000dfb4`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x18000e723`: `onecore\admin\wmi\wmx\client\remote\xmlserializer.cpp`
- `0x18000e870`: `onecore\admin\wmi\wmx\client\remote\xmlserializer.cpp`

## pseudocode

```c
char __fastcall MIXmlSerializer::ConvertXmlObjectToCim(
        MIXmlSerializer *this,
        char a2,
        struct _FWXML_ELEMENT *a3,
        struct _MI_Instance **a4)
{
  struct _MI_Instance **v4; // rdi
  MIXmlSerializer *v7; // rbx
  char v8; // si
  bool v9; // r15
  __int64 v10; // rax
  int v11; // r12d
  __int64 v12; // rdx
  int j; // esi
  __int64 v14; // r8
  const wchar_t *v15; // rsi
  __int64 v16; // r14
  const wchar_t *v17; // rax
  int v18; // eax
  int i; // r14d
  __int64 v20; // rsi
  const wchar_t *v21; // rax
  const wchar_t *v22; // rax
  const wchar_t *AttributeValue; // rax
  __int64 v24; // rsi
  wchar_t *v25; // r14
  __int64 v26; // rdx
  __int64 v27; // r9
  unsigned __int8 (__fastcall *v28)(MIXmlSerializer *, __int64, __int64, __int64, __int64, struct _MI_Class **, _QWORD); // rax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // r10
  int v32; // r14d
  int v33; // r15d
  __int64 v34; // rcx
  __int64 v35; // r13
  bool v36; // zf
  __int64 v37; // r13
  __int64 v38; // rcx
  __int64 v39; // rdx
  signed int v40; // r12d
  int v41; // r15d
  int v42; // r14d
  int v43; // r15d
  bool v44; // si
  char v45; // al
  enum _MI_Type v46; // r9d
  int v47; // edx
  bool v48; // r8
  wchar_t *v49; // r14
  unsigned int v50; // eax
  struct _MI_Instance *v51; // rcx
  MI_Result (__stdcall *SetElement)(MI_Instance *, const MI_Char *, const MI_Value *, MI_Type, MI_Uint32); // rax
  int v53; // r8d
  struct _FWXML_ELEMENT *v54; // r13
  MIXmlSerializer *v55; // rdx
  unsigned int m; // r14d
  struct _MI_Class *v57; // rcx
  int v59; // eax
  size_t v60; // rsi
  struct _MI_Instance *v61; // r13
  __int64 v62; // rax
  char *v63; // r15
  int n; // r14d
  __int64 v65; // r13
  wchar_t *v66; // rdi
  struct IRequestContext *v67; // r15
  const unsigned __int16 *AttributeName; // rsi
  const wchar_t *EntryName; // r12
  __int64 v70; // rsi
  const wchar_t *v71; // rax
  const wchar_t *v72; // rsi
  const wchar_t *v73; // rax
  wchar_t *v74; // rax
  const wchar_t *v75; // rax
  wchar_t *v76; // rax
  wchar_t *v77; // rax
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  const unsigned __int16 *v81; // r8
  unsigned int v82; // edx
  int v83; // esi
  int v84; // r12d
  const unsigned __int16 *v85; // rax
  const unsigned __int16 *v86; // rax
  int v87; // r15d
  unsigned __int16 *v88; // rax
  __int64 v89; // r11
  __int64 v90; // r11
  bool v91; // [rsp+40h] [rbp-C0h]
  bool v92; // [rsp+41h] [rbp-BFh] BYREF
  bool v93; // [rsp+42h] [rbp-BEh] BYREF
  bool v94; // [rsp+43h] [rbp-BDh]
  enum _MI_Type v95; // [rsp+44h] [rbp-BCh] BYREF
  struct _MI_Class *v96; // [rsp+48h] [rbp-B8h] BYREF
  bool v97; // [rsp+50h] [rbp-B0h] BYREF
  int v98; // [rsp+54h] [rbp-ACh] BYREF
  __int64 ElementName; // [rsp+58h] [rbp-A8h] BYREF
  enum _MI_Type v100; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *String1; // [rsp+68h] [rbp-98h]
  int v102; // [rsp+70h] [rbp-90h]
  int v103; // [rsp+74h] [rbp-8Ch]
  __int64 v104; // [rsp+78h] [rbp-88h] BYREF
  int v105; // [rsp+80h] [rbp-80h]
  int v106; // [rsp+84h] [rbp-7Ch]
  MIXmlSerializer *v107; // [rsp+88h] [rbp-78h]
  struct _MI_Instance *v108; // [rsp+90h] [rbp-70h]
  __int64 v109; // [rsp+98h] [rbp-68h]
  __int64 k; // [rsp+A0h] [rbp-60h]
  struct _MI_Instance **v111; // [rsp+A8h] [rbp-58h]
  struct _FWXML_ELEMENT *v112; // [rsp+B0h] [rbp-50h]
  union _MI_Value Src; // [rsp+B8h] [rbp-48h] BYREF
  struct _MI_Instance *v114[5]; // [rsp+E0h] [rbp-20h] BYREF

  v4 = a4;
  v111 = a4;
  v112 = a3;
  v7 = this;
  v107 = this;
  v8 = a2 & 1;
  v94 = a2 & 1;
  v9 = (a2 & 2) != 0;
  v104 = *((_QWORD *)this + 24);
  ElementName = 0;
  if ( *((_QWORD *)this + 25) && !v8 )
  {
    v10 = *((_QWORD *)this + 23);
    goto LABEL_4;
  }
  ElementName = FwXmlGetElementNameEx(a3);
  if ( !v8 )
  {
LABEL_138:
    if ( *((_DWORD *)v7 + 53) == 3 )
    {
      v78 = *((_QWORD *)v7 + 4);
      if ( v78 )
        (*(void (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v78 + 32LL))(v78, &ElementName, 0);
    }
    goto LABEL_5;
  }
  for ( i = 0; ; ++i )
  {
    if ( i == *((_DWORD *)a3 + 28) )
      goto LABEL_138;
    v20 = *((_QWORD *)a3 + 15) + 104LL * i;
    if ( v20 == -48 )
    {
LABEL_143:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
      continue;
    }
    if ( *(_DWORD *)(v20 + 64) == 41 )
    {
      v21 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v20 + 48);
      if ( !wcsncmp_0(v21, L"http://www.w3.org/2001/XMLSchema-instance", 0x29u) )
      {
        if ( !v20 )
          goto LABEL_143;
        if ( *(_DWORD *)(v20 + 16) == 4 )
        {
          v22 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v20);
          if ( !wcsncmp_0(v22, L"type", 4u) )
            break;
        }
      }
    }
  }
  AttributeValue = (const wchar_t *)FwXmlGetAttributeValue(v20);
  ElementName = (__int64)AttributeValue;
  v24 = -1;
  do
    ++v24;
  while ( AttributeValue[v24] );
  v25 = wcschr(AttributeValue, 0x3Au);
  if ( (int)v24 >= 5
    && (unsigned int)StringCchEquals((const unsigned __int16 *)(ElementName + 2LL * (int)v24 - 10), L"_Type") )
  {
    *(_WORD *)(ElementName + 2LL * (int)v24 - 10) = 0;
    if ( v25 )
    {
      v10 = (__int64)(v25 + 1);
LABEL_4:
      ElementName = v10;
    }
LABEL_5:
    v103 = a2 & 4;
    if ( *((_DWORD *)v7 + 53) == 3 )
    {
      v79 = *((_QWORD *)v7 + 4);
      if ( v79 )
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v79 + 48LL))(v79, &v104);
    }
    v11 = *((_DWORD *)a3 + 28);
    v12 = 0;
    for ( j = 0; j < v11; ++j )
    {
      v16 = *((_QWORD *)a3 + 15) + 104LL * j;
      if ( v16 )
      {
        if ( *(_DWORD *)(v16 + 16) == 14 )
        {
          v17 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v16);
          v18 = wcsncmp_0(v17, L"__cimnamespace", 0xEu);
          v12 = 0;
          if ( !v18 )
          {
            v14 = FwXmlGetAttributeValue(v16);
            v104 = v14;
            goto LABEL_9;
          }
        }
      }
      else
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
        v12 = 0;
      }
    }
    v14 = v104;
LABEL_9:
    v15 = 0;
    v96 = 0;
    if ( (unsigned int)(*((_DWORD *)v7 + 74) - 1) > 0xE || *((int *)qword_1801D2A00 + *((int *)v7 + 74)) <= 2 || v103 )
      goto LABEL_228;
    LOBYTE(v26) = (unsigned int)MIXmlSerializer::GetCurrentSchemaMode(v7, v12, v14, *(_QWORD *)v7) == 8;
    v28 = *(unsigned __int8 (__fastcall **)(MIXmlSerializer *, __int64, __int64, __int64, __int64, struct _MI_Class **, _QWORD))(v27 + 112);
    v30 = v29;
    LOBYTE(v29) = v9;
    if ( v28(v7, v26, v29, v30, v31, &v96, *((_QWORD *)v7 + 33)) )
    {
      if ( !*((_QWORD *)v7 + 25) || v94 )
      {
        if ( !(unsigned int)Instance_New(v96->classDecl, v4) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            WPP_SF_qS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              95,
              (unsigned int)&WPP_526e99e636c13891e083c028203b4f01_Traceguids,
              (_DWORD)v7,
              ElementName);
          goto LABEL_40;
        }
      }
      else if ( !(unsigned int)Instance_InitDynamic(v4, L"__PARAMETERS", 1) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_526e99e636c13891e083c028203b4f01_Traceguids, v7);
        goto LABEL_40;
      }
      goto LABEL_146;
    }
    if ( (*((_BYTE *)v7 + 296) & 3) == 0
      || (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 33) + 152LL))(*((_QWORD *)v7 + 33)) == 14 )
    {
      goto LABEL_147;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_526e99e636c13891e083c028203b4f01_Traceguids, v7);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v7 + 33) + 200LL))(*((_QWORD *)v7 + 33), 1);
LABEL_40:
    if ( !v96 )
    {
LABEL_228:
      if ( !(unsigned int)Instance_InitDynamic(v4, ElementName, 1) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_qS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            97,
            (unsigned int)&WPP_526e99e636c13891e083c028203b4f01_Traceguids,
            (_DWORD)v7,
            ElementName);
        goto LABEL_41;
      }
    }
    else
    {
LABEL_41:
      if ( !((unsigned int (__fastcall *)(struct _MI_Instance *, _QWORD))(*v4)->ft->SetServerName)(
              *v4,
              *((_QWORD *)v7 + 28))
        && (!v104 || !((unsigned int (__fastcall *)(struct _MI_Instance *))(*v4)->ft->SetNameSpace)(*v4)) )
      {
        v32 = 0;
        v33 = *((_DWORD *)a3 + 32);
        v105 = v33;
        v34 = *((_QWORD *)a3 + 17);
        for ( k = v34; ; v34 = k )
        {
          v102 = v32;
          if ( v32 >= v33 )
          {
            v54 = v112;
            v55 = (MIXmlSerializer *)*((_QWORD *)v112 + 15);
            v107 = v55;
            for ( m = 0; m < *((_DWORD *)v54 + 28); ++m )
            {
              v67 = (MIXmlSerializer *)((char *)v55 + 104 * (int)m);
              AttributeName = (const unsigned __int16 *)FwXmlGetAttributeNameEx(v67);
              v108 = (struct _MI_Instance *)FwXmlGetAttributeValue(v67);
              EntryName = (const wchar_t *)FwXmlGetEntryNameEx((char *)v67 + 48);
              if ( !EntryName )
                WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x83u, L"131", 0x54Fu, 0);
              if ( wcscmp_0(EntryName, L"http://www.w3.org/2001/XMLSchema-instance") )
              {
                v85 = (const unsigned __int16 *)FwXmlGetEntryNameEx((char *)v67 + 24);
                if ( !(unsigned int)StringCchEquals(v85, L"xml") )
                {
                  v86 = (const unsigned __int16 *)FwXmlGetEntryNameEx((char *)v67 + 24);
                  if ( !(unsigned int)StringCchEquals(v86, L"xmlns")
                    && !(unsigned int)StringCchEquals(AttributeName, L"xmlns")
                    && !(unsigned int)StringCchEquals(AttributeName, L"__cimnamespace")
                    && !(unsigned int)StringCchEquals(AttributeName, L"IsArray")
                    && !(unsigned int)StringCchEquals(AttributeName, L"IsNullArray")
                    && !(unsigned int)StringCchEquals(AttributeName, L"IsEmptyArray")
                    && !(unsigned int)StringCchEquals(AttributeName, L"IsCIM_Error") )
                  {
                    v87 = *((_DWORD *)v67 + 4) + 14;
                    v88 = (unsigned __int16 *)OSC_Batch_Get((*v4)->reserved[0], 2LL * v87);
                    if ( !v88
                      || (StringCchCopyW(v88, v87, L"__attribute__"),
                          StringCchCopyW((unsigned __int16 *)(v89 + 26), v87 - 13, AttributeName),
                          memset(&v114[1], 0, 32),
                          v114[0] = v108,
                          ((unsigned int (__fastcall *)(struct _MI_Instance *, __int64, struct _MI_Instance **, __int64, int))(*v4)->ft->AddElement)(
                            *v4,
                            v90,
                            v114,
                            13,
                            *((_DWORD *)v7 + 73) | 0x2000000)) )
                    {
                      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 33) + 24LL))(*((_QWORD *)v7 + 33));
                      ((void (__fastcall *)(struct _MI_Instance *))(*v4)->ft->Destruct)(*v4);
                      *v4 = 0;
                      goto LABEL_147;
                    }
                  }
                }
              }
              v55 = v107;
              v54 = v112;
            }
            v57 = v96;
            v96 = 0;
            if ( v57 && v57->ft )
              ((void (*)(void))v57->ft->Delete)();
            return 1;
          }
          v35 = 152LL * v32;
          v36 = v34 + v35 == 0;
          v37 = v34 + v35;
          v109 = v37;
          if ( v36 )
          {
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x5D8u, L"1496", 0x54Fu, 0);
            String1 = 0;
            v38 = v37 + 48;
          }
          else
          {
            v77 = (wchar_t *)FwXmlGetEntryNameEx(v37);
            String1 = v77;
            v38 = v37 + 48;
            if ( v37 == -48 )
            {
              WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x600u, L"1536", 0x54Fu, 0);
              goto LABEL_52;
            }
            String1 = v77;
          }
          v39 = *(_QWORD *)(v38 + 8);
          if ( v39 == -1 )
          {
            v15 = *(const wchar_t **)v38;
          }
          else
          {
            if ( !*(_QWORD *)v38 )
              goto LABEL_51;
            v15 = (const wchar_t *)(**(_QWORD **)v38 + 2 * v39);
          }
          if ( v15 )
          {
            v15[*(unsigned int *)(v38 + 16)] = 0;
            goto LABEL_52;
          }
LABEL_51:
          v15 = &Class;
LABEL_52:
          v40 = 1;
          v41 = v33 - 1;
          if ( v102 != v41 )
          {
            v65 = k + 152;
            v66 = String1;
            do
            {
              if ( !(unsigned int)FwXmlCompareElementName(v65 + 152LL * v32, v66, v15, 0) )
                break;
              ++v40;
              ++v32;
            }
            while ( v32 != v41 );
            v7 = v107;
            v4 = v111;
            v37 = v109;
          }
          v42 = 0;
          v93 = 0;
          v91 = v40 > 1;
          v95 = MI_STRING;
          if ( v96 )
          {
            if ( !MIXmlSerializer::GetTypeAndOctet(v7, v96, String1, &v95, &v93, v94) )
            {
              ((void (__fastcall *)(struct _MI_Instance *))(*v4)->ft->Destruct)(*v4);
              *v4 = 0;
              if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 33) + 144LL))(*((_QWORD *)v7 + 33)) )
              {
                v81 = L"4545";
                v82 = 4545;
                goto LABEL_213;
              }
              goto LABEL_147;
            }
            if ( v95 < MI_BOOLEANA )
            {
              if ( v40 > 1 )
              {
                ((void (__fastcall *)(struct _MI_Instance *))(*v4)->ft->Destruct)(*v4);
                *v4 = 0;
                (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v7 + 33) + 72LL))(
                  *((_QWORD *)v7 + 33),
                  2150859233LL);
                goto LABEL_147;
              }
            }
            else if ( v93 && v95 == MI_UINT8A )
            {
              v91 = 0;
            }
            else
            {
              v91 = 1;
              v95 -= 16;
            }
          }
          else
          {
            v91 = v40 > 1;
          }
          memset(&Src, 0, sizeof(Src));
          v92 = 0;
          if ( !MIXmlSerializer::ConvertXmlPropertyToCim(
                  (struct IRequestContext **)v7,
                  v96 != 0,
                  (struct _FWXML_ELEMENT *)v37,
                  &v95,
                  (struct _MI_Instance **)&Src,
                  &v92,
                  &v93,
                  *v4) )
          {
            ((void (__fastcall *)(struct _MI_Instance *))(*v4)->ft->Destruct)(*v4);
            *v4 = 0;
            if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 33) + 144LL))(*((_QWORD *)v7 + 33)) )
            {
              v81 = L"4579";
              v82 = 4579;
LABEL_213:
              WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\xmlserializer.cpp", v82, v81, 0x54Fu, 0);
            }
LABEL_147:
            AutoCleanup<AutoMIClass,_MI_Class *>::ReleasePtr(&v96);
            return 0;
          }
          v43 = *(_DWORD *)(v37 + 112);
          while ( 1 )
          {
            if ( v42 >= v43 )
              goto LABEL_58;
            v70 = *(_QWORD *)(v37 + 120) + 104LL * v42;
            if ( !v70 )
            {
              WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
              WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
              WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
              goto LABEL_124;
            }
            if ( *(_DWORD *)(v70 + 16) != 7 )
              break;
            v73 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v70);
            if ( wcsncmp_0(v73, L"IsArray", 7u) )
              goto LABEL_113;
            v74 = (wchar_t *)FwXmlGetAttributeValue(v70);
            if ( (unsigned int)StringCchEqualsCI(v74, (wchar_t *)L"true") )
              v91 = 1;
LABEL_124:
            ++v42;
          }
          if ( *(_DWORD *)(v70 + 16) == 11 )
          {
            v75 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v70);
            if ( !wcsncmp_0(v75, L"IsNullArray", 0xBu) )
            {
              v76 = (wchar_t *)FwXmlGetAttributeValue(v70);
              if ( (unsigned int)StringCchEqualsCI(v76, (wchar_t *)L"true") )
              {
                v44 = 1;
                v92 = 1;
                goto LABEL_119;
              }
LABEL_58:
              v44 = v92;
              v45 = v91;
              goto LABEL_59;
            }
          }
LABEL_113:
          if ( *(_DWORD *)(v70 + 16) != 12 )
            goto LABEL_124;
          v71 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v70);
          if ( wcsncmp_0(v71, L"IsEmptyArray", 0xCu) )
            goto LABEL_124;
          v72 = (const wchar_t *)FwXmlGetAttributeValue(v70);
          if ( !v72 )
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x8Bu, L"139", 0x54Fu, 0);
          if ( _wcsicmp(v72, L"true") )
            goto LABEL_58;
          v44 = 0;
          v92 = 0;
LABEL_119:
          v91 = 1;
          v45 = 1;
          v40 = 0;
LABEL_59:
          if ( v45 )
          {
            if ( *((_BYTE *)v7 + 301) )
            {
              if ( v40 == 1 )
              {
                v44 = 0;
                v92 = 0;
              }
            }
            else
            {
              if ( v44 )
                v40 = 0;
              v45 = v91;
            }
          }
          v46 = v95;
          if ( v93 && v95 == MI_STRINGA )
          {
            v91 = 1;
LABEL_87:
            if ( v40 > 0 )
            {
              if ( v95 >= MI_BOOLEANA )
              {
                v46 = v95 - 16;
                v95 -= 16;
              }
              v59 = MIXmlSerializer::SizeOfType(v46);
              v60 = v59;
              v106 = v59;
              v61 = *v4;
              if ( *v4 )
                v62 = OSC_Batch_Get(v61->reserved[0], v40 * v59);
              else
                v62 = WSManMemory::Alloc(v40 * v59, 0, 0);
              v63 = (char *)v62;
              if ( v62 )
              {
                for ( n = 1; n < v40; ++n )
                {
                  v100 = v95;
                  memset(v114, 0, sizeof(v114));
                  v97 = 0;
                  v93 = 0;
                  if ( !MIXmlSerializer::ConvertXmlPropertyToCim(
                          (struct IRequestContext **)v7,
                          1,
                          (struct _FWXML_ELEMENT *)(v109 + 152LL * n),
                          &v100,
                          v114,
                          &v97,
                          &v93,
                          v61) )
                  {
                    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 33) + 152LL))(*((_QWORD *)v7 + 33)) == -2144108063 )
                      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v7 + 33) + 72LL))(
                        *((_QWORD *)v7 + 33),
                        2150858817LL);
                    goto LABEL_194;
                  }
                  memcpy_0(&v63[(int)v60 * n], v114, v60);
                }
                if ( n == v40 )
                {
                  memcpy_0(v63, &Src, v60);
                  v46 = v95 + 16;
                  Src.uint64 = (MI_Uint64)v63;
                  Src.datetime.u.timestamp.month = v40;
                  v44 = v92;
                  goto LABEL_97;
                }
LABEL_194:
                if ( (unsigned int)(v95 - 14) <= 1 )
                {
                  v83 = 1;
                  if ( n > 1 )
                  {
                    v84 = v106;
                    do
                    {
                      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v63[v84 * v83] + 8LL))(*(_QWORD *)&v63[v84 * v83]);
                      ++v83;
                    }
                    while ( v83 < n );
                    v4 = v111;
                  }
                }
                if ( !v61 )
                  WSManMemory::Free(v63, 0);
                if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 33) + 144LL))(*((_QWORD *)v7 + 33)) )
                  WSManError(
                    (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\xmlserializer.cpp",
                    0x1376u,
                    L"4982",
                    0x54Fu,
                    0);
              }
              else
              {
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 33) + 24LL))(*((_QWORD *)v7 + 33));
              }
              ((void (__fastcall *)(struct _MI_Instance *))(*v4)->ft->Destruct)(*v4);
              *v4 = 0;
              if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 33) + 144LL))(*((_QWORD *)v7 + 33)) )
              {
                v81 = L"4661";
                v82 = 4661;
                goto LABEL_213;
              }
              goto LABEL_147;
            }
            if ( v95 < MI_BOOLEANA )
            {
              v46 = v95 + 16;
LABEL_97:
              v95 = v46;
            }
          }
          else if ( v45 )
          {
            goto LABEL_87;
          }
          v47 = 0x2000000;
          v98 = 0x2000000;
          v48 = v94;
          if ( v94 || (v80 = *((_QWORD *)v7 + 4)) == 0 || v96 )
          {
            v49 = String1;
          }
          else
          {
            v49 = String1;
            (*(void (__fastcall **)(__int64, wchar_t *, _QWORD, _QWORD, int *, _QWORD))(*(_QWORD *)v80 + 88LL))(
              v80,
              String1,
              0,
              0,
              &v98,
              0);
            v46 = v95;
            v47 = v98;
            v48 = v94;
          }
          if ( v91 && !v40 )
          {
            Src.datetime.u.timestamp.month = 0;
            Src.uint64 = 0;
          }
          if ( v44 )
            v47 |= 0x20000000u;
          if ( v46 == MI_STRING )
            v50 = *((_DWORD *)v7 + 73);
          else
            v50 = 0x80000000;
          v98 = v50 | v47;
          v15 = 0;
          if ( v96 && (!*((_QWORD *)v7 + 25) || v48) )
          {
            v51 = *v4;
            SetElement = (*v4)->ft->SetElement;
          }
          else
          {
            if ( v103 )
            {
              if ( (unsigned int)StringCchEqualsCI(v49, (wchar_t *)L"CIMStatusCode") )
              {
                if ( v95 == MI_STRING )
                {
                  if ( Src.uint64 )
                  {
                    v100 = MI_BOOLEAN;
                    if ( (unsigned int)StringToDword(Src.string, (unsigned int *)&v100) )
                    {
                      v95 = MI_UINT32;
                      Src.uint32 = v100;
                    }
                  }
                }
              }
            }
            v51 = *v4;
            SetElement = (*v4)->ft->AddElement;
          }
          v53 = ((__int64 (__fastcall *)(struct _MI_Instance *, wchar_t *, union _MI_Value *))SetElement)(
                  v51,
                  v49,
                  &Src);
          if ( v53 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              WPP_SF_qLd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                98,
                &WPP_526e99e636c13891e083c028203b4f01_Traceguids,
                v7,
                v53,
                v95);
            MIXmlSerializer::DiscardCimProperty(v95, &Src);
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 33) + 24LL))(*((_QWORD *)v7 + 33));
            ((void (__fastcall *)(struct _MI_Instance *))(*v4)->ft->Destruct)(*v4);
            *v4 = 0;
            if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 33) + 144LL))(*((_QWORD *)v7 + 33)) )
              WSManError(
                (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\xmlserializer.cpp",
                0x1281u,
                L"4737",
                0x54Fu,
                0);
            goto LABEL_147;
          }
          if ( !v40 )
            v40 = 1;
          v32 = v40 + v102;
          v33 = v105;
        }
      }
      ((void (__fastcall *)(struct _MI_Instance *))(*v4)->ft->Destruct)(*v4);
      *v4 = 0;
    }
LABEL_146:
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 33) + 24LL))(*((_QWORD *)v7 + 33));
    goto LABEL_147;
  }
  (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)v7 + 33) + 64LL))(
    *((_QWORD *)v7 + 33),
    2150858817LL,
    1077134382,
    ElementName);
  return 0;
}

```

## disassembly

```asm
0x18000d7c8  mov     [rsp-8+arg_8], rbx
0x18000d7cd  push    rbp
0x18000d7ce  push    rsi
0x18000d7cf  push    rdi
0x18000d7d0  push    r12
0x18000d7d2  push    r13
0x18000d7d4  push    r14
0x18000d7d6  push    r15
0x18000d7d8  lea     rbp, [rsp-10h]
0x18000d7dd  sub     rsp, 110h
0x18000d7e4  mov     rax, cs:__security_cookie
0x18000d7eb  xor     rax, rsp
0x18000d7ee  mov     [rbp+40h+var_38], rax
0x18000d7f2  mov     rdi, r9
0x18000d7f5  mov     [rbp+40h+var_98], r9
0x18000d7f9  mov     r13, r8
0x18000d7fc  mov     [rbp+40h+var_90], r8
0x18000d800  mov     r12d, edx
0x18000d803  mov     rbx, rcx
0x18000d806  mov     [rbp+40h+var_B8], rcx
0x18000d80a  mov     sil, dl
0x18000d80d  mov     eax, 1
0x18000d812  and     sil, al
0x18000d815  mov     [rsp+140h+var_FD], sil
0x18000d81a  mov     r15d, edx
0x18000d81d  shr     r15d, 1
0x18000d820  and     r15b, al
0x18000d823  mov     rax, [rcx+0C0h]
0x18000d82a  mov     [rsp+140h+var_C8], rax
0x18000d82f  xor     r8d, r8d
0x18000d832  mov     [rsp+140h+var_E8], r8
0x18000d837  cmp     [rcx+0C8h], r8
0x18000d83e  jz      loc_18000D95F
0x18000d844  test    sil, sil
0x18000d847  jnz     loc_18000D95F
0x18000d84d  mov     rax, [rcx+0B8h]
0x18000d854  mov     [rsp+140h+var_E8], rax
0x18000d859  and     r12d, 4
0x18000d85d  mov     [rsp+140h+var_CC], r12d
0x18000d862  cmp     dword ptr [rbx+0D4h], 3
0x18000d869  jz      loc_18000E2AB
0x18000d86f  mov     r12d, [r13+70h]
0x18000d873  xor     edx, edx
0x18000d875  mov     esi, edx
0x18000d877  cmp     esi, r12d
0x18000d87a  jl      loc_18000D907
0x18000d880  mov     r8, [rsp+140h+var_C8]
0x18000d885  xor     esi, esi
0x18000d887  mov     [rsp+140h+var_F8], rsi
0x18000d88c  movsxd  rcx, dword ptr [rbx+128h]
0x18000d893  lea     eax, [rcx-1]
0x18000d896  lea     r14, WPP_GLOBAL_Control
0x18000d89d  mov     r12d, 400h
0x18000d8a3  cmp     eax, 0Eh
0x18000d8a6  jbe     loc_18000E194
0x18000d8ac  mov     r8d, 1
0x18000d8b2  mov     rdx, [rsp+140h+var_E8]
0x18000d8b7  mov     rcx, rdi
0x18000d8ba  call    cs:__imp_Instance_InitDynamic
0x18000d8c0  test    eax, eax
0x18000d8c2  jnz     loc_18000E286
0x18000d8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8cf  cmp     rcx, r14
0x18000d8d2  jz      loc_18000DB2D
0x18000d8d8  test    [rcx+1Ch], r12d
0x18000d8dc  jz      loc_18000DB2D
0x18000d8e2  lea     edx, [rax+61h]
0x18000d8e5  mov     rax, [rsp+140h+var_E8]
0x18000d8ea  mov     [rsp+140h+var_120], rax
0x18000d8ef  mov     r9, rbx
0x18000d8f2  lea     r8, WPP_526e99e636c13891e083c028203b4f01_Traceguids
0x18000d8f9  mov     rcx, [rcx+10h]
0x18000d8fd  call    WPP_SF_qS
0x18000d902  jmp     loc_18000DB2D
0x18000d907  movsxd  rax, esi
0x18000d90a  imul    r14, rax, 68h ; 'h'
0x18000d90e  add     r14, [r13+78h]
0x18000d912  jz      loc_18000E2CE
0x18000d918  cmp     dword ptr [r14+10h], 0Eh
0x18000d91d  jnz     loc_18000E2F3
0x18000d923  mov     rcx, r14
0x18000d926  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18000d92b  mov     rcx, rax; String1
0x18000d92e  mov     r8d, 0Eh; MaxCount
0x18000d934  lea     rdx, aCimnamespace; "__cimnamespace"
0x18000d93b  call    wcsncmp_0
0x18000d940  xor     edx, edx
0x18000d942  test    eax, eax
0x18000d944  jnz     loc_18000E2F3
0x18000d94a  mov     rcx, r14
0x18000d94d  call    FwXmlGetAttributeValue
0x18000d952  mov     r8, rax
0x18000d955  mov     [rsp+140h+var_C8], rax
0x18000d95a  jmp     loc_18000D885
0x18000d95f  mov     rcx, r13; struct IRequestContext *
0x18000d962  call    FwXmlGetElementNameEx
0x18000d967  mov     [rsp+140h+var_E8], rax
0x18000d96c  xor     r8d, r8d
0x18000d96f  test    sil, sil
0x18000d972  jz      loc_18000E1AD
0x18000d978  mov     r14d, r8d
0x18000d97b  cmp     r14d, [r13+70h]
0x18000d97f  jz      loc_18000E1AD
0x18000d985  movsxd  rax, r14d
0x18000d988  imul    rsi, rax, 68h ; 'h'
0x18000d98c  add     rsi, [r13+78h]
0x18000d990  lea     rcx, [rsi+30h]
0x18000d994  test    rcx, rcx
0x18000d997  jz      loc_18000E224
0x18000d99d  cmp     dword ptr [rcx+10h], 29h ; ')'
0x18000d9a1  jnz     short loc_18000D9D3
0x18000d9a3  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18000d9a8  mov     rcx, rax; String1
0x18000d9ab  mov     r8d, 29h ; ')'; MaxCount
0x18000d9b1  lea     rdx, aHttpWwwW3Org20_0; "http://www.w3.org/2001/XMLSchema-instan"...
0x18000d9b8  call    wcsncmp_0
0x18000d9bd  xor     r8d, r8d
0x18000d9c0  test    eax, eax
0x18000d9c2  jnz     short loc_18000D9D3
0x18000d9c4  test    rsi, rsi
0x18000d9c7  jz      loc_18000E224
0x18000d9cd  cmp     dword ptr [rsi+10h], 4
0x18000d9d1  jz      short loc_18000D9D8
0x18000d9d3  inc     r14d
0x18000d9d6  jmp     short loc_18000D97B
0x18000d9d8  mov     rcx, rsi
0x18000d9db  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18000d9e0  mov     rcx, rax; String1
0x18000d9e3  mov     r8d, 4; MaxCount
0x18000d9e9  lea     rdx, aType_0; "type"
0x18000d9f0  call    wcsncmp_0
0x18000d9f5  xor     r8d, r8d
0x18000d9f8  test    eax, eax
0x18000d9fa  jnz     short loc_18000D9D3
0x18000d9fc  mov     rcx, rsi
0x18000d9ff  call    FwXmlGetAttributeValue
0x18000da04  mov     [rsp+140h+var_E8], rax
0x18000da09  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000da0d  xor     ecx, ecx
0x18000da0f  inc     rsi
0x18000da12  cmp     [rax+rsi*2], cx
0x18000da16  jnz     short loc_18000DA0F
0x18000da18  mov     edx, 3Ah ; ':'; Ch
0x18000da1d  mov     rcx, rax; Str
0x18000da20  call    cs:__imp_wcschr
0x18000da26  mov     r14, rax
0x18000da29  cmp     esi, 5
0x18000da2c  jl      loc_18000E24F
0x18000da32  movsxd  rsi, esi
0x18000da35  mov     rcx, [rsp+140h+var_E8]
0x18000da3a  lea     rcx, [rcx+rsi*2]
0x18000da3e  add     rcx, 0FFFFFFFFFFFFFFF6h; unsigned __int16 *
0x18000da42  lea     rdx, aType; "_Type"
0x18000da49  call    ?StringCchEquals@@YAHPEBG0@Z; StringCchEquals(ushort const *,ushort const *)
0x18000da4e  xor     r8d, r8d
0x18000da51  test    eax, eax
0x18000da53  jz      loc_18000E24F
0x18000da59  mov     rcx, [rsp+140h+var_E8]
0x18000da5e  mov     [rcx+rsi*2-0Ah], r8w
0x18000da64  test    r14, r14
0x18000da67  jz      loc_18000D859
0x18000da6d  lea     rax, [r14+2]
0x18000da71  jmp     loc_18000D854
0x18000da76  cmp     [rsp+140h+var_CC], esi
0x18000da7a  jnz     loc_18000D8AC
0x18000da80  mov     r10, [rsp+140h+var_E8]
0x18000da85  mov     r9, [rbx]
0x18000da88  mov     rcx, rbx
0x18000da8b  call    ?GetCurrentSchemaMode@MIXmlSerializer@@QEBA?AW4SchemaMode@1@XZ; MIXmlSerializer::GetCurrentSchemaMode(void)
0x18000da90  cmp     eax, 8
0x18000da93  setz    dl
0x18000da96  mov     rax, [r9+70h]
0x18000da9a  mov     rcx, [rbx+108h]
0x18000daa1  mov     [rsp+140h+var_110], rcx
0x18000daa6  lea     rcx, [rsp+140h+var_F8]
0x18000daab  mov     [rsp+140h+var_118], rcx
0x18000dab0  mov     [rsp+140h+var_120], r10
0x18000dab5  mov     r9, r8
0x18000dab8  mov     r8b, r15b
0x18000dabb  mov     rcx, rbx
0x18000dabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dac3  test    al, al
0x18000dac5  jnz     loc_18000E2FA
0x18000dacb  test    byte ptr [rbx+128h], 3
0x18000dad2  jz      loc_18000E29A
0x18000dad8  mov     rcx, [rbx+108h]
0x18000dadf  mov     rax, [rcx]
0x18000dae2  mov     rax, [rax+98h]
0x18000dae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daee  cmp     eax, 0Eh
0x18000daf1  jz      loc_18000E29A
0x18000daf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dafe  cmp     rcx, r14
0x18000db01  jnz     loc_18000E3B6
0x18000db07  mov     rcx, [rbx+108h]
0x18000db0e  mov     rax, [rcx]
0x18000db11  mov     edx, 1
0x18000db16  mov     rax, [rax+0C8h]
0x18000db1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db22  cmp     [rsp+140h+var_F8], rsi
0x18000db27  jz      loc_18000D8AC
0x18000db2d  mov     rcx, [rdi]
0x18000db30  mov     rax, [rcx]
0x18000db33  mov     rdx, [rbx+0E0h]
0x18000db3a  mov     rax, [rax+80h]
0x18000db41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db46  test    eax, eax
0x18000db48  jnz     loc_18000E274
0x18000db4e  mov     rdx, [rsp+140h+var_C8]
0x18000db53  test    rdx, rdx
0x18000db56  jnz     loc_18000E3DD
0x18000db5c  mov     r14d, esi
0x18000db5f  mov     r15d, [r13+80h]
0x18000db66  mov     [rbp+40h+var_C0], r15d
0x18000db6a  mov     rcx, [r13+88h]
0x18000db71  mov     [rbp+40h+var_A0], rcx
0x18000db75  mov     [rsp+140h+var_D0], r14d
0x18000db7a  cmp     r14d, r15d
0x18000db7d  jge     loc_18000DD83
0x18000db83  movsxd  rax, r14d
0x18000db86  imul    r13, rax, 98h
0x18000db8d  add     r13, rcx
0x18000db90  mov     [rbp+40h+var_A8], r13
0x18000db94  jnz     loc_18000E14C
0x18000db9a  mov     [rsp+140h+var_120], rsi; struct IRequestContext *
0x18000db9f  mov     r9d, 54Fh; unsigned int
0x18000dba5  lea     r8, a1496; "1496"
0x18000dbac  mov     edx, 5D8h; unsigned int
0x18000dbb1  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x18000dbb8  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18000dbbd  mov     [rsp+140h+String1], rsi
0x18000dbc2  lea     rcx, [r13+30h]
0x18000dbc6  mov     rdx, [rcx+8]
0x18000dbca  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18000dbce  jz      loc_18000E127
0x18000dbd4  mov     rax, [rcx]
0x18000dbd7  test    rax, rax
0x18000dbda  jz      short loc_18000DBEE
0x18000dbdc  mov     rax, [rax]
0x18000dbdf  lea     rsi, [rax+rdx*2]
0x18000dbe3  xor     eax, eax
0x18000dbe5  test    rsi, rsi
0x18000dbe8  jnz     loc_18000DDE5
0x18000dbee  lea     rsi, Class
0x18000dbf5  mov     r12d, 1
0x18000dbfb  dec     r15d
0x18000dbfe  cmp     [rsp+140h+var_D0], r15d
0x18000dc03  jnz     loc_18000DF16
0x18000dc09  xor     r14d, r14d
0x18000dc0c  mov     [rsp+140h+var_FE], r14b
0x18000dc11  lea     r15d, [r14+1]
0x18000dc15  cmp     r12d, r15d
0x18000dc18  setnle  sil
0x18000dc1c  mov     [rsp+140h+var_100], sil
0x18000dc21  mov     [rsp+140h+var_FC], 0Dh
0x18000dc29  mov     rdx, [rsp+140h+var_F8]; struct _MI_Class *
0x18000dc2e  test    rdx, rdx
0x18000dc31  jnz     loc_18000DDF1
0x18000dc37  mov     [rsp+140h+var_100], sil
0x18000dc3c  xorps   xmm0, xmm0
0x18000dc3f  xor     eax, eax
0x18000dc41  movups  [rbp+40h+Src], xmm0
0x18000dc45  movups  [rbp+40h+var_78], xmm0
0x18000dc49  mov     [rbp+40h+var_68], rax
0x18000dc4d  mov     [rsp+140h+var_FF], r14b
0x18000dc52  mov     edx, r14d
0x18000dc55  cmp     [rsp+140h+var_F8], r14
0x18000dc5a  setnz   dl; unsigned int
0x18000dc5d  mov     rax, [rdi]
0x18000dc60  mov     [rsp+140h+var_108], rax; struct _MI_Instance *
0x18000dc65  lea     rax, [rsp+140h+var_FE]
0x18000dc6a  mov     [rsp+140h+var_110], rax; bool *
0x18000dc6f  lea     rax, [rsp+140h+var_FF]
0x18000dc74  mov     [rsp+140h+var_118], rax; bool *
0x18000dc79  lea     rax, [rbp+40h+Src]
0x18000dc7d  mov     [rsp+140h+var_120], rax; struct _MI_Instance **
0x18000dc82  lea     r9, [rsp+140h+var_FC]; enum _MI_Type *
0x18000dc87  mov     r8, r13; struct _FWXML_ELEMENT *
0x18000dc8a  mov     rcx, rbx; this
0x18000dc8d  call    ?ConvertXmlPropertyToCim@MIXmlSerializer@@QEAA_NIPEAU_FWXML_ELEMENT@@AEAW4_MI_Type@@AEAT_MI_Value@@AEA_N3PEAU_MI_Instance@@@Z; MIXmlSerializer::ConvertXmlPropertyToCim(uint,_FWXML_ELEMENT *,_MI_Type &,_MI_Value &,bool &,bool &,_MI_Instance *)
0x18000dc92  test    al, al
0x18000dc94  jz      loc_18000E829
0x18000dc9a  mov     r15d, [r13+70h]
0x18000dc9e  cmp     r14d, r15d
0x18000dca1  jl      loc_18000DFDD
0x18000dca7  xor     r14d, r14d
0x18000dcaa  mov     sil, [rsp+140h+var_FF]
0x18000dcaf  mov     [rsp+140h+var_FF], sil
0x18000dcb4  mov     al, [rsp+140h+var_100]
0x18000dcb8  mov     ecx, 1
0x18000dcbd  test    al, al
0x18000dcbf  jnz     loc_18000E12F
0x18000dcc5  mov     r9d, [rsp+140h+var_FC]
0x18000dcca  cmp     [rsp+140h+var_FE], r14b
0x18000dccf  jnz     loc_18000E4D3
0x18000dcd5  test    al, al
0x18000dcd7  jnz     loc_18000DE46
0x18000dcdd  mov     edx, 2000000h
0x18000dce2  mov     [rsp+140h+var_EC], edx
0x18000dce6  mov     r8b, [rsp+140h+var_FD]
  ... truncated ...
```
