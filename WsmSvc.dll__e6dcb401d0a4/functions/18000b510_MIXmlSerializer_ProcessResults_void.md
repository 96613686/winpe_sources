# MIXmlSerializer::ProcessResults(void)

- ea: `0x18000b510`
- end: `0x18000c528`
- name: `?ProcessResults@MIXmlSerializer@@QEAAXXZ`
- size: `4120`
- prototype: `void __fastcall(MIXmlSerializer *__hidden this)`
- caller_count: `2`
- callee_count: `36`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ade0`
- `0x1800d82e8`

## callees

- `0x180005d10`
- `0x180008920`
- `0x1800092a0`
- `0x18000a294`
- `0x18000a9a0`
- `0x18000b510`
- `0x18000d7c8`
- `0x18000f138`
- `0x18000f7a0`
- `0x180014990`
- `0x180025b50`
- `0x180025d90`
- `0x180026100`
- `0x180026310`
- `0x180035fe0`
- `0x18005f000`
- `0x1800621e0`
- `0x180084750`
- `0x180084a20`
- `0x180090290`
- `0x1800adf00`
- `0x1800cffe0`
- `0x1800e71e0`
- `0x1800f464c`
- `0x180112460`
- `0x18011349c`
- `0x18011a6d4`
- `0x18011d96c`
- `0x180123604`
- `0x180123660`
- `0x180150d1c`
- `0x180152a64`
- `0x1801538f4`
- `0x18015397c`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `miutils!Instance_GetResourceURI` at `0x18000b979`
- `miutils!Instance_GetResourceURI` at `0x18000bc4f`
- `miutils!Instance_GetResourceURI` at `0x18000b979`
- `miutils!Instance_GetResourceURI` at `0x18000bc4f`
- `miutils!Instance_SetResourceURI` at `0x18000bc79`
- `miutils!Instance_SetResourceURI` at `0x18000c0cb`
- `miutils!Instance_SetResourceURI` at `0x18000bc79`
- `miutils!Instance_SetResourceURI` at `0x18000c0cb`

## string_xrefs

- `0x18000be22`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000b721`: `onecore\admin\wmi\wmx\client\remote\xmlserializer.cpp`
- `0x18000bd0d`: `onecore\admin\wmi\wmx\client\remote\xmlserializer.cpp`
- `0x18000bea1`: `onecore\admin\wmi\wmx\client\remote\xmlserializer.cpp`
- `0x18000c2b3`: `onecore\admin\wmi\wmx\client\remote\xmlserializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall MIXmlSerializer::ProcessResults(MIXmlSerializer *this)
{
  signed __int32 v2; // ebx
  int v3; // r8d
  bool v4; // r12
  unsigned __int8 v5; // al
  int v6; // esi
  char v7; // r15
  char v8; // r14
  __int64 Child; // rsi
  int v10; // ebx
  int v11; // r10d
  char v12; // r12
  unsigned __int8 v13; // r15
  PVOID *v14; // rcx
  int v15; // eax
  __int32 v16; // ecx
  __int64 v17; // rcx
  __int64 v18; // rax
  unsigned __int64 v19; // rsi
  __int64 v20; // rax
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // rbx
  __int64 v23; // rcx
  struct _FWXML_ELEMENT *v24; // rdx
  enum _MI_Result v25; // eax
  struct _MI_Instance *v26; // r8
  const struct _MI_Instance *v27; // rdx
  struct _FWXML_ELEMENT *v28; // rsi
  __int64 v29; // rbx
  __int64 v30; // rbx
  unsigned int Buffer; // eax
  __int64 v32; // rdx
  __int64 v33; // rbx
  const unsigned __int16 *v34; // r8
  unsigned int v35; // edx
  __int64 v36; // rdx
  struct IRequestContext *v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+28h] [rbp-D8h]
  int v39; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v40; // [rsp+50h] [rbp-B0h] BYREF
  struct _FWXML_ELEMENT *v41; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v43; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+78h] [rbp-88h]
  _BYTE v45[40]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-58h]
  _QWORD v47[84]; // [rsp+E0h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qddqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      *((_QWORD *)this + 56),
      this,
      *((_DWORD *)this + 109),
      *((_DWORD *)this + 110),
      *((_QWORD *)this + 56),
      *((unsigned __int8 *)this + 288));
  while ( 1 )
  {
    v2 = *((_DWORD *)this + 110);
    v3 = *((_DWORD *)this + 70);
    if ( *((_DWORD *)this + 71) == v3 || (unsigned int)(v2 - 2) <= 1 )
      break;
    if ( *((_QWORD *)this + 3) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\xmlserializer.cpp", 0x703u, L"1795", 0x54Fu, 0);
    if ( *((_QWORD *)this + 5) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\xmlserializer.cpp", 0x704u, L"1796", 0x54Fu, 0);
    Child = 152LL * *((int *)this + 71) + *((_QWORD *)this + 34);
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 24LL))(*((_QWORD *)this + 32))
      && (unsigned int)FwXmlCompareElementName(Child, L"Event", L"http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd", 1)
      && (unsigned int)FwXmlNumChildren(Child) == 1 )
    {
      Child = FwXmlGetChild(Child, 0);
    }
    v10 = (*(unsigned __int8 (__fastcall **)(MIXmlSerializer *, __int64))(*(_QWORD *)this + 96LL))(this, Child);
    ++*((_DWORD *)this + 71);
    v11 = *((_DWORD *)this + 70);
    if ( *((_DWORD *)this + 71) == v11 )
    {
      v12 = 1;
      v13 = *((_BYTE *)this + 288);
    }
    else
    {
      v12 = 0;
      v13 = 1;
    }
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      LODWORD(v37) = *((_DWORD *)this + 71);
      WPP_SF_qddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        &WPP_526e99e636c13891e083c028203b4f01_Traceguids,
        this,
        v37,
        v11,
        v13,
        v10,
        *((_DWORD *)this + 53));
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (_BYTE)v10 )
    {
      if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x400) != 0 )
        WPP_SF_q(v14[2], 65, &WPP_526e99e636c13891e083c028203b4f01_Traceguids, this);
      if ( !(*(unsigned __int8 (__fastcall **)(MIXmlSerializer *, __int64))(*(_QWORD *)this + 136LL))(this, Child) )
        return;
      if ( !v13 )
      {
        _InterlockedExchange((volatile __int32 *)this + 109, 1);
        _InterlockedExchange((volatile __int32 *)this + 110, 3);
        v33 = *((_QWORD *)this + 32);
        (*(void (__fastcall **)(MIXmlSerializer *, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)this + 104LL))(
          this,
          0,
          0,
          0,
          0,
          0);
        if ( v33 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            WPP_SF_qq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              68,
              &WPP_526e99e636c13891e083c028203b4f01_Traceguids,
              this,
              v33);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 32LL))(v33);
        }
        return;
      }
      if ( v12 )
        return;
    }
    else
    {
      v15 = *((_DWORD *)this + 53);
      if ( v15 == 1 )
      {
        v43 = 0;
        v44 = 0;
        if ( MIXmlSerializer::GetXmlValue(
               this,
               (struct _FWXML_ELEMENT *)Child,
               (struct MIXmlSerializer::XmlValue *)&v43) )
        {
          MIXmlSerializer::GetReferenceValue(
            this,
            (struct MIXmlSerializer::XmlValue *)&v43,
            (const unsigned __int16 **)this + 27,
            (struct _MI_Instance **)this + 3);
        }
        if ( *((_BYTE *)this + 290) )
        {
          v27 = (const struct _MI_Instance *)*((_QWORD *)this + 3);
          if ( v27 )
            MIXmlSerializer::ConvertReferenceToClass(this, v27, (struct _MI_Class **)this + 5);
        }
      }
      else if ( (v15 & 0xFFFFFFFD) != 0 )
      {
        if ( v15 == 3 )
        {
          if ( (unsigned int)FwXmlNumChildren(Child) != 2 )
            goto LABEL_74;
          if ( !Child )
          {
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x80Cu, L"2060", 0x80070057, 0);
LABEL_74:
            (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 33) + 72LL))(
              *((_QWORD *)this + 33),
              2150858819LL);
            goto LABEL_40;
          }
          if ( !(unsigned int)FwXmlCompareName(Child, 4, L"Item", 0)
            || !(unsigned int)FwXmlCompareName(Child + 48, 46, L"http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd", 0) )
          {
            goto LABEL_74;
          }
          v23 = *((_QWORD *)this + 4);
          if ( v23 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
            *((_QWORD *)this + 4) = 0;
          }
          if ( *(_DWORD *)(Child + 128) <= 1u )
            v24 = 0;
          else
            v24 = (struct _FWXML_ELEMENT *)(*(_QWORD *)(Child + 136) + 152LL);
          v43 = 0;
          v44 = 0;
          if ( MIXmlSerializer::GetXmlValue(this, v24, (struct MIXmlSerializer::XmlValue *)&v43) )
            MIXmlSerializer::GetReferenceValue(
              this,
              (struct MIXmlSerializer::XmlValue *)&v43,
              (const unsigned __int16 **)this + 27,
              (struct _MI_Instance **)this + 4);
          v42 = 0;
          if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 144LL))(*((_QWORD *)this + 33))
            && (*(unsigned int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 4) + 48LL))(
                 *((_QWORD *)this + 4),
                 &v42) )
          {
            WSManError(
              (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\xmlserializer.cpp",
              0x770u,
              L"1904",
              0x54Fu,
              0);
          }
          if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 144LL))(*((_QWORD *)this + 33)) )
          {
            v28 = (struct _FWXML_ELEMENT *)FwXmlGetChild(Child, 0);
            if ( !MIXmlSerializer::ConvertXmlObjectToCim(this, 0, v28, (struct _MI_Instance **)this + 3)
              && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 152LL))(*((_QWORD *)this + 33)) == -2144108063 )
            {
              (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 33) + 200LL))(*((_QWORD *)this + 33), 1);
              MIXmlSerializer::ConvertXmlObjectToCim(this, 2u, v28, (struct _MI_Instance **)this + 3);
            }
          }
          if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 144LL))(*((_QWORD *)this + 33))
            && (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 128LL))(
                 *((_QWORD *)this + 3),
                 *((_QWORD *)this + 28)) )
          {
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 24LL))(*((_QWORD *)this + 33));
          }
          if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 144LL))(*((_QWORD *)this + 33))
            && (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 3) + 40LL))(
                 *((_QWORD *)this + 3),
                 v42) )
          {
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 24LL))(*((_QWORD *)this + 33));
          }
          if ( *((_QWORD *)this + 4) )
          {
            if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 144LL))(*((_QWORD *)this + 33)) )
            {
              v40 = 0;
              if ( !(unsigned int)Instance_GetResourceURI(*((_QWORD *)this + 4), &v40) )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                  WPP_SF_qS(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    67,
                    (unsigned int)&WPP_526e99e636c13891e083c028203b4f01_Traceguids,
                    (_DWORD)this,
                    (__int64)v40);
                if ( (unsigned int)Instance_SetResourceURI(*((_QWORD *)this + 3), v40) )
                  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 24LL))(*((_QWORD *)this + 33));
              }
            }
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 8LL))(*((_QWORD *)this + 4));
            *((_QWORD *)this + 4) = 0;
          }
        }
        else if ( v15 == 4 )
        {
          v25 = MIXmlSerializer::ConvertXmlClassToCim(
                  this,
                  (struct _FWXML_ELEMENT *)Child,
                  (struct _MI_Class **)this + 5,
                  (struct _MI_Instance **)this + 3);
          if ( v25 )
          {
            v26 = (struct _MI_Instance *)*((_QWORD *)this + 3);
            if ( v26 )
            {
              MIXmlSerializer::ReportError(this, v25, v26);
              return;
            }
          }
        }
      }
      else
      {
        if ( !MIXmlSerializer::ConvertXmlObjectToCim(
                this,
                0,
                (struct _FWXML_ELEMENT *)Child,
                (struct _MI_Instance **)this + 3)
          && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 152LL))(*((_QWORD *)this + 33)) == -2144108063 )
        {
          (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 33) + 200LL))(*((_QWORD *)this + 33), 1);
          MIXmlSerializer::ConvertXmlObjectToCim(
            this,
            2u,
            (struct _FWXML_ELEMENT *)Child,
            (struct _MI_Instance **)this + 3);
        }
        if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 144LL))(*((_QWORD *)this + 33)) )
        {
          if ( *((_QWORD *)this + 21) )
          {
            if ( *((_QWORD *)this + 23) )
            {
              v41 = 0;
              if ( (unsigned int)Instance_GetResourceURI(*((_QWORD *)this + 3), &v41) == 6 )
              {
                v17 = -1;
                do
                  ++v17;
                while ( *(_WORD *)(*((_QWORD *)this + 21) + 2 * v17) );
                v18 = -1;
                do
                  ++v18;
                while ( *(_WORD *)(*((_QWORD *)this + 23) + 2 * v18) );
                v19 = v18 + v17 + 2;
                v20 = 2 * v19;
                if ( !is_mul_ok(v19, 2u) )
                  v20 = -1;
                v21 = (unsigned __int16 *)WSManMemory::Alloc(v20, 0, 0);
                v22 = v21;
                v40 = v21;
                if ( !v21 )
                  goto LABEL_64;
                if ( (int)StringCchCopyW(v21, v19, *((const unsigned __int16 **)this + 21)) < 0 )
                {
                  v34 = L"1857";
                  v35 = 1857;
                  goto LABEL_151;
                }
                if ( (int)StringCchCatW(v22, v19, L"/") < 0 )
                {
                  v34 = L"1859";
                  v35 = 1859;
                  goto LABEL_151;
                }
                if ( (int)StringCchCatW(v22, v19, *((const unsigned __int16 **)this + 23)) < 0 )
                {
                  v34 = L"1861";
                  v35 = 1861;
LABEL_151:
                  WSManError(
                    (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\xmlserializer.cpp",
                    v35,
                    v34,
                    0x54Fu,
                    *((struct IRequestContext **)this + 33));
                  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v40);
                  return;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                  WPP_SF_qS(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    66,
                    (unsigned int)&WPP_526e99e636c13891e083c028203b4f01_Traceguids,
                    (_DWORD)this,
                    (__int64)v22);
                if ( (unsigned int)Instance_SetResourceURI(*((_QWORD *)this + 3), v22) )
LABEL_64:
                  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 24LL))(*((_QWORD *)this + 33));
                AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v40);
              }
            }
          }
        }
      }
LABEL_40:
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 144LL))(*((_QWORD *)this + 33))
        && v12
        && (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 8LL))(*((_QWORD *)this + 32)) )
      {
        v29 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 8LL))(*((_QWORD *)this + 32));
        if ( (unsigned int)FwXmlIsSimpleContent(v29) )
        {
          *((_QWORD *)this + 31) = FwXmlGetSimpleContentEx2(v29, &v40, 2);
        }
        else if ( FwXmlGetChild(v29, 0) )
        {
          v30 = FwXmlGetChild(v29, 0);
          BufferFormatter::BufferFormatter((BufferFormatter *)v45);
          Buffer = FwXmlGetBuffer(v30, 0, v45);
          if ( Buffer )
          {
            (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 33) + 72LL))(*((_QWORD *)this + 33), Buffer);
          }
          else
          {
            v32 = v46;
            v46 = 0;
            AutoCleanup<AutoFree<unsigned char>,unsigned char *>::operator=((char *)this + 240, v32);
            *((_QWORD *)this + 31) = *((_QWORD *)this + 30);
          }
          BufferFormatter::~BufferFormatter((BufferFormatter *)v45);
        }
      }
      if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 144LL))(*((_QWORD *)this + 33)) )
      {
        MIXmlSerializer::ReportError(this, *((struct IRequestContext **)this + 33), 0);
        return;
      }
      if ( v13 )
      {
        v16 = 1;
      }
      else
      {
        _InterlockedExchange((volatile __int32 *)this + 110, 3);
        v16 = 2;
      }
      _InterlockedExchange((volatile __int32 *)this + 109, v16);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_qddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          &WPP_526e99e636c13891e083c028203b4f01_Traceguids,
          this,
          *((_DWORD *)this + 109),
          *((_DWORD *)this + 110),
          v13);
      (*(void (__fastcall **)(MIXmlSerializer *, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)this + 104LL))(
        this,
        v13,
        *((_QWORD *)this + 3),
        *((_QWORD *)this + 5),
        *((_QWORD *)this + 31),
        0);
      if ( !v13 || _InterlockedCompareExchange((volatile signed __int32 *)this + 109, 2, 1) == 1 )
        return;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      &WPP_526e99e636c13891e083c028203b4f01_Traceguids,
      this,
      *((_DWORD *)this + 71),
      v3,
      *((_DWORD *)this + 110));
  v4 = (*(unsigned __int8 (__fastcall **)(MIXmlSerializer *))(*(_QWORD *)this + 152LL))(this) && !*((_QWORD *)this + 56);
  v5 = (*(__int64 (__fastcall **)(MIXmlSerializer *))(*(_QWORD *)this + 168LL))(this);
  v6 = v5;
  if ( v5 )
    v2 = _InterlockedCompareExchange((volatile signed __int32 *)this + 110, 0, 1);
  v7 = *((_BYTE *)this + 288);
  if ( (*(unsigned __int8 (__fastcall **)(MIXmlSerializer *))(*(_QWORD *)this + 176LL))(this)
    || (*(unsigned __int8 (__fastcall **)(MIXmlSerializer *))(*(_QWORD *)this + 152LL))(this) )
  {
    v8 = 0;
    goto LABEL_10;
  }
  v8 = 1;
  if ( v2 == 2 && v7 )
  {
LABEL_160:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qLd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        &WPP_526e99e636c13891e083c028203b4f01_Traceguids,
        this,
        v2,
        v6);
    (*(void (__fastcall **)(MIXmlSerializer *))(*(_QWORD *)this + 128LL))(this);
    if ( v8 && v2 == 2 )
    {
      if ( v7 )
      {
        v41 = 0;
        if ( MIXmlSerializer::ParseAndCheckIfCallbackEvent(this, &v41) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_526e99e636c13891e083c028203b4f01_Traceguids, this);
          *((_QWORD *)this + 32) = 0;
          (*(void (__fastcall **)(MIXmlSerializer *))(*(_QWORD *)this + 144LL))(this);
        }
        else
        {
          if ( *((_QWORD *)this + 32) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              WPP_SF_qq(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                63,
                &WPP_526e99e636c13891e083c028203b4f01_Traceguids,
                this,
                *((_QWORD *)this + 32));
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 32LL))(*((_QWORD *)this + 32));
          }
          *((_QWORD *)this + 32) = 0;
        }
      }
      else
      {
        CRequestContext::CRequestContext((CRequestContext *)v47);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_526e99e636c13891e083c028203b4f01_Traceguids, this);
        (*(void (__fastcall **)(_QWORD *, __int64, __int64))(v47[0] + 64LL))(v47, 995, 995);
        LOBYTE(v39) = 0;
        LOBYTE(v38) = 1;
        LOBYTE(v36) = 1;
        (*(void (__fastcall **)(MIXmlSerializer *, __int64, _QWORD, _QWORD *, _QWORD, int, int))(*(_QWORD *)this + 72LL))(
          this,
          v36,
          0,
          v47,
          0,
          v38,
          v39);
        CRequestContext::~CRequestContext((CRequestContext *)v47);
      }
    }
  }
  else
  {
LABEL_10:
    if ( *((_QWORD *)this + 32) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          &WPP_526e99e636c13891e083c028203b4f01_Traceguids,
          this,
          *((_QWORD *)this + 32));
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 32LL))(*((_QWORD *)this + 32));
    }
    *((_QWORD *)this + 32) = 0;
    if ( v2 != 3 )
    {
      if ( v2 != 2
        && ((*(unsigned __int8 (__fastcall **)(MIXmlSerializer *))(*(_QWORD *)this + 120LL))(this)
         || (_BYTE)v6
         || _InterlockedCompareExchange((volatile signed __int32 *)this + 110, 0, 1) != 2) )
      {
        return;
      }
      goto LABEL_160;
    }
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_526e99e636c13891e083c028203b4f01_Traceguids, this, 3);
      (*(void (__fastcall **)(MIXmlSerializer *))(*(_QWORD *)this + 128LL))(this);
    }
  }
}

```

