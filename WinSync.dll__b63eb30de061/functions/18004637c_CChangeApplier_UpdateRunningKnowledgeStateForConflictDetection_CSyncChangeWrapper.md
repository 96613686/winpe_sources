# CChangeApplier::UpdateRunningKnowledgeStateForConflictDetection(CSyncChangeWrapper *)

- ea: `0x18004637c`
- end: `0x1800465d8`
- name: `?UpdateRunningKnowledgeStateForConflictDetection@CChangeApplier@@AEAAJPEAVCSyncChangeWrapper@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this, struct CSyncChangeWrapper *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800383f4`
- `0x180039948`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002d338`
- `0x18004637c`
- `0x1800646c0`
- `0x180064ea8`
- `0x180094010`

## string_xrefs

- `0x1800463ba`: `CChangeApplier::UpdateRunningKnowledgeStateForConflictDetection`
- `0x1800465a7`: `CChangeApplier::UpdateRunningKnowledgeStateForConflictDetection`

## pseudocode

```c
__int64 __fastcall CChangeApplier::UpdateRunningKnowledgeStateForConflictDetection(
        CChangeApplier *this,
        struct CSyncChangeWrapper *a2)
{
  PVOID *v4; // rcx
  int v5; // edi
  int FilteredReplicaLearnedKnowledge; // eax
  struct ISyncKnowledge *v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  struct ISyncKnowledge *v11; // [rsp+50h] [rbp+20h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      259,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::UpdateRunningKnowledgeStateForConflictDetection");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147467261;
  if ( *((_QWORD *)this + 64) )
  {
    v11 = 0;
    if ( a2 )
    {
      v5 = (*(__int64 (__fastcall **)(char *, struct ISyncKnowledge **))(*((_QWORD *)a2 + 1) + 80LL))(
             (char *)a2 + 8,
             &v11);
      if ( v5 >= 0 )
      {
        v7 = v11;
        if ( v11 == *((struct ISyncKnowledge **)this + 61) )
          goto LABEL_30;
        v8 = *((_QWORD *)this + 60);
        if ( v8 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          v7 = v11;
          *((_QWORD *)this + 60) = 0;
        }
        v5 = (*(__int64 (__fastcall **)(_QWORD, struct ISyncKnowledge *, char *))(**((_QWORD **)this + 64) + 96LL))(
               *((_QWORD *)this + 64),
               v7,
               (char *)this + 480);
        if ( v5 >= 0 )
        {
          v9 = *((_QWORD *)this + 61);
          if ( v9 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
LABEL_21:
          ((void (__fastcall *)(struct ISyncKnowledge *))v11->lpVtbl->AddRef)(v11);
          v7 = v11;
          *((_QWORD *)this + 61) = v11;
          goto LABEL_30;
        }
      }
    }
    else
    {
      if ( *((_QWORD *)this + 26) )
      {
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          WPP_SF_(v4[2], 261, &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids);
        FilteredReplicaLearnedKnowledge = CSyncChangeBatchWrapper::GetFilteredReplicaLearnedKnowledge(
                                            *((CSyncChangeBatchWrapper **)this + 62),
                                            *((struct ISyncKnowledge **)this + 65),
                                            *((struct IEnumItemIds **)this + 33),
                                            &v11);
      }
      else
      {
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          WPP_SF_(v4[2], 260, &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids);
        FilteredReplicaLearnedKnowledge = CSyncChangeBatchWrapper::GetLearnedKnowledgeWithPrerequisite(
                                            *((CSyncChangeBatchWrapper **)this + 62),
                                            *((struct ISyncKnowledge **)this + 65),
                                            &v11);
      }
      v5 = FilteredReplicaLearnedKnowledge;
      if ( FilteredReplicaLearnedKnowledge >= 0 )
      {
        v5 = -2147217379;
        if ( !v11 )
        {
LABEL_32:
          v4 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_33;
        }
        v5 = (*(__int64 (__fastcall **)(_QWORD, struct ISyncKnowledge *, char *))(**((_QWORD **)this + 64) + 96LL))(
               *((_QWORD *)this + 64),
               v11,
               (char *)this + 480);
        if ( v5 >= 0 )
          goto LABEL_21;
      }
    }
    v7 = v11;
LABEL_30:
    if ( v7 )
      ((void (__fastcall *)(struct ISyncKnowledge *))v7->lpVtbl->Release)(v7);
    goto LABEL_32;
  }
LABEL_33:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      262,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::UpdateRunningKnowledgeStateForConflictDetection",
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004637c  mov     [rsp-18h+arg_8], rbx
0x180046381  mov     [rsp-18h+arg_10], rsi
0x180046386  push    rbp
0x180046387  push    rdi
0x180046388  push    r13
0x18004638a  mov     rbp, rsp
0x18004638d  sub     rsp, 30h
0x180046391  mov     rsi, rdx
0x180046394  mov     rbx, rcx
0x180046397  mov     rcx, cs:WPP_GLOBAL_Control
0x18004639e  lea     r13, WPP_GLOBAL_Control
0x1800463a5  cmp     rcx, r13
0x1800463a8  jz      short loc_1800463D9
0x1800463aa  test    byte ptr [rcx+1Ch], 8
0x1800463ae  jz      short loc_1800463D9
0x1800463b0  cmp     byte ptr [rcx+19h], 5
0x1800463b4  jb      short loc_1800463D9
0x1800463b6  mov     rcx, [rcx+10h]
0x1800463ba  lea     r9, aCchangeapplier_21; "CChangeApplier::UpdateRunningKnowledgeS"...
0x1800463c1  mov     edx, 103h
0x1800463c6  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800463cd  call    WPP_SF_s
0x1800463d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800463d9  cmp     qword ptr [rbx+200h], 0
0x1800463e1  mov     edi, 80004003h
0x1800463e6  jz      loc_180046592
0x1800463ec  mov     [rbp+arg_0], 0
0x1800463f4  test    rsi, rsi
0x1800463f7  jnz     loc_1800464E9
0x1800463fd  cmp     [rbx+0D0h], rsi
0x180046404  jnz     short loc_180046445
0x180046406  cmp     rcx, r13
0x180046409  jz      short loc_18004642C
0x18004640b  test    byte ptr [rcx+1Ch], 8
0x18004640f  jz      short loc_18004642C
0x180046411  cmp     byte ptr [rcx+19h], 5
0x180046415  jb      short loc_18004642C
0x180046417  mov     rcx, [rcx+10h]
0x18004641b  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180046422  mov     edx, 104h
0x180046427  call    WPP_SF_
0x18004642c  mov     rdx, [rbx+208h]; struct ISyncKnowledge *
0x180046433  lea     r8, [rbp+arg_0]; struct ISyncKnowledge **
0x180046437  mov     rcx, [rbx+1F0h]; this
0x18004643e  call    ?GetLearnedKnowledgeWithPrerequisite@CSyncChangeBatchWrapper@@QEAAJPEAUISyncKnowledge@@PEAPEAU2@@Z; CSyncChangeBatchWrapper::GetLearnedKnowledgeWithPrerequisite(ISyncKnowledge *,ISyncKnowledge * *)
0x180046443  jmp     short loc_180046489
0x180046445  cmp     rcx, r13
0x180046448  jz      short loc_18004646B
0x18004644a  test    byte ptr [rcx+1Ch], 8
0x18004644e  jz      short loc_18004646B
0x180046450  cmp     byte ptr [rcx+19h], 5
0x180046454  jb      short loc_18004646B
0x180046456  mov     rcx, [rcx+10h]
0x18004645a  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180046461  mov     edx, 105h
0x180046466  call    WPP_SF_
0x18004646b  mov     r8, [rbx+108h]; struct IEnumItemIds *
0x180046472  lea     r9, [rbp+arg_0]; struct ISyncKnowledge **
0x180046476  mov     rdx, [rbx+208h]; struct ISyncKnowledge *
0x18004647d  mov     rcx, [rbx+1F0h]; this
0x180046484  call    ?GetFilteredReplicaLearnedKnowledge@CSyncChangeBatchWrapper@@QEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@PEAPEAU2@@Z; CSyncChangeBatchWrapper::GetFilteredReplicaLearnedKnowledge(ISyncKnowledge *,IEnumItemIds *,ISyncKnowledge * *)
0x180046489  mov     edi, eax
0x18004648b  test    eax, eax
0x18004648d  js      loc_180046573
0x180046493  mov     rdx, [rbp+arg_0]
0x180046497  mov     edi, 8004101Dh
0x18004649c  test    rdx, rdx
0x18004649f  jz      loc_18004658B
0x1800464a5  mov     rcx, [rbx+200h]
0x1800464ac  lea     r8, [rbx+1E0h]
0x1800464b3  mov     rax, [rcx]
0x1800464b6  mov     rax, [rax+60h]
0x1800464ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800464bf  mov     edi, eax
0x1800464c1  test    eax, eax
0x1800464c3  js      loc_180046573
0x1800464c9  mov     rcx, [rbp+arg_0]
0x1800464cd  mov     rax, [rcx]
0x1800464d0  mov     rax, [rax+8]
0x1800464d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800464d9  mov     rdx, [rbp+arg_0]
0x1800464dd  mov     [rbx+1E8h], rdx
0x1800464e4  jmp     loc_180046577
0x1800464e9  lea     rcx, [rsi+8]
0x1800464ed  mov     rax, [rcx]
0x1800464f0  lea     rdx, [rbp+arg_0]
0x1800464f4  mov     rax, [rax+50h]
0x1800464f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800464fd  mov     edi, eax
0x1800464ff  test    eax, eax
0x180046501  js      short loc_180046573
0x180046503  mov     rdx, [rbp+arg_0]
0x180046507  cmp     rdx, [rbx+1E8h]
0x18004650e  jz      short loc_180046577
0x180046510  lea     rdi, [rbx+1E0h]
0x180046517  mov     rcx, [rdi]
0x18004651a  test    rcx, rcx
0x18004651d  jz      short loc_180046536
0x18004651f  mov     rax, [rcx]
0x180046522  mov     rax, [rax+10h]
0x180046526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004652b  mov     rdx, [rbp+arg_0]
0x18004652f  mov     qword ptr [rdi], 0
0x180046536  mov     rcx, [rbx+200h]
0x18004653d  mov     r8, rdi
0x180046540  mov     rax, [rcx]
0x180046543  mov     rax, [rax+60h]
0x180046547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004654c  mov     edi, eax
0x18004654e  test    eax, eax
0x180046550  js      short loc_180046573
0x180046552  mov     rcx, [rbx+1E8h]
0x180046559  test    rcx, rcx
0x18004655c  jz      loc_1800464C9
0x180046562  mov     rax, [rcx]
0x180046565  mov     rax, [rax+10h]
0x180046569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004656e  jmp     loc_1800464C9
0x180046573  mov     rdx, [rbp+arg_0]
0x180046577  test    rdx, rdx
0x18004657a  jz      short loc_18004658B
0x18004657c  mov     rax, [rdx]
0x18004657f  mov     rcx, rdx
0x180046582  mov     rax, [rax+10h]
0x180046586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004658b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046592  cmp     rcx, r13
0x180046595  jz      short loc_1800465C3
0x180046597  test    byte ptr [rcx+1Ch], 8
0x18004659b  jz      short loc_1800465C3
0x18004659d  cmp     byte ptr [rcx+19h], 5
0x1800465a1  jb      short loc_1800465C3
0x1800465a3  mov     rcx, [rcx+10h]
0x1800465a7  lea     r9, aCchangeapplier_21; "CChangeApplier::UpdateRunningKnowledgeS"...
0x1800465ae  mov     edx, 106h
0x1800465b3  mov     [rsp+30h+var_10], edi
0x1800465b7  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800465be  call    WPP_SF_sD
0x1800465c3  mov     rbx, [rsp+30h+arg_8]
0x1800465c8  mov     eax, edi
0x1800465ca  mov     rsi, [rsp+30h+arg_10]
0x1800465cf  add     rsp, 30h
0x1800465d3  pop     r13
0x1800465d5  pop     rdi
0x1800465d6  pop     rbp
0x1800465d7  retn
```
