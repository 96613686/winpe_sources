# ConfigValidateXMLElementAttributes(IRequestContext *,_CONFIGXML_ELEMENT *,_FWXML_ELEMENT *,ushort const *)

- ea: `0x180007fb0`
- end: `0x180008912`
- name: `?ConfigValidateXMLElementAttributes@@YAHPEAVIRequestContext@@PEAU_CONFIGXML_ELEMENT@@PEAU_FWXML_ELEMENT@@PEBG@Z`
- size: `2402`
- prototype: `__int64 __fastcall(struct IRequestContext *, struct _CONFIGXML_ELEMENT *, struct _FWXML_ELEMENT *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003b1c0`

## callees

- `0x180005d10`
- `0x180007380`
- `0x180007fb0`
- `0x180008920`
- `0x180008990`
- `0x1800089e0`
- `0x18000fb60`
- `0x180035ee0`
- `0x18003c460`
- `0x18003c640`
- `0x1800bdfd0`
- `0x1800cff90`
- `0x180112380`
- `0x1801123a8`
- `0x1801133b0`
- `0x1801ba152`
- `0x1801ba182`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800080ab`
- `msvcrt!_wcsnicmp` at `0x180008181`
- `msvcrt!_wcsnicmp` at `0x180008268`
- `msvcrt!_wcsnicmp` at `0x1800080ab`
- `msvcrt!_wcsnicmp` at `0x180008181`
- `msvcrt!_wcsnicmp` at `0x180008268`
- `msvcrt!_wcsicmp` at `0x1800081d3`
- `msvcrt!_wcsicmp` at `0x1800081d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800080f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800080f5`

## string_xrefs

- `0x18000804c`: `onecore\admin\wmi\wmx\config\configxmlvalidation.cpp`
- `0x18000817a`: `xmlns`
- `0x1800081c9`: `xmlns`
- `0x18000855c`: `xmlns`
- `0x18000857e`: `xmlns`
- `0x18000840c`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000845e`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000847f`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180008767`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000878f`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x1800086f0`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConfigValidateXMLElementAttributes(
        struct IRequestContext *a1,
        struct _CONFIGXML_ELEMENT *a2,
        struct _FWXML_ELEMENT *a3,
        const unsigned __int16 *a4)
{
  struct _FWXML_ELEMENT *v4; // r15
  struct IRequestContext *v6; // rsi
  __int64 v7; // rax
  const unsigned __int16 *v8; // r8
  __int64 v9; // rdx
  const wchar_t *v11; // rax
  size_t v12; // r8
  const wchar_t *v13; // r9
  unsigned int v14; // eax
  SIZE_T v15; // rax
  unsigned __int64 v16; // kr00_8
  unsigned int v17; // ebp
  void *v18; // r12
  unsigned int v19; // edi
  __int64 v20; // r15
  const wchar_t *v21; // rax
  const wchar_t **v22; // rcx
  __int64 v23; // rdx
  const wchar_t *v24; // rbx
  unsigned int v25; // esi
  __int64 v26; // r13
  const wchar_t *v27; // rdi
  __int64 v28; // r9
  __int64 v29; // rbx
  __int64 v30; // rax
  const wchar_t *v31; // rax
  size_t v32; // r8
  const wchar_t *v33; // r9
  int v34; // eax
  BOOL v35; // ecx
  const wchar_t **v36; // rax
  __int64 v37; // rcx
  const wchar_t *v38; // rax
  const wchar_t *v39; // rcx
  __int64 v40; // rdi
  void (__fastcall *v41)(struct IRequestContext *, __int64, __int64, _QWORD, __int64); // rbx
  __int64 v42; // rax
  _QWORD *v43; // rcx
  _QWORD *v44; // rcx
  __int64 v45; // rdx
  const unsigned __int16 *v46; // r8
  unsigned int i; // ebp
  struct IRequestContext *Attribute; // rsi
  wchar_t *AttributeNamespacePrefix; // rax
  void (__fastcall *v50)(struct IRequestContext *, __int64, __int64, __int64, __int64); // rdi
  __int64 ElementName; // rbx
  __int64 AttributeName; // rax
  __int64 v53; // rax
  __int64 v54; // rdx
  _QWORD *v55; // rcx
  __int64 v56; // rdx
  void (__fastcall *v57)(struct IRequestContext *, __int64, __int64, __int64, __int64); // rdi
  __int64 v58; // rbx
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 v62; // r9
  void (__fastcall *v63)(struct IRequestContext *, __int64, __int64, __int64, __int64); // rdi
  __int64 v64; // rbx
  __int64 v65; // rax
  __int64 v66; // rax
  int v67; // [rsp+30h] [rbp-58h]
  void *v68; // [rsp+38h] [rbp-50h]
  _QWORD v69[9]; // [rsp+40h] [rbp-48h] BYREF

  v4 = a3;
  v6 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids);
  if ( !v6 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", 597, L"597", 0x54Fu, 0);
    return 0;
  }
  if ( !a2 )
  {
    v8 = L"598";
    v9 = 598;
    goto LABEL_10;
  }
  if ( !v4 )
  {
    v8 = L"599";
    v9 = 599;
    goto LABEL_10;
  }
  if ( !*(_QWORD *)a2 )
  {
    v8 = L"601";
    v9 = 601;
    goto LABEL_10;
  }
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v7) );
  if ( *((_DWORD *)v4 + 4) != (_DWORD)v7
    || (v11 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v4),
        _wcsnicmp(v11, v13, v12)) )
  {
    v8 = L"602";
    v9 = 602;
LABEL_10:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", v9, v8, 0x54Fu, v6);
    return 0;
  }
  v14 = *((_DWORD *)a2 + 6);
  if ( !v14 )
  {
    if ( (unsigned int)FwXmlNumAttributes(v4) )
    {
      for ( i = 0; i < (unsigned int)FwXmlNumAttributes(v4); ++i )
      {
        Attribute = (struct IRequestContext *)FwXmlGetAttribute(v4, i);
        if ( !(unsigned int)FwXmlCompareAttributeName(Attribute, L"xmlns", 0, 1) )
        {
          AttributeNamespacePrefix = (wchar_t *)FwXmlGetAttributeNamespacePrefix(Attribute);
          if ( !(unsigned int)StringCchEqualsCI(AttributeNamespacePrefix, (wchar_t *)L"xmlns") )
          {
            v50 = *(void (__fastcall **)(struct IRequestContext *, __int64, __int64, __int64, __int64))(*(_QWORD *)a1 + 64LL);
            ElementName = FwXmlGetElementNameEx(v4);
            AttributeName = FwXmlGetAttributeNameEx(Attribute);
            v50(a1, 2150858819LL, 1077134522, AttributeName, ElementName);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              v53 = FwXmlGetAttributeNameEx(Attribute);
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids, v53);
            }
            return 0;
          }
        }
      }
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
        return 1;
      v54 = 30;
    }
    else
    {
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
        return 1;
      v54 = 31;
    }
    WPP_SF_(v44[2], v54, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids);
    return 1;
  }
  v16 = v14;
  v15 = 4LL * v14;
  if ( !is_mul_ok(v16, 4u) )
    v15 = -1;
  v17 = 0;
  if ( dword_18027FBEC != 2 )
  {
    if ( dword_18027FBEC == 4 )
    {
      v55 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000000) == 0 )
        goto LABEL_111;
      v56 = 10;
    }
    else if ( dword_18027FBEC == 8 )
    {
      v55 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000000) == 0 )
        goto LABEL_111;
      v56 = 11;
    }
    else
    {
      v55 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000000) == 0 )
        goto LABEL_111;
      v56 = 12;
    }
    WPP_SF_(v55[2], v56, WPP_9bd13fd0c4ba3d813d171a602a744429_Traceguids);
