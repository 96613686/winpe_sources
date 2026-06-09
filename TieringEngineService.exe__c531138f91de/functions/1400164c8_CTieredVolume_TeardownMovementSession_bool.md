# CTieredVolume::TeardownMovementSession(bool)

- ea: `0x1400164c8`
- end: `0x1400166ee`
- name: `?TeardownMovementSession@CTieredVolume@@AEAAJ_N@Z`
- size: `550`
- prototype: `__int64 __fastcall(JET_API_PTR ulContext, char)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14000bf3c`
- `0x1400100a0`
- `0x1400127dc`
- `0x14002eef0`

## callees

- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x1400164c8`
- `0x140017e78`
- `0x14001866c`
- `0x14001dbf0`

## import_xrefs

- `ESENT!JetSetSessionContext` at `0x140016521`
- `ESENT!JetSetSessionContext` at `0x140016521`

## string_xrefs

- `0x1400164ee`: `CTieredVolume::TeardownMovementSession`

## pseudocode

```c
__int64 __fastcall CTieredVolume::TeardownMovementSession(JET_API_PTR ulContext, char a2)
{
  unsigned int v4; // ebx
  JET_SESID v5; // rcx
  JET_ERR v6; // eax
  int v7; // edi
  _QWORD *v8; // rcx
  int v9; // eax
  int v10; // eax
  _QWORD *v11; // rcx
  _BYTE v13[8]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v14; // [rsp+38h] [rbp-40h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::TeardownMovementSession";
  CHResultImp::CHResultImp((CHResultImp *)v13);
  v4 = 0;
  v5 = *(_QWORD *)(ulContext + 1696);
  v14 = 0;
  if ( v5 == -1 )
    goto LABEL_36;
  v6 = JetSetSessionContext(v5, ulContext);
  v7 = v6;
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        261,
        (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        *(_QWORD *)(ulContext + 1696),
        ulContext + 672);
    }
    goto LABEL_26;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Zd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      259,
      (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
      ulContext + 672,
      v6);
    v8 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 4u )
      WPP_SF_Z(v8[2], 260, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, ulContext + 672);
LABEL_26:
    v10 = TieringMovementSession::Teardown((JET_SESID *)(ulContext + 1688));
    v14 = v10;
    v4 = v10;
    if ( v10 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          262,
          (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          ulContext + 672,
          v10);
        v11 = WPP_GLOBAL_Control;
      }
      if ( a2 )
      {
        v4 = 0;
        v14 = 0;
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
          WPP_SF_Z(v11[2], 263, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, ulContext + 672);
      }
    }
    goto LABEL_36;
  }
  if ( v7 == -529 || v7 == -1092 || v7 == -1808 )
  {
    v4 = ATL::AtlHresultFromWin32(112);
  }
  else if ( v7 == -1011 )
  {
    v4 = -2147024882;
  }
  else
  {
    v9 = -v7;
    if ( v7 > 0 )
      LOWORD(v9) = v7;
    v4 = v7 & 0x8E5E0000 | (unsigned __int16)v9 | 0xE5E0000;
  }
  v14 = v4;
LABEL_36:
  CHResultImp::~CHResultImp((CHResultImp *)v13);
  return v4;
}

