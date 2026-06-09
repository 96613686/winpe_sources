# _lambda_4f9cb091d726181fa859ce89134efc24_::operator()(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)

- ea: `0x140009c54`
- end: `0x140009cf5`
- name: `??R_lambda_4f9cb091d726181fa859ce89134efc24_@@QEBA@PEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z`
- size: `161`
- prototype: `__int64 __fastcall(__int64 **, __int64, char, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140009ed0`

## callees

- `0x140005310`
- `0x140009c54`
- `0x1400136fc`
- `0x14001f010`

## string_xrefs

- `0x140009c92`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

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
0x140009c54  mov     [rsp+arg_10], r8b
0x140009c59  push    rbx
0x140009c5a  push    rsi
0x140009c5b  push    rdi
0x140009c5c  push    r14
0x140009c5e  sub     rsp, 28h
0x140009c62  mov     rax, [rdx]
0x140009c65  mov     rsi, rdx
0x140009c68  mov     rdx, [rcx]
0x140009c6b  mov     rdi, rcx
0x140009c6e  mov     r8, [rcx+8]
0x140009c72  mov     r14, r9
0x140009c75  mov     rcx, rsi
0x140009c78  mov     rax, [rax+20h]
0x140009c7c  mov     rdx, [rdx]
0x140009c7f  mov     r8, [r8]
0x140009c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c87  mov     ebx, eax
0x140009c89  test    eax, eax
0x140009c8b  jns     short loc_140009CAA
0x140009c8d  mov     rcx, [rsp+48h]; this
0x140009c92  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x140009c99  mov     r9d, eax; char *
0x140009c9c  mov     edx, 1B7h; void *
0x140009ca1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009ca6  mov     eax, ebx
0x140009ca8  jmp     short loc_140009CEB
0x140009caa  mov     rax, [rsi]
0x140009cad  mov     rcx, rsi
0x140009cb0  mov     rax, [rax+10h]
0x140009cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009cb9  mov     rcx, [rdi]
0x140009cbc  lea     rdx, [rsp+48h+arg_10]
0x140009cc1  mov     bl, al
0x140009cc3  mov     [rsp+48h+arg_10], al
0x140009cc7  call    ??$EvaluatingRegistration@AEAPEAGAEA_N@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAXAEAPEAGAEA_N@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::EvaluatingRegistration<ushort * &,bool &>(ushort * &,bool &)
0x140009ccc  test    bl, bl
0x140009cce  jz      short loc_140009CDB
0x140009cd0  mov     rax, [rdi+18h]
0x140009cd4  xor     cl, cl
0x140009cd6  mov     byte ptr [rax], 1
0x140009cd9  jmp     short loc_140009CE6
0x140009cdb  mov     rax, [rdi+20h]
0x140009cdf  mov     ecx, 1
0x140009ce4  add     [rax], ecx
0x140009ce6  mov     [r14], cl
0x140009ce9  xor     eax, eax
0x140009ceb  add     rsp, 28h
0x140009cef  pop     r14
0x140009cf1  pop     rdi
0x140009cf2  pop     rsi
0x140009cf3  pop     rbx
0x140009cf4  retn
```
