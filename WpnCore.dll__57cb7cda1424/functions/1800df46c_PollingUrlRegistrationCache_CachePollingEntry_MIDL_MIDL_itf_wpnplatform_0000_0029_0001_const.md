# PollingUrlRegistrationCache::CachePollingEntry(__MIDL___MIDL_itf_wpnplatform_0000_0029_0001 * const)

- ea: `0x1800df46c`
- end: `0x1800df788`
- name: `?CachePollingEntry@PollingUrlRegistrationCache@@QEAAJQEAU__MIDL___MIDL_itf_wpnplatform_0000_0029_0001@@@Z`
- size: `796`
- prototype: `__int64 __fastcall(PollingUrlRegistrationCache *__hidden this, struct __MIDL___MIDL_itf_wpnplatform_0000_0029_0001 *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a9de4`

## callees

- `0x18002ee38`
- `0x18002f224`
- `0x18002fae0`
- `0x1800af0a4`
- `0x1800df46c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800df69b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800df69b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800df700`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800df700`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800df682`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800df682`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800df497`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800df497`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800df483`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800df761`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800df483`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800df761`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800df76f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800df76f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df717`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df72a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df74f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df717`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df72a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df74f`

## string_xrefs

- `0x1800df4ad`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x1800df51d`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x1800df5b0`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x1800df62d`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`

## pseudocode

```c
__int64 __fastcall PollingUrlRegistrationCache::CachePollingEntry(RTL_SRWLOCK *this, const unsigned __int16 **a2)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v5; // rax
  char **v6; // rbx
  unsigned int v7; // edi
  _QWORD *v8; // r15
  int v9; // eax
  char **v10; // rbp
  unsigned int v11; // r14d
  int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rcx
  int v16; // eax
  char *v17; // rcx
  char *v18; // r14
  char *j; // rsi
  int v20; // eax
  char **v21; // rax
  char **Ptr; // rax
  char *v23; // rcx
  char *v24; // rcx
  unsigned int i; // esi
  char *v26; // rcx
  HANDLE v27; // rax
  int v29; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 8u, 0x88u);
  v6 = (char **)v5;
  if ( !v5 )
  {
    v7 = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
      (const char *)0x8007000ELL,
      v29);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3092d8a00e6a3aa07144cb8230583aa5_Traceguids, 2147942414LL);
    return v7;
  }
  v8 = v5 + 2;
  v9 = WpnCoTaskStrCpy(*a2, (unsigned __int16 **)v5 + 2);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
      (const char *)(unsigned int)v9,
      v29);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_3092d8a00e6a3aa07144cb8230583aa5_Traceguids, v7);
    v10 = v6;
LABEL_37:
    v23 = v6[2];
    if ( v23 )
    {
      CoTaskMemFree(v23);
      v6[2] = 0;
    }
    v24 = v6[13];
    if ( v24 )
    {
      CoTaskMemFree(v24);
      v6[13] = 0;
    }
    for ( i = 0; i < *((_DWORD *)v6 + 10); ++i )
    {
      if ( i >= 5 )
        break;
      v26 = v10[i + 6];
      if ( v26 )
      {
        CoTaskMemFree(v26);
        v10[i + 6] = 0;
      }
    }
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v6);
    return v7;
  }
  v10 = v6;
  *((_DWORD *)v6 + 6) = *((_DWORD *)a2 + 2);
  v11 = 0;
  *((_DWORD *)v6 + 10) = *((_DWORD *)a2 + 6);
  *((_DWORD *)v6 + 32) = *((_DWORD *)a2 + 6);
  while ( v11 < *((_DWORD *)a2 + 6) )
  {
    v12 = WpnCoTaskStrCpy(a2[v11 + 4], (unsigned __int16 **)&v6[v11 + 6]);
    v7 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
        (const char *)(unsigned int)v12,
        v29);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v14 = 12;
LABEL_17:
        WPP_SF_d(v13[2], v14, WPP_3092d8a00e6a3aa07144cb8230583aa5_Traceguids, v7);
        goto LABEL_37;
      }
      goto LABEL_37;
    }
    ++v11;
  }
  v6[11] = (char *)a2[9];
  *((_DWORD *)v6 + 24) = *((_DWORD *)a2 + 20);
  v15 = a2[11];
  if ( v15 )
  {
    v16 = WpnCoTaskStrCpy(v15, (unsigned __int16 **)v6 + 13);
    v7 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
        (const char *)(unsigned int)v16,
        v29);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v14 = 13;
        goto LABEL_17;
      }
      goto LABEL_37;
    }
  }
  else
  {
    v6[13] = 0;
  }
  v6[14] = (char *)a2[12];
  v10 = 0;
  *((_DWORD *)v6 + 30) = *((_DWORD *)a2 + 26);
  AcquireSRWLockExclusive(this + 3);
  v18 = (char *)&this[1];
  for ( j = (char *)this[1].Ptr; ; j = *(char **)j )
  {
    if ( j == v18 )
      goto LABEL_31;
    v20 = _o__wcsicmp(*((_QWORD *)j + 2), *v8);
    v17 = *(char **)j;
    if ( !v20 )
      break;
  }
  if ( *((char **)v17 + 1) != j )
    goto LABEL_32;
  v21 = (char **)*((_QWORD *)j + 1);
  if ( *v21 != j )
    goto LABEL_32;
  *v21 = v17;
  v10 = (char **)j;
  *((_QWORD *)v17 + 1) = v21;
LABEL_31:
  Ptr = (char **)this[2].Ptr;
  if ( *Ptr != v18 )
LABEL_32:
    __fastfail(3u);
  *v6 = v18;
  v6[1] = (char *)Ptr;
  *Ptr = (char *)v6;
  this[2].Ptr = v6;
  if ( (byte_18015DE45 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v17, WPNEND_POLLING_URL_CACHED, *v8);
  ReleaseSRWLockExclusive(this + 3);
  if ( v10 )
  {
    v6 = v10;
    goto LABEL_37;
  }
  return v7;
}

```

