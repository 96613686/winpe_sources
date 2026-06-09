# CConfigSource::ParseSourceDatastore(IStream *,IMVKey * *,ulong,__MIDL___MIDL_itf_mvdatastore_0000_0000_0001,std::vector<std::shared_ptr<CConfigSet>,std::allocator<std::shared_ptr<CConfigSet>>> &)

- ea: `0x18000dd4c`
- end: `0x18000e17b`
- name: `?ParseSourceDatastore@CConfigSource@@QEAAJPEAUIStream@@PEAPEAUIMVKey@@KW4__MIDL___MIDL_itf_mvdatastore_0000_0000_0001@@AEAV?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@@Z`
- size: `1071`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, int, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c160`

## callees

- `0x18000108c`
- `0x1800011c4`
- `0x1800015e4`
- `0x18000a65c`
- `0x18000c884`
- `0x18000dd4c`
- `0x18000e184`
- `0x180010d44`
- `0x180010f80`
- `0x180012010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ddc2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ddc2`
- `XmlLite!CreateXmlReader` at `0x18000de43`
- `XmlLite!CreateXmlReader` at `0x18000de43`

## string_xrefs

- `0x18000df00`: `ConfigurationSource`
- `0x18000df81`: `ConfigurationSet`
- `0x18000dfd8`: `ReplaceSet`

## pseudocode

```c
__int64 __fastcall CConfigSource::ParseSourceDatastore(__int64 a1, __int64 a2, int a3, int a4, int a5, __int64 *a6)
{
  __int64 v10; // rdi
  int XmlAttribute; // ebx
  char *v12; // r9
  int v13; // edi
  __int64 v14; // rcx
  unsigned __int16 *v15; // rax
  int v16; // ecx
  int v17; // edx
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rcx
  int v20; // edx
  int v21; // r8d
  int v22; // ebx
  char *v23; // rcx
  int v24; // edx
  int v25; // r8d
  int v26; // ecx
  int v27; // edx
  __int64 v29; // [rsp+40h] [rbp-A9h] BYREF
  void *ppvObject; // [rsp+48h] [rbp-A1h] BYREF
  int v31; // [rsp+50h] [rbp-99h] BYREF
  char *v32; // [rsp+58h] [rbp-91h] BYREF
  int *v33; // [rsp+60h] [rbp-89h] BYREF
  __int64 v34; // [rsp+68h] [rbp-81h] BYREF
  __int64 v35; // [rsp+70h] [rbp-79h] BYREF
  int v36; // [rsp+78h] [rbp-71h]
  char v37; // [rsp+7Ch] [rbp-6Dh]
  GUID ActivityId; // [rsp+80h] [rbp-69h] BYREF
  char v39[32]; // [rsp+A0h] [rbp-49h] BYREF
  __int64 *v40; // [rsp+C0h] [rbp-29h]
  __int64 v41; // [rsp+C8h] [rbp-21h]
  __int64 *v42; // [rsp+D0h] [rbp-19h]
  __int64 v43; // [rsp+D8h] [rbp-11h]

  ppvObject = 0;
  v31 = 0;
  v32 = 0;
  v35 = 0;
  v10 = a6[1];
  v29 = v10;
  v34 = *a6;
  v36 = 0;
  v37 = 0;
  if ( (unsigned int)dword_180019000 <= 4 )
    ActivityId = 0;
  else
    EventActivityIdControl(3u, &ActivityId);
  v36 = 1;
  if ( (unsigned int)dword_180019000 > 4 )
  {
    v33 = (int *)(a1 + 524);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_180019000,
      (__int64)&byte_180015837,
      (__int64)&ActivityId,
      0,
      &v33);
  }
  XmlAttribute = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( XmlAttribute >= 0 )
  {
    XmlAttribute = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
    if ( XmlAttribute >= 0 )
    {
      v13 = 0;
      XmlAttribute = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 24LL))(ppvObject, a2);
      if ( XmlAttribute >= 0 )
      {
        while ( 1 )
        {
          XmlAttribute = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v31);
          if ( XmlAttribute )
            break;
          if ( v31 == 1 )
          {
            XmlAttribute = (*(__int64 (__fastcall **)(void *, char **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                             ppvObject,
                             &v32,
                             0);
            if ( XmlAttribute < 0 )
              goto LABEL_46;
            if ( v13 )
            {
              if ( v13 != 1 )
              {
                MicrosoftTelemetryAssertTriggeredNoArgs(v14);
                XmlAttribute = -2147418113;
                goto LABEL_46;
              }
              v18 = (unsigned __int16 *)v32;
              v19 = (unsigned __int16 *)v32;
              do
              {
                v20 = *(unsigned __int16 *)((char *)v19 + (char *)L"ConfigurationSet" - v32);
                v21 = *v19 - v20;
                if ( v21 )
                  break;
                ++v19;
              }
              while ( v20 );
              if ( v21 )
              {
                v23 = v32;
                v12 = (char *)((char *)L"ProfileSet" - v32);
                do
                {
                  v24 = *(unsigned __int16 *)&v12[(_QWORD)v23];
                  v25 = *(unsigned __int16 *)v23 - v24;
                  if ( v25 )
                    break;
                  v23 += 2;
                }
                while ( v24 );
                if ( v25 )
                {
                  do
                  {
                    v26 = *(unsigned __int16 *)((char *)v18 + (char *)L"ReplaceSet" - v32);
                    v27 = *v18 - v26;
                    if ( v27 )
                      break;
                    ++v18;
                  }
                  while ( v26 );
                  if ( v27 )
                    goto LABEL_42;
                  v22 = 2;
                }
                else
                {
                  v22 = 1;
                }
              }
              else
              {
                v22 = 0;
              }
              if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) )
                goto LABEL_42;
              XmlAttribute = CConfigSource::ProcessElement(a1, v22, (_DWORD)ppvObject, a3, a4, a5, (__int64)a6);
              if ( XmlAttribute < 0 )
                goto LABEL_46;
            }
            else
            {
              v15 = (unsigned __int16 *)v32;
              do
              {
                v16 = *(unsigned __int16 *)((char *)v15 + (char *)L"ConfigurationSource" - v32);
                v17 = *v15 - v16;
                if ( v17 )
                  break;
                ++v15;
              }
              while ( v16 );
              if ( v17 )
                goto LABEL_42;
              XmlAttribute = GetXmlAttribute((__int64)ppvObject, (__int64)L"Version", 1, &v35);
              if ( XmlAttribute < 0 )
                goto LABEL_46;
              if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) == 1 )
              {
LABEL_42:
                XmlAttribute = -2147024809;
                goto LABEL_46;
              }
              v13 = 1;
            }
          }
          else if ( v31 == 15 )
          {
            if ( v13 != 1 )
              MicrosoftTelemetryAssertTriggeredNoArgs((unsigned int)(v31 - 1));
            --v13;
          }
        }
        if ( XmlAttribute >= 0 )
          XmlAttribute = 0;
      }
