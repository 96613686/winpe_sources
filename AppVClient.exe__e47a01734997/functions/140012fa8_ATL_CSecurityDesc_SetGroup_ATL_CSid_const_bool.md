# ATL::CSecurityDesc::SetGroup(ATL::CSid const &,bool)

- ea: `0x140012fa8`
- end: `0x1400130fb`
- name: `?SetGroup@CSecurityDesc@ATL@@QEAAXAEBVCSid@2@_N@Z`
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
- `0x140012fa8`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140013084`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140013084`
- `ADVAPI32!GetLengthSid` at `0x140013050`
- `ADVAPI32!GetLengthSid` at `0x140013050`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14001301f`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14001301f`
- `ADVAPI32!IsValidSid` at `0x140013043`
- `ADVAPI32!IsValidSid` at `0x140013043`
- `ADVAPI32!CopySid` at `0x140013070`
- `ADVAPI32!CopySid` at `0x140013070`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x140012fef`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x140012fef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140013093`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400130cd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400130ed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140013093`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400130cd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400130ed`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140013004`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001305a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140013004`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001305a`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetGroup(void **this, const struct ATL::CSid *a2, char a3)
{
  void *v5; // rcx
  void *v6; // rax
  char *v7; // rbx
  DWORD LengthSid; // ebp
  void *v9; // rax
  void *v10; // rsi
  int Error; // ebx
  int v12; // ebx
  PSID pGroup; // [rsp+40h] [rbp+8h] BYREF
  BOOL bGroupDefaulted; // [rsp+50h] [rbp+18h] BYREF

  LOBYTE(bGroupDefaulted) = a3;
  if ( this[1] )
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)this);
  v5 = this[1];
  pGroup = 0;
  if ( v5 )
  {
    bGroupDefaulted = 0;
    if ( !GetSecurityDescriptorGroup(v5, &pGroup, &bGroupDefaulted) )
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
    pGroup = 0;
  }
  if ( !*((_BYTE *)a2 + 76) || (v7 = (char *)a2 + 8, !IsValidSid(v7)) )
    ATL::AtlThrowImpl(-2147467259);
  LengthSid = GetLengthSid(v7);
  v9 = malloc(LengthSid);
  v10 = v9;
  if ( !v9 )
LABEL_17:
    ATL::AtlThrowImpl(-2147024882);
  if ( !CopySid(LengthSid, v9, v7) || !SetSecurityDescriptorGroup(this[1], v10, 0) )
  {
    v12 = ATL::AtlHresultFromLastError();
    free(v10);
    ATL::AtlThrowImpl(v12);
  }
  free(pGroup);
}

```

## disassembly

```asm
0x140012fa8  mov     [rsp+arg_8], rbx
0x140012fad  mov     byte ptr [rsp+bGroupDefaulted], r8b
0x140012fb2  push    rbp
0x140012fb3  push    rsi
0x140012fb4  push    rdi
0x140012fb5  sub     rsp, 20h
0x140012fb9  cmp     qword ptr [rcx+8], 0
0x140012fbe  mov     rbx, rdx
0x140012fc1  mov     rdi, rcx
0x140012fc4  jz      short loc_140012FCB
0x140012fc6  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x140012fcb  mov     rcx, [rdi+8]; pSecurityDescriptor
0x140012fcf  mov     [rsp+38h+pGroup], 0
0x140012fd8  test    rcx, rcx
0x140012fdb  jz      short loc_140012FFF
0x140012fdd  lea     r8, [rsp+38h+bGroupDefaulted]; lpbGroupDefaulted
0x140012fe2  mov     [rsp+38h+bGroupDefaulted], 0
0x140012fea  lea     rdx, [rsp+38h+pGroup]; pGroup
0x140012fef  call    cs:__imp_GetSecurityDescriptorGroup
0x140012ff5  test    eax, eax
0x140012ff7  jz      loc_1400130B1
0x140012ffd  jmp     short loc_140013036
0x140012fff  mov     ecx, 28h ; '('; Size
0x140013004  call    cs:__imp_malloc
0x14001300a  mov     [rdi+8], rax
0x14001300e  test    rax, rax
0x140013011  jz      loc_1400130B7
0x140013017  mov     edx, 1; dwRevision
0x14001301c  mov     rcx, rax; pSecurityDescriptor
0x14001301f  call    cs:__imp_InitializeSecurityDescriptor
0x140013025  test    eax, eax
0x140013027  jz      loc_1400130C2
0x14001302d  mov     [rsp+38h+pGroup], 0
0x140013036  cmp     byte ptr [rbx+4Ch], 0
0x14001303a  jz      short loc_1400130A6
0x14001303c  add     rbx, 8
0x140013040  mov     rcx, rbx; pSid
0x140013043  call    cs:__imp_IsValidSid
0x140013049  test    eax, eax
0x14001304b  jz      short loc_1400130A6
0x14001304d  mov     rcx, rbx; pSid
0x140013050  call    cs:__imp_GetLengthSid
0x140013056  mov     ecx, eax; Size
0x140013058  mov     ebp, eax
0x14001305a  call    cs:__imp_malloc
0x140013060  mov     rsi, rax
0x140013063  test    rax, rax
0x140013066  jz      short loc_1400130B7
0x140013068  mov     r8, rbx; pSourceSid
0x14001306b  mov     rdx, rax; pDestinationSid
0x14001306e  mov     ecx, ebp; nDestinationSidLength
0x140013070  call    cs:__imp_CopySid
0x140013076  test    eax, eax
0x140013078  jz      short loc_1400130E3
0x14001307a  mov     rcx, [rdi+8]; pSecurityDescriptor
0x14001307e  xor     r8d, r8d; bGroupDefaulted
0x140013081  mov     rdx, rsi; pGroup
0x140013084  call    cs:__imp_SetSecurityDescriptorGroup
0x14001308a  test    eax, eax
0x14001308c  jz      short loc_1400130E3
0x14001308e  mov     rcx, [rsp+38h+pGroup]; Block
0x140013093  call    cs:__imp_free
0x140013099  mov     rbx, [rsp+38h+arg_8]
0x14001309e  add     rsp, 20h
0x1400130a2  pop     rdi
0x1400130a3  pop     rsi
0x1400130a4  pop     rbp
0x1400130a5  retn
0x1400130a6  mov     ecx, 80004005h; int
0x1400130ab  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400130b1  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1400130b7  mov     ecx, 8007000Eh; int
0x1400130bc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400130c2  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1400130c7  mov     rcx, [rdi+8]; Block
0x1400130cb  mov     ebx, eax
0x1400130cd  call    cs:__imp_free
0x1400130d3  mov     ecx, ebx; int
0x1400130d5  mov     qword ptr [rdi+8], 0
0x1400130dd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400130e3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1400130e8  mov     rcx, rsi; Block
0x1400130eb  mov     ebx, eax
0x1400130ed  call    cs:__imp_free
0x1400130f3  mov     ecx, ebx; int
0x1400130f5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
