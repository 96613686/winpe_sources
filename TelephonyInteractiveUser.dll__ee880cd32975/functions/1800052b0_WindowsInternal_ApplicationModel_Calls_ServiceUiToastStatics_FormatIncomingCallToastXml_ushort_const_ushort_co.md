# WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::_FormatIncomingCallToastXml(ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x1800052b0`
- end: `0x1800053dd`
- name: `?_FormatIncomingCallToastXml@ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJPEBG0PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `301`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800053f0`

## callees

- `0x180001dc0`
- `0x180004a0c`
- `0x180004b4c`
- `0x180004d8c`
- `0x1800052b0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180005321`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180005377`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800053ad`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800053bc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180005321`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180005377`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800053ad`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800053bc`
- `dmxmlhelputils!XMLHEscapeString` at `0x1800052fc`
- `dmxmlhelputils!XMLHEscapeString` at `0x180005350`
- `dmxmlhelputils!XMLHEscapeString` at `0x1800052fc`
- `dmxmlhelputils!XMLHEscapeString` at `0x180005350`

## string_xrefs

- `0x180005383`: `<toast scenario="systemDialog"><visual><binding template="ToastGeneric"><text id="1">%s</text><text id="2">%s</text></binding></visual></toast>`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::_FormatIncomingCallToastXml(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4)
{
  _WORD *v6; // rdx
  unsigned __int16 **v8; // rax
  int v9; // eax
  __int64 v10; // r8
  int v11; // ebx
  unsigned __int16 **v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  HLOCAL hMem; // [rsp+30h] [rbp-20h] BYREF
  HLOCAL v17; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-Ch] BYREF

  v6 = *(_WORD **)a4;
  *(_QWORD *)(a4 + 8) = *(_QWORD *)a4;
  *v6 = 0;
  hMem = 0;
  v18 = 0;
  v8 = (unsigned __int16 **)tlx::replace<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>(&hMem);
  v9 = XMLHEscapeString(a2, v8, &v18);
  v11 = v9;
  if ( v9 < 0 )
  {
    Log_HREvent((unsigned int)v9, 1, v10, 57);
LABEL_3:
    if ( hMem )
      LocalFree(hMem);
    return (unsigned int)v11;
  }
  v17 = 0;
  v19 = 0;
  v13 = (unsigned __int16 **)tlx::replace<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>(&v17);
  v11 = XMLHEscapeString(a3, v13, &v19);
  if ( v11 < 0 )
  {
    v15 = 62;
    goto LABEL_8;
  }
  v11 = tlx::append_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
          a4,
          L"<toast scenario=\"systemDialog\"><visual><binding template=\"ToastGeneric\"><text id=\"1\">%s</text><text id=\""
           "2\">%s</text></binding></visual></toast>",
          hMem,
          v17);
  if ( v11 < 0 )
  {
    v15 = 64;
LABEL_8:
    Log_HREvent((unsigned int)v11, 1, v14, v15);
    if ( v17 )
      LocalFree(v17);
    goto LABEL_3;
  }
  if ( v17 )
    LocalFree(v17);
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x1800052b0  mov     [rsp-18h+arg_0], rbx
0x1800052b5  push    rbp
0x1800052b6  push    rsi
0x1800052b7  push    rdi
0x1800052b8  mov     rbp, rsp
0x1800052bb  sub     rsp, 50h
0x1800052bf  mov     rax, cs:__security_cookie
0x1800052c6  xor     rax, rsp
0x1800052c9  mov     [rbp+var_8], rax
0x1800052cd  xor     eax, eax
0x1800052cf  lea     rcx, [rbp+hMem]
0x1800052d3  mov     rbx, rdx
0x1800052d6  mov     rdi, r9
0x1800052d9  mov     rdx, [r9]
0x1800052dc  mov     rsi, r8
0x1800052df  mov     [r9+8], rdx
0x1800052e3  mov     [rdx], ax
0x1800052e6  mov     [rbp+hMem], rax
0x1800052ea  mov     [rbp+var_10], eax
0x1800052ed  call    ??$replace@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<ushort *,void * (*)(void *),&LocalFree(void *),0> &)
0x1800052f2  mov     rdx, rax
0x1800052f5  lea     r8, [rbp+var_10]
0x1800052f9  mov     rcx, rbx
0x1800052fc  call    cs:__imp_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z; XMLHEscapeString(ushort const *,ushort * *,ulong *)
0x180005302  mov     ebx, eax
0x180005304  test    eax, eax
0x180005306  jns     short loc_18000532E
0x180005308  mov     edx, 1
0x18000530d  mov     ecx, eax
0x18000530f  lea     r9d, [rdx+38h]
0x180005313  call    Log_HREvent
0x180005318  mov     rcx, [rbp+hMem]; hMem
0x18000531c  test    rcx, rcx
0x18000531f  jz      short loc_180005327
0x180005321  call    cs:__imp_LocalFree
0x180005327  mov     eax, ebx
0x180005329  jmp     loc_1800053C4
0x18000532e  lea     rcx, [rbp+var_18]
0x180005332  mov     [rbp+var_18], 0
0x18000533a  mov     [rbp+var_C], 0
0x180005341  call    ??$replace@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<ushort *,void * (*)(void *),&LocalFree(void *),0> &)
0x180005346  mov     rdx, rax
0x180005349  lea     r8, [rbp+var_C]
0x18000534d  mov     rcx, rsi
0x180005350  call    cs:__imp_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z; XMLHEscapeString(ushort const *,ushort * *,ulong *)
0x180005356  mov     ebx, eax
0x180005358  test    eax, eax
0x18000535a  jns     short loc_18000537F
0x18000535c  mov     r9d, 3Eh ; '>'
0x180005362  mov     edx, 1
0x180005367  mov     ecx, ebx
0x180005369  call    Log_HREvent
0x18000536e  mov     rcx, [rbp+var_18]; hMem
0x180005372  test    rcx, rcx
0x180005375  jz      short loc_180005318
0x180005377  call    cs:__imp_LocalFree
0x18000537d  jmp     short loc_180005318
0x18000537f  mov     r9, [rbp+var_18]
0x180005383  lea     rdx, aToastScenarioS; "<toast scenario=\"systemDialog\"><visua"...
0x18000538a  mov     r8, [rbp+hMem]
0x18000538e  mov     rcx, rdi
0x180005391  call    ??$append_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::append_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180005396  mov     ebx, eax
0x180005398  test    eax, eax
0x18000539a  jns     short loc_1800053A4
0x18000539c  mov     r9d, 40h ; '@'
0x1800053a2  jmp     short loc_180005362
0x1800053a4  mov     rcx, [rbp+var_18]; hMem
0x1800053a8  test    rcx, rcx
0x1800053ab  jz      short loc_1800053B3
0x1800053ad  call    cs:__imp_LocalFree
0x1800053b3  mov     rcx, [rbp+hMem]; hMem
0x1800053b7  test    rcx, rcx
0x1800053ba  jz      short loc_1800053C2
0x1800053bc  call    cs:__imp_LocalFree
0x1800053c2  xor     eax, eax
0x1800053c4  mov     rcx, [rbp+var_8]
0x1800053c8  xor     rcx, rsp; StackCookie
0x1800053cb  call    __security_check_cookie
0x1800053d0  mov     rbx, [rsp+50h+arg_0]
0x1800053d5  add     rsp, 50h
0x1800053d9  pop     rdi
0x1800053da  pop     rsi
0x1800053db  pop     rbp
0x1800053dc  retn
```
