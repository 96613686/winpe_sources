# CSmsMessageStore::GetMessageXML(unsigned __int64,IXMLDOMDocument * *)

- ea: `0x18001d548`
- end: `0x18001d72b`
- name: `?GetMessageXML@CSmsMessageStore@@QEAAJ_KPEAPEAUIXMLDOMDocument@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(CSmsMessageStore *__hidden this, unsigned __int64, struct IXMLDOMDocument **)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034c5c`
- `0x180035ff8`
- `0x180036650`

## callees

- `0x180015aac`
- `0x18001993c`
- `0x18001d3c8`
- `0x18001d548`
- `0x1800216e4`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d6e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d6e5`

## string_xrefs

- `0x18001d5c8`: `CSmsMessageStore::GetMessageXML`
- `0x18001d6aa`: `CSmsMessageStore::GetMessageXML`
- `0x18001d69b`: `Malformed XML: %S`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSmsMessageStore::GetMessageXML(
        CSmsMessageStore *this,
        unsigned __int64 a2,
        struct IXMLDOMDocument **a3)
{
  wchar_t *v5; // rbx
  char *v6; // rsi
  struct IXMLDOMDocument *v7; // rdi
  int MessageW; // ebx
  char *v9; // r15
  unsigned int v10; // r14d
  __int64 v11; // rax
  struct IXMLDOMDocument *v12; // r15
  int XmlDocument; // eax
  _BYTE v15[16]; // [rsp+38h] [rbp-28h] BYREF
  void **v16; // [rsp+48h] [rbp-18h]
  char *v17; // [rsp+50h] [rbp-10h]
  struct IXMLDOMDocument *v18; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int64 v19; // [rsp+A8h] [rbp+48h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp+58h] BYREF

  v19 = a2;
  hMem = 0;
  v5 = 0;
  v16 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v6 = (char *)this + 8;
  v17 = (char *)this + 8;
  (**((void (__fastcall ***)(char *))this + 1))((char *)this + 8);
  v7 = 0;
  v18 = 0;
  if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                    (char *)this + 112,
                    v15,
                    &v19) == *((_QWORD *)this + 15) )
  {
    MessageW = -2147023728;
    LogSmsRouterError("CSmsMessageStore::GetMessageXML", 0x1A1u, -2147023728, "Message not found");
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
    return (unsigned int)MessageW;
  }
  v9 = (char *)this + 176;
  if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                    (char *)this + 176,
                    v15,
                    &v19) == *((_QWORD *)this + 23)
    || !*(_QWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                                 (__int64)this + 176,
                                 (__int64)v15,
                                 &v19)
                  + 64LL) )
  {
    MessageW = CSmsMessageStore::GetMessageW(this, v19, (unsigned __int16 **)&hMem);
    if ( MessageW < 0 )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
      return (unsigned int)MessageW;
    }
    v5 = (wchar_t *)hMem;
    XmlDocument = Windows::Sms::Common::CSmsUtil::GetXmlDocument((const unsigned __int16 *)hMem, (LPVOID *)&v18);
    v10 = XmlDocument;
    if ( XmlDocument < 0 )
    {
      LogSmsRouterError("CSmsMessageStore::GetMessageXML", 0x1B0u, XmlDocument, "Malformed XML: %S", v5);
      if ( v18 )
        ((void (__fastcall *)(struct IXMLDOMDocument *))v18->lpVtbl->Release)(v18);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
      goto LABEL_12;
    }
    v7 = v18;
  }
  else
  {
    v10 = 0;
    v11 = std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::_Try_emplace<unsigned __int64 const &,>(
            (__int64)v9,
            (__int64)v15,
            &v19);
    v12 = *(struct IXMLDOMDocument **)(*(_QWORD *)v11 + 64LL);
    if ( v12 )
    {
      ((void (__fastcall *)(_QWORD))v12->lpVtbl->AddRef)(*(_QWORD *)(*(_QWORD *)v11 + 64LL));
      v7 = v12;
    }
  }
  *a3 = v7;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
LABEL_12:
  if ( v5 )
    LocalFree(v5);
  return v10;
}

```

## disassembly

