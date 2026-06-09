# ParseDataRowsetFromBuffer(Csi::ISoapWebService *,_WS_XML_BUFFER *,Ofc::TCntPtrList<Csi::ISharePointItemDescriptor> &,MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CBuffer<wchar_t>> &)

- ea: `0x180490ea0`
- end: `0x180491663`
- name: `?ParseDataRowsetFromBuffer@@YAJPEAUISoapWebService@Csi@@PEAU_WS_XML_BUFFER@@AEAV?$TCntPtrList@UISharePointItemDescriptor@Csi@@@Ofc@@AEAV?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CBuffer@_W@2@@MsoCF@@@Z`
- size: `1987`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18048fb20`

## callees

- `0x18006be0c`
- `0x180100b00`
- `0x180192520`
- `0x180192560`
- `0x180490ea0`
- `0x180491664`
- `0x18049172c`

## import_xrefs

- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1804914e4`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1804914e4`
- `webservices!WsFreeReader` at `0x1804915cf`
- `webservices!WsFreeReader` at `0x1804915cf`
- `webservices!WsReadNode` at `0x180490fda`
- `webservices!WsReadNode` at `0x180490fda`
- `webservices!WsXmlStringEquals` at `0x180491044`
- `webservices!WsXmlStringEquals` at `0x18049108f`
- `webservices!WsXmlStringEquals` at `0x18049130b`
- `webservices!WsXmlStringEquals` at `0x180491337`
- `webservices!WsXmlStringEquals` at `0x180491363`
- `webservices!WsXmlStringEquals` at `0x18049138f`
- `webservices!WsXmlStringEquals` at `0x1804913bb`
- `webservices!WsXmlStringEquals` at `0x1804913e7`
- `webservices!WsXmlStringEquals` at `0x180491413`
- `webservices!WsXmlStringEquals` at `0x180491442`
- `webservices!WsXmlStringEquals` at `0x180491471`
- `webservices!WsXmlStringEquals` at `0x1804914a0`
- `webservices!WsXmlStringEquals` at `0x180491644`
- `webservices!WsXmlStringEquals` at `0x180491044`
- `webservices!WsXmlStringEquals` at `0x18049108f`
- `webservices!WsXmlStringEquals` at `0x18049130b`
- `webservices!WsXmlStringEquals` at `0x180491337`
- `webservices!WsXmlStringEquals` at `0x180491363`
- `webservices!WsXmlStringEquals` at `0x18049138f`
- `webservices!WsXmlStringEquals` at `0x1804913bb`
- `webservices!WsXmlStringEquals` at `0x1804913e7`
- `webservices!WsXmlStringEquals` at `0x180491413`
- `webservices!WsXmlStringEquals` at `0x180491442`
- `webservices!WsXmlStringEquals` at `0x180491471`
- `webservices!WsXmlStringEquals` at `0x1804914a0`
- `webservices!WsXmlStringEquals` at `0x180491644`
- `webservices!WsGetReaderNode` at `0x180490fa4`
- `webservices!WsGetReaderNode` at `0x180490fa4`
- `webservices!WsSetInputToBuffer` at `0x180490f79`
- `webservices!WsSetInputToBuffer` at `0x180490f79`
- `webservices!WsCreateReader` at `0x180490f26`
- `webservices!WsCreateReader` at `0x180490f26`

## string_xrefs

- `0x1804911b8`: `ows_Created`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __fastcall ParseDataRowsetFromBuffer(__int64 a1, WS_XML_BUFFER *a2, Ofc::CListImpl *a3, __int64 a4)
{
  WS_ERROR *v8; // rax
  HRESULT result; // eax
  WS_ERROR *error; // rax
  WS_ERROR *v11; // rax
  HRESULT ReaderNode; // edi
  WS_XML_NODE *v13; // r14
  WS_ERROR *v14; // rax
  WS_XML_READER *v15; // rcx
  WS_ERROR *v16; // rax
  WS_ERROR *v17; // rax
  __int64 Instance; // rax
  char *v19; // rdi
  __int64 v20; // r15
  __int64 v21; // rsi
  WS_ERROR *v22; // rax
  WS_ERROR *v23; // rax
  WS_ERROR *v24; // rax
  WS_ERROR *v25; // rax
  WS_ERROR *v26; // rax
  WS_ERROR *v27; // rax
  WS_ERROR *v28; // rax
  WS_ERROR *v29; // rax
  WS_ERROR *v30; // rax
  WS_ERROR *v31; // rax
  void *v32; // rdx
  char *v33; // rdx
  WS_XML_NODE_TYPE i; // edi
  __int64 v35; // rsi
  WS_ERROR *v36; // rax
  WS_XML_READER *reader; // [rsp+30h] [rbp-D0h] BYREF
  int v38; // [rsp+38h] [rbp-C8h] BYREF
  WS_XML_NODE *node; // [rsp+40h] [rbp-C0h] BYREF
  WS_XML_STRING v40; // [rsp+48h] [rbp-B8h] BYREF
  WS_XML_READER_PROPERTY properties; // [rsp+68h] [rbp-98h] BYREF
  WS_XML_STRING string2; // [rsp+80h] [rbp-80h] BYREF
  WS_XML_STRING v43; // [rsp+A0h] [rbp-60h] BYREF
  WS_XML_STRING v44; // [rsp+C0h] [rbp-40h] BYREF
  WS_XML_STRING v45; // [rsp+E0h] [rbp-20h] BYREF
  WS_XML_STRING v46; // [rsp+100h] [rbp+0h] BYREF
  WS_XML_STRING v47; // [rsp+120h] [rbp+20h] BYREF
  WS_XML_STRING v48; // [rsp+140h] [rbp+40h] BYREF
  WS_XML_STRING v49; // [rsp+160h] [rbp+60h] BYREF
  WS_XML_STRING v50; // [rsp+180h] [rbp+80h] BYREF
  WS_XML_STRING v51; // [rsp+1A0h] [rbp+A0h] BYREF
  WS_XML_STRING v52; // [rsp+1C0h] [rbp+C0h] BYREF
  char *v53; // [rsp+1E0h] [rbp+E0h]
  void ***v54; // [rsp+1F0h] [rbp+F0h] BYREF
  Mso::Memory *v55; // [rsp+1F8h] [rbp+F8h]
  int v56; // [rsp+200h] [rbp+100h]
  __int64 v57; // [rsp+208h] [rbp+108h]
  _WORD v58[136]; // [rsp+210h] [rbp+110h] BYREF

  reader = 0;
  *(_QWORD *)&properties.id = 1;
  *(_QWORD *)&properties.valueSize = 4;
  v38 = 1;
  properties.value = &v38;
  v8 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
  result = WsCreateReader(&properties, 1u, &reader, v8);
  if ( result < 0 )
    return result;
  error = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
  WsSetInputToBuffer(reader, a2, 0, 0, error);
  node = 0;
  do
  {
    v11 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
    ReaderNode = WsGetReaderNode(reader, (const WS_XML_NODE **)&node, v11);
    if ( ReaderNode < 0 )
    {
LABEL_44:
      v15 = reader;
      goto LABEL_45;
    }
    v13 = node;
    if ( node->nodeType == WS_XML_NODE_TYPE_ELEMENT )
    {
      *(_QWORD *)&string2.length = 4;
      string2.bytes = (BYTE *)"data";
      string2.dictionary = 0;
      *(_QWORD *)&string2.id = 0;
      v16 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
      if ( !WsXmlStringEquals(*(const WS_XML_STRING **)&v13[4].nodeType, &string2, v16) )
      {
        for ( i = 0; (unsigned int)i < v13[8].nodeType; ++i )
        {
          v35 = *(_QWORD *)(*(_QWORD *)&v13[10].nodeType + 8LL * (unsigned int)i);
          if ( !*(_BYTE *)(v35 + 1) && **(_DWORD **)(v35 + 32) == 1 )
          {
            *(_QWORD *)&v40.length = 30;
            v40.bytes = (BYTE *)"ListItemCollectionPositionNext";
            v40.dictionary = 0;
            *(_QWORD *)&v40.id = 0;
            v36 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
            if ( !WsXmlStringEquals(*(const WS_XML_STRING **)(v35 + 16), &v40, v36) )
            {
              sub_180491664(v35, a4);
              break;
            }
          }
        }
      }
      *(_QWORD *)&v43.length = 3;
      v43.bytes = (BYTE *)"row";
      v43.dictionary = 0;
      *(_QWORD *)&v43.id = 0;
      v17 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
      if ( !WsXmlStringEquals(*(const WS_XML_STRING **)&v13[4].nodeType, &v43, v17) )
      {
        Instance = MsoCF::CJotComObject<CListItemDescriptor,MsoCF::CAllocatorOnNew>::CreateInstance();
        v19 = (char *)Instance;
        if ( Instance )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)Instance + 8LL))(Instance);
        v53 = v19;
        v20 = 0;
        if ( v13[8].nodeType )
        {
          while ( 1 )
          {
            v21 = *(_QWORD *)(*(_QWORD *)&v13[10].nodeType + 8 * v20);
            if ( !*(_BYTE *)(v21 + 1) && **(_DWORD **)(v21 + 32) == 1 )
              break;
LABEL_16:
            v20 = (unsigned int)(v20 + 1);
            if ( (unsigned int)v20 >= v13[8].nodeType )
              goto LABEL_17;
          }
          v57 = 258;
          v54 = &off_180F74C50;
          v55 = (Mso::Memory *)v58;
          v56 = 258;
          v58[0] = 0;
          *(_QWORD *)&v40.length = 6;
          v40.bytes = (BYTE *)"ows_ID";
          v40.dictionary = 0;
          *(_QWORD *)&v40.id = 0;
          *(_QWORD *)&v44.length = 12;
          v44.bytes = (BYTE *)"ows_Modified";
          v44.dictionary = 0;
          *(_QWORD *)&v44.id = 0;
          *(_QWORD *)&v45.length = 11;
          v45.bytes = (BYTE *)"ows_Created";
          v45.dictionary = 0;
          *(_QWORD *)&v45.id = 0;
          *(_QWORD *)&v46.length = 11;
          v46.bytes = (BYTE *)"ows_FileRef";
          v46.dictionary = 0;
          *(_QWORD *)&v46.id = 0;
          *(_QWORD *)&v47.length = 12;
          v47.bytes = (BYTE *)"ows_UniqueId";
          v47.dictionary = 0;
          *(_QWORD *)&v47.id = 0;
          *(_QWORD *)&v48.length = 13;
          v48.bytes = (BYTE *)"ows_FSObjType";
          v48.dictionary = 0;
          *(_QWORD *)&v48.id = 0;
          *(_QWORD *)&v49.length = 19;
          v49.bytes = (BYTE *)"ows_FileSizeDisplay";
          v49.dictionary = 0;
          *(_QWORD *)&v49.id = 0;
          *(_QWORD *)&v50.length = 10;
          v50.bytes = (BYTE *)"ows_ProgId";
          v50.dictionary = 0;
          *(_QWORD *)&v50.id = 0;
          *(_QWORD *)&v51.length = 16;
          v51.bytes = (BYTE *)"ows_NotebookType";
          v51.dictionary = 0;
          *(_QWORD *)&v51.id = 0;
          *(_QWORD *)&v52.length = 12;
          v52.bytes = (BYTE *)"ows_MetaInfo";
          v52.dictionary = 0;
          *(_QWORD *)&v52.id = 0;
          v22 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
          if ( WsXmlStringEquals(*(const WS_XML_STRING **)(v21 + 16), &v40, v22) )
          {
            v23 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
            if ( WsXmlStringEquals(*(const WS_XML_STRING **)(v21 + 16), &v44, v23) )
            {
              v24 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
              if ( WsXmlStringEquals(*(const WS_XML_STRING **)(v21 + 16), &v45, v24) )
              {
                v25 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
                if ( WsXmlStringEquals(*(const WS_XML_STRING **)(v21 + 16), &v46, v25) )
                {
                  v26 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
                  if ( WsXmlStringEquals(*(const WS_XML_STRING **)(v21 + 16), &v47, v26) )
                  {
                    v27 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
                    if ( WsXmlStringEquals(*(const WS_XML_STRING **)(v21 + 16), &v48, v27) )
                    {
                      v28 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
                      if ( WsXmlStringEquals(*(const WS_XML_STRING **)(v21 + 16), &v49, v28) )
                      {
                        v29 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
                        if ( WsXmlStringEquals(*(const WS_XML_STRING **)(v21 + 16), &v50, v29) )
                        {
                          v30 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
                          if ( WsXmlStringEquals(*(const WS_XML_STRING **)(v21 + 16), &v51, v30) )
                          {
                            v31 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
                            if ( WsXmlStringEquals(*(const WS_XML_STRING **)(v21 + 16), &v52, v31) )
                              goto LABEL_33;
                            sub_180491664(v21, &v54);
                            v33 = v19 + 256;
                          }
                          else
                          {
                            sub_180491664(v21, &v54);
                            v33 = v19 + 232;
                          }
                        }
                        else
                        {
                          sub_180491664(v21, &v54);
                          v33 = v19 + 208;
                        }
                      }
                      else
                      {
                        sub_180491664(v21, &v54);
                        v33 = v19 + 160;
                      }
                    }
                    else
                    {
                      sub_180491664(v21, &v54);
                      v33 = v19 + 136;
                    }
                  }
                  else
                  {
                    sub_180491664(v21, &v54);
                    v33 = v19 + 112;
                  }
                }
                else
                {
                  sub_180491664(v21, &v54);
                  v33 = v19 + 88;
                }
              }
              else
              {
                sub_180491664(v21, &v54);
                v33 = v19 + 64;
              }
            }
            else
            {
              sub_180491664(v21, &v54);
              v33 = v19 + 40;
            }
          }
          else
          {
            sub_180491664(v21, &v54);
            v33 = v19 + 16;
          }
          MsoCF::Strings::CopyWzToWz(v55, v33);
LABEL_33:
          if ( v55 != (Mso::Memory *)v58 )
            Mso::Memory::Free(v55, v32);
          goto LABEL_16;
        }
LABEL_17:
        if ( v19 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v19 + 8LL))(v19);
        *Ofc::CListImpl::NewTail(a3) = v19;
        if ( v19 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
    v14 = (WS_ERROR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
    ReaderNode = WsReadNode(reader, v14);
    if ( ReaderNode < 0 )
      goto LABEL_44;
  }
  while ( node->nodeType != WS_XML_NODE_TYPE_EOF );
  v15 = reader;
  if ( reader )
LABEL_45:
    WsFreeReader(v15);
  return ReaderNode;
}

```

