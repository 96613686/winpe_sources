# CSmsMessageFilterFactory::GetSmsMessageFilter(ushort *,ISmsMessageFilter * *)

- ea: `0x180068300`
- end: `0x180068637`
- name: `?GetSmsMessageFilter@CSmsMessageFilterFactory@@UEAAJPEAGPEAPEAUISmsMessageFilter@@@Z`
- size: `823`
- prototype: `__int64 __fastcall(CSmsMessageFilterFactory *__hidden this, unsigned __int16 *, struct ISmsMessageFilter **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180003a90`
- `0x18000d388`
- `0x180067978`
- `0x180067a14`
- `0x180067a84`
- `0x180068300`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006832b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068360`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800683f0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068425`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006845a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006848f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800684c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800684f9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006852e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068563`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068598`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800685ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068601`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006832b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068360`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800683f0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068425`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006845a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006848f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800684c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800684f9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006852e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068563`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068598`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800685ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068601`

## string_xrefs

- `0x180068406`: `/Message/Imsi`
- `0x18006850f`: `/Message/ProtocolId`
- `0x180068524`: `TeleserviceId`
- `0x1800684ef`: `ProtocolId`
- `0x180068544`: `/Message/TeleserviceId`
- `0x1800683e6`: `ImsiPrefix`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CSmsMessageFilterFactory::GetSmsMessageFilter(
        CSmsMessageFilterFactory *this,
        unsigned __int16 *a2,
        struct ISmsMessageFilter **a3)
{
  struct ISmsMessageFilter *v6; // rax
  unsigned int v7; // edi
  void *v8; // [rsp+58h] [rbp+30h]
  char *v9; // [rsp+58h] [rbp+30h]
  void *v10; // [rsp+58h] [rbp+30h]
  void *v11; // [rsp+58h] [rbp+30h]
  void *v12; // [rsp+58h] [rbp+30h]
  void *v13; // [rsp+58h] [rbp+30h]
  void *v14; // [rsp+58h] [rbp+30h]
  void *v15; // [rsp+58h] [rbp+30h]
  void *v16; // [rsp+58h] [rbp+30h]
  void *v17; // [rsp+58h] [rbp+30h]
  void *v18; // [rsp+58h] [rbp+30h]
  void *v19; // [rsp+58h] [rbp+30h]
  void *v20; // [rsp+58h] [rbp+30h]

