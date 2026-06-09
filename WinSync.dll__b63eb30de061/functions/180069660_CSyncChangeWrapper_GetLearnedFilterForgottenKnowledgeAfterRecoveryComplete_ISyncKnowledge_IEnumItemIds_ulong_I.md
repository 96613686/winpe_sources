# CSyncChangeWrapper::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete(ISyncKnowledge *,IEnumItemIds *,ulong,ISyncKnowledge * *)

- ea: `0x180069660`
- end: `0x18006983f`
- name: `?GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete@CSyncChangeWrapper@@UEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@KPEAPEAU2@@Z`
- size: `479`
- prototype: `__int64 __fastcall(CSyncChangeWrapper *__hidden this, struct ISyncKnowledge *, struct IEnumItemIds *, unsigned int, struct ISyncKnowledge **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800641b4`
- `0x1800659c8`
- `0x180069364`
- `0x180069660`
- `0x180094010`

## string_xrefs

- `0x1800696aa`: `CSyncChangeWrapper::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete`
- `0x180069808`: `CSyncChangeWrapper::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChangeWrapper::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete(
        CSyncChangeWrapper *this,
        struct ISyncKnowledge *a2,
        struct IEnumItemIds *a3,
        unsigned int a4,
        struct ISyncKnowledge **a5)
{
  __int64 v5; // rsi
  PVOID *v9; // rcx
  struct ISyncKnowledge **v10; // rbp
  unsigned int v11; // ebx
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rbx
  CSyncChangeWrapper *v13; // rcx
  unsigned int v14; // eax
  int v15; // eax
  __int64 v17; // [rsp+30h] [rbp-38h] BYREF
  int v18; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v19; // [rsp+88h] [rbp+20h] BYREF

  v19 = a4;
  v5 = a4;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      189,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 || (v10 = a5) == 0 )
  {
    v11 = -2147467261;
    goto LABEL_23;
  }
  if ( (unsigned int)v5 < *((_DWORD *)this + 73) )
  {
    v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
    v13 = (CSyncChangeWrapper *)((char *)this - 48);
    if ( v12 )
    {
      if ( (unsigned __int8)HashTable<unsigned long,unsigned long,SimpleHashTableContext>::ContainsItem(
                              *((_QWORD *)v13 + 46),
                              &v19) )
      {
        v17 = 0;
        v14 = (**v12)(v12, &GUID_bfe1ef00_e87d_42fd_a4e9_242d70414aef, &v17);
        v11 = v14;
        if ( v14 )
        {
          if ( v14 == -2147467262 )
            v11 = -2147217379;
        }
        else
        {
          v18 = v5;
          if ( !*((_DWORD *)this + 72) )
          {
            HashTable<unsigned long,unsigned long,SimpleHashTableContext>::LookupItem(
              *((_QWORD *)this + 40),
              &v19,
              &v18);
            LODWORD(v5) = v18;
          }
          v11 = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge *, struct IEnumItemIds *, _QWORD, struct ISyncKnowledge **))(*(_QWORD *)v17 + 88LL))(
                  v17,
                  a2,
                  a3,
                  (unsigned int)v5,
                  v10);
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
        goto LABEL_20;
      }
      v15 = (*(__int64 (__fastcall **)(_QWORD, struct ISyncKnowledge **))(**((_QWORD **)this + 4) + 24LL))(
              *((_QWORD *)this + 4),
              v10);
    }
    else
    {
      v15 = CSyncChangeWrapper::GetKnowledgeProjectedToItemAndRelevantChangeUnits(
              v13,
              *(struct ISyncKnowledge **)(*((_QWORD *)this + 38) + 8 * v5),
              a5);
    }
    v11 = v15;
LABEL_20:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_23;
  }
  v11 = -2147024809;
LABEL_23:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      190,
      (unsigned int)WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      (unsigned int)"CSyncChangeWrapper::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete",
      v11);
  return v11;
}

```

## disassembly

