# AsNegCacheUpdate(void *,ulong,void *,ulong,long)

- ea: `0x180014314`
- end: `0x18001454d`
- name: `?AsNegCacheUpdate@@YAJPEAXK0KJ@Z`
- size: `569`
- prototype: `__int64 __fastcall(void *, __int64, void *, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180014c9c`

## callees

- `0x18000508c`
- `0x180005c74`
- `0x18001022c`
- `0x180013c84`
- `0x180014314`
- `0x180014bc0`
- `0x180020518`
- `0x18005a060`
- `0x18005a090`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001447b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001447b`

## pseudocode

```c
__int64 __fastcall AsNegCacheUpdate(void *a1, __int64 a2, void *a3, int a4, int a5)
{
  unsigned int v6; // ebp
  void **v7; // rdx
  __int64 v8; // r8
  void **v9; // rax
  _DWORD *v10; // rsi
  struct _FILETIME *v11; // rbx
  __int64 v12; // rcx
  void **v13; // rcx
  struct _FILETIME *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int128 v17; // xmm0
  void *v18; // rcx
  void **v19; // rax
  _QWORD *v20; // rax
  char v21[8]; // [rsp+30h] [rbp-48h] BYREF
  char v22[8]; // [rsp+38h] [rbp-40h] BYREF
  _QWORD *v23; // [rsp+40h] [rbp-38h]
  int v24; // [rsp+48h] [rbp-30h]

  if ( !g_fApNegCacheInitialized )
    return 3221225797LL;
  CalculateRequestHash(v22, a1, a3, a3, a4);
  if ( v24 < 0 )
  {
    Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)v22);
    return 3221225626LL;
  }
  else
  {
    v6 = 0;
    wil::EnterCriticalSection(v21, &l_ApNegCacheCritSect);
    v9 = (void **)l_ApNegCacheList;
    v10 = v23;
    while ( 1 )
    {
      v11 = 0;
      if ( v9 == &l_ApNegCacheList )
        goto LABEL_13;
      v11 = (struct _FILETIME *)v9;
      v12 = *v23 - (_QWORD)v9[4];
      if ( (void *)*v23 == v9[4] )
        v12 = v23[1] - (_QWORD)v9[5];
      v7 = (void **)*v9;
      if ( !v12 )
        break;
      ++v6;
      v9 = (void **)*v9;
    }
    if ( v7[1] != v9 )
      goto LABEL_28;
    v13 = (void **)v9[1];
    if ( *v13 != v9 )
      goto LABEL_28;
    *v13 = v7;
    v7[1] = v13;
LABEL_13:
    if ( a5 >= 0 )
    {
      if ( v11 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            191,
            WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
            8675,
            *v10);
        }
        MIDL_user_free(v11);
      }
    }
    else
    {
      if ( !v11 )
      {
        v14 = (struct _FILETIME *)MIDL_user_allocate(0x30u);
        v11 = v14;
        if ( !v14 )
        {
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(
            v21,
            v15,
            v16);
          Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)v22);
          return 3221225495LL;
        }
        v17 = *(_OWORD *)v10;
        v14[2].dwLowDateTime = 0;
        *(_OWORD *)&v14[4].dwLowDateTime = v17;
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            189,
            WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
            8645,
            *v10);
        }
        if ( v6 > 0x32 )
        {
          v18 = qword_1800B2948;
          if ( *(void ***)qword_1800B2948 != &l_ApNegCacheList )
            goto LABEL_28;
          v19 = (void **)*((_QWORD *)qword_1800B2948 + 1);
          if ( *v19 != qword_1800B2948 )
            goto LABEL_28;
          qword_1800B2948 = (void *)*((_QWORD *)qword_1800B2948 + 1);
          *v19 = &l_ApNegCacheList;
          MIDL_user_free(v18);
        }
      }
      GetSystemTimeAsFileTime(v11 + 3);
      ++v11[2].dwLowDateTime;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_dDd(*((_QWORD *)WPP_GLOBAL_Control + 2));
      v20 = l_ApNegCacheList;
      if ( *((void ***)l_ApNegCacheList + 1) != &l_ApNegCacheList )
