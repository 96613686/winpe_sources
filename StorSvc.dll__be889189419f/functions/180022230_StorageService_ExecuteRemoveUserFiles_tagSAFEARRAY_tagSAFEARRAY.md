# StorageService::ExecuteRemoveUserFiles(tagSAFEARRAY *,tagSAFEARRAY *)

- ea: `0x180022230`
- end: `0x180022403`
- name: `?ExecuteRemoveUserFiles@StorageService@@QEAAJPEAUtagSAFEARRAY@@0@Z`
- size: `467`
- prototype: `__int64 __fastcall(StorageService *this, struct tagSAFEARRAY *, struct tagSAFEARRAY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x1800373f0`

## callees

- `0x180012734`
- `0x18001fcac`
- `0x180022230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002237b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002237b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180022371`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180022371`
- `RPCRT4!RpcRevertToSelf` at `0x18002228e`
- `RPCRT4!RpcRevertToSelf` at `0x1800223d6`
- `RPCRT4!RpcRevertToSelf` at `0x1800223eb`
- `RPCRT4!RpcRevertToSelf` at `0x18002228e`
- `RPCRT4!RpcRevertToSelf` at `0x1800223d6`
- `RPCRT4!RpcRevertToSelf` at `0x1800223eb`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800222ec`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180022338`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800222ec`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180022338`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800222cd`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180022316`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800222cd`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180022316`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002225e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800222a6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002225e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800222a6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002239c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800223b5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002239c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800223b5`

## string_xrefs

