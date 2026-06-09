# CspReadFile

- ea: `0x18001e66c`
- end: `0x18001e865`
- name: `CspReadFile`
- size: `505`
- prototype: `__int64 __fastcall(__int64, char *, char *, unsigned int, _QWORD *, _DWORD *)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180020204`
- `0x180020638`
- `0x180020cdc`
- `0x1800258d4`
- `0x180025a40`

## callees

- `0x18000de80`
- `0x180017bac`
- `0x18001cba0`
- `0x18001e66c`
- `0x18001f3a4`
- `0x180021928`
- `0x18002217c`
- `0x18002cfa0`
- `0x18002e010`

## pseudocode

```c
__int64 __fastcall CspReadFile(__int64 a1, char *a2, char *a3, unsigned int a4, _QWORD *a5, _DWORD *a6)
{
  unsigned int v6; // r15d
  int v9; // ebp
  __int64 v11; // rcx
  unsigned int String; // ebx
  unsigned int CachedCardData; // eax
  __int64 v14; // rax
  int v15; // r9d
  unsigned int v16; // eax
  _DWORD v18[4]; // [rsp+40h] [rbp-278h] BYREF
  unsigned __int16 v19[264]; // [rsp+50h] [rbp-268h] BYREF

  v6 = a4 & 0xFFFEFFFF;
  v18[0] = 0;
  v9 = a4 & 0x10000;
  if ( (a4 & 0x10000) == 0 )
    v6 = a4;
  String = I_BuildFileCacheQueryString(v19, (unsigned int)a2, a2, a3);
  if ( String )
    goto LABEL_20;
  if ( v9 )
    goto LABEL_7;
  CachedCardData = GetCachedCardData(a1, v19, String + 4, String + 1, a5, a6, v18);
  String = CachedCardData;
  if ( CachedCardData )
  {
    if ( CachedCardData != 1168 )
      goto LABEL_20;
LABEL_7:
    v14 = *(_QWORD *)(a1 + 8);
    if ( !v14 )
    {
      String = 87;
      WppTraceIndent(v11, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
          v15,
          (__int64)"pCardState->pCardData");
      }
      goto LABEL_20;
    }
    v16 = (*(__int64 (__fastcall **)(_QWORD, char *, char *, _QWORD, _QWORD *, _DWORD *))(v14 + 248))(
            *(_QWORD *)(a1 + 8),
            a2,
            a3,
            v6,
            a5,
            a6);
    String = v16;
    if ( !v9 )
    {
      if ( v16 )
      {
        if ( v16 == -2146435036 )
        {
          AddCachedCardData(a1, v19, 4, 1, 0, 0, 2);
          goto LABEL_20;
        }
      }
      else
      {
        String = AddCachedCardData(a1, v19, 4, 1, *a5, *a6, 0);
      }
    }
    if ( !String )
      return String;
    goto LABEL_20;
  }
  if ( (v18[0] & 2) == 0 )
    return String;
  String = -2146435036;
LABEL_20:
  if ( *a5 )
  {
    CspFreeH(*a5);
    *a5 = 0;
  }
  return String;
}

```

## disassembly

