# ChangeApplicationContext::CreateConflictKnowledge(SharedRefPtr<ISyncKnowledge> &)

- ea: `0x180075150`
- end: `0x1800752ab`
- name: `?CreateConflictKnowledge@ChangeApplicationContext@@AEAAJAEAV?$SharedRefPtr@UISyncKnowledge@@@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18007731c`

## callees

- `0x180005e8c`
- `0x18001a038`
- `0x18001ae20`
- `0x180074098`
- `0x180074e64`
- `0x180075150`
- `0x18007e594`
- `0x180094010`

## string_xrefs

- `0x18007518c`: `ChangeApplicationContext::CreateConflictKnowledge`
- `0x180075261`: `ChangeApplicationContext::CreateConflictKnowledge`

## pseudocode

```c
__int64 __fastcall ChangeApplicationContext::CreateConflictKnowledge(__int64 a1, __int64 a2)
{
  __int64 (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rcx
  int v5; // eax
  int ConflictKnowledge; // ebx
  int v7; // eax
  __int64 v9[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v10; // [rsp+80h] [rbp+40h] BYREF
  __int64 v11; // [rsp+88h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      WPP_ea1ebbbe88c730e42fdf891d4c557d97_Traceguids,
      "ChangeApplicationContext::CreateConflictKnowledge");
  }
  v4 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a1 + 184);
  v9[0] = 0;
  v5 = (**v4)(v4, &IID_ISyncChange, v9);
  v11 = 0;
  ConflictKnowledge = v5;
  if ( v5 < 0 )
  {
    v10 = 0;
  }
  else
  {
    v7 = GetLearnedKnowledgeForChange(v9, a1 + 96, &v11);
    v10 = 0;
    ConflictKnowledge = v7;
    if ( v7 >= 0 )
    {
      ConflictKnowledge = ChangeConflict::GetConflictKnowledge(*(_QWORD *)(a1 + 192), &v11, &v10);
      if ( ConflictKnowledge >= 0 )
      {
        ConflictKnowledge = ChangeApplicationContext::ApplyChangeConflictExclusions(a1, &v10);
        if ( ConflictKnowledge >= 0 )
          ConflictKnowledge = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(a1 + 96) + 96LL))(
                                *(_QWORD *)(a1 + 96),
                                v10,
                                a2);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      53,
      (unsigned int)WPP_ea1ebbbe88c730e42fdf891d4c557d97_Traceguids,
      (unsigned int)"ChangeApplicationContext::CreateConflictKnowledge",
      ConflictKnowledge);
  }
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v10);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v11);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(v9);
  return (unsigned int)ConflictKnowledge;
}

```

## disassembly