- `0x18002226f`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageService::ExecuteRemoveUserFiles(
        StorageService *this,
        struct tagSAFEARRAY *a2,
        struct tagSAFEARRAY *a3)
{
  HRESULT LBound; // ebx
  __int64 v6; // rdx
  char v7; // cl
  LONG v9; // ebx
  char v10; // al
  char v11; // al
  int v12; // [rsp+20h] [rbp-38h] BYREF
  LONG plUbound; // [rsp+24h] [rbp-34h] BYREF
  LONG plLbound; // [rsp+28h] [rbp-30h] BYREF
  LONG v15; // [rsp+2Ch] [rbp-2Ch] BYREF
  LONG v16; // [rsp+30h] [rbp-28h] BYREF
  void *v17; // [rsp+38h] [rbp-20h] BYREF
  void *ppvData; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]

  AutoRpcImpersonateClient(&v12);
  ppvData = 0;
  LBound = SafeArrayAccessData(a2, &ppvData);
  if ( LBound < 0 )
  {
    v6 = 1849;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
      (const char *)(unsigned int)LBound,
      v12);
    v7 = v12;
    LOBYTE(v12) = 0;
    if ( v7 )
      RpcRevertToSelf();
    return (unsigned int)LBound;
  }
  v17 = 0;
  LBound = SafeArrayAccessData(a3, &v17);
  if ( LBound < 0 )
  {
    v6 = 1853;
    goto LABEL_3;
  }
  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(a2, 1u, &plLbound);
  if ( LBound < 0 )
  {
    v6 = 1856;
    goto LABEL_3;
  }
  LBound = SafeArrayGetUBound(a2, 1u, &plUbound);
  if ( LBound < 0 )
  {
    v6 = 1857;
    goto LABEL_3;
  }
  v15 = 0;
  v16 = 0;
  LBound = SafeArrayGetLBound(a3, 1u, &v15);
  if ( LBound < 0 )
  {
    v6 = 1860;
    goto LABEL_3;
  }
  LBound = SafeArrayGetUBound(a3, 1u, &v16);
  if ( LBound < 0 )
  {
    v6 = 1861;
    goto LABEL_3;
  }
  v9 = plLbound;
  if ( v15 == plLbound && v16 == plUbound )
  {
    if ( plLbound <= plUbound )
    {
      do
      {
        if ( DeleteFileW(*((LPCWSTR *)ppvData + v9)) )
          *((_DWORD *)v17 + v9) = 0;
        else
          *((_DWORD *)v17 + v9) = GetLastError();
        ++v9;
      }
      while ( v9 <= plUbound );
    }
    LBound = SafeArrayUnaccessData(a2);
    if ( LBound < 0 )
    {
      v6 = 1881;
      goto LABEL_3;
    }
    LBound = SafeArrayUnaccessData(a3);
    if ( LBound < 0 )
    {
      v6 = 1882;
      goto LABEL_3;
    }
    v10 = v12;
    LOBYTE(v12) = 0;
    if ( v10 )
      RpcRevertToSelf();
    return 0;
  }
  else
  {
    v11 = v12;
    LOBYTE(v12) = 0;
    if ( v11 )
      RpcRevertToSelf();
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180022230  push    rbp
0x180022232  push    rbx
0x180022233  push    rsi
0x180022234  push    rdi
0x180022235  push    r14
0x180022237  push    r15
0x180022239  mov     rbp, rsp
0x18002223c  sub     rsp, 58h
0x180022240  mov     rdi, r8
0x180022243  mov     r14, rdx
0x180022246  lea     rcx, [rbp+var_38]
0x18002224a  call    ?AutoRpcImpersonateClient@@YA?AV?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@XZ; AutoRpcImpersonateClient(void)
0x18002224f  nop
0x180022250  xor     r15d, r15d
0x180022253  mov     [rbp+ppvData], r15
0x180022257  lea     rdx, [rbp+ppvData]; ppvData
0x18002225b  mov     rcx, r14; psa
0x18002225e  call    cs:__imp_SafeArrayAccessData
0x180022264  mov     ebx, eax
0x180022266  test    eax, eax
0x180022268  jns     short loc_18002229B
0x18002226a  mov     edx, 739h; void *
0x18002226f  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180022276  mov     r9d, ebx; char *
0x180022279  mov     rcx, [rbp+30h]; this
0x18002227d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022282  nop
0x180022283  mov     cl, byte ptr [rbp+var_38]
0x180022286  mov     byte ptr [rbp+var_38], r15b
0x18002228a  test    cl, cl
0x18002228c  jz      short loc_180022294
0x18002228e  call    cs:__imp_RpcRevertToSelf
0x180022294  mov     eax, ebx
0x180022296  jmp     loc_1800223F6
0x18002229b  mov     [rbp+var_20], r15
0x18002229f  lea     rdx, [rbp+var_20]; ppvData
0x1800222a3  mov     rcx, rdi; psa
0x1800222a6  call    cs:__imp_SafeArrayAccessData
0x1800222ac  mov     ebx, eax
0x1800222ae  test    eax, eax
0x1800222b0  jns     short loc_1800222B9
0x1800222b2  mov     edx, 73Dh
0x1800222b7  jmp     short loc_18002226F
0x1800222b9  mov     [rbp+plLbound], r15d
0x1800222bd  mov     [rbp+plUbound], r15d
0x1800222c1  lea     r8, [rbp+plLbound]; plLbound
0x1800222c5  mov     edx, 1; nDim
0x1800222ca  mov     rcx, r14; psa
0x1800222cd  call    cs:__imp_SafeArrayGetLBound
0x1800222d3  mov     ebx, eax
0x1800222d5  test    eax, eax
0x1800222d7  jns     short loc_1800222E0
0x1800222d9  mov     edx, 740h
0x1800222de  jmp     short loc_18002226F
0x1800222e0  lea     r8, [rbp+plUbound]; plUbound
0x1800222e4  mov     edx, 1; nDim
0x1800222e9  mov     rcx, r14; psa
0x1800222ec  call    cs:__imp_SafeArrayGetUBound
0x1800222f2  mov     ebx, eax
0x1800222f4  test    eax, eax
0x1800222f6  jns     short loc_180022302
0x1800222f8  mov     edx, 741h
0x1800222fd  jmp     loc_18002226F
0x180022302  mov     [rbp+var_2C], r15d
0x180022306  mov     [rbp+var_28], r15d
0x18002230a  lea     r8, [rbp+var_2C]; plLbound
0x18002230e  mov     edx, 1; nDim
0x180022313  mov     rcx, rdi; psa
0x180022316  call    cs:__imp_SafeArrayGetLBound
0x18002231c  mov     ebx, eax
0x18002231e  test    eax, eax
0x180022320  jns     short loc_18002232C
0x180022322  mov     edx, 744h
0x180022327  jmp     loc_18002226F
0x18002232c  lea     r8, [rbp+var_28]; plUbound
0x180022330  mov     edx, 1; nDim
0x180022335  mov     rcx, rdi; psa
0x180022338  call    cs:__imp_SafeArrayGetUBound
0x18002233e  mov     ebx, eax
0x180022340  test    eax, eax
0x180022342  jns     short loc_18002234E
0x180022344  mov     edx, 745h
0x180022349  jmp     loc_18002226F
0x18002234e  mov     ebx, [rbp+plLbound]
0x180022351  cmp     [rbp+var_2C], ebx
0x180022354  jnz     loc_1800223E0
0x18002235a  mov     eax, [rbp+plUbound]
0x18002235d  cmp     [rbp+var_28], eax
0x180022360  jnz     short loc_1800223E0
0x180022362  cmp     ebx, eax
0x180022364  jg      short loc_180022399
0x180022366  movsxd  rsi, ebx
0x180022369  mov     rcx, [rbp+ppvData]
0x18002236d  mov     rcx, [rcx+rsi*8]; lpFileName
0x180022371  call    cs:__imp_DeleteFileW
0x180022377  test    eax, eax
0x180022379  jnz     short loc_18002238A
0x18002237b  call    cs:__imp_GetLastError
0x180022381  mov     rcx, [rbp+var_20]
0x180022385  mov     [rcx+rsi*4], eax
0x180022388  jmp     short loc_180022392
0x18002238a  mov     rax, [rbp+var_20]
0x18002238e  mov     [rax+rsi*4], r15d
0x180022392  inc     ebx
0x180022394  cmp     ebx, [rbp+plUbound]
0x180022397  jle     short loc_180022366
0x180022399  mov     rcx, r14; psa
0x18002239c  call    cs:__imp_SafeArrayUnaccessData
0x1800223a2  mov     ebx, eax
0x1800223a4  test    eax, eax
0x1800223a6  jns     short loc_1800223B2
0x1800223a8  mov     edx, 759h
0x1800223ad  jmp     loc_18002226F
0x1800223b2  mov     rcx, rdi; psa
0x1800223b5  call    cs:__imp_SafeArrayUnaccessData
0x1800223bb  mov     ebx, eax
0x1800223bd  test    eax, eax
0x1800223bf  jns     short loc_1800223CB
0x1800223c1  mov     edx, 75Ah
0x1800223c6  jmp     loc_18002226F
0x1800223cb  mov     al, byte ptr [rbp+var_38]
0x1800223ce  mov     byte ptr [rbp+var_38], r15b
0x1800223d2  test    al, al
0x1800223d4  jz      short loc_1800223DC
0x1800223d6  call    cs:__imp_RpcRevertToSelf
0x1800223dc  xor     eax, eax
0x1800223de  jmp     short loc_1800223F6
0x1800223e0  mov     al, byte ptr [rbp+var_38]
0x1800223e3  mov     byte ptr [rbp+var_38], r15b
0x1800223e7  test    al, al
0x1800223e9  jz      short loc_1800223F1
0x1800223eb  call    cs:__imp_RpcRevertToSelf
0x1800223f1  mov     eax, 80070057h
0x1800223f6  add     rsp, 58h
0x1800223fa  pop     r15
0x1800223fc  pop     r14
0x1800223fe  pop     rdi
0x1800223ff  pop     rsi
0x180022400  pop     rbx
0x180022401  pop     rbp
0x180022402  retn
```