  if ( !a2 )
    return 2147942487LL;
  if ( !(unsigned int)_o__wcsicmp(a2, L"TextPrefix") )
  {
    v8 = operator new(0x50u);
    v6 = (struct ISmsMessageFilter *)CSmsMessageFilter<PrefixListFilter>::CSmsMessageFilter<PrefixListFilter>(
                                       v8,
                                       L"/Message/Text");
LABEL_29:
    *a3 = v6;
    return 0;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"MessageType") )
  {
    v9 = (char *)operator new(0x58u);
    *(_QWORD *)v9 = &CSmsMessageFilter<StringMatchIgnoreCaseFilter>::`vftable';
    *((_DWORD *)v9 + 2) = 1;
    *((_OWORD *)v9 + 1) = 0;
    *((_QWORD *)v9 + 4) = 0;
    *((_QWORD *)v9 + 5) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)v9 + 2, L"/Message/MessageType", 0x14u);
    *((_QWORD *)v9 + 6) = &StringMatchIgnoreCaseFilter::`vftable';
    *(_OWORD *)(v9 + 56) = 0;
    *((_QWORD *)v9 + 9) = 0;
    *((_QWORD *)v9 + 10) = 7;
    *((_WORD *)v9 + 28) = 0;
    *a3 = (struct ISmsMessageFilter *)v9;
    return 0;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"ImsiPrefix") )
  {
    v10 = operator new(0x50u);
    v6 = (struct ISmsMessageFilter *)CSmsMessageFilter<PrefixListFilter>::CSmsMessageFilter<PrefixListFilter>(
                                       v10,
                                       L"/Message/Imsi");
    goto LABEL_29;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"SmsDeviceId") )
  {
    v11 = operator new(0x50u);
    v6 = (struct ISmsMessageFilter *)CSmsMessageFilter<StringListIgnoreCaseFilter>::CSmsMessageFilter<StringListIgnoreCaseFilter>(
                                       v11,
                                       L"/Message/SmsDeviceId");
    goto LABEL_29;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"SenderNumber") )
  {
    v12 = operator new(0x50u);
    v6 = (struct ISmsMessageFilter *)CSmsMessageFilter<StringListIgnoreCaseFilter>::CSmsMessageFilter<StringListIgnoreCaseFilter>(
                                       v12,
                                       L"/Message/Sender");
    goto LABEL_29;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"PortNumber") )
  {
    v13 = operator new(0x48u);
    v6 = (struct ISmsMessageFilter *)CSmsMessageFilter<IntegerListIgnoreCaseFilter>::CSmsMessageFilter<IntegerListIgnoreCaseFilter>(
                                       v13,
                                       L"/Message/Port");
    goto LABEL_29;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"CellularClass") )
  {
    v14 = operator new(0x50u);
    v6 = (struct ISmsMessageFilter *)CSmsMessageFilter<StringListIgnoreCaseFilter>::CSmsMessageFilter<StringListIgnoreCaseFilter>(
                                       v14,
                                       L"/Message/CellularClass");
    goto LABEL_29;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"ProtocolId") )
  {
    v15 = operator new(0x48u);
    v6 = (struct ISmsMessageFilter *)CSmsMessageFilter<IntegerListIgnoreCaseFilter>::CSmsMessageFilter<IntegerListIgnoreCaseFilter>(
                                       v15,
                                       L"/Message/ProtocolId");
    goto LABEL_29;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"TeleserviceId") )
  {
    v16 = operator new(0x48u);
    v6 = (struct ISmsMessageFilter *)CSmsMessageFilter<IntegerListIgnoreCaseFilter>::CSmsMessageFilter<IntegerListIgnoreCaseFilter>(
                                       v16,
                                       L"/Message/TeleserviceId");
    goto LABEL_29;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"WapApplicationId") )
  {
    v17 = operator new(0x50u);
    v6 = (struct ISmsMessageFilter *)CSmsMessageFilter<StringListIgnoreCaseFilter>::CSmsMessageFilter<StringListIgnoreCaseFilter>(
                                       v17,
                                       L"/Message/ApplicationId");
    goto LABEL_29;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"WapContentType") )
  {
    v18 = operator new(0x50u);
    v6 = (struct ISmsMessageFilter *)CSmsMessageFilter<StringListIgnoreCaseFilter>::CSmsMessageFilter<StringListIgnoreCaseFilter>(
                                       v18,
                                       L"/Message/ContentType");
    goto LABEL_29;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"BroadcastType") )
  {
    v19 = operator new(0x50u);
    v6 = (struct ISmsMessageFilter *)CSmsMessageFilter<StringListIgnoreCaseFilter>::CSmsMessageFilter<StringListIgnoreCaseFilter>(
                                       v19,
                                       L"/Message/BroadcastType");
    goto LABEL_29;
  }
  v7 = -2147023728;
  if ( !(unsigned int)_o__wcsicmp(a2, L"BroadcastChannel") )
  {
    v20 = operator new(0x48u);
    v6 = (struct ISmsMessageFilter *)CSmsMessageFilter<IntegerListIgnoreCaseFilter>::CSmsMessageFilter<IntegerListIgnoreCaseFilter>(
                                       v20,
                                       L"/Message/BroadcastChannel");
    goto LABEL_29;
  }
  return v7;
}

