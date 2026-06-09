# SoapSemanticConverter::ParseEvent(_FWXML_ELEMENT *,ulong *,IRequestContext *)

- ea: `0x18012b300`
- end: `0x18012bea2`
- name: `?ParseEvent@SoapSemanticConverter@@QEAAPEAVSemanticMessage@@PEAU_FWXML_ELEMENT@@PEAKPEAVIRequestContext@@@Z`
- size: `2978`
- prototype: `struct SemanticMessage *(SoapSemanticConverter *__hidden this, struct _FWXML_ELEMENT *, unsigned int *, struct IRequestContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180140470`

## callees

- `0x180005d10`
- `0x1800092a0`
- `0x1800621e0`
- `0x180084750`
- `0x1800a0cf0`
- `0x180112380`
- `0x1801133b0`
- `0x18012abe0`
- `0x18012afd0`
- `0x18012b1d0`
- `0x18012b300`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18012b5f1`
- `msvcrt!_wtoi` at `0x18012b671`
- `msvcrt!_wtoi` at `0x18012bc4e`
- `msvcrt!_wtoi` at `0x18012b5f1`
- `msvcrt!_wtoi` at `0x18012b671`
- `msvcrt!_wtoi` at `0x18012bc4e`

## string_xrefs

- `0x18012b3fb`: `http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd`
- `0x18012b4a3`: `http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd`
- `0x18012b502`: `http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd`
- `0x18012b57a`: `http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd`
- `0x18012b5fc`: `http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd`
- `0x18012b713`: `http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd`
- `0x18012b793`: `http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd`
- `0x18012b928`: `http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd`
- `0x18012b9a8`: `http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd`
- `0x18012bacc`: `http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd`
- `0x18012bbb6`: `http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd`
- `0x18012bc60`: `http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd`
- `0x18012b595`: `PercentComplete`

## pseudocode

```c
struct SemanticMessage *__fastcall SoapSemanticConverter::ParseEvent(
        SoapSemanticConverter *this,
        struct _FWXML_ELEMENT *a2,
        unsigned int *a3,
        struct IRequestContext *a4)
{
  struct _FWXML_ELEMENT *EventTypeAndResponseElement; // rax
  struct _FWXML_ELEMENT *v7; // rsi
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  char *v10; // rsi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  const wchar_t *SimpleContentEx2; // rax
  const wchar_t *v14; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  _QWORD *v18; // rax
  const unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // rsi
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rax
  const unsigned __int16 *v24; // rax
  char *v25; // rax
  _QWORD *v26; // rax
  _QWORD *v27; // rsi
  const wchar_t *v28; // rax
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  const wchar_t *v31; // rax
  int v32; // eax
  _QWORD *v33; // rax
  char *v34; // [rsp+48h] [rbp-8h]
  _QWORD *v36; // [rsp+98h] [rbp+48h] BYREF