## disassembly

```asm
0x180490ea0  push    rbp
0x180490ea2  push    rbx
0x180490ea3  push    rsi
0x180490ea4  push    rdi
0x180490ea5  push    r12
0x180490ea7  push    r13
0x180490ea9  push    r14
0x180490eab  push    r15
0x180490ead  lea     rbp, [rsp-238h]
0x180490eb5  sub     rsp, 338h
0x180490ebc  mov     rax, cs:__security_cookie
0x180490ec3  xor     rax, rsp
0x180490ec6  mov     [rbp+270h+var_50], rax
0x180490ecd  mov     r13, r9
0x180490ed0  mov     r12, r8
0x180490ed3  mov     rdi, rdx
0x180490ed6  mov     rbx, rcx
0x180490ed9  xor     r15d, r15d
0x180490edc  mov     [rsp+370h+reader], r15
0x180490ee1  mov     qword ptr [rsp+370h+properties.id], 1
0x180490eea  mov     qword ptr [rsp+370h+properties.valueSize], 4
0x180490ef3  mov     [rsp+370h+var_338], 1
0x180490efb  lea     rax, [rsp+370h+var_338]
0x180490f00  mov     [rsp+370h+properties.value], rax
0x180490f05  mov     rax, [rcx]
0x180490f08  mov     rax, [rax+80h]
0x180490f0f  call    cs:__guard_dispatch_icall_fptr
0x180490f15  mov     r9, rax; error
0x180490f18  lea     r8, [rsp+370h+reader]; reader
0x180490f1d  lea     edx, [r15+1]; propertyCount
0x180490f21  lea     rcx, [rsp+370h+properties]; properties
0x180490f26  call    cs:__imp_WsCreateReader
0x180490f2c  test    eax, eax
0x180490f2e  jns     short loc_180490F53
0x180490f30  mov     rcx, [rbp+270h+var_50]
0x180490f37  xor     rcx, rsp; StackCookie
0x180490f3a  call    __security_check_cookie
0x180490f3f  add     rsp, 338h
0x180490f46  pop     r15
0x180490f48  pop     r14
0x180490f4a  pop     r13
0x180490f4c  pop     r12
0x180490f4e  pop     rdi
0x180490f4f  pop     rsi
0x180490f50  pop     rbx
0x180490f51  pop     rbp
0x180490f52  retn
0x180490f53  mov     rax, [rbx]
0x180490f56  mov     rcx, rbx
0x180490f59  mov     rax, [rax+80h]
0x180490f60  call    cs:__guard_dispatch_icall_fptr
0x180490f66  mov     [rsp+370h+error], rax; error
0x180490f6b  xor     r9d, r9d; propertyCount
0x180490f6e  xor     r8d, r8d; properties
0x180490f71  mov     rdx, rdi; buffer
0x180490f74  mov     rcx, [rsp+370h+reader]; reader
0x180490f79  call    cs:__imp_WsSetInputToBuffer
0x180490f7f  mov     [rsp+370h+node], r15
0x180490f84  mov     rax, [rbx]
0x180490f87  mov     rcx, rbx
0x180490f8a  mov     rax, [rax+80h]
0x180490f91  call    cs:__guard_dispatch_icall_fptr
0x180490f97  mov     r8, rax; error
0x180490f9a  lea     rdx, [rsp+370h+node]; node
0x180490f9f  mov     rcx, [rsp+370h+reader]; xmlReader
0x180490fa4  call    cs:__imp_WsGetReaderNode
0x180490faa  mov     edi, eax
0x180490fac  test    eax, eax
0x180490fae  js      loc_1804915CA
0x180490fb4  mov     r14, [rsp+370h+node]
0x180490fb9  cmp     dword ptr [r14], 1
0x180490fbd  jz      short loc_180491007
0x180490fbf  mov     rax, [rbx]
0x180490fc2  mov     rcx, rbx
0x180490fc5  mov     rax, [rax+80h]
0x180490fcc  call    cs:__guard_dispatch_icall_fptr
0x180490fd2  mov     rdx, rax; error
0x180490fd5  mov     rcx, [rsp+370h+reader]; reader
0x180490fda  call    cs:__imp_WsReadNode
0x180490fe0  mov     edi, eax
0x180490fe2  test    eax, eax
0x180490fe4  js      loc_1804915CA
0x180490fea  mov     rcx, [rsp+370h+node]
0x180490fef  cmp     dword ptr [rcx], 8
0x180490ff2  jnz     short loc_180490F84
0x180490ff4  mov     rcx, [rsp+370h+reader]
0x180490ff9  test    rcx, rcx
0x180490ffc  jz      loc_1804915D5
0x180491002  jmp     loc_1804915CF
0x180491007  mov     qword ptr [rbp+270h+string2.length], 4
0x18049100f  lea     rax, aData_0; "data"
0x180491016  mov     [rbp+270h+string2.bytes], rax
0x18049101a  mov     [rbp+270h+string2.dictionary], r15
0x18049101e  mov     qword ptr [rbp+270h+string2.id], 0
0x180491026  mov     rax, [rbx]
0x180491029  mov     rcx, rbx
0x18049102c  mov     rax, [rax+80h]
0x180491033  call    cs:__guard_dispatch_icall_fptr
0x180491039  mov     r8, rax; error
0x18049103c  lea     rdx, [rbp+270h+string2]; string2
0x180491040  mov     rcx, [r14+10h]; string1
0x180491044  call    cs:__imp_WsXmlStringEquals
0x18049104a  test    eax, eax
0x18049104c  jz      loc_1804915DC
0x180491052  mov     qword ptr [rbp+270h+var_2D0.length], 3
0x18049105a  lea     rax, aRow; "row"
0x180491061  mov     [rbp+270h+var_2D0.bytes], rax
0x180491065  mov     [rbp+270h+var_2D0.dictionary], r15
0x180491069  mov     qword ptr [rbp+270h+var_2D0.id], 0
0x180491071  mov     rax, [rbx]
0x180491074  mov     rcx, rbx
0x180491077  mov     rax, [rax+80h]
0x18049107e  call    cs:__guard_dispatch_icall_fptr
0x180491084  mov     r8, rax; error
0x180491087  lea     rdx, [rbp+270h+var_2D0]; string2
0x18049108b  mov     rcx, [r14+10h]; string1
0x18049108f  call    cs:__imp_WsXmlStringEquals
0x180491095  test    eax, eax
0x180491097  jnz     loc_180490FBF
0x18049109d  call    ?CreateInstance@?$CJotComObject@VCListItemDescriptor@@VCAllocatorOnNew@MsoCF@@@MsoCF@@SAPEAVCListItemDescriptor@@AEAVCAllocatorOnNew@2@_N@Z; MsoCF::CJotComObject<CListItemDescriptor,MsoCF::CAllocatorOnNew>::CreateInstance(MsoCF::CAllocatorOnNew &,bool)
0x1804910a2  mov     rdi, rax
0x1804910a5  test    rax, rax
0x1804910a8  jz      short loc_1804910BA
0x1804910aa  mov     rcx, [rax]
0x1804910ad  mov     rax, [rcx+8]
0x1804910b1  mov     rcx, rdi
0x1804910b4  call    cs:__guard_dispatch_icall_fptr
0x1804910ba  mov     [rbp+270h+var_190], rdi
0x1804910c1  xor     r15d, r15d
0x1804910c4  cmp     [r14+20h], r15d
0x1804910c8  jbe     short loc_1804910EA
0x1804910ca  mov     rax, [r14+28h]
0x1804910ce  mov     rsi, [rax+r15*8]
0x1804910d2  cmp     byte ptr [rsi+1], 0
0x1804910d6  jnz     short loc_1804910E1
0x1804910d8  mov     rax, [rsi+20h]
0x1804910dc  cmp     dword ptr [rax], 1
0x1804910df  jz      short loc_18049112B
0x1804910e1  inc     r15d
0x1804910e4  cmp     r15d, [r14+20h]
0x1804910e8  jb      short loc_1804910CA
0x1804910ea  test    rdi, rdi
0x1804910ed  jz      short loc_1804910FF
0x1804910ef  mov     rax, [rdi]
0x1804910f2  mov     rcx, rdi
0x1804910f5  mov     rax, [rax+8]
0x1804910f9  call    cs:__guard_dispatch_icall_fptr
0x1804910ff  mov     rcx, r12; this
0x180491102  call    ?NewTail@CListImpl@Ofc@@IEAAPEAPEAXXZ; Ofc::CListImpl::NewTail(void)
0x180491107  mov     [rax], rdi
0x18049110a  xor     r15d, r15d
0x18049110d  test    rdi, rdi
0x180491110  jz      loc_180490FBF
0x180491116  mov     rax, [rdi]
0x180491119  mov     rcx, rdi
0x18049111c  mov     rax, [rax+10h]
0x180491120  call    cs:__guard_dispatch_icall_fptr
0x180491126  jmp     loc_180490FBF
0x18049112b  mov     [rbp+270h+var_168], 102h
0x180491136  mov     ecx, 102h
0x18049113b  lea     rax, off_180F74C50
0x180491142  mov     [rbp+270h+var_180], rax
0x180491149  lea     rax, [rbp+270h+var_160]
0x180491150  mov     [rbp+270h+var_178], rax
0x180491157  mov     [rbp+270h+var_170], ecx
0x18049115d  xor     eax, eax
0x18049115f  mov     [rbp+270h+var_160], ax
0x180491166  mov     qword ptr [rsp+370h+var_328.length], 6
0x18049116f  lea     rax, aOwsId; "ows_ID"
0x180491176  mov     [rsp+370h+var_328.bytes], rax
0x18049117b  mov     [rsp+370h+var_328.dictionary], 0
0x180491184  mov     qword ptr [rsp+370h+var_328.id], 0
0x18049118d  mov     qword ptr [rbp+270h+var_2B0.length], 0Ch
0x180491195  lea     rax, aOwsModified; "ows_Modified"
0x18049119c  mov     [rbp+270h+var_2B0.bytes], rax
0x1804911a0  mov     [rbp+270h+var_2B0.dictionary], 0
0x1804911a8  mov     qword ptr [rbp+270h+var_2B0.id], 0
0x1804911b0  mov     qword ptr [rbp+270h+var_290.length], 0Bh
0x1804911b8  lea     rax, aOwsCreated; "ows_Created"
0x1804911bf  mov     [rbp+270h+var_290.bytes], rax
0x1804911c3  mov     [rbp+270h+var_290.dictionary], 0
0x1804911cb  mov     qword ptr [rbp+270h+var_290.id], 0
0x1804911d3  mov     qword ptr [rbp+270h+var_270.length], 0Bh
0x1804911db  lea     rax, aOwsFileref; "ows_FileRef"
0x1804911e2  mov     [rbp+270h+var_270.bytes], rax
0x1804911e6  mov     [rbp+270h+var_270.dictionary], 0
0x1804911ee  mov     qword ptr [rbp+270h+var_270.id], 0
0x1804911f6  mov     qword ptr [rbp+270h+var_250.length], 0Ch
0x1804911fe  lea     rax, aOwsUniqueid; "ows_UniqueId"
0x180491205  mov     [rbp+270h+var_250.bytes], rax
0x180491209  mov     [rbp+270h+var_250.dictionary], 0
0x180491211  mov     qword ptr [rbp+270h+var_250.id], 0
0x180491219  mov     qword ptr [rbp+270h+var_230.length], 0Dh
0x180491221  lea     rax, aOwsFsobjtype; "ows_FSObjType"
0x180491228  mov     [rbp+270h+var_230.bytes], rax
0x18049122c  mov     [rbp+270h+var_230.dictionary], 0
0x180491234  mov     qword ptr [rbp+270h+var_230.id], 0
0x18049123c  mov     qword ptr [rbp+270h+var_210.length], 13h
0x180491244  lea     rax, aOwsFilesizedis; "ows_FileSizeDisplay"
0x18049124b  mov     [rbp+270h+var_210.bytes], rax
0x18049124f  mov     [rbp+270h+var_210.dictionary], 0
0x180491257  mov     qword ptr [rbp+270h+var_210.id], 0
0x18049125f  mov     qword ptr [rbp+270h+var_1F0.length], 0Ah
0x18049126a  lea     rax, aOwsProgid; "ows_ProgId"
0x180491271  mov     [rbp+270h+var_1F0.bytes], rax
0x180491278  mov     [rbp+270h+var_1F0.dictionary], 0
0x180491283  mov     qword ptr [rbp+270h+var_1F0.id], 0
0x18049128e  mov     qword ptr [rbp+270h+var_1D0.length], 10h
0x180491299  lea     rax, aOwsNotebooktyp; "ows_NotebookType"
0x1804912a0  mov     [rbp+270h+var_1D0.bytes], rax
0x1804912a7  mov     [rbp+270h+var_1D0.dictionary], 0
0x1804912b2  mov     qword ptr [rbp+270h+var_1D0.id], 0
0x1804912bd  mov     qword ptr [rbp+270h+var_1B0.length], 0Ch
0x1804912c8  lea     rax, aOwsMetainfo; "ows_MetaInfo"
0x1804912cf  mov     [rbp+270h+var_1B0.bytes], rax
0x1804912d6  mov     [rbp+270h+var_1B0.dictionary], 0
0x1804912e1  mov     qword ptr [rbp+270h+var_1B0.id], 0
0x1804912ec  mov     rax, [rbx]
0x1804912ef  mov     rcx, rbx
0x1804912f2  mov     rax, [rax+80h]
0x1804912f9  call    cs:__guard_dispatch_icall_fptr
0x1804912ff  mov     r8, rax; error
0x180491302  lea     rdx, [rsp+370h+var_328]; string2
0x180491307  mov     rcx, [rsi+10h]; string1
0x18049130b  call    cs:__imp_WsXmlStringEquals
0x180491311  test    eax, eax
0x180491313  jz      loc_1804914EF
0x180491319  mov     rax, [rbx]
0x18049131c  mov     rcx, rbx
0x18049131f  mov     rax, [rax+80h]
0x180491326  call    cs:__guard_dispatch_icall_fptr
0x18049132c  mov     r8, rax; error
0x18049132f  lea     rdx, [rbp+270h+var_2B0]; string2
0x180491333  mov     rcx, [rsi+10h]; string1
0x180491337  call    cs:__imp_WsXmlStringEquals
0x18049133d  test    eax, eax
0x18049133f  jz      loc_18049154C
0x180491345  mov     rax, [rbx]
0x180491348  mov     rcx, rbx
0x18049134b  mov     rax, [rax+80h]
0x180491352  call    cs:__guard_dispatch_icall_fptr
0x180491358  mov     r8, rax; error
0x18049135b  lea     rdx, [rbp+270h+var_290]; string2
0x18049135f  mov     rcx, [rsi+10h]; string1
0x180491363  call    cs:__imp_WsXmlStringEquals
0x180491369  test    eax, eax
0x18049136b  jz      loc_180491534
0x180491371  mov     rax, [rbx]
0x180491374  mov     rcx, rbx
0x180491377  mov     rax, [rax+80h]
0x18049137e  call    cs:__guard_dispatch_icall_fptr
0x180491384  mov     r8, rax; error
0x180491387  lea     rdx, [rbp+270h+var_270]; string2
0x18049138b  mov     rcx, [rsi+10h]; string1
0x18049138f  call    cs:__imp_WsXmlStringEquals
0x180491395  test    eax, eax
0x180491397  jz      loc_180491564
0x18049139d  mov     rax, [rbx]
0x1804913a0  mov     rcx, rbx
0x1804913a3  mov     rax, [rax+80h]
0x1804913aa  call    cs:__guard_dispatch_icall_fptr
0x1804913b0  mov     r8, rax; error
0x1804913b3  lea     rdx, [rbp+270h+var_250]; string2
0x1804913b7  mov     rcx, [rsi+10h]; string1
0x1804913bb  call    cs:__imp_WsXmlStringEquals
0x1804913c1  test    eax, eax
0x1804913c3  jz      loc_180491597
0x1804913c9  mov     rax, [rbx]
0x1804913cc  mov     rcx, rbx
0x1804913cf  mov     rax, [rax+80h]
0x1804913d6  call    cs:__guard_dispatch_icall_fptr
0x1804913dc  mov     r8, rax; error
0x1804913df  lea     rdx, [rbp+270h+var_230]; string2
0x1804913e3  mov     rcx, [rsi+10h]; string1
0x1804913e7  call    cs:__imp_WsXmlStringEquals
0x1804913ed  test    eax, eax
0x1804913ef  jz      loc_18049151C
0x1804913f5  mov     rax, [rbx]
0x1804913f8  mov     rcx, rbx
0x1804913fb  mov     rax, [rax+80h]
0x180491402  call    cs:__guard_dispatch_icall_fptr
0x180491408  mov     r8, rax; error
0x18049140b  lea     rdx, [rbp+270h+var_210]; string2
0x18049140f  mov     rcx, [rsi+10h]; string1
0x180491413  call    cs:__imp_WsXmlStringEquals
0x180491419  test    eax, eax
0x18049141b  jz      loc_18049157C
0x180491421  mov     rax, [rbx]
0x180491424  mov     rcx, rbx
0x180491427  mov     rax, [rax+80h]
0x18049142e  call    cs:__guard_dispatch_icall_fptr
0x180491434  mov     r8, rax; error
0x180491437  lea     rdx, [rbp+270h+var_1F0]; string2
0x18049143e  mov     rcx, [rsi+10h]; string1
0x180491442  call    cs:__imp_WsXmlStringEquals
0x180491448  test    eax, eax
0x18049144a  jz      loc_180491504
0x180491450  mov     rax, [rbx]
0x180491453  mov     rcx, rbx
0x180491456  mov     rax, [rax+80h]
  ... truncated ...
```
