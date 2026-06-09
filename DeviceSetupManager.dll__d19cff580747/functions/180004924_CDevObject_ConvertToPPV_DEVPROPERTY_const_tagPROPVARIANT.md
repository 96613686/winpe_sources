# CDevObject::_ConvertToPPV(_DEVPROPERTY const *,tagPROPVARIANT *)

- ea: `0x180004924`
- end: `0x180004b3a`
- name: `?_ConvertToPPV@CDevObject@@AEAAJPEBU_DEVPROPERTY@@PEAUtagPROPVARIANT@@@Z`
- size: `534`
- prototype: `int(CDevObject *__hidden this, const struct _DEVPROPERTY *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004520`
- `0x180004580`

## callees

- `0x180004924`
- `0x180005100`
- `0x180005120`
- `0x18001ba48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004941`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a5b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004ab0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004941`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a5b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004ab0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800049cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004ae3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800049cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004ae3`

## pseudocode

```c
__int64 __fastcall CDevObject::_ConvertToPPV(CDevObject *this, const struct _DEVPROPERTY *a2, PROPVARIANT *a3)
{
  __int64 v5; // r8
  __int64 v6; // r9
  DEVPROPTYPE Type; // ecx
  unsigned int v8; // ebx
  DEVPROPTYPE v9; // ecx
  DEVPROPTYPE v10; // ecx
  DEVPROPTYPE v11; // ecx
  DEVPROPTYPE v12; // ecx
  _WORD *Buffer; // rcx
  unsigned int v14; // eax
  __int64 v15; // rdx
  SIZE_T v16; // r14
  BYTE *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  _WORD *v20; // rsi
  int v21; // r14d
  CDevObject *v22; // rdx
  BYTE *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  CDevObject *v26; // rax
  __int128 v27; // xmm1
  bool v28; // cf
  _OWORD *v29; // rcx
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v32; // [rsp+30h] [rbp-18h]
  CDevObject *v33; // [rsp+80h] [rbp+38h] BYREF

  v33 = this;
  PropVariantClear(a3);
  Type = a2->Type;
  v8 = -2147467259;
  if ( !Type )
  {
    *(_WORD *)a3 = 0;
    return 0;
  }
  v9 = Type - 7;
  if ( !v9 )
  {
    if ( a2->BufferSize < 4 )
      return v8;
    *(_WORD *)a3 = 19;
    *((_DWORD *)a3 + 2) = *(_DWORD *)a2->Buffer;
    return 0;
  }
  v10 = v9 - 6;
  if ( !v10 )
  {
    v29 = CoTaskMemAlloc(0x10u);
    if ( !v29 )
      return (unsigned int)-2147024882;
    *v29 = *(_OWORD *)a2->Buffer;
    a3[1] = v29;
    *(_WORD *)a3 = 72;
    return 0;
  }
  v11 = v10 - 4;
  if ( !v11 )
  {
    v28 = *(_BYTE *)a2->Buffer != 0;
    *(_WORD *)a3 = 11;
    *((_WORD *)a3 + 4) = -v28;
    return 0;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    if ( v12 == 0x2000 )
    {
      Buffer = a2->Buffer;
      v14 = 0;
      while ( *Buffer )
      {
        ++v14;
        v15 = -1;
        do
          ++v15;
        while ( Buffer[v15] );
        Buffer += v15 + 1;
      }
      *(_WORD *)a3 = 4127;
      *((_DWORD *)a3 + 2) = v14;
      if ( v14 )
      {
        v16 = 8LL * v14;
        v17 = (BYTE *)CoTaskMemAlloc(v16);
        a3[2] = v17;
        if ( v17 )
        {
          v8 = 0;
          memset_0(v17, 0, v16);
          v20 = a2->Buffer;
          v21 = 0;
          while ( *v20 )
          {
            wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v33,
              v20,
              v18,
              v19);
            v22 = v33;
            if ( !v33 )
            {
              v8 = -2147024882;
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v33);
              goto LABEL_22;
            }
            v23 = (BYTE *)a3[2];
            v24 = v21++;
            v33 = 0;
            *(_QWORD *)&v23[8 * v24] = v22;
            v25 = -1;
            do
              ++v25;
            while ( v20[v25] );
            v20 += v25 + 1;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v33);
          }
        }
        else
        {
          v8 = -2147024882;
LABEL_22:
          PropVariantClear(a3);
        }
      }
    }
  }
  else
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v33,
      a2->Buffer,
      v5,
      v6);
    v26 = v33;
    if ( v33 )
    {
      v33 = 0;
      v8 = 0;
      pvar[0] = (PROPVARIANT)31;
      pvar[1] = v26;
      v32 = 0;
      v27 = *(_OWORD *)pvar;
      *(_OWORD *)pvar = 0;
      *(_OWORD *)a3 = v27;
      a3[2] = 0;
      PropVariantClear(pvar);
    }
    else
    {
      v8 = -2147024882;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v33);
  }
  return v8;
}

```