```asm
0x180069660  mov     [rsp+arg_0], rbx
0x180069665  mov     [rsp+arg_10], rbp
0x18006966a  mov     [rsp+arg_18], r9d
0x18006966f  push    rsi
0x180069670  push    rdi
0x180069671  push    r12
0x180069673  push    r14
0x180069675  push    r15
0x180069677  sub     rsp, 40h
0x18006967b  mov     esi, r9d
0x18006967e  mov     r15, r8
0x180069681  mov     r14, rdx
0x180069684  mov     rdi, rcx
0x180069687  mov     rcx, cs:WPP_GLOBAL_Control
0x18006968e  lea     r12, WPP_GLOBAL_Control
0x180069695  cmp     rcx, r12
0x180069698  jz      short loc_1800696C9
0x18006969a  test    byte ptr [rcx+1Ch], 8
0x18006969e  jz      short loc_1800696C9
0x1800696a0  cmp     byte ptr [rcx+19h], 5
0x1800696a4  jb      short loc_1800696C9
0x1800696a6  mov     rcx, [rcx+10h]
0x1800696aa  lea     r9, aCsyncchangewra_20; "CSyncChangeWrapper::GetLearnedFilterFor"...
0x1800696b1  mov     edx, 0BDh
0x1800696b6  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x1800696bd  call    WPP_SF_s
0x1800696c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800696c9  test    r14, r14
0x1800696cc  jz      loc_1800697EE
0x1800696d2  mov     rbp, [rsp+68h+arg_20]
0x1800696da  test    rbp, rbp
0x1800696dd  jz      loc_1800697EE
0x1800696e3  cmp     esi, [rdi+124h]
0x1800696e9  jb      short loc_1800696F5
0x1800696eb  mov     ebx, 80070057h
0x1800696f0  jmp     loc_1800697F3
0x1800696f5  mov     rbx, [rdi+10h]
0x1800696f9  lea     rcx, [rdi-30h]; this
0x1800696fd  test    rbx, rbx
0x180069700  jz      loc_1800697D9
0x180069706  mov     rcx, [rcx+170h]
0x18006970d  lea     rdx, [rsp+68h+arg_18]
0x180069715  call    ?ContainsItem@?$HashTable@KKVSimpleHashTableContext@@@@QEBA_NAEBK@Z; HashTable<ulong,ulong,SimpleHashTableContext>::ContainsItem(ulong const &)
0x18006971a  test    al, al
0x18006971c  jz      loc_1800697BB
0x180069722  mov     [rsp+68h+var_38], 0
0x18006972b  lea     r8, [rsp+68h+var_38]
0x180069730  mov     rax, [rbx]
0x180069733  lea     rdx, _GUID_bfe1ef00_e87d_42fd_a4e9_242d70414aef
0x18006973a  mov     rcx, rbx
0x18006973d  mov     rax, [rax]
0x180069740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069745  mov     ebx, eax
0x180069747  test    eax, eax
0x180069749  jnz     short loc_1800697AD
0x18006974b  mov     [rsp+68h+arg_8], esi
0x18006974f  cmp     [rdi+120h], eax
0x180069755  jnz     short loc_180069774
0x180069757  mov     rcx, [rdi+140h]
0x18006975e  lea     r8, [rsp+68h+arg_8]
0x180069763  lea     rdx, [rsp+68h+arg_18]
0x18006976b  call    ?LookupItem@?$HashTable@KKVSimpleHashTableContext@@@@QEBA_NAEBKAEAK@Z; HashTable<ulong,ulong,SimpleHashTableContext>::LookupItem(ulong const &,ulong &)
0x180069770  mov     esi, [rsp+68h+arg_8]
0x180069774  mov     rcx, [rsp+68h+var_38]
0x180069779  mov     r9d, esi
0x18006977c  mov     r8, r15
0x18006977f  mov     [rsp+68h+var_48], rbp
0x180069784  mov     rdx, r14
0x180069787  mov     rax, [rcx]
0x18006978a  mov     rax, [rax+58h]
0x18006978e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069793  mov     rcx, [rsp+68h+var_38]
0x180069798  mov     ebx, eax
0x18006979a  test    rcx, rcx
0x18006979d  jz      short loc_1800697D0
0x18006979f  mov     rax, [rcx]
0x1800697a2  mov     rax, [rax+10h]
0x1800697a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800697ab  jmp     short loc_1800697D0
0x1800697ad  cmp     eax, 80004002h
0x1800697b2  jnz     short loc_1800697D0
0x1800697b4  mov     ebx, 8004101Dh
0x1800697b9  jmp     short loc_1800697D0
0x1800697bb  mov     rcx, [rdi+20h]
0x1800697bf  mov     rdx, rbp
0x1800697c2  mov     rax, [rcx]
0x1800697c5  mov     rax, [rax+18h]
0x1800697c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800697ce  mov     ebx, eax
0x1800697d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800697d7  jmp     short loc_1800697F3
0x1800697d9  mov     rdx, [rdi+130h]
0x1800697e0  mov     r8, rbp; struct ISyncKnowledge **
0x1800697e3  mov     rdx, [rdx+rsi*8]; struct ISyncKnowledge *
0x1800697e7  call    ?GetKnowledgeProjectedToItemAndRelevantChangeUnits@CSyncChangeWrapper@@QEAAJPEAUISyncKnowledge@@PEAPEAU2@@Z; CSyncChangeWrapper::GetKnowledgeProjectedToItemAndRelevantChangeUnits(ISyncKnowledge *,ISyncKnowledge * *)
0x1800697ec  jmp     short loc_1800697CE
0x1800697ee  mov     ebx, 80004003h
0x1800697f3  cmp     rcx, r12
0x1800697f6  jz      short loc_180069824
0x1800697f8  test    byte ptr [rcx+1Ch], 8
0x1800697fc  jz      short loc_180069824
0x1800697fe  cmp     byte ptr [rcx+19h], 5
0x180069802  jb      short loc_180069824
0x180069804  mov     rcx, [rcx+10h]
0x180069808  lea     r9, aCsyncchangewra_20; "CSyncChangeWrapper::GetLearnedFilterFor"...
0x18006980f  mov     edx, 0BEh
0x180069814  mov     dword ptr [rsp+68h+var_48], ebx
0x180069818  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006981f  call    WPP_SF_sD
0x180069824  lea     r11, [rsp+68h+var_28]
0x180069829  mov     eax, ebx
0x18006982b  mov     rbx, [r11+30h]
0x18006982f  mov     rbp, [r11+40h]
0x180069833  mov     rsp, r11
0x180069836  pop     r15
0x180069838  pop     r14
0x18006983a  pop     r12
0x18006983c  pop     rdi
0x18006983d  pop     rsi
0x18006983e  retn
```
