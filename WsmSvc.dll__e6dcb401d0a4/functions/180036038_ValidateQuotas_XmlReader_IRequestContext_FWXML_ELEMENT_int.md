# ValidateQuotas(XmlReader *,IRequestContext *,_FWXML_ELEMENT *,int)

- ea: `0x180036038`
- end: `0x18003685c`
- name: `?ValidateQuotas@@YA_NPEAVXmlReader@@PEAVIRequestContext@@PEAU_FWXML_ELEMENT@@H@Z`
- size: `2084`
- prototype: `bool(struct XmlReader *, struct IRequestContext *, struct _FWXML_ELEMENT *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036de0`

## callees

- `0x180005d10`
- `0x180034d1c`
- `0x180036038`
- `0x18003c640`
- `0x1801133b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800360ac`
- `msvcrt!_wcsnicmp` at `0x18003618c`
- `msvcrt!_wcsnicmp` at `0x18003626c`
- `msvcrt!_wcsnicmp` at `0x18003634c`
- `msvcrt!_wcsnicmp` at `0x18003642c`
- `msvcrt!_wcsnicmp` at `0x18003650c`
- `msvcrt!_wcsnicmp` at `0x1800365ec`
- `msvcrt!_wcsnicmp` at `0x1800366cc`
- `msvcrt!_wcsnicmp` at `0x1800367ae`
- `msvcrt!_wcsnicmp` at `0x1800360ac`
- `msvcrt!_wcsnicmp` at `0x18003618c`
- `msvcrt!_wcsnicmp` at `0x18003626c`
- `msvcrt!_wcsnicmp` at `0x18003634c`
- `msvcrt!_wcsnicmp` at `0x18003642c`
- `msvcrt!_wcsnicmp` at `0x18003650c`
- `msvcrt!_wcsnicmp` at `0x1800365ec`
- `msvcrt!_wcsnicmp` at `0x1800366cc`
- `msvcrt!_wcsnicmp` at `0x1800367ae`

## string_xrefs