## disassembly

```asm
0x180004924  mov     [rsp-30h+arg_0], rcx
0x180004929  push    rbp
0x18000492a  push    rbx
0x18000492b  push    rsi
0x18000492c  push    rdi
0x18000492d  push    r14
0x18000492f  push    r15
0x180004931  mov     rbp, rsp
0x180004934  sub     rsp, 48h
0x180004938  mov     rcx, r8; pvar
0x18000493b  mov     rdi, r8
0x18000493e  mov     rsi, rdx
0x180004941  call    cs:__imp_PropVariantClear
0x180004947  mov     ecx, [rsi+20h]
0x18000494a  xor     r15d, r15d
0x18000494d  mov     ebx, 80004005h
0x180004952  test    ecx, ecx
0x180004954  jz      loc_180004B24
0x18000495a  sub     ecx, 7
0x18000495d  jz      loc_180004B0E
0x180004963  sub     ecx, 6
0x180004966  jz      loc_180004ADE
0x18000496c  sub     ecx, 4
0x18000496f  jz      loc_180004AC8
0x180004975  sub     ecx, 1
0x180004978  jz      loc_180004A66
0x18000497e  cmp     ecx, 2000h
0x180004984  jnz     loc_180004B2B
0x18000498a  mov     rcx, [rsi+28h]
0x18000498e  mov     eax, r15d
0x180004991  jmp     short loc_1800049AB
0x180004993  inc     eax
0x180004995  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180004999  inc     rdx
0x18000499c  cmp     [rcx+rdx*2], r15w
0x1800049a1  jnz     short loc_180004999
0x1800049a3  lea     rcx, [rcx+rdx*2]
0x1800049a7  add     rcx, 2
0x1800049ab  cmp     [rcx], r15w
0x1800049af  jnz     short loc_180004993
0x1800049b1  mov     word ptr [rdi], 101Fh
0x1800049b6  mov     [rdi+8], eax
0x1800049b9  test    eax, eax
0x1800049bb  jz      loc_180004B2B
0x1800049c1  mov     r14d, eax
0x1800049c4  shl     r14, 3
0x1800049c8  mov     rcx, r14; cb
0x1800049cb  call    cs:__imp_CoTaskMemAlloc
0x1800049d1  mov     [rdi+10h], rax
0x1800049d5  test    rax, rax
0x1800049d8  jz      short loc_180004A53
0x1800049da  mov     r8, r14; Size
0x1800049dd  xor     edx, edx; Val
0x1800049df  mov     rcx, rax; void *
0x1800049e2  mov     ebx, r15d
0x1800049e5  call    memset_0
0x1800049ea  mov     rsi, [rsi+28h]
0x1800049ee  mov     r14d, r15d
0x1800049f1  cmp     [rsi], r15w
0x1800049f5  jz      loc_180004B2B
0x1800049fb  mov     rdx, rsi
0x1800049fe  lea     rcx, [rbp+arg_0]
0x180004a02  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180004a07  mov     rdx, [rbp+arg_0]
0x180004a0b  test    rdx, rdx
0x180004a0e  jz      short loc_180004A43
0x180004a10  mov     rax, [rdi+10h]
0x180004a14  movsxd  rcx, r14d
0x180004a17  inc     r14d
0x180004a1a  mov     [rbp+arg_0], r15
0x180004a1e  mov     [rax+rcx*8], rdx
0x180004a22  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004a26  inc     rax
0x180004a29  cmp     [rsi+rax*2], r15w
0x180004a2e  jnz     short loc_180004A26
0x180004a30  lea     rsi, [rsi+rax*2]
0x180004a34  add     rsi, 2
0x180004a38  lea     rcx, [rbp+arg_0]
0x180004a3c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180004a41  jmp     short loc_1800049F1
0x180004a43  lea     rcx, [rbp+arg_0]
0x180004a47  mov     ebx, 8007000Eh
0x180004a4c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180004a51  jmp     short loc_180004A58
0x180004a53  mov     ebx, 8007000Eh
0x180004a58  mov     rcx, rdi; pvar
0x180004a5b  call    cs:__imp_PropVariantClear
0x180004a61  jmp     loc_180004B2B
0x180004a66  mov     rdx, [rsi+28h]
0x180004a6a  lea     rcx, [rbp+arg_0]
0x180004a6e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180004a73  mov     rax, [rbp+arg_0]
0x180004a77  test    rax, rax
0x180004a7a  jz      short loc_180004AB8
0x180004a7c  xor     edx, edx
0x180004a7e  mov     [rbp+arg_0], r15
0x180004a82  xorps   xmm0, xmm0
0x180004a85  mov     ebx, r15d
0x180004a88  movups  xmmword ptr [rbp+pvar], xmm0
0x180004a8c  mov     [rbp+pvar+8], rax
0x180004a90  xor     eax, eax
0x180004a92  lea     ecx, [rdx+1Fh]
0x180004a95  mov     [rbp+var_18], rax
0x180004a99  mov     word ptr [rbp+pvar], cx
0x180004a9d  lea     rcx, [rbp+pvar]; pvar
0x180004aa1  movups  xmm1, xmmword ptr [rbp+pvar]
0x180004aa5  movups  xmmword ptr [rbp+pvar], xmm0
0x180004aa9  movups  xmmword ptr [rdi], xmm1
0x180004aac  mov     [rdi+10h], rdx
0x180004ab0  call    cs:__imp_PropVariantClear
0x180004ab6  jmp     short loc_180004ABD
0x180004ab8  mov     ebx, 8007000Eh
0x180004abd  lea     rcx, [rbp+arg_0]
0x180004ac1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180004ac6  jmp     short loc_180004B2B
0x180004ac8  mov     rax, [rsi+28h]
0x180004acc  mov     cl, [rax]
0x180004ace  neg     cl
0x180004ad0  mov     word ptr [rdi], 0Bh
0x180004ad5  sbb     ax, ax
0x180004ad8  mov     [rdi+8], ax
0x180004adc  jmp     short loc_180004B28
0x180004ade  mov     ecx, 10h; cb
0x180004ae3  call    cs:__imp_CoTaskMemAlloc
0x180004ae9  mov     rcx, rax
0x180004aec  test    rax, rax
0x180004aef  jz      short loc_180004B07
0x180004af1  mov     rax, [rsi+28h]
0x180004af5  movups  xmm0, xmmword ptr [rax]
0x180004af8  movdqu  xmmword ptr [rcx], xmm0
0x180004afc  mov     [rdi+8], rcx
0x180004b00  mov     word ptr [rdi], 48h ; 'H'
0x180004b05  jmp     short loc_180004B28
0x180004b07  mov     ebx, 8007000Eh
0x180004b0c  jmp     short loc_180004B2B
0x180004b0e  cmp     dword ptr [rsi+24h], 4
0x180004b12  jb      short loc_180004B2B
0x180004b14  mov     word ptr [rdi], 13h
0x180004b19  mov     rax, [rsi+28h]
0x180004b1d  mov     ecx, [rax]
0x180004b1f  mov     [rdi+8], ecx
0x180004b22  jmp     short loc_180004B28
0x180004b24  mov     [rdi], r15w
0x180004b28  mov     ebx, r15d
0x180004b2b  mov     eax, ebx
0x180004b2d  add     rsp, 48h
0x180004b31  pop     r15
0x180004b33  pop     r14
0x180004b35  pop     rdi
0x180004b36  pop     rsi
0x180004b37  pop     rbx
0x180004b38  pop     rbp
0x180004b39  retn
```
