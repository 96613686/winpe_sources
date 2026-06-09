# CManagedAppProcessor::GetManagedApplications(_GUID *,ARPCONTEXT *)

- ea: `0x18001069c`
- end: `0x180010ae2`
- name: `?GetManagedApplications@CManagedAppProcessor@@QEAAKPEAU_GUID@@PEAUARPCONTEXT@@@Z`
- size: `1094`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct _GUID *, struct ARPCONTEXT *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000219c`
- `0x18000bd38`

## callees

- `0x1800016d0`
- `0x180002024`
- `0x180007388`
- `0x180007de4`
- `0x18000b0a8`
- `0x18000ca60`
- `0x18000f634`
- `0x18001069c`
- `0x180011610`
- `0x180011fc0`
- `0x180012630`
- `0x180012fbc`
- `0x180013530`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001078d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001078d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107a3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800107d0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800107d0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001077b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001077b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010a77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010a77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800108c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800108c1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010aa7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010aa7`
- `KERNEL32!lstrcmpW` at `0x180010854`
- `KERNEL32!lstrcmpW` at `0x180010854`

## pseudocode

```c
__int64 __fastcall CManagedAppProcessor::GetManagedApplications(
        const unsigned __int16 **this,
        struct _GUID *a2,
        struct ARPCONTEXT *a3)
{
  struct ARPCONTEXT *v3; // r13
  __int64 v6; // r12
  const unsigned __int16 **v7; // rdx
  unsigned int PolicyList; // edi
  const unsigned __int16 *v9; // rcx
  DWORD LastError; // eax
  const unsigned __int16 *v11; // rax
  char *v12; // rcx
  const unsigned __int16 *v13; // rsi
  unsigned int v14; // r14d
  __int64 v15; // rbp
  HLOCAL v16; // rax
  unsigned int v18; // r15d
  const unsigned __int16 *v19; // rsi
  unsigned __int64 v20; // r14
  const unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // rax
  const unsigned __int16 *v23; // rcx
  unsigned __int16 *v24; // rax
  const unsigned __int16 *v25; // rcx
  unsigned __int16 *v26; // rax
  const unsigned __int16 *v27; // rcx
  unsigned __int16 *v28; // rax
  unsigned int i; // ebx
  unsigned __int16 *v30; // rcx
  WCHAR String2[40]; // [rsp+30h] [rbp-98h] BYREF

  v3 = a3;
  *((_DWORD *)this + 77) = 1;
  if ( a3 )
    v6 = *((_QWORD *)a3 + 1);
  else
    v6 = 0;
  if ( *((_DWORD *)this + 99) == 1 )
  {
    v7 = (const unsigned __int16 **)this[1];
    this[3] = this[2];
    for ( this[2] = (const unsigned __int16 *)v7; ; this[2] = (const unsigned __int16 *)v7 )
    {
      if ( v7 == this )
        v7 = 0;
      if ( !v7 )
        break;
      PolicyList = (unsigned int)CSPath::AddComponent((HLOCAL *)this + 30, v7[4], v7[3]);
      if ( PolicyList )
        goto LABEL_69;
      v7 = (const unsigned __int16 **)*((_QWORD *)this[2] + 1);
    }
  }
  else
  {
    PolicyList = CManagedAppProcessor::LoadPolicyList((CManagedAppProcessor *)this);
    if ( PolicyList )
      goto LABEL_69;
  }
  PolicyList = CManagedAppProcessor::GetAppsFromDirectory((CManagedAppProcessor *)this);
  if ( PolicyList )
    goto LABEL_69;
  v9 = this[14];
  if ( *((_DWORD *)v9 + 99) == 1 || !*((_DWORD *)v9 + 74) || ImpersonateLoggedOnUser(*((HANDLE *)v9 + 33)) )
    goto LABEL_19;
  if ( *(_DWORD *)&gDebugLevel )
  {
    LastError = GetLastError();
    _DebugMsg(PolicyList + 2, 0xBC4u, LastError);
  }
  PolicyList = GetLastError();
  if ( !PolicyList )
LABEL_19:
    PolicyList = CAppList::SetAppActions((CAppList *)(this + 4));
  v11 = this[14];
  if ( *((_DWORD *)v11 + 99) != 1 && *((_DWORD *)v11 + 74) )
    RevertToSelf();
  if ( PolicyList || *((_DWORD *)this + 99) == 1 )
  {
LABEL_69:
    if ( v3 )
      goto LABEL_70;
    goto LABEL_72;
  }
  if ( a2 )
  {
    GuidToString(a2, String2);
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xBFFu, String2);
  }
  v12 = (char *)(this + 10);
  v13 = this[11];
  v14 = 0;
  this[13] = this[12];
  while ( 1 )
  {
    this[12] = v13;
    if ( v13 == (const unsigned __int16 *)v12 )
      v13 = 0;
    if ( !v13 )
      break;
    if ( *((_DWORD *)v13 + 57) != 2 )
      goto LABEL_37;
    if ( a2 )
    {
      v15 = 0;
      if ( !*((_DWORD *)v13 + 86) )
      {
LABEL_34:
        CAppInfo::SetAction(v13, 4, 0);
        v12 = (char *)(this + 10);
        goto LABEL_37;
      }
      while ( lstrcmpW(*(LPCWSTR *)(*((_QWORD *)v13 + 42) + 8 * v15), String2) )
      {
        v15 = (unsigned int)(v15 + 1);
        if ( (unsigned int)v15 >= *((_DWORD *)v13 + 86) )
          goto LABEL_34;
      }
      v12 = (char *)(this + 10);
    }
    ++v14;
LABEL_37:
    v13 = (const unsigned __int16 *)*((_QWORD *)this[12] + 1);
  }
  this[12] = this[13];
  if ( v3 )
  {
    v16 = LocalAlloc(0x40u, (unsigned __int64)v14 << 7);
    *(_QWORD *)(v6 + 8) = v16;
    if ( !v16 )
    {
      *((_DWORD *)v3 + 10) = 8;
      return 8;
    }
    memset_0(v16, 0, (unsigned __int64)v14 << 7);
    v18 = 0;
    this[13] = this[12];
    this[12] = this[11];
    while ( 1 )
    {
      v19 = this[12];
      if ( v19 == (const unsigned __int16 *)(this + 10) || !v19 )
        break;
      this[12] = (const unsigned __int16 *)*((_QWORD *)v19 + 1);
      if ( *((_DWORD *)v19 + 57) == 2 )
      {
        v20 = *(_QWORD *)(v6 + 8) + ((unsigned __int64)v18 << 7);
        StringToGuid(*((wchar_t **)v19 + 6), (struct _GUID *)(v20 + 28));
        StringToGuid(*((wchar_t **)v19 + 10), (struct _GUID *)(v20 + 56));
        PolicyList = 0;
        *(_DWORD *)(v20 + 16) = *((_DWORD *)v19 + 40);
        *(_DWORD *)(v20 + 20) = *((_DWORD *)v19 + 41);
        *(_DWORD *)(v20 + 24) = *((_DWORD *)v19 + 48);
        *(_WORD *)(v20 + 72) = v19[90];
        *(_QWORD *)(v20 + 80) = 0;
        *(_QWORD *)(v20 + 88) = 0;
        *(_QWORD *)(v20 + 96) = 0;
        *(_QWORD *)(v20 + 104) = 0;
        if ( *((_DWORD *)v19 + 42) == 5 )
        {
          *(_DWORD *)(v20 + 120) = 1;
        }
        else if ( *((_DWORD *)v19 + 42) == 6 )
        {
          *(_DWORD *)(v20 + 120) = 2;
        }
        else
        {
          *(_DWORD *)(v20 + 120) = 3;
        }
        *(_DWORD *)(v20 + 124) = (v19[112] & 3) != 0;
        v21 = (const unsigned __int16 *)*((_QWORD *)v19 + 5);
        if ( v21 )
        {
          v22 = MidlStringDuplicate(v21);
          *(_QWORD *)v20 = v22;
          if ( !v22 )
            goto LABEL_61;
        }
        v23 = (const unsigned __int16 *)*((_QWORD *)v19 + 9);
        if ( v23 )
        {
          v24 = MidlStringDuplicate(v23);
          *(_QWORD *)(v20 + 48) = v24;
          if ( !v24 )
            goto LABEL_61;
        }
        if ( (v25 = (const unsigned __int16 *)*((_QWORD *)v19 + 18)) != 0
          && (v26 = MidlStringDuplicate(v25), (*(_QWORD *)(v20 + 8) = v26) == 0)
          || (v27 = (const unsigned __int16 *)*((_QWORD *)v19 + 19)) != 0
          && (v28 = MidlStringDuplicate(v27), (*(_QWORD *)(v20 + 112) = v28) == 0) )
        {
LABEL_61:
          PolicyList = 8;
          ClearManagedApp((struct __MIDL_appmgmt_0006 *)v20);
        }
        if ( PolicyList )
          break;
        ++v18;
      }
    }
    v3 = a3;
    this[12] = this[13];
    if ( PolicyList )
    {
      for ( i = 0; i < v18; ++i )
        ClearManagedApp((struct __MIDL_appmgmt_0006 *)(*(_QWORD *)(v6 + 8) + ((unsigned __int64)i << 7)));
      LocalFree(*(HLOCAL *)(v6 + 8));
      *(_QWORD *)(v6 + 8) = 0;
      *((_DWORD *)a3 + 10) = PolicyList;
      return PolicyList;
    }
    *(_DWORD *)v6 = v18;
LABEL_70:
    *((_DWORD *)v3 + 10) = PolicyList;
    v30 = (unsigned __int16 *)this[60];
    if ( v30 )
      SetEvent(v30);
  }
LABEL_72:
  CManagedAppProcessor::WriteRsopLogs((CManagedAppProcessor *)this);
  return PolicyList;
}

```