```

## disassembly

```asm
0x180068300  push    rbp
0x180068302  push    rbx
0x180068303  push    rsi
0x180068304  push    rdi
0x180068305  mov     rbp, rsp
0x180068308  sub     rsp, 28h
0x18006830c  mov     rsi, r8
0x18006830f  mov     rbx, rdx
0x180068312  test    rdx, rdx
0x180068315  jnz     short loc_180068321
0x180068317  mov     eax, 80070057h
0x18006831c  jmp     loc_18006862E
0x180068321  lea     rdx, aTextprefix; "TextPrefix"
0x180068328  mov     rcx, rbx
0x18006832b  call    cs:__imp__o__wcsicmp
0x180068331  test    eax, eax
0x180068333  jnz     short loc_180068356
0x180068335  lea     ecx, [rax+50h]; Size
0x180068338  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006833d  mov     [rbp+arg_8], rax
0x180068341  lea     rdx, aMessageText; "/Message/Text"
0x180068348  mov     rcx, rax
0x18006834b  call    ??0?$CSmsMessageFilter@VPrefixListFilter@@@@QEAA@PEBG@Z; CSmsMessageFilter<PrefixListFilter>::CSmsMessageFilter<PrefixListFilter>(ushort const *)
0x180068350  nop
0x180068351  jmp     loc_180068627
0x180068356  lea     rdx, aMessagetype; "MessageType"
0x18006835d  mov     rcx, rbx
0x180068360  call    cs:__imp__o__wcsicmp
0x180068366  test    eax, eax
0x180068368  jnz     short loc_1800683E6
0x18006836a  lea     ecx, [rax+58h]; Size
0x18006836d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068372  mov     rbx, rax
0x180068375  mov     [rbp+arg_8], rax
0x180068379  lea     rax, ??_7?$CSmsMessageFilter@VStringMatchIgnoreCaseFilter@@@@6B@; const CSmsMessageFilter<StringMatchIgnoreCaseFilter>::`vftable'
0x180068380  mov     [rbx], rax
0x180068383  mov     dword ptr [rbx+8], 1
0x18006838a  lea     rcx, [rbx+10h]
0x18006838e  xorps   xmm0, xmm0
0x180068391  movups  xmmword ptr [rcx], xmm0
0x180068394  mov     qword ptr [rcx+10h], 0
0x18006839c  mov     qword ptr [rcx+18h], 0
0x1800683a4  mov     r8d, 14h
0x1800683aa  lea     rdx, aMessageMessage; "/Message/MessageType"
0x1800683b1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800683b6  lea     rax, ??_7StringMatchIgnoreCaseFilter@@6B@; const StringMatchIgnoreCaseFilter::`vftable'
0x1800683bd  mov     [rbx+30h], rax
0x1800683c1  xorps   xmm0, xmm0
0x1800683c4  movups  xmmword ptr [rbx+38h], xmm0
0x1800683c8  mov     qword ptr [rbx+48h], 0
0x1800683d0  mov     qword ptr [rbx+50h], 7
0x1800683d8  xor     eax, eax
0x1800683da  mov     [rbx+38h], ax
0x1800683de  mov     [rsi], rbx
0x1800683e1  jmp     loc_18006862A
0x1800683e6  lea     rdx, aImsiprefix; "ImsiPrefix"
0x1800683ed  mov     rcx, rbx
0x1800683f0  call    cs:__imp__o__wcsicmp
0x1800683f6  test    eax, eax
0x1800683f8  jnz     short loc_18006841B
0x1800683fa  lea     ecx, [rax+50h]; Size
0x1800683fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068402  mov     [rbp+arg_8], rax
0x180068406  lea     rdx, aMessageImsi; "/Message/Imsi"
0x18006840d  mov     rcx, rax
0x180068410  call    ??0?$CSmsMessageFilter@VPrefixListFilter@@@@QEAA@PEBG@Z; CSmsMessageFilter<PrefixListFilter>::CSmsMessageFilter<PrefixListFilter>(ushort const *)
0x180068415  nop
0x180068416  jmp     loc_180068627
0x18006841b  lea     rdx, aSmsdeviceid; "SmsDeviceId"
0x180068422  mov     rcx, rbx
0x180068425  call    cs:__imp__o__wcsicmp
0x18006842b  test    eax, eax
0x18006842d  jnz     short loc_180068450
0x18006842f  lea     ecx, [rax+50h]; Size
0x180068432  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068437  mov     [rbp+arg_8], rax
0x18006843b  lea     rdx, aMessageSmsdevi; "/Message/SmsDeviceId"
0x180068442  mov     rcx, rax
0x180068445  call    ??0?$CSmsMessageFilter@VStringListIgnoreCaseFilter@@@@QEAA@PEBG@Z; CSmsMessageFilter<StringListIgnoreCaseFilter>::CSmsMessageFilter<StringListIgnoreCaseFilter>(ushort const *)
0x18006844a  nop
0x18006844b  jmp     loc_180068627
0x180068450  lea     rdx, aSendernumber; "SenderNumber"
0x180068457  mov     rcx, rbx
0x18006845a  call    cs:__imp__o__wcsicmp
0x180068460  test    eax, eax
0x180068462  jnz     short loc_180068485
0x180068464  lea     ecx, [rax+50h]; Size
0x180068467  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006846c  mov     [rbp+arg_8], rax
0x180068470  lea     rdx, aMessageSender; "/Message/Sender"
0x180068477  mov     rcx, rax
0x18006847a  call    ??0?$CSmsMessageFilter@VStringListIgnoreCaseFilter@@@@QEAA@PEBG@Z; CSmsMessageFilter<StringListIgnoreCaseFilter>::CSmsMessageFilter<StringListIgnoreCaseFilter>(ushort const *)
0x18006847f  nop
0x180068480  jmp     loc_180068627
0x180068485  lea     rdx, aPortnumber; "PortNumber"
0x18006848c  mov     rcx, rbx
0x18006848f  call    cs:__imp__o__wcsicmp
0x180068495  test    eax, eax
0x180068497  jnz     short loc_1800684BA
0x180068499  lea     ecx, [rax+48h]; Size
0x18006849c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800684a1  mov     [rbp+arg_8], rax
0x1800684a5  lea     rdx, aMessagePort; "/Message/Port"
0x1800684ac  mov     rcx, rax
0x1800684af  call    ??0?$CSmsMessageFilter@VIntegerListIgnoreCaseFilter@@@@QEAA@PEBG@Z; CSmsMessageFilter<IntegerListIgnoreCaseFilter>::CSmsMessageFilter<IntegerListIgnoreCaseFilter>(ushort const *)
0x1800684b4  nop
0x1800684b5  jmp     loc_180068627
0x1800684ba  lea     rdx, aCellularclass; "CellularClass"
0x1800684c1  mov     rcx, rbx
0x1800684c4  call    cs:__imp__o__wcsicmp
0x1800684ca  test    eax, eax
0x1800684cc  jnz     short loc_1800684EF
0x1800684ce  lea     ecx, [rax+50h]; Size
0x1800684d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800684d6  mov     [rbp+arg_8], rax
0x1800684da  lea     rdx, aMessageCellula; "/Message/CellularClass"
0x1800684e1  mov     rcx, rax
0x1800684e4  call    ??0?$CSmsMessageFilter@VStringListIgnoreCaseFilter@@@@QEAA@PEBG@Z; CSmsMessageFilter<StringListIgnoreCaseFilter>::CSmsMessageFilter<StringListIgnoreCaseFilter>(ushort const *)
0x1800684e9  nop
0x1800684ea  jmp     loc_180068627
0x1800684ef  lea     rdx, aProtocolid; "ProtocolId"
0x1800684f6  mov     rcx, rbx
0x1800684f9  call    cs:__imp__o__wcsicmp
0x1800684ff  test    eax, eax
0x180068501  jnz     short loc_180068524
0x180068503  lea     ecx, [rax+48h]; Size
0x180068506  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006850b  mov     [rbp+arg_8], rax
0x18006850f  lea     rdx, aMessageProtoco; "/Message/ProtocolId"
0x180068516  mov     rcx, rax
0x180068519  call    ??0?$CSmsMessageFilter@VIntegerListIgnoreCaseFilter@@@@QEAA@PEBG@Z; CSmsMessageFilter<IntegerListIgnoreCaseFilter>::CSmsMessageFilter<IntegerListIgnoreCaseFilter>(ushort const *)
0x18006851e  nop
0x18006851f  jmp     loc_180068627
0x180068524  lea     rdx, aTeleserviceid; "TeleserviceId"
0x18006852b  mov     rcx, rbx
0x18006852e  call    cs:__imp__o__wcsicmp
0x180068534  test    eax, eax
0x180068536  jnz     short loc_180068559
0x180068538  lea     ecx, [rax+48h]; Size
0x18006853b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068540  mov     [rbp+arg_8], rax
0x180068544  lea     rdx, aMessageTeleser; "/Message/TeleserviceId"
0x18006854b  mov     rcx, rax
0x18006854e  call    ??0?$CSmsMessageFilter@VIntegerListIgnoreCaseFilter@@@@QEAA@PEBG@Z; CSmsMessageFilter<IntegerListIgnoreCaseFilter>::CSmsMessageFilter<IntegerListIgnoreCaseFilter>(ushort const *)
0x180068553  nop
0x180068554  jmp     loc_180068627
0x180068559  lea     rdx, aWapapplication; "WapApplicationId"
0x180068560  mov     rcx, rbx
0x180068563  call    cs:__imp__o__wcsicmp
0x180068569  test    eax, eax
0x18006856b  jnz     short loc_18006858E
0x18006856d  lea     ecx, [rax+50h]; Size
0x180068570  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068575  mov     [rbp+arg_8], rax
0x180068579  lea     rdx, aMessageApplica; "/Message/ApplicationId"
0x180068580  mov     rcx, rax
0x180068583  call    ??0?$CSmsMessageFilter@VStringListIgnoreCaseFilter@@@@QEAA@PEBG@Z; CSmsMessageFilter<StringListIgnoreCaseFilter>::CSmsMessageFilter<StringListIgnoreCaseFilter>(ushort const *)
0x180068588  nop
0x180068589  jmp     loc_180068627
0x18006858e  lea     rdx, aWapcontenttype; "WapContentType"
0x180068595  mov     rcx, rbx
0x180068598  call    cs:__imp__o__wcsicmp
0x18006859e  test    eax, eax
0x1800685a0  jnz     short loc_1800685C0
0x1800685a2  lea     ecx, [rax+50h]; Size
0x1800685a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800685aa  mov     [rbp+arg_8], rax
0x1800685ae  lea     rdx, aMessageContent; "/Message/ContentType"
0x1800685b5  mov     rcx, rax
0x1800685b8  call    ??0?$CSmsMessageFilter@VStringListIgnoreCaseFilter@@@@QEAA@PEBG@Z; CSmsMessageFilter<StringListIgnoreCaseFilter>::CSmsMessageFilter<StringListIgnoreCaseFilter>(ushort const *)
0x1800685bd  nop
0x1800685be  jmp     short loc_180068627
0x1800685c0  lea     rdx, aBroadcasttype; "BroadcastType"
0x1800685c7  mov     rcx, rbx
0x1800685ca  call    cs:__imp__o__wcsicmp
0x1800685d0  test    eax, eax
0x1800685d2  jnz     short loc_1800685F2
0x1800685d4  lea     ecx, [rax+50h]; Size
0x1800685d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800685dc  mov     [rbp+arg_8], rax
0x1800685e0  lea     rdx, aMessageBroadca; "/Message/BroadcastType"
0x1800685e7  mov     rcx, rax
0x1800685ea  call    ??0?$CSmsMessageFilter@VStringListIgnoreCaseFilter@@@@QEAA@PEBG@Z; CSmsMessageFilter<StringListIgnoreCaseFilter>::CSmsMessageFilter<StringListIgnoreCaseFilter>(ushort const *)
0x1800685ef  nop
0x1800685f0  jmp     short loc_180068627
0x1800685f2  mov     edi, 80070490h
0x1800685f7  lea     rdx, aBroadcastchann; "BroadcastChannel"
0x1800685fe  mov     rcx, rbx
0x180068601  call    cs:__imp__o__wcsicmp
0x180068607  test    eax, eax
0x180068609  jnz     short loc_18006862C
0x18006860b  lea     ecx, [rax+48h]; Size
0x18006860e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068613  mov     [rbp+arg_8], rax
0x180068617  lea     rdx, aMessageBroadca_0; "/Message/BroadcastChannel"
0x18006861e  mov     rcx, rax
0x180068621  call    ??0?$CSmsMessageFilter@VIntegerListIgnoreCaseFilter@@@@QEAA@PEBG@Z; CSmsMessageFilter<IntegerListIgnoreCaseFilter>::CSmsMessageFilter<IntegerListIgnoreCaseFilter>(ushort const *)
0x180068626  nop
0x180068627  mov     [rsi], rax
0x18006862a  xor     edi, edi
0x18006862c  mov     eax, edi
0x18006862e  add     rsp, 28h
0x180068632  pop     rdi
0x180068633  pop     rsi
0x180068634  pop     rbx
0x180068635  pop     rbp
0x180068636  retn
```
