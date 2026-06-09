# ConvertArrayToPaths(Windows::Data::Json::IJsonArray *)

- ea: `0x14000a934`
- end: `0x14000ac17`
- name: `?ConvertArrayToPaths@@YA?AV?$vector@GV?$allocator@G@std@@@std@@PEAUIJsonArray@Json@Data@Windows@@@Z`
- size: `739`
- prototype: `void **__fastcall(void **, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000f3b8`

## callees

- `0x140002504`
- `0x14000305c`
- `0x14000704c`
- `0x140009260`
- `0x140009d90`
- `0x14000a934`
- `0x14000d49c`
- `0x14000f794`
- `0x14000fbb0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x14000aa33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x14000aa33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000aa07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000aa42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000aaa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ab0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000aa07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000aa42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000aaa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ab0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000aad6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000aad6`

## pseudocode

```c
void **__fastcall ConvertArrayToPaths(void **a1, __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  unsigned int v4; // r12d
  __int64 (__fastcall *v5)(_QWORD, GUID *, __int64 *); // rbx
  int v6; // eax
  int v7; // eax
  unsigned __int64 v8; // r13
  unsigned int i; // r14d
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  int v11; // eax
  unsigned __int16 *v12; // r15
  unsigned __int16 *v13; // r14
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rbx
  int v15; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int v17; // eax
  __int64 v18; // r11
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rcx
  unsigned __int64 v22; // rdi
  char *v23; // rbx
  unsigned __int16 *v24; // rcx
  unsigned __int64 v26; // r14
  __int64 v27; // [rsp+28h] [rbp-20h]
  _QWORD v28[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  unsigned int v30; // [rsp+98h] [rbp+50h] BYREF
  HSTRING string; // [rsp+A0h] [rbp+58h] BYREF
  __int64 v32; // [rsp+A8h] [rbp+60h] BYREF

  v4 = 0;
  v32 = 0;
  v30 = 0;
  v28[0] = a2;
  if ( a2 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[1])(a2);
  v5 = **a2;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v32);
  v6 = v5(a2, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v32);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x31F,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v6,
      0);
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 56LL))(v32, &v30);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x320,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v7,
      0);
  LODWORD(v8) = 0;
  for ( i = 0; i < v30; ++i )
  {
    string = 0;
    v10 = (*a2)[8];
    WindowsDeleteString(0);
    string = 0;
    v11 = v10(a2, (GUID *)i, (__int64 *)&string);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x327,
        (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
        (const char *)(unsigned int)v11,
        0);
    LODWORD(v8) = WindowsGetStringLen(string) + 1 + v8;
    WindowsDeleteString(string);
  }
  v12 = (unsigned __int16 *)operator new[](saturated_mul((int)v8 + 1, 2u));
  v28[1] = v12;
  v13 = v12;
  v27 = (int)v8;
  v8 = (int)v8;
  if ( v30 )
  {
    while ( 1 )
    {
      string = 0;
      v14 = (*a2)[8];
      WindowsDeleteString(0);
      string = 0;
      v15 = v14(a2, (GUID *)v4, (__int64 *)&string);
      if ( v15 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x331,
          (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
          (const char *)(unsigned int)v15,
          0);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v17 = StringCchCopyW(v13, v8, StringRawBuffer);
      if ( v17 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x333,
          (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
          (const char *)(unsigned int)v17,
          0);
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)(v18 + 2 * v19) );
      v20 = v19 + 1;
      v13 += v19 + 1;
      WindowsDeleteString(string);
      if ( ++v4 >= v30 )
        break;
      v8 -= v20;
    }
  }
  *v13 = 0;
  std::vector<AppUriHandlerRegistrationInfo>::vector<AppUriHandlerRegistrationInfo>(a1);
  v22 = (2 * v27 + 2) >> 1;
  v23 = (char *)*a1;
  if ( v22 <= ((_BYTE *)a1[2] - (_BYTE *)*a1) >> 1 )
  {
    v26 = ((_BYTE *)a1[1] - v23) >> 1;
    if ( v22 > v26 )
    {
      std::_Copy_memmove_n<unsigned short *,unsigned short *>(v12, ((_BYTE *)a1[1] - v23) >> 1, *a1);
      v23 = (char *)a1[1];
      v22 -= v26;
      v24 = &v12[v26];
      goto LABEL_23;
    }
  }
  else
  {
    std::vector<unsigned short>::_Clear_and_reserve_geometric(v21, (2 * v27 + 2) >> 1);
    v23 = (char *)*a1;
  }
  v24 = v12;
LABEL_23:
  std::_Copy_memmove_n<unsigned short *,unsigned short *>(v24, v22, v23);
  a1[1] = &v23[2 * v22];
  operator delete(v12);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(v28);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v32);
  return a1;
}

```

## disassembly