```asm
0x18001e66c  push    rbx
0x18001e66e  push    rbp
0x18001e66f  push    rsi
0x18001e670  push    rdi
0x18001e671  push    r12
0x18001e673  push    r13
0x18001e675  push    r14
0x18001e677  push    r15
0x18001e679  sub     rsp, 278h
0x18001e680  mov     rax, cs:__security_cookie
0x18001e687  xor     rax, rsp
0x18001e68a  mov     [rsp+2B8h+var_58], rax
0x18001e692  mov     rdi, [rsp+2B8h+arg_20]
0x18001e69a  mov     r15d, r9d
0x18001e69d  mov     r14, [rsp+2B8h+arg_28]
0x18001e6a5  mov     ebp, r9d
0x18001e6a8  btr     r15d, 10h
0x18001e6ad  mov     [rsp+2B8h+var_278], 0
0x18001e6b5  mov     r13, r8
0x18001e6b8  mov     rsi, rcx
0x18001e6bb  and     ebp, 10000h
0x18001e6c1  lea     rcx, [rsp+2B8h+var_268]; unsigned __int16 *
0x18001e6c6  mov     r12, rdx
0x18001e6c9  cmovz   r15d, r9d
0x18001e6cd  mov     r9, r8; char *
0x18001e6d0  mov     r8, rdx; char *
0x18001e6d3  call    ?I_BuildFileCacheQueryString@@YAKPEAGKPEAD1@Z; I_BuildFileCacheQueryString(ushort *,ulong,char *,char *)
0x18001e6d8  mov     ebx, eax
0x18001e6da  test    eax, eax
0x18001e6dc  jnz     loc_18001E82B
0x18001e6e2  test    ebp, ebp
0x18001e6e4  jnz     short loc_18001E720
0x18001e6e6  lea     rax, [rsp+2B8h+var_278]
0x18001e6eb  mov     rcx, rsi
0x18001e6ee  mov     [rsp+2B8h+var_288], rax
0x18001e6f3  lea     r9d, [rbx+1]
0x18001e6f7  mov     [rsp+2B8h+var_290], r14
0x18001e6fc  lea     r8d, [rbx+4]
0x18001e700  lea     rdx, [rsp+2B8h+var_268]
0x18001e705  mov     [rsp+2B8h+var_298], rdi
0x18001e70a  call    GetCachedCardData
0x18001e70f  mov     ebx, eax
0x18001e711  test    eax, eax
0x18001e713  jz      short loc_18001E783
0x18001e715  cmp     eax, 490h
0x18001e71a  jnz     loc_18001E82B
0x18001e720  mov     rax, [rsi+8]
0x18001e724  test    rax, rax
0x18001e727  jnz     short loc_18001E798
0x18001e729  lea     edx, [rax+2]
0x18001e72c  lea     ebx, [rax+57h]
0x18001e72f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e734  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e73b  lea     rax, WPP_GLOBAL_Control
0x18001e742  cmp     rcx, rax
0x18001e745  jz      loc_18001E82B
0x18001e74b  test    byte ptr [rcx+1Ch], 1
0x18001e74f  jz      loc_18001E82B
0x18001e755  cmp     byte ptr [rcx+19h], 2
0x18001e759  jb      loc_18001E82B
0x18001e75f  mov     rcx, [rcx+10h]
0x18001e763  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18001e76a  lea     edx, [rbx-3Ch]
0x18001e76d  mov     [rsp+2B8h+var_298], rax
0x18001e772  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001e779  call    WPP_SF_ss
0x18001e77e  jmp     loc_18001E82B
0x18001e783  test    byte ptr [rsp+2B8h+var_278], 2
0x18001e788  jz      loc_18001E83F
0x18001e78e  mov     ebx, 80100024h
0x18001e793  jmp     loc_18001E82B
0x18001e798  mov     rcx, rax
0x18001e79b  mov     [rsp+2B8h+var_290], r14
0x18001e7a0  mov     rax, [rax+0F8h]
0x18001e7a7  mov     r9d, r15d
0x18001e7aa  mov     r8, r13
0x18001e7ad  mov     [rsp+2B8h+var_298], rdi
0x18001e7b2  mov     rdx, r12
0x18001e7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7ba  mov     ebx, eax
0x18001e7bc  test    ebp, ebp
0x18001e7be  jnz     short loc_18001E827
0x18001e7c0  test    eax, eax
0x18001e7c2  jz      short loc_18001E7F7
0x18001e7c4  cmp     eax, 80100024h
0x18001e7c9  jnz     short loc_18001E827
0x18001e7cb  mov     dword ptr [rsp+2B8h+var_288], 2
0x18001e7d3  lea     r9d, [rbp+1]
0x18001e7d7  mov     dword ptr [rsp+2B8h+var_290], ebp
0x18001e7db  lea     r8d, [rbp+4]
0x18001e7df  lea     rdx, [rsp+2B8h+var_268]
0x18001e7e4  mov     [rsp+2B8h+var_298], 0
0x18001e7ed  mov     rcx, rsi
0x18001e7f0  call    AddCachedCardData
0x18001e7f5  jmp     short loc_18001E82B
0x18001e7f7  mov     eax, [r14]
0x18001e7fa  lea     rdx, [rsp+2B8h+var_268]
0x18001e7ff  mov     r9d, 1
0x18001e805  mov     dword ptr [rsp+2B8h+var_288], 0
0x18001e80d  mov     dword ptr [rsp+2B8h+var_290], eax
0x18001e811  mov     rcx, rsi
0x18001e814  mov     rax, [rdi]
0x18001e817  mov     [rsp+2B8h+var_298], rax
0x18001e81c  lea     r8d, [r9+3]
0x18001e820  call    AddCachedCardData
0x18001e825  mov     ebx, eax
0x18001e827  test    ebx, ebx
0x18001e829  jz      short loc_18001E83F
0x18001e82b  mov     rcx, [rdi]
0x18001e82e  test    rcx, rcx
0x18001e831  jz      short loc_18001E83F
0x18001e833  call    CspFreeH
0x18001e838  mov     qword ptr [rdi], 0
0x18001e83f  mov     eax, ebx
0x18001e841  mov     rcx, [rsp+2B8h+var_58]
0x18001e849  xor     rcx, rsp; StackCookie
0x18001e84c  call    __security_check_cookie
0x18001e851  add     rsp, 278h
0x18001e858  pop     r15
0x18001e85a  pop     r14
0x18001e85c  pop     r13
0x18001e85e  pop     r12
0x18001e860  pop     rdi
0x18001e861  pop     rsi
0x18001e862  pop     rbp
0x18001e863  pop     rbx
0x18001e864  retn
```
