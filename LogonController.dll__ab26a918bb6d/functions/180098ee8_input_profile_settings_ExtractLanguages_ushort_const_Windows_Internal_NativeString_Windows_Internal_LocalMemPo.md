# input_profile_settings::ExtractLanguages(ushort const *,Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> &)

- ea: `0x180098ee8`
- end: `0x180099047`
- name: `?ExtractLanguages@input_profile_settings@@YA_NPEBGAEAV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(input_profile_settings *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config`

## callers

- `0x1800962b0`

## callees

- `0x180095e98`
- `0x180098ee8`
- `0x180099b44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180098f27`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18009900a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180098f27`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18009900a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098fad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098ffe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098fad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098ffe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180098f91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180098f91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180098fbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180098fbe`
- `Bcp47Langs!Bcp47FromLcid` at `0x180098f6d`
- `Bcp47Langs!Bcp47FromLcid` at `0x180098f6d`
- `Bcp47Langs!Bcp47Normalize` at `0x180098fa3`
- `Bcp47Langs!Bcp47Normalize` at `0x180098fa3`

## pseudocode

```c
char __fastcall input_profile_settings::ExtractLanguages(wchar_t *this, _QWORD *a2)
{
  wchar_t *v3; // rbx
  char v4; // si
  wchar_t *v5; // rdi
  unsigned int *v6; // r9
  PCWSTR StringRawBuffer; // rax
  __int64 v8; // r8
  wchar_t *v9; // rax
  HSTRING string; // [rsp+60h] [rbp+40h] BYREF
  unsigned int v12; // [rsp+68h] [rbp+48h] BYREF
  int v13; // [rsp+70h] [rbp+50h] BYREF
  HSTRING v14; // [rsp+78h] [rbp+58h] BYREF

  v3 = this;
  v4 = 1;
  if ( this )
  {
    while ( 1 )
    {
      if ( !*v3 )
        goto LABEL_20;
      v5 = wcschr(v3, 0x3Au);
      if ( !v5 )
        goto LABEL_20;
      v14 = 0;
      LODWORD(string) = 0;
      v12 = 0;
      if ( input_profile_settings::HexStringToUint(
             (input_profile_settings *)v3,
             (const unsigned __int16 *)&string,
             &v12,
             v6)
        && &v3[(unsigned int)string] == v5 )
      {
        break;
      }
      if ( v5 != v3 )
      {
        string = 0;
        if ( WindowsCreateString(v3, v5 - v3, &string) >= 0 )
        {
          Bcp47Normalize(string, &v14);
          WindowsDeleteString(string);
        }
        goto LABEL_10;
      }
LABEL_17:
      v9 = wcschr(v3, 0x3Bu);
      v3 = v9 + 1;
      if ( !v9 )
        v3 = 0;
      if ( !v3 )
        goto LABEL_20;
    }
    Bcp47FromLcid((unsigned __int16)v12, &v14);
LABEL_10:
    if ( v14 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v14, 0);
      if ( StringRawBuffer )
      {
        v8 = -1;
        do
          ++v8;
        while ( StringRawBuffer[v8] );
      }
      else
      {
        v8 = 0;
      }
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Concat(
        a2,
        StringRawBuffer,
        v8);
      v13 = 59;
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Concat(a2, &v13, 1);
      WindowsDeleteString(v14);
    }
    goto LABEL_17;
  }
LABEL_20:
  if ( !*a2 || !*(_WORD *)*a2 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x180098ee8  push    rbp
0x180098eea  push    rbx
0x180098eeb  push    rsi
0x180098eec  push    rdi
0x180098eed  push    r12
0x180098eef  push    r14
0x180098ef1  push    r15
0x180098ef3  mov     rbp, rsp
0x180098ef6  sub     rsp, 20h
0x180098efa  xor     r15d, r15d
0x180098efd  mov     r14, rdx
0x180098f00  mov     rbx, rcx
0x180098f03  mov     esi, 1
0x180098f08  test    rcx, rcx
0x180098f0b  jz      loc_180099024
0x180098f11  lea     r12d, [rsi+3Ah]
0x180098f15  cmp     [rbx], r15w
0x180098f19  jz      loc_180099024
0x180098f1f  mov     edx, 3Ah ; ':'; Ch
0x180098f24  mov     rcx, rbx; Str
0x180098f27  call    cs:__imp_wcschr
0x180098f2d  mov     rdi, rax
0x180098f30  test    rax, rax
0x180098f33  jz      loc_180099024
0x180098f39  lea     r8, [rbp+arg_8]; unsigned int *
0x180098f3d  mov     [rbp+arg_18], r15
0x180098f41  lea     rdx, [rbp+string]; unsigned __int16 *
0x180098f45  mov     dword ptr [rbp+string], r15d
0x180098f49  mov     rcx, rbx; this
0x180098f4c  mov     [rbp+arg_8], r15d
0x180098f50  call    ?HexStringToUint@input_profile_settings@@YA_NPEBGPEAI1@Z; input_profile_settings::HexStringToUint(ushort const *,uint *,uint *)
0x180098f55  test    al, al
0x180098f57  jz      short loc_180098F75
0x180098f59  mov     eax, dword ptr [rbp+string]
0x180098f5c  lea     rcx, [rbx+rax*2]
0x180098f60  cmp     rcx, rdi
0x180098f63  jnz     short loc_180098F75
0x180098f65  movzx   ecx, word ptr [rbp+arg_8]
0x180098f69  lea     rdx, [rbp+arg_18]
0x180098f6d  call    cs:__imp_Bcp47FromLcid
0x180098f73  jmp     short loc_180098FB3
0x180098f75  cmp     rdi, rbx
0x180098f78  jz      loc_180099004
0x180098f7e  sub     rdi, rbx
0x180098f81  mov     [rbp+string], r15
0x180098f85  sar     rdi, 1
0x180098f88  lea     r8, [rbp+string]; string
0x180098f8c  mov     edx, edi; length
0x180098f8e  mov     rcx, rbx; sourceString
0x180098f91  call    cs:__imp_WindowsCreateString
0x180098f97  test    eax, eax
0x180098f99  js      short loc_180098FB3
0x180098f9b  mov     rcx, [rbp+string]
0x180098f9f  lea     rdx, [rbp+arg_18]
0x180098fa3  call    cs:__imp_Bcp47Normalize
0x180098fa9  mov     rcx, [rbp+string]; string
0x180098fad  call    cs:__imp_WindowsDeleteString
0x180098fb3  mov     rcx, [rbp+arg_18]; string
0x180098fb7  test    rcx, rcx
0x180098fba  jz      short loc_180099004
0x180098fbc  xor     edx, edx; length
0x180098fbe  call    cs:__imp_WindowsGetStringRawBuffer
0x180098fc4  test    rax, rax
0x180098fc7  jz      short loc_180098FD9
0x180098fc9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180098fcd  inc     r8
0x180098fd0  cmp     [rax+r8*2], r15w
0x180098fd5  jnz     short loc_180098FCD
0x180098fd7  jmp     short loc_180098FDC
0x180098fd9  mov     r8, r15
0x180098fdc  mov     rdx, rax
0x180098fdf  mov     rcx, r14
0x180098fe2  call    ?_Concat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180098fe7  mov     r8, rsi
0x180098fea  mov     [rbp+arg_10], r12d
0x180098fee  lea     rdx, [rbp+arg_10]
0x180098ff2  mov     rcx, r14
0x180098ff5  call    ?_Concat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180098ffa  mov     rcx, [rbp+arg_18]; string
0x180098ffe  call    cs:__imp_WindowsDeleteString
0x180099004  mov     edx, r12d; Ch
0x180099007  mov     rcx, rbx; Str
0x18009900a  call    cs:__imp_wcschr
0x180099010  test    rax, rax
0x180099013  lea     rbx, [rax+2]
0x180099017  cmovz   rbx, rax
0x18009901b  test    rbx, rbx
0x18009901e  jnz     loc_180098F15
0x180099024  mov     rax, [r14]
0x180099027  test    rax, rax
0x18009902a  jz      short loc_180099032
0x18009902c  cmp     [rax], r15w
0x180099030  jnz     short loc_180099035
0x180099032  mov     sil, r15b
0x180099035  mov     al, sil
0x180099038  add     rsp, 20h
0x18009903c  pop     r15
0x18009903e  pop     r14
0x180099040  pop     r12
0x180099042  pop     rdi
0x180099043  pop     rsi
0x180099044  pop     rbx
0x180099045  pop     rbp
0x180099046  retn
```