```asm
0x180075150  mov     [rsp-28h+arg_0], rbx
0x180075155  push    rbp
0x180075156  push    rsi
0x180075157  push    rdi
0x180075158  push    r12
0x18007515a  push    r14
0x18007515c  mov     rbp, rsp
0x18007515f  sub     rsp, 40h
0x180075163  mov     r14, rdx
0x180075166  mov     rdi, rcx
0x180075169  mov     rcx, cs:WPP_GLOBAL_Control
0x180075170  lea     r12, WPP_GLOBAL_Control
0x180075177  cmp     rcx, r12
0x18007517a  jz      short loc_1800751A4
0x18007517c  test    byte ptr [rcx+1Ch], 80h
0x180075180  jz      short loc_1800751A4
0x180075182  cmp     byte ptr [rcx+19h], 5
0x180075186  jb      short loc_1800751A4
0x180075188  mov     rcx, [rcx+10h]
0x18007518c  lea     r9, aChangeapplicat_48; "ChangeApplicationContext::CreateConflic"...
0x180075193  mov     edx, 34h ; '4'
0x180075198  lea     r8, WPP_ea1ebbbe88c730e42fdf891d4c557d97_Traceguids
0x18007519f  call    WPP_SF_s
0x1800751a4  mov     rcx, [rdi+0B8h]
0x1800751ab  lea     r8, [rbp+var_10]
0x1800751af  mov     [rbp+var_10], 0
0x1800751b7  lea     rdx, IID_ISyncChange
0x1800751be  mov     rax, [rcx]
0x1800751c1  mov     rax, [rax]
0x1800751c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800751c9  mov     [rbp+arg_18], 0
0x1800751d1  mov     ebx, eax
0x1800751d3  test    eax, eax
0x1800751d5  js      short loc_18007523D
0x1800751d7  lea     r8, [rbp+arg_18]
0x1800751db  lea     rdx, [rdi+60h]
0x1800751df  lea     rcx, [rbp+var_10]
0x1800751e3  call    ?GetLearnedKnowledgeForChange@@YAJAEAV?$SharedRefPtr@UISyncChange@@@@AEAV?$SharedRefPtr@UISyncKnowledge@@@@1@Z; GetLearnedKnowledgeForChange(SharedRefPtr<ISyncChange> &,SharedRefPtr<ISyncKnowledge> &,SharedRefPtr<ISyncKnowledge> &)
0x1800751e8  mov     [rbp+arg_10], 0
0x1800751f0  mov     ebx, eax
0x1800751f2  test    eax, eax
0x1800751f4  js      short loc_180075245
0x1800751f6  mov     rcx, [rdi+0C0h]
0x1800751fd  lea     r8, [rbp+arg_10]
0x180075201  lea     rdx, [rbp+arg_18]
0x180075205  call    ?GetConflictKnowledge@ChangeConflict@@QEAAJAEBV?$SharedRefPtr@UISyncKnowledge@@@@AEAV2@@Z; ChangeConflict::GetConflictKnowledge(SharedRefPtr<ISyncKnowledge> const &,SharedRefPtr<ISyncKnowledge> &)
0x18007520a  mov     ebx, eax
0x18007520c  test    eax, eax
0x18007520e  js      short loc_180075245
0x180075210  lea     rdx, [rbp+arg_10]
0x180075214  mov     rcx, rdi
0x180075217  call    ?ApplyChangeConflictExclusions@ChangeApplicationContext@@AEAAJAEAV?$SharedRefPtr@UISyncKnowledge@@@@@Z; ChangeApplicationContext::ApplyChangeConflictExclusions(SharedRefPtr<ISyncKnowledge> &)
0x18007521c  mov     ebx, eax
0x18007521e  test    eax, eax
0x180075220  js      short loc_180075245
0x180075222  mov     rcx, [rdi+60h]
0x180075226  mov     r8, r14
0x180075229  mov     rdx, [rbp+arg_10]
0x18007522d  mov     rax, [rcx]
0x180075230  mov     rax, [rax+60h]
0x180075234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075239  mov     ebx, eax
0x18007523b  jmp     short loc_180075245
0x18007523d  mov     [rbp+arg_10], 0
0x180075245  mov     rcx, cs:WPP_GLOBAL_Control
0x18007524c  cmp     rcx, r12
0x18007524f  jz      short loc_18007527D
0x180075251  test    byte ptr [rcx+1Ch], 80h
0x180075255  jz      short loc_18007527D
0x180075257  cmp     byte ptr [rcx+19h], 5
0x18007525b  jb      short loc_18007527D
0x18007525d  mov     rcx, [rcx+10h]
0x180075261  lea     r9, aChangeapplicat_48; "ChangeApplicationContext::CreateConflic"...
0x180075268  mov     edx, 35h ; '5'
0x18007526d  mov     [rsp+40h+var_20], ebx
0x180075271  lea     r8, WPP_ea1ebbbe88c730e42fdf891d4c557d97_Traceguids
0x180075278  call    WPP_SF_sD
0x18007527d  lea     rcx, [rbp+arg_10]
0x180075281  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180075286  lea     rcx, [rbp+arg_18]
0x18007528a  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18007528f  lea     rcx, [rbp+var_10]
0x180075293  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180075298  mov     eax, ebx
0x18007529a  mov     rbx, [rsp+40h+arg_0]
0x18007529f  add     rsp, 40h
0x1800752a3  pop     r14
0x1800752a5  pop     r12
0x1800752a7  pop     rdi
0x1800752a8  pop     rsi
0x1800752a9  pop     rbp
0x1800752aa  retn
```
