# SyncKnowledge::CompareToKnowledgeCookie(IUnknown *,__MIDL___MIDL_itf_winsync_0000_0000_0011 *)

- ea: `0x180084410`
- end: `0x1800844e3`
- name: `?CompareToKnowledgeCookie@SyncKnowledge@@UEAAJPEAUIUnknown@@PEAW4__MIDL___MIDL_itf_winsync_0000_0000_0011@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(SyncKnowledge *__hidden this, struct IUnknown *, enum __MIDL___MIDL_itf_winsync_0000_0000_0011 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800217ec`
- `0x180084410`

## string_xrefs

- `0x180084445`: `SyncKnowledge::CompareToKnowledgeCookie`
- `0x1800844bc`: `SyncKnowledge::CompareToKnowledgeCookie`

## pseudocode

```c
__int64 __fastcall SyncKnowledge::CompareToKnowledgeCookie(
        SyncKnowledge *this,
        struct IUnknown *a2,
        enum __MIDL___MIDL_itf_winsync_0000_0000_0011 *a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // ebx

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      90,
      WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids,
      "SyncKnowledge::CompareToKnowledgeCookie");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 )
  {
    if ( *((_QWORD *)this + 92) )
    {
      v7 = KnowledgeCookie::CompareToCookie((_QWORD *)this + 92, (unsigned __int16 **)this + 94, (__int64)a2, a3);
    }
    else
    {
      v7 = 0;
      *a3 = KCCR_COOKIE_KNOWLEDGE_NOT_COMPARABLE;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v7 = -2147467261;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      91,
      (unsigned int)WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids,
      (unsigned int)"SyncKnowledge::CompareToKnowledgeCookie",
      v7);
  return v7;
}

```

## disassembly

```asm
0x180084410  push    rbx
0x180084412  push    rbp
0x180084413  push    rsi
0x180084414  push    rdi
0x180084415  sub     rsp, 38h
0x180084419  mov     rdi, r8
0x18008441c  mov     rbx, rdx
0x18008441f  mov     rsi, rcx
0x180084422  mov     rcx, cs:WPP_GLOBAL_Control
0x180084429  lea     rbp, WPP_GLOBAL_Control
0x180084430  cmp     rcx, rbp
0x180084433  jz      short loc_180084464
0x180084435  test    byte ptr [rcx+1Ch], 40h
0x180084439  jz      short loc_180084464
0x18008443b  cmp     byte ptr [rcx+19h], 5
0x18008443f  jb      short loc_180084464
0x180084441  mov     rcx, [rcx+10h]
0x180084445  lea     r9, aSyncknowledgeC_7; "SyncKnowledge::CompareToKnowledgeCookie"
0x18008444c  mov     edx, 5Ah ; 'Z'
0x180084451  lea     r8, WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids
0x180084458  call    WPP_SF_s
0x18008445d  mov     rcx, cs:WPP_GLOBAL_Control
0x180084464  test    rbx, rbx
0x180084467  jz      short loc_1800844A2
0x180084469  test    rdi, rdi
0x18008446c  jz      short loc_1800844A2
0x18008446e  lea     rcx, [rsi+2E0h]
0x180084475  cmp     qword ptr [rcx], 0
0x180084479  jnz     short loc_180084485
0x18008447b  xor     ebx, ebx
0x18008447d  mov     dword ptr [rdi], 3
0x180084483  jmp     short loc_180084499
0x180084485  lea     rdx, [rsi+2F0h]
0x18008448c  mov     r9, rdi
0x18008448f  mov     r8, rbx
0x180084492  call    ?CompareToCookie@KnowledgeCookie@@SAJAEAV?$SharedRefPtr@VKnowledgeId@@@@AEAV?$ScopedPtr@UKnowledgeOperationsSnapshot@@@@PEAUIUnknown@@PEAW4__MIDL___MIDL_itf_winsync_0000_0000_0011@@@Z; KnowledgeCookie::CompareToCookie(SharedRefPtr<KnowledgeId> &,ScopedPtr<KnowledgeOperationsSnapshot> &,IUnknown *,__MIDL___MIDL_itf_winsync_0000_0000_0011 *)
0x180084497  mov     ebx, eax
0x180084499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800844a0  jmp     short loc_1800844A7
0x1800844a2  mov     ebx, 80004003h
0x1800844a7  cmp     rcx, rbp
0x1800844aa  jz      short loc_1800844D8
0x1800844ac  test    byte ptr [rcx+1Ch], 40h
0x1800844b0  jz      short loc_1800844D8
0x1800844b2  cmp     byte ptr [rcx+19h], 5
0x1800844b6  jb      short loc_1800844D8
0x1800844b8  mov     rcx, [rcx+10h]
0x1800844bc  lea     r9, aSyncknowledgeC_7; "SyncKnowledge::CompareToKnowledgeCookie"
0x1800844c3  mov     edx, 5Bh ; '['
0x1800844c8  mov     [rsp+58h+var_38], ebx
0x1800844cc  lea     r8, WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids
0x1800844d3  call    WPP_SF_sD
0x1800844d8  mov     eax, ebx
0x1800844da  add     rsp, 38h
0x1800844de  pop     rdi
0x1800844df  pop     rsi
0x1800844e0  pop     rbp
0x1800844e1  pop     rbx
0x1800844e2  retn
```
