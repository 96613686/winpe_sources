# _generateDMConfigRootNode(IXMLDOMDocument2 *,WWAN_PROFILE *)

- ea: `0x18000ec80`
- end: `0x18000f055`
- name: `?_generateDMConfigRootNode@@YAKPEAUIXMLDOMDocument2@@PEAUWWAN_PROFILE@@@Z`
- size: `981`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, OLECHAR *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009b30`

## callees

- `0x180001670`
- `0x1800092fc`
- `0x18000ec80`
- `0x18000f05c`
- `0x180011f90`
- `0x180012310`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000eda7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000eda7`

## string_xrefs

- `0x18000ecc7`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000efce`: `http://www.microsoft.com/networking/WWAN/profile/v7`
- `0x18000ecd1`: `ModemDMConfigProfile`

## pseudocode

```c
__int64 __fastcall _generateDMConfigRootNode(struct IXMLDOMDocument2 *a1, OLECHAR *a2)
{
  unsigned int v4; // ebx
  struct IXMLDOMNode *v6; // rbx
  unsigned int ContextNode; // ebp
  unsigned int v8; // eax
  signed int v9; // eax
  unsigned int v10; // edi
  struct IXMLDOMNode **v11; // [rsp+38h] [rbp-A0h]
  struct IXMLDOMNode **v12; // [rsp+38h] [rbp-A0h]
  struct IXMLDOMNode **v13; // [rsp+38h] [rbp-A0h]
  struct IXMLDOMNode **v14; // [rsp+38h] [rbp-A0h]
  struct IXMLDOMNode *v15; // [rsp+40h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-88h] BYREF

  v15 = 0;
  v4 = XcAddChildElement(
         a1,
         (struct IXMLDOMNode *)a1,
         (OLECHAR *)L"ModemDMConfigProfile",
         (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4",
         0,
         &v15);
  if ( v4 )
  {
    if ( v15 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
    return v4;
  }
  v6 = v15;
  ContextNode = XcAddChildElement(
                  a1,
                  v15,
                  (OLECHAR *)L"Name",
                  (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4",
                  a2,
                  0);
  if ( ContextNode )
  {
    if ( v6 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
    return ContextNode;
  }
  ContextNode = XcAddChildElement(
                  a1,
                  v6,
                  (OLECHAR *)L"SimIccID",
                  (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4",
                  a2 + 1556,
                  0);
  if ( ContextNode )
  {
    if ( v6 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
    return ContextNode;
  }
  if ( StringFromGUID2((const GUID *const)a2 + 294, sz, 40) )
  {
    ContextNode = XcAddChildElement(
                    a1,
                    v6,
                    (OLECHAR *)L"OemConnectionId",
                    (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4",
                    sz,
                    0);
    if ( ContextNode )
    {
      if ( v6 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
      return ContextNode;
    }
    v8 = *((_DWORD *)a2 + 1175);
    if ( v8 )
    {
      ContextNode = XcAddChildElementEnum(
                      a1,
                      v6,
                      (OLECHAR *)L"RoamApplicability",
                      (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4",
                      v8,
                      (const struct _XC_STRING_VALUE_MAPPING *)&_roamApplicabilityType,
                      6u,
                      v11);
      if ( ContextNode )
      {
        if ( v6 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
        return ContextNode;
      }
    }
    ContextNode = _generateContextNode(a1, v6, (struct WWAN_CONTEXT_INFO *)(a2 + 1600), 2u);
    if ( ContextNode )
    {
      if ( v6 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
      return ContextNode;
    }
    ContextNode = XcAddChildElementEnum(
                    a1,
                    v6,
                    (OLECHAR *)L"AdminEnable",
                    (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4",
                    *((_DWORD *)a2 + 1174) != 0,
                    (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                    4u,
                    v11);
    if ( ContextNode )
    {
      if ( v6 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
      return ContextNode;
    }
    ContextNode = XcAddChildElementEnum(
                    a1,
                    v6,
                    (OLECHAR *)L"AdminRoamControl",
                    (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4",
                    *((_DWORD *)a2 + 1172),
                    (const struct _XC_STRING_VALUE_MAPPING *)&_roamControl,
                    3u,
                    v12);
    if ( ContextNode )
    {
      if ( v6 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
      return ContextNode;
    }
    v9 = *((_DWORD *)a2 + 769);
    if ( v9 >= 4 )
      v9 = 3;
    ContextNode = XcAddChildElementEnum(
                    a1,
                    v6,
                    (OLECHAR *)L"ProfileCreationType",
                    (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4",
                    v9,
                    (const struct _XC_STRING_VALUE_MAPPING *)&_creationType,
                    4u,
                    v13);
    if ( ContextNode )
    {
      if ( v6 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
      return ContextNode;
    }
    if ( *((_DWORD *)a2 + 769) == 4 )
    {
      ContextNode = XcAddChildElementEnum(
                      a1,
                      v6,
                      (OLECHAR *)L"IsBasedOnModemProvisionedContext",
                      (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v7",
                      1u,
                      (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                      4u,
                      v14);
      if ( ContextNode )
      {
        if ( v6 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
        return ContextNode;
      }
    }
    v10 = generateodemDMProfilePurposesNode(a1);
    if ( v6 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
    return v10;
  }
  else
  {
    if ( v6 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
    return 1206;
  }
}

```

