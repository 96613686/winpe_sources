# CIISGenObject::CacheMetaDataPath(void)

- ea: `0x18000474c`
- end: `0x1800048e0`
- name: `?CacheMetaDataPath@CIISGenObject@@QEAAJXZ`
- size: `404`
- prototype: `__int64 __fastcall(CIISGenObject *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000549c`
- `0x180005830`
- `0x180005cd0`

## callees

- `0x18000474c`
- `0x18001364c`
- `0x1800152f0`
- `0x18001537c`
- `0x18001608c`
- `0x1800160d0`
- `0x18001b5ec`
- `0x18001d66a`
- `0x18001d6c0`
- `0x18001e010`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsStr` at `0x1800047d0`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000483e`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180004888`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800047d0`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000483e`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180004888`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800047c5`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000487f`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800048a7`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800048bc`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800047c5`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000487f`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800048a7`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800048bc`

## pseudocode

```c
__int64 __fastcall CIISGenObject::CacheMetaDataPath(CIISGenObject *this)
{
  int inited; // ebx
  WCHAR *v3; // rcx
  LPWSTR v4; // rax
  __int64 v5; // rcx
  IIsSchema *v6; // rcx
  LPWSTR v7; // rax
  WCHAR *v8; // rsi
  __int64 v9; // r8
  WCHAR *v10; // rcx
  LPWSTR v11; // rax
  int v12; // ecx
  _BYTE v14[8]; // [rsp+20h] [rbp-288h] BYREF
  LPWSTR v15; // [rsp+28h] [rbp-280h]
  _BYTE v16[8]; // [rsp+40h] [rbp-268h] BYREF
  LPCWSTR pStr; // [rsp+48h] [rbp-260h]

  memset_0(v16, 0, 0x230u);
  CLexer::CLexer((CLexer *)v14, *((const unsigned __int16 **)this + 3));
  memset_0(v16, 0, 0x230u);
  inited = ADsObject((struct CLexer *)v14, (struct _objectinfo *)v16);
  if ( inited >= 0 )
  {
    v3 = (WCHAR *)*((_QWORD *)this + 17);
    if ( v3 )
      FreeADsStr(v3);
    v4 = AllocADsStr(pStr);
    *((_QWORD *)this + 17) = v4;
    if ( !v4 )
      goto LABEL_5;
    v5 = *((_QWORD *)this + 25);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v6 = (IIsSchema *)*((_QWORD *)this + 26);
    if ( v6 )
      IIsSchema::Release(v6);
    inited = InitServerInfo(
               (CIISGenObject *)((char *)this + 176),
               *((const unsigned __int16 **)this + 17),
               (struct IMSAdminBaseW **)this + 25,
               (struct IIsSchema **)this + 26);
    if ( inited >= 0 )
    {
      v7 = AllocADsStr(*((LPCWSTR *)this + 3));
      v8 = v7;
      if ( !v7 )
      {
LABEL_5:
        inited = -2147024882;
        goto LABEL_21;
      }
      v9 = -1;
      do
        ++v9;
      while ( v7[v9] );
      *v7 = 0;
      inited = BuildIISPathFromADsPath((struct _objectinfo *)v16, v7, v9 + 1);
      if ( inited >= 0 )
      {
        v10 = (WCHAR *)*((_QWORD *)this + 18);
        if ( v10 )
          FreeADsStr(v10);
        v11 = AllocADsStr(v8);
        v12 = inited;
        *((_QWORD *)this + 18) = v11;
        if ( !v11 )
          v12 = -2147024882;
        inited = v12;
      }
      FreeADsStr(v8);
    }
  }
LABEL_21:
  FreeObjectInfo((struct _objectinfo *)v16);
  FreeADsStr(v15);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000474c  push    rbx
0x18000474e  push    rbp
0x18000474f  push    rsi
0x180004750  push    rdi
0x180004751  sub     rsp, 288h
0x180004758  mov     rax, cs:__security_cookie
0x18000475f  xor     rax, rsp
0x180004762  mov     [rsp+2A8h+var_38], rax
0x18000476a  mov     rdi, rcx
0x18000476d  mov     ebx, 230h
0x180004772  mov     r8d, ebx; Size
0x180004775  lea     rcx, [rsp+2A8h+var_268]; void *
0x18000477a  xor     edx, edx; Val
0x18000477c  call    memset_0
0x180004781  mov     rdx, [rdi+18h]; unsigned __int16 *
0x180004785  lea     rcx, [rsp+2A8h+var_288]; this
0x18000478a  call    ??0CLexer@@QEAA@PEBG@Z; CLexer::CLexer(ushort const *)
0x18000478f  mov     r8d, ebx; Size
0x180004792  lea     rcx, [rsp+2A8h+var_268]; void *
0x180004797  xor     edx, edx; Val
0x180004799  call    memset_0
0x18000479e  lea     rdx, [rsp+2A8h+var_268]; struct _objectinfo *
0x1800047a3  lea     rcx, [rsp+2A8h+var_288]; struct CLexer *
0x1800047a8  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x1800047ad  xor     ebp, ebp
0x1800047af  mov     ebx, eax
0x1800047b1  test    eax, eax
0x1800047b3  js      loc_1800048AD
0x1800047b9  mov     rcx, [rdi+88h]; pStr
0x1800047c0  test    rcx, rcx
0x1800047c3  jz      short loc_1800047CB
0x1800047c5  call    cs:__imp_FreeADsStr
0x1800047cb  mov     rcx, [rsp+2A8h+pStr]; pStr
0x1800047d0  call    cs:__imp_AllocADsStr
0x1800047d6  mov     [rdi+88h], rax
0x1800047dd  test    rax, rax
0x1800047e0  jnz     short loc_1800047EC
0x1800047e2  mov     ebx, 8007000Eh
0x1800047e7  jmp     loc_1800048AD
0x1800047ec  lea     rsi, [rdi+0C8h]
0x1800047f3  mov     rcx, [rsi]
0x1800047f6  test    rcx, rcx
0x1800047f9  jz      short loc_180004807
0x1800047fb  mov     rax, [rcx]
0x1800047fe  mov     rax, [rax+10h]
0x180004802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004807  lea     rbx, [rdi+0D0h]
0x18000480e  mov     rcx, [rbx]; this
0x180004811  test    rcx, rcx
0x180004814  jz      short loc_18000481B
0x180004816  call    ?Release@IIsSchema@@QEAAJXZ; IIsSchema::Release(void)
0x18000481b  mov     rdx, [rdi+88h]; unsigned __int16 *
0x180004822  lea     rcx, [rdi+0B0h]; struct CCredentials *
0x180004829  mov     r9, rbx; struct IIsSchema **
0x18000482c  mov     r8, rsi; struct IMSAdminBaseW **
0x18000482f  call    ?InitServerInfo@@YAJAEAVCCredentials@@PEBGPEAPEAUIMSAdminBaseW@@PEAPEAVIIsSchema@@@Z; InitServerInfo(CCredentials &,ushort const *,IMSAdminBaseW * *,IIsSchema * *)
0x180004834  mov     ebx, eax
0x180004836  test    eax, eax
0x180004838  js      short loc_1800048AD
0x18000483a  mov     rcx, [rdi+18h]; pStr
0x18000483e  call    cs:__imp_AllocADsStr
0x180004844  mov     rsi, rax
0x180004847  test    rax, rax
0x18000484a  jz      short loc_1800047E2
0x18000484c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004850  inc     r8
0x180004853  cmp     [rax+r8*2], bp
0x180004858  jnz     short loc_180004850
0x18000485a  inc     r8; unsigned __int64
0x18000485d  mov     [rax], bp
0x180004860  mov     rdx, rsi; unsigned __int16 *
0x180004863  lea     rcx, [rsp+2A8h+var_268]; struct _objectinfo *
0x180004868  call    ?BuildIISPathFromADsPath@@YAJPEAU_objectinfo@@PEAG_K@Z; BuildIISPathFromADsPath(_objectinfo *,ushort *,unsigned __int64)
0x18000486d  mov     ebx, eax
0x18000486f  test    eax, eax
0x180004871  js      short loc_1800048A4
0x180004873  mov     rcx, [rdi+90h]; pStr
0x18000487a  test    rcx, rcx
0x18000487d  jz      short loc_180004885
0x18000487f  call    cs:__imp_FreeADsStr
0x180004885  mov     rcx, rsi; pStr
0x180004888  call    cs:__imp_AllocADsStr
0x18000488e  mov     ecx, ebx
0x180004890  mov     ebx, 8007000Eh
0x180004895  test    rax, rax
0x180004898  mov     [rdi+90h], rax
0x18000489f  cmovz   ecx, ebx
0x1800048a2  mov     ebx, ecx
0x1800048a4  mov     rcx, rsi; pStr
0x1800048a7  call    cs:__imp_FreeADsStr
0x1800048ad  lea     rcx, [rsp+2A8h+var_268]; struct _objectinfo *
0x1800048b2  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x1800048b7  mov     rcx, [rsp+2A8h+var_280]; pStr
0x1800048bc  call    cs:__imp_FreeADsStr
0x1800048c2  mov     eax, ebx
0x1800048c4  mov     rcx, [rsp+2A8h+var_38]
0x1800048cc  xor     rcx, rsp; StackCookie
0x1800048cf  call    __security_check_cookie
0x1800048d4  add     rsp, 288h
0x1800048db  pop     rdi
0x1800048dc  pop     rsi
0x1800048dd  pop     rbp
0x1800048de  pop     rbx
0x1800048df  retn
```