```asm
0x14000a934  mov     [rsp-40h+arg_0], rcx
0x14000a939  push    rbp
0x14000a93a  push    rbx
0x14000a93b  push    rsi
0x14000a93c  push    rdi
0x14000a93d  push    r12
0x14000a93f  push    r13
0x14000a941  push    r14
0x14000a943  push    r15
0x14000a945  mov     rbp, rsp
0x14000a948  sub     rsp, 48h
0x14000a94c  mov     rdi, rdx
0x14000a94f  mov     rsi, rcx
0x14000a952  xor     r12d, r12d
0x14000a955  mov     [rbp+var_28], r12d
0x14000a959  mov     [rbp+arg_18], r12
0x14000a95d  mov     [rbp+arg_8], r12d
0x14000a961  mov     [rbp+var_18], rdx
0x14000a965  test    rdx, rdx
0x14000a968  jz      short loc_14000A97A
0x14000a96a  mov     rax, [rdx]
0x14000a96d  mov     rcx, rdx
0x14000a970  mov     rax, [rax+8]
0x14000a974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a979  nop
0x14000a97a  mov     rax, [rdi]
0x14000a97d  mov     rbx, [rax]
0x14000a980  lea     rcx, [rbp+arg_18]
0x14000a984  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000a989  lea     r8, [rbp+arg_18]
0x14000a98d  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x14000a994  mov     rcx, rdi
0x14000a997  mov     rax, rbx
0x14000a99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a99f  nop
0x14000a9a0  mov     rcx, [rbp+40h]; this
0x14000a9a4  test    eax, eax
0x14000a9a6  jns     short loc_14000A9BD
0x14000a9a8  mov     r9d, eax; char *
0x14000a9ab  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000a9b2  mov     edx, 31Fh; void *
0x14000a9b7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000a9bd  mov     rcx, [rbp+arg_18]
0x14000a9c1  mov     rax, [rcx]
0x14000a9c4  lea     rdx, [rbp+arg_8]
0x14000a9c8  mov     rax, [rax+38h]
0x14000a9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9d1  mov     rcx, [rbp+40h]; this
0x14000a9d5  test    eax, eax
0x14000a9d7  jns     short loc_14000A9EE
0x14000a9d9  mov     r9d, eax; char *
0x14000a9dc  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000a9e3  mov     edx, 320h; void *
0x14000a9e8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000a9ee  mov     r13d, r12d
0x14000a9f1  mov     r14d, r12d
0x14000a9f4  cmp     [rbp+arg_8], r12d
0x14000a9f8  jbe     short loc_14000AA51
0x14000a9fa  mov     [rbp+string], r12
0x14000a9fe  mov     rax, [rdi]
0x14000aa01  mov     rbx, [rax+40h]
0x14000aa05  xor     ecx, ecx; string
0x14000aa07  call    cs:__imp_WindowsDeleteString
0x14000aa0d  mov     [rbp+string], r12
0x14000aa11  lea     r8, [rbp+string]
0x14000aa15  mov     edx, r14d
0x14000aa18  mov     rcx, rdi
0x14000aa1b  mov     rax, rbx
0x14000aa1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa23  mov     rcx, [rbp+40h]; this
0x14000aa27  test    eax, eax
0x14000aa29  js      loc_14000AB26
0x14000aa2f  mov     rcx, [rbp+string]; string
0x14000aa33  call    cs:__imp_WindowsGetStringLen
0x14000aa39  inc     eax
0x14000aa3b  add     r13d, eax
0x14000aa3e  mov     rcx, [rbp+string]; string
0x14000aa42  call    cs:__imp_WindowsDeleteString
0x14000aa48  inc     r14d
0x14000aa4b  cmp     r14d, [rbp+arg_8]
0x14000aa4f  jb      short loc_14000A9FA
0x14000aa51  lea     eax, [r13+1]
0x14000aa55  movsxd  rcx, eax
0x14000aa58  mov     eax, 2
0x14000aa5d  mul     rcx
0x14000aa60  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000aa67  cmovb   rax, rcx
0x14000aa6b  mov     rcx, rax; unsigned __int64
0x14000aa6e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000aa73  mov     r15, rax
0x14000aa76  mov     [rbp+var_10], rax
0x14000aa7a  mov     r14, rax
0x14000aa7d  movsxd  rax, r13d
0x14000aa80  mov     [rbp+var_20], rax
0x14000aa84  mov     r13, rax
0x14000aa87  cmp     [rbp+arg_8], 0
0x14000aa8b  jbe     loc_14000AB65
0x14000aa91  mov     [rbp+string], 0
0x14000aa99  mov     rax, [rdi]
0x14000aa9c  mov     rbx, [rax+40h]
0x14000aaa0  xor     ecx, ecx; string
0x14000aaa2  call    cs:__imp_WindowsDeleteString
0x14000aaa8  mov     [rbp+string], 0
0x14000aab0  lea     r8, [rbp+string]
0x14000aab4  mov     edx, r12d
0x14000aab7  mov     rcx, rdi
0x14000aaba  mov     rax, rbx
0x14000aabd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aac2  mov     rcx, [rbp+40h]; this
0x14000aac6  xor     ebx, ebx
0x14000aac8  test    eax, eax
0x14000aaca  js      loc_14000AB50
0x14000aad0  xor     edx, edx; length
0x14000aad2  mov     rcx, [rbp+string]; string
0x14000aad6  call    cs:__imp_WindowsGetStringRawBuffer
0x14000aadc  mov     r11, rax
0x14000aadf  mov     r8, rax; unsigned __int16 *
0x14000aae2  mov     rdx, r13; unsigned __int64
0x14000aae5  mov     rcx, r14; unsigned __int16 *
0x14000aae8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000aaed  mov     rcx, [rbp+40h]; this
0x14000aaf1  test    eax, eax
0x14000aaf3  js      short loc_14000AB3B
0x14000aaf5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000aaf9  inc     rcx
0x14000aafc  cmp     [r11+rcx*2], bx
0x14000ab01  jnz     short loc_14000AAF9
0x14000ab03  lea     rbx, [rcx+1]
0x14000ab07  lea     r14, [r14+rbx*2]
0x14000ab0b  mov     rcx, [rbp+string]; string
0x14000ab0f  call    cs:__imp_WindowsDeleteString
0x14000ab15  inc     r12d
0x14000ab18  cmp     r12d, [rbp+arg_8]
0x14000ab1c  jnb     short loc_14000AB65
0x14000ab1e  sub     r13, rbx
0x14000ab21  jmp     loc_14000AA91
0x14000ab26  mov     r9d, eax; char *
0x14000ab29  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000ab30  mov     edx, 327h; void *
0x14000ab35  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000ab3b  mov     r9d, eax; char *
0x14000ab3e  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000ab45  mov     edx, 333h; void *
0x14000ab4a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000ab50  mov     r9d, eax; char *
0x14000ab53  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000ab5a  mov     edx, 331h; void *
0x14000ab5f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000ab65  xor     eax, eax
0x14000ab67  mov     [r14], ax
0x14000ab6b  mov     rcx, rsi
0x14000ab6e  call    ??0?$vector@UAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@QEAA@XZ; std::vector<AppUriHandlerRegistrationInfo>::vector<AppUriHandlerRegistrationInfo>(void)
0x14000ab73  mov     [rbp+var_28], 1
0x14000ab7a  mov     rdi, [rbp+var_20]
0x14000ab7e  lea     rdi, ds:2[rdi*2]
0x14000ab86  sar     rdi, 1
0x14000ab89  mov     rbx, [rsi]
0x14000ab8c  mov     rax, [rsi+10h]
0x14000ab90  sub     rax, rbx
0x14000ab93  sar     rax, 1
0x14000ab96  cmp     rdi, rax
0x14000ab99  jbe     short loc_14000ABEC
0x14000ab9b  mov     rdx, rdi
0x14000ab9e  call    ?_Clear_and_reserve_geometric@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Clear_and_reserve_geometric(unsigned __int64)
0x14000aba3  mov     rbx, [rsi]
0x14000aba6  mov     rcx, r15; Src
0x14000aba9  mov     r8, rbx
0x14000abac  mov     rdx, rdi
0x14000abaf  call    ??$_Copy_memmove_n@PEAGPEAG@std@@YAPEAGPEAG_K0@Z; std::_Copy_memmove_n<ushort *,ushort *>(ushort *,unsigned __int64,ushort *)
0x14000abb4  lea     rax, [rbx+rdi*2]
0x14000abb8  mov     [rsi+8], rax
0x14000abbc  mov     rcx, r15; void *
0x14000abbf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000abc4  nop
0x14000abc5  lea     rcx, [rbp+var_18]
0x14000abc9  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000abce  nop
0x14000abcf  lea     rcx, [rbp+arg_18]
0x14000abd3  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000abd8  mov     rax, rsi
0x14000abdb  add     rsp, 48h
0x14000abdf  pop     r15
0x14000abe1  pop     r14
0x14000abe3  pop     r13
0x14000abe5  pop     r12
0x14000abe7  pop     rdi
0x14000abe8  pop     rsi
0x14000abe9  pop     rbx
0x14000abea  pop     rbp
0x14000abeb  retn
0x14000abec  mov     r14, [rsi+8]
0x14000abf0  sub     r14, rbx
0x14000abf3  sar     r14, 1
0x14000abf6  cmp     rdi, r14
0x14000abf9  jbe     short loc_14000ABA6
0x14000abfb  mov     r8, rbx
0x14000abfe  mov     rdx, r14
0x14000ac01  mov     rcx, r15; Src
0x14000ac04  call    ??$_Copy_memmove_n@PEAGPEAG@std@@YAPEAGPEAG_K0@Z; std::_Copy_memmove_n<ushort *,ushort *>(ushort *,unsigned __int64,ushort *)
0x14000ac09  mov     rbx, [rsi+8]
0x14000ac0d  sub     rdi, r14
0x14000ac10  lea     rcx, [r15+r14*2]
0x14000ac14  jmp     short loc_14000ABA9
```