LABEL_28:
        __fastfail(3u);
      *v11 = (struct _FILETIME)l_ApNegCacheList;
      v11[1] = (struct _FILETIME)&l_ApNegCacheList;
      v20[1] = v11;
      l_ApNegCacheList = v11;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(
      v21,
      v7,
      v8);
    Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)v22);
    return 0;
  }
}

```

## disassembly

```asm
0x180014314  push    rbx
0x180014316  push    rbp
0x180014317  push    rsi
0x180014318  push    rdi
0x180014319  push    r15
0x18001431b  sub     rsp, 50h
0x18001431f  cmp     cs:?g_fApNegCacheInitialized@@3EA, 0; uchar g_fApNegCacheInitialized
0x180014326  jnz     short loc_180014332
0x180014328  mov     eax, 0C0000145h
0x18001432d  jmp     loc_180014542
0x180014332  mov     [rsp+78h+var_58], r9d
0x180014337  mov     rdx, rcx
0x18001433a  mov     r9, r8
0x18001433d  lea     rcx, [rsp+78h+var_40]
0x180014342  call    ?CalculateRequestHash@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@PEAXK0K@Z; CalculateRequestHash(void *,ulong,void *,ulong)
0x180014347  cmp     [rsp+78h+var_30], 0
0x18001434c  jl      loc_180014533
0x180014352  xor     ebp, ebp
0x180014354  lea     rdx, ?l_ApNegCacheCritSect@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION l_ApNegCacheCritSect
0x18001435b  lea     rcx, [rsp+78h+var_48]
0x180014360  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180014365  mov     rax, cs:?l_ApNegCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY l_ApNegCacheList
0x18001436c  lea     r15, ?l_ApNegCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY l_ApNegCacheList
0x180014373  mov     rsi, [rsp+78h+var_38]
0x180014378  xor     ebx, ebx
0x18001437a  cmp     rax, r15
0x18001437d  jz      short loc_1800143C0
0x18001437f  mov     rcx, [rsi]
0x180014382  mov     rbx, rax
0x180014385  sub     rcx, [rax+20h]
0x180014389  jnz     short loc_180014393
0x18001438b  mov     rcx, [rsi+8]
0x18001438f  sub     rcx, [rax+28h]
0x180014393  mov     rdx, [rax]
0x180014396  test    rcx, rcx
0x180014399  jz      short loc_1800143A2
0x18001439b  inc     ebp
0x18001439d  mov     rax, rdx
0x1800143a0  jmp     short loc_180014378
0x1800143a2  cmp     [rdx+8], rax
0x1800143a6  jnz     loc_1800144B9
0x1800143ac  mov     rcx, [rax+8]
0x1800143b0  cmp     [rcx], rax
0x1800143b3  jnz     loc_1800144B9
0x1800143b9  mov     [rcx], rdx
0x1800143bc  mov     [rdx+8], rcx
0x1800143c0  cmp     [rsp+78h+arg_20], 0
0x1800143c8  jge     loc_1800144D4
0x1800143ce  lea     rdi, WPP_GLOBAL_Control
0x1800143d5  test    rbx, rbx
0x1800143d8  jnz     loc_180014477
0x1800143de  lea     ecx, [rbx+30h]; size
0x1800143e1  call    MIDL_user_allocate
0x1800143e6  mov     rbx, rax
0x1800143e9  test    rax, rax
0x1800143ec  jnz     short loc_18001440C
0x1800143ee  lea     rcx, [rsp+78h+var_48]
0x1800143f3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800143f8  lea     rcx, [rsp+78h+var_40]; this
0x1800143fd  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x180014402  mov     eax, 0C0000017h
0x180014407  jmp     loc_180014542
0x18001440c  movups  xmm0, xmmword ptr [rsi]
0x18001440f  mov     dword ptr [rax+10h], 0
0x180014416  movdqu  xmmword ptr [rax+20h], xmm0
0x18001441b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014422  cmp     rcx, rdi
0x180014425  jz      short loc_18001444E
0x180014427  test    byte ptr [rcx+1Ch], 4
0x18001442b  jz      short loc_18001444E
0x18001442d  mov     eax, [rsi]
0x18001442f  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x180014436  mov     rcx, [rcx+10h]
0x18001443a  mov     edx, 0BDh
0x18001443f  mov     r9d, 21C5h
0x180014445  mov     [rsp+78h+var_58], eax
0x180014449  call    WPP_SF_Dd
0x18001444e  cmp     ebp, 32h ; '2'
0x180014451  jbe     short loc_180014477
0x180014453  mov     rcx, cs:qword_1800B2948; void *
0x18001445a  cmp     [rcx], r15
0x18001445d  jnz     short loc_1800144B9
0x18001445f  mov     rax, [rcx+8]
0x180014463  cmp     [rax], rcx
0x180014466  jnz     short loc_1800144B9
0x180014468  mov     cs:qword_1800B2948, rax
0x18001446f  mov     [rax], r15
0x180014472  call    MIDL_user_free
0x180014477  lea     rcx, [rbx+18h]; lpSystemTimeAsFileTime
0x18001447b  call    cs:__imp_GetSystemTimeAsFileTime
0x180014481  inc     dword ptr [rbx+10h]
0x180014484  mov     eax, [rbx+10h]
0x180014487  mov     rcx, cs:WPP_GLOBAL_Control
0x18001448e  cmp     rcx, rdi
0x180014491  jz      short loc_1800144AC
0x180014493  test    byte ptr [rcx+1Ch], 4
0x180014497  jz      short loc_1800144AC
0x180014499  mov     rcx, [rcx+10h]
0x18001449d  mov     [rsp+78h+var_50], eax
0x1800144a1  mov     eax, [rsi]
0x1800144a3  mov     [rsp+78h+var_58], eax
0x1800144a7  call    WPP_SF_dDd
0x1800144ac  mov     rax, cs:?l_ApNegCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY l_ApNegCacheList
0x1800144b3  cmp     [rax+8], r15
0x1800144b7  jz      short loc_1800144C0
0x1800144b9  mov     ecx, 3
0x1800144be  int     29h; Win8: RtlFailFast(ecx)
0x1800144c0  mov     [rbx], rax
0x1800144c3  mov     [rbx+8], r15
0x1800144c7  mov     [rax+8], rbx
0x1800144cb  mov     cs:?l_ApNegCacheList@@3U_LIST_ENTRY@@A, rbx; _LIST_ENTRY l_ApNegCacheList
0x1800144d2  jmp     short loc_18001451B
0x1800144d4  test    rbx, rbx
0x1800144d7  jz      short loc_18001451B
0x1800144d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144e0  lea     rdi, WPP_GLOBAL_Control
0x1800144e7  cmp     rcx, rdi
0x1800144ea  jz      short loc_180014513
0x1800144ec  test    byte ptr [rcx+1Ch], 4
0x1800144f0  jz      short loc_180014513
0x1800144f2  mov     eax, [rsi]
0x1800144f4  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x1800144fb  mov     rcx, [rcx+10h]
0x1800144ff  mov     edx, 0BFh
0x180014504  mov     r9d, 21E3h
0x18001450a  mov     [rsp+78h+var_58], eax
0x18001450e  call    WPP_SF_Dd
0x180014513  mov     rcx, rbx; void *
0x180014516  call    MIDL_user_free
0x18001451b  lea     rcx, [rsp+78h+var_48]
0x180014520  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180014525  lea     rcx, [rsp+78h+var_40]; this
0x18001452a  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x18001452f  xor     eax, eax
0x180014531  jmp     short loc_180014542
0x180014533  lea     rcx, [rsp+78h+var_40]; this
0x180014538  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x18001453d  mov     eax, 0C000009Ah
0x180014542  add     rsp, 50h
0x180014546  pop     r15
0x180014548  pop     rdi
0x180014549  pop     rsi
0x18001454a  pop     rbp
0x18001454b  pop     rbx
0x18001454c  retn
```
