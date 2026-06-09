# _generateContextNode(IXMLDOMDocument2 *,IXMLDOMNode *,WWAN_CONTEXT_INFO *,ulong)

- ea: `0x1800092fc`
- end: `0x18000956d`
- name: `?_generateContextNode@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAUWWAN_CONTEXT_INFO@@K@Z`
- size: `625`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct WWAN_CONTEXT_INFO *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a298`
- `0x18000ec80`

## callees

- `0x1800092fc`
- `0x18000b060`
- `0x180011f90`
- `0x180012310`
- `0x180014010`

## string_xrefs

- `0x180009322`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x180009334`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180009399`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180009431`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x1800094a0`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000950f`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000931b`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000943b`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x1800094aa`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x1800093b9`: `AccessString`
- `0x18000945e`: `Compression`
- `0x1800094cd`: `AuthProtocol`

## pseudocode

```c
__int64 __fastcall _generateContextNode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        struct WWAN_CONTEXT_INFO *a3,
        unsigned int a4)
{
  OLECHAR *v7; // r14
  OLECHAR *v8; // r9
  unsigned int v9; // ebx
  struct IXMLDOMNode *v11; // rbx
  OLECHAR *v12; // r9
  unsigned int UserLogonCredNode; // ebp
  OLECHAR *v14; // r9
  OLECHAR *v15; // r9
  struct IXMLDOMNode **v16; // [rsp+38h] [rbp-50h]
  struct IXMLDOMNode **v17; // [rsp+38h] [rbp-50h]
  struct IXMLDOMNode **v18; // [rsp+38h] [rbp-50h]
  struct IXMLDOMNode *v19; // [rsp+40h] [rbp-48h] BYREF

  v19 = 0;
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
  v9 = XcAddChildElement(a1, a2, (OLECHAR *)L"Context", v8, 0, &v19);
  if ( v9 )
  {
    if ( v19 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
    return v9;
  }
  else
  {
    v11 = v19;
    if ( (*(_BYTE *)a3 & 1) == 0 )
      goto LABEL_49;
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
    UserLogonCredNode = XcAddChildElement(a1, v19, (OLECHAR *)L"AccessString", v12, (OLECHAR *)a3 + 4, 0);
    if ( UserLogonCredNode )
    {
      if ( v11 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
    }
    else
    {
LABEL_49:
      if ( (*(_BYTE *)a3 & 2) != 0 && (UserLogonCredNode = generateUserLogonCredNode(a1)) != 0 )
      {
        if ( v11 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
      }
      else
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
        UserLogonCredNode = XcAddChildElementEnum(
                              a1,
                              v11,
                              (OLECHAR *)L"Compression",
                              v14,
                              *((_DWORD *)a3 + 310),
                              (const struct _XC_STRING_VALUE_MAPPING *)&_compression,
                              2u,
                              v16);
        if ( UserLogonCredNode )
        {
          if ( v11 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
        }
        else
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
          UserLogonCredNode = XcAddChildElementEnum(
                                a1,
                                v11,
                                (OLECHAR *)L"AuthProtocol",
                                v15,
                                *((_DWORD *)a3 + 311),
                                (const struct _XC_STRING_VALUE_MAPPING *)&_authProtocol,
                                5u,
                                v17);
          if ( UserLogonCredNode )
          {
            if ( v11 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
          }
          else
          {
            if ( a4 >= 2 && (*(_BYTE *)a3 & 8) != 0 )
            {
              if ( a4 < 3 )
                v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
              UserLogonCredNode = XcAddChildElementEnum(
                                    a1,
                                    v11,
                                    (OLECHAR *)L"IPType",
                                    v7,
                                    *((_DWORD *)a3 + 316),
                                    (const struct _XC_STRING_VALUE_MAPPING *)&_ipTYpe,
                                    5u,
                                    v18);
            }
            if ( v11 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
          }
        }
      }
    }
    return UserLogonCredNode;
  }
}

```

## disassembly

