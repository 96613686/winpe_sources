# GetModernAppId

- ea: `0x1800cf08c`
- end: `0x1800cf237`
- name: `GetModernAppId`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800cee68`

## callees

- `0x18001332c`
- `0x180013ac8`
- `0x180014a5c`
- `0x1800cee48`
- `0x1800cf004`
- `0x1800cf08c`
- `0x1800cf570`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cf157`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cf157`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cf19b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cf19b`

## string_xrefs

- `0x1800cf181`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800cf0e1`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`
- `0x1800cf20f`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`

## pseudocode

```c
__int64 __fastcall GetModernAppId(__int64 a1, unsigned __int16 **a2, _DWORD *a3)
{
  const unsigned __int16 *v5; // r15
  int v6; // ebx
  __int64 v7; // r11
  __int64 v8; // rdx
  const unsigned __int16 *v10; // r14
  __int64 v11; // r11
  __int64 v12; // rax
  const char *v13; // r9
  unsigned __int64 v14; // r13
  unsigned __int64 v15; // rdi
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rbx
  int v18; // eax
  unsigned int v19; // edi
  __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // [rsp+20h] [rbp-28h]
  __int64 v23[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  const unsigned __int16 *v25; // [rsp+90h] [rbp+48h] BYREF
  unsigned __int64 v26; // [rsp+98h] [rbp+50h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+58h] BYREF
  unsigned __int64 v28; // [rsp+A8h] [rbp+60h] BYREF

  *a2 = 0;
  *a3 = 0;
  v5 = (const unsigned __int16 *)(a1 + *(unsigned int *)(a1 + 80));
  v28 = 0;
  v6 = StringCchLengthW(v5, 0x104u, &v28);
  if ( v6 < 0 )
  {
    v8 = 71;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
      (const char *)(unsigned int)v6,
      v22);
    return (unsigned int)v6;
  }
  v10 = (const unsigned __int16 *)(v7 + *(unsigned int *)(v7 + 84));
  v26 = 0;
  v6 = StringCchLengthW(v10, 0x104u, &v26);
  if ( v6 < 0 )
  {
    v8 = 76;
    goto LABEL_3;
  }
  v12 = *(unsigned int *)(v11 + 76);
  v27 = 0;
  v23[0] = v11 + v12;
  v25 = &dword_180112D8C;
  GetFileName(v23, &v25, &v27);
  *a3 = ((unsigned int)_o__wcsicmp(v25, L"wwahost.exe") != 0) + 1;
  v14 = v28 + v26 + v27;
  v15 = v14 + 8;
  if ( v14 == -9 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v13);
  v16 = (unsigned __int16 *)CoTaskMemAlloc(2 * v15 + 2);
  v25 = v16;
  v17 = v16;
  if ( v16 )
  {
    *v16 = 0;
    v16[v15] = 0;
    v22 = (int)v10;
    v18 = StringCchPrintfW(v16, v14 + 9, aUSS, v5);
    v19 = v18;
    if ( v18 >= 0 )
    {
      v25 = 0;
      *a2 = v17;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
      return 0;
    }
    v20 = (unsigned int)v18;
    v21 = 126;
  }
  else
  {
    v19 = -2147024882;
    v21 = 114;
    v20 = 2147942414LL;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v21,
    (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
    (const char *)v20,
    v22);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
  return v19;
}

```

## disassembly

```asm
0x1800cf08c  push    rbp
0x1800cf08e  push    rbx
0x1800cf08f  push    rsi
0x1800cf090  push    rdi
0x1800cf091  push    r12
0x1800cf093  push    r13
0x1800cf095  push    r14
0x1800cf097  push    r15
0x1800cf099  mov     rbp, rsp
0x1800cf09c  sub     rsp, 48h
0x1800cf0a0  xor     r12d, r12d
0x1800cf0a3  mov     rsi, rdx
0x1800cf0a6  mov     [rdx], r12
0x1800cf0a9  mov     r11, rcx
0x1800cf0ac  mov     [r8], r12d
0x1800cf0af  mov     r13d, 104h
0x1800cf0b5  mov     r15d, [rcx+50h]
0x1800cf0b9  mov     rdi, r8
0x1800cf0bc  add     r15, rcx
0x1800cf0bf  mov     [rbp+arg_18], r12
0x1800cf0c3  mov     rcx, r15; unsigned __int16 *
0x1800cf0c6  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x1800cf0ca  mov     edx, r13d; unsigned __int64
0x1800cf0cd  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800cf0d2  mov     ebx, eax
0x1800cf0d4  test    eax, eax
0x1800cf0d6  jns     short loc_1800CF0F7
0x1800cf0d8  lea     edx, [r12+47h]; void *
0x1800cf0dd  mov     rcx, [rbp+40h]; this
0x1800cf0e1  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\dwm\\common\\telem"...
0x1800cf0e8  mov     r9d, ebx; char *
0x1800cf0eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf0f0  mov     eax, ebx
0x1800cf0f2  jmp     loc_1800CF226
0x1800cf0f7  mov     r14d, [r11+54h]
0x1800cf0fb  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x1800cf0ff  add     r14, r11
0x1800cf102  mov     [rbp+arg_8], r12
0x1800cf106  mov     rcx, r14; unsigned __int16 *
0x1800cf109  mov     rdx, r13; unsigned __int64
0x1800cf10c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800cf111  mov     ebx, eax
0x1800cf113  test    eax, eax
0x1800cf115  jns     short loc_1800CF11E
0x1800cf117  mov     edx, 4Ch ; 'L'
0x1800cf11c  jmp     short loc_1800CF0DD
0x1800cf11e  mov     eax, [r11+4Ch]
0x1800cf122  lea     r8, [rbp+arg_10]
0x1800cf126  add     rax, r11
0x1800cf129  mov     [rbp+arg_10], r12
0x1800cf12d  mov     [rbp+var_18], rax
0x1800cf131  lea     rdx, [rbp+arg_0]
0x1800cf135  lea     rax, dword_180112D8C
0x1800cf13c  lea     rcx, [rbp+var_18]
0x1800cf140  mov     [rbp+arg_0], rax
0x1800cf144  call    GetFileName
0x1800cf149  mov     r12, [rbp+arg_0]
0x1800cf14d  lea     rdx, aWwahostExe; "wwahost.exe"
0x1800cf154  mov     rcx, r12
0x1800cf157  call    cs:__imp__o__wcsicmp
0x1800cf15d  neg     eax
0x1800cf15f  sbb     ecx, ecx
0x1800cf161  neg     ecx
0x1800cf163  inc     ecx
0x1800cf165  mov     [rdi], ecx
0x1800cf167  mov     r13, [rbp+arg_10]
0x1800cf16b  add     r13, [rbp+arg_8]
0x1800cf16f  add     r13, [rbp+arg_18]
0x1800cf173  lea     rdi, [r13+8]
0x1800cf177  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800cf17b  jnz     short loc_1800CF193
0x1800cf17d  mov     rcx, [rbp+40h]; this
0x1800cf181  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800cf188  mov     edx, 0F89h; void *
0x1800cf18d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800cf193  lea     rcx, ds:2[rdi*2]; cb
0x1800cf19b  call    cs:__imp_CoTaskMemAlloc
0x1800cf1a1  mov     [rbp+arg_0], rax
0x1800cf1a5  mov     rbx, rax
0x1800cf1a8  test    rax, rax
0x1800cf1ab  jz      short loc_1800CF1FE
0x1800cf1ad  xor     ecx, ecx
0x1800cf1af  mov     [rsp+48h+var_20], r12
0x1800cf1b4  mov     [rax], cx
0x1800cf1b7  lea     r8, aUSS; "U:%s!%s"
0x1800cf1be  mov     [rax+rdi*2], cx
0x1800cf1c2  lea     rdx, [r13+9]; unsigned __int64
0x1800cf1c6  mov     rcx, rax; unsigned __int16 *
0x1800cf1c9  mov     [rsp+48h+var_28], r14
0x1800cf1ce  mov     r9, r15
0x1800cf1d1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cf1d6  mov     edi, eax
0x1800cf1d8  test    eax, eax
0x1800cf1da  jns     short loc_1800CF1E6
0x1800cf1dc  mov     r9d, eax
0x1800cf1df  mov     edx, 7Eh ; '~'
0x1800cf1e4  jmp     short loc_1800CF20B
0x1800cf1e6  lea     rcx, [rbp+arg_0]
0x1800cf1ea  mov     [rbp+arg_0], 0
0x1800cf1f2  mov     [rsi], rbx
0x1800cf1f5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800cf1fa  xor     eax, eax
0x1800cf1fc  jmp     short loc_1800CF226
0x1800cf1fe  mov     edi, 8007000Eh
0x1800cf203  mov     edx, 72h ; 'r'; void *
0x1800cf208  mov     r9d, edi; char *
0x1800cf20b  mov     rcx, [rbp+40h]; this
0x1800cf20f  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\dwm\\common\\telem"...
0x1800cf216  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf21b  lea     rcx, [rbp+arg_0]
0x1800cf21f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800cf224  mov     eax, edi
0x1800cf226  add     rsp, 48h
0x1800cf22a  pop     r15
0x1800cf22c  pop     r14
0x1800cf22e  pop     r13
0x1800cf230  pop     r12
0x1800cf232  pop     rdi
0x1800cf233  pop     rsi
0x1800cf234  pop     rbx
0x1800cf235  pop     rbp
0x1800cf236  retn
```