```asm
0x18001d548  mov     [rsp-38h+arg_8], rdx
0x18001d54d  push    rbp
0x18001d54e  push    rbx
0x18001d54f  push    rsi
0x18001d550  push    rdi
0x18001d551  push    r12
0x18001d553  push    r14
0x18001d555  push    r15
0x18001d557  mov     rbp, rsp
0x18001d55a  sub     rsp, 60h
0x18001d55e  mov     r12, r8
0x18001d561  mov     r14, rcx
0x18001d564  mov     [rbp+hMem], 0
0x18001d56c  xor     ebx, ebx
0x18001d56e  mov     [rbp+var_30], rbx
0x18001d572  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18001d579  mov     [rbp+var_18], rax
0x18001d57d  lea     rsi, [rcx+8]
0x18001d581  mov     [rbp+var_10], rsi
0x18001d585  mov     rax, [rsi]
0x18001d588  mov     rcx, rsi
0x18001d58b  mov     rax, [rax]
0x18001d58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d593  nop
0x18001d594  xor     edi, edi
0x18001d596  mov     [rbp+arg_0], rdi
0x18001d59a  lea     rcx, [r14+70h]
0x18001d59e  lea     r8, [rbp+arg_8]
0x18001d5a2  lea     rdx, [rbp+var_28]
0x18001d5a6  call    ?find@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(unsigned __int64 const &)
0x18001d5ab  mov     rcx, [r14+78h]
0x18001d5af  cmp     [rax], rcx
0x18001d5b2  jnz     short loc_18001D5EA
0x18001d5b4  lea     r9, aMessageNotFoun; "Message not found"
0x18001d5bb  mov     ebx, 80070490h
0x18001d5c0  mov     r8d, ebx; int
0x18001d5c3  mov     edx, 1A1h; unsigned int
0x18001d5c8  lea     rcx, aCsmsmessagesto_1; "CSmsMessageStore::GetMessageXML"
0x18001d5cf  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001d5d4  nop
0x18001d5d5  mov     rdx, [rsi]
0x18001d5d8  mov     rcx, rsi
0x18001d5db  mov     rax, [rdx+8]
0x18001d5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5e4  nop
0x18001d5e5  jmp     loc_18001D71A
0x18001d5ea  lea     r15, [r14+0B0h]
0x18001d5f1  lea     r8, [rbp+arg_8]
0x18001d5f5  lea     rdx, [rbp+var_28]
0x18001d5f9  mov     rcx, r15
0x18001d5fc  call    ?find@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(unsigned __int64 const &)
0x18001d601  mov     rcx, [r14+0B8h]
0x18001d608  cmp     [rax], rcx
0x18001d60b  jz      short loc_18001D661
0x18001d60d  lea     r8, [rbp+arg_8]
0x18001d611  lea     rdx, [rbp+var_28]
0x18001d615  mov     rcx, r15
0x18001d618  call    ??$_Try_emplace@AEB_K$$V@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_KUMessageProcessingState@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x18001d61d  mov     rdx, [rax]
0x18001d620  cmp     qword ptr [rdx+40h], 0
0x18001d625  jz      short loc_18001D661
0x18001d627  xor     r14d, r14d
0x18001d62a  lea     r8, [rbp+arg_8]
0x18001d62e  lea     rdx, [rbp+var_28]
0x18001d632  mov     rcx, r15
0x18001d635  call    ??$_Try_emplace@AEB_K$$V@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_KUMessageProcessingState@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x18001d63a  mov     rcx, [rax]
0x18001d63d  mov     r15, [rcx+40h]
0x18001d641  test    r15, r15
0x18001d644  jz      loc_18001D6F4
0x18001d64a  mov     rax, [r15]
0x18001d64d  mov     rcx, r15
0x18001d650  mov     rax, [rax+8]
0x18001d654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d659  mov     rdi, r15
0x18001d65c  jmp     loc_18001D6F4
0x18001d661  lea     r8, [rbp+hMem]; unsigned __int16 **
0x18001d665  mov     rdx, [rbp+arg_8]; unsigned __int64
0x18001d669  mov     rcx, r14; this
0x18001d66c  call    ?GetMessageW@CSmsMessageStore@@AEAAJ_KPEAPEAG@Z; CSmsMessageStore::GetMessageW(unsigned __int64,ushort * *)
0x18001d671  mov     ebx, eax
0x18001d673  test    eax, eax
0x18001d675  js      loc_18001D70A
0x18001d67b  lea     rdx, [rbp+arg_0]; struct IXMLDOMDocument **
0x18001d67f  mov     rbx, [rbp+hMem]
0x18001d683  mov     rcx, rbx; unsigned __int16 *
0x18001d686  call    ?GetXmlDocument@CSmsUtil@Common@Sms@Windows@@SAJPEBGPEAPEAUIXMLDOMDocument@@@Z; Windows::Sms::Common::CSmsUtil::GetXmlDocument(ushort const *,IXMLDOMDocument * *)
0x18001d68b  mov     r14d, eax
0x18001d68e  mov     [rbp+var_30], rbx
0x18001d692  test    eax, eax
0x18001d694  jns     short loc_18001D6F0
0x18001d696  mov     [rsp+60h+var_40], rbx
0x18001d69b  lea     r9, aMalformedXmlS; "Malformed XML: %S"
0x18001d6a2  mov     r8d, eax; int
0x18001d6a5  mov     edx, 1B0h; unsigned int
0x18001d6aa  lea     rcx, aCsmsmessagesto_1; "CSmsMessageStore::GetMessageXML"
0x18001d6b1  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001d6b6  nop
0x18001d6b7  mov     rcx, [rbp+arg_0]
0x18001d6bb  test    rcx, rcx
0x18001d6be  jz      short loc_18001D6CD
0x18001d6c0  mov     rax, [rcx]
0x18001d6c3  mov     rax, [rax+10h]
0x18001d6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6cc  nop
0x18001d6cd  mov     rax, [rsi]
0x18001d6d0  mov     rcx, rsi
0x18001d6d3  mov     rax, [rax+8]
0x18001d6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6dc  nop
0x18001d6dd  test    rbx, rbx
0x18001d6e0  jz      short loc_18001D6EB
0x18001d6e2  mov     rcx, rbx; hMem
0x18001d6e5  call    cs:__imp_LocalFree
0x18001d6eb  mov     eax, r14d
0x18001d6ee  jmp     short loc_18001D71C
0x18001d6f0  mov     rdi, [rbp+arg_0]
0x18001d6f4  mov     [r12], rdi
0x18001d6f8  mov     rax, [rsi]
0x18001d6fb  mov     rcx, rsi
0x18001d6fe  mov     rax, [rax+8]
0x18001d702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d707  nop
0x18001d708  jmp     short loc_18001D6DD
0x18001d70a  mov     rax, [rsi]
0x18001d70d  mov     rcx, rsi
0x18001d710  mov     rax, [rax+8]
0x18001d714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d719  nop
0x18001d71a  mov     eax, ebx
0x18001d71c  add     rsp, 60h
0x18001d720  pop     r15
0x18001d722  pop     r14
0x18001d724  pop     r12
0x18001d726  pop     rdi
0x18001d727  pop     rsi
0x18001d728  pop     rbx
0x18001d729  pop     rbp
0x18001d72a  retn
```
