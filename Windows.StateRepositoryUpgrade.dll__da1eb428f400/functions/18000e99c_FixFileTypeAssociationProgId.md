# FixFileTypeAssociationProgId

- ea: `0x18000e99c`
- end: `0x18000eadd`
- name: `FixFileTypeAssociationProgId`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e52c`

## callees

- `0x18000a3a0`
- `0x18000a3c0`
- `0x18000e22c`
- `0x18000e99c`
- `0x1800148ec`
- `0x18001ff88`
- `0x180020058`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ea51`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ea51`

## string_xrefs

- `0x18000ea5f`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000ea9d`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000ea23`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation.cpp`

## pseudocode

```c
__int64 __fastcall FixFileTypeAssociationProgId(struct StateRepository::Database *a1, __int64 a2, const WCHAR *a3)
{
  unsigned int LastError; // ebx
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  const char *v10; // r9
  int v11; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-49h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-49h]
  _QWORD v15[2]; // [rsp+30h] [rbp-39h] BYREF
  __int128 v16; // [rsp+40h] [rbp-29h]
  __int128 v17; // [rsp+50h] [rbp-19h]
  __int128 v18; // [rsp+60h] [rbp-9h]
  int v19; // [rsp+70h] [rbp+7h]
  LPCWCH lpString1; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v21; // [rsp+80h] [rbp+17h]
  __int128 v22; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  bool v24; // [rsp+E8h] [rbp+7Fh] BYREF

  v15[0] = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v21 = 0;
  v22 = 0;
  v15[1] = 0;
  v19 = 0;
  lpString1 = 0;
  v24 = 0;
  LastError = StateRepository::Entity::FileTypeAssociation::TryGet(
                a1,
                a2,
                (struct StateRepository::Entity::FileTypeAssociation *)v15,
                &v24);
  if ( (LastError & 0x80000000) != 0 )
  {
    v6 = 567;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation.cpp",
      (const char *)LastError,
      bIgnoreCase);
    v7 = LastError;
    v8 = 137;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)v7,
      bIgnoreCasea);
    goto LABEL_16;
  }
  if ( !v24 )
  {
    LastError = -2147023728;
    v6 = 568;
    goto LABEL_5;
  }
  v9 = CompareStringOrdinal(lpString1, -1, a3, -1, 0);
  if ( v9 )
  {
    if ( v9 != 2 )
    {
      v11 = StateRepository::Text::Set((StateRepository::Text *)&lpString1, a3, 0xFFu);
      LastError = v11;
      if ( v11 < 0 )
      {
        v8 = 143;
LABEL_11:
        v7 = (unsigned int)v11;
        goto LABEL_12;
      }
      v11 = StateRepository::Entity::FileTypeAssociation::Update(v15, a1);
      LastError = v11;
      if ( v11 < 0 )
      {
        v8 = 144;
        goto LABEL_11;
      }
    }
    LastError = 0;
    goto LABEL_16;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x8B,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
                v10);
LABEL_16:
  StateRepository::Entity::FileTypeAssociation::~FileTypeAssociation((StateRepository::Entity::FileTypeAssociation *)v15);
  return LastError;
}

```

## disassembly

