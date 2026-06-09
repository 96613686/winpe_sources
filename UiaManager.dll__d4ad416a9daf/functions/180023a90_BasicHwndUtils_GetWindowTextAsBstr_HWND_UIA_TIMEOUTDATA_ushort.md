# BasicHwndUtils::GetWindowTextAsBstr(HWND__ *,UIA_TIMEOUTDATA &,ushort * *)

- ea: `0x180023a90`
- end: `0x180023c52`
- name: `?GetWindowTextAsBstr@BasicHwndUtils@@SAJPEAUHWND__@@AEAUUIA_TIMEOUTDATA@@PEAPEAG@Z`
- size: `450`
- prototype: `__int64 __fastcall(HWND, struct UIA_TIMEOUTDATA *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800234f0`

## callees

- `0x1800109bc`
- `0x180012484`
- `0x180023a90`
- `0x180023ce8`
- `0x180023d0c`
- `0x180024a40`
- `0x180031540`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180023b30`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180023bcc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180023b30`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180023bcc`

## string_xrefs

- `0x180023aea`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x180023b48`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x180023b8b`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x180023bb2`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x180023be1`: `onecore\windows\accessibletech\common\basichwndutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BasicHwndUtils::GetWindowTextAsBstr(HWND a1, struct UIA_TIMEOUTDATA *a2, unsigned __int16 **a3)
{
  int v6; // eax
  __int64 v7; // rdi
  unsigned __int16 **bstr; // rax
  unsigned __int16 *v9; // rcx
  __int64 *v10; // rcx
  const OLECHAR *v11; // rbx
  const char *v12; // r9
  int v13; // eax
  UINT v14; // edx
  BSTR v15; // rax
  const char *v16; // r9
  const char *v17; // r9
  __int64 result; // rax
  int v19; // [rsp+20h] [rbp-28h]
  int v20; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v22; // [rsp+60h] [rbp+18h] BYREF
  const OLECHAR *v23; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  v22 = 0;
  v6 = BasicHwndUtils::UIASendMessageTimeout(a2, a1, 0xEu, 0, 0, &v22);
  try
  {
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2E7,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
        (const char *)(unsigned int)v6,
        v19);
    v7 = (int)v22;
    if ( (_DWORD)v22 )
    {
      v11 = SysAllocStringLen(0, v22);
      v23 = v11;
      if ( !v11 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x2F2,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
          v12);
      v13 = BasicHwndUtils::UIASendMessageTimeout(a2, a1, 0xDu, (int)v7 + 1, (__int64)v11, &v22);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2F6,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
          (const char *)(unsigned int)v13,
          v20);
      v14 = v22;
      if ( (_DWORD)v22 == (_DWORD)v7 )
      {
        v11[v7] = 0;
      }
      else
      {
        if ( (int)v22 >= (int)v7 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2FC,
            (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
            (const char *)0x80004005LL,
            v20);
        v11[(int)v22] = 0;
        v15 = SysAllocStringLen(v11, v14);
        v22 = (__int64)v15;
        if ( !v15 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x303,
            (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
            v16);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v23,
          v15);
        v22 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
        v11 = v23;
      }
      v23 = 0;
      *a3 = (unsigned __int16 *)v11;
      v10 = (__int64 *)&v23;
    }
    else
    {
      bstr = (unsigned __int16 **)wil::make_bstr(&v22, &qword_1800A2748);
      v9 = *bstr;
      *bstr = 0;
      *a3 = v9;
      v10 = &v22;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x312,
                           (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x180023a90  mov     r11, rsp
0x180023a93  mov     [r11+8], rbx
0x180023a97  mov     [r11+10h], rsi
0x180023a9b  push    rdi
0x180023a9c  push    r14
0x180023a9e  push    r15
0x180023aa0  sub     rsp, 30h
0x180023aa4  mov     rsi, r8
0x180023aa7  mov     r14, rdx
0x180023aaa  mov     r15, rcx
0x180023aad  mov     qword ptr [r8], 0
0x180023ab4  mov     qword ptr [r11+18h], 0
0x180023abc  lea     rax, [r11+18h]
0x180023ac0  mov     [r11-20h], rax
0x180023ac4  mov     qword ptr [r11-28h], 0
0x180023acc  xor     r9d, r9d; unsigned __int64
0x180023acf  lea     r8d, [r9+0Eh]; unsigned int
0x180023ad3  mov     rdx, rcx; HWND
0x180023ad6  mov     rcx, r14; struct UIA_TIMEOUTDATA *
0x180023ad9  call    ?UIASendMessageTimeout@BasicHwndUtils@@SAJAEBUUIA_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; BasicHwndUtils::UIASendMessageTimeout(UIA_TIMEOUTDATA const &,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180023ade  mov     rcx, [rsp+48h]; this
0x180023ae3  test    eax, eax
0x180023ae5  jns     short loc_180023AFB
0x180023ae7  mov     r9d, eax; char *
0x180023aea  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x180023af1  mov     edx, 2E7h; void *
0x180023af6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023afb  movsxd  rdi, dword ptr [rsp+48h+arg_10]
0x180023b00  test    edi, edi
0x180023b02  jnz     short loc_180023B2C
0x180023b04  lea     rdx, qword_1800A2748
0x180023b0b  lea     rcx, [rsp+48h+arg_10]
0x180023b10  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180023b15  mov     rcx, [rax]
0x180023b18  mov     qword ptr [rax], 0
0x180023b1f  mov     [rsi], rcx
0x180023b22  lea     rcx, [rsp+48h+arg_10]
0x180023b27  jmp     loc_180023C30
0x180023b2c  mov     edx, edi; ui
0x180023b2e  xor     ecx, ecx; strIn
0x180023b30  call    cs:__imp_SysAllocStringLen
0x180023b36  mov     rbx, rax
0x180023b39  mov     [rsp+48h+arg_18], rax
0x180023b3e  mov     rcx, [rsp+48h]; this
0x180023b43  test    rax, rax
0x180023b46  jnz     short loc_180023B59
0x180023b48  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x180023b4f  mov     edx, 2F2h; void *
0x180023b54  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180023b59  lea     eax, [rdi+1]
0x180023b5c  movsxd  r9, eax; unsigned __int64
0x180023b5f  lea     rax, [rsp+48h+arg_10]
0x180023b64  mov     [rsp+48h+var_20], rax; __int64 *
0x180023b69  mov     [rsp+48h+var_28], rbx; int
0x180023b6e  mov     r8d, 0Dh; unsigned int
0x180023b74  mov     rdx, r15; HWND
0x180023b77  mov     rcx, r14; struct UIA_TIMEOUTDATA *
0x180023b7a  call    ?UIASendMessageTimeout@BasicHwndUtils@@SAJAEBUUIA_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; BasicHwndUtils::UIASendMessageTimeout(UIA_TIMEOUTDATA const &,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180023b7f  mov     rcx, [rsp+48h]; this
0x180023b84  test    eax, eax
0x180023b86  jns     short loc_180023B9C
0x180023b88  mov     r9d, eax; char *
0x180023b8b  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x180023b92  mov     edx, 2F6h; void *
0x180023b97  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023b9c  movsxd  rdx, dword ptr [rsp+48h+arg_10]; ui
0x180023ba1  cmp     edx, edi
0x180023ba3  jz      short loc_180023C19
0x180023ba5  mov     rcx, [rsp+48h]; this
0x180023baa  jl      short loc_180023BC3
0x180023bac  mov     r9d, 80004005h; char *
0x180023bb2  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x180023bb9  mov     edx, 2FCh; void *
0x180023bbe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023bc3  xor     eax, eax
0x180023bc5  mov     [rbx+rdx*2], ax
0x180023bc9  mov     rcx, rbx; strIn
0x180023bcc  call    cs:__imp_SysAllocStringLen
0x180023bd2  mov     [rsp+48h+arg_10], rax
0x180023bd7  mov     rcx, [rsp+48h]; this
0x180023bdc  test    rax, rax
0x180023bdf  jnz     short loc_180023BF2
0x180023be1  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x180023be8  mov     edx, 303h; void *
0x180023bed  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180023bf2  mov     rdx, rax
0x180023bf5  lea     rcx, [rsp+48h+arg_18]
0x180023bfa  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180023bff  mov     [rsp+48h+arg_10], 0
0x180023c08  lea     rcx, [rsp+48h+arg_10]
0x180023c0d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023c12  mov     rbx, [rsp+48h+arg_18]
0x180023c17  jmp     short loc_180023C1F
0x180023c19  xor     eax, eax
0x180023c1b  mov     [rbx+rdi*2], ax
0x180023c1f  mov     [rsp+48h+arg_18], 0
0x180023c28  mov     [rsi], rbx
0x180023c2b  lea     rcx, [rsp+48h+arg_18]
0x180023c30  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023c35  xor     eax, eax
0x180023c37  jmp     short loc_180023C3D
0x180023c39  mov     eax, dword ptr [rsp+48h+arg_10]
0x180023c3d  mov     rbx, [rsp+48h+arg_0]
0x180023c42  mov     rsi, [rsp+48h+arg_8]
0x180023c47  add     rsp, 30h
0x180023c4b  pop     r15
0x180023c4d  pop     r14
0x180023c4f  pop     rdi
0x180023c50  retn
```
