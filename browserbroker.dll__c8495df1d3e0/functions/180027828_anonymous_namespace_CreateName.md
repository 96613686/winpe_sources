# _anonymous_namespace_::CreateName

- ea: `0x180027828`
- end: `0x180027aca`
- name: `_anonymous_namespace_::CreateName`
- size: `674`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, char, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180028490`

## callees

- `0x180002ce0`
- `0x18000d1c0`
- `0x18000dc74`
- `0x18001078c`
- `0x18002583c`
- `0x180026b10`
- `0x18002778c`
- `0x180027828`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800279a6`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800279a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800278c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800278c5`

## string_xrefs

- `0x18002790a`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\fileoperationbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::CreateName(
        unsigned __int16 *a1,
        __int64 a2,
        const WCHAR *a3,
        unsigned int a4,
        char a5,
        unsigned __int16 *a6)
{
  unsigned int v6; // r10d
  const unsigned __int16 *v8; // r15
  __int64 v9; // rsi
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // r14
  unsigned __int16 *v12; // rcx
  signed int v13; // ebx
  __int64 v14; // r14
  unsigned __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // r12
  unsigned int v18; // ebx
  __int64 v19; // rax
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rax
  const WCHAR *v22; // rax
  const wchar_t *v23; // rcx
  unsigned __int16 *v24; // rdi
  int v25; // eax
  unsigned __int16 **v27; // [rsp+20h] [rbp-A1h]
  unsigned __int64 *v28; // [rsp+28h] [rbp-99h]
  unsigned int v29; // [rsp+30h] [rbp-91h]
  const unsigned __int16 *v31; // [rsp+58h] [rbp-69h] BYREF
  __int64 v32; // [rsp+60h] [rbp-61h]
  unsigned __int16 *v33; // [rsp+68h] [rbp-59h]
  const unsigned __int16 **v34; // [rsp+70h] [rbp-51h] BYREF
  unsigned __int16 *v35; // [rsp+78h] [rbp-49h]
  char v36; // [rsp+80h] [rbp-41h]
  _WORD v37[16]; // [rsp+90h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  v6 = a4;
  v32 = a2;
  v8 = a1;
  v33 = a6;
  v31 = 0;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( a1[v10] );
  if ( v10 && a1[v10 - 1] == 92 )
  {
    v34 = &v31;
    v36 = 1;
    v35 = 0;
    v11 = v10 + 1;
    if ( v10 + 1 < v10 )
    {
      v13 = -2147024362;
    }
    else
    {
      v12 = 0;
      v35 = 0;
      if ( is_mul_ok(v11, 2u) )
      {
        v12 = (unsigned __int16 *)CoTaskMemAlloc(2 * v11);
        v35 = v12;
        v13 = v12 == 0 ? 0x8007000E : 0;
      }
      else
      {
        v13 = -2147024362;
      }
      if ( v13 >= 0 )
        StringCchCopyNExW(v12, v10 + 1, v8, v10, v27, v28, v29);
    }
    if ( v13 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x8D,
        (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\fileoperationbroker.cpp",
        (const char *)(unsigned int)v13,
        (int)v27);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v34);
    v31[v10 - 1] = 0;
    v8 = v31;
    v6 = a4;
    a2 = v32;
  }
  v14 = -1;
  do
    ++v14;
  while ( v8[v14] );
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(a2 + 2 * v15) );
  if ( a3 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a3[v16] );
    v17 = v16 + 36;
  }
  else
  {
    v17 = 35;
  }
  memset(v37, 0, 30);
  v18 = -2147467259;
  if ( v6 <= 0x3E7 && !(unsigned int)_o__itow_s(v6, v37, 15, 10) )
  {
    do
      ++v9;
    while ( v37[v9] );
    v19 = v9 + v14 + 3;
    if ( !a4 )
      v19 = v14;
    v20 = v17 + v15 + v19;
    if ( v20 >= 0x104 )
    {
      v21 = v20 - 259;
      if ( v21 >= v15 )
        goto LABEL_42;
      LODWORD(v15) = v15 - v21;
    }
    v22 = a3;
    v23 = L".";
    if ( a4 )
    {
      if ( !a3 )
      {
        v22 = &pszSubkey;
        v23 = &pszSubkey;
      }
      LODWORD(v27) = v15;
      v24 = v33;
      v25 = StringCchPrintfW(v33, 0x104u, L"%s\\%.*s (%s)%s%s", v8, v27, v32, v37, v23, v22);
    }
    else
    {
      if ( !a3 )
      {
        v22 = &pszSubkey;
        v23 = &pszSubkey;
      }
      LODWORD(v27) = v15;
      v24 = v33;
      v25 = StringCchPrintfW(v33, 0x104u, L"%s\\%.*s%s%s", v8, v27, v32, v23, v22);
    }
    v18 = v25;
    if ( v25 >= 0 && a5 )
      v18 = anonymous_namespace_::ConvertFinalPathToProgressPathInPlace(v24);
  }
LABEL_42:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v31);
  return v18;
}

```

