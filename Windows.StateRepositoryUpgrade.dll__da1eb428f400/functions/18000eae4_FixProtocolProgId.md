# FixProtocolProgId

- ea: `0x18000eae4`
- end: `0x18000ec30`
- name: `FixProtocolProgId`
- size: `332`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e2e0`

## callees

- `0x18000a3a0`
- `0x18000a3c0`
- `0x18000e2b0`
- `0x18000eae4`
- `0x1800148ec`
- `0x18001f654`
- `0x18001f724`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000eba6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000eba6`

## string_xrefs

- `0x18000ebb4`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000ebf0`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000eb78`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-protocol.cpp`

## pseudocode

```c
__int64 __fastcall FixProtocolProgId(struct StateRepository::Database *a1, __int64 a2, const WCHAR *a3)
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
  __int64 v17; // [rsp+50h] [rbp-19h]
  int v18; // [rsp+58h] [rbp-11h]
  __int64 v19; // [rsp+60h] [rbp-9h]
  int v20; // [rsp+68h] [rbp-1h]
  LPCWCH lpString1[2]; // [rsp+70h] [rbp+7h] BYREF
  __int128 v22; // [rsp+80h] [rbp+17h]
  __int64 v23; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  bool v25; // [rsp+E8h] [rbp+7Fh] BYREF

  v15[0] = 0;
  v16 = 0;
  *(_OWORD *)lpString1 = 0;
  v22 = 0;
  v15[1] = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v23 = 0;
  v25 = 0;
  LastError = StateRepository::Entity::Protocol::TryGet(a1, a2, (struct StateRepository::Entity::Protocol *)v15, &v25);
  if ( (LastError & 0x80000000) != 0 )
  {
    v6 = 508;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-protocol.cpp",
      (const char *)LastError,
      bIgnoreCase);
    v7 = LastError;
    v8 = 71;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)v7,
      bIgnoreCasea);
    goto LABEL_16;
  }
  if ( !v25 )
  {
    LastError = -2147023728;
    v6 = 509;
    goto LABEL_5;
  }
  v9 = CompareStringOrdinal(lpString1[0], -1, a3, -1, 0);
  if ( v9 )
  {
    if ( v9 != 2 )
    {
      v11 = StateRepository::Text::Set((StateRepository::Text *)lpString1, a3, 0xFFu);
      LastError = v11;
      if ( v11 < 0 )
      {
        v8 = 77;
LABEL_11:
        v7 = (unsigned int)v11;
        goto LABEL_12;
      }
      v11 = StateRepository::Entity::Protocol::Update(v15, a1);
      LastError = v11;
      if ( v11 < 0 )
      {
        v8 = 78;
        goto LABEL_11;
      }
    }
    LastError = 0;
    goto LABEL_16;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x49,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
                v10);
LABEL_16:
  StateRepository::Entity::Protocol::~Protocol((StateRepository::Entity::Protocol *)v15);
  return LastError;
}

