# _generateRSDNode(IXMLDOMDocument2 *,IXMLDOMNode *,ROUTE_SELECTION_DESCRIPTOR *,ulong)

- ea: `0x18000fc08`
- end: `0x1800100a6`
- name: `?_generateRSDNode@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAUROUTE_SELECTION_DESCRIPTOR@@K@Z`
- size: `1182`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct ROUTE_SELECTION_DESCRIPTOR *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800100ac`

## callees

- `0x18000fc08`
- `0x18001027c`
- `0x180011f90`
- `0x180012260`
- `0x180012310`
- `0x180014010`

## string_xrefs

- `0x18000fc40`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000fc52`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000fc90`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000fce0`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000fd54`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000fe97`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000ff10`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000ff9d`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000fff4`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180010048`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000fc39`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000fd5e`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000fe08`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000ff1a`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000ffa7`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000fffe`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180010052`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000fc64`: `RouteSelectionDescriptorPrecedence`
- `0x180010078`: `AccessTypePreference`

## pseudocode

```c
unsigned int __fastcall _generateRSDNode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        struct ROUTE_SELECTION_DESCRIPTOR *a3,
        unsigned int a4)
{
  struct IXMLDOMNode *v6; // rdi
  struct IXMLDOMDocument2 *v7; // r13
  OLECHAR *v8; // r15
  OLECHAR *v9; // r9
  unsigned int result; // eax
  unsigned int v11; // r12d
  OLECHAR *v12; // r9
  _DWORD *v13; // rax
  OLECHAR *v14; // r9
  unsigned int v15; // ebx
  struct IXMLDOMNode *v16; // rbx
  OLECHAR *v17; // r9
  unsigned int v18; // edi
  struct IXMLDOMNode *v19; // rdi
  unsigned int SNSSAINode; // r13d
  _DWORD *v21; // rax
  OLECHAR *v22; // r9
  OLECHAR *v23; // rdx
  struct IXMLDOMNode *v24; // rbx
  unsigned int v25; // edi
  OLECHAR *v26; // r9
  unsigned int v27; // r12d
  unsigned int v28; // eax
  OLECHAR *v29; // r9
  OLECHAR *v30; // r9
  unsigned int v31; // eax
  struct IXMLDOMNode **v32; // [rsp+28h] [rbp-28h]
  struct IXMLDOMNode **v33; // [rsp+28h] [rbp-28h]
  struct IXMLDOMNode **v34; // [rsp+38h] [rbp-18h]
  struct IXMLDOMNode *v35; // [rsp+40h] [rbp-10h] BYREF
  struct IXMLDOMNode *v38; // [rsp+A0h] [rbp+50h] BYREF

  v6 = a2;
  v7 = a1;
  v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  if ( a4 < 3 )
  {
    v9 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
    if ( a4 != 2 )
      v9 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
  }
  else
  {
    v9 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  }
  result = XcAddChildElementDWORD(
             a1,
             a2,
             (OLECHAR *)L"RouteSelectionDescriptorPrecedence",
             v9,
             *(unsigned __int8 *)a3,
             v32);
  v11 = 0;
  if ( result )
    return result;
  if ( *((_DWORD *)a3 + 1) )
  {
    if ( a4 < 3 )
    {
      v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( a4 != 2 )
        v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    result = XcAddChildElementDWORD(v7, v6, (OLECHAR *)L"SSCMode", v12, *((unsigned __int8 *)a3 + 1), v33);
    if ( result )
      return result;
  }
  v13 = (_DWORD *)*((_QWORD *)a3 + 3);
  if ( !v13 || !*v13 )
  {
LABEL_35:
    v21 = (_DWORD *)*((_QWORD *)a3 + 4);
    if ( v21 && *v21 )
    {
      v38 = 0;
      if ( a4 < 3 )
      {
        v22 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
        if ( a4 != 2 )
          v22 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
      }
      else
      {
        v22 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
      }
      v15 = XcAddChildElement(v7, v6, (OLECHAR *)L"DNNSelections", v22, 0, &v38);
      if ( v15 )
      {
        if ( v38 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v38->lpVtbl->Release)(v38);
        return v15;
      }
      v23 = (OLECHAR *)*((_QWORD *)a3 + 4);
      v24 = v38;
      if ( *(_DWORD *)v23 )
      {
        v25 = 0;
        while ( 1 )
        {
          if ( a4 < 3 )
          {
            v26 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
            if ( a4 != 2 )
              v26 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
          }
          else
          {
            v26 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
          }
          v27 = XcAddChildElement(v7, v24, (OLECHAR *)L"DNNSelection", v26, &v23[101 * v25 + 2], 0);
          if ( v27 )
            break;
          ++v25;
          v23 = (OLECHAR *)*((_QWORD *)a3 + 4);
          if ( v25 >= *(_DWORD *)v23 )
          {
            v6 = a2;
            goto LABEL_64;
          }
        }
        if ( v24 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
        return v27;
      }
LABEL_64:
      if ( v24 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
    }
    v28 = *((_DWORD *)a3 + 2);
    if ( !v28 )
      goto LABEL_89;
    if ( a4 < 3 )
    {
      v29 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( a4 != 2 )
        v29 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v29 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    result = XcAddChildElementEnum(
               v7,
               v6,
               (OLECHAR *)L"PDUSession",
               v29,
               v28,
               (const struct _XC_STRING_VALUE_MAPPING *)&_SessionType,
               7u,
               v34);
    if ( !result )
    {
LABEL_89:
      if ( !*((_DWORD *)a3 + 3) )
        goto LABEL_81;
      if ( a4 < 3 )
      {
        v30 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
        if ( a4 != 2 )
          v30 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
      }
      else
      {
        v30 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
      }
      result = XcAddChildElementEnum(
                 v7,
                 v6,
                 (OLECHAR *)L"NonSeamlessSOffloadIndication",
                 v30,
                 1u,
                 (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                 4u,
                 v34);
      if ( !result )
      {
LABEL_81:
        v31 = *((_DWORD *)a3 + 4);
        if ( v31 )
        {
          if ( a4 < 3 )
          {
            v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
            if ( a4 != 2 )
              v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
          }
          return XcAddChildElementEnum(
                   v7,
                   v6,
                   (OLECHAR *)L"AccessTypePreference",
                   v8,
                   v31,
                   (const struct _XC_STRING_VALUE_MAPPING *)&_AccessTypePreference,
                   2u,
                   v34);
        }
        else
        {
          return 0;
        }
      }
    }
    return result;
  }
  v38 = 0;
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
  v15 = XcAddChildElement(v7, v6, (OLECHAR *)L"SNSSAIs", v14, 0, &v38);
  if ( v15 )
  {
    if ( v38 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v38->lpVtbl->Release)(v38);
    return v15;
  }
  v16 = v38;
  if ( !**((_DWORD **)a3 + 3) )
  {
LABEL_33:
    if ( v16 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v16->lpVtbl->Release)(v16);
    goto LABEL_35;
  }
  while ( 1 )
  {
    v35 = 0;
    if ( a4 < 3 )
    {
      v17 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( a4 != 2 )
        v17 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v17 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    v18 = XcAddChildElement(v7, v16, (OLECHAR *)L"SNSSAI", v17, 0, &v35);
    if ( v18 )
      break;
    v19 = v35;
    SNSSAINode = _generateSNSSAINode(v7, v35, (struct SNSSAI_TYPE *)(*((_QWORD *)a3 + 3) + 4 * (5LL * v11 + 1)), a4);
    if ( SNSSAINode )
    {
      if ( v19 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
      if ( v16 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v16->lpVtbl->Release)(v16);
      return SNSSAINode;
    }
    if ( v19 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
    ++v11;
    v7 = a1;
    if ( v11 >= **((_DWORD **)a3 + 3) )
    {
      v6 = a2;
      goto LABEL_33;
    }
  }
  if ( v35 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v35->lpVtbl->Release)(v35);
  if ( v16 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v16->lpVtbl->Release)(v16);
  return v18;
}

```

