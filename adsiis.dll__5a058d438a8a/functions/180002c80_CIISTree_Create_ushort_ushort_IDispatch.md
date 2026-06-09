# CIISTree::Create(ushort *,ushort *,IDispatch * *)

- ea: `0x180002c80`
- end: `0x180002d92`
- name: `?Create@CIISTree@@UEAAJPEAG0PEAPEAUIDispatch@@@Z`
- size: `274`
- prototype: `int(CIISTree *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180002c80`
- `0x18000549c`
- `0x18001364c`
- `0x18001608c`
- `0x1800160d0`
- `0x18001bc54`
- `0x18001d66a`
- `0x18001d6c0`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsStr` at `0x180002d61`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180002d61`

## pseudocode

```c
__int64 __fastcall CIISTree::Create(CIISTree *this, unsigned __int16 *a2, unsigned __int16 *a3, struct IDispatch **a4)
{
  int inited; // ebx
  _BYTE v10[8]; // [rsp+40h] [rbp-298h] BYREF
  LPWSTR pStr; // [rsp+48h] [rbp-290h]
  _BYTE v12[8]; // [rsp+60h] [rbp-278h] BYREF
  unsigned __int16 *v13; // [rsp+68h] [rbp-270h]

  if ( !a2 || !a3 || !a4 )
    return 2147500035LL;
  memset_0(v12, 0, 0x230u);
  CLexer::CLexer((CLexer *)v10, *((const unsigned __int16 **)this - 6));
  inited = ADsObject((struct CLexer *)v10, (struct _objectinfo *)v12);
  if ( inited >= 0 )
  {
    inited = InitServerInfo(
               (CIISTree *)((char *)this + 56),
               v13,
               (struct IMSAdminBaseW **)this + 10,
               (struct IIsSchema **)this + 11);
    if ( inited >= 0 )
    {
      inited = IIsSchema::ValidateClassName(*((IIsSchema **)this + 11), a2);
      if ( inited >= 0 )
        inited = CIISGenObject::CreateGenericObject(
                   *((const unsigned __int16 **)this - 6),
                   a3,
                   a2,
                   (CIISTree *)((char *)this + 56),
                   2u,
                   &IID_IDispatch,
                   (void **)a4);
    }
  }
  FreeADsStr(pStr);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180002c80  push    rbx
0x180002c82  push    rbp
0x180002c83  push    rsi
0x180002c84  push    rdi
0x180002c85  push    r12
0x180002c87  push    r14
0x180002c89  push    r15
0x180002c8b  sub     rsp, 2A0h
0x180002c92  mov     rax, cs:__security_cookie
0x180002c99  xor     rax, rsp
0x180002c9c  mov     [rsp+2D8h+var_48], rax
0x180002ca4  mov     r14, r9
0x180002ca7  mov     rbp, r8
0x180002caa  mov     rsi, rdx
0x180002cad  mov     rdi, rcx
0x180002cb0  test    rdx, rdx
0x180002cb3  jz      loc_180002D6B
0x180002cb9  test    r8, r8
0x180002cbc  jz      loc_180002D6B
0x180002cc2  test    r9, r9
0x180002cc5  jz      loc_180002D6B
0x180002ccb  xor     edx, edx; Val
0x180002ccd  lea     rcx, [rsp+2D8h+var_278]; void *
0x180002cd2  mov     r8d, 230h; Size
0x180002cd8  call    memset_0
0x180002cdd  mov     rdx, [rdi-30h]; unsigned __int16 *
0x180002ce1  lea     rcx, [rsp+2D8h+var_298]; this
0x180002ce6  call    ??0CLexer@@QEAA@PEBG@Z; CLexer::CLexer(ushort const *)
0x180002ceb  lea     rdx, [rsp+2D8h+var_278]; struct _objectinfo *
0x180002cf0  lea     rcx, [rsp+2D8h+var_298]; struct CLexer *
0x180002cf5  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x180002cfa  mov     ebx, eax
0x180002cfc  test    eax, eax
0x180002cfe  js      short loc_180002D5C
0x180002d00  mov     rdx, [rsp+2D8h+var_270]; unsigned __int16 *
0x180002d05  lea     r8, [rdi+50h]; struct IMSAdminBaseW **
0x180002d09  lea     r9, [rdi+58h]; struct IIsSchema **
0x180002d0d  lea     rcx, [rdi+38h]; struct CCredentials *
0x180002d11  call    ?InitServerInfo@@YAJAEAVCCredentials@@PEBGPEAPEAUIMSAdminBaseW@@PEAPEAVIIsSchema@@@Z; InitServerInfo(CCredentials &,ushort const *,IMSAdminBaseW * *,IIsSchema * *)
0x180002d16  mov     ebx, eax
0x180002d18  test    eax, eax
0x180002d1a  js      short loc_180002D5C
0x180002d1c  mov     rcx, [rdi+58h]; this
0x180002d20  mov     rdx, rsi; unsigned __int16 *
0x180002d23  call    ?ValidateClassName@IIsSchema@@QEAAJPEBG@Z; IIsSchema::ValidateClassName(ushort const *)
0x180002d28  mov     ebx, eax
0x180002d2a  test    eax, eax
0x180002d2c  js      short loc_180002D5C
0x180002d2e  mov     rcx, [rdi-30h]; unsigned __int16 *
0x180002d32  lea     rax, IID_IDispatch
0x180002d39  mov     [rsp+2D8h+var_2A8], r14; void **
0x180002d3e  lea     r9, [rdi+38h]; struct CCredentials *
0x180002d42  mov     [rsp+2D8h+var_2B0], rax; struct _GUID *
0x180002d47  mov     r8, rsi; unsigned __int16 *
0x180002d4a  mov     rdx, rbp; unsigned __int16 *
0x180002d4d  mov     [rsp+2D8h+var_2B8], 2; unsigned int
0x180002d55  call    ?CreateGenericObject@CIISGenObject@@SAJPEBG00AEAVCCredentials@@KAEBU_GUID@@PEAPEAX@Z; CIISGenObject::CreateGenericObject(ushort const *,ushort const *,ushort const *,CCredentials &,ulong,_GUID const &,void * *)
0x180002d5a  mov     ebx, eax
0x180002d5c  mov     rcx, [rsp+2D8h+pStr]; pStr
0x180002d61  call    cs:__imp_FreeADsStr
0x180002d67  mov     eax, ebx
0x180002d69  jmp     short loc_180002D70
0x180002d6b  mov     eax, 80004003h
0x180002d70  mov     rcx, [rsp+2D8h+var_48]
0x180002d78  xor     rcx, rsp; StackCookie
0x180002d7b  call    __security_check_cookie
0x180002d80  add     rsp, 2A0h
0x180002d87  pop     r15
0x180002d89  pop     r14
0x180002d8b  pop     r12
0x180002d8d  pop     rdi
0x180002d8e  pop     rsi
0x180002d8f  pop     rbp
0x180002d90  pop     rbx
0x180002d91  retn
```
