# FixAppUriHandlerProgId

- ea: `0x18000e85c`
- end: `0x18000e993`
- name: `FixAppUriHandlerProgId`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e438`

## callees

- `0x18000a3a0`
- `0x18000a3c0`
- `0x18000e1f4`
- `0x18000e85c`
- `0x1800148ec`
- `0x180020594`
- `0x180020664`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e907`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e907`

## string_xrefs

- `0x18000e915`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000e953`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000e8d9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appurihandler.cpp`

## pseudocode

```c
__int64 __fastcall FixAppUriHandlerProgId(struct StateRepository::Database *a1, __int64 a2, const WCHAR *a3)
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
  LPCWCH lpString1[2]; // [rsp+70h] [rbp+7h] BYREF
  __int128 v20; // [rsp+80h] [rbp+17h]
  __int128 v21; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  bool v23; // [rsp+E8h] [rbp+7Fh] BYREF

  v15[0] = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  *(_OWORD *)lpString1 = 0;
  v20 = 0;
  v21 = 0;
  v15[1] = 0;
  v23 = 0;
  LastError = StateRepository::Entity::AppUriHandler::TryGet(
                a1,
                a2,
                (struct StateRepository::Entity::AppUriHandler *)v15,
                &v23);
  if ( (LastError & 0x80000000) != 0 )
  {
    v6 = 415;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appurihandler.cpp",
      (const char *)LastError,
      bIgnoreCase);
    v7 = LastError;
    v8 = 196;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)v7,
      bIgnoreCasea);
    goto LABEL_16;
  }
  if ( !v23 )
  {
    LastError = -2147023728;
    v6 = 416;
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
        v8 = 202;
LABEL_11:
        v7 = (unsigned int)v11;
        goto LABEL_12;
      }
      v11 = StateRepository::Entity::AppUriHandler::Update(v15, a1);
      LastError = v11;
      if ( v11 < 0 )
      {
        v8 = 203;
        goto LABEL_11;
      }
    }
    LastError = 0;
    goto LABEL_16;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0xC6,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
                v10);
LABEL_16:
  StateRepository::Entity::AppUriHandler::~AppUriHandler((StateRepository::Entity::AppUriHandler *)v15);
  return LastError;
}

```

## disassembly

```asm
0x18000e85c  push    rbp
0x18000e85e  push    rbx
0x18000e85f  push    rsi
0x18000e860  push    rdi
0x18000e861  lea     rbp, [rsp-3Fh]
0x18000e866  sub     rsp, 0A8h
0x18000e86d  xorps   xmm0, xmm0
0x18000e870  mov     [rbp+57h+var_90], 0
0x18000e878  xorps   xmm1, xmm1
0x18000e87b  movdqa  [rbp+57h+var_80], xmm0
0x18000e880  mov     rdi, r8
0x18000e883  movdqa  [rbp+57h+var_70], xmm1
0x18000e888  lea     r8, [rbp+57h+var_90]; struct StateRepository::Entity::AppUriHandler *
0x18000e88c  movdqa  [rbp+57h+var_60], xmm0
0x18000e891  lea     r9, [rbp+57h+arg_18]; bool *
0x18000e895  movdqa  xmmword ptr [rbp+57h+lpString1], xmm1
0x18000e89a  movdqa  [rbp+57h+var_40], xmm0
0x18000e89f  mov     rsi, rcx
0x18000e8a2  movdqa  [rbp+57h+var_30], xmm1
0x18000e8a7  mov     [rbp+57h+var_88], 0
0x18000e8af  mov     [rbp+57h+arg_18], 0
0x18000e8b3  call    ?TryGet@AppUriHandler@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAV123@AEA_N@Z; StateRepository::Entity::AppUriHandler::TryGet(StateRepository::Database &,__int64,StateRepository::Entity::AppUriHandler &,bool &)
0x18000e8b8  mov     ebx, eax
0x18000e8ba  test    eax, eax
0x18000e8bc  jns     short loc_18000E8C5
0x18000e8be  mov     edx, 19Fh
0x18000e8c3  jmp     short loc_18000E8D5
0x18000e8c5  cmp     [rbp+57h+arg_18], 0
0x18000e8c9  jnz     short loc_18000E8F2
0x18000e8cb  mov     ebx, 80070490h
0x18000e8d0  mov     edx, 1A0h; void *
0x18000e8d5  mov     rcx, [rbp+5Fh]; this
0x18000e8d9  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\staterepositor"...
0x18000e8e0  mov     r9d, ebx; char *
0x18000e8e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e8e8  mov     r9d, ebx
0x18000e8eb  mov     edx, 0C4h
0x18000e8f0  jmp     short loc_18000E94F
0x18000e8f2  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18000e8f6  or      edx, 0FFFFFFFFh; cchCount1
0x18000e8f9  mov     r9d, edx; cchCount2
0x18000e8fc  mov     [rsp+0C0h+bIgnoreCase], 0; int
0x18000e904  mov     r8, rdi; lpString2
0x18000e907  call    cs:__imp_CompareStringOrdinal
0x18000e90d  test    eax, eax
0x18000e90f  jnz     short loc_18000E92A
0x18000e911  mov     rcx, [rbp+5Fh]; this
0x18000e915  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000e91c  mov     edx, 0C6h; void *
0x18000e921  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e926  mov     ebx, eax
0x18000e928  jmp     short loc_18000E97C
0x18000e92a  cmp     eax, 2
0x18000e92d  jz      short loc_18000E97A
0x18000e92f  mov     r8d, 0FFh; unsigned __int64
0x18000e935  lea     rcx, [rbp+57h+lpString1]; this
0x18000e939  mov     rdx, rdi; unsigned __int16 *
0x18000e93c  call    ?Set@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Set(ushort const *,unsigned __int64)
0x18000e941  mov     ebx, eax
0x18000e943  test    eax, eax
0x18000e945  jns     short loc_18000E961
0x18000e947  mov     edx, 0CAh; void *
0x18000e94c  mov     r9d, eax; char *
0x18000e94f  mov     rcx, [rbp+5Fh]; this
0x18000e953  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000e95a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e95f  jmp     short loc_18000E97C
0x18000e961  mov     rdx, rsi
0x18000e964  lea     rcx, [rbp+57h+var_90]
0x18000e968  call    ?Update@AppUriHandler@Entity@StateRepository@@QEAAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::AppUriHandler::Update(StateRepository::Database &,StateRepository::ExecutionFlags)
0x18000e96d  mov     ebx, eax
0x18000e96f  test    eax, eax
0x18000e971  jns     short loc_18000E97A
0x18000e973  mov     edx, 0CBh
0x18000e978  jmp     short loc_18000E94C
0x18000e97a  xor     ebx, ebx
0x18000e97c  lea     rcx, [rbp+57h+var_90]; this
0x18000e980  call    ??1AppUriHandler@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::AppUriHandler::~AppUriHandler(void)
0x18000e985  mov     eax, ebx
0x18000e987  add     rsp, 0A8h
0x18000e98e  pop     rdi
0x18000e98f  pop     rsi
0x18000e990  pop     rbx
0x18000e991  pop     rbp
0x18000e992  retn
```
