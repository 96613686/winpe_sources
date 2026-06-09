# _anonymous_namespace_::GetPackageFamilyNameFromPackage

- ea: `0x18006df84`
- end: `0x18006e0b0`
- name: `_anonymous_namespace_::GetPackageFamilyNameFromPackage`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006df40`

## callees

- `0x180008d50`
- `0x18001ccf0`
- `0x18006df84`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dfd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dfd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e004`

## string_xrefs

- `0x18006e089`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006e09e`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall anonymous_namespace_::GetPackageFamilyNameFromPackage(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v13; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  HSTRING string; // [rsp+70h] [rbp+40h] BYREF
  __int64 v16; // [rsp+78h] [rbp+48h] BYREF

  v16 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 72LL))(*a2, &v16);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v4,
      v13);
  string = 0;
  v5 = v16;
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v16 + 88LL);
  WindowsDeleteString(0);
  string = 0;
  v7 = v6(v5, &string);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v7,
      v13);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v9 = -1;
  do
    ++v9;
  while ( StringRawBuffer[v9] );
  std::wstring::_Construct<1,unsigned short const *>(a1, StringRawBuffer, v9);
  WindowsDeleteString(string);
  string = 0;
  v10 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return a1;
}

```

## disassembly

```asm
0x18006df84  mov     [rsp-28h+arg_0], rbx
0x18006df89  mov     [rsp-28h+arg_8], rdx
0x18006df8e  push    rbp
0x18006df8f  push    rsi
0x18006df90  push    rdi
0x18006df91  push    r14
0x18006df93  push    r15
0x18006df95  mov     rbp, rsp
0x18006df98  sub     rsp, 30h
0x18006df9c  mov     r14, rdx
0x18006df9f  mov     rsi, rcx
0x18006dfa2  xor     r15d, r15d
0x18006dfa5  mov     [rbp+arg_18], r15
0x18006dfa9  mov     rcx, [rdx]
0x18006dfac  mov     rax, [rcx]
0x18006dfaf  lea     rdx, [rbp+arg_18]
0x18006dfb3  mov     rax, [rax+48h]
0x18006dfb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dfbc  mov     rcx, [rbp+28h]; this
0x18006dfc0  test    eax, eax
0x18006dfc2  js      loc_18006E09B
0x18006dfc8  mov     [rbp+string], r15
0x18006dfcc  mov     rdi, [rbp+arg_18]
0x18006dfd0  mov     rax, [rdi]
0x18006dfd3  mov     rbx, [rax+58h]
0x18006dfd7  xor     ecx, ecx; string
0x18006dfd9  call    cs:__imp_WindowsDeleteString
0x18006dfdf  mov     [rbp+string], r15
0x18006dfe3  lea     rdx, [rbp+string]
0x18006dfe7  mov     rcx, rdi
0x18006dfea  mov     rax, rbx
0x18006dfed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dff2  mov     rcx, [rbp+28h]; this
0x18006dff6  test    eax, eax
0x18006dff8  js      loc_18006E086
0x18006dffe  xor     edx, edx; length
0x18006e000  mov     rcx, [rbp+string]; string
0x18006e004  call    cs:__imp_WindowsGetStringRawBuffer
0x18006e00a  xorps   xmm0, xmm0
0x18006e00d  movups  xmmword ptr [rsi], xmm0
0x18006e010  mov     [rsi+10h], r15
0x18006e014  mov     [rsi+18h], r15
0x18006e018  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006e01c  inc     r8
0x18006e01f  cmp     [rax+r8*2], r15w
0x18006e024  jnz     short loc_18006E01C
0x18006e026  mov     rdx, rax
0x18006e029  mov     rcx, rsi
0x18006e02c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18006e031  nop
0x18006e032  mov     rcx, [rbp+string]; string
0x18006e036  call    cs:__imp_WindowsDeleteString
0x18006e03c  mov     [rbp+string], r15
0x18006e040  mov     rcx, [rbp+arg_18]
0x18006e044  test    rcx, rcx
0x18006e047  jz      short loc_18006E05A
0x18006e049  mov     [rbp+arg_18], r15
0x18006e04d  mov     rax, [rcx]
0x18006e050  mov     rax, [rax+10h]
0x18006e054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e059  nop
0x18006e05a  mov     rcx, [r14]
0x18006e05d  test    rcx, rcx
0x18006e060  jz      short loc_18006E072
0x18006e062  mov     [r14], r15
0x18006e065  mov     rax, [rcx]
0x18006e068  mov     rax, [rax+10h]
0x18006e06c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e071  nop
0x18006e072  mov     rax, rsi
0x18006e075  mov     rbx, [rsp+30h+arg_0]
0x18006e07a  add     rsp, 30h
0x18006e07e  pop     r15
0x18006e080  pop     r14
0x18006e082  pop     rdi
0x18006e083  pop     rsi
0x18006e084  pop     rbp
0x18006e085  retn
0x18006e086  mov     r9d, eax; char *
0x18006e089  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006e090  mov     edx, 6Ah ; 'j'; void *
0x18006e095  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006e09b  mov     r9d, eax; char *
0x18006e09e  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006e0a5  mov     edx, 67h ; 'g'; void *
0x18006e0aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
