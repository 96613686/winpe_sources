# Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::Close(void)

- ea: `0x18001d1b0`
- end: `0x18001d3fd`
- name: `?Close@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@UEAAJXZ`
- size: `589`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180017f50`
- `0x18001ca24`
- `0x18001d1b0`
- `0x180048ae8`
- `0x18004d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001d33d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d33d`
- `OLEAUT32!__imp_VariantClear` at `0x18001d37a`
- `OLEAUT32!__imp_VariantClear` at `0x18001d3cf`
- `OLEAUT32!__imp_VariantClear` at `0x18001d37a`
- `OLEAUT32!__imp_VariantClear` at `0x18001d3cf`

## string_xrefs

- `0x18001d200`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`
- `0x18001d304`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`
- `0x18001d3b7`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::Close(
        Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *this)
{
  _QWORD *v1; // r14
  __int64 v3; // rcx
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  const OLECHAR *v14; // rbx
  VARTYPE vt; // ax
  __int64 *v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG v21; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int16 v23; // [rsp+90h] [rbp+30h] BYREF
  __int64 v24; // [rsp+98h] [rbp+38h] BYREF
  __int64 v25; // [rsp+A0h] [rbp+40h] BYREF

  v1 = (_QWORD *)((char *)this + 48);
  v24 = 0;
  v3 = *((_QWORD *)this + 6);
  v23 = 0;
  if ( v3 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v3 + 176LL))(v3, &v23);
    if ( v4 < 0 )
    {
      v5 = 261;
LABEL_4:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v5,
        (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
        (const char *)(unsigned int)v4);
      goto LABEL_28;
    }
    if ( !v23 )
    {
      v6 = *((_QWORD *)this + 5);
      v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v6 + 160LL);
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v24);
      v4 = v7(v6, *v1, &v24);
      if ( v4 < 0 )
      {
        v5 = 264;
        goto LABEL_4;
      }
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(v1);
    }
  }
  v8 = *((_QWORD *)this + 7);
  if ( v8 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v8 + 176LL))(v8, &v23);
    if ( v4 < 0 )
    {
      v5 = 272;
      goto LABEL_4;
    }
    if ( !v23 )
    {
      v9 = *((_QWORD *)this + 5);
      v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v9 + 160LL);
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v24);
      v4 = v10(v9, *((_QWORD *)this + 7), &v24);
      if ( v4 < 0 )
      {
        v5 = 275;
        goto LABEL_4;
      }
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease((char *)this + 56);
    }
  }
  v11 = *((_QWORD *)this + 4);
  v25 = 0;
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 632LL);
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v25);
  v13 = v12(v11, &v25);
  v4 = v13;
  if ( v13 >= 0 )
  {
    v14 = (const OLECHAR *)*((_QWORD *)this + 2);
    pvarg.vt = 0;
    Common::AutoVariant::InternalClear((Common::AutoVariant *)&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(v14);
    if ( pvarg.llVal || !v14 )
    {
      vt = pvarg.vt;
    }
    else
    {
      vt = 10;
      pvarg.lVal = -2147024882;
      pvarg.vt = 10;
    }
    if ( vt == 8 )
    {
      v16 = (__int64 *)*((_QWORD *)this + 4);
      v17 = *v16;
      v21 = pvarg;
      v18 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(v17 + 528))(v16, &v21);
      v4 = v18;
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x11F,
          (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
          (const char *)(unsigned int)v18);
      VariantClear(&pvarg);
    }
    else
    {
      VariantClear(&pvarg);
      v4 = -2147024882;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x11A,
      (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
      (const char *)(unsigned int)v13);
  }
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v25);
LABEL_28:
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v24);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001d1b0  mov     [rsp-28h+arg_18], rbx
0x18001d1b5  push    rbp
0x18001d1b6  push    rsi
0x18001d1b7  push    rdi
0x18001d1b8  push    r14
0x18001d1ba  push    r15
0x18001d1bc  mov     rbp, rsp
0x18001d1bf  sub     rsp, 60h
0x18001d1c3  xor     r15d, r15d
0x18001d1c6  lea     r14, [rcx+30h]
0x18001d1ca  mov     rsi, rcx
0x18001d1cd  mov     [rbp+arg_8], r15
0x18001d1d1  mov     rcx, [r14]
0x18001d1d4  mov     [rbp+arg_0], r15w
0x18001d1d9  test    rcx, rcx
0x18001d1dc  jz      short loc_18001D259
0x18001d1de  mov     rax, [rcx]
0x18001d1e1  lea     rdx, [rbp+arg_0]
0x18001d1e5  mov     rax, [rax+0B0h]
0x18001d1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1f1  mov     ebx, eax
0x18001d1f3  test    eax, eax
0x18001d1f5  jns     short loc_18001D214
0x18001d1f7  mov     edx, 105h; void *
0x18001d1fc  mov     rcx, [rbp+28h]; this
0x18001d200  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d207  mov     r9d, ebx; char *
0x18001d20a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d20f  jmp     loc_18001D3DE
0x18001d214  cmp     [rbp+arg_0], r15w
0x18001d219  jnz     short loc_18001D259
0x18001d21b  mov     rdi, [rsi+28h]
0x18001d21f  lea     rcx, [rbp+arg_8]
0x18001d223  mov     rax, [rdi]
0x18001d226  mov     rbx, [rax+0A0h]
0x18001d22d  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d232  mov     rdx, [r14]
0x18001d235  lea     r8, [rbp+arg_8]
0x18001d239  mov     rcx, rdi
0x18001d23c  mov     rax, rbx
0x18001d23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d244  mov     ebx, eax
0x18001d246  test    eax, eax
0x18001d248  jns     short loc_18001D251
0x18001d24a  mov     edx, 108h
0x18001d24f  jmp     short loc_18001D1FC
0x18001d251  mov     rcx, r14
0x18001d254  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d259  lea     r14, [rsi+38h]
0x18001d25d  mov     rcx, [r14]
0x18001d260  test    rcx, rcx
0x18001d263  jz      short loc_18001D2D0
0x18001d265  mov     rax, [rcx]
0x18001d268  lea     rdx, [rbp+arg_0]
0x18001d26c  mov     rax, [rax+0B0h]
0x18001d273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d278  mov     ebx, eax
0x18001d27a  test    eax, eax
0x18001d27c  jns     short loc_18001D288
0x18001d27e  mov     edx, 110h
0x18001d283  jmp     loc_18001D1FC
0x18001d288  cmp     [rbp+arg_0], r15w
0x18001d28d  jnz     short loc_18001D2D0
0x18001d28f  mov     rdi, [rsi+28h]
0x18001d293  lea     rcx, [rbp+arg_8]
0x18001d297  mov     rax, [rdi]
0x18001d29a  mov     rbx, [rax+0A0h]
0x18001d2a1  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d2a6  mov     rdx, [r14]
0x18001d2a9  lea     r8, [rbp+arg_8]
0x18001d2ad  mov     rcx, rdi
0x18001d2b0  mov     rax, rbx
0x18001d2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2b8  mov     ebx, eax
0x18001d2ba  test    eax, eax
0x18001d2bc  jns     short loc_18001D2C8
0x18001d2be  mov     edx, 113h
0x18001d2c3  jmp     loc_18001D1FC
0x18001d2c8  mov     rcx, r14
0x18001d2cb  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d2d0  mov     rdi, [rsi+20h]
0x18001d2d4  lea     rcx, [rbp+arg_10]
0x18001d2d8  mov     [rbp+arg_10], r15
0x18001d2dc  mov     rax, [rdi]
0x18001d2df  mov     rbx, [rax+278h]
0x18001d2e6  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d2eb  lea     rdx, [rbp+arg_10]
0x18001d2ef  mov     rcx, rdi
0x18001d2f2  mov     rax, rbx
0x18001d2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2fa  mov     ebx, eax
0x18001d2fc  test    eax, eax
0x18001d2fe  jns     short loc_18001D31D
0x18001d300  mov     rcx, [rbp+28h]; this
0x18001d304  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d30b  mov     r9d, eax; char *
0x18001d30e  mov     edx, 11Ah; void *
0x18001d313  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d318  jmp     loc_18001D3D5
0x18001d31d  mov     rbx, [rsi+10h]
0x18001d321  lea     rcx, [rbp+pvarg]; this
0x18001d325  mov     word ptr [rbp+pvarg], r15w
0x18001d32a  call    ?InternalClear@AutoVariant@Common@@IEAAJXZ; Common::AutoVariant::InternalClear(void)
0x18001d32f  mov     r14d, 8
0x18001d335  mov     rcx, rbx; psz
0x18001d338  mov     word ptr [rbp+pvarg], r14w
0x18001d33d  call    cs:__imp_SysAllocString
0x18001d343  mov     rcx, rax
0x18001d346  mov     dword ptr [rbp+pvarg+8], eax
0x18001d349  sar     rcx, 20h
0x18001d34d  mov     edi, 8007000Eh
0x18001d352  mov     dword ptr [rbp+pvarg+0Ch], ecx
0x18001d355  test    rax, rax
0x18001d358  jnz     short loc_18001D36C
0x18001d35a  test    rbx, rbx
0x18001d35d  jz      short loc_18001D36C
0x18001d35f  lea     eax, [r14+2]
0x18001d363  mov     dword ptr [rbp+pvarg+8], edi
0x18001d366  mov     word ptr [rbp+pvarg], ax
0x18001d36a  jmp     short loc_18001D370
0x18001d36c  movzx   eax, word ptr [rbp+pvarg]
0x18001d370  cmp     ax, r14w
0x18001d374  jz      short loc_18001D384
0x18001d376  lea     rcx, [rbp+pvarg]; pvarg
0x18001d37a  call    cs:__imp_VariantClear
0x18001d380  mov     ebx, edi
0x18001d382  jmp     short loc_18001D3D5
0x18001d384  mov     rcx, [rsi+20h]
0x18001d388  lea     rdx, [rbp+var_20]
0x18001d38c  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001d390  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18001d395  mov     rax, [rcx]
0x18001d398  movaps  [rbp+var_20], xmm0
0x18001d39c  movsd   [rbp+var_10], xmm1
0x18001d3a1  mov     rax, [rax+210h]
0x18001d3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3ad  mov     ebx, eax
0x18001d3af  test    eax, eax
0x18001d3b1  jns     short loc_18001D3CB
0x18001d3b3  mov     rcx, [rbp+28h]; this
0x18001d3b7  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d3be  mov     r9d, eax; char *
0x18001d3c1  mov     edx, 11Fh; void *
0x18001d3c6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d3cb  lea     rcx, [rbp+pvarg]; pvarg
0x18001d3cf  call    cs:__imp_VariantClear
0x18001d3d5  lea     rcx, [rbp+arg_10]
0x18001d3d9  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d3de  lea     rcx, [rbp+arg_8]
0x18001d3e2  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d3e7  mov     eax, ebx
0x18001d3e9  mov     rbx, [rsp+60h+arg_18]
0x18001d3f1  add     rsp, 60h
0x18001d3f5  pop     r15
0x18001d3f7  pop     r14
0x18001d3f9  pop     rdi
0x18001d3fa  pop     rsi
0x18001d3fb  pop     rbp
0x18001d3fc  retn
```
