# WaasMedic::CRegKeyInformationFromXML::GatherRegKeyInfoFromXML(ushort const *)

- ea: `0x180034290`
- end: `0x1800344bb`
- name: `?GatherRegKeyInfoFromXML@CRegKeyInformationFromXML@WaasMedic@@QEAAJPEBG@Z`
- size: `555`
- prototype: `__int64 __fastcall(WaasMedic::CRegKeyInformationFromXML *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004bc00`

## callees

- `0x180009a54`
- `0x18002543c`
- `0x180034290`
- `0x180035158`
- `0x180035810`
- `0x180036558`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034396`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003440d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034396`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003440d`

## string_xrefs

- `0x18003447d`: `XmlNodeType_Element without local name in %s`
- `0x180034402`: `securityDescriptorDefinition`
- `0x18003438b`: `registryKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::CRegKeyInformationFromXML::GatherRegKeyInfoFromXML(
        char **this,
        const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  int v6; // eax
  int v7; // esi
  __int64 v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  int v12; // eax
  __int64 v13; // [rsp+20h] [rbp-10h] BYREF
  int v14; // [rsp+28h] [rbp-8h]
  char v15; // [rsp+2Ch] [rbp-4h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  __int64 v17; // [rsp+68h] [rbp+38h] BYREF
  __int64 v18; // [rsp+70h] [rbp+40h] BYREF

  v13 = 0;
  v14 = -1;
  v15 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x484,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)0x80004003LL,
      v13);
    return v4;
  }
  v6 = WaasMedic::XmlReader::Initialize((WaasMedic::XmlReader *)&v13, a2);
  v4 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x487,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)(unsigned int)v6,
      v13);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    return v4;
  }
  v7 = 0;
  v8 = v13;
  while ( 1 )
  {
    LODWORD(v17) = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 48LL))(v8, &v17);
    v10 = v9;
    if ( v9 >= 0 )
    {
      if ( v9 == 1 )
        v7 = 0;
      else
        v7 = v17;
    }
    if ( v9 )
      break;
    v17 = 0;
    if ( v7 == 1 )
    {
      if ( (*(int (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v8 + 112LL))(v8, &v17, 0) < 0 )
      {
        LogLevelW(5u, L"XmlNodeType_Element without local name in %s", a2);
      }
      else if ( (unsigned int)_o__wcsicmp(v17, L"registryKey") )
      {
        if ( !(unsigned int)_o__wcsicmp(v17, L"securityDescriptorDefinition") )
        {
          v18 = v8;
          if ( v8 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
          v12 = WaasMedic::CRegKeyInformationFromXML::ParseSecurityDescriptorDefinitions(this, &v18);
          v10 = v12;
          if ( v12 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x499,
              (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
              (const char *)(unsigned int)v12,
              v13);
            if ( v8 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            return v10;
          }
        }
      }
      else
      {
        v18 = v8;
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
        v11 = WaasMedic::CRegKeyInformationFromXML::ParseRegistryKeyDataElement(this, &v18);
        v10 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x495,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
            (const char *)(unsigned int)v11,
            v13);
          if ( v8 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          return v10;
        }
      }
    }
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return v10;
}

```

## disassembly

```asm
0x180034290  mov     [rsp-28h+arg_0], rbx
0x180034295  push    rbp
0x180034296  push    rsi
0x180034297  push    rdi
0x180034298  push    r14
0x18003429a  push    r15
0x18003429c  mov     rbp, rsp
0x18003429f  sub     rsp, 30h
0x1800342a3  mov     r14, rdx
0x1800342a6  mov     r15, rcx
0x1800342a9  mov     [rbp+var_10], 0
0x1800342b1  mov     [rbp+var_8], 0FFFFFFFFh
0x1800342b8  mov     [rbp+var_4], 0
0x1800342bc  test    rdx, rdx
0x1800342bf  jnz     short loc_1800342E6
0x1800342c1  mov     rcx, [rbp+28h]; this
0x1800342c5  mov     ebx, 80004003h
0x1800342ca  mov     r9d, ebx; char *
0x1800342cd  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800342d4  mov     edx, 484h; void *
0x1800342d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800342de  nop
0x1800342df  mov     eax, ebx
0x1800342e1  jmp     loc_1800344AA
0x1800342e6  lea     rcx, [rbp+var_10]; this
0x1800342ea  call    ?Initialize@XmlReader@WaasMedic@@QEAAJPEBG@Z; WaasMedic::XmlReader::Initialize(ushort const *)
0x1800342ef  mov     ebx, eax
0x1800342f1  test    eax, eax
0x1800342f3  jns     short loc_180034326
0x1800342f5  mov     rcx, [rbp+28h]; this
0x1800342f9  mov     r9d, eax; char *
0x1800342fc  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180034303  mov     edx, 487h; void *
0x180034308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003430d  nop
0x18003430e  mov     rcx, [rbp+var_10]
0x180034312  test    rcx, rcx
0x180034315  jz      short loc_180034324
0x180034317  mov     rax, [rcx]
0x18003431a  mov     rax, [rax+10h]
0x18003431e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034323  nop
0x180034324  jmp     short loc_1800342DF
0x180034326  xor     esi, esi
0x180034328  mov     rbx, [rbp+var_10]
0x18003432c  mov     dword ptr [rbp+arg_8], 0
0x180034333  mov     rax, [rbx]
0x180034336  lea     rdx, [rbp+arg_8]
0x18003433a  mov     rcx, rbx
0x18003433d  mov     rax, [rax+30h]
0x180034341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034346  mov     edi, eax
0x180034348  test    eax, eax
0x18003434a  js      short loc_180034358
0x18003434c  cmp     eax, 1
0x18003434f  jnz     short loc_180034355
0x180034351  xor     esi, esi
0x180034353  jmp     short loc_180034358
0x180034355  mov     esi, dword ptr [rbp+arg_8]
0x180034358  test    edi, edi
0x18003435a  jnz     loc_180034493
0x180034360  mov     [rbp+arg_8], 0
0x180034368  cmp     esi, 1
0x18003436b  jnz     short loc_18003432C
0x18003436d  mov     rax, [rbx]
0x180034370  xor     r8d, r8d
0x180034373  lea     rdx, [rbp+arg_8]
0x180034377  mov     rcx, rbx
0x18003437a  mov     rax, [rax+70h]
0x18003437e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034383  test    eax, eax
0x180034385  js      loc_18003447A
0x18003438b  lea     rdx, aRegistrykey; "registryKey"
0x180034392  mov     rcx, [rbp+arg_8]
0x180034396  call    cs:__imp__o__wcsicmp
0x18003439c  test    eax, eax
0x18003439e  jnz     short loc_180034402
0x1800343a0  mov     [rbp+arg_10], rbx
0x1800343a4  test    rbx, rbx
0x1800343a7  jz      short loc_1800343B9
0x1800343a9  mov     rax, [rbx]
0x1800343ac  mov     rcx, rbx
0x1800343af  mov     rax, [rax+8]
0x1800343b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343b8  nop
0x1800343b9  lea     rdx, [rbp+arg_10]
0x1800343bd  mov     rcx, r15
0x1800343c0  call    ?ParseRegistryKeyDataElement@CRegKeyInformationFromXML@WaasMedic@@QEAAJV?$ComPtr@UIXmlReader@@@WRL@Microsoft@@@Z; WaasMedic::CRegKeyInformationFromXML::ParseRegistryKeyDataElement(Microsoft::WRL::ComPtr<IXmlReader>)
0x1800343c5  mov     edi, eax
0x1800343c7  test    eax, eax
0x1800343c9  jns     loc_18003432C
0x1800343cf  mov     rcx, [rbp+28h]; this
0x1800343d3  mov     r9d, eax; char *
0x1800343d6  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800343dd  mov     edx, 495h; void *
0x1800343e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800343e7  nop
0x1800343e8  test    rbx, rbx
0x1800343eb  jz      short loc_1800343FD
0x1800343ed  mov     rax, [rbx]
0x1800343f0  mov     rcx, rbx
0x1800343f3  mov     rax, [rax+10h]
0x1800343f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343fc  nop
0x1800343fd  jmp     loc_1800344A8
0x180034402  lea     rdx, aSecuritydescri; "securityDescriptorDefinition"
0x180034409  mov     rcx, [rbp+arg_8]
0x18003440d  call    cs:__imp__o__wcsicmp
0x180034413  test    eax, eax
0x180034415  jnz     loc_18003432C
0x18003441b  mov     [rbp+arg_10], rbx
0x18003441f  test    rbx, rbx
0x180034422  jz      short loc_180034434
0x180034424  mov     rax, [rbx]
0x180034427  mov     rcx, rbx
0x18003442a  mov     rax, [rax+8]
0x18003442e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034433  nop
0x180034434  lea     rdx, [rbp+arg_10]
0x180034438  mov     rcx, r15
0x18003443b  call    ?ParseSecurityDescriptorDefinitions@CRegKeyInformationFromXML@WaasMedic@@QEAAJV?$ComPtr@UIXmlReader@@@WRL@Microsoft@@@Z; WaasMedic::CRegKeyInformationFromXML::ParseSecurityDescriptorDefinitions(Microsoft::WRL::ComPtr<IXmlReader>)
0x180034440  mov     edi, eax
0x180034442  test    eax, eax
0x180034444  jns     loc_18003432C
0x18003444a  mov     rcx, [rbp+28h]; this
0x18003444e  mov     r9d, eax; char *
0x180034451  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180034458  mov     edx, 499h; void *
0x18003445d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034462  nop
0x180034463  test    rbx, rbx
0x180034466  jz      short loc_180034478
0x180034468  mov     rax, [rbx]
0x18003446b  mov     rcx, rbx
0x18003446e  mov     rax, [rax+10h]
0x180034472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034477  nop
0x180034478  jmp     short loc_1800344A8
0x18003447a  mov     r8, r14
0x18003447d  lea     rdx, aXmlnodetypeEle; "XmlNodeType_Element without local name "...
0x180034484  mov     ecx, 5; unsigned __int8
0x180034489  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003448e  jmp     loc_18003432C
0x180034493  test    rbx, rbx
0x180034496  jz      short loc_1800344A8
0x180034498  mov     rax, [rbx]
0x18003449b  mov     rcx, rbx
0x18003449e  mov     rax, [rax+10h]
0x1800344a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344a7  nop
0x1800344a8  mov     eax, edi
0x1800344aa  mov     rbx, [rsp+30h+arg_0]
0x1800344af  add     rsp, 30h
0x1800344b3  pop     r15
0x1800344b5  pop     r14
0x1800344b7  pop     rdi
0x1800344b8  pop     rsi
0x1800344b9  pop     rbp
0x1800344ba  retn
```