```

## disassembly

```asm
0x1400164c8  push    rbx
0x1400164ca  push    rbp
0x1400164cb  push    rsi
0x1400164cc  push    rdi
0x1400164cd  push    r13
0x1400164cf  push    r14
0x1400164d1  push    r15
0x1400164d3  sub     rsp, 40h
0x1400164d7  mov     rax, gs:58h
0x1400164e0  mov     rbp, rcx
0x1400164e3  mov     ecx, 8
0x1400164e8  mov     r15b, dl
0x1400164eb  mov     r8, [rax]
0x1400164ee  lea     rax, aCtieredvolumeT; "CTieredVolume::TeardownMovementSession"
0x1400164f5  mov     [rcx+r8], rax
0x1400164f9  lea     rcx, [rsp+78h+var_48]; this
0x1400164fe  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140016503  xor     ebx, ebx
0x140016505  lea     r14, [rbp+698h]
0x14001650c  mov     rcx, [r14+8]; sesid
0x140016510  mov     [rsp+78h+var_40], ebx
0x140016514  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140016518  jz      loc_1400166D3
0x14001651e  mov     rdx, rbp; ulContext
0x140016521  call    cs:__imp_JetSetSessionContext
0x140016527  lea     r13, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14001652e  mov     edi, eax
0x140016530  test    eax, eax
0x140016532  jz      loc_14001660F
0x140016538  mov     rcx, cs:WPP_GLOBAL_Control
0x14001653f  lea     rsi, WPP_GLOBAL_Control
0x140016546  cmp     rcx, rsi
0x140016549  jz      short loc_14001657A
0x14001654b  test    byte ptr [rcx+1Ch], 1
0x14001654f  jz      short loc_14001657A
0x140016551  cmp     byte ptr [rcx+19h], 2
0x140016555  jb      short loc_14001657A
0x140016557  mov     rcx, [rcx+10h]
0x14001655b  lea     r9, [rbp+2A0h]
0x140016562  mov     edx, 103h
0x140016567  mov     dword ptr [rsp+78h+var_58], eax
0x14001656b  mov     r8, r13
0x14001656e  call    WPP_SF_Zd
0x140016573  mov     rcx, cs:WPP_GLOBAL_Control
0x14001657a  test    r15b, r15b
0x14001657d  jz      short loc_1400165B9
0x14001657f  cmp     rcx, rsi
0x140016582  jz      loc_140016652
0x140016588  test    byte ptr [rcx+1Ch], 1
0x14001658c  jz      loc_140016652
0x140016592  cmp     byte ptr [rcx+19h], 4
0x140016596  jb      loc_140016652
0x14001659c  mov     rcx, [rcx+10h]
0x1400165a0  lea     r9, [rbp+2A0h]
0x1400165a7  mov     edx, 104h
0x1400165ac  mov     r8, r13
0x1400165af  call    WPP_SF_Z
0x1400165b4  jmp     loc_140016652
0x1400165b9  cmp     edi, 0FFFFFDEFh
0x1400165bf  jz      short loc_1400165FA
0x1400165c1  cmp     edi, 0FFFFFBBCh
0x1400165c7  jz      short loc_1400165FA
0x1400165c9  cmp     edi, 0FFFFF8F0h
0x1400165cf  jz      short loc_1400165FA
0x1400165d1  cmp     edi, 0FFFFFC0Dh
0x1400165d7  jnz     short loc_1400165E0
0x1400165d9  mov     ebx, 8007000Eh
0x1400165de  jmp     short loc_140016606
0x1400165e0  mov     eax, edi
0x1400165e2  neg     eax
0x1400165e4  cmovs   eax, edi
0x1400165e7  and     edi, 8E5E0000h
0x1400165ed  movzx   ebx, ax
0x1400165f0  or      ebx, edi
0x1400165f2  or      ebx, 0E5E0000h
0x1400165f8  jmp     short loc_140016606
0x1400165fa  mov     ecx, 70h ; 'p'; unsigned int
0x1400165ff  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140016604  mov     ebx, eax
0x140016606  mov     [rsp+78h+var_40], ebx
0x14001660a  jmp     loc_1400166D3
0x14001660f  mov     rcx, cs:WPP_GLOBAL_Control
0x140016616  lea     rsi, WPP_GLOBAL_Control
0x14001661d  cmp     rcx, rsi
0x140016620  jz      short loc_140016652
0x140016622  test    byte ptr [rcx+1Ch], 1
0x140016626  jz      short loc_140016652
0x140016628  cmp     byte ptr [rcx+19h], 4
0x14001662c  jb      short loc_140016652
0x14001662e  mov     r9, [rbp+6A0h]
0x140016635  lea     rax, [rbp+2A0h]
0x14001663c  mov     rcx, [rcx+10h]
0x140016640  mov     edx, 105h
0x140016645  mov     r8, r13
0x140016648  mov     [rsp+78h+var_58], rax
0x14001664d  call    WPP_SF_qZ
0x140016652  mov     rcx, r14; this
0x140016655  call    ?Teardown@TieringMovementSession@@QEAAJXZ; TieringMovementSession::Teardown(void)
0x14001665a  mov     [rsp+78h+var_40], eax
0x14001665e  mov     ebx, eax
0x140016660  test    eax, eax
0x140016662  jns     short loc_1400166D3
0x140016664  mov     rcx, cs:WPP_GLOBAL_Control
0x14001666b  cmp     rcx, rsi
0x14001666e  jz      short loc_14001669F
0x140016670  test    byte ptr [rcx+1Ch], 1
0x140016674  jz      short loc_14001669F
0x140016676  cmp     byte ptr [rcx+19h], 2
0x14001667a  jb      short loc_14001669F
0x14001667c  mov     rcx, [rcx+10h]
0x140016680  lea     r9, [rbp+2A0h]
0x140016687  mov     edx, 106h
0x14001668c  mov     dword ptr [rsp+78h+var_58], eax
0x140016690  mov     r8, r13
0x140016693  call    WPP_SF_Zd
0x140016698  mov     rcx, cs:WPP_GLOBAL_Control
0x14001669f  test    r15b, r15b
0x1400166a2  jz      short loc_1400166D3
0x1400166a4  xor     ebx, ebx
0x1400166a6  mov     [rsp+78h+var_40], ebx
0x1400166aa  cmp     rcx, rsi
0x1400166ad  jz      short loc_1400166D3
0x1400166af  test    byte ptr [rcx+1Ch], 1
0x1400166b3  jz      short loc_1400166D3
0x1400166b5  cmp     byte ptr [rcx+19h], 4
0x1400166b9  jb      short loc_1400166D3
0x1400166bb  mov     rcx, [rcx+10h]
0x1400166bf  lea     r9, [rbp+2A0h]
0x1400166c6  mov     edx, 107h
0x1400166cb  mov     r8, r13
0x1400166ce  call    WPP_SF_Z
0x1400166d3  lea     rcx, [rsp+78h+var_48]; this
0x1400166d8  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1400166dd  mov     eax, ebx
0x1400166df  add     rsp, 40h
0x1400166e3  pop     r15
0x1400166e5  pop     r14
0x1400166e7  pop     r13
0x1400166e9  pop     rdi
0x1400166ea  pop     rsi
0x1400166eb  pop     rbp
0x1400166ec  pop     rbx
0x1400166ed  retn
```
