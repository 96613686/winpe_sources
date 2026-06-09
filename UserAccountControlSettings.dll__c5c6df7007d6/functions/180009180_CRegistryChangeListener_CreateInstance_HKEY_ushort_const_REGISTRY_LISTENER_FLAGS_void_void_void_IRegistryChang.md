# CRegistryChangeListener_CreateInstance(HKEY__ *,ushort const *,REGISTRY_LISTENER_FLAGS,void (*)(void *),void *,IRegistryChangeListener * *)

- ea: `0x180009180`
- end: `0x180009273`
- name: `?CRegistryChangeListener_CreateInstance@@YAJPEAUHKEY__@@PEBGW4REGISTRY_LISTENER_FLAGS@@P6AXPEAX@Z3PEAPEAUIRegistryChangeListener@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, void **ppv)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000751c`

## callees

- `0x1800031b4`
- `0x180009180`
- `0x180009320`
- `0x180009370`
- `0x180009468`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x18000923d`
- `SHLWAPI!__imp_QISearch` at `0x18000923d`

## pseudocode

```c
__int64 __fastcall CRegistryChangeListener_CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        void **ppv)
{
  char *v6; // rax
  __int64 v7; // rdx
  void *v8; // r8
  __int64 v9; // r9
  char *v10; // rbx
  int v11; // edi
  __int64 v13; // [rsp+20h] [rbp-18h]

  *ppv = 0;
  v6 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 4) = 1;
    *(_QWORD *)v6 = &CRegistryChangeListener::`vftable'{for `IOleCommandTarget'};
    *((_QWORD *)v6 + 1) = &CRegistryChangeListener::`vftable'{for `IRegistryChangeListener'};
    *((_QWORD *)v6 + 3) = 0;
    *((_QWORD *)v6 + 4) = 0;
    *((_QWORD *)v6 + 5) = 0;
    *((_DWORD *)v6 + 12) = 0;
    *((_QWORD *)v6 + 8) = 0;
    *((_QWORD *)v6 + 10) = 0;
    *((_DWORD *)v6 + 22) = 0;
    _InterlockedIncrement((volatile signed __int32 *)&g_cLocks);
    v11 = CRegistryChangeListener::_Initialize((__int64)v6, v7, v8, v9, v13, a5);
    if ( v11 < 0
      || (v11 = QISearch(
                  v10,
                  &`CRegistryChangeListener::QueryInterface'::`2'::qit,
                  &GUID_077b0abd_69ee_4ce7_aa79_a3044499881e,
                  ppv),
          v11 < 0) )
    {
      CRegistryChangeListener::Shutdown((CRegistryChangeListener *)(v10 + 8));
    }
    CRegistryChangeListener::Release((CRegistryChangeListener *)v10);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180009180  mov     [rsp+arg_0], rbx
0x180009185  mov     [rsp+arg_8], rsi
0x18000918a  push    rdi
0x18000918b  sub     rsp, 30h
0x18000918f  mov     rsi, [rsp+38h+ppv]
0x180009194  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000919b  mov     ecx, 60h ; '`'; unsigned __int64
0x1800091a0  mov     qword ptr [rsi], 0
0x1800091a7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800091ac  mov     rbx, rax
0x1800091af  test    rax, rax
0x1800091b2  jz      loc_18000925C
0x1800091b8  lea     rax, ??_7CRegistryChangeListener@@6BIOleCommandTarget@@@; const CRegistryChangeListener::`vftable'{for `IOleCommandTarget'}
0x1800091bf  mov     dword ptr [rbx+10h], 1
0x1800091c6  mov     [rbx], rax
0x1800091c9  lea     rax, ??_7CRegistryChangeListener@@6BIRegistryChangeListener@@@; const CRegistryChangeListener::`vftable'{for `IRegistryChangeListener'}
0x1800091d0  mov     [rbx+8], rax
0x1800091d4  mov     qword ptr [rbx+18h], 0
0x1800091dc  mov     qword ptr [rbx+20h], 0
0x1800091e4  mov     qword ptr [rbx+28h], 0
0x1800091ec  mov     dword ptr [rbx+30h], 0
0x1800091f3  mov     qword ptr [rbx+40h], 0
0x1800091fb  mov     qword ptr [rbx+50h], 0
0x180009203  mov     dword ptr [rbx+58h], 0
0x18000920a  lock inc cs:?g_cLocks@@3KA; ulong g_cLocks
0x180009211  mov     rax, [rsp+38h+arg_20]
0x180009216  mov     rcx, rbx
0x180009219  mov     [rsp+38h+var_10], rax
0x18000921e  call    ?_Initialize@CRegistryChangeListener@@QEAAJPEAUHKEY__@@PEBGW4REGISTRY_LISTENER_FLAGS@@P6AXPEAX@Z3@Z; CRegistryChangeListener::_Initialize(HKEY__ *,ushort const *,REGISTRY_LISTENER_FLAGS,void (*)(void *),void *)
0x180009223  mov     edi, eax
0x180009225  test    eax, eax
0x180009227  js      short loc_180009249
0x180009229  mov     r9, rsi; ppv
0x18000922c  lea     r8, _GUID_077b0abd_69ee_4ce7_aa79_a3044499881e; riid
0x180009233  lea     rdx, ?qit@?1??QueryInterface@CRegistryChangeListener@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x18000923a  mov     rcx, rbx; that
0x18000923d  call    cs:__imp_QISearch
0x180009243  mov     edi, eax
0x180009245  test    eax, eax
0x180009247  jns     short loc_180009252
0x180009249  lea     rcx, [rbx+8]; this
0x18000924d  call    ?Shutdown@CRegistryChangeListener@@UEAAJXZ; CRegistryChangeListener::Shutdown(void)
0x180009252  mov     rcx, rbx; this
0x180009255  call    ?Release@CRegistryChangeListener@@UEAAKXZ; CRegistryChangeListener::Release(void)
0x18000925a  jmp     short loc_180009261
0x18000925c  mov     edi, 8007000Eh
0x180009261  mov     rbx, [rsp+38h+arg_0]
0x180009266  mov     eax, edi
0x180009268  mov     rsi, [rsp+38h+arg_8]
0x18000926d  add     rsp, 30h
0x180009271  pop     rdi
0x180009272  retn
```
