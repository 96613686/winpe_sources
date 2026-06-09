# CIISGenObjectEnum::Create(CIISGenObjectEnum * *,ushort *,tagVARIANT,CCredentials &)

- ea: `0x18000d638`
- end: `0x18000d833`
- name: `?Create@CIISGenObjectEnum@@SAJPEAPEAV1@PEAGUtagVARIANT@@AEAVCCredentials@@@Z`
- size: `507`
- prototype: `static int(struct CIISGenObjectEnum **, unsigned __int16 *, struct tagVARIANT *__struct_ptr, struct CCredentials *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180008000`

## callees

- `0x1800010b0`
- `0x18000d380`
- `0x18000d638`
- `0x18001364c`
- `0x1800152f0`
- `0x18001537c`
- `0x18001608c`
- `0x1800160d0`
- `0x1800195b8`
- `0x18001984c`
- `0x18001beb8`
- `0x18001d66a`
- `0x18001d6c0`
- `0x18001e010`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsStr` at `0x18000d741`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000d76c`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000d7b2`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000d741`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000d76c`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000d7b2`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000d7e6`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000d800`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000d7e6`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000d800`

## pseudocode

```c
__int64 __fastcall CIISGenObjectEnum::Create(
        struct CIISGenObjectEnum **a1,
        unsigned __int16 *a2,
        struct tagVARIANT *a3,
        struct CCredentials *a4)
{
  struct _objectinfo *v7; // rbp
  CIISEnumVariant *v8; // rax
  CIISEnumVariant *v9; // rdi
  unsigned __int16 *v10; // rsi
  int inited; // ebx
  const WCHAR *v12; // rcx
  const unsigned __int16 *v13; // rax
  LPWSTR v14; // rax
  __int64 v15; // rbx
  unsigned __int64 v16; // rbx
  LPWSTR v17; // rax
  _BYTE v19[8]; // [rsp+20h] [rbp-298h] BYREF
  LPWSTR v20; // [rsp+28h] [rbp-290h]
  _BYTE v21[8]; // [rsp+40h] [rbp-278h] BYREF
  LPCWSTR pStr; // [rsp+48h] [rbp-270h]

  memset_0(v21, 0, 0x230u);
  v7 = 0;
  CLexer::CLexer((CLexer *)v19, a2);
  *a1 = 0;
  v8 = (CIISEnumVariant *)operator new(0x58u);
  v9 = v8;
  if ( !v8 )
  {
    inited = -2147024882;
    goto LABEL_15;
  }
  v10 = 0;
  CIISEnumVariant::CIISEnumVariant(v8);
  *((_QWORD *)v9 + 3) = 0;
  *(_QWORD *)v9 = &CIISGenObjectEnum::`vftable';
  *((_QWORD *)v9 + 4) = 0;
  *((_QWORD *)v9 + 5) = 0;
  *((_QWORD *)v9 + 6) = 0;
  *((_QWORD *)v9 + 7) = 0;
  CCredentials::Initialize((CIISEnumVariant *)((char *)v9 + 64), 0, 0, 0);
  *((_DWORD *)v9 + 4) = 0;
  inited = ADsAllocString(a2, (char *)v9 + 24);
  if ( inited >= 0 )
  {
    v7 = (struct _objectinfo *)v21;
    memset_0(v21, 0, 0x230u);
    inited = ADsObject((struct CLexer *)v19, (struct _objectinfo *)v21);
    if ( inited >= 0 )
    {
      CCredentials::operator=((CIISEnumVariant *)((char *)v9 + 64), a4);
      v12 = pStr;
      *a1 = v9;
      v13 = AllocADsStr(v12);
      *((_QWORD *)v9 + 4) = v13;
      if ( !v13 )
        goto LABEL_11;
      inited = InitServerInfo(a4, v13, (struct IMSAdminBaseW **)v9 + 6, (struct IIsSchema **)v9 + 7);
      if ( inited < 0 )
        goto LABEL_12;
      v14 = AllocADsStr(a2);
      v10 = v14;
      if ( !v14 )
        goto LABEL_11;
      v15 = -1;
      do
        ++v15;
      while ( v14[v15] );
      v16 = v15 + 1;
      memset_0(v14, 0, 2 * v16);
      inited = BuildIISPathFromADsPath((struct _objectinfo *)v21, v10, v16);
      if ( inited >= 0 )
      {
        v17 = AllocADsStr(v10);
        *((_QWORD *)v9 + 5) = v17;
        if ( v17 )
        {
LABEL_13:
          FreeADsStr(v10);
          goto LABEL_15;
        }
LABEL_11:
        inited = -2147024882;
      }
    }
  }
