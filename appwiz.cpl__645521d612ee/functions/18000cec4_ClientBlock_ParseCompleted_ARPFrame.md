# ClientBlock::ParseCompleted(ARPFrame *)

- ea: `0x18000cec4`
- end: `0x18000d20c`
- name: `?ParseCompleted@ClientBlock@@QEAAJPEAVARPFrame@@@Z`
- size: `840`
- prototype: `__int64 __fastcall(ClientBlock *__hidden this, struct ARPFrame *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000fc80`

## callees

- `0x180008a88`
- `0x180009498`
- `0x18000aa98`
- `0x18000ac0c`
- `0x18000cec4`
- `0x18000e624`
- `0x18000e6b4`
- `0x18000f200`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `msvcrt!qsort` at `0x18000cfde`
- `msvcrt!qsort` at `0x18000cfde`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000d15a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000d15a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000d188`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000d188`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1b5`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18000cf64`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18000d06e`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18000cf64`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18000d06e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000cf08`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000cf08`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000d1ca`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000d1d7`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000d1ca`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000d1d7`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000cf89`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000d097`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000cf89`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000d097`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000d0e7`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000d1aa`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000d0e7`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000d1aa`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000d0cb`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000d0cb`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000cf2e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000cf2e`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000cf14`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000cf14`

## pseudocode

```c
__int64 __fastcall ClientBlock::ParseCompleted(struct DirectUI::Element **this, DirectUI::DUIXmlParser **a2)
{
  DirectUI::Value *Value; // rbx
  const unsigned __int16 *String; // rax
  int Element; // edi
  struct DirectUI::Element **v7; // r14
  struct DirectUI::Element *v8; // rcx
  int v9; // edx
  _QWORD *v10; // rcx
  unsigned int v11; // r15d
  struct DirectUI::Element *v12; // rcx
  int v13; // edx
  _QWORD *v14; // rcx
  struct DirectUI::Element *v15; // r9
  __int64 v16; // r13
  DirectUI::DUIXmlParser *v17; // rcx
  const unsigned __int16 *v18; // rbx
  DirectUI::Element *DescendentByName; // rax
  DirectUI::Element *v20; // rax
  struct DirectUI::Element *v21; // rax
  DirectUI::Element *v22; // rax
  struct DirectUI::Element *v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR lpBuffer[4]; // [rsp+48h] [rbp-B8h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  Value = DirectUI::Element::GetValue(
            (DirectUI::Element *)this,
            (const struct DirectUI::PropertyInfo *)&off_1800773C8,
            2,
            0);
  String = DirectUI::Value::GetString(Value);
  Element = StringList::SetStringList((StringList *)(this + 26), String);
  DirectUI::Value::Release(Value);
  if ( Element >= 0 )
  {
    v7 = this + 28;
    Element = DirectUI::DUIXmlParser::CreateElement(
                a2[35],
                L"clientblockselector",
                0,
                (struct DirectUI::Element *)this,
                0,
                this + 28);
    if ( Element >= 0 )
    {
      TraverseTree<DirectUI::Button>(*v7, (int (*)(struct DirectUI::Element *, __int64))FixDUIButtonAccessibilityCB);
      Element = DirectUI::Element::Add((DirectUI::Element *)this, *v7);
      if ( Element < 0 )
      {
        DirectUI::Element::Destroy(*v7, 1);
        *v7 = 0;
      }
      else
      {
        ClientBlock::_AddFromClientKey((ClientBlock *)this, 0);
        ClientBlock::_AddFromClientKey((ClientBlock *)this, 1);
        v8 = this[25];
        v9 = *(_DWORD *)v8;
        if ( (*(_DWORD *)v8 & 0xFFFFFFF) != 0 )
        {
          v10 = (_QWORD *)((char *)v8 + 8);
          if ( (v9 & 0x10000000) != 0 )
            v10 = (_QWORD *)*v10;
          qsort(v10, v9 & 0xFFFFFFF, 8u, CLIENTINFO::QSortCMP);
        }
        Element = ClientBlock::AddStaticClientInfoToTop(
                    (ClientBlock *)this,
                    (const struct DirectUI::PropertyInfo *)&off_1800773F8);
        if ( Element >= 0 )
          Element = ClientBlock::AddStaticClientInfoToTop(
                      (ClientBlock *)this,
                      (const struct DirectUI::PropertyInfo *)&off_180077458);
        v11 = 1;
        if ( Element >= 0 )
        {
          while ( 1 )
          {
            v12 = this[25];
            v13 = *(_DWORD *)v12;
            if ( v11 >= (*(_DWORD *)v12 & 0xFFFFFFFu) )
              break;
            v14 = (_QWORD *)((char *)v12 + 8);
            if ( (v13 & 0x10000000) != 0 )
              v14 = (_QWORD *)*v14;
            v15 = *v7;
            v16 = v14[v11];
            v17 = a2[35];
            v24 = 0;
            Element = DirectUI::DUIXmlParser::CreateElement(v17, L"clientitem", 0, v15, 0, &v24);
            if ( Element < 0 )
              break;
            TraverseTree<DirectUI::Button>(
              v24,
              (int (*)(struct DirectUI::Element *, __int64))FixDUIButtonAccessibilityCB);
            Element = DirectUI::Element::Add(*v7, v24);
            if ( Element < 0 )
            {
              DirectUI::Element::Destroy(v24, 1);
              return (unsigned int)Element;
            }
            v18 = *(const unsigned __int16 **)(v16 + 8);
            *(_QWORD *)(v16 + 32) = v24;
            DescendentByName = FindDescendentByName(v24, L"radiotext");
            DirectUI::Element::SetContentString(DescendentByName, v18);
            v20 = FindDescendentByName(*(struct DirectUI::Element **)(v16 + 32), L"setdefault");
            DirectUI::Element::SetAccName(v20, v18);
            if ( *(_QWORD *)v16 )
            {
              CLIENTINFO::SetShowCheckbox((CLIENTINFO *)v16, *(_BYTE *)(v16 + 41));
              Arguments = *(va_list *)(v16 + 8);
              *(_QWORD *)lpBuffer = 0;
              LoadStringW(g_hinst, 0x8Au, Buffer, 260);
              if ( FormatMessageW(0x2500u, Buffer, 0, 0, lpBuffer, 0, &Arguments) )
              {
                v22 = FindDescendentByName(*(struct DirectUI::Element **)(v16 + 32), L"show");
                DirectUI::Element::SetAccName(v22, *(const unsigned __int16 **)lpBuffer);
                LocalFree(*(HLOCAL *)lpBuffer);
              }
            }
            else
            {
              v21 = FindDescendentByName(v24, L"show");
              DisableElementTreeShortcut(v21);
              (*(void (__fastcall **)(struct DirectUI::Element *, struct DirectUI::Element *))(*(_QWORD *)*v7 + 360LL))(
                *v7,
                v24);
            }
            ++v11;
          }
        }
      }
    }
  }
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x18000cec4  mov     [rsp-8+arg_10], rbx
0x18000cec9  push    rbp
0x18000ceca  push    rsi
0x18000cecb  push    rdi
0x18000cecc  push    r12
0x18000cece  push    r13
0x18000ced0  push    r14
0x18000ced2  push    r15
0x18000ced4  lea     rbp, [rsp-180h]
0x18000cedc  sub     rsp, 280h
0x18000cee3  mov     rax, cs:__security_cookie
0x18000ceea  xor     rax, rsp
0x18000ceed  mov     [rbp+1B0h+var_40], rax
0x18000cef4  xor     r9d, r9d
0x18000cef7  mov     r12, rdx
0x18000cefa  lea     rdx, off_1800773C8; "OtherMSClients"
0x18000cf01  mov     rsi, rcx
0x18000cf04  lea     r8d, [r9+2]
0x18000cf08  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18000cf0e  mov     rcx, rax
0x18000cf11  mov     rbx, rax
0x18000cf14  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18000cf1a  mov     rdx, rax; unsigned __int16 *
0x18000cf1d  lea     rcx, [rsi+0D0h]; this
0x18000cf24  call    ?SetStringList@StringList@@QEAAJPEBG@Z; StringList::SetStringList(ushort const *)
0x18000cf29  mov     rcx, rbx
0x18000cf2c  mov     edi, eax
0x18000cf2e  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000cf34  xor     ebx, ebx
0x18000cf36  test    edi, edi
0x18000cf38  js      loc_18000D1E0
0x18000cf3e  mov     rcx, [r12+118h]
0x18000cf46  lea     r14, [rsi+0E0h]
0x18000cf4d  mov     qword ptr [rsp+2B0h+nSize], r14
0x18000cf52  lea     rdx, aClientblocksel; "clientblockselector"
0x18000cf59  mov     r9, rsi
0x18000cf5c  mov     [rsp+2B0h+lpBuffer], rbx
0x18000cf61  xor     r8d, r8d
0x18000cf64  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000cf6a  mov     edi, eax
0x18000cf6c  test    eax, eax
0x18000cf6e  js      loc_18000D1E0
0x18000cf74  mov     rcx, [r14]; struct DirectUI::Element *
0x18000cf77  lea     rdx, ?FixDUIButtonAccessibilityCB@@YAJPEAVButton@DirectUI@@_J@Z; int (*)(struct DirectUI::Element *, __int64)
0x18000cf7e  call    ??$TraverseTree@VButton@DirectUI@@@@YAJPEAVElement@DirectUI@@P6AJPEAVButton@1@_J@Z2@Z; TraverseTree<DirectUI::Button>(DirectUI::Element *,long (*)(DirectUI::Button *,__int64),__int64)
0x18000cf83  mov     rdx, [r14]
0x18000cf86  mov     rcx, rsi
0x18000cf89  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18000cf8f  mov     edi, eax
0x18000cf91  test    eax, eax
0x18000cf93  js      loc_18000D1D2
0x18000cf99  xor     edx, edx; bool
0x18000cf9b  mov     rcx, rsi; this
0x18000cf9e  call    ?_AddFromClientKey@ClientBlock@@AEAAJ_N@Z; ClientBlock::_AddFromClientKey(bool)
0x18000cfa3  mov     dl, 1; bool
0x18000cfa5  mov     rcx, rsi; this
0x18000cfa8  call    ?_AddFromClientKey@ClientBlock@@AEAAJ_N@Z; ClientBlock::_AddFromClientKey(bool)
0x18000cfad  mov     rcx, [rsi+0C8h]
0x18000cfb4  mov     edx, [rcx]
0x18000cfb6  test    edx, 0FFFFFFFh
0x18000cfbc  jz      short loc_18000CFE4
0x18000cfbe  add     rcx, 8
0x18000cfc2  bt      edx, 1Ch
0x18000cfc6  jnb     short loc_18000CFCB
0x18000cfc8  mov     rcx, [rcx]; Base
0x18000cfcb  and     edx, 0FFFFFFFh; NumOfElements
0x18000cfd1  lea     r9, ?QSortCMP@CLIENTINFO@@SAHPEBX0@Z; CompareFunction
0x18000cfd8  mov     r8d, 8; SizeOfElements
0x18000cfde  call    cs:__imp_qsort
0x18000cfe4  lea     rdx, off_1800773F8; struct DirectUI::PropertyInfo *
0x18000cfeb  mov     rcx, rsi; this
0x18000cfee  call    ?AddStaticClientInfoToTop@ClientBlock@@QEAAJPEBUPropertyInfo@DirectUI@@@Z; ClientBlock::AddStaticClientInfoToTop(DirectUI::PropertyInfo const *)
0x18000cff3  mov     edi, eax
0x18000cff5  test    eax, eax
0x18000cff7  js      short loc_18000D00A
0x18000cff9  lea     rdx, off_180077458; struct DirectUI::PropertyInfo *
0x18000d000  mov     rcx, rsi; this
0x18000d003  call    ?AddStaticClientInfoToTop@ClientBlock@@QEAAJPEBUPropertyInfo@DirectUI@@@Z; ClientBlock::AddStaticClientInfoToTop(DirectUI::PropertyInfo const *)
0x18000d008  mov     edi, eax
0x18000d00a  mov     r15d, 1
0x18000d010  test    edi, edi
0x18000d012  js      loc_18000D1E0
0x18000d018  mov     rcx, [rsi+0C8h]
0x18000d01f  mov     edx, [rcx]
0x18000d021  mov     eax, edx
0x18000d023  and     eax, 0FFFFFFFh
0x18000d028  cmp     r15d, eax
0x18000d02b  jnb     loc_18000D1E0
0x18000d031  add     rcx, 8
0x18000d035  bt      edx, 1Ch
0x18000d039  jnb     short loc_18000D03E
0x18000d03b  mov     rcx, [rcx]
0x18000d03e  mov     r9, [r14]
0x18000d041  lea     rdx, aClientitem; "clientitem"
0x18000d048  mov     eax, r15d
0x18000d04b  xor     r8d, r8d
0x18000d04e  mov     r13, [rcx+rax*8]
0x18000d052  lea     rax, [rsp+2B0h+var_270]
0x18000d057  mov     rcx, [r12+118h]
0x18000d05f  mov     qword ptr [rsp+2B0h+nSize], rax
0x18000d064  mov     [rsp+2B0h+lpBuffer], rbx
0x18000d069  mov     [rsp+2B0h+var_270], rbx
0x18000d06e  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000d074  mov     edi, eax
0x18000d076  test    eax, eax
0x18000d078  js      loc_18000D1E0
0x18000d07e  mov     rcx, [rsp+2B0h+var_270]; struct DirectUI::Element *
0x18000d083  lea     rdx, ?FixDUIButtonAccessibilityCB@@YAJPEAVButton@DirectUI@@_J@Z; int (*)(struct DirectUI::Element *, __int64)
0x18000d08a  call    ??$TraverseTree@VButton@DirectUI@@@@YAJPEAVElement@DirectUI@@P6AJPEAVButton@1@_J@Z2@Z; TraverseTree<DirectUI::Button>(DirectUI::Element *,long (*)(DirectUI::Button *,__int64),__int64)
0x18000d08f  mov     rdx, [rsp+2B0h+var_270]
0x18000d094  mov     rcx, [r14]
0x18000d097  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18000d09d  mov     edi, eax
0x18000d09f  test    eax, eax
0x18000d0a1  js      loc_18000D1C3
0x18000d0a7  mov     rax, [rsp+2B0h+var_270]
0x18000d0ac  lea     rdx, aRadiotext; "radiotext"
0x18000d0b3  mov     rbx, [r13+8]
0x18000d0b7  mov     [r13+20h], rax
0x18000d0bb  mov     rcx, [rsp+2B0h+var_270]; struct DirectUI::Element *
0x18000d0c0  call    ?FindDescendentByName@@YAPEAVElement@DirectUI@@PEAV12@PEBG@Z; FindDescendentByName(DirectUI::Element *,ushort const *)
0x18000d0c5  mov     rdx, rbx
0x18000d0c8  mov     rcx, rax
0x18000d0cb  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18000d0d1  mov     rcx, [r13+20h]; struct DirectUI::Element *
0x18000d0d5  lea     rdx, aSetdefault; "setdefault"
0x18000d0dc  call    ?FindDescendentByName@@YAPEAVElement@DirectUI@@PEAV12@PEBG@Z; FindDescendentByName(DirectUI::Element *,ushort const *)
0x18000d0e1  mov     rdx, rbx
0x18000d0e4  mov     rcx, rax
0x18000d0e7  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x18000d0ed  xor     ebx, ebx
0x18000d0ef  cmp     [r13+0], rbx
0x18000d0f3  jnz     short loc_18000D12A
0x18000d0f5  mov     rcx, [rsp+2B0h+var_270]; struct DirectUI::Element *
0x18000d0fa  lea     rdx, aShow; "show"
0x18000d101  call    ?FindDescendentByName@@YAPEAVElement@DirectUI@@PEAV12@PEBG@Z; FindDescendentByName(DirectUI::Element *,ushort const *)
0x18000d106  mov     rcx, rax; struct DirectUI::Element *
0x18000d109  call    ?DisableElementTreeShortcut@@YAXPEAVElement@DirectUI@@@Z; DisableElementTreeShortcut(DirectUI::Element *)
0x18000d10e  mov     rcx, [r14]
0x18000d111  mov     rdx, [rsp+2B0h+var_270]
0x18000d116  mov     rax, [rcx]
0x18000d119  mov     rax, [rax+168h]
0x18000d120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d125  jmp     loc_18000D1BB
0x18000d12a  mov     dl, [r13+29h]; bool
0x18000d12e  mov     rcx, r13; this
0x18000d131  call    ?SetShowCheckbox@CLIENTINFO@@QEAAJ_N@Z; CLIENTINFO::SetShowCheckbox(bool)
0x18000d136  mov     rax, [r13+8]
0x18000d13a  lea     r8, [rsp+2B0h+Buffer]; lpBuffer
0x18000d13f  mov     rcx, cs:g_hinst; hInstance
0x18000d146  mov     r9d, 104h; cchBufferMax
0x18000d14c  mov     [rsp+2B0h+var_260], rax
0x18000d151  mov     qword ptr [rsp+2B0h+var_268], rbx
0x18000d156  lea     edx, [r9-7Ah]; uID
0x18000d15a  call    cs:__imp_LoadStringW
0x18000d160  lea     rax, [rsp+2B0h+var_260]
0x18000d165  xor     r9d, r9d; dwLanguageId
0x18000d168  mov     [rsp+2B0h+Arguments], rax; Arguments
0x18000d16d  lea     rdx, [rsp+2B0h+Buffer]; lpSource
0x18000d172  lea     rax, [rsp+2B0h+var_268]
0x18000d177  mov     [rsp+2B0h+nSize], ebx; nSize
0x18000d17b  xor     r8d, r8d; dwMessageId
0x18000d17e  mov     [rsp+2B0h+lpBuffer], rax; lpBuffer
0x18000d183  mov     ecx, 2500h; dwFlags
0x18000d188  call    cs:__imp_FormatMessageW
0x18000d18e  test    eax, eax
0x18000d190  jz      short loc_18000D1BB
0x18000d192  mov     rcx, [r13+20h]; struct DirectUI::Element *
0x18000d196  lea     rdx, aShow; "show"
0x18000d19d  call    ?FindDescendentByName@@YAPEAVElement@DirectUI@@PEAV12@PEBG@Z; FindDescendentByName(DirectUI::Element *,ushort const *)
0x18000d1a2  mov     rdx, qword ptr [rsp+2B0h+var_268]
0x18000d1a7  mov     rcx, rax
0x18000d1aa  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x18000d1b0  mov     rcx, qword ptr [rsp+2B0h+var_268]; hMem
0x18000d1b5  call    cs:__imp_LocalFree
0x18000d1bb  inc     r15d
0x18000d1be  jmp     loc_18000D018
0x18000d1c3  mov     rcx, [rsp+2B0h+var_270]
0x18000d1c8  mov     dl, 1
0x18000d1ca  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000d1d0  jmp     short loc_18000D1E0
0x18000d1d2  mov     rcx, [r14]
0x18000d1d5  mov     dl, 1
0x18000d1d7  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000d1dd  mov     [r14], rbx
0x18000d1e0  mov     eax, edi
0x18000d1e2  mov     rcx, [rbp+1B0h+var_40]
0x18000d1e9  xor     rcx, rsp; StackCookie
0x18000d1ec  call    __security_check_cookie
0x18000d1f1  mov     rbx, [rsp+2B0h+arg_10]
0x18000d1f9  add     rsp, 280h
0x18000d200  pop     r15
0x18000d202  pop     r14
0x18000d204  pop     r13
0x18000d206  pop     r12
0x18000d208  pop     rdi
0x18000d209  pop     rsi
0x18000d20a  pop     rbp
0x18000d20b  retn
```
