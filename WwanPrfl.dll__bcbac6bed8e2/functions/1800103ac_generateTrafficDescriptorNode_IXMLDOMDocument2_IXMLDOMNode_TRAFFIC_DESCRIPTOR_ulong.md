# _generateTrafficDescriptorNode(IXMLDOMDocument2 *,IXMLDOMNode *,_TRAFFIC_DESCRIPTOR *,ulong)

- ea: `0x1800103ac`
- end: `0x180010814`
- name: `?_generateTrafficDescriptorNode@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAU_TRAFFIC_DESCRIPTOR@@K@Z`
- size: `1128`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct _TRAFFIC_DESCRIPTOR *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a298`

## callees

- `0x180001670`
- `0x18000f73c`
- `0x18000f854`
- `0x1800103ac`
- `0x180011f90`
- `0x180012310`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800104dd`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800104dd`

## string_xrefs

- `0x1800103e7`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x1800103f9`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18001045e`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180010510`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18001057d`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x1800105e9`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180010658`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x1800106cf`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x1800103e0`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180010468`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18001051a`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180010587`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x1800105f3`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180010662`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x1800106d9`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18001041a`: `TrafficDescriptor`
- `0x1800106fa`: `IPDescriptor`

## pseudocode

```c
__int64 __fastcall _generateTrafficDescriptorNode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        struct _TRAFFIC_DESCRIPTOR *a3,
        unsigned int a4)
{
  OLECHAR *v7; // rdi
  OLECHAR *v8; // r9
  unsigned int ConnectionCapabilitiesNode; // esi
  struct IXMLDOMNode *v10; // rbx
  OLECHAR *v11; // r9
  OLECHAR *v13; // r9
  OLECHAR *v14; // r9
  OLECHAR *v15; // r9
  OLECHAR *v16; // r9
  unsigned int v17; // edi
  struct IXMLDOMNode *v18; // rdi
  int v19; // r8d
  struct IXMLDOMNode **v20; // [rsp+38h] [rbp-B0h]
  struct IXMLDOMNode *v21; // [rsp+40h] [rbp-A8h] BYREF
  struct IXMLDOMNode *v22; // [rsp+48h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-98h] BYREF

  v21 = 0;
  v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  if ( a4 < 3 )
  {
    v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
    if ( a4 != 2 )
      v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
  }
  else
  {
    v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  }
  ConnectionCapabilitiesNode = XcAddChildElement(a1, a2, (OLECHAR *)L"TrafficDescriptor", v8, 0, &v21);
  if ( ConnectionCapabilitiesNode )
  {
    if ( v21 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
    return ConnectionCapabilitiesNode;
  }
  v10 = v21;
  if ( *((_DWORD *)a3 + 1) == 1 )
  {
    if ( a4 < 3 )
    {
      v11 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( a4 != 2 )
        v11 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v11 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    ConnectionCapabilitiesNode = XcAddChildElementEnum(
                                   a1,
                                   v21,
                                   (OLECHAR *)L"MatchAllRule",
                                   v11,
                                   1u,
                                   (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                                   4u,
                                   v20);
    if ( ConnectionCapabilitiesNode )
    {
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      return ConnectionCapabilitiesNode;
    }
  }
  if ( (*(_DWORD *)a3 & 0x8000) != 0 )
  {
    if ( !StringFromGUID2((const GUID *const)((char *)a3 + 8), sz, 40) )
    {
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      return 1206;
    }
    if ( a4 < 3 )
    {
      v13 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( a4 != 2 )
        v13 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v13 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    ConnectionCapabilitiesNode = XcAddChildElement(a1, v10, (OLECHAR *)L"OSId", v13, sz, 0);
    if ( ConnectionCapabilitiesNode )
    {
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      return ConnectionCapabilitiesNode;
    }
  }
  if ( (*(_DWORD *)a3 & 0x800) != 0 )
  {
    if ( a4 < 3 )
    {
      v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( a4 != 2 )
        v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    ConnectionCapabilitiesNode = XcAddChildElement(a1, v10, (OLECHAR *)L"OSAppId", v14, (OLECHAR *)a3 + 12, 0);
    if ( ConnectionCapabilitiesNode )
    {
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      return ConnectionCapabilitiesNode;
    }
  }
  if ( (*(_DWORD *)a3 & 0x1000) != 0 )
  {
    if ( a4 < 3 )
    {
      v15 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( a4 != 2 )
        v15 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v15 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    ConnectionCapabilitiesNode = XcAddChildElement(a1, v10, (OLECHAR *)L"DNN", v15, (OLECHAR *)a3 + 142, 0);
    if ( ConnectionCapabilitiesNode )
    {
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      return ConnectionCapabilitiesNode;
    }
  }
  if ( (*(_DWORD *)a3 & 0x2000) != 0 )
  {
    if ( a4 < 3 )
    {
      v16 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( a4 != 2 )
        v16 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v16 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    ConnectionCapabilitiesNode = XcAddChildElement(a1, v10, (OLECHAR *)L"DestinationFQDN", v16, (OLECHAR *)a3 + 243, 0);
    if ( ConnectionCapabilitiesNode )
    {
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      return ConnectionCapabilitiesNode;
    }
  }
  if ( (*(_DWORD *)a3 & 0x4000) == 0 )
  {
LABEL_76:
    v19 = *((_DWORD *)a3 + 70);
    if ( v19 && (ConnectionCapabilitiesNode = _generateConnectionCapabilitiesNode(a1, v10, v19, a4)) != 0 )
    {
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
    }
    else if ( v10 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
    }
    return ConnectionCapabilitiesNode;
  }
  v22 = 0;
  if ( a4 < 3 )
  {
    v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
    if ( a4 != 2 )
      v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
  }
  v17 = XcAddChildElement(a1, v10, (OLECHAR *)L"IPDescriptor", v7, 0, &v22);
  if ( !v17 )
  {
    v18 = v22;
    ConnectionCapabilitiesNode = _generateIPDescriptorNode(
                                   a1,
                                   v22,
                                   (struct _TRAFFIC_DESCRIPTOR *)((char *)a3 + 1008),
                                   a4);
    if ( ConnectionCapabilitiesNode )
    {
      if ( v18 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v18->lpVtbl->Release)(v18);
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      return ConnectionCapabilitiesNode;
    }
    if ( v18 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v18->lpVtbl->Release)(v18);
    goto LABEL_76;
  }
  if ( v22 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v22->lpVtbl->Release)(v22);
  if ( v10 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
  return v17;
}

```