LABEL_12:
  (*(void (__fastcall **)(CIISEnumVariant *, __int64))(*(_QWORD *)v9 + 56LL))(v9, 1);
  *a1 = 0;
  if ( v10 )
    goto LABEL_13;
LABEL_15:
  FreeObjectInfo(v7);
  FreeADsStr(v20);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000d638  mov     [rsp+arg_10], rbx
0x18000d63d  push    rbp
0x18000d63e  push    rsi
0x18000d63f  push    rdi
0x18000d640  push    r12
0x18000d642  push    r13
0x18000d644  push    r14
0x18000d646  push    r15
0x18000d648  sub     rsp, 280h
0x18000d64f  mov     rax, cs:__security_cookie
0x18000d656  xor     rax, rsp
0x18000d659  mov     [rsp+2B8h+var_48], rax
0x18000d661  mov     r14, rdx
0x18000d664  mov     r12, rcx
0x18000d667  xor     edx, edx; Val
0x18000d669  lea     rcx, [rsp+2B8h+var_278]; void *
0x18000d66e  mov     r8d, 230h; Size
0x18000d674  mov     r15, r9
0x18000d677  call    memset_0
0x18000d67c  xor     r13d, r13d
0x18000d67f  lea     rcx, [rsp+2B8h+var_298]; this
0x18000d684  mov     rdx, r14; unsigned __int16 *
0x18000d687  mov     ebp, r13d
0x18000d68a  call    ??0CLexer@@QEAA@PEBG@Z; CLexer::CLexer(ushort const *)
0x18000d68f  lea     ecx, [r13+58h]; Size
0x18000d693  mov     [r12], r13
0x18000d697  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d69c  mov     rdi, rax
0x18000d69f  test    rax, rax
0x18000d6a2  jz      loc_18000D7EE
0x18000d6a8  mov     rcx, rax; this
0x18000d6ab  mov     esi, r13d
0x18000d6ae  call    ??0CIISEnumVariant@@QEAA@XZ; CIISEnumVariant::CIISEnumVariant(void)
0x18000d6b3  lea     rax, ??_7CIISGenObjectEnum@@6B@; const CIISGenObjectEnum::`vftable'
0x18000d6ba  mov     [rdi+18h], r13
0x18000d6be  lea     rcx, [rdi+40h]; this
0x18000d6c2  mov     [rdi], rax
0x18000d6c5  xor     r9d, r9d; unsigned int
0x18000d6c8  mov     [rdi+20h], r13
0x18000d6cc  xor     r8d, r8d; unsigned __int16 *
0x18000d6cf  mov     [rdi+28h], r13
0x18000d6d3  xor     edx, edx; unsigned __int16 *
0x18000d6d5  mov     [rdi+30h], r13
0x18000d6d9  mov     [rdi+38h], r13
0x18000d6dd  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x18000d6e2  lea     rdx, [rdi+18h]
0x18000d6e6  mov     [rdi+10h], r13d
0x18000d6ea  mov     rcx, r14
0x18000d6ed  call    ADsAllocString
0x18000d6f2  mov     ebx, eax
0x18000d6f4  test    eax, eax
0x18000d6f6  js      loc_18000D7C6
0x18000d6fc  xor     edx, edx; Val
0x18000d6fe  lea     rcx, [rsp+2B8h+var_278]; void *
0x18000d703  mov     r8d, 230h; Size
0x18000d709  lea     rbp, [rsp+2B8h+var_278]
0x18000d70e  call    memset_0
0x18000d713  lea     rdx, [rsp+2B8h+var_278]; struct _objectinfo *
0x18000d718  lea     rcx, [rsp+2B8h+var_298]; struct CLexer *
0x18000d71d  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x18000d722  mov     ebx, eax
0x18000d724  test    eax, eax
0x18000d726  js      loc_18000D7C6
0x18000d72c  lea     rcx, [rdi+40h]; this
0x18000d730  mov     rdx, r15; struct CCredentials *
0x18000d733  call    ??4CCredentials@@QEAAXAEBV0@@Z; CCredentials::operator=(CCredentials const &)
0x18000d738  mov     rcx, [rsp+2B8h+pStr]; pStr
0x18000d73d  mov     [r12], rdi
0x18000d741  call    cs:__imp_AllocADsStr
0x18000d747  mov     [rdi+20h], rax
0x18000d74b  test    rax, rax
0x18000d74e  jz      short loc_18000D7C1
0x18000d750  lea     r9, [rdi+38h]; struct IIsSchema **
0x18000d754  mov     rdx, rax; unsigned __int16 *
0x18000d757  lea     r8, [rdi+30h]; struct IMSAdminBaseW **
0x18000d75b  mov     rcx, r15; struct CCredentials *
0x18000d75e  call    ?InitServerInfo@@YAJAEAVCCredentials@@PEBGPEAPEAUIMSAdminBaseW@@PEAPEAVIIsSchema@@@Z; InitServerInfo(CCredentials &,ushort const *,IMSAdminBaseW * *,IIsSchema * *)
0x18000d763  mov     ebx, eax
0x18000d765  test    eax, eax
0x18000d767  js      short loc_18000D7C6
0x18000d769  mov     rcx, r14; pStr
0x18000d76c  call    cs:__imp_AllocADsStr
0x18000d772  mov     rsi, rax
0x18000d775  test    rax, rax
0x18000d778  jz      short loc_18000D7C1
0x18000d77a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d77e  inc     rbx
0x18000d781  cmp     [rax+rbx*2], r13w
0x18000d786  jnz     short loc_18000D77E
0x18000d788  inc     rbx
0x18000d78b  xor     edx, edx; Val
0x18000d78d  mov     rcx, rsi; void *
0x18000d790  lea     r8, [rbx+rbx]; Size
0x18000d794  call    memset_0
0x18000d799  mov     r8, rbx; unsigned __int64
0x18000d79c  lea     rcx, [rsp+2B8h+var_278]; struct _objectinfo *
0x18000d7a1  mov     rdx, rsi; unsigned __int16 *
0x18000d7a4  call    ?BuildIISPathFromADsPath@@YAJPEAU_objectinfo@@PEAG_K@Z; BuildIISPathFromADsPath(_objectinfo *,ushort *,unsigned __int64)
0x18000d7a9  mov     ebx, eax
0x18000d7ab  test    eax, eax
0x18000d7ad  js      short loc_18000D7C6
0x18000d7af  mov     rcx, rsi; pStr
0x18000d7b2  call    cs:__imp_AllocADsStr
0x18000d7b8  mov     [rdi+28h], rax
0x18000d7bc  test    rax, rax
0x18000d7bf  jnz     short loc_18000D7E3
0x18000d7c1  mov     ebx, 8007000Eh
0x18000d7c6  mov     rax, [rdi]
0x18000d7c9  mov     edx, 1
0x18000d7ce  mov     rcx, rdi
0x18000d7d1  mov     rax, [rax+38h]
0x18000d7d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7da  mov     [r12], r13
0x18000d7de  test    rsi, rsi
0x18000d7e1  jz      short loc_18000D7F3
0x18000d7e3  mov     rcx, rsi; pStr
0x18000d7e6  call    cs:__imp_FreeADsStr
0x18000d7ec  jmp     short loc_18000D7F3
0x18000d7ee  mov     ebx, 8007000Eh
0x18000d7f3  mov     rcx, rbp; struct _objectinfo *
0x18000d7f6  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x18000d7fb  mov     rcx, [rsp+2B8h+var_290]; pStr
0x18000d800  call    cs:__imp_FreeADsStr
0x18000d806  mov     eax, ebx
0x18000d808  mov     rcx, [rsp+2B8h+var_48]
0x18000d810  xor     rcx, rsp; StackCookie
0x18000d813  call    __security_check_cookie
0x18000d818  mov     rbx, [rsp+2B8h+arg_10]
0x18000d820  add     rsp, 280h
0x18000d827  pop     r15
0x18000d829  pop     r14
0x18000d82b  pop     r13
0x18000d82d  pop     r12
0x18000d82f  pop     rdi
0x18000d830  pop     rsi
0x18000d831  pop     rbp
0x18000d832  retn
```