```

## disassembly

```asm
0x18000eae4  push    rbp
0x18000eae6  push    rbx
0x18000eae7  push    rsi
0x18000eae8  push    rdi
0x18000eae9  lea     rbp, [rsp-3Fh]
0x18000eaee  sub     rsp, 0A8h
0x18000eaf5  xorps   xmm0, xmm0
0x18000eaf8  mov     [rbp+57h+var_90], 0
0x18000eb00  mov     rdi, r8
0x18000eb03  movdqa  [rbp+57h+var_80], xmm0
0x18000eb08  xorps   xmm1, xmm1
0x18000eb0b  movdqa  xmmword ptr [rbp+57h+lpString1], xmm0
0x18000eb10  lea     r8, [rbp+57h+var_90]; struct StateRepository::Entity::Protocol *
0x18000eb14  movdqa  [rbp+57h+var_40], xmm1
0x18000eb19  lea     r9, [rbp+57h+arg_18]; bool *
0x18000eb1d  mov     [rbp+57h+var_88], 0
0x18000eb25  mov     rsi, rcx
0x18000eb28  mov     [rbp+57h+var_70], 0
0x18000eb30  mov     [rbp+57h+var_68], 0
0x18000eb37  mov     [rbp+57h+var_60], 0
0x18000eb3f  mov     [rbp+57h+var_58], 0
0x18000eb46  mov     [rbp+57h+var_30], 0
0x18000eb4e  mov     [rbp+57h+arg_18], 0
0x18000eb52  call    ?TryGet@Protocol@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAV123@AEA_N@Z; StateRepository::Entity::Protocol::TryGet(StateRepository::Database &,__int64,StateRepository::Entity::Protocol &,bool &)
0x18000eb57  mov     ebx, eax
0x18000eb59  test    eax, eax
0x18000eb5b  jns     short loc_18000EB64
0x18000eb5d  mov     edx, 1FCh
0x18000eb62  jmp     short loc_18000EB74
0x18000eb64  cmp     [rbp+57h+arg_18], 0
0x18000eb68  jnz     short loc_18000EB91
0x18000eb6a  mov     ebx, 80070490h
0x18000eb6f  mov     edx, 1FDh; void *
0x18000eb74  mov     rcx, [rbp+5Fh]; this
0x18000eb78  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18000eb7f  mov     r9d, ebx; char *
0x18000eb82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eb87  mov     r9d, ebx
0x18000eb8a  mov     edx, 47h ; 'G'
0x18000eb8f  jmp     short loc_18000EBEC
0x18000eb91  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18000eb95  or      edx, 0FFFFFFFFh; cchCount1
0x18000eb98  mov     r9d, edx; cchCount2
0x18000eb9b  mov     [rsp+0C0h+bIgnoreCase], 0; int
0x18000eba3  mov     r8, rdi; lpString2
0x18000eba6  call    cs:__imp_CompareStringOrdinal
0x18000ebac  test    eax, eax
0x18000ebae  jnz     short loc_18000EBC7
0x18000ebb0  mov     rcx, [rbp+5Fh]; this
0x18000ebb4  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000ebbb  lea     edx, [rax+49h]; void *
0x18000ebbe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ebc3  mov     ebx, eax
0x18000ebc5  jmp     short loc_18000EC19
0x18000ebc7  cmp     eax, 2
0x18000ebca  jz      short loc_18000EC17
0x18000ebcc  mov     r8d, 0FFh; unsigned __int64
0x18000ebd2  lea     rcx, [rbp+57h+lpString1]; this
0x18000ebd6  mov     rdx, rdi; unsigned __int16 *
0x18000ebd9  call    ?Set@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Set(ushort const *,unsigned __int64)
0x18000ebde  mov     ebx, eax
0x18000ebe0  test    eax, eax
0x18000ebe2  jns     short loc_18000EBFE
0x18000ebe4  mov     edx, 4Dh ; 'M'; void *
0x18000ebe9  mov     r9d, eax; char *
0x18000ebec  mov     rcx, [rbp+5Fh]; this
0x18000ebf0  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000ebf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ebfc  jmp     short loc_18000EC19
0x18000ebfe  mov     rdx, rsi
0x18000ec01  lea     rcx, [rbp+57h+var_90]
0x18000ec05  call    ?Update@Protocol@Entity@StateRepository@@QEAAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::Protocol::Update(StateRepository::Database &,StateRepository::ExecutionFlags)
0x18000ec0a  mov     ebx, eax
0x18000ec0c  test    eax, eax
0x18000ec0e  jns     short loc_18000EC17
0x18000ec10  mov     edx, 4Eh ; 'N'
0x18000ec15  jmp     short loc_18000EBE9
0x18000ec17  xor     ebx, ebx
0x18000ec19  lea     rcx, [rbp+57h+var_90]; this
0x18000ec1d  call    ??1Protocol@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Protocol::~Protocol(void)
0x18000ec22  mov     eax, ebx
0x18000ec24  add     rsp, 0A8h
0x18000ec2b  pop     rdi
0x18000ec2c  pop     rsi
0x18000ec2d  pop     rbx
0x18000ec2e  pop     rbp
0x18000ec2f  retn
```
