# StateRepository::Macros::Evaluators::BuiltIn::Expand(ushort const *,StateRepository::Core::Text &,SRCacheExpandMacrosFlags,bool &)

- ea: `0x18000f228`
- end: `0x18000f374`
- name: `?Expand@BuiltIn@Evaluators@Macros@StateRepository@@YAJPEBGAEAVText@Core@4@W4SRCacheExpandMacrosFlags@@AEA_N@Z`
- size: `332`
- prototype: `__int64 __fastcall(const WCHAR *, StateRepository::Core::Text *, char, struct StateRepository::Core::Text *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000df50`

## callees

- `0x180001ed0`
- `0x18000940c`
- `0x18000f174`
- `0x18000f228`
- `0x18000f450`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f297`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f328`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f297`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f328`

## pseudocode

```c
__int64 __fastcall StateRepository::Macros::Evaluators::BuiltIn::Expand(
        const WCHAR *a1,
        StateRepository::Core::Text *a2,
        char a3,
        struct StateRepository::Core::Text *a4)
{
  unsigned int v7; // ebx
  unsigned __int64 v8; // rdi
  const WCHAR *v9; // r8
  __int64 (__fastcall *v10)(const WCHAR *, StateRepository::Core::Text *, struct StateRepository::Core::Text *); // rbp
  int v11; // ebx
  __int64 v12; // rdx
  bool *v14; // r9
  BOOL bIgnoreCase; // [rsp+20h] [rbp-68h]
  WCHAR String1[8]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *(_BYTE *)a4 = 0;
  if ( (a3 & 1) == 0 )
  {
    v7 = 0;
    v8 = -1;
    while ( v7 < 2 )
    {
      v9 = (&off_1800121A0)[2 * (int)v7];
      if ( v9 )
      {
        v10 = (__int64 (__fastcall *)(const WCHAR *, StateRepository::Core::Text *, struct StateRepository::Core::Text *))*(&funcs_18000F2B6 + 2 * (int)v7);
        if ( CompareStringOrdinal(a1, -1, v9, -1, 1) == 2 )
        {
          *(_BYTE *)a4 = 1;
          v11 = v10(a1, a2, a4);
          if ( v11 >= 0 )
            return 0;
          v12 = 58;
          goto LABEL_9;
        }
      }
      ++v7;
    }
    wcscpy(String1, L"env:");
    do
      ++v8;
    while ( a1[v8] );
    if ( v8 > 4 && CompareStringOrdinal(String1, 4, a1, 4, 1) == 2 )
    {
      *(_BYTE *)a4 = 1;
      v11 = StateRepository::Macros::Evaluators::BuiltIn::Env(
              (StateRepository::Macros::Evaluators::BuiltIn *)(a1 + 4),
              a2,
              a4,
              v14);
      if ( v11 < 0 )
      {
        v12 = 77;
LABEL_9:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srmacros-builtin.cpp",
          (const char *)(unsigned int)v11,
          bIgnoreCase);
        return (unsigned int)v11;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f228  push    rbx
0x18000f22a  push    rbp
0x18000f22b  push    rsi
0x18000f22c  push    rdi
0x18000f22d  push    r12
0x18000f22f  push    r14
0x18000f231  push    r15
0x18000f233  sub     rsp, 50h
0x18000f237  mov     rax, cs:__security_cookie
0x18000f23e  xor     rax, rsp
0x18000f241  mov     [rsp+88h+var_48], rax
0x18000f246  xor     r12d, r12d
0x18000f249  mov     r14, r9
0x18000f24c  mov     [r9], r12b
0x18000f24f  mov     r15, rdx
0x18000f252  mov     rsi, rcx
0x18000f255  test    r8b, 1
0x18000f259  jnz     loc_18000F356
0x18000f25f  mov     ebx, r12d
0x18000f262  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f266  cmp     ebx, 2
0x18000f269  jnb     short loc_18000F2E5
0x18000f26b  movsxd  rax, ebx
0x18000f26e  lea     rbp, off_1800121A0; "windows.path"
0x18000f275  add     rax, rax
0x18000f278  mov     r8, [rbp+rax*8+0]; lpString2
0x18000f27d  test    r8, r8
0x18000f280  jz      short loc_18000F2A2
0x18000f282  mov     rbp, ss:(funcs_18000F2B6 - 1800121A0h)[rbp+rax*8]
0x18000f287  mov     r9d, edi; cchCount2
0x18000f28a  mov     edx, edi; cchCount1
0x18000f28c  mov     [rsp+88h+bIgnoreCase], 1; int
0x18000f294  mov     rcx, rsi; lpString1
0x18000f297  call    cs:__imp_CompareStringOrdinal
0x18000f29d  cmp     eax, 2
0x18000f2a0  jz      short loc_18000F2A6
0x18000f2a2  inc     ebx
0x18000f2a4  jmp     short loc_18000F266
0x18000f2a6  mov     r8, r14; struct StateRepository::Core::Text *
0x18000f2a9  mov     byte ptr [r14], 1
0x18000f2ad  mov     rdx, r15; unsigned __int16 *
0x18000f2b0  mov     rcx, rsi; this
0x18000f2b3  mov     rax, rbp
0x18000f2b6  call    _guard_dispatch_icall$thunk$10345483385596137414; StateRepository::Macros::Evaluators::BuiltIn::WindowsPath(ushort const *,StateRepository::Core::Text &,bool &) ...
0x18000f2bb  mov     ebx, eax
0x18000f2bd  test    eax, eax
0x18000f2bf  jns     loc_18000F356
0x18000f2c5  mov     edx, 3Ah ; ':'; void *
0x18000f2ca  mov     rcx, [rsp+88h]; this
0x18000f2d2  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x18000f2d9  mov     r9d, ebx; char *
0x18000f2dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f2e1  mov     eax, ebx
0x18000f2e3  jmp     short loc_18000F358
0x18000f2e5  movsd   xmm0, qword ptr cs:aEnv; "env:"
0x18000f2ed  movzx   eax, word ptr cs:aEnv+8; ""
0x18000f2f4  movsd   qword ptr [rsp+88h+String1], xmm0
0x18000f2fa  mov     [rsp+88h+var_50], ax
0x18000f2ff  inc     rdi
0x18000f302  cmp     [rsi+rdi*2], r12w
0x18000f307  jnz     short loc_18000F2FF
0x18000f309  cmp     rdi, 4
0x18000f30d  jbe     short loc_18000F356
0x18000f30f  mov     r9d, 4; cchCount2
0x18000f315  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x18000f31d  mov     edx, r9d; cchCount1
0x18000f320  lea     rcx, [rsp+88h+String1]; lpString1
0x18000f325  mov     r8, rsi; lpString2
0x18000f328  call    cs:__imp_CompareStringOrdinal
0x18000f32e  cmp     eax, 2
0x18000f331  jnz     short loc_18000F356
0x18000f333  lea     rcx, [rsi+8]; this
0x18000f337  mov     byte ptr [r14], 1
0x18000f33b  mov     r8, r14; struct StateRepository::Core::Text *
0x18000f33e  mov     rdx, r15; unsigned __int16 *
0x18000f341  call    ?Env@BuiltIn@Evaluators@Macros@StateRepository@@YAJPEBGAEAVText@Core@4@AEA_N@Z; StateRepository::Macros::Evaluators::BuiltIn::Env(ushort const *,StateRepository::Core::Text &,bool &)
0x18000f346  mov     ebx, eax
0x18000f348  test    eax, eax
0x18000f34a  jns     short loc_18000F356
0x18000f34c  mov     edx, 4Dh ; 'M'
0x18000f351  jmp     loc_18000F2CA
0x18000f356  xor     eax, eax
0x18000f358  mov     rcx, [rsp+88h+var_48]
0x18000f35d  xor     rcx, rsp; StackCookie
0x18000f360  call    __security_check_cookie
0x18000f365  add     rsp, 50h
0x18000f369  pop     r15
0x18000f36b  pop     r14
0x18000f36d  pop     r12
0x18000f36f  pop     rdi
0x18000f370  pop     rsi
0x18000f371  pop     rbp
0x18000f372  pop     rbx
0x18000f373  retn
```