## disassembly

```asm
0x18000fc08  mov     [rsp-38h+arg_18], rbx
0x18000fc0d  mov     [rsp-38h+arg_8], rdx
0x18000fc12  mov     [rsp-38h+arg_0], rcx
0x18000fc17  push    rbp
0x18000fc18  push    rsi
0x18000fc19  push    rdi
0x18000fc1a  push    r12
0x18000fc1c  push    r13
0x18000fc1e  push    r14
0x18000fc20  push    r15
0x18000fc22  mov     rbp, rsp
0x18000fc25  sub     rsp, 50h
0x18000fc29  mov     esi, r9d
0x18000fc2c  mov     r14, r8
0x18000fc2f  mov     rdi, rdx
0x18000fc32  mov     r13, rcx
0x18000fc35  movzx   eax, byte ptr [r8]
0x18000fc39  lea     rbx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000fc40  lea     r15, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000fc47  cmp     r9d, 3
0x18000fc4b  jb      short loc_18000FC52
0x18000fc4d  mov     r9, r15
0x18000fc50  jmp     short loc_18000FC60
0x18000fc52  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000fc59  cmp     esi, 2
0x18000fc5c  cmovnz  r9, rbx; OLECHAR *
0x18000fc60  mov     dword ptr [rsp+50h+var_30], eax; unsigned int
0x18000fc64  lea     r8, aRouteselection_0; "RouteSelectionDescriptorPrecedence"
0x18000fc6b  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000fc70  xor     r12d, r12d
0x18000fc73  test    eax, eax
0x18000fc75  jnz     loc_18001008E
0x18000fc7b  cmp     [r14+4], r12d
0x18000fc7f  jz      short loc_18000FCBC
0x18000fc81  movzx   eax, byte ptr [r14+1]
0x18000fc86  cmp     esi, 3
0x18000fc89  jb      short loc_18000FC90
0x18000fc8b  mov     r9, r15
0x18000fc8e  jmp     short loc_18000FC9E
0x18000fc90  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000fc97  cmp     esi, 2
0x18000fc9a  cmovnz  r9, rbx; OLECHAR *
0x18000fc9e  mov     dword ptr [rsp+50h+var_30], eax; unsigned int
0x18000fca2  lea     r8, aSscmode; "SSCMode"
0x18000fca9  mov     rdx, rdi; struct IXMLDOMNode *
0x18000fcac  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000fcaf  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000fcb4  test    eax, eax
0x18000fcb6  jnz     loc_18001008E
0x18000fcbc  mov     rax, [r14+18h]
0x18000fcc0  test    rax, rax
0x18000fcc3  jz      loc_18000FE0F
0x18000fcc9  cmp     [rax], r12d
0x18000fccc  jbe     loc_18000FE0F
0x18000fcd2  mov     [rbp+arg_10], r12
0x18000fcd6  cmp     esi, 3
0x18000fcd9  jb      short loc_18000FCE0
0x18000fcdb  mov     r9, r15
0x18000fcde  jmp     short loc_18000FCEE
0x18000fce0  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000fce7  cmp     esi, 2
0x18000fcea  cmovnz  r9, rbx; OLECHAR *
0x18000fcee  lea     rax, [rbp+arg_10]
0x18000fcf2  mov     [rsp+50h+var_28], rax; struct IXMLDOMNode **
0x18000fcf7  mov     [rsp+50h+var_30], r12; OLECHAR *
0x18000fcfc  lea     r8, aSnssais; "SNSSAIs"
0x18000fd03  mov     rdx, rdi; struct IXMLDOMNode *
0x18000fd06  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000fd09  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000fd0e  mov     ebx, eax
0x18000fd10  test    eax, eax
0x18000fd12  jz      short loc_18000FD31
0x18000fd14  mov     rcx, [rbp+arg_10]
0x18000fd18  test    rcx, rcx
0x18000fd1b  jz      short loc_18000FD2A
0x18000fd1d  mov     rdx, [rcx]
0x18000fd20  mov     rax, [rdx+10h]
0x18000fd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd29  nop
0x18000fd2a  mov     eax, ebx
0x18000fd2c  jmp     loc_18001008E
0x18000fd31  mov     rax, [r14+18h]
0x18000fd35  mov     rbx, [rbp+arg_10]
0x18000fd39  cmp     dword ptr [rax], 0
0x18000fd3c  jbe     loc_18000FDF0
0x18000fd42  mov     [rbp+var_10], 0
0x18000fd4a  cmp     esi, 3
0x18000fd4d  jb      short loc_18000FD54
0x18000fd4f  mov     r9, r15
0x18000fd52  jmp     short loc_18000FD69
0x18000fd54  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000fd5b  cmp     esi, 2
0x18000fd5e  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000fd65  cmovnz  r9, rax; OLECHAR *
0x18000fd69  lea     rax, [rbp+var_10]
0x18000fd6d  mov     [rsp+50h+var_28], rax; struct IXMLDOMNode **
0x18000fd72  mov     [rsp+50h+var_30], 0; OLECHAR *
0x18000fd7b  lea     r8, aSnssai; "SNSSAI"
0x18000fd82  mov     rdx, rbx; struct IXMLDOMNode *
0x18000fd85  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000fd88  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000fd8d  mov     edi, eax
0x18000fd8f  test    eax, eax
0x18000fd91  jnz     loc_18000FE65
0x18000fd97  mov     eax, r12d
0x18000fd9a  lea     rcx, [rax+rax*4]
0x18000fd9e  mov     rax, [r14+18h]
0x18000fda2  lea     rcx, [rcx+1]
0x18000fda6  lea     r8, [rax+rcx*4]; struct SNSSAI_TYPE *
0x18000fdaa  mov     r9d, esi; unsigned int
0x18000fdad  mov     rdi, [rbp+var_10]
0x18000fdb1  mov     rdx, rdi; struct IXMLDOMNode *
0x18000fdb4  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000fdb7  call    ?_generateSNSSAINode@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAUSNSSAI_TYPE@@K@Z; _generateSNSSAINode(IXMLDOMDocument2 *,IXMLDOMNode *,SNSSAI_TYPE *,ulong)
0x18000fdbc  mov     r13d, eax
0x18000fdbf  test    eax, eax
0x18000fdc1  jnz     short loc_18000FE33
0x18000fdc3  test    rdi, rdi
0x18000fdc6  jz      short loc_18000FDD8
0x18000fdc8  mov     rax, [rdi]
0x18000fdcb  mov     rcx, rdi
0x18000fdce  mov     rax, [rax+10h]
0x18000fdd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdd7  nop
0x18000fdd8  inc     r12d
0x18000fddb  mov     rax, [r14+18h]
0x18000fddf  cmp     r12d, [rax]
0x18000fde2  mov     r13, [rbp+arg_0]
0x18000fde6  jb      loc_18000FD42
0x18000fdec  mov     rdi, [rbp+arg_8]
0x18000fdf0  xor     r12d, r12d
0x18000fdf3  test    rbx, rbx
0x18000fdf6  jz      short loc_18000FE08
0x18000fdf8  mov     rax, [rbx]
0x18000fdfb  mov     rcx, rbx
0x18000fdfe  mov     rax, [rax+10h]
0x18000fe02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe07  nop
0x18000fe08  lea     rbx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000fe0f  mov     rax, [r14+20h]
0x18000fe13  test    rax, rax
0x18000fe16  jz      loc_18000FF6E
0x18000fe1c  cmp     [rax], r12d
0x18000fe1f  jbe     loc_18000FF6E
0x18000fe25  mov     [rbp+arg_10], r12
0x18000fe29  cmp     esi, 3
0x18000fe2c  jb      short loc_18000FE97
0x18000fe2e  mov     r9, r15
0x18000fe31  jmp     short loc_18000FEA5
0x18000fe33  test    rdi, rdi
0x18000fe36  jz      short loc_18000FE48
0x18000fe38  mov     rax, [rdi]
0x18000fe3b  mov     rcx, rdi
0x18000fe3e  mov     rax, [rax+10h]
0x18000fe42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe47  nop
0x18000fe48  test    rbx, rbx
0x18000fe4b  jz      short loc_18000FE5D
0x18000fe4d  mov     rax, [rbx]
0x18000fe50  mov     rcx, rbx
0x18000fe53  mov     rax, [rax+10h]
0x18000fe57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe5c  nop
0x18000fe5d  mov     eax, r13d
0x18000fe60  jmp     loc_18001008E
0x18000fe65  mov     rcx, [rbp+var_10]
0x18000fe69  test    rcx, rcx
0x18000fe6c  jz      short loc_18000FE7B
0x18000fe6e  mov     rax, [rcx]
0x18000fe71  mov     rax, [rax+10h]
0x18000fe75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe7a  nop
0x18000fe7b  test    rbx, rbx
0x18000fe7e  jz      short loc_18000FE90
0x18000fe80  mov     rax, [rbx]
0x18000fe83  mov     rcx, rbx
0x18000fe86  mov     rax, [rax+10h]
0x18000fe8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe8f  nop
0x18000fe90  mov     eax, edi
0x18000fe92  jmp     loc_18001008E
0x18000fe97  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000fe9e  cmp     esi, 2
0x18000fea1  cmovnz  r9, rbx; OLECHAR *
0x18000fea5  lea     rax, [rbp+arg_10]
0x18000fea9  mov     [rsp+50h+var_28], rax; struct IXMLDOMNode **
0x18000feae  mov     [rsp+50h+var_30], r12; OLECHAR *
0x18000feb3  lea     r8, aDnnselections; "DNNSelections"
0x18000feba  mov     rdx, rdi; struct IXMLDOMNode *
0x18000febd  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000fec0  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000fec5  mov     ebx, eax
0x18000fec7  test    eax, eax
0x18000fec9  jz      short loc_18000FEE6
0x18000fecb  mov     rcx, [rbp+arg_10]
0x18000fecf  test    rcx, rcx
0x18000fed2  jz      short loc_18000FEE1
0x18000fed4  mov     rdx, [rcx]
0x18000fed7  mov     rax, [rdx+10h]
0x18000fedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fee0  nop
0x18000fee1  jmp     loc_18000FD2A
0x18000fee6  mov     rdx, [r14+20h]
0x18000feea  mov     rbx, [rbp+arg_10]
0x18000feee  cmp     [rdx], r12d
0x18000fef1  jbe     short loc_18000FF59
0x18000fef3  mov     edi, r12d
0x18000fef6  mov     eax, edi
0x18000fef8  imul    rcx, rax, 0CAh
0x18000feff  lea     rax, [rdx+4]
0x18000ff03  add     rax, rcx
0x18000ff06  cmp     esi, 3
0x18000ff09  jb      short loc_18000FF10
0x18000ff0b  mov     r9, r15
0x18000ff0e  jmp     short loc_18000FF25
0x18000ff10  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000ff17  cmp     esi, 2
0x18000ff1a  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000ff21  cmovnz  r9, rcx; OLECHAR *
0x18000ff25  mov     [rsp+50h+var_28], r12; struct IXMLDOMNode **
0x18000ff2a  mov     [rsp+50h+var_30], rax; OLECHAR *
0x18000ff2f  lea     r8, aDnnselection; "DNNSelection"
0x18000ff36  mov     rdx, rbx; struct IXMLDOMNode *
0x18000ff39  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000ff3c  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000ff41  mov     r12d, eax
0x18000ff44  test    eax, eax
0x18000ff46  jnz     short loc_18000FF80
0x18000ff48  inc     edi
0x18000ff4a  mov     rdx, [r14+20h]
0x18000ff4e  cmp     edi, [rdx]
0x18000ff50  mov     r12d, eax
0x18000ff53  jb      short loc_18000FEF6
0x18000ff55  mov     rdi, [rbp+arg_8]
0x18000ff59  test    rbx, rbx
0x18000ff5c  jz      short loc_18000FF6E
0x18000ff5e  mov     rax, [rbx]
0x18000ff61  mov     rcx, rbx
0x18000ff64  mov     rax, [rax+10h]
0x18000ff68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff6d  nop
0x18000ff6e  mov     eax, [r14+8]
0x18000ff72  test    eax, eax
0x18000ff74  jz      short loc_18000FFE4
0x18000ff76  cmp     esi, 3
0x18000ff79  jb      short loc_18000FF9D
0x18000ff7b  mov     r9, r15
0x18000ff7e  jmp     short loc_18000FFB2
0x18000ff80  test    rbx, rbx
0x18000ff83  jz      short loc_18000FF95
0x18000ff85  mov     rax, [rbx]
0x18000ff88  mov     rcx, rbx
0x18000ff8b  mov     rax, [rax+10h]
0x18000ff8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff94  nop
0x18000ff95  mov     eax, r12d
0x18000ff98  jmp     loc_18001008E
0x18000ff9d  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000ffa4  cmp     esi, 2
0x18000ffa7  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000ffae  cmovnz  r9, rcx; OLECHAR *
0x18000ffb2  mov     [rsp+50h+var_20], 7; unsigned int
0x18000ffba  lea     rcx, ?_SessionType@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _SessionType
0x18000ffc1  mov     [rsp+50h+var_28], rcx; struct _XC_STRING_VALUE_MAPPING *
0x18000ffc6  mov     dword ptr [rsp+50h+var_30], eax; unsigned int
0x18000ffca  lea     r8, aPdusession; "PDUSession"
0x18000ffd1  mov     rdx, rdi; struct IXMLDOMNode *
0x18000ffd4  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000ffd7  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18000ffdc  test    eax, eax
0x18000ffde  jnz     loc_18001008E
0x18000ffe4  cmp     [r14+0Ch], r12d
0x18000ffe8  jz      short loc_18001003B
0x18000ffea  cmp     esi, 3
0x18000ffed  jb      short loc_18000FFF4
0x18000ffef  mov     r9, r15
0x18000fff2  jmp     short loc_180010009
0x18000fff4  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000fffb  cmp     esi, 2
0x18000fffe  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180010005  cmovnz  r9, rax; OLECHAR *
0x180010009  mov     [rsp+50h+var_20], 4; unsigned int
0x180010011  lea     rax, off_180015490; "true"
0x180010018  mov     [rsp+50h+var_28], rax; struct _XC_STRING_VALUE_MAPPING *
0x18001001d  mov     dword ptr [rsp+50h+var_30], 1; unsigned int
0x180010025  lea     r8, aNonseamlesssof; "NonSeamlessSOffloadIndication"
0x18001002c  mov     rdx, rdi; struct IXMLDOMNode *
0x18001002f  mov     rcx, r13; struct IXMLDOMDocument2 *
0x180010032  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x180010037  test    eax, eax
0x180010039  jnz     short loc_18001008E
0x18001003b  mov     eax, [r14+10h]
0x18001003f  test    eax, eax
0x180010041  jz      short loc_18001008C
0x180010043  cmp     esi, 3
0x180010046  jnb     short loc_18001005D
0x180010048  lea     r15, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18001004f  cmp     esi, 2
0x180010052  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180010059  cmovnz  r15, rcx
  ... truncated ...
```
