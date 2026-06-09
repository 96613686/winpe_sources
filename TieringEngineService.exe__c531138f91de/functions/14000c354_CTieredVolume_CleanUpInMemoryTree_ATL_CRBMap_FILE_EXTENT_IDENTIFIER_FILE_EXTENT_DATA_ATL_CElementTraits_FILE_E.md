# CTieredVolume::CleanUpInMemoryTree(ATL::CRBMap<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>> *,_FILE_DELETE_DATA * *)

- ea: `0x14000c354`
- end: `0x14000c43e`
- name: `?CleanUpInMemoryTree@CTieredVolume@@AEAAXPEAV?$CRBMap@U_FILE_EXTENT_IDENTIFIER@@PEAU_FILE_EXTENT_DATA@@V?$CElementTraits@U_FILE_EXTENT_IDENTIFIER@@@ATL@@V?$CElementTraits@PEAU_FILE_EXTENT_DATA@@@4@@ATL@@PEAPEAU_FILE_DELETE_DATA@@@Z`
- size: `234`
- prototype: `void __fastcall(__int64, __int64 *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140010d1c`

## callees

- `0x140009f1c`
- `0x14000c354`
- `0x140014ed0`
- `0x140016470`
- `0x140018700`

## import_xrefs

- `msvcrt!free` at `0x14000c3ce`
- `msvcrt!free` at `0x14000c422`
- `msvcrt!free` at `0x14000c3ce`
- `msvcrt!free` at `0x14000c422`

## pseudocode

```c
void __fastcall CTieredVolume::CleanUpInMemoryTree(__int64 a1, __int64 *a2, void **a3)
{
  __int64 v3; // rbx
  void *v6; // rbp
  void **v7; // r9
  void *v8; // rbx

  v3 = *a2;
  if ( *a2 && v3 != a2[5] )
  {
    while ( *(_QWORD *)(v3 + 40) != a2[5] )
      v3 = *(_QWORD *)(v3 + 40);
    while ( v3 )
    {
      v6 = *(void **)(v3 + 24);
      v3 = ATL::CRBTree<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::Successor(
             a2,
             v3);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, v6);
      }
      free(v6);
    }
  }
  ATL::CRBTree<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::RemoveAll(a2);
  v7 = (void **)*a3;
  if ( *a3 )
  {
    do
    {
      v8 = *v7;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_qii(*((_QWORD *)WPP_GLOBAL_Control + 2));
      }
      free(*a3);
      *a3 = v8;
      v7 = (void **)v8;
    }
    while ( v8 );
  }
}

```

## disassembly

```asm
0x14000c354  push    rbx
0x14000c356  push    rbp
0x14000c357  push    rsi
0x14000c358  push    rdi
0x14000c359  push    r14
0x14000c35b  sub     rsp, 30h
0x14000c35f  mov     rbx, [rdx]
0x14000c362  lea     r14, WPP_GLOBAL_Control
0x14000c369  mov     rsi, r8
0x14000c36c  mov     rdi, rdx
0x14000c36f  test    rbx, rbx
0x14000c372  jz      short loc_14000C3D9
0x14000c374  cmp     rbx, [rdx+28h]
0x14000c378  jz      short loc_14000C3D9
0x14000c37a  mov     rax, [rbx+28h]
0x14000c37e  cmp     rax, [rdx+28h]
0x14000c382  jz      short loc_14000C3D4
0x14000c384  mov     rbx, rax
0x14000c387  jmp     short loc_14000C37A
0x14000c389  mov     rbp, [rbx+18h]
0x14000c38d  mov     rdx, rbx
0x14000c390  mov     rcx, rdi
0x14000c393  call    ?Successor@?$CRBTree@U_FILE_EXTENT_IDENTIFIER@@PEAU_FILE_EXTENT_DATA@@V?$CElementTraits@U_FILE_EXTENT_IDENTIFIER@@@ATL@@V?$CElementTraits@PEAU_FILE_EXTENT_DATA@@@4@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::Successor(ATL::CRBTree<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::CNode *)
0x14000c398  mov     rbx, rax
0x14000c39b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c3a2  cmp     rcx, r14
0x14000c3a5  jz      short loc_14000C3CB
0x14000c3a7  test    byte ptr [rcx+1Ch], 1
0x14000c3ab  jz      short loc_14000C3CB
0x14000c3ad  cmp     byte ptr [rcx+19h], 5
0x14000c3b1  jb      short loc_14000C3CB
0x14000c3b3  mov     rcx, [rcx+10h]
0x14000c3b7  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000c3be  mov     edx, 0CBh
0x14000c3c3  mov     r9, rbp
0x14000c3c6  call    WPP_SF_q
0x14000c3cb  mov     rcx, rbp; Block
0x14000c3ce  call    cs:__imp_free
0x14000c3d4  test    rbx, rbx
0x14000c3d7  jnz     short loc_14000C389
0x14000c3d9  mov     rcx, rdi
0x14000c3dc  call    ?RemoveAll@?$CRBTree@U_FILE_EXTENT_IDENTIFIER@@PEAU_FILE_EXTENT_DATA@@V?$CElementTraits@U_FILE_EXTENT_IDENTIFIER@@@ATL@@V?$CElementTraits@PEAU_FILE_EXTENT_DATA@@@4@@ATL@@QEAAXXZ; ATL::CRBTree<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::RemoveAll(void)
0x14000c3e1  mov     r9, [rsi]
0x14000c3e4  test    r9, r9
0x14000c3e7  jz      short loc_14000C433
0x14000c3e9  mov     rbx, [r9]
0x14000c3ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c3f3  cmp     rcx, r14
0x14000c3f6  jz      short loc_14000C41F
0x14000c3f8  test    byte ptr [rcx+1Ch], 1
0x14000c3fc  jz      short loc_14000C41F
0x14000c3fe  cmp     byte ptr [rcx+19h], 5
0x14000c402  jb      short loc_14000C41F
0x14000c404  mov     rax, [r9+8]
0x14000c408  mov     rcx, [rcx+10h]
0x14000c40c  mov     [rsp+58h+var_30], rax
0x14000c411  mov     rax, [r9+10h]
0x14000c415  mov     [rsp+58h+var_38], rax
0x14000c41a  call    WPP_SF_qii
0x14000c41f  mov     rcx, [rsi]; Block
0x14000c422  call    cs:__imp_free
0x14000c428  mov     [rsi], rbx
0x14000c42b  mov     r9, rbx
0x14000c42e  test    rbx, rbx
0x14000c431  jnz     short loc_14000C3E9
0x14000c433  add     rsp, 30h
0x14000c437  pop     r14
0x14000c439  pop     rdi
0x14000c43a  pop     rsi
0x14000c43b  pop     rbp
0x14000c43c  pop     rbx
0x14000c43d  retn
```
