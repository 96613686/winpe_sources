# KnowledgeCookie::CompareToCookie(SharedRefPtr<KnowledgeId> &,ScopedPtr<KnowledgeOperationsSnapshot> &,IUnknown *,__MIDL___MIDL_itf_winsync_0000_0000_0011 *)

- ea: `0x1800217ec`
- end: `0x180021911`
- name: `?CompareToCookie@KnowledgeCookie@@SAJAEAV?$SharedRefPtr@VKnowledgeId@@@@AEAV?$ScopedPtr@UKnowledgeOperationsSnapshot@@@@PEAUIUnknown@@PEAW4__MIDL___MIDL_itf_winsync_0000_0000_0011@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int16 **, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180084410`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800217ec`
- `0x180082ec4`
- `0x1800832c8`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021855`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021855`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021893`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021893`

## string_xrefs

- `0x18002182d`: `KnowledgeCookie::CompareToCookie`
- `0x1800218e2`: `KnowledgeCookie::CompareToCookie`

## pseudocode

```c
__int64 __fastcall KnowledgeCookie::CompareToCookie(_QWORD *a1, unsigned __int16 **a2, __int64 a3, _DWORD *a4)
{
  __int64 v7; // rbx
  unsigned int v8; // edi
  __int64 v9; // rcx
  __int64 v11; // [rsp+70h] [rbp+18h] BYREF
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  v11 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_98ca5cf25e833a9fb458cde358e2579e_Traceguids,
      "KnowledgeCookie::CompareToCookie");
  }
  v7 = 0;
  v12 = 0;
  v8 = 0;
  EnterCriticalSection(g_pCookieTableLock);
  if ( g_pCookieTable )
  {
    HashTable<IUnknown *,KnowledgeCookie *,DefaultHashTableContext>::LookupItem(v9, &v11, &v12);
    v7 = v12;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  }
  LeaveCriticalSection(g_pCookieTableLock);
  *a4 = 3;
  if ( v7 )
  {
    v8 = KnowledgeCookie::Compare(v7, a1, a2, a4);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)WPP_98ca5cf25e833a9fb458cde358e2579e_Traceguids,
      (unsigned int)"KnowledgeCookie::CompareToCookie",
      v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1800217ec  mov     [rsp+arg_0], rbx
0x1800217f1  mov     [rsp+arg_10], r8
0x1800217f6  push    rbp
0x1800217f7  push    rsi
0x1800217f8  push    rdi
0x1800217f9  push    r14
0x1800217fb  push    r15
0x1800217fd  sub     rsp, 30h
0x180021801  mov     rsi, r9
0x180021804  mov     rbp, rdx
0x180021807  mov     r14, rcx
0x18002180a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021811  lea     r15, WPP_GLOBAL_Control
0x180021818  cmp     rcx, r15
0x18002181b  jz      short loc_180021845
0x18002181d  test    byte ptr [rcx+1Ch], 40h
0x180021821  jz      short loc_180021845
0x180021823  cmp     byte ptr [rcx+19h], 5
0x180021827  jb      short loc_180021845
0x180021829  mov     rcx, [rcx+10h]
0x18002182d  lea     r9, aKnowledgecooki_1; "KnowledgeCookie::CompareToCookie"
0x180021834  mov     edx, 0Eh
0x180021839  lea     r8, WPP_98ca5cf25e833a9fb458cde358e2579e_Traceguids
0x180021840  call    WPP_SF_s
0x180021845  mov     rcx, cs:?g_pCookieTableLock@@3PEAVLock@@EA; lpCriticalSection
0x18002184c  xor     ebx, ebx
0x18002184e  mov     [rsp+58h+arg_18], rbx
0x180021853  xor     edi, edi
0x180021855  call    cs:__imp_EnterCriticalSection
0x18002185b  cmp     cs:?g_pCookieTable@@3PEAV?$HashTable@PEAUIUnknown@@PEAVKnowledgeCookie@@VDefaultHashTableContext@@@@EA, rbx; HashTable<IUnknown *,KnowledgeCookie *,DefaultHashTableContext> * g_pCookieTable
0x180021862  jz      short loc_18002188C
0x180021864  lea     r8, [rsp+58h+arg_18]
0x180021869  lea     rdx, [rsp+58h+arg_10]
0x18002186e  call    ?LookupItem@?$HashTable@PEAUIUnknown@@PEAVKnowledgeCookie@@VDefaultHashTableContext@@@@QEBA_NAEBQEAUIUnknown@@AEAPEAVKnowledgeCookie@@@Z; HashTable<IUnknown *,KnowledgeCookie *,DefaultHashTableContext>::LookupItem(IUnknown * const &,KnowledgeCookie * &)
0x180021873  mov     rbx, [rsp+58h+arg_18]
0x180021878  test    rbx, rbx
0x18002187b  jz      short loc_18002188C
0x18002187d  mov     rax, [rbx]
0x180021880  mov     rcx, rbx
0x180021883  mov     rax, [rax+8]
0x180021887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002188c  mov     rcx, cs:?g_pCookieTableLock@@3PEAVLock@@EA; lpCriticalSection
0x180021893  call    cs:__imp_LeaveCriticalSection
0x180021899  mov     dword ptr [rsi], 3
0x18002189f  test    rbx, rbx
0x1800218a2  jz      short loc_1800218C6
0x1800218a4  mov     r9, rsi
0x1800218a7  mov     r8, rbp
0x1800218aa  mov     rdx, r14
0x1800218ad  mov     rcx, rbx
0x1800218b0  call    ?Compare@KnowledgeCookie@@AEAAJAEAV?$SharedRefPtr@VKnowledgeId@@@@AEAV?$ScopedPtr@UKnowledgeOperationsSnapshot@@@@PEAW4__MIDL___MIDL_itf_winsync_0000_0000_0011@@@Z; KnowledgeCookie::Compare(SharedRefPtr<KnowledgeId> &,ScopedPtr<KnowledgeOperationsSnapshot> &,__MIDL___MIDL_itf_winsync_0000_0000_0011 *)
0x1800218b5  mov     rdx, [rbx]
0x1800218b8  mov     edi, eax
0x1800218ba  mov     rcx, rbx
0x1800218bd  mov     rax, [rdx+10h]
0x1800218c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218cd  cmp     rcx, r15
0x1800218d0  jz      short loc_1800218FE
0x1800218d2  test    byte ptr [rcx+1Ch], 40h
0x1800218d6  jz      short loc_1800218FE
0x1800218d8  cmp     byte ptr [rcx+19h], 5
0x1800218dc  jb      short loc_1800218FE
0x1800218de  mov     rcx, [rcx+10h]
0x1800218e2  lea     r9, aKnowledgecooki_1; "KnowledgeCookie::CompareToCookie"
0x1800218e9  mov     edx, 0Fh
0x1800218ee  mov     [rsp+58h+var_38], edi
0x1800218f2  lea     r8, WPP_98ca5cf25e833a9fb458cde358e2579e_Traceguids
0x1800218f9  call    WPP_SF_sD
0x1800218fe  mov     rbx, [rsp+58h+arg_0]
0x180021903  mov     eax, edi
0x180021905  add     rsp, 30h
0x180021909  pop     r15
0x18002190b  pop     r14
0x18002190d  pop     rdi
0x18002190e  pop     rsi
0x18002190f  pop     rbp
0x180021910  retn
```
