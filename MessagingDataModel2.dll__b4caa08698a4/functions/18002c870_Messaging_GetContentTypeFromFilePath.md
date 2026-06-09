# Messaging_GetContentTypeFromFilePath

- ea: `0x18002c870`
- end: `0x18002ca04`
- name: `Messaging_GetContentTypeFromFilePath`
- size: `404`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000b9d0`
- `0x1800677e8`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18000b6d4`
- `0x18002413c`
- `0x18002bd78`
- `0x18002c0f4`
- `0x18002c6b4`
- `0x18002c870`
- `0x1800c6940`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002c8e6`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c995`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c8e6`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c995`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18002c899`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18002c899`

## pseudocode

```c
__int64 __fastcall Messaging_GetContentTypeFromFilePath(unsigned __int16 *a1, unsigned __int16 **a2)
{
  LPWSTR ExtensionW; // rax
  wchar_t *v5; // r8
  int MimeTypeFromFileExtension; // eax
  unsigned int v7; // ebx
  BSTR v8; // rax
  unsigned __int16 *v9; // rax
  BSTR v10; // rax
  unsigned __int16 *v11; // rax
  unsigned __int16 *v13; // [rsp+30h] [rbp-30h] BYREF
  OLECHAR *psz[2]; // [rsp+38h] [rbp-28h] BYREF
  __int128 v15; // [rsp+48h] [rbp-18h]

  ExtensionW = PathFindExtensionW(a1);
  if ( ExtensionW && *ExtensionW )
  {
    *(_OWORD *)psz = 0;
    v15 = 0;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(psz);
    MimeTypeFromFileExtension = GetMimeTypeFromFileExtension(v5);
    v7 = MimeTypeFromFileExtension;
    if ( MimeTypeFromFileExtension < 0 )
    {
      if ( MimeTypeFromFileExtension != -2147023728
        || (Log_HREvent_11(-2147023728),
            MimeTypeFromFileExtension = GetContentTypeFromFilePathFromPacManWithCache(a1, a2),
            v7 = MimeTypeFromFileExtension,
            MimeTypeFromFileExtension < 0) )
      {
        Log_HREvent_11(MimeTypeFromFileExtension);
        goto LABEL_11;
      }
    }
    else
    {
      v13 = 0;
      v8 = SysAllocString(psz[0]);
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::reset(
        &v13,
        v8);
      v9 = v13;
      if ( !v13 )
      {
        v7 = -2147024882;
        Log_HREvent_11(-2147024882);
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v13);
LABEL_11:
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(psz);
        return v7;
      }
      v13 = 0;
      *a2 = v9;
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v13);
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(psz);
  }
  else
  {
    v13 = 0;
    v10 = SysAllocString(&::psz);
    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::reset(&v13, v10);
    v11 = v13;
    if ( !v13 )
    {
      v7 = -2147024882;
      Log_HREvent_11(-2147024882);
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v13);
      return v7;
    }
    v13 = 0;
    *a2 = v11;
    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v13);
  }
  return 0;
}

```

## disassembly