```asm
0x1800092fc  push    rbx
0x1800092fe  push    rbp
0x1800092ff  push    rsi
0x180009300  push    rdi
0x180009301  push    r14
0x180009303  push    r15
0x180009305  sub     rsp, 58h
0x180009309  mov     edi, r9d
0x18000930c  mov     rsi, r8
0x18000930f  mov     r15, rcx
0x180009312  mov     [rsp+88h+var_48], 0
0x18000931b  lea     rbp, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180009322  lea     r14, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x180009329  cmp     r9d, 3
0x18000932d  jb      short loc_180009334
0x18000932f  mov     r9, r14
0x180009332  jmp     short loc_180009342
0x180009334  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000933b  cmp     edi, 2
0x18000933e  cmovnz  r9, rbp; OLECHAR *
0x180009342  lea     rax, [rsp+88h+var_48]
0x180009347  mov     [rsp+88h+var_60], rax; struct IXMLDOMNode **
0x18000934c  mov     [rsp+88h+var_68], 0; OLECHAR *
0x180009355  lea     r8, aContext; "Context"
0x18000935c  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180009361  mov     ebx, eax
0x180009363  test    eax, eax
0x180009365  jz      short loc_180009385
0x180009367  mov     rcx, [rsp+88h+var_48]
0x18000936c  test    rcx, rcx
0x18000936f  jz      short loc_18000937E
0x180009371  mov     rdx, [rcx]
0x180009374  mov     rax, [rdx+10h]
0x180009378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000937d  nop
0x18000937e  mov     eax, ebx
0x180009380  jmp     loc_180009560
0x180009385  mov     rbx, [rsp+88h+var_48]
0x18000938a  test    byte ptr [rsi], 1
0x18000938d  jz      short loc_1800093EB
0x18000938f  cmp     edi, 3
0x180009392  jb      short loc_180009399
0x180009394  mov     r9, r14
0x180009397  jmp     short loc_1800093A7
0x180009399  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x1800093a0  cmp     edi, 2
0x1800093a3  cmovnz  r9, rbp; OLECHAR *
0x1800093a7  lea     rax, [rsi+8]
0x1800093ab  mov     [rsp+88h+var_60], 0; struct IXMLDOMNode **
0x1800093b4  mov     [rsp+88h+var_68], rax; OLECHAR *
0x1800093b9  lea     r8, aAccessstring; "AccessString"
0x1800093c0  mov     rdx, rbx; struct IXMLDOMNode *
0x1800093c3  mov     rcx, r15; struct IXMLDOMDocument2 *
0x1800093c6  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800093cb  mov     ebp, eax
0x1800093cd  test    eax, eax
0x1800093cf  jz      short loc_1800093EB
0x1800093d1  test    rbx, rbx
0x1800093d4  jz      short loc_1800093E6
0x1800093d6  mov     rcx, [rbx]
0x1800093d9  mov     rax, [rcx+10h]
0x1800093dd  mov     rcx, rbx
0x1800093e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093e5  nop
0x1800093e6  jmp     loc_18000955E
0x1800093eb  test    byte ptr [rsi], 2
0x1800093ee  jz      short loc_180009421
0x1800093f0  mov     r9d, edi
0x1800093f3  mov     r8, rsi
0x1800093f6  mov     rdx, rbx
0x1800093f9  mov     rcx, r15; struct IXMLDOMDocument2 *
0x1800093fc  call    _generateUserLogonCredNode
0x180009401  mov     ebp, eax
0x180009403  test    eax, eax
0x180009405  jz      short loc_180009421
0x180009407  test    rbx, rbx
0x18000940a  jz      short loc_18000941C
0x18000940c  mov     rcx, [rbx]
0x18000940f  mov     rax, [rcx+10h]
0x180009413  mov     rcx, rbx
0x180009416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000941b  nop
0x18000941c  jmp     loc_18000955E
0x180009421  mov     eax, [rsi+4D8h]
0x180009427  cmp     edi, 3
0x18000942a  jb      short loc_180009431
0x18000942c  mov     r9, r14
0x18000942f  jmp     short loc_180009446
0x180009431  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180009438  cmp     edi, 2
0x18000943b  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180009442  cmovnz  r9, rcx; OLECHAR *
0x180009446  mov     [rsp+88h+var_58], 2; unsigned int
0x18000944e  lea     rcx, ?_compression@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _compression
0x180009455  mov     [rsp+88h+var_60], rcx; struct _XC_STRING_VALUE_MAPPING *
0x18000945a  mov     dword ptr [rsp+88h+var_68], eax; unsigned int
0x18000945e  lea     r8, aCompression; "Compression"
0x180009465  mov     rdx, rbx; struct IXMLDOMNode *
0x180009468  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18000946b  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x180009470  mov     ebp, eax
0x180009472  test    eax, eax
0x180009474  jz      short loc_180009490
0x180009476  test    rbx, rbx
0x180009479  jz      short loc_18000948B
0x18000947b  mov     rcx, [rbx]
0x18000947e  mov     rax, [rcx+10h]
0x180009482  mov     rcx, rbx
0x180009485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000948a  nop
0x18000948b  jmp     loc_18000955E
0x180009490  mov     eax, [rsi+4DCh]
0x180009496  cmp     edi, 3
0x180009499  jb      short loc_1800094A0
0x18000949b  mov     r9, r14
0x18000949e  jmp     short loc_1800094B5
0x1800094a0  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x1800094a7  cmp     edi, 2
0x1800094aa  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x1800094b1  cmovnz  r9, rcx; OLECHAR *
0x1800094b5  mov     [rsp+88h+var_58], 5; unsigned int
0x1800094bd  lea     rcx, ?_authProtocol@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _authProtocol
0x1800094c4  mov     [rsp+88h+var_60], rcx; struct _XC_STRING_VALUE_MAPPING *
0x1800094c9  mov     dword ptr [rsp+88h+var_68], eax; unsigned int
0x1800094cd  lea     r8, aAuthprotocol; "AuthProtocol"
0x1800094d4  mov     rdx, rbx; struct IXMLDOMNode *
0x1800094d7  mov     rcx, r15; struct IXMLDOMDocument2 *
0x1800094da  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x1800094df  mov     ebp, eax
0x1800094e1  test    eax, eax
0x1800094e3  jz      short loc_1800094FC
0x1800094e5  test    rbx, rbx
0x1800094e8  jz      short loc_1800094FA
0x1800094ea  mov     rcx, [rbx]
0x1800094ed  mov     rax, [rcx+10h]
0x1800094f1  mov     rcx, rbx
0x1800094f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f9  nop
0x1800094fa  jmp     short loc_18000955E
0x1800094fc  cmp     edi, 2
0x1800094ff  jb      short loc_180009549
0x180009501  test    byte ptr [rsi], 8
0x180009504  jz      short loc_180009549
0x180009506  mov     eax, [rsi+4F0h]
0x18000950c  cmp     edi, 3
0x18000950f  lea     rcx, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180009516  cmovb   r14, rcx
0x18000951a  mov     [rsp+88h+var_58], 5; unsigned int
0x180009522  lea     rcx, ?_ipTYpe@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _ipTYpe
0x180009529  mov     [rsp+88h+var_60], rcx; struct _XC_STRING_VALUE_MAPPING *
0x18000952e  mov     dword ptr [rsp+88h+var_68], eax; unsigned int
0x180009532  mov     r9, r14; OLECHAR *
0x180009535  lea     r8, aIptype; "IPType"
0x18000953c  mov     rdx, rbx; struct IXMLDOMNode *
0x18000953f  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180009542  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x180009547  mov     ebp, eax
0x180009549  test    rbx, rbx
0x18000954c  jz      short loc_18000955E
0x18000954e  mov     rax, [rbx]
0x180009551  mov     rcx, rbx
0x180009554  mov     rax, [rax+10h]
0x180009558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000955d  nop
0x18000955e  mov     eax, ebp
0x180009560  add     rsp, 58h
0x180009564  pop     r15
0x180009566  pop     r14
0x180009568  pop     rdi
0x180009569  pop     rsi
0x18000956a  pop     rbp
0x18000956b  pop     rbx
0x18000956c  retn
```
