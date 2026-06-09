# TieringMovementSession::DeleteMovementTables(void)

- ea: `0x14001d7ec`
- end: `0x14001d959`
- name: `?DeleteMovementTables@TieringMovementSession@@QEAAJXZ`
- size: `365`
- prototype: `__int64 __fastcall(TieringMovementSession *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14001dbf0`
- `0x140031e04`

## callees

- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x14001d534`
- `0x14001d7ec`

## import_xrefs

- `ESENT!JetCloseTable` at `0x14001d894`
- `ESENT!JetCloseTable` at `0x14001d8f0`
- `ESENT!JetCloseTable` at `0x14001d894`
- `ESENT!JetCloseTable` at `0x14001d8f0`

## string_xrefs

- `0x14001d80f`: `TieringMovementSession::DeleteMovementTables`

## pseudocode

```c
__int64 __fastcall TieringMovementSession::DeleteMovementTables(TieringMovementSession *this)
{
  unsigned int v2; // ebx
  JET_ERR v3; // eax
  JET_TABLEID v4; // rdx
  JET_SESID v5; // rcx
  JET_ERR v6; // eax
  _BYTE v8[8]; // [rsp+30h] [rbp-18h] BYREF
  int v9; // [rsp+38h] [rbp-10h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringMovementSession::DeleteMovementTables";
  CHResultImp::CHResultImp((CHResultImp *)v8);
  if ( TieringMovementSession::AreMovementTablesPresent(this) )
  {
    v3 = JetCloseTable(*((_QWORD *)this + 1), *((_QWORD *)this + 2));
    if ( v3
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids,
        *(_DWORD *)this + 696,
        v3);
    }
    v4 = *((_QWORD *)this + 3);
    v5 = *((_QWORD *)this + 1);
    *((_QWORD *)this + 2) = -1;
    v6 = JetCloseTable(v5, v4);
    if ( v6
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)&WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids,
        *(_DWORD *)this + 696,
        v6);
    }
    *((_QWORD *)this + 3) = -1;
    v2 = 0;
    v9 = 0;
  }
  else
  {
    v2 = -2147020584;
    v9 = -2147020584;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)&WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids,
        *(_DWORD *)this + 696,
        216);
    }
  }
  CHResultImp::~CHResultImp((CHResultImp *)v8);
  return v2;
}

```

## disassembly

```asm
0x14001d7ec  mov     [rsp+arg_0], rbx
0x14001d7f1  mov     [rsp+arg_8], rsi
0x14001d7f6  push    rdi
0x14001d7f7  sub     rsp, 40h
0x14001d7fb  mov     rax, gs:58h
0x14001d804  mov     rdi, rcx
0x14001d807  mov     ecx, 8
0x14001d80c  mov     rdx, [rax]
0x14001d80f  lea     rax, aTieringmovemen; "TieringMovementSession::DeleteMovementT"...
0x14001d816  mov     [rcx+rdx], rax
0x14001d81a  lea     rcx, [rsp+48h+var_18]; this
0x14001d81f  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14001d824  mov     rcx, rdi; this
0x14001d827  call    ?AreMovementTablesPresent@TieringMovementSession@@QEAA_NXZ; TieringMovementSession::AreMovementTablesPresent(void)
0x14001d82c  test    al, al
0x14001d82e  jnz     short loc_14001D88C
0x14001d830  mov     ebx, 800710D8h
0x14001d835  mov     [rsp+48h+var_10], ebx
0x14001d839  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d840  lea     rsi, WPP_GLOBAL_Control
0x14001d847  cmp     rcx, rsi
0x14001d84a  jz      loc_14001D93D
0x14001d850  test    byte ptr [rcx+1Ch], 1
0x14001d854  jz      loc_14001D93D
0x14001d85a  cmp     byte ptr [rcx+19h], 2
0x14001d85e  jb      loc_14001D93D
0x14001d864  mov     r9, [rdi]
0x14001d867  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001d86e  mov     rcx, [rcx+10h]
0x14001d872  add     r9, 2B8h
0x14001d879  mov     edx, 15h
0x14001d87e  mov     [rsp+48h+var_28], ebx
0x14001d882  call    WPP_SF_Zd
0x14001d887  jmp     loc_14001D93D
0x14001d88c  mov     rdx, [rdi+10h]; tableid
0x14001d890  mov     rcx, [rdi+8]; sesid
0x14001d894  call    cs:__imp_JetCloseTable
0x14001d89a  lea     rsi, WPP_GLOBAL_Control
0x14001d8a1  test    eax, eax
0x14001d8a3  jz      short loc_14001D8E0
0x14001d8a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d8ac  cmp     rcx, rsi
0x14001d8af  jz      short loc_14001D8E0
0x14001d8b1  test    byte ptr [rcx+1Ch], 1
0x14001d8b5  jz      short loc_14001D8E0
0x14001d8b7  cmp     byte ptr [rcx+19h], 2
0x14001d8bb  jb      short loc_14001D8E0
0x14001d8bd  mov     r9, [rdi]
0x14001d8c0  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001d8c7  mov     rcx, [rcx+10h]
0x14001d8cb  add     r9, 2B8h
0x14001d8d2  mov     edx, 16h
0x14001d8d7  mov     [rsp+48h+var_28], eax
0x14001d8db  call    WPP_SF_Zd
0x14001d8e0  mov     rdx, [rdi+18h]; tableid
0x14001d8e4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14001d8e8  mov     rcx, [rdi+8]; sesid
0x14001d8ec  mov     [rdi+10h], rbx
0x14001d8f0  call    cs:__imp_JetCloseTable
0x14001d8f6  test    eax, eax
0x14001d8f8  jz      short loc_14001D933
0x14001d8fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d901  cmp     rcx, rsi
0x14001d904  jz      short loc_14001D933
0x14001d906  test    byte ptr [rcx+1Ch], 1
0x14001d90a  jz      short loc_14001D933
0x14001d90c  cmp     byte ptr [rcx+19h], 2
0x14001d910  jb      short loc_14001D933
0x14001d912  mov     r9, [rdi]
0x14001d915  lea     edx, [rbx+18h]
0x14001d918  mov     rcx, [rcx+10h]
0x14001d91c  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001d923  add     r9, 2B8h
0x14001d92a  mov     [rsp+48h+var_28], eax
0x14001d92e  call    WPP_SF_Zd
0x14001d933  mov     [rdi+18h], rbx
0x14001d937  xor     ebx, ebx
0x14001d939  mov     [rsp+48h+var_10], ebx
0x14001d93d  lea     rcx, [rsp+48h+var_18]; this
0x14001d942  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14001d947  mov     rsi, [rsp+48h+arg_8]
0x14001d94c  mov     eax, ebx
0x14001d94e  mov     rbx, [rsp+48h+arg_0]
0x14001d953  add     rsp, 40h
0x14001d957  pop     rdi
0x14001d958  retn
```