```asm
0x18000e99c  push    rbp
0x18000e99e  push    rbx
0x18000e99f  push    rsi
0x18000e9a0  push    rdi
0x18000e9a1  lea     rbp, [rsp-3Fh]
0x18000e9a6  sub     rsp, 0A8h
0x18000e9ad  xorps   xmm0, xmm0
0x18000e9b0  mov     [rbp+57h+var_90], 0
0x18000e9b8  xorps   xmm1, xmm1
0x18000e9bb  movdqa  [rbp+57h+var_80], xmm0
0x18000e9c0  mov     rdi, r8
0x18000e9c3  movdqa  [rbp+57h+var_70], xmm1
0x18000e9c8  lea     r8, [rbp+57h+var_90]; struct StateRepository::Entity::FileTypeAssociation *
0x18000e9cc  movdqa  [rbp+57h+var_60], xmm0
0x18000e9d1  lea     r9, [rbp+57h+arg_18]; bool *
0x18000e9d5  movdqa  [rbp+57h+var_40], xmm0
0x18000e9da  movdqa  [rbp+57h+var_30], xmm1
0x18000e9df  mov     rsi, rcx
0x18000e9e2  mov     [rbp+57h+var_88], 0
0x18000e9ea  mov     [rbp+57h+var_50], 0
0x18000e9f1  mov     [rbp+57h+lpString1], 0
0x18000e9f9  mov     [rbp+57h+arg_18], 0
0x18000e9fd  call    ?TryGet@FileTypeAssociation@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAV123@AEA_N@Z; StateRepository::Entity::FileTypeAssociation::TryGet(StateRepository::Database &,__int64,StateRepository::Entity::FileTypeAssociation &,bool &)
0x18000ea02  mov     ebx, eax
0x18000ea04  test    eax, eax
0x18000ea06  jns     short loc_18000EA0F
0x18000ea08  mov     edx, 237h
0x18000ea0d  jmp     short loc_18000EA1F
0x18000ea0f  cmp     [rbp+57h+arg_18], 0
0x18000ea13  jnz     short loc_18000EA3C
0x18000ea15  mov     ebx, 80070490h
0x18000ea1a  mov     edx, 238h; void *
0x18000ea1f  mov     rcx, [rbp+5Fh]; this
0x18000ea23  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\staterepositor"...
0x18000ea2a  mov     r9d, ebx; char *
0x18000ea2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea32  mov     r9d, ebx
0x18000ea35  mov     edx, 89h
0x18000ea3a  jmp     short loc_18000EA99
0x18000ea3c  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18000ea40  or      edx, 0FFFFFFFFh; cchCount1
0x18000ea43  mov     r9d, edx; cchCount2
0x18000ea46  mov     [rsp+0C0h+bIgnoreCase], 0; int
0x18000ea4e  mov     r8, rdi; lpString2
0x18000ea51  call    cs:__imp_CompareStringOrdinal
0x18000ea57  test    eax, eax
0x18000ea59  jnz     short loc_18000EA74
0x18000ea5b  mov     rcx, [rbp+5Fh]; this
0x18000ea5f  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000ea66  mov     edx, 8Bh; void *
0x18000ea6b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ea70  mov     ebx, eax
0x18000ea72  jmp     short loc_18000EAC6
0x18000ea74  cmp     eax, 2
0x18000ea77  jz      short loc_18000EAC4
0x18000ea79  mov     r8d, 0FFh; unsigned __int64
0x18000ea7f  lea     rcx, [rbp+57h+lpString1]; this
0x18000ea83  mov     rdx, rdi; unsigned __int16 *
0x18000ea86  call    ?Set@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Set(ushort const *,unsigned __int64)
0x18000ea8b  mov     ebx, eax
0x18000ea8d  test    eax, eax
0x18000ea8f  jns     short loc_18000EAAB
0x18000ea91  mov     edx, 8Fh; void *
0x18000ea96  mov     r9d, eax; char *
0x18000ea99  mov     rcx, [rbp+5Fh]; this
0x18000ea9d  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000eaa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eaa9  jmp     short loc_18000EAC6
0x18000eaab  mov     rdx, rsi
0x18000eaae  lea     rcx, [rbp+57h+var_90]
0x18000eab2  call    ?Update@FileTypeAssociation@Entity@StateRepository@@QEAAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::FileTypeAssociation::Update(StateRepository::Database &,StateRepository::ExecutionFlags)
0x18000eab7  mov     ebx, eax
0x18000eab9  test    eax, eax
0x18000eabb  jns     short loc_18000EAC4
0x18000eabd  mov     edx, 90h
0x18000eac2  jmp     short loc_18000EA96
0x18000eac4  xor     ebx, ebx
0x18000eac6  lea     rcx, [rbp+57h+var_90]; this
0x18000eaca  call    ??1FileTypeAssociation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::FileTypeAssociation::~FileTypeAssociation(void)
0x18000eacf  mov     eax, ebx
0x18000ead1  add     rsp, 0A8h
0x18000ead8  pop     rdi
0x18000ead9  pop     rsi
0x18000eada  pop     rbx
0x18000eadb  pop     rbp
0x18000eadc  retn
```