  if ( !a4 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\soapsemanticconverter.cpp", 505, L"505", 0x54Fu, 0);
    return 0;
  }
  if ( a2 )
  {
    if ( !a3 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\soapsemanticconverter.cpp", 507, L"507", 0x54Fu, a4);
      return 0;
    }
    EventTypeAndResponseElement = SoapSemanticConverter::GetEventTypeAndResponseElement(this, a2, a3, a4);
    v7 = EventTypeAndResponseElement;
    if ( !EventTypeAndResponseElement )
      return 0;
    switch ( *a3 )
    {
      case 8u:
        v8 = (_QWORD *)WSManMemory::Alloc(48, 0, 0);
        v36 = v8;
        v9 = v8;
        if ( v8 )
        {
          v8[5] = 0;
          v8[1] = &Class;
          *v8 = &SemanticStreamingMessage::`vftable';
          v8[2] = &Class;
          v8[3] = &Class;
          v8[4] = &Class;
          v10 = (char *)v7 + 128;
          if ( !(unsigned int)FwXmlFindChildElement(
                                v10,
                                61,
                                L"http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd") )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
              goto LABEL_16;
            v12 = 26;
            goto LABEL_15;
          }
          v9[2] = FwXmlGetSimpleContentEx2(0, &v36, 2);
          if ( !(unsigned int)FwXmlFindChildElement(
                                v10,
                                61,
                                L"http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd") )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
              goto LABEL_16;
            v12 = 27;
            goto LABEL_15;
          }
          v9[3] = FwXmlGetSimpleContentEx2(0, &v36, 2);
          if ( !(unsigned int)FwXmlFindChildElement(
                                v10,
                                61,
                                L"http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd") )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
              goto LABEL_16;
            v12 = 28;
            goto LABEL_15;
          }
          v9[4] = FwXmlGetSimpleContentEx2(0, &v36, 2);
          if ( !(unsigned int)FwXmlFindChildElement(
                                v10,
                                61,
                                L"http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd") )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
              goto LABEL_16;
            v12 = 29;
            goto LABEL_15;
          }
          SimpleContentEx2 = FwXmlGetSimpleContentEx2(0, &v36, 2);
          *((_DWORD *)v9 + 10) = _wtoi(SimpleContentEx2);
          if ( !(unsigned int)FwXmlFindChildElement(
                                v10,
                                61,
                                L"http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd") )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
              goto LABEL_16;
            v12 = 30;
            goto LABEL_15;
          }
          v14 = FwXmlGetSimpleContentEx2(0, &v36, 2);
          *((_DWORD *)v9 + 11) = _wtoi(v14);
          return (struct SemanticMessage *)v9;
        }
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          v17 = 25;
LABEL_127:
          WPP_SF_(v16[2], v17, WPP_759acc01cabf3cc501c6c87da5784521_Traceguids);
          goto LABEL_128;
        }
        goto LABEL_128;
      case 0x20u:
        v18 = (_QWORD *)WSManMemory::Alloc(24, 0, 0);
        v36 = v18;
        v9 = v18;
        if ( !v18 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
            goto LABEL_128;
          v17 = 31;
          goto LABEL_127;
        }
        v18[2] = 0;
        v18[1] = &Class;
        *v18 = &SemanticStreamingMessage::`vftable';
        if ( !(unsigned int)FwXmlFindChildElement(
                              (char *)v7 + 128,
                              61,
                              L"http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd") )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
            goto LABEL_16;
          v12 = 32;
          goto LABEL_15;
        }
        v9[1] = FwXmlGetSimpleContentEx2(0, &v36, 2);
        if ( !(unsigned int)FwXmlFindChildElement(
                              (char *)v7 + 128,
                              61,
                              L"http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd") )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
            goto LABEL_16;
          v12 = 33;
          goto LABEL_15;
        }
        v19 = FwXmlGetSimpleContentEx2(0, &v36, 2);
        v20 = v19;
        if ( v19 && *v19 )
        {
          if ( SoapSemanticConverter::GetActionType(
                 this,
                 v19,
                 (enum _MI_OperationCallback_ResponseType *)v9 + 4,
                 (enum _MI_CallbackMode *)v9 + 5,
                 a4) )
          {
            return (struct SemanticMessage *)v9;
          }
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
            return 0;
          v22 = 35;
LABEL_54:
          WPP_SF_S(v21[2], v22, WPP_759acc01cabf3cc501c6c87da5784521_Traceguids, v20);
          return 0;
        }
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
          goto LABEL_16;
        v12 = 34;
        goto LABEL_15;
      case 0x10u:
        v23 = WSManMemory::Alloc(24, 0, 0);
        v36 = (_QWORD *)v23;
        v9 = (_QWORD *)v23;
        if ( !v23 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
            goto LABEL_128;
          v17 = 36;
          goto LABEL_127;
        }
        *(_DWORD *)(v23 + 16) = 0;
        *(_QWORD *)(v23 + 8) = &Class;
        *(_QWORD *)v23 = &SemanticStreamingMessage::`vftable';
        if ( (unsigned int)FwXmlFindChildElement(
                             (char *)v7 + 128,
                             61,
                             L"http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd") )
        {
          v9[1] = FwXmlGetSimpleContentEx2(0, &v36, 2);
          if ( (unsigned int)FwXmlFindChildElement(
                               (char *)v7 + 128,
                               61,
                               L"http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd") )
          {
            v24 = FwXmlGetSimpleContentEx2(0, &v36, 2);
            v20 = v24;
            if ( v24 && *v24 )
            {
              if ( SoapSemanticConverter::GetPromptType(this, v24, (enum _MI_PromptType *)v9 + 4, a4) )
                return (struct SemanticMessage *)v9;
              v21 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
                return 0;
              v22 = 40;
              goto LABEL_54;
            }
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
              goto LABEL_16;
            v12 = 39;
          }
          else
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
              goto LABEL_16;
            v12 = 38;
          }
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
            goto LABEL_16;
          v12 = 37;
        }
LABEL_15:
        WPP_SF_(v11[2], v12, WPP_759acc01cabf3cc501c6c87da5784521_Traceguids);
LABEL_16:
        (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a4 + 72LL))(a4, 2150858819LL);
        return 0;
    }
    v25 = (char *)EventTypeAndResponseElement + 128;
    v34 = v25;
    if ( *a3 != 64 )
    {
      if ( (unsigned int)FwXmlFindChildElement(
                           v25,
                           61,
                           L"http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd") )
      {
        v33 = (_QWORD *)WSManMemory::Alloc(16, 0, 0);
        v36 = v33;
        v9 = v33;
        if ( v33 )
        {
          *v33 = &SemanticStreamingMessage::`vftable';
          v33[1] = &Class;
          v33[1] = FwXmlGetSimpleContentEx2(0, &v36, 2);
          return (struct SemanticMessage *)v9;
        }
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          v17 = 49;
          goto LABEL_127;
        }
