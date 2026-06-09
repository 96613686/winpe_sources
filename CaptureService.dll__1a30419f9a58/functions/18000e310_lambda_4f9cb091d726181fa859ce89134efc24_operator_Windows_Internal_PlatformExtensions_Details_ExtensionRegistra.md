# _lambda_4f9cb091d726181fa859ce89134efc24_::operator()(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)

- ea: `0x18000e310`
- end: `0x18000e3b1`
- name: `??R_lambda_4f9cb091d726181fa859ce89134efc24_@@QEBA@PEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z`
- size: `161`
- prototype: `__int64 __fastcall(__int64 **, __int64, char, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000e450`

## callees

- `0x18000907c`
- `0x18000c04c`
- `0x18000e310`
- `0x180022010`

## string_xrefs

- `0x18000e34e`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall _lambda_4f9cb091d726181fa859ce89134efc24_::operator()(__int64 **a1, __int64 a2, char a3, char *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  char v10; // al
  __int64 *v11; // rcx
  char v12; // bl
  char v13; // cl
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v16; // [rsp+60h] [rbp+18h] BYREF

  v16 = a3;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a2 + 32LL))(a2, **a1, *a1[1]);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
    v11 = *a1;
    v12 = v10;
    v16 = v10;
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::EvaluatingRegistration<unsigned short * &,bool &>(
      v11,
      &v16);
    if ( v12 )
    {
      v13 = 0;
      *(_BYTE *)a1[3] = 1;
    }
    else
    {
      v13 = 1;
      ++*(_DWORD *)a1[4];
    }
    *a4 = v13;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v7,
      v14);
    return v8;
  }
}

```

## disassembly

```asm
0x18000e310  mov     [rsp+arg_10], r8b
0x18000e315  push    rbx
0x18000e316  push    rsi
0x18000e317  push    rdi
0x18000e318  push    r14
0x18000e31a  sub     rsp, 28h
0x18000e31e  mov     rax, [rdx]
0x18000e321  mov     rsi, rdx
0x18000e324  mov     rdx, [rcx]
0x18000e327  mov     rdi, rcx
0x18000e32a  mov     r8, [rcx+8]
0x18000e32e  mov     r14, r9
0x18000e331  mov     rcx, rsi
0x18000e334  mov     rax, [rax+20h]
0x18000e338  mov     rdx, [rdx]
0x18000e33b  mov     r8, [r8]
0x18000e33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e343  mov     ebx, eax
0x18000e345  test    eax, eax
0x18000e347  jns     short loc_18000E366
0x18000e349  mov     rcx, [rsp+48h]; this
0x18000e34e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000e355  mov     r9d, eax; char *
0x18000e358  mov     edx, 1B7h; void *
0x18000e35d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e362  mov     eax, ebx
0x18000e364  jmp     short loc_18000E3A7
0x18000e366  mov     rax, [rsi]
0x18000e369  mov     rcx, rsi
0x18000e36c  mov     rax, [rax+10h]
0x18000e370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e375  mov     rcx, [rdi]
0x18000e378  lea     rdx, [rsp+48h+arg_10]
0x18000e37d  mov     bl, al
0x18000e37f  mov     [rsp+48h+arg_10], al
0x18000e383  call    ??$EvaluatingRegistration@AEAPEAGAEA_N@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAXAEAPEAGAEA_N@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::EvaluatingRegistration<ushort * &,bool &>(ushort * &,bool &)
0x18000e388  test    bl, bl
0x18000e38a  jz      short loc_18000E397
0x18000e38c  mov     rax, [rdi+18h]
0x18000e390  xor     cl, cl
0x18000e392  mov     byte ptr [rax], 1
0x18000e395  jmp     short loc_18000E3A2
0x18000e397  mov     rax, [rdi+20h]
0x18000e39b  mov     ecx, 1
0x18000e3a0  add     [rax], ecx
0x18000e3a2  mov     [r14], cl
0x18000e3a5  xor     eax, eax
0x18000e3a7  add     rsp, 28h
0x18000e3ab  pop     r14
0x18000e3ad  pop     rdi
0x18000e3ae  pop     rsi
0x18000e3af  pop     rbx
0x18000e3b0  retn
```