## disassembly

```asm
0x1800df46c  push    rbx
0x1800df46e  push    rbp
0x1800df46f  push    rsi
0x1800df470  push    rdi
0x1800df471  push    r12
0x1800df473  push    r13
0x1800df475  push    r14
0x1800df477  push    r15
0x1800df479  sub     rsp, 28h
0x1800df47d  mov     rsi, rdx
0x1800df480  mov     r13, rcx
0x1800df483  call    cs:__imp_GetProcessHeap
0x1800df489  mov     edx, 8; dwFlags
0x1800df48e  mov     r8d, 88h; dwBytes
0x1800df494  mov     rcx, rax; hHeap
0x1800df497  call    cs:__imp_HeapAlloc
0x1800df49d  xor     r12d, r12d
0x1800df4a0  mov     rbx, rax
0x1800df4a3  test    rax, rax
0x1800df4a6  jnz     short loc_1800DF503
0x1800df4a8  mov     rcx, [rsp+68h]; this
0x1800df4ad  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800df4b4  mov     edi, 8007000Eh
0x1800df4b9  lea     edx, [rax+5Ah]; void *
0x1800df4bc  mov     r9d, edi; char *
0x1800df4bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800df4c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800df4cb  lea     rax, WPP_GLOBAL_Control
0x1800df4d2  cmp     rcx, rax
0x1800df4d5  jz      loc_1800DF775
0x1800df4db  test    byte ptr [rcx+1Ch], 80h
0x1800df4df  jz      loc_1800DF775
0x1800df4e5  mov     rcx, [rcx+10h]
0x1800df4e9  lea     edx, [rbx+0Ah]
0x1800df4ec  mov     r9d, 8007000Eh
0x1800df4f2  lea     r8, WPP_3092d8a00e6a3aa07144cb8230583aa5_Traceguids
0x1800df4f9  call    WPP_SF_d
0x1800df4fe  jmp     loc_1800DF775
0x1800df503  mov     rcx, [rsi]; unsigned __int16 *
0x1800df506  lea     r15, [rax+10h]
0x1800df50a  mov     rdx, r15; unsigned __int16 **
0x1800df50d  call    ?WpnCoTaskStrCpy@@YAJPEBGPEAPEAG@Z; WpnCoTaskStrCpy(ushort const *,ushort * *)
0x1800df512  mov     edi, eax
0x1800df514  test    eax, eax
0x1800df516  jns     short loc_1800DF56A
0x1800df518  mov     rcx, [rsp+68h]; this
0x1800df51d  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800df524  mov     r9d, eax; char *
0x1800df527  mov     edx, 5Eh ; '^'; void *
0x1800df52c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800df531  mov     rcx, cs:WPP_GLOBAL_Control
0x1800df538  lea     rax, WPP_GLOBAL_Control
0x1800df53f  cmp     rcx, rax
0x1800df542  jz      short loc_1800DF562
0x1800df544  test    byte ptr [rcx+1Ch], 80h
0x1800df548  jz      short loc_1800DF562
0x1800df54a  mov     rcx, [rcx+10h]
0x1800df54e  lea     r8, WPP_3092d8a00e6a3aa07144cb8230583aa5_Traceguids
0x1800df555  mov     edx, 0Bh
0x1800df55a  mov     r9d, edi
0x1800df55d  call    WPP_SF_d
0x1800df562  mov     rbp, rbx
0x1800df565  jmp     loc_1800DF70E
0x1800df56a  mov     eax, [rsi+8]
0x1800df56d  mov     rbp, rbx
0x1800df570  mov     [rbx+18h], eax
0x1800df573  mov     r14d, r12d
0x1800df576  mov     eax, [rsi+18h]
0x1800df579  mov     [rbx+28h], eax
0x1800df57c  mov     eax, [rsi+18h]
0x1800df57f  mov     [rbx+80h], eax
0x1800df585  cmp     r14d, [rsi+18h]
0x1800df589  jnb     short loc_1800DF602
0x1800df58b  mov     ecx, r14d
0x1800df58e  lea     rdx, [rbx+30h]
0x1800df592  lea     rdx, [rdx+rcx*8]; unsigned __int16 **
0x1800df596  mov     rcx, [rsi+rcx*8+20h]; unsigned __int16 *
0x1800df59b  call    ?WpnCoTaskStrCpy@@YAJPEBGPEAPEAG@Z; WpnCoTaskStrCpy(ushort const *,ushort * *)
0x1800df5a0  mov     edi, eax
0x1800df5a2  test    eax, eax
0x1800df5a4  js      short loc_1800DF5AB
0x1800df5a6  inc     r14d
0x1800df5a9  jmp     short loc_1800DF585
0x1800df5ab  mov     rcx, [rsp+68h]; this
0x1800df5b0  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800df5b7  mov     r9d, edi; char *
0x1800df5ba  mov     edx, 6Ah ; 'j'; void *
0x1800df5bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800df5c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800df5cb  lea     rax, WPP_GLOBAL_Control
0x1800df5d2  cmp     rcx, rax
0x1800df5d5  jz      loc_1800DF70E
0x1800df5db  test    byte ptr [rcx+1Ch], 80h
0x1800df5df  jz      loc_1800DF70E
0x1800df5e5  mov     edx, 0Ch
0x1800df5ea  mov     rcx, [rcx+10h]
0x1800df5ee  lea     r8, WPP_3092d8a00e6a3aa07144cb8230583aa5_Traceguids
0x1800df5f5  mov     r9d, edi
0x1800df5f8  call    WPP_SF_d
0x1800df5fd  jmp     loc_1800DF70E
0x1800df602  mov     rax, [rsi+48h]
0x1800df606  mov     [rbx+58h], rax
0x1800df60a  mov     eax, [rsi+50h]
0x1800df60d  mov     [rbx+60h], eax
0x1800df610  mov     rcx, [rsi+58h]; unsigned __int16 *
0x1800df614  test    rcx, rcx
0x1800df617  jz      short loc_1800DF669
0x1800df619  lea     rdx, [rbx+68h]; unsigned __int16 **
0x1800df61d  call    ?WpnCoTaskStrCpy@@YAJPEBGPEAPEAG@Z; WpnCoTaskStrCpy(ushort const *,ushort * *)
0x1800df622  mov     edi, eax
0x1800df624  test    eax, eax
0x1800df626  jns     short loc_1800DF66D
0x1800df628  mov     rcx, [rsp+68h]; this
0x1800df62d  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800df634  mov     r9d, eax; char *
0x1800df637  mov     edx, 75h ; 'u'; void *
0x1800df63c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800df641  mov     rcx, cs:WPP_GLOBAL_Control
0x1800df648  lea     rax, WPP_GLOBAL_Control
0x1800df64f  cmp     rcx, rax
0x1800df652  jz      loc_1800DF70E
0x1800df658  test    byte ptr [rcx+1Ch], 80h
0x1800df65c  jz      loc_1800DF70E
0x1800df662  mov     edx, 0Dh
0x1800df667  jmp     short loc_1800DF5EA
0x1800df669  mov     [rbx+68h], r12
0x1800df66d  mov     rax, [rsi+60h]
0x1800df671  lea     rcx, [r13+18h]; SRWLock
0x1800df675  mov     [rbx+70h], rax
0x1800df679  mov     rbp, r12
0x1800df67c  mov     eax, [rsi+68h]
0x1800df67f  mov     [rbx+78h], eax
0x1800df682  call    cs:__imp_AcquireSRWLockExclusive
0x1800df688  lea     r14, [r13+8]
0x1800df68c  mov     rsi, [r14]
0x1800df68f  cmp     rsi, r14
0x1800df692  jz      short loc_1800DF6C6
0x1800df694  mov     rdx, [r15]
0x1800df697  mov     rcx, [rsi+10h]
0x1800df69b  call    cs:__imp__o__wcsicmp
0x1800df6a1  mov     rcx, [rsi]
0x1800df6a4  test    eax, eax
0x1800df6a6  jz      short loc_1800DF6AD
0x1800df6a8  mov     rsi, rcx
0x1800df6ab  jmp     short loc_1800DF68F
0x1800df6ad  cmp     [rcx+8], rsi
0x1800df6b1  jnz     short loc_1800DF6CF
0x1800df6b3  mov     rax, [rsi+8]
0x1800df6b7  cmp     [rax], rsi
0x1800df6ba  jnz     short loc_1800DF6CF
0x1800df6bc  mov     [rax], rcx
0x1800df6bf  mov     rbp, rsi
0x1800df6c2  mov     [rcx+8], rax
0x1800df6c6  mov     rax, [r14+8]
0x1800df6ca  cmp     [rax], r14
0x1800df6cd  jz      short loc_1800DF6D6
0x1800df6cf  mov     ecx, 3
0x1800df6d4  int     29h; Win8: RtlFailFast(ecx)
0x1800df6d6  mov     [rbx], r14
0x1800df6d9  mov     [rbx+8], rax
0x1800df6dd  mov     [rax], rbx
0x1800df6e0  mov     [r14+8], rbx
0x1800df6e4  test    cs:byte_18015DE45, 1
0x1800df6eb  jz      short loc_1800DF6FC
0x1800df6ed  mov     r8, [r15]
0x1800df6f0  lea     rdx, WPNEND_POLLING_URL_CACHED
0x1800df6f7  call    McTemplateU0z_EventWriteTransfer
0x1800df6fc  lea     rcx, [r13+18h]; SRWLock
0x1800df700  call    cs:__imp_ReleaseSRWLockExclusive
0x1800df706  test    rbp, rbp
0x1800df709  jz      short loc_1800DF775
0x1800df70b  mov     rbx, rbp
0x1800df70e  mov     rcx, [rbx+10h]; pv
0x1800df712  test    rcx, rcx
0x1800df715  jz      short loc_1800DF721
0x1800df717  call    cs:__imp_CoTaskMemFree
0x1800df71d  mov     [rbx+10h], r12
0x1800df721  mov     rcx, [rbx+68h]; pv
0x1800df725  test    rcx, rcx
0x1800df728  jz      short loc_1800DF734
0x1800df72a  call    cs:__imp_CoTaskMemFree
0x1800df730  mov     [rbx+68h], r12
0x1800df734  mov     esi, r12d
0x1800df737  cmp     [rbx+28h], r12d
0x1800df73b  jbe     short loc_1800DF761
0x1800df73d  cmp     esi, 5
0x1800df740  jnb     short loc_1800DF761
0x1800df742  mov     r14d, esi
0x1800df745  mov     rcx, [rbp+r14*8+30h]; pv
0x1800df74a  test    rcx, rcx
0x1800df74d  jz      short loc_1800DF75A
0x1800df74f  call    cs:__imp_CoTaskMemFree
0x1800df755  mov     [rbp+r14*8+30h], r12
0x1800df75a  inc     esi
0x1800df75c  cmp     esi, [rbx+28h]
0x1800df75f  jb      short loc_1800DF73D
0x1800df761  call    cs:__imp_GetProcessHeap
0x1800df767  mov     r8, rbx; lpMem
0x1800df76a  xor     edx, edx; dwFlags
0x1800df76c  mov     rcx, rax; hHeap
0x1800df76f  call    cs:__imp_HeapFree
0x1800df775  mov     eax, edi
0x1800df777  add     rsp, 28h
0x1800df77b  pop     r15
0x1800df77d  pop     r14
0x1800df77f  pop     r13
0x1800df781  pop     r12
0x1800df783  pop     rdi
0x1800df784  pop     rsi
0x1800df785  pop     rbp
0x1800df786  pop     rbx
0x1800df787  retn
```