LABEL_128:
        (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a4 + 24LL))(a4);
        return 0;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_16;
      v12 = 48;
      goto LABEL_15;
    }
    if ( !(unsigned int)FwXmlFindChildElement(v25, 61, L"http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd") )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_16;
      v12 = 41;
      goto LABEL_15;
    }
    v26 = (_QWORD *)WSManMemory::Alloc(56, 0, 0);
    v36 = v26;
    v27 = v26;
    if ( !v26 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_128;
      v17 = 42;
      goto LABEL_127;
    }
    v26[1] = &Class;
    *v26 = &SemanticStreamingMessage::`vftable';
    v28 = FwXmlGetSimpleContentEx2(0, &v36, 2);
    v27[1] = v28;
    if ( v28 && *v28 )
    {
      if ( (unsigned int)FwXmlFindChildElement(
                           v34,
                           61,
                           L"http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd") )
      {
        v31 = FwXmlGetSimpleContentEx2(0, &v36, 2);
        if ( v31 && *v31 )
        {
          *((_DWORD *)v27 + 4) = _wtoi(v31);
          if ( (unsigned int)FwXmlFindChildElement(
                               v34,
                               61,
                               L"http://schemas.microsoft.com/wbem/wsman/1/cim/interactive.xsd") )
          {
            v32 = FwXmlNumChildren(0);
            *((_DWORD *)v27 + 10) = v32;
            if ( MEMORY[0x88] && v32 )
            {
              v27[6] = MEMORY[0x88];
              return (struct SemanticMessage *)v27;
            }
            v29 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
              goto LABEL_96;
            v30 = 47;
          }
          else
          {
            v29 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
              goto LABEL_96;
            v30 = 46;
          }
        }
        else
        {
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
            goto LABEL_96;
          v30 = 45;
        }
      }
      else
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
          goto LABEL_96;
        v30 = 44;
      }
    }
    else
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_96;
      v30 = 43;
    }
    WPP_SF_(v29[2], v30, WPP_759acc01cabf3cc501c6c87da5784521_Traceguids);
LABEL_96:
    (*(void (__fastcall **)(_QWORD *, __int64))*v27)(v27, 1);
    goto LABEL_16;
  }
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\soapsemanticconverter.cpp", 506, L"506", 0x54Fu, a4);
  return 0;
}

```

## disassembly

