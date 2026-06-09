# I_CommonEndTransaction(_CARD_STATE *)

- ea: `0x18002c098`
- end: `0x18002c26b`
- name: `?I_CommonEndTransaction@@YAKPEAU_CARD_STATE@@@Z`
- size: `467`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002c920`

## callees

- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x18001f3a4`
- `0x18002c098`
- `0x18002e010`

## import_xrefs

- `WinSCard!SCardDisconnect` at `0x18002c1cc`
- `WinSCard!SCardDisconnect` at `0x18002c1cc`
- `WinSCard!SCardEndTransaction` at `0x18002c1ac`
- `WinSCard!SCardEndTransaction` at `0x18002c1ac`
- `WinSCard!SCardReleaseContext` at `0x18002c1e6`
- `WinSCard!SCardReleaseContext` at `0x18002c1e6`

## pseudocode

```c
__int64 __fastcall I_CommonEndTransaction(struct _CARD_STATE *a1)
{
  DWORD v2; // edi
  PVOID v3; // rcx
  __int64 v4; // rax
  unsigned int v5; // edi
  int v6; // r9d
  PVOID v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  LONG v10; // eax

  v2 = *((_DWORD *)a1 + 178) != 0;
  WppTraceIndent((__int64)a1, 0);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids, WPP_pszIndent);
  }
  v4 = *((_QWORD *)a1 + 1);
  if ( !v4 )
  {
    v5 = 87;
    WppTraceIndent((__int64)v3, 2u);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
        v6,
        (__int64)"pCardState->pCardData");
    }
    goto LABEL_20;
  }
  v8 = *((unsigned int *)a1 + 178);
  if ( (_DWORD)v8 )
  {
    if ( *(_DWORD *)v4 >= 6u )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(v4 + 376))(*((_QWORD *)a1 + 1), v8, 0);
      goto LABEL_15;
    }
    if ( *(_QWORD *)(v4 + 200) )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(v4 + 200))(*((_QWORD *)a1 + 1), L"user", 0);
LABEL_15:
      if ( !v9 )
        v2 = 0;
    }
  }
  v10 = SCardEndTransaction(*(_QWORD *)(*((_QWORD *)a1 + 1) + 104LL), v2);
  v5 = v10;
  if ( v10 && v10 != -2146434968 )
  {
    SCardDisconnect(*(_QWORD *)(*((_QWORD *)a1 + 1) + 104LL), 1u);
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 104LL) = 0;
    SCardReleaseContext(*(_QWORD *)(*((_QWORD *)a1 + 1) + 96LL));
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 96LL) = 0;
  }
LABEL_20:
  *((_DWORD *)a1 + 178) = 0;
  *((_DWORD *)a1 + 148) = 0;
  *((_DWORD *)a1 + 155) = 0;
  WppTraceIndent((__int64)v7, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
      (_DWORD)WPP_pszIndent,
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18002c098  mov     [rsp+arg_0], rbx
0x18002c09d  mov     [rsp+arg_8], rdi
0x18002c0a2  push    r12
0x18002c0a4  sub     rsp, 30h
0x18002c0a8  xor     edi, edi
0x18002c0aa  mov     rbx, rcx
0x18002c0ad  cmp     [rcx+2C8h], edi
0x18002c0b3  setnz   dil
0x18002c0b7  xor     edx, edx
0x18002c0b9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c0be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0c5  lea     r12, WPP_GLOBAL_Control
0x18002c0cc  cmp     rcx, r12
0x18002c0cf  jz      short loc_18002C0F9
0x18002c0d1  test    byte ptr [rcx+1Ch], 2
0x18002c0d5  jz      short loc_18002C0F9
0x18002c0d7  cmp     byte ptr [rcx+19h], 5
0x18002c0db  jb      short loc_18002C0F9
0x18002c0dd  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002c0e4  lea     r8, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids
0x18002c0eb  mov     rcx, [rcx+10h]
0x18002c0ef  mov     edx, 0Dh
0x18002c0f4  call    WPP_SF_s
0x18002c0f9  mov     rax, [rbx+8]
0x18002c0fd  test    rax, rax
0x18002c100  jnz     short loc_18002C155
0x18002c102  lea     edx, [rax+2]
0x18002c105  lea     edi, [rax+57h]
0x18002c108  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c10d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c114  cmp     rcx, r12
0x18002c117  jz      loc_18002C1F8
0x18002c11d  test    byte ptr [rcx+1Ch], 1
0x18002c121  jz      loc_18002C1F8
0x18002c127  cmp     byte ptr [rcx+19h], 2
0x18002c12b  jb      loc_18002C1F8
0x18002c131  mov     rcx, [rcx+10h]
0x18002c135  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002c13c  lea     edx, [rdi-49h]
0x18002c13f  mov     [rsp+38h+var_18], rax
0x18002c144  lea     r8, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids
0x18002c14b  call    WPP_SF_ss
0x18002c150  jmp     loc_18002C1F8
0x18002c155  mov     edx, [rbx+2C8h]
0x18002c15b  test    edx, edx
0x18002c15d  jz      short loc_18002C1A2
0x18002c15f  cmp     dword ptr [rax], 6
0x18002c162  jb      short loc_18002C178
0x18002c164  mov     rcx, rax
0x18002c167  xor     r8d, r8d
0x18002c16a  mov     rax, [rax+178h]
0x18002c171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c176  jmp     short loc_18002C199
0x18002c178  mov     r9, [rax+0C8h]
0x18002c17f  test    r9, r9
0x18002c182  jz      short loc_18002C1A2
0x18002c184  mov     rcx, rax
0x18002c187  lea     rdx, aUser; "user"
0x18002c18e  mov     rax, r9
0x18002c191  xor     r8d, r8d
0x18002c194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c199  mov     ecx, eax
0x18002c19b  xor     eax, eax
0x18002c19d  test    ecx, ecx
0x18002c19f  cmovz   edi, eax
0x18002c1a2  mov     rcx, [rbx+8]
0x18002c1a6  mov     edx, edi; dwDisposition
0x18002c1a8  mov     rcx, [rcx+68h]; hCard
0x18002c1ac  call    cs:__imp_SCardEndTransaction
0x18002c1b2  mov     edi, eax
0x18002c1b4  test    eax, eax
0x18002c1b6  jz      short loc_18002C1F8
0x18002c1b8  cmp     eax, 80100068h
0x18002c1bd  jz      short loc_18002C1F8
0x18002c1bf  mov     rcx, [rbx+8]
0x18002c1c3  mov     edx, 1; dwDisposition
0x18002c1c8  mov     rcx, [rcx+68h]; hCard
0x18002c1cc  call    cs:__imp_SCardDisconnect
0x18002c1d2  mov     rcx, [rbx+8]
0x18002c1d6  mov     qword ptr [rcx+68h], 0
0x18002c1de  mov     rcx, [rbx+8]
0x18002c1e2  mov     rcx, [rcx+60h]; hContext
0x18002c1e6  call    cs:__imp_SCardReleaseContext
0x18002c1ec  mov     rax, [rbx+8]
0x18002c1f0  mov     qword ptr [rax+60h], 0
0x18002c1f8  mov     edx, 1
0x18002c1fd  mov     dword ptr [rbx+2C8h], 0
0x18002c207  mov     dword ptr [rbx+250h], 0
0x18002c211  mov     dword ptr [rbx+26Ch], 0
0x18002c21b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c220  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c227  cmp     rcx, r12
0x18002c22a  jz      short loc_18002C258
0x18002c22c  test    byte ptr [rcx+1Ch], 2
0x18002c230  jz      short loc_18002C258
0x18002c232  cmp     byte ptr [rcx+19h], 5
0x18002c236  jb      short loc_18002C258
0x18002c238  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002c23f  lea     r8, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids
0x18002c246  mov     rcx, [rcx+10h]
0x18002c24a  mov     edx, 0Fh
0x18002c24f  mov     dword ptr [rsp+38h+var_18], edi
0x18002c253  call    WPP_SF_sD
0x18002c258  mov     rbx, [rsp+38h+arg_0]
0x18002c25d  mov     eax, edi
0x18002c25f  mov     rdi, [rsp+38h+arg_8]
0x18002c264  add     rsp, 30h
0x18002c268  pop     r12
0x18002c26a  retn
```