## disassembly

```asm
0x180027828  push    rbp
0x18002782a  push    rbx
0x18002782b  push    rsi
0x18002782c  push    rdi
0x18002782d  push    r12
0x18002782f  push    r13
0x180027831  push    r14
0x180027833  push    r15
0x180027835  lea     rbp, [rsp-7]
0x18002783a  sub     rsp, 0C8h
0x180027841  mov     rax, cs:__security_cookie
0x180027848  xor     rax, rsp
0x18002784b  mov     [rbp+3Fh+var_50], rax
0x18002784f  mov     r10d, r9d
0x180027852  mov     [rbp+3Fh+var_B0], r9d
0x180027856  mov     r13, r8
0x180027859  mov     [rbp+3Fh+var_A0], rdx
0x18002785d  mov     r15, rcx
0x180027860  mov     rax, [rbp+3Fh+arg_28]
0x180027864  mov     [rbp+3Fh+var_98], rax
0x180027868  xor     r12d, r12d
0x18002786b  mov     [rbp+3Fh+var_A8], r12
0x18002786f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180027873  mov     rdi, rsi
0x180027876  inc     rdi
0x180027879  cmp     [rcx+rdi*2], r12w
0x18002787e  jnz     short loc_180027876
0x180027880  test    rdi, rdi
0x180027883  jz      loc_18002793B
0x180027889  cmp     word ptr [rcx+rdi*2-2], 5Ch ; '\'
0x18002788f  jnz     loc_18002793B
0x180027895  lea     rax, [rbp+3Fh+var_A8]
0x180027899  mov     [rbp+3Fh+var_90], rax
0x18002789d  mov     [rbp+3Fh+var_80], 1
0x1800278a1  mov     [rbp+3Fh+var_88], r12
0x1800278a5  lea     r14, [rdi+1]
0x1800278a9  cmp     r14, rdi
0x1800278ac  jb      short loc_1800278FA
0x1800278ae  mov     rcx, r12; unsigned __int16 *
0x1800278b1  mov     [rbp+3Fh+var_88], rcx
0x1800278b5  mov     eax, 2
0x1800278ba  mul     r14
0x1800278bd  test    rdx, rdx
0x1800278c0  jnz     short loc_1800278E1
0x1800278c2  mov     rcx, rax; cb
0x1800278c5  call    cs:__imp_CoTaskMemAlloc
0x1800278cb  mov     rcx, rax
0x1800278ce  mov     [rbp+3Fh+var_88], rax
0x1800278d2  neg     rax
0x1800278d5  sbb     ebx, ebx
0x1800278d7  not     ebx
0x1800278d9  and     ebx, 8007000Eh
0x1800278df  jmp     short loc_1800278E6
0x1800278e1  mov     ebx, 80070216h
0x1800278e6  test    ebx, ebx
0x1800278e8  js      short loc_1800278FF
0x1800278ea  mov     r9, rdi; unsigned __int64
0x1800278ed  mov     r8, r15; unsigned __int16 *
0x1800278f0  mov     rdx, r14; unsigned __int64
0x1800278f3  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800278f8  jmp     short loc_1800278FF
0x1800278fa  mov     ebx, 80070216h
0x1800278ff  mov     rcx, [rbp+47h]; this
0x180027903  test    ebx, ebx
0x180027905  jns     short loc_18002791C
0x180027907  mov     r9d, ebx; char *
0x18002790a  lea     r8, aOnecoreuapInet_7; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180027911  mov     edx, 8Dh; void *
0x180027916  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18002791c  lea     rcx, [rbp+3Fh+var_90]
0x180027920  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180027925  mov     rax, [rbp+3Fh+var_A8]
0x180027929  mov     [rax+rdi*2-2], r12w
0x18002792f  mov     r15, [rbp+3Fh+var_A8]
0x180027933  mov     r10d, [rbp+3Fh+var_B0]
0x180027937  mov     rdx, [rbp+3Fh+var_A0]
0x18002793b  mov     r14, rsi
0x18002793e  inc     r14
0x180027941  cmp     [r15+r14*2], r12w
0x180027946  jnz     short loc_18002793E
0x180027948  mov     rdi, rsi
0x18002794b  inc     rdi
0x18002794e  cmp     [rdx+rdi*2], r12w
0x180027953  jnz     short loc_18002794B
0x180027955  test    r13, r13
0x180027958  jz      short loc_18002796E
0x18002795a  mov     rax, rsi
0x18002795d  inc     rax
0x180027960  cmp     [r13+rax*2+0], r12w
0x180027966  jnz     short loc_18002795D
0x180027968  lea     r12, [rax+24h]
0x18002796c  jmp     short loc_180027974
0x18002796e  mov     r12d, 23h ; '#'
0x180027974  xor     eax, eax
0x180027976  mov     [rbp+3Fh+var_70], ax
0x18002797a  xorps   xmm0, xmm0
0x18002797d  movups  xmmword ptr [rbp+3Fh+var_6E], xmm0
0x180027981  movups  xmmword ptr [rbp+3Fh+var_6E+0Ch], xmm0
0x180027985  mov     ebx, 80004005h
0x18002798a  cmp     r10d, 3E7h
0x180027991  ja      loc_180027A9F
0x180027997  lea     r9d, [rax+0Ah]
0x18002799b  lea     r8d, [rax+0Fh]
0x18002799f  lea     rdx, [rbp+3Fh+var_70]
0x1800279a3  mov     ecx, r10d
0x1800279a6  call    cs:__imp__o__itow_s
0x1800279ac  xor     edx, edx
0x1800279ae  test    eax, eax
0x1800279b0  jnz     loc_180027A9F
0x1800279b6  lea     rax, [rbp+3Fh+var_70]
0x1800279ba  inc     rsi
0x1800279bd  cmp     [rax+rsi*2], dx
0x1800279c1  jnz     short loc_1800279BA
0x1800279c3  lea     rax, [r14+3]
0x1800279c7  add     rax, rsi
0x1800279ca  mov     ecx, [rbp+3Fh+var_B0]
0x1800279cd  test    ecx, ecx
0x1800279cf  cmovz   rax, r14
0x1800279d3  add     rax, rdi
0x1800279d6  add     rax, r12
0x1800279d9  mov     r10d, 104h
0x1800279df  cmp     rax, r10
0x1800279e2  jb      short loc_1800279F5
0x1800279e4  add     rax, 0FFFFFFFFFFFFFEFDh
0x1800279ea  cmp     rax, rdi
0x1800279ed  jnb     loc_180027A9F
0x1800279f3  sub     edi, eax
0x1800279f5  lea     r8, pszSubkey
0x1800279fc  mov     rax, r13
0x1800279ff  mov     r9, r15
0x180027a02  mov     rdx, r10; unsigned __int64
0x180027a05  test    ecx, ecx
0x180027a07  lea     rcx, asc_180033B78; "."
0x180027a0e  jnz     short loc_180027A47
0x180027a10  test    r13, r13
0x180027a13  cmovz   rax, r8
0x180027a17  cmovz   rcx, r8
0x180027a1b  mov     [rsp+100h+var_C8], rax
0x180027a20  mov     [rsp+100h+var_D0], rcx
0x180027a25  mov     rax, [rbp+3Fh+var_A0]
0x180027a29  mov     [rsp+100h+var_D8], rax
0x180027a2e  mov     dword ptr [rsp+100h+var_E0], edi
0x180027a32  lea     r8, aSSSS_0; "%s\\%.*s%s%s"
0x180027a39  mov     rdi, [rbp+3Fh+var_98]
0x180027a3d  mov     rcx, rdi; unsigned __int16 *
0x180027a40  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027a45  jmp     short loc_180027A85
0x180027a47  test    r13, r13
0x180027a4a  cmovz   rax, r8
0x180027a4e  cmovz   rcx, r8
0x180027a52  mov     [rsp+100h+var_C0], rax
0x180027a57  mov     [rsp+100h+var_C8], rcx
0x180027a5c  lea     rax, [rbp+3Fh+var_70]
0x180027a60  mov     [rsp+100h+var_D0], rax
0x180027a65  mov     rax, [rbp+3Fh+var_A0]
0x180027a69  mov     [rsp+100h+var_D8], rax
0x180027a6e  mov     dword ptr [rsp+100h+var_E0], edi
0x180027a72  lea     r8, aSSSSS; "%s\\%.*s (%s)%s%s"
0x180027a79  mov     rdi, [rbp+3Fh+var_98]
0x180027a7d  mov     rcx, rdi; unsigned __int16 *
0x180027a80  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027a85  mov     ebx, eax
0x180027a87  xor     eax, eax
0x180027a89  test    ebx, ebx
0x180027a8b  js      short loc_180027A9F
0x180027a8d  cmp     [rbp+3Fh+arg_20], al
0x180027a90  jz      short loc_180027A9F
0x180027a92  mov     r8b, 1
0x180027a95  mov     rcx, rdi; unsigned __int16 *
0x180027a98  call    _anonymous_namespace___ConvertFinalPathToProgressPathInPlace
0x180027a9d  mov     ebx, eax
0x180027a9f  lea     rcx, [rbp+3Fh+var_A8]
0x180027aa3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180027aa8  mov     eax, ebx
0x180027aaa  mov     rcx, [rbp+3Fh+var_50]
0x180027aae  xor     rcx, rsp; StackCookie
0x180027ab1  call    __security_check_cookie
0x180027ab6  add     rsp, 0C8h
0x180027abd  pop     r15
0x180027abf  pop     r14
0x180027ac1  pop     r13
0x180027ac3  pop     r12
0x180027ac5  pop     rdi
0x180027ac6  pop     rsi
0x180027ac7  pop     rbx
0x180027ac8  pop     rbp
0x180027ac9  retn
```