```asm
0x18012b300  mov     rax, rsp
0x18012b303  mov     [rax+10h], rbx
0x18012b307  mov     [rax+18h], rsi
0x18012b30b  mov     [rax+8], rcx
0x18012b30f  push    rbp
0x18012b310  push    rdi
0x18012b311  push    r13
0x18012b313  push    r14
0x18012b315  push    r15
0x18012b317  mov     rbp, rsp
0x18012b31a  sub     rsp, 50h
0x18012b31e  xor     r15d, r15d
0x18012b321  mov     rdi, r9
0x18012b324  mov     rbx, r8
0x18012b327  test    r9, r9
0x18012b32a  jnz     short loc_18012B353
0x18012b32c  mov     [rax-58h], r15
0x18012b330  lea     r8, a505; "505"
0x18012b337  mov     edx, 1F9h; unsigned int
0x18012b33c  mov     r9d, 54Fh; unsigned int
0x18012b342  lea     rcx, aOnecoreAdminWm_63; "onecore\\admin\\wmi\\wmx\\stdlib\\soaps"...
0x18012b349  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18012b34e  jmp     loc_18012BE87
0x18012b353  test    rdx, rdx
0x18012b356  jnz     short loc_18012B36B
0x18012b358  mov     [rsp+50h+var_30], rdi
0x18012b35d  lea     r8, a506; "506"
0x18012b364  mov     edx, 1FAh
0x18012b369  jmp     short loc_18012B33C
0x18012b36b  test    rbx, rbx
0x18012b36e  jnz     short loc_18012B383
0x18012b370  mov     [rsp+50h+var_30], rdi
0x18012b375  lea     r8, a507; "507"
0x18012b37c  mov     edx, 1FBh; struct _FWXML_ELEMENT *
0x18012b381  jmp     short loc_18012B33C
0x18012b383  call    ?GetEventTypeAndResponseElement@SoapSemanticConverter@@AEAAPEAU_FWXML_ELEMENT@@PEAU2@PEAKPEAVIRequestContext@@@Z; SoapSemanticConverter::GetEventTypeAndResponseElement(_FWXML_ELEMENT *,ulong *,IRequestContext *)
0x18012b388  mov     rsi, rax
0x18012b38b  test    rax, rax
0x18012b38e  jz      loc_18012BE87
0x18012b394  cmp     dword ptr [rbx], 8
0x18012b397  mov     [rbp+var_10], r15
0x18012b39b  jnz     loc_18012B6B0
0x18012b3a1  xor     edx, edx
0x18012b3a3  xor     r8d, r8d
0x18012b3a6  lea     ecx, [rdx+30h]
0x18012b3a9  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18012b3ae  mov     [rbp+arg_18], rax
0x18012b3b2  mov     rbx, rax
0x18012b3b5  test    rax, rax
0x18012b3b8  jz      loc_18012B682
0x18012b3be  mov     [rbx+28h], r15
0x18012b3c2  lea     rax, Class
0x18012b3c9  mov     [rbx+8], rax
0x18012b3cd  lea     rcx, ??_7SemanticStreamingMessage@@6B@; const SemanticStreamingMessage::`vftable'
0x18012b3d4  mov     [rbx], rcx
0x18012b3d7  mov     [rbx+10h], rax
0x18012b3db  mov     [rbx+18h], rax
0x18012b3df  mov     [rbx+20h], rax
0x18012b3e3  test    rbx, rbx
0x18012b3e6  jz      loc_18012B682
0x18012b3ec  mov     r14d, 1
0x18012b3f2  lea     rax, [rbp+var_10]
0x18012b3f6  mov     [rsp+50h+var_20], r14d
0x18012b3fb  lea     r8, aHttpSchemasMic_62; "http://schemas.microsoft.com/wbem/wsman"...
0x18012b402  mov     [rsp+50h+var_28], rax
0x18012b407  sub     rsi, 0FFFFFFFFFFFFFF80h
0x18012b40b  lea     rax, aActivity; "Activity"
0x18012b412  mov     rcx, rsi
0x18012b415  lea     r13d, [r14+3Ch]
0x18012b419  mov     [rsp+50h+var_30], rax
0x18012b41e  mov     edx, r13d
0x18012b421  lea     r9d, [r14+7]
0x18012b425  call    FwXmlFindChildElement
0x18012b42a  test    eax, eax
0x18012b42c  jnz     short loc_18012B477
0x18012b42e  mov     rcx, cs:WPP_GLOBAL_Control
0x18012b435  lea     rax, WPP_GLOBAL_Control
0x18012b43c  cmp     rcx, rax
0x18012b43f  jz      short loc_18012B45E
0x18012b441  test    dword ptr [rcx+1Ch], 200h
0x18012b448  jz      short loc_18012B45E
0x18012b44a  lea     edx, [r14+19h]
0x18012b44e  mov     rcx, [rcx+10h]
0x18012b452  lea     r8, WPP_759acc01cabf3cc501c6c87da5784521_Traceguids
0x18012b459  call    WPP_SF_
0x18012b45e  mov     rax, [rdi]
0x18012b461  mov     edx, 80338043h
0x18012b466  mov     rcx, rdi
0x18012b469  mov     rax, [rax+48h]
0x18012b46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b472  jmp     loc_18012BE87
0x18012b477  mov     rcx, [rbp+var_10]
0x18012b47b  lea     rdx, [rbp+arg_18]
0x18012b47f  mov     r15d, 2
0x18012b485  mov     r8d, r15d
0x18012b488  call    FwXmlGetSimpleContentEx2
0x18012b48d  mov     [rbx+10h], rax
0x18012b491  lea     r9d, [r15+0Eh]
0x18012b495  lea     rax, [rbp+var_10]
0x18012b499  mov     [rsp+50h+var_20], r14d
0x18012b49e  mov     [rsp+50h+var_28], rax
0x18012b4a3  lea     r8, aHttpSchemasMic_62; "http://schemas.microsoft.com/wbem/wsman"...
0x18012b4aa  lea     rax, aCurrentoperati; "CurrentOperation"
0x18012b4b1  mov     edx, r13d
0x18012b4b4  mov     rcx, rsi
0x18012b4b7  mov     [rsp+50h+var_30], rax
0x18012b4bc  call    FwXmlFindChildElement
0x18012b4c1  test    eax, eax
0x18012b4c3  jnz     short loc_18012B4EE
0x18012b4c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18012b4cc  lea     rax, WPP_GLOBAL_Control
0x18012b4d3  cmp     rcx, rax
0x18012b4d6  jz      short loc_18012B45E
0x18012b4d8  test    dword ptr [rcx+1Ch], 200h
0x18012b4df  jz      loc_18012B45E
0x18012b4e5  lea     edx, [r15+19h]
0x18012b4e9  jmp     loc_18012B44E
0x18012b4ee  mov     rcx, [rbp+var_10]
0x18012b4f2  lea     rdx, [rbp+arg_18]
0x18012b4f6  mov     r8d, r15d
0x18012b4f9  call    FwXmlGetSimpleContentEx2
0x18012b4fe  mov     [rbx+18h], rax
0x18012b502  lea     r8, aHttpSchemasMic_62; "http://schemas.microsoft.com/wbem/wsman"...
0x18012b509  lea     rax, [rbp+var_10]
0x18012b50d  mov     [rsp+50h+var_20], r14d
0x18012b512  mov     [rsp+50h+var_28], rax
0x18012b517  mov     r9d, 11h
0x18012b51d  lea     rax, aStatusdescript; "StatusDescription"
0x18012b524  mov     edx, r13d
0x18012b527  mov     rcx, rsi
0x18012b52a  mov     [rsp+50h+var_30], rax
0x18012b52f  call    FwXmlFindChildElement
0x18012b534  test    eax, eax
0x18012b536  jnz     short loc_18012B566
0x18012b538  mov     rcx, cs:WPP_GLOBAL_Control
0x18012b53f  lea     rax, WPP_GLOBAL_Control
0x18012b546  cmp     rcx, rax
0x18012b549  jz      loc_18012B45E
0x18012b54f  test    dword ptr [rcx+1Ch], 200h
0x18012b556  jz      loc_18012B45E
0x18012b55c  mov     edx, 1Ch
0x18012b561  jmp     loc_18012B44E
0x18012b566  mov     rcx, [rbp+var_10]
0x18012b56a  lea     rdx, [rbp+arg_18]
0x18012b56e  mov     r8d, r15d
0x18012b571  call    FwXmlGetSimpleContentEx2
0x18012b576  mov     [rbx+20h], rax
0x18012b57a  lea     r8, aHttpSchemasMic_62; "http://schemas.microsoft.com/wbem/wsman"...
0x18012b581  lea     rax, [rbp+var_10]
0x18012b585  mov     [rsp+50h+var_20], r14d
0x18012b58a  mov     [rsp+50h+var_28], rax
0x18012b58f  mov     r9d, 0Fh
0x18012b595  lea     rax, aPercentcomplet; "PercentComplete"
0x18012b59c  mov     edx, r13d
0x18012b59f  mov     rcx, rsi
0x18012b5a2  mov     [rsp+50h+var_30], rax
0x18012b5a7  call    FwXmlFindChildElement
0x18012b5ac  test    eax, eax
0x18012b5ae  jnz     short loc_18012B5DE
0x18012b5b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18012b5b7  lea     rax, WPP_GLOBAL_Control
0x18012b5be  cmp     rcx, rax
0x18012b5c1  jz      loc_18012B45E
0x18012b5c7  test    dword ptr [rcx+1Ch], 200h
0x18012b5ce  jz      loc_18012B45E
0x18012b5d4  mov     edx, 1Dh
0x18012b5d9  jmp     loc_18012B44E
0x18012b5de  mov     rcx, [rbp+var_10]
0x18012b5e2  lea     rdx, [rbp+arg_18]
0x18012b5e6  mov     r8d, r15d
0x18012b5e9  call    FwXmlGetSimpleContentEx2
0x18012b5ee  mov     rcx, rax; String
0x18012b5f1  call    cs:__imp__wtoi
0x18012b5f7  mov     [rsp+50h+var_20], r14d
0x18012b5fc  lea     r8, aHttpSchemasMic_62; "http://schemas.microsoft.com/wbem/wsman"...
0x18012b603  mov     [rbx+28h], eax
0x18012b606  mov     r9d, 10h
0x18012b60c  lea     rax, [rbp+var_10]
0x18012b610  mov     edx, r13d
0x18012b613  mov     [rsp+50h+var_28], rax
0x18012b618  mov     rcx, rsi
0x18012b61b  lea     rax, aSecondsremaini; "SecondsRemaining"
0x18012b622  mov     [rsp+50h+var_30], rax
0x18012b627  call    FwXmlFindChildElement
0x18012b62c  test    eax, eax
0x18012b62e  jnz     short loc_18012B65E
0x18012b630  mov     rcx, cs:WPP_GLOBAL_Control
0x18012b637  lea     rax, WPP_GLOBAL_Control
0x18012b63e  cmp     rcx, rax
0x18012b641  jz      loc_18012B45E
0x18012b647  test    dword ptr [rcx+1Ch], 200h
0x18012b64e  jz      loc_18012B45E
0x18012b654  mov     edx, 1Eh
0x18012b659  jmp     loc_18012B44E
0x18012b65e  mov     rcx, [rbp+var_10]
0x18012b662  lea     rdx, [rbp+arg_18]
0x18012b666  mov     r8d, r15d
0x18012b669  call    FwXmlGetSimpleContentEx2
0x18012b66e  mov     rcx, rax; String
0x18012b671  call    cs:__imp__wtoi
0x18012b677  mov     [rbx+2Ch], eax
0x18012b67a  mov     rax, rbx
0x18012b67d  jmp     loc_18012BE89
0x18012b682  mov     rcx, cs:WPP_GLOBAL_Control
0x18012b689  lea     rax, WPP_GLOBAL_Control
0x18012b690  cmp     rcx, rax
0x18012b693  jz      loc_18012BE78
0x18012b699  test    dword ptr [rcx+1Ch], 200h
0x18012b6a0  jz      loc_18012BE78
0x18012b6a6  mov     edx, 19h
0x18012b6ab  jmp     loc_18012BE68
0x18012b6b0  cmp     dword ptr [rbx], 20h ; ' '
0x18012b6b3  jnz     loc_18012B8C5
0x18012b6b9  xor     edx, edx
0x18012b6bb  xor     r8d, r8d
0x18012b6be  lea     ecx, [rdx+18h]
0x18012b6c1  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18012b6c6  mov     [rbp+arg_18], rax
0x18012b6ca  mov     rbx, rax
0x18012b6cd  test    rax, rax
0x18012b6d0  jz      loc_18012B897
0x18012b6d6  mov     [rbx+10h], r15
0x18012b6da  lea     rax, Class
0x18012b6e1  mov     [rbx+8], rax
0x18012b6e5  lea     rax, ??_7SemanticStreamingMessage@@6B@; const SemanticStreamingMessage::`vftable'
0x18012b6ec  mov     [rbx], rax
0x18012b6ef  test    rbx, rbx
0x18012b6f2  jz      loc_18012B897
0x18012b6f8  mov     r14d, 1
0x18012b6fe  lea     rax, [rbp+var_10]
0x18012b702  mov     [rsp+50h+var_20], r14d
0x18012b707  lea     rcx, aDescription; "Description"
0x18012b70e  mov     [rsp+50h+var_28], rax
0x18012b713  lea     r8, aHttpSchemasMic_62; "http://schemas.microsoft.com/wbem/wsman"...
0x18012b71a  mov     [rsp+50h+var_30], rcx
0x18012b71f  lea     rcx, [rsi+80h]
0x18012b726  lea     r13d, [r14+3Ch]
0x18012b72a  mov     edx, r13d
0x18012b72d  lea     r9d, [r14+0Ah]
0x18012b731  call    FwXmlFindChildElement
0x18012b736  test    eax, eax
0x18012b738  jnz     short loc_18012B767
0x18012b73a  mov     rcx, cs:WPP_GLOBAL_Control
0x18012b741  lea     rax, WPP_GLOBAL_Control
0x18012b748  cmp     rcx, rax
0x18012b74b  jz      loc_18012B45E
0x18012b751  test    dword ptr [rcx+1Ch], 200h
0x18012b758  jz      loc_18012B45E
0x18012b75e  lea     edx, [r14+1Fh]
0x18012b762  jmp     loc_18012B44E
0x18012b767  mov     rcx, [rbp+var_10]
0x18012b76b  lea     rdx, [rbp+arg_18]
0x18012b76f  mov     r15d, 2
0x18012b775  mov     r8d, r15d
0x18012b778  call    FwXmlGetSimpleContentEx2
0x18012b77d  mov     [rbx+8], rax
0x18012b781  lea     r9d, [r15+8]
0x18012b785  lea     rax, [rbp+var_10]
0x18012b789  mov     [rsp+50h+var_20], r14d
0x18012b78e  mov     [rsp+50h+var_28], rax
0x18012b793  lea     r8, aHttpSchemasMic_62; "http://schemas.microsoft.com/wbem/wsman"...
0x18012b79a  lea     rax, aActiontype; "ActionType"
0x18012b7a1  mov     edx, r13d
0x18012b7a4  lea     rcx, [rsi+80h]
0x18012b7ab  mov     [rsp+50h+var_30], rax
0x18012b7b0  call    FwXmlFindChildElement
0x18012b7b5  xor     r14d, r14d
0x18012b7b8  test    eax, eax
0x18012b7ba  jnz     short loc_18012B7E9
0x18012b7bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18012b7c3  lea     rax, WPP_GLOBAL_Control
0x18012b7ca  cmp     rcx, rax
0x18012b7cd  jz      loc_18012B45E
0x18012b7d3  test    dword ptr [rcx+1Ch], 200h
0x18012b7da  jz      loc_18012B45E
0x18012b7e0  lea     edx, [r15+1Fh]
0x18012b7e4  jmp     loc_18012B44E
0x18012b7e9  mov     rcx, [rbp+var_10]
0x18012b7ed  lea     rdx, [rbp+arg_18]
0x18012b7f1  mov     r8d, r15d
0x18012b7f4  call    FwXmlGetSimpleContentEx2
0x18012b7f9  mov     rsi, rax
0x18012b7fc  test    rax, rax
0x18012b7ff  jz      short loc_18012B869
0x18012b801  cmp     [rax], r14w
0x18012b805  jz      short loc_18012B869
0x18012b807  mov     rcx, [rbp+arg_0]; this
0x18012b80b  lea     r9, [rbx+14h]; enum _MI_CallbackMode *
0x18012b80f  lea     r8, [rbx+10h]; enum _MI_OperationCallback_ResponseType *
0x18012b813  mov     [rsp+50h+var_30], rdi; struct IRequestContext *
0x18012b818  mov     rdx, rax; unsigned __int16 *
0x18012b81b  call    ?GetActionType@SoapSemanticConverter@@AEAA_NPEBGPEAW4_MI_OperationCallback_ResponseType@@PEAW4_MI_CallbackMode@@PEAVIRequestContext@@@Z; SoapSemanticConverter::GetActionType(ushort const *,_MI_OperationCallback_ResponseType *,_MI_CallbackMode *,IRequestContext *)
0x18012b820  test    al, al
0x18012b822  jnz     loc_18012B67A
0x18012b828  mov     rcx, cs:WPP_GLOBAL_Control
0x18012b82f  lea     rax, WPP_GLOBAL_Control
0x18012b836  cmp     rcx, rax
0x18012b839  jz      loc_18012BE87
0x18012b83f  test    dword ptr [rcx+1Ch], 200h
0x18012b846  jz      loc_18012BE87
  ... truncated ...
```