LABEL_111:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
    v18 = 0;
    goto LABEL_21;
  }
  if ( !g_wsManHeap )
    goto LABEL_111;
  v18 = HeapAlloc(g_wsManHeap, 0, v15);
LABEL_21:
  v68 = v18;
  v69[0] = v18;
  if ( !v18 )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)v6 + 24LL))(v6);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids, 14);
    goto LABEL_64;
  }
  v19 = 0;
  v67 = 0;
  memset_0(v18, 0, 4LL * *((unsigned int *)a2 + 6));
  while ( 1 )
  {
    if ( v19 >= *((_DWORD *)v4 + 28) )
    {
      while ( 1 )
      {
        if ( v17 >= *((_DWORD *)a2 + 6) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids);
          AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(v69);
          return 1;
        }
        if ( !*((_DWORD *)v18 + v17) )
        {
          v40 = *((_QWORD *)a2 + 2) + 40LL * v17;
          if ( *(_DWORD *)(v40 + 24) )
            break;
        }
        ++v17;
      }
      v41 = *(void (__fastcall **)(struct IRequestContext *, __int64, __int64, _QWORD, __int64))(*(_QWORD *)v6 + 64LL);
      v42 = FwXmlGetElementNameEx(v4);
      v41(v6, 2150858819LL, 1077134524, *(_QWORD *)v40, v42);
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      {
        v61 = 36;
        v62 = *(_QWORD *)v40;
        goto LABEL_128;
      }
      goto LABEL_64;
    }
    v20 = 104LL * v19 + *((_QWORD *)v4 + 15);
    if ( !v20 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 2092, L"2092", 0x80070057, 0);
      v45 = 1512;
      v46 = L"1512";