- `0x1800363d7`: `MaxConcurrentCommandsPerShell`
- `0x18003607f`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003615f`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003623f`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003631f`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x1800363ff`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x1800364df`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x1800365bf`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003669f`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180036781`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`

## pseudocode

```c
bool __fastcall ValidateQuotas(struct XmlReader *a1, struct IRequestContext *a2, struct _FWXML_ELEMENT *a3, int a4)
{
  char *v5; // rbx
  const wchar_t *v7; // r15
  int i; // edi
  __int64 v9; // rcx
  const wchar_t *v10; // rax
  PVOID *v11; // rcx
  __int64 v12; // rdx
  int v13; // edi
  __int64 v14; // rcx
  const wchar_t *v15; // rax
  int v16; // edi
  __int64 v17; // rcx
  const wchar_t *v18; // rax
  int v19; // edi
  __int64 v20; // rcx
  const wchar_t *v21; // rax
  int v22; // edi
  __int64 v23; // rcx
  const wchar_t *v24; // rax
  int v25; // edi
  __int64 v26; // rcx
  const wchar_t *v27; // rax
  int v28; // edi
  __int64 v29; // rcx
  const wchar_t *v30; // rax
  int v31; // edi
  __int64 v32; // rcx
  const wchar_t *v33; // rax
  int v34; // edi
  __int64 v35; // rcx
  const wchar_t *v36; // rax

  v5 = (char *)a3 + 112;
  v7 = L"IdleTimeoutms";
  for ( i = 0; i != *(_DWORD *)v5; ++i )
  {
    v9 = *((_QWORD *)v5 + 1) + 104LL * i;
    if ( v9 )
    {
      if ( *(_DWORD *)(v9 + 16) == 13 )
      {
        v10 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v9);
        if ( !_wcsnicmp(v10, L"IdleTimeoutms", 0xDu) )
        {
          if ( !a4 )
          {
            (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
              a2,
              2150858819LL,
              1077134586,
              L"IdleTimeoutms");
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return 0;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                75,
                WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids,
                L"IdleTimeoutms");
              v11 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v11 == &WPP_GLOBAL_Control || (*((_DWORD *)v11 + 7) & 0x200000) == 0 )
              return 0;
            v12 = 76;
            goto LABEL_127;
          }
          break;
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    }
  }
  v13 = 0;
  v7 = L"MaxIdleTimeoutms";
  while ( v13 != *(_DWORD *)v5 )
  {
    v14 = *((_QWORD *)v5 + 1) + 104LL * v13;
    if ( v14 )
    {
      if ( *(_DWORD *)(v14 + 16) == 16 )
      {
        v15 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v14);
        if ( !_wcsnicmp(v15, L"MaxIdleTimeoutms", 0x10u) )
        {
          if ( !a4 )
          {
            (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
              a2,
              2150858819LL,
              1077134586,
              L"MaxIdleTimeoutms");
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return 0;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                75,
                WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids,
                L"MaxIdleTimeoutms");
              v11 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v11 == &WPP_GLOBAL_Control || (*((_DWORD *)v11 + 7) & 0x200000) == 0 )
              return 0;
            v12 = 77;
            goto LABEL_127;
          }
          break;
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    }
    ++v13;
  }
  v16 = 0;
  v7 = L"MaxProcessesPerShell";
  while ( v16 != *(_DWORD *)v5 )
  {
    v17 = *((_QWORD *)v5 + 1) + 104LL * v16;
    if ( v17 )
    {
      if ( *(_DWORD *)(v17 + 16) == 20 )
      {
        v18 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v17);
        if ( !_wcsnicmp(v18, L"MaxProcessesPerShell", 0x14u) )
        {
          if ( !a4 )
          {
            (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
              a2,
              2150858819LL,
              1077134586,
              L"MaxProcessesPerShell");
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return 0;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                75,
                WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids,
                L"MaxProcessesPerShell");
              v11 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v11 == &WPP_GLOBAL_Control || (*((_DWORD *)v11 + 7) & 0x200000) == 0 )
              return 0;
            v12 = 78;
            goto LABEL_127;
          }
          break;
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    }
    ++v16;
  }
  v19 = 0;
  v7 = L"MaxMemoryPerShellMB";
  while ( v19 != *(_DWORD *)v5 )
  {
    v20 = *((_QWORD *)v5 + 1) + 104LL * v19;
    if ( v20 )
    {
      if ( *(_DWORD *)(v20 + 16) == 19 )
      {
        v21 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v20);
        if ( !_wcsnicmp(v21, L"MaxMemoryPerShellMB", 0x13u) )
        {
          if ( !a4 )
          {
            (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
              a2,
              2150858819LL,
              1077134586,
              L"MaxMemoryPerShellMB");
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return 0;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                75,
                WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids,
                L"MaxMemoryPerShellMB");
              v11 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v11 == &WPP_GLOBAL_Control || (*((_DWORD *)v11 + 7) & 0x200000) == 0 )
              return 0;
            v12 = 79;
            goto LABEL_127;
          }
          break;
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    }
    ++v19;
  }
  v22 = 0;
  v7 = L"MaxConcurrentCommandsPerShell";
  while ( v22 != *(_DWORD *)v5 )
  {
    v23 = *((_QWORD *)v5 + 1) + 104LL * v22;
    if ( v23 )
    {
      if ( *(_DWORD *)(v23 + 16) == 29 )
      {
        v24 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v23);
        if ( !_wcsnicmp(v24, L"MaxConcurrentCommandsPerShell", 0x1Du) )
        {
          if ( !a4 )
          {
            (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
              a2,
              2150858819LL,
              1077134586,
              L"MaxConcurrentCommandsPerShell");
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return 0;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                75,
                WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids,
                L"MaxConcurrentCommandsPerShell");
              v11 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v11 == &WPP_GLOBAL_Control || (*((_DWORD *)v11 + 7) & 0x200000) == 0 )
              return 0;
            v12 = 80;
            goto LABEL_127;
          }
          break;
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    }
    ++v22;
  }
  v25 = 0;
  v7 = L"MaxShells";
  while ( v25 != *(_DWORD *)v5 )
  {
    v26 = *((_QWORD *)v5 + 1) + 104LL * v25;
    if ( v26 )
    {
      if ( *(_DWORD *)(v26 + 16) == 9 )
      {
        v27 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v26);
        if ( !_wcsnicmp(v27, L"MaxShells", 9u) )
        {
          if ( !a4 )
          {
            (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
              a2,
              2150858819LL,
              1077134586,
              L"MaxShells");
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return 0;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                75,
                WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids,
                L"MaxShells");
              v11 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v11 == &WPP_GLOBAL_Control || (*((_DWORD *)v11 + 7) & 0x200000) == 0 )
              return 0;
            v12 = 81;
            goto LABEL_127;
          }
          break;
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    }
    ++v25;
  }
  v28 = 0;
  v7 = L"MaxShellsPerUser";
  while ( v28 != *(_DWORD *)v5 )
  {
    v29 = *((_QWORD *)v5 + 1) + 104LL * v28;
    if ( v29 )
    {
      if ( *(_DWORD *)(v29 + 16) == 16 )
      {
        v30 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v29);
        if ( !_wcsnicmp(v30, L"MaxShellsPerUser", 0x10u) )
        {
          if ( !a4 )
          {
            (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
              a2,
              2150858819LL,
              1077134586,
              L"MaxShellsPerUser");
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return 0;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                75,
                WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids,
                L"MaxShellsPerUser");
              v11 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v11 == &WPP_GLOBAL_Control || (*((_DWORD *)v11 + 7) & 0x200000) == 0 )
              return 0;
            v12 = 82;
            goto LABEL_127;
          }
          break;
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    }
    ++v28;
  }
  v31 = 0;
  v7 = L"MaxConcurrentOperationsPerUser";
  while ( 1 )
  {
    if ( v31 == *(_DWORD *)v5 )
      goto LABEL_113;
    v32 = *((_QWORD *)v5 + 1) + 104LL * v31;
    if ( !v32 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
      goto LABEL_105;
    }
    if ( *(_DWORD *)(v32 + 16) == 30 )
    {
      v33 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v32);
      if ( !_wcsnicmp(v33, L"MaxConcurrentOperationsPerUser", 0x1Eu) )
        break;
    }
