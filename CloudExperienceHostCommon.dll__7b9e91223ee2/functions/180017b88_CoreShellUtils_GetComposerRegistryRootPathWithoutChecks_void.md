# CoreShellUtils::GetComposerRegistryRootPathWithoutChecks(void)

- ea: `0x180017b88`
- end: `0x180017c4e`
- name: `?GetComposerRegistryRootPathWithoutChecks@CoreShellUtils@@YA?AVHString@Wrappers@WRL@Microsoft@@XZ`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180076d64`
- `0x1800774f8`

## callees

- `0x180017b88`
- `0x180018ecc`
- `0x18001a540`
- `0x18001b004`
- `0x1800227ac`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180017be8`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180017be8`

## string_xrefs

- `0x180017be1`: `CoreShellComposer`
- `0x180017bda`: `Software\Microsoft\CoreShell\Composer`
- `0x180017c06`: `onecoreuap\internal\shell\inc\composerclassregistration.h`

## pseudocode

```c
__int64 __fastcall CoreShellUtils::GetComposerRegistryRootPathWithoutChecks(__int64 a1)
{
  signed int PersistedRegistryLocationW; // eax
  bool v3; // sf
  int v5[4]; // [rsp+30h] [rbp-438h] BYREF
  _BYTE v6[1040]; // [rsp+40h] [rbp-428h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+468h] [rbp+0h]

  v5[1] = HIDWORD(a1);
  memset_0(v6, 0, sizeof(v6));
  v5[0] = 1040;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"CoreShellComposer",
                                 L"Software\\Microsoft\\CoreShell\\Composer",
                                 v6,
                                 1040);
  v3 = PersistedRegistryLocationW < 0;
  if ( PersistedRegistryLocationW > 0 )
  {
    PersistedRegistryLocationW = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    v3 = PersistedRegistryLocationW < 0;
  }
  if ( v3 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\composerclassregistration.h",
      (const char *)(unsigned int)PersistedRegistryLocationW,
      (int)v5);
  cshell::make_hstring(a1, v6, ((unsigned int)v5[0] >> 1) - 1);
  return a1;
}

```

## disassembly

```asm
0x180017b88  push    rbx
0x180017b8a  sub     rsp, 460h
0x180017b91  mov     rax, cs:__security_cookie
0x180017b98  xor     rax, rsp
0x180017b9b  mov     [rsp+468h+var_18], rax
0x180017ba3  mov     rbx, rcx
0x180017ba6  mov     qword ptr [rsp+468h+var_438], rcx
0x180017bab  lea     rcx, [rsp+468h+var_428]; void *
0x180017bb0  xor     edx, edx; Val
0x180017bb2  mov     r8d, 410h; Size
0x180017bb8  call    memset_0
0x180017bbd  lea     rax, [rsp+468h+var_438]
0x180017bc2  mov     [rsp+468h+var_438], 410h
0x180017bca  mov     r9d, 410h
0x180017bd0  mov     qword ptr [rsp+468h+var_448], rax; int
0x180017bd5  lea     r8, [rsp+468h+var_428]
0x180017bda  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\CoreShell\\Compose"...
0x180017be1  lea     rcx, aCoreshellcompo; "CoreShellComposer"
0x180017be8  call    cs:__imp_GetPersistedRegistryLocationW
0x180017bee  test    eax, eax
0x180017bf0  jle     short loc_180017BFC
0x180017bf2  movzx   eax, ax
0x180017bf5  or      eax, 80070000h
0x180017bfa  test    eax, eax
0x180017bfc  jns     short loc_180017C1A
0x180017bfe  mov     rcx, [rsp+468h]; this
0x180017c06  lea     r8, aOnecoreuapInte_7; "onecoreuap\\internal\\shell\\inc\\compo"...
0x180017c0d  mov     r9d, eax; char *
0x180017c10  mov     edx, 80h; void *
0x180017c15  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017c1a  mov     r8d, [rsp+468h+var_438]
0x180017c1f  lea     rdx, [rsp+468h+var_428]
0x180017c24  shr     r8d, 1
0x180017c27  mov     rcx, rbx
0x180017c2a  dec     r8d
0x180017c2d  call    ?make_hstring@cshell@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBGI@Z; cshell::make_hstring(ushort const *,uint)
0x180017c32  mov     rax, rbx
0x180017c35  mov     rcx, [rsp+468h+var_18]
0x180017c3d  xor     rcx, rsp; StackCookie
0x180017c40  call    __security_check_cookie
0x180017c45  add     rsp, 460h
0x180017c4c  pop     rbx
0x180017c4d  retn
```