LABEL_46:
      v10 = v29;
    }
  }
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  if ( XmlAttribute < 0 && (unsigned int)dword_180019000 > 2 )
  {
    LODWORD(v29) = XmlAttribute;
    v33 = (int *)(a1 + 524);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180019000,
      (__int64)byte_180015773,
      (__int64)&ActivityId,
      (__int64)v12,
      &v33,
      (__int64)&v29);
  }
  v36 = 2;
  if ( (unsigned int)dword_180019000 > 4 )
  {
    v34 = ((a6[1] - *a6) >> 4) - ((v10 - v34) >> 4);
    LODWORD(v29) = XmlAttribute;
    v42 = &v34;
    v43 = 8;
    v40 = &v29;
    v41 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180019000, word_18001573A, &ActivityId, 0, 4, v39);
  }
  if ( v36 == 1 )
  {
    v36 = 2;
    _tlgWriteActivityAutoStop<0,4>((unsigned int *)&dword_180019000, (__int64)&ActivityId);
  }
  return (unsigned int)XmlAttribute;
}

```

## disassembly

```asm
0x18000dd4c  push    rbp
0x18000dd4e  push    rbx
0x18000dd4f  push    rsi
0x18000dd50  push    rdi
0x18000dd51  push    r12
0x18000dd53  push    r13
0x18000dd55  push    r14
0x18000dd57  push    r15
0x18000dd59  lea     rbp, [rsp-0Fh]
0x18000dd5e  sub     rsp, 0F8h
0x18000dd65  mov     rax, cs:__security_cookie
0x18000dd6c  xor     rax, rsp
0x18000dd6f  mov     [rbp+47h+var_50], rax
0x18000dd73  mov     r13d, r9d
0x18000dd76  mov     r12, r8
0x18000dd79  mov     rsi, rdx
0x18000dd7c  mov     r14, rcx
0x18000dd7f  mov     r15, [rbp+47h+arg_28]
0x18000dd83  xor     ecx, ecx
0x18000dd85  mov     [rsp+130h+ppvObject], rcx
0x18000dd8a  mov     [rsp+130h+var_E0], ecx
0x18000dd8e  mov     [rsp+130h+var_D8], rcx
0x18000dd93  mov     [rbp+47h+var_C0], rcx
0x18000dd97  mov     rdi, [r15+8]
0x18000dd9b  mov     [rsp+130h+var_F0], rdi
0x18000dda0  mov     rax, [r15]
0x18000dda3  mov     [rsp+130h+var_C8], rax
0x18000dda8  mov     [rbp+47h+var_B8], ecx
0x18000ddab  mov     [rbp+47h+var_B4], cl
0x18000ddae  mov     eax, cs:dword_180019000
0x18000ddb4  cmp     eax, 4
0x18000ddb7  jbe     short loc_18000DDCC
0x18000ddb9  lea     rdx, [rbp+47h+ActivityId]; ActivityId
0x18000ddbd  mov     ecx, 3; ControlCode
0x18000ddc2  call    cs:__imp_EventActivityIdControl
0x18000ddc8  xor     ecx, ecx
0x18000ddca  jmp     short loc_18000DDD3
0x18000ddcc  xorps   xmm0, xmm0
0x18000ddcf  movups  xmmword ptr [rbp+47h+ActivityId.Data1], xmm0
0x18000ddd3  mov     [rbp+47h+var_B8], 1
0x18000ddda  mov     eax, cs:dword_180019000
0x18000dde0  cmp     eax, 4
0x18000dde3  jbe     short loc_18000DE34
0x18000dde5  lea     rax, [r14+20Ch]
0x18000ddec  mov     [rsp+130h+var_D0], rax
0x18000ddf1  cmp     [rbp+47h+var_B4], cl
0x18000ddf4  jz      short loc_18000DE10
0x18000ddf6  cmp     [rbp+47h+var_A0], ecx
0x18000ddf9  jnz     short loc_18000DE0A
0x18000ddfb  cmp     [rbp+47h+var_9C], ecx
0x18000ddfe  jnz     short loc_18000DE0A
0x18000de00  cmp     [rbp+47h+var_98], ecx
0x18000de03  jnz     short loc_18000DE0A
0x18000de05  cmp     [rbp+47h+var_94], ecx
0x18000de08  jz      short loc_18000DE10
0x18000de0a  lea     r9, [rbp+47h+var_A0]
0x18000de0e  jmp     short loc_18000DE13
0x18000de10  mov     r9, rcx
0x18000de13  lea     rax, [rsp+130h+var_D0]
0x18000de18  mov     [rsp+130h+var_110], rax
0x18000de1d  lea     r8, [rbp+47h+ActivityId]
0x18000de21  lea     rdx, byte_180015837
0x18000de28  lea     rcx, dword_180019000
0x18000de2f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000de34  xor     r8d, r8d; pMalloc
0x18000de37  lea     rdx, [rsp+130h+ppvObject]; ppvObject
0x18000de3c  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18000de43  call    cs:__imp_CreateXmlReader
0x18000de49  mov     ebx, eax
0x18000de4b  test    eax, eax
0x18000de4d  js      loc_18000E060
0x18000de53  mov     rcx, [rsp+130h+ppvObject]
0x18000de58  mov     rax, [rcx]
0x18000de5b  xor     r8d, r8d
0x18000de5e  lea     edx, [r8+4]
0x18000de62  mov     rax, [rax+28h]
0x18000de66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de6b  mov     ebx, eax
0x18000de6d  test    eax, eax
0x18000de6f  js      loc_18000E060
0x18000de75  xor     edi, edi
0x18000de77  mov     rcx, [rsp+130h+ppvObject]
0x18000de7c  mov     rax, [rcx]
0x18000de7f  mov     rdx, rsi
0x18000de82  mov     rax, [rax+18h]
0x18000de86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de8b  mov     ebx, eax
0x18000de8d  test    eax, eax
0x18000de8f  js      loc_18000E05B
0x18000de95  mov     esi, [rbp+47h+arg_20]
0x18000de98  mov     rcx, [rsp+130h+ppvObject]
0x18000de9d  mov     rax, [rcx]
0x18000dea0  lea     rdx, [rsp+130h+var_E0]
0x18000dea5  mov     rax, [rax+30h]
0x18000dea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deae  mov     ebx, eax
0x18000deb0  test    eax, eax
0x18000deb2  jnz     loc_18000E054
0x18000deb8  mov     ecx, [rsp+130h+var_E0]
0x18000debc  sub     ecx, 1
0x18000debf  jz      short loc_18000DED4
0x18000dec1  cmp     ecx, 0Eh
0x18000dec4  jnz     short loc_18000DE98
0x18000dec6  cmp     edi, 1
0x18000dec9  jz      short loc_18000DED0
0x18000decb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ded0  dec     edi
0x18000ded2  jmp     short loc_18000DE98
0x18000ded4  mov     rcx, [rsp+130h+ppvObject]
0x18000ded9  mov     rax, [rcx]
0x18000dedc  xor     r8d, r8d
0x18000dedf  lea     rdx, [rsp+130h+var_D8]
0x18000dee4  mov     rax, [rax+70h]
0x18000dee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deed  mov     ebx, eax
0x18000deef  test    eax, eax
0x18000def1  js      loc_18000E05B
0x18000def7  test    edi, edi
0x18000def9  jnz     short loc_18000DF70
0x18000defb  mov     rax, [rsp+130h+var_D8]
0x18000df00  lea     r8, aConfigurations_1; "ConfigurationSource"
0x18000df07  sub     r8, rax
0x18000df0a  movzx   edx, word ptr [rax]
0x18000df0d  movzx   ecx, word ptr [rax+r8]
0x18000df12  sub     edx, ecx
0x18000df14  jnz     short loc_18000DF1E
0x18000df16  add     rax, 2
0x18000df1a  test    ecx, ecx
0x18000df1c  jnz     short loc_18000DF0A
0x18000df1e  test    edx, edx
0x18000df20  jnz     loc_18000E041
0x18000df26  lea     r9, [rbp+47h+var_C0]
0x18000df2a  lea     r8d, [rdx+1]
0x18000df2e  lea     rdx, aVersion_0; "Version"
0x18000df35  mov     rcx, [rsp+130h+ppvObject]
0x18000df3a  call    ?GetXmlAttribute@@YAJPEAUIXmlReader@@PEBGW4AttributePresence@@PEAPEBG@Z; GetXmlAttribute(IXmlReader *,ushort const *,AttributePresence,ushort const * *)
0x18000df3f  mov     ebx, eax
0x18000df41  test    eax, eax
0x18000df43  js      loc_18000E05B
0x18000df49  mov     rcx, [rsp+130h+ppvObject]
0x18000df4e  mov     rax, [rcx]
0x18000df51  mov     rax, [rax+0A0h]
0x18000df58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df5d  cmp     eax, 1
0x18000df60  jz      loc_18000E041
0x18000df66  mov     edi, 1
0x18000df6b  jmp     loc_18000DE98
0x18000df70  cmp     edi, 1
0x18000df73  jnz     loc_18000E048
0x18000df79  mov     rax, [rsp+130h+var_D8]
0x18000df7e  mov     rcx, rax
0x18000df81  lea     r9, aConfigurations_2; "ConfigurationSet"
0x18000df88  sub     r9, rax
0x18000df8b  movzx   r8d, word ptr [rcx]
0x18000df8f  movzx   edx, word ptr [rcx+r9]
0x18000df94  sub     r8d, edx
0x18000df97  jnz     short loc_18000DFA1
0x18000df99  add     rcx, 2
0x18000df9d  test    edx, edx
0x18000df9f  jnz     short loc_18000DF8B
0x18000dfa1  test    r8d, r8d
0x18000dfa4  jnz     short loc_18000DFAA
0x18000dfa6  xor     ebx, ebx
0x18000dfa8  jmp     short loc_18000DFFD
0x18000dfaa  mov     rcx, rax
0x18000dfad  lea     r9, aProfileset; "ProfileSet"
0x18000dfb4  sub     r9, rax
0x18000dfb7  movzx   r8d, word ptr [rcx]
0x18000dfbb  movzx   edx, word ptr [rcx+r9]
0x18000dfc0  sub     r8d, edx
0x18000dfc3  jnz     short loc_18000DFCD
0x18000dfc5  add     rcx, 2
0x18000dfc9  test    edx, edx
0x18000dfcb  jnz     short loc_18000DFB7
0x18000dfcd  test    r8d, r8d
0x18000dfd0  jnz     short loc_18000DFD8
0x18000dfd2  lea     ebx, [r8+1]
0x18000dfd6  jmp     short loc_18000DFFD
0x18000dfd8  lea     r8, aReplaceset; "ReplaceSet"
0x18000dfdf  sub     r8, rax
0x18000dfe2  movzx   edx, word ptr [rax]
0x18000dfe5  movzx   ecx, word ptr [rax+r8]
0x18000dfea  sub     edx, ecx
0x18000dfec  jnz     short loc_18000DFF6
0x18000dfee  add     rax, 2
0x18000dff2  test    ecx, ecx
0x18000dff4  jnz     short loc_18000DFE2
0x18000dff6  test    edx, edx
0x18000dff8  jnz     short loc_18000E041
0x18000dffa  lea     ebx, [rdx+2]
0x18000dffd  mov     rcx, [rsp+130h+ppvObject]
0x18000e002  mov     rax, [rcx]
0x18000e005  mov     rax, [rax+0A0h]
0x18000e00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e011  test    eax, eax
0x18000e013  jz      short loc_18000E041
0x18000e015  mov     [rsp+130h+var_100], r15
0x18000e01a  mov     dword ptr [rsp+130h+var_108], esi
0x18000e01e  mov     dword ptr [rsp+130h+var_110], r13d
0x18000e023  mov     r9, r12
0x18000e026  mov     r8, [rsp+130h+ppvObject]
0x18000e02b  mov     edx, ebx
0x18000e02d  mov     rcx, r14
0x18000e030  call    ?ProcessElement@CConfigSource@@AEAAJW4__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0001@@PEAUIXmlReader@@PEAPEAUIMVKey@@KW4__MIDL___MIDL_itf_mvdatastore_0000_0000_0001@@AEAV?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@@Z; CConfigSource::ProcessElement(__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0001,IXmlReader *,IMVKey * *,ulong,__MIDL___MIDL_itf_mvdatastore_0000_0000_0001,std::vector<std::shared_ptr<CConfigSet>> &)
0x18000e035  mov     ebx, eax
0x18000e037  test    eax, eax
0x18000e039  jns     loc_18000DE98
0x18000e03f  jmp     short loc_18000E05B
0x18000e041  mov     ebx, 80070057h
0x18000e046  jmp     short loc_18000E05B
0x18000e048  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e04d  mov     ebx, 8000FFFFh
0x18000e052  jmp     short loc_18000E05B
0x18000e054  xor     eax, eax
0x18000e056  test    ebx, ebx
0x18000e058  cmovns  ebx, eax
0x18000e05b  mov     rdi, [rsp+130h+var_F0]
0x18000e060  mov     rcx, [rsp+130h+ppvObject]
0x18000e065  test    rcx, rcx
0x18000e068  jz      short loc_18000E076
0x18000e06a  mov     rax, [rcx]
0x18000e06d  mov     rax, [rax+10h]
0x18000e071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e076  test    ebx, ebx
0x18000e078  jns     short loc_18000E0C0
0x18000e07a  mov     eax, cs:dword_180019000
0x18000e080  cmp     eax, 2
0x18000e083  jbe     short loc_18000E0C0
0x18000e085  mov     dword ptr [rsp+130h+var_F0], ebx
0x18000e089  lea     rax, [r14+20Ch]
0x18000e090  mov     [rsp+130h+var_D0], rax
0x18000e095  lea     rax, [rsp+130h+var_F0]
0x18000e09a  mov     [rsp+130h+var_108], rax
0x18000e09f  lea     rax, [rsp+130h+var_D0]
0x18000e0a4  mov     [rsp+130h+var_110], rax
0x18000e0a9  lea     r8, [rbp+47h+ActivityId]
0x18000e0ad  lea     rdx, byte_180015773
0x18000e0b4  lea     rcx, dword_180019000
0x18000e0bb  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e0c0  mov     [rbp+47h+var_B8], 2
0x18000e0c7  mov     eax, cs:dword_180019000
0x18000e0cd  mov     ecx, 4
0x18000e0d2  cmp     eax, ecx
0x18000e0d4  jbe     short loc_18000E13C
0x18000e0d6  sub     rdi, [rsp+130h+var_C8]
0x18000e0db  sar     rdi, 4
0x18000e0df  mov     rax, [r15+8]
0x18000e0e3  sub     rax, [r15]
0x18000e0e6  sar     rax, 4
0x18000e0ea  sub     rax, rdi
0x18000e0ed  mov     [rsp+130h+var_C8], rax
0x18000e0f2  mov     dword ptr [rsp+130h+var_F0], ebx
0x18000e0f6  lea     rax, [rsp+130h+var_C8]
0x18000e0fb  mov     [rbp+47h+var_60], rax
0x18000e0ff  mov     [rbp+47h+var_58], 8
0x18000e107  lea     rax, [rsp+130h+var_F0]
0x18000e10c  mov     [rbp+47h+var_70], rax
0x18000e110  mov     [rbp+47h+var_68], rcx
0x18000e114  lea     rax, [rbp+47h+var_90]
0x18000e118  mov     [rsp+130h+var_108], rax
0x18000e11d  mov     dword ptr [rsp+130h+var_110], ecx
0x18000e121  xor     r9d, r9d
0x18000e124  lea     r8, [rbp+47h+ActivityId]
0x18000e128  lea     rdx, word_18001573A
0x18000e12f  lea     rcx, dword_180019000
0x18000e136  call    _tlgWriteTransfer_EventWriteTransfer
0x18000e13b  nop
0x18000e13c  cmp     [rbp+47h+var_B8], 1
0x18000e140  jnz     short loc_18000E159
0x18000e142  mov     [rbp+47h+var_B8], 2
0x18000e149  lea     rdx, [rbp+47h+ActivityId]
0x18000e14d  lea     rcx, dword_180019000
0x18000e154  call    ??$_tlgWriteActivityAutoStop@$0A@$03@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,4>(_tlgProvider_t const *,_GUID const *)
0x18000e159  mov     eax, ebx
0x18000e15b  mov     rcx, [rbp+47h+var_50]
0x18000e15f  xor     rcx, rsp; StackCookie
0x18000e162  call    __security_check_cookie
0x18000e167  add     rsp, 0F8h
0x18000e16e  pop     r15
0x18000e170  pop     r14
0x18000e172  pop     r13
0x18000e174  pop     r12
0x18000e176  pop     rdi
0x18000e177  pop     rsi
0x18000e178  pop     rbx
0x18000e179  pop     rbp
0x18000e17a  retn
```