## disassembly

```asm
0x1800103ac  push    rbx
0x1800103ae  push    rbp
0x1800103af  push    rsi
0x1800103b0  push    rdi
0x1800103b1  push    r14
0x1800103b3  push    r15
0x1800103b5  sub     rsp, 0B8h
0x1800103bc  mov     rax, cs:__security_cookie
0x1800103c3  xor     rax, rsp
0x1800103c6  mov     [rsp+0E8h+var_48], rax
0x1800103ce  mov     ebp, r9d
0x1800103d1  mov     r14, r8
0x1800103d4  mov     r15, rcx
0x1800103d7  mov     [rsp+0E8h+var_A8], 0
0x1800103e0  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x1800103e7  lea     rdi, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x1800103ee  cmp     r9d, 3
0x1800103f2  jb      short loc_1800103F9
0x1800103f4  mov     r9, rdi
0x1800103f7  jmp     short loc_180010407
0x1800103f9  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180010400  cmp     ebp, 2
0x180010403  cmovnz  r9, rax; OLECHAR *
0x180010407  lea     rax, [rsp+0E8h+var_A8]
0x18001040c  mov     [rsp+0E8h+var_C0], rax; struct IXMLDOMNode **
0x180010411  mov     [rsp+0E8h+var_C8], 0; OLECHAR *
0x18001041a  lea     r8, aTrafficdescrip; "TrafficDescriptor"
0x180010421  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180010426  mov     esi, eax
0x180010428  test    eax, eax
0x18001042a  jz      short loc_180010448
0x18001042c  mov     rcx, [rsp+0E8h+var_A8]
0x180010431  test    rcx, rcx
0x180010434  jz      short loc_180010443
0x180010436  mov     rdx, [rcx]
0x180010439  mov     rax, [rdx+10h]
0x18001043d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010442  nop
0x180010443  jmp     loc_1800107F2
0x180010448  mov     rbx, [rsp+0E8h+var_A8]
0x18001044d  cmp     dword ptr [r14+4], 1
0x180010452  jnz     short loc_1800104C1
0x180010454  cmp     ebp, 3
0x180010457  jb      short loc_18001045E
0x180010459  mov     r9, rdi
0x18001045c  jmp     short loc_180010473
0x18001045e  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180010465  cmp     ebp, 2
0x180010468  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18001046f  cmovnz  r9, rax; OLECHAR *
0x180010473  mov     [rsp+0E8h+var_B8], 4; unsigned int
0x18001047b  lea     rax, off_180015490; "true"
0x180010482  mov     [rsp+0E8h+var_C0], rax; struct _XC_STRING_VALUE_MAPPING *
0x180010487  mov     dword ptr [rsp+0E8h+var_C8], 1; unsigned int
0x18001048f  lea     r8, aMatchallrule; "MatchAllRule"
0x180010496  mov     rdx, rbx; struct IXMLDOMNode *
0x180010499  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18001049c  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x1800104a1  mov     esi, eax
0x1800104a3  test    eax, eax
0x1800104a5  jz      short loc_1800104C1
0x1800104a7  test    rbx, rbx
0x1800104aa  jz      short loc_1800104BC
0x1800104ac  mov     rax, [rbx]
0x1800104af  mov     rcx, rbx
0x1800104b2  mov     rax, [rax+10h]
0x1800104b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104bb  nop
0x1800104bc  jmp     loc_1800107F2
0x1800104c1  test    dword ptr [r14], 8000h
0x1800104c8  jz      loc_18001056A
0x1800104ce  lea     rcx, [r14+8]; rguid
0x1800104d2  mov     r8d, 28h ; '('; cchMax
0x1800104d8  lea     rdx, [rsp+0E8h+sz]; lpsz
0x1800104dd  call    cs:__imp_StringFromGUID2
0x1800104e3  test    eax, eax
0x1800104e5  jnz     short loc_180010506
0x1800104e7  test    rbx, rbx
0x1800104ea  jz      short loc_1800104FC
0x1800104ec  mov     rax, [rbx]
0x1800104ef  mov     rcx, rbx
0x1800104f2  mov     rax, [rax+10h]
0x1800104f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104fb  nop
0x1800104fc  mov     eax, 4B6h
0x180010501  jmp     loc_1800107F4
0x180010506  cmp     ebp, 3
0x180010509  jb      short loc_180010510
0x18001050b  mov     r9, rdi
0x18001050e  jmp     short loc_180010525
0x180010510  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180010517  cmp     ebp, 2
0x18001051a  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180010521  cmovnz  r9, rax; OLECHAR *
0x180010525  mov     [rsp+0E8h+var_C0], 0; struct IXMLDOMNode **
0x18001052e  lea     rax, [rsp+0E8h+sz]
0x180010533  mov     [rsp+0E8h+var_C8], rax; OLECHAR *
0x180010538  lea     r8, aOsid; "OSId"
0x18001053f  mov     rdx, rbx; struct IXMLDOMNode *
0x180010542  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180010545  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18001054a  mov     esi, eax
0x18001054c  test    eax, eax
0x18001054e  jz      short loc_18001056A
0x180010550  test    rbx, rbx
0x180010553  jz      short loc_180010565
0x180010555  mov     rax, [rbx]
0x180010558  mov     rcx, rbx
0x18001055b  mov     rax, [rax+10h]
0x18001055f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010564  nop
0x180010565  jmp     loc_1800107F2
0x18001056a  test    dword ptr [r14], 800h
0x180010571  jz      short loc_1800105D6
0x180010573  cmp     ebp, 3
0x180010576  jb      short loc_18001057D
0x180010578  mov     r9, rdi
0x18001057b  jmp     short loc_180010592
0x18001057d  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180010584  cmp     ebp, 2
0x180010587  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18001058e  cmovnz  r9, rax; OLECHAR *
0x180010592  lea     rax, [r14+18h]
0x180010596  mov     [rsp+0E8h+var_C0], 0; struct IXMLDOMNode **
0x18001059f  mov     [rsp+0E8h+var_C8], rax; OLECHAR *
0x1800105a4  lea     r8, aOsappid; "OSAppId"
0x1800105ab  mov     rdx, rbx; struct IXMLDOMNode *
0x1800105ae  mov     rcx, r15; struct IXMLDOMDocument2 *
0x1800105b1  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800105b6  mov     esi, eax
0x1800105b8  test    eax, eax
0x1800105ba  jz      short loc_1800105D6
0x1800105bc  test    rbx, rbx
0x1800105bf  jz      short loc_1800105D1
0x1800105c1  mov     rax, [rbx]
0x1800105c4  mov     rcx, rbx
0x1800105c7  mov     rax, [rax+10h]
0x1800105cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105d0  nop
0x1800105d1  jmp     loc_1800107F2
0x1800105d6  test    dword ptr [r14], 1000h
0x1800105dd  jz      short loc_180010645
0x1800105df  cmp     ebp, 3
0x1800105e2  jb      short loc_1800105E9
0x1800105e4  mov     r9, rdi
0x1800105e7  jmp     short loc_1800105FE
0x1800105e9  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x1800105f0  cmp     ebp, 2
0x1800105f3  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x1800105fa  cmovnz  r9, rax; OLECHAR *
0x1800105fe  lea     rax, [r14+11Ch]
0x180010605  mov     [rsp+0E8h+var_C0], 0; struct IXMLDOMNode **
0x18001060e  mov     [rsp+0E8h+var_C8], rax; OLECHAR *
0x180010613  lea     r8, aDnn; "DNN"
0x18001061a  mov     rdx, rbx; struct IXMLDOMNode *
0x18001061d  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180010620  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180010625  mov     esi, eax
0x180010627  test    eax, eax
0x180010629  jz      short loc_180010645
0x18001062b  test    rbx, rbx
0x18001062e  jz      short loc_180010640
0x180010630  mov     rax, [rbx]
0x180010633  mov     rcx, rbx
0x180010636  mov     rax, [rax+10h]
0x18001063a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001063f  nop
0x180010640  jmp     loc_1800107F2
0x180010645  test    dword ptr [r14], 2000h
0x18001064c  jz      short loc_1800106B4
0x18001064e  cmp     ebp, 3
0x180010651  jb      short loc_180010658
0x180010653  mov     r9, rdi
0x180010656  jmp     short loc_18001066D
0x180010658  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18001065f  cmp     ebp, 2
0x180010662  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180010669  cmovnz  r9, rax; OLECHAR *
0x18001066d  lea     rax, [r14+1E6h]
0x180010674  mov     [rsp+0E8h+var_C0], 0; struct IXMLDOMNode **
0x18001067d  mov     [rsp+0E8h+var_C8], rax; OLECHAR *
0x180010682  lea     r8, aDestinationfqd; "DestinationFQDN"
0x180010689  mov     rdx, rbx; struct IXMLDOMNode *
0x18001068c  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18001068f  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180010694  mov     esi, eax
0x180010696  test    eax, eax
0x180010698  jz      short loc_1800106B4
0x18001069a  test    rbx, rbx
0x18001069d  jz      short loc_1800106AF
0x18001069f  mov     rax, [rbx]
0x1800106a2  mov     rcx, rbx
0x1800106a5  mov     rax, [rax+10h]
0x1800106a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106ae  nop
0x1800106af  jmp     loc_1800107F2
0x1800106b4  test    dword ptr [r14], 4000h
0x1800106bb  jz      loc_1800107A6
0x1800106c1  mov     [rsp+0E8h+var_A0], 0
0x1800106ca  cmp     ebp, 3
0x1800106cd  jnb     short loc_1800106E4
0x1800106cf  lea     rdi, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x1800106d6  cmp     ebp, 2
0x1800106d9  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x1800106e0  cmovnz  rdi, rax
0x1800106e4  lea     rax, [rsp+0E8h+var_A0]
0x1800106e9  mov     [rsp+0E8h+var_C0], rax; struct IXMLDOMNode **
0x1800106ee  mov     [rsp+0E8h+var_C8], 0; OLECHAR *
0x1800106f7  mov     r9, rdi; OLECHAR *
0x1800106fa  lea     r8, aIpdescriptor; "IPDescriptor"
0x180010701  mov     rdx, rbx; struct IXMLDOMNode *
0x180010704  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180010707  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18001070c  mov     edi, eax
0x18001070e  test    eax, eax
0x180010710  jz      short loc_180010745
0x180010712  mov     rcx, [rsp+0E8h+var_A0]
0x180010717  test    rcx, rcx
0x18001071a  jz      short loc_180010729
0x18001071c  mov     rdx, [rcx]
0x18001071f  mov     rax, [rdx+10h]
0x180010723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010728  nop
0x180010729  test    rbx, rbx
0x18001072c  jz      short loc_18001073E
0x18001072e  mov     rax, [rbx]
0x180010731  mov     rcx, rbx
0x180010734  mov     rax, [rax+10h]
0x180010738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001073d  nop
0x18001073e  mov     eax, edi
0x180010740  jmp     loc_1800107F4
0x180010745  lea     r8, [r14+3F0h]; struct IP_DESCRIPTOR *
0x18001074c  mov     r9d, ebp; unsigned int
0x18001074f  mov     rdi, [rsp+0E8h+var_A0]
0x180010754  mov     rdx, rdi; struct IXMLDOMNode *
0x180010757  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18001075a  call    ?_generateIPDescriptorNode@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAUIP_DESCRIPTOR@@K@Z; _generateIPDescriptorNode(IXMLDOMDocument2 *,IXMLDOMNode *,IP_DESCRIPTOR *,ulong)
0x18001075f  mov     esi, eax
0x180010761  test    eax, eax
0x180010763  jz      short loc_180010791
0x180010765  test    rdi, rdi
0x180010768  jz      short loc_18001077A
0x18001076a  mov     rax, [rdi]
0x18001076d  mov     rcx, rdi
0x180010770  mov     rax, [rax+10h]
0x180010774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010779  nop
0x18001077a  test    rbx, rbx
0x18001077d  jz      short loc_18001078F
0x18001077f  mov     rax, [rbx]
0x180010782  mov     rcx, rbx
0x180010785  mov     rax, [rax+10h]
0x180010789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001078e  nop
0x18001078f  jmp     short loc_1800107F2
0x180010791  test    rdi, rdi
0x180010794  jz      short loc_1800107A6
0x180010796  mov     rax, [rdi]
0x180010799  mov     rcx, rdi
0x18001079c  mov     rax, [rax+10h]
0x1800107a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107a5  nop
0x1800107a6  mov     r8d, [r14+118h]; unsigned int
0x1800107ad  test    r8d, r8d
0x1800107b0  jz      short loc_1800107DD
0x1800107b2  mov     r9d, ebp; unsigned int
0x1800107b5  mov     rdx, rbx; struct IXMLDOMNode *
0x1800107b8  mov     rcx, r15; struct IXMLDOMDocument2 *
0x1800107bb  call    ?_generateConnectionCapabilitiesNode@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@KK@Z; _generateConnectionCapabilitiesNode(IXMLDOMDocument2 *,IXMLDOMNode *,ulong,ulong)
0x1800107c0  mov     esi, eax
0x1800107c2  test    eax, eax
0x1800107c4  jz      short loc_1800107DD
0x1800107c6  test    rbx, rbx
0x1800107c9  jz      short loc_1800107DB
0x1800107cb  mov     rax, [rbx]
0x1800107ce  mov     rcx, rbx
0x1800107d1  mov     rax, [rax+10h]
0x1800107d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107da  nop
0x1800107db  jmp     short loc_1800107F2
0x1800107dd  test    rbx, rbx
0x1800107e0  jz      short loc_1800107F2
0x1800107e2  mov     rax, [rbx]
0x1800107e5  mov     rcx, rbx
0x1800107e8  mov     rax, [rax+10h]
0x1800107ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107f1  nop
0x1800107f2  mov     eax, esi
0x1800107f4  mov     rcx, [rsp+0E8h+var_48]
0x1800107fc  xor     rcx, rsp; StackCookie
0x1800107ff  call    __security_check_cookie
0x180010804  add     rsp, 0B8h
0x18001080b  pop     r15
0x18001080d  pop     r14
0x18001080f  pop     rdi
0x180010810  pop     rsi
0x180010811  pop     rbp
0x180010812  pop     rbx
0x180010813  retn
  ... truncated ...
```
