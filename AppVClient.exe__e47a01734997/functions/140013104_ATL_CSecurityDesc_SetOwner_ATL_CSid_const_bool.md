# ATL::CSecurityDesc::SetOwner(ATL::CSid const &,bool)

- ea: `0x140013104`
- end: `0x140013257`
- name: `?SetOwner@CSecurityDesc@ATL@@QEAAXAEBVCSid@2@_N@Z`
- size: `339`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this, const struct ATL::CSid *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a5a0`

## callees

- `0x14000a220`
- `0x14000a2e8`
- `0x14000a310`
- `0x140010a58`
- `0x140013104`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x1400131ac`
- `ADVAPI32!GetLengthSid` at `0x1400131ac`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14001317b`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14001317b`
- `ADVAPI32!IsValidSid` at `0x14001319f`
- `ADVAPI32!IsValidSid` at `0x14001319f`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x14001314b`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x14001314b`
- `ADVAPI32!CopySid` at `0x1400131cc`
- `ADVAPI32!CopySid` at `0x1400131cc`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1400131e0`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1400131e0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400131ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140013229`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140013249`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400131ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140013229`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140013249`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140013160`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400131b6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140013160`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400131b6`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetOwner(void **this, const struct ATL::CSid *a2, char a3)
{
  void *v5; // rcx
  void *v6; // rax
  char *v7; // rbx
  DWORD LengthSid; // ebp
  void *v9; // rax
  void *v10; // rsi
  int Error; // ebx
  int v12; // ebx
  PSID pOwner; // [rsp+40h] [rbp+8h] BYREF
  BOOL bOwnerDefaulted; // [rsp+50h] [rbp+18h] BYREF

  LOBYTE(bOwnerDefaulted) = a3;
  if ( this[1] )
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)this);
  v5 = this[1];
  pOwner = 0;
  if ( v5 )
  {
    bOwnerDefaulted = 0;
    if ( !GetSecurityDescriptorOwner(v5, &pOwner, &bOwnerDefaulted) )
      ATL::AtlThrowLastWin32();
  }
  else
  {
    v6 = malloc(0x28u);
    this[1] = v6;
    if ( !v6 )
      goto LABEL_17;
    if ( !InitializeSecurityDescriptor(v6, 1u) )
    {
      Error = ATL::AtlHresultFromLastError();
      free(this[1]);
      this[1] = 0;
      ATL::AtlThrowImpl(Error);
    }
    pOwner = 0;
  }
  if ( !*((_BYTE *)a2 + 76) || (v7 = (char *)a2 + 8, !IsValidSid(v7)) )
    ATL::AtlThrowImpl(-2147467259);
  LengthSid = GetLengthSid(v7);
  v9 = malloc(LengthSid);
  v10 = v9;
  if ( !v9 )
LABEL_17:
    ATL::AtlThrowImpl(-2147024882);
  if ( !CopySid(LengthSid, v9, v7) || !SetSecurityDescriptorOwner(this[1], v10, 0) )
  {
    v12 = ATL::AtlHresultFromLastError();
    free(v10);
    ATL::AtlThrowImpl(v12);
  }
  free(pOwner);
}

```

## disassembly

```asm
0x140013104  mov     [rsp+arg_8], rbx
0x140013109  mov     byte ptr [rsp+bOwnerDefaulted], r8b
0x14001310e  push    rbp
0x14001310f  push    rsi
0x140013110  push    rdi
0x140013111  sub     rsp, 20h
0x140013115  cmp     qword ptr [rcx+8], 0
0x14001311a  mov     rbx, rdx
0x14001311d  mov     rdi, rcx
0x140013120  jz      short loc_140013127
0x140013122  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x140013127  mov     rcx, [rdi+8]; pSecurityDescriptor
0x14001312b  mov     [rsp+38h+pOwner], 0
0x140013134  test    rcx, rcx
0x140013137  jz      short loc_14001315B
0x140013139  lea     r8, [rsp+38h+bOwnerDefaulted]; lpbOwnerDefaulted
0x14001313e  mov     [rsp+38h+bOwnerDefaulted], 0
0x140013146  lea     rdx, [rsp+38h+pOwner]; pOwner
0x14001314b  call    cs:__imp_GetSecurityDescriptorOwner
0x140013151  test    eax, eax
0x140013153  jz      loc_14001320D
0x140013159  jmp     short loc_140013192
0x14001315b  mov     ecx, 28h ; '('; Size
0x140013160  call    cs:__imp_malloc
0x140013166  mov     [rdi+8], rax
0x14001316a  test    rax, rax
0x14001316d  jz      loc_140013213
0x140013173  mov     edx, 1; dwRevision
0x140013178  mov     rcx, rax; pSecurityDescriptor
0x14001317b  call    cs:__imp_InitializeSecurityDescriptor
0x140013181  test    eax, eax
0x140013183  jz      loc_14001321E
0x140013189  mov     [rsp+38h+pOwner], 0
0x140013192  cmp     byte ptr [rbx+4Ch], 0
0x140013196  jz      short loc_140013202
0x140013198  add     rbx, 8
0x14001319c  mov     rcx, rbx; pSid
0x14001319f  call    cs:__imp_IsValidSid
0x1400131a5  test    eax, eax
0x1400131a7  jz      short loc_140013202
0x1400131a9  mov     rcx, rbx; pSid
0x1400131ac  call    cs:__imp_GetLengthSid
0x1400131b2  mov     ecx, eax; Size
0x1400131b4  mov     ebp, eax
0x1400131b6  call    cs:__imp_malloc
0x1400131bc  mov     rsi, rax
0x1400131bf  test    rax, rax
0x1400131c2  jz      short loc_140013213
0x1400131c4  mov     r8, rbx; pSourceSid
0x1400131c7  mov     rdx, rax; pDestinationSid
0x1400131ca  mov     ecx, ebp; nDestinationSidLength
0x1400131cc  call    cs:__imp_CopySid
0x1400131d2  test    eax, eax
0x1400131d4  jz      short loc_14001323F
0x1400131d6  mov     rcx, [rdi+8]; pSecurityDescriptor
0x1400131da  xor     r8d, r8d; bOwnerDefaulted
0x1400131dd  mov     rdx, rsi; pOwner
0x1400131e0  call    cs:__imp_SetSecurityDescriptorOwner
0x1400131e6  test    eax, eax
0x1400131e8  jz      short loc_14001323F
0x1400131ea  mov     rcx, [rsp+38h+pOwner]; Block
0x1400131ef  call    cs:__imp_free
0x1400131f5  mov     rbx, [rsp+38h+arg_8]
0x1400131fa  add     rsp, 20h
0x1400131fe  pop     rdi
0x1400131ff  pop     rsi
0x140013200  pop     rbp
0x140013201  retn
0x140013202  mov     ecx, 80004005h; int
0x140013207  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001320d  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x140013213  mov     ecx, 8007000Eh; int
0x140013218  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001321e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140013223  mov     rcx, [rdi+8]; Block
0x140013227  mov     ebx, eax
0x140013229  call    cs:__imp_free
0x14001322f  mov     ecx, ebx; int
0x140013231  mov     qword ptr [rdi+8], 0
0x140013239  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001323f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140013244  mov     rcx, rsi; Block
0x140013247  mov     ebx, eax
0x140013249  call    cs:__imp_free
0x14001324f  mov     ecx, ebx; int
0x140013251  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