## disassembly

```asm
0x18001069c  mov     [rsp+arg_18], rbx
0x1800106a1  push    rbp
0x1800106a2  push    rsi
0x1800106a3  push    rdi
0x1800106a4  push    r12
0x1800106a6  push    r13
0x1800106a8  push    r14
0x1800106aa  push    r15
0x1800106ac  sub     rsp, 90h
0x1800106b3  mov     rax, cs:__security_cookie
0x1800106ba  xor     rax, rsp
0x1800106bd  mov     [rsp+0C8h+var_48], rax
0x1800106c5  mov     [rsp+0C8h+var_A8], r8
0x1800106ca  mov     r13, r8
0x1800106cd  mov     dword ptr [rcx+134h], 1
0x1800106d7  mov     r15, rdx
0x1800106da  mov     rbx, rcx
0x1800106dd  test    r8, r8
0x1800106e0  jnz     short loc_1800106E7
0x1800106e2  xor     r12d, r12d
0x1800106e5  jmp     short loc_1800106EB
0x1800106e7  mov     r12, [r8+8]
0x1800106eb  cmp     dword ptr [rcx+18Ch], 1
0x1800106f2  jnz     short loc_18001073E
0x1800106f4  mov     rax, [rcx+10h]
0x1800106f8  mov     rdx, [rcx+8]
0x1800106fc  mov     [rcx+18h], rax
0x180010700  mov     [rcx+10h], rdx
0x180010704  xor     eax, eax
0x180010706  cmp     rdx, rbx
0x180010709  cmovz   rdx, rax
0x18001070d  test    rdx, rdx
0x180010710  jz      short loc_18001074D
0x180010712  mov     r8, [rdx+18h]; unsigned __int16 *
0x180010716  lea     rcx, [rbx+0F0h]; this
0x18001071d  mov     rdx, [rdx+20h]; unsigned __int16 *
0x180010721  call    ?AddComponent@CSPath@@QEAAKPEBG0@Z; CSPath::AddComponent(ushort const *,ushort const *)
0x180010726  mov     edi, eax
0x180010728  test    eax, eax
0x18001072a  jnz     loc_180010A92
0x180010730  mov     rax, [rbx+10h]
0x180010734  mov     rdx, [rax+8]
0x180010738  mov     [rbx+10h], rdx
0x18001073c  jmp     short loc_180010704
0x18001073e  call    ?LoadPolicyList@CManagedAppProcessor@@QEAAKXZ; CManagedAppProcessor::LoadPolicyList(void)
0x180010743  mov     edi, eax
0x180010745  test    eax, eax
0x180010747  jnz     loc_180010A92
0x18001074d  mov     rcx, rbx; this
0x180010750  call    ?GetAppsFromDirectory@CManagedAppProcessor@@AEAAJXZ; CManagedAppProcessor::GetAppsFromDirectory(void)
0x180010755  mov     edi, eax
0x180010757  test    eax, eax
0x180010759  jnz     loc_180010A92
0x18001075f  mov     rcx, [rbx+70h]
0x180010763  cmp     dword ptr [rcx+18Ch], 1
0x18001076a  jz      short loc_1800107AF
0x18001076c  cmp     [rcx+128h], eax
0x180010772  jz      short loc_1800107AF
0x180010774  mov     rcx, [rcx+108h]; hToken
0x18001077b  call    cs:__imp_ImpersonateLoggedOnUser
0x180010781  test    eax, eax
0x180010783  jnz     short loc_1800107AF
0x180010785  cmp     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x18001078b  jz      short loc_1800107A3
0x18001078d  call    cs:__imp_GetLastError
0x180010793  mov     edx, 0BC4h; unsigned int
0x180010798  lea     ecx, [rdi+2]; unsigned int
0x18001079b  mov     r8d, eax
0x18001079e  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800107a3  call    cs:__imp_GetLastError
0x1800107a9  mov     edi, eax
0x1800107ab  test    eax, eax
0x1800107ad  jnz     short loc_1800107BA
0x1800107af  lea     rcx, [rbx+20h]; this
0x1800107b3  call    ?SetAppActions@CAppList@@QEAAKXZ; CAppList::SetAppActions(void)
0x1800107b8  mov     edi, eax
0x1800107ba  mov     rax, [rbx+70h]
0x1800107be  cmp     dword ptr [rax+18Ch], 1
0x1800107c5  jz      short loc_1800107D6
0x1800107c7  cmp     dword ptr [rax+128h], 0
0x1800107ce  jz      short loc_1800107D6
0x1800107d0  call    cs:__imp_RevertToSelf
0x1800107d6  test    edi, edi
0x1800107d8  jnz     loc_180010A92
0x1800107de  cmp     dword ptr [rbx+18Ch], 1
0x1800107e5  jz      loc_180010A92
0x1800107eb  test    r15, r15
0x1800107ee  jz      short loc_180010817
0x1800107f0  lea     rdx, [rsp+0C8h+String2]; unsigned __int16 *
0x1800107f5  mov     rcx, r15; struct _GUID *
0x1800107f8  call    ?GuidToString@@YAXAEAU_GUID@@PEAG@Z; GuidToString(_GUID &,ushort *)
0x1800107fd  cmp     cs:?gDebugLevel@@3KA, edi; ulong gDebugLevel
0x180010803  jz      short loc_180010817
0x180010805  lea     r8, [rsp+0C8h+String2]
0x18001080a  mov     edx, 0BFFh; unsigned int
0x18001080f  lea     ecx, [rdi+4]; unsigned int
0x180010812  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180010817  mov     rax, [rbx+60h]
0x18001081b  lea     rcx, [rbx+50h]
0x18001081f  mov     rsi, [rbx+58h]
0x180010823  xor     r14d, r14d
0x180010826  mov     [rbx+68h], rax
0x18001082a  jmp     short loc_18001088F
0x18001082c  cmp     dword ptr [rsi+0E4h], 2
0x180010833  jnz     short loc_180010887
0x180010835  test    r15, r15
0x180010838  jz      short loc_180010884
0x18001083a  xor     ebp, ebp
0x18001083c  cmp     [rsi+158h], ebp
0x180010842  jbe     short loc_180010868
0x180010844  mov     rcx, [rsi+150h]
0x18001084b  lea     rdx, [rsp+0C8h+String2]; lpString2
0x180010850  mov     rcx, [rcx+rbp*8]; lpString1
0x180010854  call    cs:__imp_lstrcmpW
0x18001085a  test    eax, eax
0x18001085c  jz      short loc_180010880
0x18001085e  inc     ebp
0x180010860  cmp     ebp, [rsi+158h]
0x180010866  jb      short loc_180010844
0x180010868  xor     r9d, r9d
0x18001086b  xor     r8d, r8d
0x18001086e  mov     rcx, rsi
0x180010871  lea     edx, [r9+4]
0x180010875  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x18001087a  lea     rcx, [rbx+50h]
0x18001087e  jmp     short loc_180010887
0x180010880  lea     rcx, [rbx+50h]
0x180010884  inc     r14d
0x180010887  mov     rax, [rbx+60h]
0x18001088b  mov     rsi, [rax+8]
0x18001088f  xor     eax, eax
0x180010891  mov     [rbx+60h], rsi
0x180010895  cmp     rsi, rcx
0x180010898  cmovz   rsi, rax
0x18001089c  test    rsi, rsi
0x18001089f  jnz     short loc_18001082C
0x1800108a1  mov     rax, [rbx+68h]
0x1800108a5  mov     [rbx+60h], rax
0x1800108a9  test    r13, r13
0x1800108ac  jz      loc_180010AAD
0x1800108b2  mov     esi, r14d
0x1800108b5  mov     ecx, 40h ; '@'; uFlags
0x1800108ba  shl     rsi, 7
0x1800108be  mov     rdx, rsi; uBytes
0x1800108c1  call    cs:__imp_LocalAlloc
0x1800108c7  mov     [r12+8], rax
0x1800108cc  test    rax, rax
0x1800108cf  jnz     short loc_1800108DF
0x1800108d1  lea     ebp, [rax+8]
0x1800108d4  mov     [r13+28h], ebp
0x1800108d8  mov     eax, ebp
0x1800108da  jmp     loc_180010AB7
0x1800108df  mov     r8, rsi; Size
0x1800108e2  xor     edx, edx; Val
0x1800108e4  mov     rcx, rax; void *
0x1800108e7  call    memset_0
0x1800108ec  mov     rax, [rbx+60h]
0x1800108f0  lea     r13, [rbx+50h]
0x1800108f4  xor     r15d, r15d
0x1800108f7  mov     [rbx+68h], rax
0x1800108fb  mov     rax, [rbx+58h]
0x1800108ff  mov     [rbx+60h], rax
0x180010903  lea     ebp, [r15+8]
0x180010907  mov     rsi, [rbx+60h]
0x18001090b  cmp     rsi, r13
0x18001090e  jz      loc_180010A43
0x180010914  test    rsi, rsi
0x180010917  jz      loc_180010A43
0x18001091d  mov     rax, [rsi+8]
0x180010921  mov     [rbx+60h], rax
0x180010925  cmp     dword ptr [rsi+0E4h], 2
0x18001092c  jnz     short loc_180010907
0x18001092e  mov     rcx, [rsi+30h]; String
0x180010932  mov     r14d, r15d
0x180010935  shl     r14, 7
0x180010939  add     r14, [r12+8]
0x18001093e  lea     rdx, [r14+1Ch]; struct _GUID *
0x180010942  call    ?StringToGuid@@YAXPEAGPEAU_GUID@@@Z; StringToGuid(ushort *,_GUID *)
0x180010947  mov     rcx, [rsi+50h]; String
0x18001094b  lea     rdx, [r14+38h]; struct _GUID *
0x18001094f  call    ?StringToGuid@@YAXPEAGPEAU_GUID@@@Z; StringToGuid(ushort *,_GUID *)
0x180010954  mov     eax, [rsi+0A0h]
0x18001095a  xor     edi, edi
0x18001095c  mov     [r14+10h], eax
0x180010960  mov     eax, [rsi+0A4h]
0x180010966  mov     [r14+14h], eax
0x18001096a  mov     eax, [rsi+0C0h]
0x180010970  mov     [r14+18h], eax
0x180010974  movzx   eax, word ptr [rsi+0B4h]
0x18001097b  mov     [r14+48h], ax
0x180010980  mov     [r14+50h], rdi
0x180010984  mov     [r14+58h], rdi
0x180010988  mov     [r14+60h], rdi
0x18001098c  mov     [r14+68h], rdi
0x180010990  mov     ecx, [rsi+0A8h]
0x180010996  sub     ecx, 5
0x180010999  jz      short loc_1800109B4
0x18001099b  cmp     ecx, 1
0x18001099e  jz      short loc_1800109AA
0x1800109a0  mov     dword ptr [r14+78h], 3
0x1800109a8  jmp     short loc_1800109BC
0x1800109aa  mov     dword ptr [r14+78h], 2
0x1800109b2  jmp     short loc_1800109BC
0x1800109b4  mov     dword ptr [r14+78h], 1
0x1800109bc  test    byte ptr [rsi+0E0h], 3
0x1800109c3  mov     eax, edi
0x1800109c5  setnz   al
0x1800109c8  mov     [r14+7Ch], eax
0x1800109cc  mov     rcx, [rsi+28h]; unsigned __int16 *
0x1800109d0  test    rcx, rcx
0x1800109d3  jz      short loc_1800109E2
0x1800109d5  call    ?MidlStringDuplicate@@YAPEAGPEBG@Z; MidlStringDuplicate(ushort const *)
0x1800109da  mov     [r14], rax
0x1800109dd  test    rax, rax
0x1800109e0  jz      short loc_180010A2D
0x1800109e2  mov     rcx, [rsi+48h]; unsigned __int16 *
0x1800109e6  test    rcx, rcx
0x1800109e9  jz      short loc_1800109F9
0x1800109eb  call    ?MidlStringDuplicate@@YAPEAGPEBG@Z; MidlStringDuplicate(ushort const *)
0x1800109f0  mov     [r14+30h], rax
0x1800109f4  test    rax, rax
0x1800109f7  jz      short loc_180010A2D
0x1800109f9  mov     rcx, [rsi+90h]; unsigned __int16 *
0x180010a00  test    rcx, rcx
0x180010a03  jz      short loc_180010A13
0x180010a05  call    ?MidlStringDuplicate@@YAPEAGPEBG@Z; MidlStringDuplicate(ushort const *)
0x180010a0a  mov     [r14+8], rax
0x180010a0e  test    rax, rax
0x180010a11  jz      short loc_180010A2D
0x180010a13  mov     rcx, [rsi+98h]; unsigned __int16 *
0x180010a1a  test    rcx, rcx
0x180010a1d  jz      short loc_180010A37
0x180010a1f  call    ?MidlStringDuplicate@@YAPEAGPEBG@Z; MidlStringDuplicate(ushort const *)
0x180010a24  mov     [r14+70h], rax
0x180010a28  test    rax, rax
0x180010a2b  jnz     short loc_180010A37
0x180010a2d  mov     edi, ebp
0x180010a2f  mov     rcx, r14; struct __MIDL_appmgmt_0006 *
0x180010a32  call    ?ClearManagedApp@@YAXPEAU__MIDL_appmgmt_0006@@@Z; ClearManagedApp(__MIDL_appmgmt_0006 *)
0x180010a37  test    edi, edi
0x180010a39  jnz     short loc_180010A43
0x180010a3b  inc     r15d
0x180010a3e  jmp     loc_180010907
0x180010a43  mov     rax, [rbx+68h]
0x180010a47  mov     r13, [rsp+0C8h+var_A8]
0x180010a4c  mov     [rbx+60h], rax
0x180010a50  test    edi, edi
0x180010a52  jz      short loc_180010A8C
0x180010a54  xor     ebx, ebx
0x180010a56  test    r15d, r15d
0x180010a59  jz      short loc_180010A72
0x180010a5b  mov     ecx, ebx
0x180010a5d  shl     rcx, 7
0x180010a61  add     rcx, [r12+8]; struct __MIDL_appmgmt_0006 *
0x180010a66  call    ?ClearManagedApp@@YAXPEAU__MIDL_appmgmt_0006@@@Z; ClearManagedApp(__MIDL_appmgmt_0006 *)
0x180010a6b  inc     ebx
0x180010a6d  cmp     ebx, r15d
0x180010a70  jb      short loc_180010A5B
0x180010a72  mov     rcx, [r12+8]; hMem
0x180010a77  call    cs:__imp_LocalFree
0x180010a7d  mov     qword ptr [r12+8], 0
0x180010a86  mov     [r13+28h], edi
0x180010a8a  jmp     short loc_180010AB5
0x180010a8c  mov     [r12], r15d
0x180010a90  jmp     short loc_180010A97
0x180010a92  test    r13, r13
0x180010a95  jz      short loc_180010AAD
0x180010a97  mov     [r13+28h], edi
0x180010a9b  mov     rcx, [rbx+1E0h]; hEvent
0x180010aa2  test    rcx, rcx
0x180010aa5  jz      short loc_180010AAD
0x180010aa7  call    cs:__imp_SetEvent
0x180010aad  mov     rcx, rbx; this
0x180010ab0  call    ?WriteRsopLogs@CManagedAppProcessor@@QEAAXXZ; CManagedAppProcessor::WriteRsopLogs(void)
0x180010ab5  mov     eax, edi
0x180010ab7  mov     rcx, [rsp+0C8h+var_48]
0x180010abf  xor     rcx, rsp; StackCookie
0x180010ac2  call    __security_check_cookie
0x180010ac7  mov     rbx, [rsp+0C8h+arg_18]
0x180010acf  add     rsp, 90h
0x180010ad6  pop     r15
0x180010ad8  pop     r14
0x180010ada  pop     r13
0x180010adc  pop     r12
0x180010ade  pop     rdi
0x180010adf  pop     rsi
0x180010ae0  pop     rbp
0x180010ae1  retn
```