## disassembly

```asm
0x18000b510  push    rbp
0x18000b512  push    rbx
0x18000b513  push    rsi
0x18000b514  push    rdi
0x18000b515  push    r12
0x18000b517  push    r13
0x18000b519  push    r14
0x18000b51b  push    r15
0x18000b51d  lea     rbp, [rsp-298h]
0x18000b525  sub     rsp, 398h
0x18000b52c  mov     rax, cs:__security_cookie
0x18000b533  xor     rax, rsp
0x18000b536  mov     [rbp+2D0h+var_50], rax
0x18000b53d  mov     rdi, rcx
0x18000b540  lea     r13, WPP_GLOBAL_Control
0x18000b547  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b54e  cmp     rcx, r13
0x18000b551  jnz     loc_18000B8C6
0x18000b557  mov     r12d, 1
0x18000b55d  mov     ebx, [rdi+1B8h]
0x18000b563  mov     eax, [rdi+11Ch]
0x18000b569  mov     r8d, [rdi+118h]
0x18000b570  cmp     eax, r8d
0x18000b573  jnz     loc_18000B6E8
0x18000b579  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b580  cmp     rcx, r13
0x18000b583  jnz     loc_18000B6AB
0x18000b589  mov     rax, [rdi]
0x18000b58c  mov     rcx, rdi
0x18000b58f  mov     rax, [rax+98h]
0x18000b596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b59b  test    al, al
0x18000b59d  jnz     loc_18000B695
0x18000b5a3  xor     r12b, r12b
0x18000b5a6  mov     rax, [rdi]
0x18000b5a9  mov     rcx, rdi
0x18000b5ac  mov     rax, [rax+0A8h]
0x18000b5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5b8  movzx   esi, al
0x18000b5bb  test    al, al
0x18000b5bd  jnz     loc_18000C2E6
0x18000b5c3  movzx   r15d, byte ptr [rdi+120h]
0x18000b5cb  mov     rcx, [rdi]
0x18000b5ce  mov     rax, [rcx+0B0h]
0x18000b5d5  mov     rcx, rdi
0x18000b5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5dd  test    al, al
0x18000b5df  jz      loc_18000B892
0x18000b5e5  xor     r14b, r14b
0x18000b5e8  mov     rax, [rdi+100h]
0x18000b5ef  test    rax, rax
0x18000b5f2  jz      short loc_18000B613
0x18000b5f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5fb  cmp     rcx, r13
0x18000b5fe  jnz     short loc_18000B66A
0x18000b600  mov     rcx, [rdi+100h]
0x18000b607  mov     rax, [rcx]
0x18000b60a  mov     rax, [rax+20h]
0x18000b60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b613  mov     qword ptr [rdi+100h], 0
0x18000b61e  cmp     ebx, 3
0x18000b621  jz      loc_18000C2FC
0x18000b627  cmp     ebx, 2
0x18000b62a  jz      loc_18000C372
0x18000b630  mov     rcx, [rdi]
0x18000b633  mov     rax, [rcx+78h]
0x18000b637  mov     rcx, rdi
0x18000b63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b63f  test    al, al
0x18000b641  jz      loc_18000C351
0x18000b647  mov     rcx, [rbp+2D0h+var_50]
0x18000b64e  xor     rcx, rsp; StackCookie
0x18000b651  call    __security_check_cookie
0x18000b656  add     rsp, 398h
0x18000b65d  pop     r15
0x18000b65f  pop     r14
0x18000b661  pop     r13
0x18000b663  pop     r12
0x18000b665  pop     rdi
0x18000b666  pop     rsi
0x18000b667  pop     rbx
0x18000b668  pop     rbp
0x18000b669  retn
0x18000b66a  test    dword ptr [rcx+1Ch], 400h
0x18000b671  jz      short loc_18000B600
0x18000b673  mov     edx, 3Ah ; ':'
0x18000b678  mov     [rsp+3D0h+var_3B0], rax
0x18000b67d  mov     r9, rdi
0x18000b680  lea     r8, WPP_526e99e636c13891e083c028203b4f01_Traceguids
0x18000b687  mov     rcx, [rcx+10h]
0x18000b68b  call    WPP_SF_qq
0x18000b690  jmp     loc_18000B600
0x18000b695  cmp     qword ptr [rdi+1C0h], 0
0x18000b69d  jnz     loc_18000B5A3
0x18000b6a3  mov     r12b, 1
0x18000b6a6  jmp     loc_18000B5A6
0x18000b6ab  test    dword ptr [rcx+1Ch], 400h
0x18000b6b2  jz      loc_18000B589
0x18000b6b8  mov     rcx, [rcx+10h]
0x18000b6bc  mov     edx, 39h ; '9'
0x18000b6c1  mov     dword ptr [rsp+3D0h+var_3A0], ebx
0x18000b6c5  mov     [rsp+3D0h+var_3A8], r8d
0x18000b6ca  mov     eax, [rdi+11Ch]
0x18000b6d0  mov     dword ptr [rsp+3D0h+var_3B0], eax
0x18000b6d4  mov     r9, rdi
0x18000b6d7  lea     r8, WPP_526e99e636c13891e083c028203b4f01_Traceguids
0x18000b6de  call    WPP_SF_qddd
0x18000b6e3  jmp     loc_18000B589
0x18000b6e8  lea     eax, [rbx-2]
0x18000b6eb  cmp     eax, 1
0x18000b6ee  jbe     loc_18000B579
0x18000b6f4  cmp     qword ptr [rdi+18h], 0
0x18000b6f9  jnz     loc_18000BCF2
0x18000b6ff  cmp     qword ptr [rdi+28h], 0
0x18000b704  jz      short loc_18000B72D
0x18000b706  mov     [rsp+3D0h+var_3B0], 0; struct IRequestContext *
0x18000b70f  mov     r9d, 54Fh; unsigned int
0x18000b715  lea     r8, a1796; "1796"
0x18000b71c  mov     edx, 704h; unsigned int
0x18000b721  lea     rcx, aOnecoreAdminWm_98; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x18000b728  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18000b72d  movsxd  rax, dword ptr [rdi+11Ch]
0x18000b734  imul    rdx, rax, 98h
0x18000b73b  mov     rsi, [rdi+110h]
0x18000b742  add     rsi, rdx
0x18000b745  mov     rcx, [rdi+100h]
0x18000b74c  mov     rax, [rcx]
0x18000b74f  mov     rax, [rax+18h]
0x18000b753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b758  test    al, al
0x18000b75a  jz      short loc_18000B793
0x18000b75c  mov     r9d, r12d
0x18000b75f  lea     r8, aHttpSchemasDmt_5; "http://schemas.dmtf.org/wbem/wsman/1/ws"...
0x18000b766  lea     rdx, aEvent; "Event"
0x18000b76d  mov     rcx, rsi
0x18000b770  call    FwXmlCompareElementName
0x18000b775  test    eax, eax
0x18000b777  jz      short loc_18000B793
0x18000b779  mov     rcx, rsi
0x18000b77c  call    FwXmlNumChildren
0x18000b781  cmp     eax, 1
0x18000b784  jnz     short loc_18000B793
0x18000b786  xor     edx, edx
0x18000b788  mov     rcx, rsi
0x18000b78b  call    FwXmlGetChild
0x18000b790  mov     rsi, rax
0x18000b793  mov     rax, [rdi]
0x18000b796  mov     rdx, rsi
0x18000b799  mov     rcx, rdi
0x18000b79c  mov     rax, [rax+60h]
0x18000b7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7a5  movzx   ebx, al
0x18000b7a8  mov     eax, [rdi+11Ch]
0x18000b7ae  inc     eax
0x18000b7b0  mov     [rdi+11Ch], eax
0x18000b7b6  mov     r10d, [rdi+118h]
0x18000b7bd  mov     eax, [rdi+11Ch]
0x18000b7c3  cmp     eax, r10d
0x18000b7c6  jz      loc_18000BCA4
0x18000b7cc  xor     r12b, r12b
0x18000b7cf  mov     r15b, 1
0x18000b7d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7d9  lea     rax, WPP_GLOBAL_Control
0x18000b7e0  cmp     rcx, rax
0x18000b7e3  jnz     loc_18000BD1E
0x18000b7e9  test    bl, bl
0x18000b7eb  jnz     loc_18000BA13
0x18000b7f1  mov     eax, [rdi+0D4h]
0x18000b7f7  cmp     eax, 1
0x18000b7fa  jz      loc_18000BDA1
0x18000b800  test    eax, 0FFFFFFFDh
0x18000b805  jz      loc_18000B914
0x18000b80b  cmp     eax, 3
0x18000b80e  jz      loc_18000BA57
0x18000b814  cmp     eax, 4
0x18000b817  jz      loc_18000BCBB
0x18000b81d  mov     rcx, [rdi+108h]
0x18000b824  mov     rax, [rcx]
0x18000b827  mov     rax, [rax+90h]
0x18000b82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b833  test    eax, eax
0x18000b835  jz      short loc_18000B858
0x18000b837  test    r12b, r12b
0x18000b83a  jz      short loc_18000B858
0x18000b83c  mov     rcx, [rdi+100h]
0x18000b843  mov     rax, [rcx]
0x18000b846  mov     rax, [rax+8]
0x18000b84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b84f  test    rax, rax
0x18000b852  jnz     loc_18000C0DE
0x18000b858  mov     esi, 2
0x18000b85d  mov     rcx, [rdi+108h]
0x18000b864  mov     rax, [rcx]
0x18000b867  mov     rax, [rax+90h]
0x18000b86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b873  test    eax, eax
0x18000b875  jz      loc_18000C2CF
0x18000b87b  mov     r12d, 1
0x18000b881  test    r15b, r15b
0x18000b884  jz      loc_18000BAA9
0x18000b88a  mov     ecx, r12d
0x18000b88d  jmp     loc_18000BAB6
0x18000b892  mov     rcx, [rdi]
0x18000b895  mov     rax, [rcx+98h]
0x18000b89c  mov     rcx, rdi
0x18000b89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8a4  test    al, al
0x18000b8a6  jnz     loc_18000B5E5
0x18000b8ac  mov     r14b, 1
0x18000b8af  cmp     ebx, 2
0x18000b8b2  jnz     loc_18000B5E8
0x18000b8b8  test    r15b, r15b
0x18000b8bb  jnz     loc_18000C372
0x18000b8c1  jmp     loc_18000B5E8
0x18000b8c6  test    dword ptr [rcx+1Ch], 400h
0x18000b8cd  jz      loc_18000B557
0x18000b8d3  movzx   eax, byte ptr [rdi+120h]
0x18000b8da  mov     r8, [rdi+1C0h]
0x18000b8e1  mov     rcx, [rcx+10h]
0x18000b8e5  mov     edx, 38h ; '8'
0x18000b8ea  mov     [rsp+3D0h+var_398], eax
0x18000b8ee  mov     [rsp+3D0h+var_3A0], r8
0x18000b8f3  mov     eax, [rdi+1B8h]
0x18000b8f9  mov     [rsp+3D0h+var_3A8], eax
0x18000b8fd  mov     eax, [rdi+1B4h]
0x18000b903  mov     dword ptr [rsp+3D0h+var_3B0], eax
0x18000b907  mov     r9, rdi
0x18000b90a  call    WPP_SF_qddqd
0x18000b90f  jmp     loc_18000B557
0x18000b914  lea     r9, [rdi+18h]; struct _MI_Instance **
0x18000b918  mov     r8, rsi; struct _FWXML_ELEMENT *
0x18000b91b  xor     edx, edx; unsigned int
0x18000b91d  mov     rcx, rdi; this
0x18000b920  call    ?ConvertXmlObjectToCim@MIXmlSerializer@@QEAA_NIPEAU_FWXML_ELEMENT@@AEAPEAU_MI_Instance@@@Z; MIXmlSerializer::ConvertXmlObjectToCim(uint,_FWXML_ELEMENT *,_MI_Instance * &)
0x18000b925  test    al, al
0x18000b927  jz      loc_18000BFE8
0x18000b92d  mov     rcx, [rdi+108h]
0x18000b934  mov     rax, [rcx]
0x18000b937  mov     rax, [rax+90h]
0x18000b93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b943  test    eax, eax
0x18000b945  jz      loc_18000B81D
0x18000b94b  cmp     qword ptr [rdi+0A8h], 0
0x18000b953  jz      loc_18000B81D
0x18000b959  cmp     qword ptr [rdi+0B8h], 0
0x18000b961  jz      loc_18000B81D
0x18000b967  mov     [rsp+3D0h+var_378], 0
0x18000b970  lea     rdx, [rsp+3D0h+var_378]
0x18000b975  mov     rcx, [rdi+18h]
0x18000b979  call    cs:__imp_Instance_GetResourceURI
0x18000b97f  cmp     eax, 6
0x18000b982  jnz     loc_18000B81D
0x18000b988  mov     rax, [rdi+0A8h]
0x18000b98f  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000b996  mov     rcx, r8
0x18000b999  nop     dword ptr [rax+00000000h]
0x18000b9a0  lea     rcx, [rcx+1]
0x18000b9a4  cmp     word ptr [rax+rcx*2], 0
0x18000b9a9  jnz     short loc_18000B9A0
0x18000b9ab  mov     rdx, [rdi+0B8h]
0x18000b9b2  mov     rax, r8
0x18000b9b5  inc     rax
0x18000b9b8  cmp     word ptr [rdx+rax*2], 0
0x18000b9bd  jnz     short loc_18000B9B5
0x18000b9bf  lea     rsi, [rcx+2]
0x18000b9c3  add     rsi, rax
0x18000b9c6  mov     eax, 2
0x18000b9cb  mul     rsi
0x18000b9ce  cmovb   rax, r8
0x18000b9d2  xor     r8d, r8d
0x18000b9d5  xor     edx, edx
0x18000b9d7  mov     rcx, rax
0x18000b9da  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18000b9df  mov     rbx, rax
0x18000b9e2  mov     [rsp+3D0h+var_380], rax
0x18000b9e7  test    rax, rax
0x18000b9ea  jnz     loc_18000C03D
0x18000b9f0  mov     rcx, [rdi+108h]
0x18000b9f7  mov     rax, [rcx]
0x18000b9fa  mov     rax, [rax+18h]
0x18000b9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba03  nop
0x18000ba04  lea     rcx, [rsp+3D0h+var_380]
0x18000ba09  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18000ba0e  jmp     loc_18000B81D
0x18000ba13  lea     r13, WPP_GLOBAL_Control
0x18000ba1a  cmp     rcx, r13
0x18000ba1d  jnz     loc_18000BD77
0x18000ba23  mov     rax, [rdi]
0x18000ba26  mov     rdx, rsi
0x18000ba29  mov     rcx, rdi
0x18000ba2c  mov     rax, [rax+88h]
0x18000ba33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba38  test    al, al
0x18000ba3a  jz      loc_18000B647
0x18000ba40  test    r15b, r15b
0x18000ba43  jz      loc_18000C1EB
0x18000ba49  test    r12b, r12b
0x18000ba4c  jz      loc_18000B557
0x18000ba52  jmp     loc_18000B647
  ... truncated ...
```
