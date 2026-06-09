# CIISTreeEnum::Create(CIISTreeEnum * *,ushort *,tagVARIANT,CCredentials &)

- ea: `0x180003bb8`
- end: `0x180003db3`
- name: `?Create@CIISTreeEnum@@SAJPEAPEAV1@PEAGUtagVARIANT@@AEAVCCredentials@@@Z`
- size: `507`
- prototype: `static int(struct CIISTreeEnum **, unsigned __int16 *, struct tagVARIANT *__struct_ptr, struct CCredentials *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1800039e0`

## callees

- `0x1800010b0`
- `0x180003bb8`
- `0x18000d380`
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

- `ACTIVEDS!__imp_AllocADsStr` at `0x180003cc1`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180003cec`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180003d32`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180003cc1`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180003cec`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180003d32`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180003d66`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180003d80`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180003d66`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180003d80`

## pseudocode

```c
__int64 __fastcall CIISTreeEnum::Create(
        struct CIISTreeEnum **a1,
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
  *(_QWORD *)v9 = &CIISTreeEnum::`vftable';
  CCredentials::Initialize((CIISEnumVariant *)((char *)v9 + 32), 0, 0, 0);
  *((_QWORD *)v9 + 7) = 0;
  *((_QWORD *)v9 + 8) = 0;
  *((_QWORD *)v9 + 9) = 0;
  *((_QWORD *)v9 + 10) = 0;
  *((_DWORD *)v9 + 4) = 0;
  inited = ADsAllocString(a2, (char *)v9 + 24);
  if ( inited >= 0 )
  {
    v7 = (struct _objectinfo *)v21;
    memset_0(v21, 0, 0x230u);
    inited = ADsObject((struct CLexer *)v19, (struct _objectinfo *)v21);
    if ( inited >= 0 )
    {
      CCredentials::operator=((CIISEnumVariant *)((char *)v9 + 32), a4);
      v12 = pStr;
      *a1 = v9;
      v13 = AllocADsStr(v12);
      *((_QWORD *)v9 + 9) = v13;
      if ( !v13 )
        goto LABEL_11;
      inited = InitServerInfo(a4, v13, (struct IMSAdminBaseW **)v9 + 7, (struct IIsSchema **)v9 + 8);
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
        *((_QWORD *)v9 + 10) = v17;
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
0x180003bb8  mov     [rsp+arg_10], rbx
0x180003bbd  push    rbp
0x180003bbe  push    rsi
0x180003bbf  push    rdi
0x180003bc0  push    r12
0x180003bc2  push    r13
0x180003bc4  push    r14
0x180003bc6  push    r15
0x180003bc8  sub     rsp, 280h
0x180003bcf  mov     rax, cs:__security_cookie
0x180003bd6  xor     rax, rsp
0x180003bd9  mov     [rsp+2B8h+var_48], rax
0x180003be1  mov     r14, rdx
0x180003be4  mov     r12, rcx
0x180003be7  xor     edx, edx; Val
0x180003be9  lea     rcx, [rsp+2B8h+var_278]; void *
0x180003bee  mov     r8d, 230h; Size
0x180003bf4  mov     r15, r9
0x180003bf7  call    memset_0
0x180003bfc  xor     r13d, r13d
0x180003bff  lea     rcx, [rsp+2B8h+var_298]; this
0x180003c04  mov     rdx, r14; unsigned __int16 *
0x180003c07  mov     ebp, r13d
0x180003c0a  call    ??0CLexer@@QEAA@PEBG@Z; CLexer::CLexer(ushort const *)
0x180003c0f  lea     ecx, [r13+58h]; Size
0x180003c13  mov     [r12], r13
0x180003c17  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003c1c  mov     rdi, rax
0x180003c1f  test    rax, rax
0x180003c22  jz      loc_180003D6E
0x180003c28  mov     rcx, rax; this
0x180003c2b  mov     esi, r13d
0x180003c2e  call    ??0CIISEnumVariant@@QEAA@XZ; CIISEnumVariant::CIISEnumVariant(void)
0x180003c33  lea     rax, ??_7CIISTreeEnum@@6B@; const CIISTreeEnum::`vftable'
0x180003c3a  mov     [rdi+18h], r13
0x180003c3e  lea     rcx, [rdi+20h]; this
0x180003c42  mov     [rdi], rax
0x180003c45  xor     r9d, r9d; unsigned int
0x180003c48  xor     r8d, r8d; unsigned __int16 *
0x180003c4b  xor     edx, edx; unsigned __int16 *
0x180003c4d  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x180003c52  lea     rdx, [rdi+18h]
0x180003c56  mov     [rdi+38h], r13
0x180003c5a  mov     rcx, r14
0x180003c5d  mov     [rdi+40h], r13
0x180003c61  mov     [rdi+48h], r13
0x180003c65  mov     [rdi+50h], r13
0x180003c69  mov     [rdi+10h], r13d
0x180003c6d  call    ADsAllocString
0x180003c72  mov     ebx, eax
0x180003c74  test    eax, eax
0x180003c76  js      loc_180003D46
0x180003c7c  xor     edx, edx; Val
0x180003c7e  lea     rcx, [rsp+2B8h+var_278]; void *
0x180003c83  mov     r8d, 230h; Size
0x180003c89  lea     rbp, [rsp+2B8h+var_278]
0x180003c8e  call    memset_0
0x180003c93  lea     rdx, [rsp+2B8h+var_278]; struct _objectinfo *
0x180003c98  lea     rcx, [rsp+2B8h+var_298]; struct CLexer *
0x180003c9d  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x180003ca2  mov     ebx, eax
0x180003ca4  test    eax, eax
0x180003ca6  js      loc_180003D46
0x180003cac  lea     rcx, [rdi+20h]; this
0x180003cb0  mov     rdx, r15; struct CCredentials *
0x180003cb3  call    ??4CCredentials@@QEAAXAEBV0@@Z; CCredentials::operator=(CCredentials const &)
0x180003cb8  mov     rcx, [rsp+2B8h+pStr]; pStr
0x180003cbd  mov     [r12], rdi
0x180003cc1  call    cs:__imp_AllocADsStr
0x180003cc7  mov     [rdi+48h], rax
0x180003ccb  test    rax, rax
0x180003cce  jz      short loc_180003D41
0x180003cd0  lea     r9, [rdi+40h]; struct IIsSchema **
0x180003cd4  mov     rdx, rax; unsigned __int16 *
0x180003cd7  lea     r8, [rdi+38h]; struct IMSAdminBaseW **
0x180003cdb  mov     rcx, r15; struct CCredentials *
0x180003cde  call    ?InitServerInfo@@YAJAEAVCCredentials@@PEBGPEAPEAUIMSAdminBaseW@@PEAPEAVIIsSchema@@@Z; InitServerInfo(CCredentials &,ushort const *,IMSAdminBaseW * *,IIsSchema * *)
0x180003ce3  mov     ebx, eax
0x180003ce5  test    eax, eax
0x180003ce7  js      short loc_180003D46
0x180003ce9  mov     rcx, r14; pStr
0x180003cec  call    cs:__imp_AllocADsStr
0x180003cf2  mov     rsi, rax
0x180003cf5  test    rax, rax
0x180003cf8  jz      short loc_180003D41
0x180003cfa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003cfe  inc     rbx
0x180003d01  cmp     [rax+rbx*2], r13w
0x180003d06  jnz     short loc_180003CFE
0x180003d08  inc     rbx
0x180003d0b  xor     edx, edx; Val
0x180003d0d  mov     rcx, rsi; void *
0x180003d10  lea     r8, [rbx+rbx]; Size
0x180003d14  call    memset_0
0x180003d19  mov     r8, rbx; unsigned __int64
0x180003d1c  lea     rcx, [rsp+2B8h+var_278]; struct _objectinfo *
0x180003d21  mov     rdx, rsi; unsigned __int16 *
0x180003d24  call    ?BuildIISPathFromADsPath@@YAJPEAU_objectinfo@@PEAG_K@Z; BuildIISPathFromADsPath(_objectinfo *,ushort *,unsigned __int64)
0x180003d29  mov     ebx, eax
0x180003d2b  test    eax, eax
0x180003d2d  js      short loc_180003D46
0x180003d2f  mov     rcx, rsi; pStr
0x180003d32  call    cs:__imp_AllocADsStr
0x180003d38  mov     [rdi+50h], rax
0x180003d3c  test    rax, rax
0x180003d3f  jnz     short loc_180003D63
0x180003d41  mov     ebx, 8007000Eh
0x180003d46  mov     rax, [rdi]
0x180003d49  mov     edx, 1
0x180003d4e  mov     rcx, rdi
0x180003d51  mov     rax, [rax+38h]
0x180003d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d5a  mov     [r12], r13
0x180003d5e  test    rsi, rsi
0x180003d61  jz      short loc_180003D73
0x180003d63  mov     rcx, rsi; pStr
0x180003d66  call    cs:__imp_FreeADsStr
0x180003d6c  jmp     short loc_180003D73
0x180003d6e  mov     ebx, 8007000Eh
0x180003d73  mov     rcx, rbp; struct _objectinfo *
0x180003d76  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x180003d7b  mov     rcx, [rsp+2B8h+var_290]; pStr
0x180003d80  call    cs:__imp_FreeADsStr
0x180003d86  mov     eax, ebx
0x180003d88  mov     rcx, [rsp+2B8h+var_48]
0x180003d90  xor     rcx, rsp; StackCookie
0x180003d93  call    __security_check_cookie
0x180003d98  mov     rbx, [rsp+2B8h+arg_10]
0x180003da0  add     rsp, 280h
0x180003da7  pop     r15
0x180003da9  pop     r14
0x180003dab  pop     r13
0x180003dad  pop     r12
0x180003daf  pop     rdi
0x180003db0  pop     rsi
0x180003db1  pop     rbp
0x180003db2  retn
```