LABEL_105:
    ++v31;
  }
  if ( a4 )
  {
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
      a2,
      2150858819LL,
      1077134586,
      L"MaxConcurrentOperationsPerUser");
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return 0;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids,
        L"MaxConcurrentOperationsPerUser");
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 == &WPP_GLOBAL_Control || (*((_DWORD *)v11 + 7) & 0x200000) == 0 )
      return 0;
    v12 = 83;
LABEL_127:
    WPP_SF_S(v11[2], v12, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids, v7);
    return 0;
  }
LABEL_113:
  v34 = 0;
  v7 = L"MaxConcurrentOperations";
  while ( 2 )
  {
    if ( v34 == *(_DWORD *)v5 )
      return ValidateIdleTimeOutCombination(a2, (struct FWXML_ATTRIBUTE_LIST *)v5);
    v35 = *((_QWORD *)v5 + 1) + 104LL * v34;
    if ( !v35 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
LABEL_119:
      ++v34;
      continue;
    }
    break;
  }
  if ( *(_DWORD *)(v35 + 16) != 23 )
    goto LABEL_119;
  v36 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v35);
  if ( _wcsnicmp(v36, L"MaxConcurrentOperations", 0x17u) )
    goto LABEL_119;
  if ( !a4 )
    return ValidateIdleTimeOutCombination(a2, (struct FWXML_ATTRIBUTE_LIST *)v5);
  (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
    a2,
    2150858819LL,
    1077134586,
    L"MaxConcurrentOperations");
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids,
        L"MaxConcurrentOperations");
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x200000) != 0 )
    {
      v12 = 84;
      goto LABEL_127;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180036038  push    rbx
0x18003603a  push    rbp
0x18003603b  push    rsi
0x18003603c  push    rdi
0x18003603d  push    r13
0x18003603f  push    r15
0x180036041  sub     rsp, 38h
0x180036045  mov     ebp, r9d
0x180036048  lea     rbx, [r8+70h]
0x18003604c  mov     rsi, rdx
0x18003604f  lea     r15, aIdletimeoutms; "IdleTimeoutms"
0x180036056  xor     edi, edi
0x180036058  mov     r13d, 54Fh
0x18003605e  cmp     edi, [rbx]
0x180036060  jz      loc_180036135
0x180036066  movsxd  rax, edi
0x180036069  imul    rcx, rax, 68h ; 'h'
0x18003606d  add     rcx, [rbx+8]
0x180036071  jnz     short loc_180036095
0x180036073  mov     [rsp+68h+var_48], rcx; struct IRequestContext *
0x180036078  lea     r8, a522; "522"
0x18003607f  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x180036086  mov     r9d, r13d; unsigned int
0x180036089  mov     edx, 20Ah; unsigned int
0x18003608e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180036093  jmp     short loc_1800360B6
0x180036095  cmp     dword ptr [rcx+10h], 0Dh
0x180036099  jnz     short loc_1800360B6
0x18003609b  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x1800360a0  mov     rcx, rax; String1
0x1800360a3  mov     rdx, r15; String2
0x1800360a6  mov     r8d, 0Dh; MaxCount
0x1800360ac  call    cs:__imp__wcsnicmp
0x1800360b2  test    eax, eax
0x1800360b4  jz      short loc_1800360BA
0x1800360b6  inc     edi
0x1800360b8  jmp     short loc_18003605E
0x1800360ba  test    ebp, ebp
0x1800360bc  jnz     short loc_180036135
0x1800360be  mov     rax, [rsi]
0x1800360c1  mov     r9, r15
0x1800360c4  mov     edx, 80338043h
0x1800360c9  mov     r8d, 4033C4FAh
0x1800360cf  mov     rcx, rsi
0x1800360d2  mov     rax, [rax+40h]
0x1800360d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800360e2  lea     rdi, WPP_GLOBAL_Control
0x1800360e9  mov     ebx, 200000h
0x1800360ee  cmp     rcx, rdi
0x1800360f1  jz      loc_18003683B
0x1800360f7  test    [rcx+1Ch], ebx
0x1800360fa  jz      short loc_180036119
0x1800360fc  mov     rcx, [rcx+10h]
0x180036100  lea     edx, [rbp+4Bh]
0x180036103  mov     r9, r15
0x180036106  lea     r8, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids
0x18003610d  call    WPP_SF_S
0x180036112  mov     rcx, cs:WPP_GLOBAL_Control
0x180036119  cmp     rcx, rdi
0x18003611c  jz      loc_18003683B
0x180036122  test    [rcx+1Ch], ebx
0x180036125  jz      loc_18003683B
0x18003612b  mov     edx, 4Ch ; 'L'
0x180036130  jmp     loc_180036828
0x180036135  xor     edi, edi
0x180036137  lea     r15, aMaxidletimeout_0; "MaxIdleTimeoutms"
0x18003613e  cmp     edi, [rbx]
0x180036140  jz      loc_180036215
0x180036146  movsxd  rax, edi
0x180036149  imul    rcx, rax, 68h ; 'h'
0x18003614d  add     rcx, [rbx+8]
0x180036151  jnz     short loc_180036175
0x180036153  mov     [rsp+68h+var_48], rcx; struct IRequestContext *
0x180036158  lea     r8, a522; "522"
0x18003615f  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x180036166  mov     r9d, r13d; unsigned int
0x180036169  mov     edx, 20Ah; unsigned int
0x18003616e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180036173  jmp     short loc_180036196
0x180036175  cmp     dword ptr [rcx+10h], 10h
0x180036179  jnz     short loc_180036196
0x18003617b  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180036180  mov     rcx, rax; String1
0x180036183  mov     rdx, r15; String2
0x180036186  mov     r8d, 10h; MaxCount
0x18003618c  call    cs:__imp__wcsnicmp
0x180036192  test    eax, eax
0x180036194  jz      short loc_18003619A
0x180036196  inc     edi
0x180036198  jmp     short loc_18003613E
0x18003619a  test    ebp, ebp
0x18003619c  jnz     short loc_180036215
0x18003619e  mov     rax, [rsi]
0x1800361a1  mov     r9, r15
0x1800361a4  mov     edx, 80338043h
0x1800361a9  mov     r8d, 4033C4FAh
0x1800361af  mov     rcx, rsi
0x1800361b2  mov     rax, [rax+40h]
0x1800361b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800361c2  lea     rdi, WPP_GLOBAL_Control
0x1800361c9  mov     ebx, 200000h
0x1800361ce  cmp     rcx, rdi
0x1800361d1  jz      loc_18003683B
0x1800361d7  test    [rcx+1Ch], ebx
0x1800361da  jz      short loc_1800361F9
0x1800361dc  mov     rcx, [rcx+10h]
0x1800361e0  lea     edx, [rbp+4Bh]
0x1800361e3  mov     r9, r15
0x1800361e6  lea     r8, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids
0x1800361ed  call    WPP_SF_S
0x1800361f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800361f9  cmp     rcx, rdi
0x1800361fc  jz      loc_18003683B
0x180036202  test    [rcx+1Ch], ebx
0x180036205  jz      loc_18003683B
0x18003620b  mov     edx, 4Dh ; 'M'
0x180036210  jmp     loc_180036828
0x180036215  xor     edi, edi
0x180036217  lea     r15, aMaxprocessespe; "MaxProcessesPerShell"
0x18003621e  cmp     edi, [rbx]
0x180036220  jz      loc_1800362F5
0x180036226  movsxd  rax, edi
0x180036229  imul    rcx, rax, 68h ; 'h'
0x18003622d  add     rcx, [rbx+8]
0x180036231  jnz     short loc_180036255
0x180036233  mov     [rsp+68h+var_48], rcx; struct IRequestContext *
0x180036238  lea     r8, a522; "522"
0x18003623f  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x180036246  mov     r9d, r13d; unsigned int
0x180036249  mov     edx, 20Ah; unsigned int
0x18003624e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180036253  jmp     short loc_180036276
0x180036255  cmp     dword ptr [rcx+10h], 14h
0x180036259  jnz     short loc_180036276
0x18003625b  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180036260  mov     rcx, rax; String1
0x180036263  mov     rdx, r15; String2
0x180036266  mov     r8d, 14h; MaxCount
0x18003626c  call    cs:__imp__wcsnicmp
0x180036272  test    eax, eax
0x180036274  jz      short loc_18003627A
0x180036276  inc     edi
0x180036278  jmp     short loc_18003621E
0x18003627a  test    ebp, ebp
0x18003627c  jnz     short loc_1800362F5
0x18003627e  mov     rax, [rsi]
0x180036281  mov     r9, r15
0x180036284  mov     edx, 80338043h
0x180036289  mov     r8d, 4033C4FAh
0x18003628f  mov     rcx, rsi
0x180036292  mov     rax, [rax+40h]
0x180036296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003629b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362a2  lea     rdi, WPP_GLOBAL_Control
0x1800362a9  mov     ebx, 200000h
0x1800362ae  cmp     rcx, rdi
0x1800362b1  jz      loc_18003683B
0x1800362b7  test    [rcx+1Ch], ebx
0x1800362ba  jz      short loc_1800362D9
0x1800362bc  mov     rcx, [rcx+10h]
0x1800362c0  lea     edx, [rbp+4Bh]
0x1800362c3  mov     r9, r15
0x1800362c6  lea     r8, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids
0x1800362cd  call    WPP_SF_S
0x1800362d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362d9  cmp     rcx, rdi
0x1800362dc  jz      loc_18003683B
0x1800362e2  test    [rcx+1Ch], ebx
0x1800362e5  jz      loc_18003683B
0x1800362eb  mov     edx, 4Eh ; 'N'
0x1800362f0  jmp     loc_180036828
0x1800362f5  xor     edi, edi
0x1800362f7  lea     r15, aMaxmemorypersh; "MaxMemoryPerShellMB"
0x1800362fe  cmp     edi, [rbx]
0x180036300  jz      loc_1800363D5
0x180036306  movsxd  rax, edi
0x180036309  imul    rcx, rax, 68h ; 'h'
0x18003630d  add     rcx, [rbx+8]
0x180036311  jnz     short loc_180036335
0x180036313  mov     [rsp+68h+var_48], rcx; struct IRequestContext *
0x180036318  lea     r8, a522; "522"
0x18003631f  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x180036326  mov     r9d, r13d; unsigned int
0x180036329  mov     edx, 20Ah; unsigned int
0x18003632e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180036333  jmp     short loc_180036356
0x180036335  cmp     dword ptr [rcx+10h], 13h
0x180036339  jnz     short loc_180036356
0x18003633b  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180036340  mov     rcx, rax; String1
0x180036343  mov     rdx, r15; String2
0x180036346  mov     r8d, 13h; MaxCount
0x18003634c  call    cs:__imp__wcsnicmp
0x180036352  test    eax, eax
0x180036354  jz      short loc_18003635A
0x180036356  inc     edi
0x180036358  jmp     short loc_1800362FE
0x18003635a  test    ebp, ebp
0x18003635c  jnz     short loc_1800363D5
0x18003635e  mov     rax, [rsi]
0x180036361  mov     r9, r15
0x180036364  mov     edx, 80338043h
0x180036369  mov     r8d, 4033C4FAh
0x18003636f  mov     rcx, rsi
0x180036372  mov     rax, [rax+40h]
0x180036376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003637b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036382  lea     rdi, WPP_GLOBAL_Control
0x180036389  mov     ebx, 200000h
0x18003638e  cmp     rcx, rdi
0x180036391  jz      loc_18003683B
0x180036397  test    [rcx+1Ch], ebx
0x18003639a  jz      short loc_1800363B9
0x18003639c  mov     rcx, [rcx+10h]
0x1800363a0  lea     edx, [rbp+4Bh]
0x1800363a3  mov     r9, r15
0x1800363a6  lea     r8, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids
0x1800363ad  call    WPP_SF_S
0x1800363b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800363b9  cmp     rcx, rdi
0x1800363bc  jz      loc_18003683B
0x1800363c2  test    [rcx+1Ch], ebx
0x1800363c5  jz      loc_18003683B
0x1800363cb  mov     edx, 4Fh ; 'O'
0x1800363d0  jmp     loc_180036828
0x1800363d5  xor     edi, edi
0x1800363d7  lea     r15, aMaxconcurrentc; "MaxConcurrentCommandsPerShell"
0x1800363de  cmp     edi, [rbx]
0x1800363e0  jz      loc_1800364B5
0x1800363e6  movsxd  rax, edi
0x1800363e9  imul    rcx, rax, 68h ; 'h'
0x1800363ed  add     rcx, [rbx+8]
0x1800363f1  jnz     short loc_180036415
0x1800363f3  mov     [rsp+68h+var_48], rcx; struct IRequestContext *
0x1800363f8  lea     r8, a522; "522"
0x1800363ff  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x180036406  mov     r9d, r13d; unsigned int
0x180036409  mov     edx, 20Ah; unsigned int
0x18003640e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180036413  jmp     short loc_180036436
0x180036415  cmp     dword ptr [rcx+10h], 1Dh
0x180036419  jnz     short loc_180036436
0x18003641b  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180036420  mov     rcx, rax; String1
0x180036423  mov     rdx, r15; String2
0x180036426  mov     r8d, 1Dh; MaxCount
0x18003642c  call    cs:__imp__wcsnicmp
0x180036432  test    eax, eax
0x180036434  jz      short loc_18003643A
0x180036436  inc     edi
0x180036438  jmp     short loc_1800363DE
0x18003643a  test    ebp, ebp
0x18003643c  jnz     short loc_1800364B5
0x18003643e  mov     rax, [rsi]
0x180036441  mov     r9, r15
0x180036444  mov     edx, 80338043h
0x180036449  mov     r8d, 4033C4FAh
0x18003644f  mov     rcx, rsi
0x180036452  mov     rax, [rax+40h]
0x180036456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003645b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036462  lea     rdi, WPP_GLOBAL_Control
0x180036469  mov     ebx, 200000h
0x18003646e  cmp     rcx, rdi
0x180036471  jz      loc_18003683B
0x180036477  test    [rcx+1Ch], ebx
0x18003647a  jz      short loc_180036499
0x18003647c  mov     rcx, [rcx+10h]
0x180036480  lea     edx, [rbp+4Bh]
0x180036483  mov     r9, r15
0x180036486  lea     r8, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids
0x18003648d  call    WPP_SF_S
0x180036492  mov     rcx, cs:WPP_GLOBAL_Control
0x180036499  cmp     rcx, rdi
0x18003649c  jz      loc_18003683B
0x1800364a2  test    [rcx+1Ch], ebx
0x1800364a5  jz      loc_18003683B
0x1800364ab  mov     edx, 50h ; 'P'
0x1800364b0  jmp     loc_180036828
0x1800364b5  xor     edi, edi
0x1800364b7  lea     r15, aMaxshells; "MaxShells"
0x1800364be  cmp     edi, [rbx]
0x1800364c0  jz      loc_180036595
0x1800364c6  movsxd  rax, edi
0x1800364c9  imul    rcx, rax, 68h ; 'h'
0x1800364cd  add     rcx, [rbx+8]
0x1800364d1  jnz     short loc_1800364F5
0x1800364d3  mov     [rsp+68h+var_48], rcx; struct IRequestContext *
0x1800364d8  lea     r8, a522; "522"
0x1800364df  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x1800364e6  mov     r9d, r13d; unsigned int
0x1800364e9  mov     edx, 20Ah; unsigned int
0x1800364ee  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800364f3  jmp     short loc_180036516
0x1800364f5  cmp     dword ptr [rcx+10h], 9
0x1800364f9  jnz     short loc_180036516
0x1800364fb  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180036500  mov     rcx, rax; String1
  ... truncated ...
```