LABEL_75:
      v24 = 0;
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", v45, v46, 0x54Fu, 0);
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 139, L"139", 0x54Fu, 0);
      goto LABEL_36;
    }
    if ( *(_DWORD *)(v20 + 16) != 5 )
      break;
    v21 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v20);
    if ( _wcsnicmp(v21, L"xmlns", 5u) )
      break;
LABEL_61:
    v67 = ++v19;
    v4 = a3;
  }
  v22 = (const wchar_t **)(v20 + 24);
  if ( v20 == -24 )
  {
    v45 = 1536;
    v46 = L"1536";
    goto LABEL_75;
  }
  v23 = *(_QWORD *)(v20 + 32);
  if ( v23 != -1 )
  {
    if ( *v22 )
    {
      v24 = (const wchar_t *)(*(_QWORD *)*v22 + 2 * v23);
      goto LABEL_34;
    }
    goto LABEL_35;
  }
  v24 = *v22;
LABEL_34:
  if ( !v24 )
  {
LABEL_35:
    v24 = &Class;
    goto LABEL_36;
  }
  v24[*(unsigned int *)(v20 + 40)] = 0;
LABEL_36:
  if ( !_wcsicmp(v24, L"xmlns") )
    goto LABEL_61;
  v25 = 0;
  if ( !*((_DWORD *)a2 + 6) )
  {
LABEL_123:
    v63 = *(void (__fastcall **)(struct IRequestContext *, __int64, __int64, __int64, __int64))(*(_QWORD *)a1 + 64LL);
    v64 = FwXmlGetElementNameEx(a3);
    v65 = FwXmlGetAttributeNameEx((struct IRequestContext *)v20);
    v63(a1, 2150858819LL, 1077134522, v65, v64);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
      goto LABEL_64;
    v66 = FwXmlGetAttributeNameEx((struct IRequestContext *)v20);
    v61 = 33;
    v62 = v66;
    v43 = WPP_GLOBAL_Control;
LABEL_128:
    WPP_SF_S(v43[2], v61, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids, v62);
    goto LABEL_64;
  }
  while ( 2 )
  {
    v26 = *((_QWORD *)a2 + 2) + 40LL * v25;
    v27 = *(const wchar_t **)(v26 + 8);
    v28 = *(_QWORD *)v26;
    if ( v27 || (v27 = a4) != 0 )
    {
      v29 = -1;
      do
        ++v29;
      while ( v27[v29] );
    }
    else
    {
      LODWORD(v29) = 0;
    }
    v30 = -1;
    do
      ++v30;
    while ( *(_WORD *)(v28 + 2 * v30) );
    if ( !v20 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 2092, L"2092", 0x80070057, 0);
      goto LABEL_57;
    }
    if ( !v28 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 2097, L"2097", 0x80070057, 0);
      goto LABEL_57;
    }
    if ( *(_DWORD *)(v20 + 16) != (_DWORD)v30 )
      goto LABEL_57;
    v31 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v20);
    v34 = _wcsnicmp(v31, v33, v32);
    v35 = v34 == 0;
    if ( !v34 )
    {
      if ( !v27 )
        break;
      v36 = (const wchar_t **)(v20 + 48);
      if ( v20 == -48 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
        v35 = 0;
      }
      else if ( *(_DWORD *)(v20 + 64) == (_DWORD)v29 )
      {
        v37 = *(_QWORD *)(v20 + 56);
        if ( v37 == -1 )
        {
          v39 = *v36;
        }
        else
        {
          v38 = *v36;
          if ( v38 )
            v39 = (const wchar_t *)(*(_QWORD *)v38 + 2 * v37);
          else
            v39 = 0;
        }
        v35 = wcsncmp_0(v39, v27, (unsigned int)v29) == 0;
      }
      else
      {
        v35 = 0;
      }
    }
    if ( !v35 )
    {
LABEL_57:
      if ( ++v25 >= *((_DWORD *)a2 + 6) )
        break;
      continue;
    }
    break;
  }
  v18 = v68;
  v19 = v67;
  if ( v25 >= *((_DWORD *)a2 + 6) )
    goto LABEL_123;
  if ( *((_DWORD *)v68 + v25) )
  {
    v57 = *(void (__fastcall **)(struct IRequestContext *, __int64, __int64, __int64, __int64))(*(_QWORD *)a1 + 64LL);
    v58 = FwXmlGetElementNameEx(a3);
    v59 = FwXmlGetAttributeNameEx((struct IRequestContext *)v20);
    v57(a1, 2150858819LL, 1077134523, v59, v58);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
      goto LABEL_64;
    v60 = FwXmlGetAttributeNameEx((struct IRequestContext *)v20);
    v61 = 34;
    v62 = v60;
    v43 = WPP_GLOBAL_Control;
    goto LABEL_128;
  }
  *((_DWORD *)v68 + v25) = 1;
  v6 = a1;
  if ( (unsigned int)ValidateConfigXMLAttributeValue(
                       a1,
                       (struct _CONFIGXML_ATTRIBUTE *)v26,
                       (struct FWXML_ATTRIBUTE *)v20) )
    goto LABEL_61;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids);
