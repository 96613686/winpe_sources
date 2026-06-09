# pre_c_init

- ea: `0x140001a60`
- end: `0x140001b37`
- name: `pre_c_init`
- size: `215`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001a60`
- `0x140002104`
- `0x140003520`

## import_xrefs

- `msvcrt!_fmode` at `0x140001afd`
- `msvcrt!_commode` at `0x140001b06`
- `msvcrt!__setusermatherr` at `0x140001b2a`
- `msvcrt!__setusermatherr` at `0x140001b2a`
- `msvcrt!__set_app_type` at `0x140001adf`
- `msvcrt!__set_app_type` at `0x140001adf`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init()
{
  int v0; // eax
  bool v1; // zf
  _crt_app_type image_app_type; // eax

  if ( LOWORD(_ImageBase.unused) != 23117 || *(int *)((char *)&_ImageBase.unused + (int)off_14000003C) != 17744 )
    goto LABEL_2;
  if ( *(__int16 *)((char *)&word_140000018 + (int)off_14000003C) != 267 )
  {
    if ( *(__int16 *)((char *)&word_140000018 + (int)off_14000003C) == 523 )
    {
      v0 = 0;
      if ( *(_DWORD *)&byte_140000040[(int)off_14000003C + 68] <= 0xEu )
        goto LABEL_11;
      v1 = *(int *)((char *)&dword_1400000F8 + (int)off_14000003C) == 0;
      goto LABEL_10;
    }
LABEL_2:
    v0 = 0;
    goto LABEL_11;
  }
  v0 = 0;
  if ( *(_DWORD *)&byte_140000040[(int)off_14000003C + 52] <= 0xEu )
    goto LABEL_11;
  v1 = *(_DWORD *)&byte_140000040[(int)off_14000003C + 168] == 0;
LABEL_10:
  LOBYTE(v0) = !v1;
LABEL_11:
  dword_14004C420 = v0;
  image_app_type = (unsigned int)get_image_app_type(2);
  __set_app_type(image_app_type);
  _onexitend = -1;
  _onexitbegin = -1;
  _fmode = fmode;
  _commode = commode;
  ATL::CComCoClass<CTieringEngineApiServer,&_GUID const CLSID_TieringEngine>::GetObjectDescription(*(struct _exception **)&_commode);
  if ( !_defaultmatherr )
    __setusermatherr((_UserMathErrorFunctionPointer)ATL::CComCoClass<CTieringEngineApiServer,&_GUID const CLSID_TieringEngine>::GetObjectDescription);
  return 0;
}

```

## disassembly

```asm
0x140001a60  sub     rsp, 28h
0x140001a64  mov     eax, 5A4Dh
0x140001a69  cmp     word ptr cs:__ImageBase.unused, ax
0x140001a70  jz      short loc_140001A76
0x140001a72  xor     eax, eax
0x140001a74  jmp     short loc_140001ACD
0x140001a76  movsxd  rcx, cs:off_14000003C
0x140001a7d  lea     rdx, __ImageBase
0x140001a84  cmp     dword ptr [rcx+rdx], 4550h
0x140001a8b  jnz     short loc_140001A72
0x140001a8d  mov     eax, 10Bh
0x140001a92  cmp     [rcx+rdx+18h], ax
0x140001a97  jz      short loc_140001ABA
0x140001a99  mov     eax, 20Bh
0x140001a9e  cmp     [rcx+rdx+18h], ax
0x140001aa3  jnz     short loc_140001A72
0x140001aa5  xor     eax, eax
0x140001aa7  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x140001aaf  jbe     short loc_140001ACD
0x140001ab1  cmp     [rcx+rdx+0F8h], eax
0x140001ab8  jmp     short loc_140001ACA
0x140001aba  xor     eax, eax
0x140001abc  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001ac1  jbe     short loc_140001ACD
0x140001ac3  cmp     [rcx+rdx+0E8h], eax
0x140001aca  setnz   al
0x140001acd  mov     ecx, 2
0x140001ad2  mov     cs:dword_14004C420, eax
0x140001ad8  call    _get_image_app_type
0x140001add  mov     ecx, eax; Type
0x140001adf  call    cs:__imp___set_app_type
0x140001ae5  mov     ecx, cs:_fmode
0x140001aeb  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001aef  mov     cs:__onexitend, rax
0x140001af6  mov     cs:__onexitbegin, rax
0x140001afd  mov     rax, cs:__imp__fmode
0x140001b04  mov     [rax], ecx
0x140001b06  mov     rcx, cs:__imp__commode; struct _exception *
0x140001b0d  mov     eax, cs:_commode
0x140001b13  mov     [rcx], eax
0x140001b15  call    ?GetObjectDescription@?$CComCoClass@VCTieringEngineApiServer@@$1?CLSID_TieringEngine@@3U_GUID@@B@ATL@@SAPEBGXZ; ATL::CComCoClass<CTieringEngineApiServer,&_GUID const CLSID_TieringEngine>::GetObjectDescription(void)
0x140001b1a  cmp     cs:__defaultmatherr, 0
0x140001b21  jnz     short loc_140001B30
0x140001b23  lea     rcx, ?GetObjectDescription@?$CComCoClass@VCTieringEngineApiServer@@$1?CLSID_TieringEngine@@3U_GUID@@B@ATL@@SAPEBGXZ; UserMathErrorFunction
0x140001b2a  call    cs:__imp___setusermatherr
0x140001b30  xor     eax, eax
0x140001b32  add     rsp, 28h
0x140001b36  retn
```