## disassembly

```asm
0x18000ec80  mov     [rsp+arg_10], rbx
0x18000ec85  push    rbp
0x18000ec86  push    rsi
0x18000ec87  push    rdi
0x18000ec88  push    r13
0x18000ec8a  push    r15
0x18000ec8c  sub     rsp, 0B0h
0x18000ec93  mov     rax, cs:__security_cookie
0x18000ec9a  xor     rax, rsp
0x18000ec9d  mov     [rsp+0D8h+var_38], rax
0x18000eca5  mov     rsi, rdx
0x18000eca8  mov     rdi, rcx
0x18000ecab  mov     [rsp+0D8h+var_98], 0
0x18000ecb4  lea     rax, [rsp+0D8h+var_98]
0x18000ecb9  mov     [rsp+0D8h+var_B0], rax; struct IXMLDOMNode **
0x18000ecbe  mov     [rsp+0D8h+var_B8], 0; OLECHAR *
0x18000ecc7  lea     r15, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000ecce  mov     r9, r15; OLECHAR *
0x18000ecd1  lea     r8, aModemdmconfigp; "ModemDMConfigProfile"
0x18000ecd8  mov     rdx, rcx; struct IXMLDOMNode *
0x18000ecdb  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000ece0  mov     ebx, eax
0x18000ece2  test    eax, eax
0x18000ece4  jz      short loc_18000ED04
0x18000ece6  mov     rcx, [rsp+0D8h+var_98]
0x18000eceb  test    rcx, rcx
0x18000ecee  jz      short loc_18000ECFD
0x18000ecf0  mov     rdx, [rcx]
0x18000ecf3  mov     rax, [rdx+10h]
0x18000ecf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecfc  nop
0x18000ecfd  mov     eax, ebx
0x18000ecff  jmp     loc_18000F02E
0x18000ed04  mov     [rsp+0D8h+var_B0], 0; struct IXMLDOMNode **
0x18000ed0d  mov     [rsp+0D8h+var_B8], rsi; OLECHAR *
0x18000ed12  mov     r9, r15; OLECHAR *
0x18000ed15  lea     r8, aName; "Name"
0x18000ed1c  mov     rbx, [rsp+0D8h+var_98]
0x18000ed21  mov     rdx, rbx; struct IXMLDOMNode *
0x18000ed24  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18000ed27  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000ed2c  mov     ebp, eax
0x18000ed2e  test    eax, eax
0x18000ed30  jz      short loc_18000ED4E
0x18000ed32  test    rbx, rbx
0x18000ed35  jz      short loc_18000ED47
0x18000ed37  mov     rdx, [rbx]
0x18000ed3a  mov     rcx, rbx
0x18000ed3d  mov     rax, [rdx+10h]
0x18000ed41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed46  nop
0x18000ed47  mov     eax, ebp
0x18000ed49  jmp     loc_18000F02E
0x18000ed4e  lea     rax, [rsi+0C28h]
0x18000ed55  mov     [rsp+0D8h+var_B0], 0; struct IXMLDOMNode **
0x18000ed5e  mov     [rsp+0D8h+var_B8], rax; OLECHAR *
0x18000ed63  mov     r9, r15; OLECHAR *
0x18000ed66  lea     r8, aSimiccid; "SimIccID"
0x18000ed6d  mov     rdx, rbx; struct IXMLDOMNode *
0x18000ed70  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18000ed73  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000ed78  mov     ebp, eax
0x18000ed7a  test    eax, eax
0x18000ed7c  jz      short loc_18000ED95
0x18000ed7e  test    rbx, rbx
0x18000ed81  jz      short loc_18000ED93
0x18000ed83  mov     rcx, [rbx]
0x18000ed86  mov     rax, [rcx+10h]
0x18000ed8a  mov     rcx, rbx
0x18000ed8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed92  nop
0x18000ed93  jmp     short loc_18000ED47
0x18000ed95  lea     rcx, [rsi+1260h]; rguid
0x18000ed9c  mov     r8d, 28h ; '('; cchMax
0x18000eda2  lea     rdx, [rsp+0D8h+sz]; lpsz
0x18000eda7  call    cs:__imp_StringFromGUID2
0x18000edad  test    eax, eax
0x18000edaf  jnz     short loc_18000EDD0
0x18000edb1  test    rbx, rbx
0x18000edb4  jz      short loc_18000EDC6
0x18000edb6  mov     rax, [rbx]
0x18000edb9  mov     rcx, rbx
0x18000edbc  mov     rax, [rax+10h]
0x18000edc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edc5  nop
0x18000edc6  mov     eax, 4B6h
0x18000edcb  jmp     loc_18000F02E
0x18000edd0  mov     [rsp+0D8h+var_B0], 0; struct IXMLDOMNode **
0x18000edd9  lea     rax, [rsp+0D8h+sz]
0x18000edde  mov     [rsp+0D8h+var_B8], rax; OLECHAR *
0x18000ede3  mov     r9, r15; OLECHAR *
0x18000ede6  lea     r8, aOemconnectioni; "OemConnectionId"
0x18000eded  mov     rdx, rbx; struct IXMLDOMNode *
0x18000edf0  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18000edf3  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000edf8  mov     ebp, eax
0x18000edfa  test    eax, eax
0x18000edfc  jz      short loc_18000EE18
0x18000edfe  test    rbx, rbx
0x18000ee01  jz      short loc_18000EE13
0x18000ee03  mov     rcx, [rbx]
0x18000ee06  mov     rax, [rcx+10h]
0x18000ee0a  mov     rcx, rbx
0x18000ee0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee12  nop
0x18000ee13  jmp     loc_18000ED47
0x18000ee18  mov     eax, [rsi+125Ch]
0x18000ee1e  test    eax, eax
0x18000ee20  jz      short loc_18000EE6F
0x18000ee22  mov     [rsp+0D8h+var_A8], 6; unsigned int
0x18000ee2a  lea     rcx, ?_roamApplicabilityType@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _roamApplicabilityType
0x18000ee31  mov     [rsp+0D8h+var_B0], rcx; struct _XC_STRING_VALUE_MAPPING *
0x18000ee36  mov     dword ptr [rsp+0D8h+var_B8], eax; unsigned int
0x18000ee3a  mov     r9, r15; OLECHAR *
0x18000ee3d  lea     r8, aRoamapplicabil; "RoamApplicability"
0x18000ee44  mov     rdx, rbx; struct IXMLDOMNode *
0x18000ee47  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18000ee4a  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18000ee4f  mov     ebp, eax
0x18000ee51  test    eax, eax
0x18000ee53  jz      short loc_18000EE6F
0x18000ee55  test    rbx, rbx
0x18000ee58  jz      short loc_18000EE6A
0x18000ee5a  mov     rcx, [rbx]
0x18000ee5d  mov     rax, [rcx+10h]
0x18000ee61  mov     rcx, rbx
0x18000ee64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee69  nop
0x18000ee6a  jmp     loc_18000ED47
0x18000ee6f  lea     r8, [rsi+0C80h]; struct WWAN_CONTEXT_INFO *
0x18000ee76  mov     r9d, 2; unsigned int
0x18000ee7c  mov     rdx, rbx; struct IXMLDOMNode *
0x18000ee7f  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18000ee82  call    ?_generateContextNode@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAUWWAN_CONTEXT_INFO@@K@Z; _generateContextNode(IXMLDOMDocument2 *,IXMLDOMNode *,WWAN_CONTEXT_INFO *,ulong)
0x18000ee87  mov     ebp, eax
0x18000ee89  test    eax, eax
0x18000ee8b  jz      short loc_18000EEA7
0x18000ee8d  test    rbx, rbx
0x18000ee90  jz      short loc_18000EEA2
0x18000ee92  mov     rcx, [rbx]
0x18000ee95  mov     rax, [rcx+10h]
0x18000ee99  mov     rcx, rbx
0x18000ee9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eea1  nop
0x18000eea2  jmp     loc_18000ED47
0x18000eea7  xor     eax, eax
0x18000eea9  cmp     [rsi+1258h], eax
0x18000eeaf  setnz   al
0x18000eeb2  mov     [rsp+0D8h+var_A8], 4; unsigned int
0x18000eeba  lea     r13, off_180015490; "true"
0x18000eec1  mov     [rsp+0D8h+var_B0], r13; struct _XC_STRING_VALUE_MAPPING *
0x18000eec6  mov     dword ptr [rsp+0D8h+var_B8], eax; unsigned int
0x18000eeca  mov     r9, r15; OLECHAR *
0x18000eecd  lea     r8, aAdminenable; "AdminEnable"
0x18000eed4  mov     rdx, rbx; struct IXMLDOMNode *
0x18000eed7  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18000eeda  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18000eedf  mov     ebp, eax
0x18000eee1  test    eax, eax
0x18000eee3  jz      short loc_18000EEFF
0x18000eee5  test    rbx, rbx
0x18000eee8  jz      short loc_18000EEFA
0x18000eeea  mov     rcx, [rbx]
0x18000eeed  mov     rax, [rcx+10h]
0x18000eef1  mov     rcx, rbx
0x18000eef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eef9  nop
0x18000eefa  jmp     loc_18000ED47
0x18000eeff  mov     [rsp+0D8h+var_A8], 3; unsigned int
0x18000ef07  lea     rax, ?_roamControl@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _roamControl
0x18000ef0e  mov     [rsp+0D8h+var_B0], rax; struct _XC_STRING_VALUE_MAPPING *
0x18000ef13  mov     eax, [rsi+1250h]
0x18000ef19  mov     dword ptr [rsp+0D8h+var_B8], eax; unsigned int
0x18000ef1d  mov     r9, r15; OLECHAR *
0x18000ef20  lea     r8, aAdminroamcontr; "AdminRoamControl"
0x18000ef27  mov     rdx, rbx; struct IXMLDOMNode *
0x18000ef2a  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18000ef2d  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18000ef32  mov     ebp, eax
0x18000ef34  test    eax, eax
0x18000ef36  jz      short loc_18000EF52
0x18000ef38  test    rbx, rbx
0x18000ef3b  jz      short loc_18000EF4D
0x18000ef3d  mov     rcx, [rbx]
0x18000ef40  mov     rax, [rcx+10h]
0x18000ef44  mov     rcx, rbx
0x18000ef47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef4c  nop
0x18000ef4d  jmp     loc_18000ED47
0x18000ef52  mov     eax, [rsi+0C04h]
0x18000ef58  cmp     eax, 4
0x18000ef5b  mov     ecx, 3
0x18000ef60  cmovge  eax, ecx
0x18000ef63  mov     [rsp+0D8h+var_A8], 4; unsigned int
0x18000ef6b  lea     rcx, ?_creationType@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _creationType
0x18000ef72  mov     [rsp+0D8h+var_B0], rcx; struct _XC_STRING_VALUE_MAPPING *
0x18000ef77  mov     dword ptr [rsp+0D8h+var_B8], eax; unsigned int
0x18000ef7b  mov     r9, r15; OLECHAR *
0x18000ef7e  lea     r8, aProfilecreatio; "ProfileCreationType"
0x18000ef85  mov     rdx, rbx; struct IXMLDOMNode *
0x18000ef88  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18000ef8b  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18000ef90  mov     ebp, eax
0x18000ef92  test    eax, eax
0x18000ef94  jz      short loc_18000EFB0
0x18000ef96  test    rbx, rbx
0x18000ef99  jz      short loc_18000EFAB
0x18000ef9b  mov     rcx, [rbx]
0x18000ef9e  mov     rax, [rcx+10h]
0x18000efa2  mov     rcx, rbx
0x18000efa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efaa  nop
0x18000efab  jmp     loc_18000ED47
0x18000efb0  cmp     dword ptr [rsi+0C04h], 4
0x18000efb7  jnz     short loc_18000F007
0x18000efb9  mov     [rsp+0D8h+var_A8], 4; unsigned int
0x18000efc1  mov     [rsp+0D8h+var_B0], r13; struct _XC_STRING_VALUE_MAPPING *
0x18000efc6  mov     dword ptr [rsp+0D8h+var_B8], 1; unsigned int
0x18000efce  lea     r9, aHttpWwwMicroso_4; "http://www.microsoft.com/networking/WWA"...
0x18000efd5  lea     r8, aIsbasedonmodem; "IsBasedOnModemProvisionedContext"
0x18000efdc  mov     rdx, rbx; struct IXMLDOMNode *
0x18000efdf  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18000efe2  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18000efe7  mov     ebp, eax
0x18000efe9  test    eax, eax
0x18000efeb  jz      short loc_18000F007
0x18000efed  test    rbx, rbx
0x18000eff0  jz      short loc_18000F002
0x18000eff2  mov     rcx, [rbx]
0x18000eff5  mov     rax, [rcx+10h]
0x18000eff9  mov     rcx, rbx
0x18000effc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f001  nop
0x18000f002  jmp     loc_18000ED47
0x18000f007  mov     r8, rsi
0x18000f00a  mov     rdx, rbx
0x18000f00d  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18000f010  call    _generateodemDMProfilePurposesNode
0x18000f015  mov     edi, eax
0x18000f017  test    rbx, rbx
0x18000f01a  jz      short loc_18000F02C
0x18000f01c  mov     rcx, [rbx]
0x18000f01f  mov     rax, [rcx+10h]
0x18000f023  mov     rcx, rbx
0x18000f026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f02b  nop
0x18000f02c  mov     eax, edi
0x18000f02e  mov     rcx, [rsp+0D8h+var_38]
0x18000f036  xor     rcx, rsp; StackCookie
0x18000f039  call    __security_check_cookie
0x18000f03e  mov     rbx, [rsp+0D8h+arg_10]
0x18000f046  add     rsp, 0B0h
0x18000f04d  pop     r15
0x18000f04f  pop     r13
0x18000f051  pop     rdi
0x18000f052  pop     rsi
0x18000f053  pop     rbp
0x18000f054  retn
```