LABEL_64:
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(v69);
  return 0;
}

```

## disassembly

```asm
0x180007fb0  mov     [rsp+arg_8], rbx
0x180007fb5  mov     [rsp+arg_18], r9
0x180007fba  mov     [rsp+arg_10], r8
0x180007fbf  mov     [rsp+arg_0], rcx
0x180007fc4  push    rbp
0x180007fc5  push    rsi
0x180007fc6  push    rdi
0x180007fc7  push    r12
0x180007fc9  push    r13
0x180007fcb  push    r14
0x180007fcd  push    r15
0x180007fcf  sub     rsp, 50h
0x180007fd3  mov     r15, r8
0x180007fd6  mov     r14, rdx
0x180007fd9  mov     rsi, rcx
0x180007fdc  lea     r13, WPP_GLOBAL_Control
0x180007fe3  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fea  cmp     rcx, r13
0x180007fed  jnz     loc_18000839B
0x180007ff3  test    rsi, rsi
0x180007ff6  jz      loc_1800084E9
0x180007ffc  test    r14, r14
0x180007fff  jz      loc_180008501
0x180008005  test    r15, r15
0x180008008  jz      loc_180008512
0x18000800e  mov     r9, [r14]
0x180008011  test    r9, r9
0x180008014  jz      loc_180008523
0x18000801a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180008021  mov     rax, rbx
0x180008024  inc     rax
0x180008027  cmp     word ptr [r9+rax*2], 0
0x18000802d  jnz     short loc_180008024
0x18000802f  cmp     [r15+10h], eax
0x180008033  jz      short loc_18000809A
0x180008035  lea     r8, a602; "602"
0x18000803c  mov     edx, 25Ah; unsigned int
0x180008041  mov     [rsp+88h+var_68], rsi; struct IRequestContext *
0x180008046  mov     r9d, 54Fh; unsigned int
0x18000804c  lea     rcx, aOnecoreAdminWm_113; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x180008053  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180008058  xor     eax, eax
0x18000805a  jmp     short loc_180008082
0x18000805c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008063  lea     rdx, WPP_GLOBAL_Control
0x18000806a  cmp     rcx, rdx
0x18000806d  jnz     loc_1800083C2
0x180008073  lea     rcx, [rsp+88h+var_48]
0x180008078  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18000807d  mov     eax, 1
0x180008082  mov     rbx, [rsp+88h+arg_8]
0x18000808a  add     rsp, 50h
0x18000808e  pop     r15
0x180008090  pop     r14
0x180008092  pop     r13
0x180008094  pop     r12
0x180008096  pop     rdi
0x180008097  pop     rsi
0x180008098  pop     rbp
0x180008099  retn
0x18000809a  mov     r8d, eax
0x18000809d  mov     rcx, r15
0x1800080a0  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x1800080a5  mov     rcx, rax; String1
0x1800080a8  mov     rdx, r9; String2
0x1800080ab  call    cs:__imp__wcsnicmp
0x1800080b1  test    eax, eax
0x1800080b3  jnz     short loc_180008035
0x1800080b5  mov     eax, [r14+18h]
0x1800080b9  test    eax, eax
0x1800080bb  jz      loc_18000841D
0x1800080c1  mov     ecx, eax
0x1800080c3  mov     eax, 4
0x1800080c8  mul     rcx
0x1800080cb  cmovb   rax, rbx
0x1800080cf  xor     ebp, ebp
0x1800080d1  mov     ecx, cs:dword_18027FBEC
0x1800080d7  cmp     ecx, 2
0x1800080da  jnz     loc_18000866D
0x1800080e0  mov     rcx, cs:?g_wsManHeap@@3VCHeap@@A; hHeap
0x1800080e7  test    rcx, rcx
0x1800080ea  jz      loc_1800086D9
0x1800080f0  mov     r8, rax; dwBytes
0x1800080f3  xor     edx, edx; dwFlags
0x1800080f5  call    cs:__imp_HeapAlloc
0x1800080fb  mov     r12, rax
0x1800080fe  mov     [rsp+88h+var_50], r12
0x180008103  mov     [rsp+88h+var_48], r12
0x180008108  test    r12, r12
0x18000810b  jz      loc_180008704
0x180008111  mov     r13, rbp
0x180008114  mov     edi, ebp
0x180008116  mov     [rsp+88h+var_58], ebp
0x18000811a  mov     r8d, [r14+18h]
0x18000811e  shl     r8, 2; Size
0x180008122  xor     edx, edx; Val
0x180008124  mov     rcx, r12; void *
0x180008127  call    memset_0
0x18000812c  cmp     edi, [r15+70h]
0x180008130  jb      short loc_18000814F
0x180008132  mov     edx, [r14+18h]
0x180008136  cmp     ebp, edx
0x180008138  jnb     loc_18000805C
0x18000813e  mov     eax, ebp
0x180008140  cmp     dword ptr [r12+rax*4], 0
0x180008145  jz      loc_180008330
0x18000814b  inc     ebp
0x18000814d  jmp     short loc_180008136
0x18000814f  mov     eax, edi
0x180008151  imul    rcx, rax, 68h ; 'h'
0x180008155  mov     r15, [r15+78h]
0x180008159  add     r15, rcx
0x18000815c  jz      loc_180008447
0x180008162  cmp     dword ptr [r15+10h], 5
0x180008167  jnz     short loc_18000818F
0x180008169  mov     rcx, r15
0x18000816c  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180008171  mov     rcx, rax; String1
0x180008174  mov     r8d, 5; MaxCount
0x18000817a  lea     rdx, aXmlns_2; "xmlns"
0x180008181  call    cs:__imp__wcsnicmp
0x180008187  test    eax, eax
0x180008189  jz      loc_18000831D
0x18000818f  lea     rcx, [r15+18h]
0x180008193  test    rcx, rcx
0x180008196  jz      loc_1800084BB
0x18000819c  mov     rdx, [rcx+8]
0x1800081a0  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800081a4  jz      loc_1800084D1
0x1800081aa  mov     rax, [rcx]
0x1800081ad  test    rax, rax
0x1800081b0  jz      short loc_1800081C2
0x1800081b2  mov     rax, [rax]
0x1800081b5  lea     rbx, [rax+rdx*2]
0x1800081b9  test    rbx, rbx
0x1800081bc  jnz     loc_1800083E9
0x1800081c2  lea     rbx, Class
0x1800081c9  lea     rdx, aXmlns_2; "xmlns"
0x1800081d0  mov     rcx, rbx; String1
0x1800081d3  call    cs:__imp__wcsicmp
0x1800081d9  test    eax, eax
0x1800081db  jz      loc_18000831D
0x1800081e1  mov     esi, ebp
0x1800081e3  cmp     ebp, [r14+18h]
0x1800081e7  jnb     loc_180008865
0x1800081ed  mov     r12, [rsp+88h+arg_18]
0x1800081f5  mov     eax, esi
0x1800081f7  lea     rcx, [rax+rax*4]
0x1800081fb  mov     rax, [r14+10h]
0x1800081ff  lea     r13, [rax+rcx*8]
0x180008203  mov     rdi, [r13+8]
0x180008207  mov     r9, [r13+0]
0x18000820b  test    rdi, rdi
0x18000820e  jnz     short loc_18000821C
0x180008210  mov     rdi, r12
0x180008213  test    r12, r12
0x180008216  jz      loc_1800084C9
0x18000821c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180008223  inc     rbx
0x180008226  cmp     word ptr [rdi+rbx*2], 0
0x18000822b  jnz     short loc_180008223
0x18000822d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008234  inc     rax
0x180008237  cmp     word ptr [r9+rax*2], 0
0x18000823d  jnz     short loc_180008234
0x18000823f  test    r15, r15
0x180008242  jz      loc_1800083F5
0x180008248  test    r9, r9
0x18000824b  jz      loc_180008750
0x180008251  cmp     [r15+10h], eax
0x180008255  jnz     short loc_1800082CB
0x180008257  mov     r8d, eax
0x18000825a  mov     rcx, r15
0x18000825d  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180008262  mov     rcx, rax; String1
0x180008265  mov     rdx, r9; String2
0x180008268  call    cs:__imp__wcsnicmp
0x18000826e  mov     ecx, ebp
0x180008270  test    eax, eax
0x180008272  setz    cl
0x180008275  test    eax, eax
0x180008277  jnz     short loc_1800082C7
0x180008279  test    rdi, rdi
0x18000827c  jz      short loc_1800082D7
0x18000827e  lea     rax, [r15+30h]
0x180008282  test    rax, rax
0x180008285  jz      loc_180008778
0x18000828b  cmp     [rax+10h], ebx
0x18000828e  jz      short loc_180008294
0x180008290  mov     ecx, ebp
0x180008292  jmp     short loc_1800082C7
0x180008294  mov     rcx, [rax+8]
0x180008298  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000829c  jz      loc_1800084D9
0x1800082a2  mov     rax, [rax]
0x1800082a5  test    rax, rax
0x1800082a8  jz      loc_1800084E1
0x1800082ae  mov     rax, [rax]
0x1800082b1  lea     rcx, [rax+rcx*2]; String1
0x1800082b5  mov     r8d, ebx; MaxCount
0x1800082b8  mov     rdx, rdi; String2
0x1800082bb  call    wcsncmp_0
0x1800082c0  mov     ecx, ebp
0x1800082c2  test    eax, eax
0x1800082c4  setz    cl
0x1800082c7  test    ecx, ecx
0x1800082c9  jnz     short loc_1800082D7
0x1800082cb  inc     esi
0x1800082cd  cmp     esi, [r14+18h]
0x1800082d1  jb      loc_1800081F5
0x1800082d7  mov     r12, [rsp+88h+var_50]
0x1800082dc  mov     edi, [rsp+88h+var_58]
0x1800082e0  cmp     esi, [r14+18h]
0x1800082e4  jnb     loc_180008865
0x1800082ea  mov     eax, esi
0x1800082ec  cmp     dword ptr [r12+rax*4], 0
0x1800082f1  jnz     loc_1800087E0
0x1800082f7  mov     dword ptr [r12+rax*4], 1
0x1800082ff  mov     r8, r15; struct FWXML_ATTRIBUTE *
0x180008302  mov     rdx, r13; struct _CONFIGXML_ATTRIBUTE *
0x180008305  mov     rsi, [rsp+88h+arg_0]
0x18000830d  mov     rcx, rsi; struct IRequestContext *
0x180008310  call    ?ValidateConfigXMLAttributeValue@@YAHPEAVIRequestContext@@PEAU_CONFIGXML_ATTRIBUTE@@PEAUFWXML_ATTRIBUTE@@@Z; ValidateConfigXMLAttributeValue(IRequestContext *,_CONFIGXML_ATTRIBUTE *,FWXML_ATTRIBUTE *)
0x180008315  test    eax, eax
0x180008317  jz      loc_1800087A2
0x18000831d  inc     edi
0x18000831f  mov     [rsp+88h+var_58], edi
0x180008323  mov     r15, [rsp+88h+arg_10]
0x18000832b  jmp     loc_18000812C
0x180008330  lea     rcx, [rax+rax*4]
0x180008334  mov     rax, [r14+10h]
0x180008338  lea     rdi, [rax+rcx*8]
0x18000833c  cmp     dword ptr [rdi+18h], 0
0x180008340  jz      loc_18000814B
0x180008346  mov     rax, [rsi]
0x180008349  mov     rbx, [rax+40h]
0x18000834d  mov     rcx, r15; struct IRequestContext *
0x180008350  call    FwXmlGetElementNameEx
0x180008355  mov     [rsp+88h+var_68], rax
0x18000835a  mov     r9, [rdi]
0x18000835d  mov     edx, 80338043h
0x180008362  mov     r8d, 4033C4BCh
0x180008368  mov     rcx, rsi
0x18000836b  mov     rax, rbx
0x18000836e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008373  mov     rcx, cs:WPP_GLOBAL_Control
0x18000837a  lea     rdx, WPP_GLOBAL_Control
0x180008381  cmp     rcx, rdx
0x180008384  jnz     loc_1800088E7
0x18000838a  lea     rcx, [rsp+88h+var_48]
0x18000838f  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180008394  xor     eax, eax
0x180008396  jmp     loc_180008082
0x18000839b  test    dword ptr [rcx+1Ch], 200000h
0x1800083a2  jz      loc_180007FF3
0x1800083a8  mov     edx, 1Ch
0x1800083ad  lea     r8, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids
0x1800083b4  mov     rcx, [rcx+10h]
0x1800083b8  call    WPP_SF_
0x1800083bd  jmp     loc_180007FF3
0x1800083c2  test    dword ptr [rcx+1Ch], 200000h
0x1800083c9  jz      loc_180008073
0x1800083cf  mov     edx, 25h ; '%'
0x1800083d4  lea     r8, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids
0x1800083db  mov     rcx, [rcx+10h]
0x1800083df  call    WPP_SF_
0x1800083e4  jmp     loc_180008073
0x1800083e9  mov     eax, [rcx+10h]
0x1800083ec  mov     [rbx+rax*2], bp
0x1800083f0  jmp     loc_1800081C9
0x1800083f5  mov     [rsp+88h+var_68], rbp; struct IRequestContext *
0x1800083fa  mov     r9d, 80070057h; unsigned int
0x180008400  lea     r8, a2092; "2092"
0x180008407  mov     edx, 82Ch; unsigned int
0x18000840c  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x180008413  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180008418  jmp     loc_1800082CB
0x18000841d  mov     rcx, r15
0x180008420  call    FwXmlNumAttributes
0x180008425  test    eax, eax
0x180008427  jnz     loc_180008534
0x18000842d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008434  cmp     rcx, r13
0x180008437  jnz     loc_180008646
0x18000843d  mov     eax, 1
0x180008442  jmp     loc_180008082
0x180008447  mov     [rsp+88h+var_68], rbp; struct IRequestContext *
0x18000844c  mov     r9d, 80070057h; unsigned int
0x180008452  lea     r8, a2092; "2092"
0x180008459  mov     edx, 82Ch; unsigned int
0x18000845e  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x180008465  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18000846a  mov     edx, 5E8h; unsigned int
0x18000846f  lea     r8, a1512; "1512"
0x180008476  mov     rax, rbp
0x180008479  mov     r9d, 54Fh; unsigned int
0x18000847f  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x180008486  mov     rbx, rbp
0x180008489  mov     [rsp+88h+var_68], rax; struct IRequestContext *
0x18000848e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
  ... truncated ...
```