```asm
0x18002c870  mov     [rsp-18h+arg_10], rbx
0x18002c875  mov     [rsp-18h+arg_18], rsi
0x18002c87a  push    rbp
0x18002c87b  push    rdi
0x18002c87c  push    r14
0x18002c87e  mov     rbp, rsp
0x18002c881  sub     rsp, 60h
0x18002c885  mov     rax, cs:__security_cookie
0x18002c88c  xor     rax, rsp
0x18002c88f  mov     [rbp+var_8], rax
0x18002c893  mov     rdi, rdx
0x18002c896  mov     rsi, rcx
0x18002c899  call    cs:__imp_PathFindExtensionW
0x18002c89f  xor     r14d, r14d
0x18002c8a2  mov     r8, rax
0x18002c8a5  test    rax, rax
0x18002c8a8  jz      loc_18002C98A
0x18002c8ae  cmp     [rax], r14w
0x18002c8b2  jz      loc_18002C98A
0x18002c8b8  xorps   xmm0, xmm0
0x18002c8bb  lea     rcx, [rbp+psz]
0x18002c8bf  movups  xmmword ptr [rbp+psz], xmm0
0x18002c8c3  movups  [rbp+var_18], xmm0
0x18002c8c7  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18002c8cc  lea     rdx, [rbp+psz]
0x18002c8d0  mov     rcx, r8; String1
0x18002c8d3  call    _GetMimeTypeFromFileExtension
0x18002c8d8  mov     ebx, eax
0x18002c8da  test    eax, eax
0x18002c8dc  js      short loc_18002C93E
0x18002c8de  mov     rcx, [rbp+psz]; psz
0x18002c8e2  mov     [rbp+var_30], r14
0x18002c8e6  call    cs:__imp_SysAllocString
0x18002c8ec  mov     rdx, rax
0x18002c8ef  lea     rcx, [rbp+var_30]
0x18002c8f3  call    ?reset@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAAXPEAG@Z; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::reset(ushort *)
0x18002c8f8  mov     rax, [rbp+var_30]
0x18002c8fc  test    rax, rax
0x18002c8ff  jnz     short loc_18002C920
0x18002c901  mov     ebx, 8007000Eh
0x18002c906  xor     edx, edx
0x18002c908  mov     ecx, ebx; int
0x18002c90a  mov     r9d, 125h
0x18002c910  call    Log_HREvent_11
0x18002c915  lea     rcx, [rbp+var_30]
0x18002c919  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18002c91e  jmp     short loc_18002C97F
0x18002c920  lea     rcx, [rbp+var_30]
0x18002c924  mov     [rbp+var_30], r14
0x18002c928  mov     [rdi], rax
0x18002c92b  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18002c930  lea     rcx, [rbp+psz]
0x18002c934  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002c939  jmp     loc_18002C9E1
0x18002c93e  mov     ecx, 80070490h; int
0x18002c943  cmp     eax, ecx
0x18002c945  jnz     short loc_18002C96D
0x18002c947  xor     edx, edx
0x18002c949  mov     r9d, 12Ah
0x18002c94f  call    Log_HREvent_11
0x18002c954  mov     rdx, rdi; unsigned __int16 **
0x18002c957  mov     rcx, rsi; unsigned __int16 *
0x18002c95a  call    _GetContentTypeFromFilePathFromPacManWithCache
0x18002c95f  mov     ebx, eax
0x18002c961  test    eax, eax
0x18002c963  jns     short loc_18002C930
0x18002c965  mov     r9d, 12Ch
0x18002c96b  jmp     short loc_18002C973
0x18002c96d  mov     r9d, 130h
0x18002c973  mov     edx, 1
0x18002c978  mov     ecx, eax; int
0x18002c97a  call    Log_HREvent_11
0x18002c97f  lea     rcx, [rbp+psz]
0x18002c983  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002c988  jmp     short loc_18002C9CD
0x18002c98a  lea     rcx, psz; psz
0x18002c991  mov     [rbp+var_30], r14
0x18002c995  call    cs:__imp_SysAllocString
0x18002c99b  mov     rdx, rax
0x18002c99e  lea     rcx, [rbp+var_30]
0x18002c9a2  call    ?reset@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAAXPEAG@Z; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::reset(ushort *)
0x18002c9a7  mov     rax, [rbp+var_30]
0x18002c9ab  test    rax, rax
0x18002c9ae  jnz     short loc_18002C9D1
0x18002c9b0  mov     ebx, 8007000Eh
0x18002c9b5  xor     edx, edx
0x18002c9b7  mov     ecx, ebx; int
0x18002c9b9  mov     r9d, 118h
0x18002c9bf  call    Log_HREvent_11
0x18002c9c4  lea     rcx, [rbp+var_30]
0x18002c9c8  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18002c9cd  mov     eax, ebx
0x18002c9cf  jmp     short loc_18002C9E3
0x18002c9d1  lea     rcx, [rbp+var_30]
0x18002c9d5  mov     [rbp+var_30], r14
0x18002c9d9  mov     [rdi], rax
0x18002c9dc  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18002c9e1  xor     eax, eax
0x18002c9e3  mov     rcx, [rbp+var_8]
0x18002c9e7  xor     rcx, rsp; StackCookie
0x18002c9ea  call    __security_check_cookie
0x18002c9ef  lea     r11, [rsp+60h+var_s0]
0x18002c9f4  mov     rbx, [r11+30h]
0x18002c9f8  mov     rsi, [r11+38h]
0x18002c9fc  mov     rsp, r11
0x18002c9ff  pop     r14
0x18002ca01  pop     rdi
0x18002ca02  pop     rbp
0x18002ca03  retn
```
