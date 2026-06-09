# NLG::LanguageIdServices::FindStandardProofDir(ushort *,int)

- ea: `0x1800494d8`
- end: `0x180049523`
- name: `?FindStandardProofDir@LanguageIdServices@NLG@@SAJPEAGH@Z`
- size: `75`
- prototype: `int __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004952c`

## callees

- `0x180017858`
- `0x1800494d8`

## import_xrefs

- `msvcrt!_wgetenv` at `0x1800494e8`
- `msvcrt!_wgetenv` at `0x1800494e8`

## string_xrefs

- `0x1800494e1`: `CommonProgramFiles`

## pseudocode

```c
int __fastcall NLG::LanguageIdServices::FindStandardProofDir(unsigned __int16 *a1)
{
  wchar_t *v2; // rax

  v2 = _wgetenv(L"CommonProgramFiles");
  if ( v2 )
    return StringCchPrintfW(a1, 0x105u, L"%s%s", v2, L"\\Microsoft Shared\\Proof\\");
  else
    return -2147467259;
}

```

## disassembly

```asm
0x1800494d8  push    rbx
0x1800494da  sub     rsp, 30h
0x1800494de  mov     rbx, rcx
0x1800494e1  lea     rcx, aCommonprogramf; "CommonProgramFiles"
0x1800494e8  call    cs:__imp__wgetenv
0x1800494ee  test    rax, rax
0x1800494f1  jz      short loc_180049518
0x1800494f3  lea     rcx, aMicrosoftShare; "\\Microsoft Shared\\Proof\\"
0x1800494fa  mov     r9, rax
0x1800494fd  mov     [rsp+38h+var_18], rcx
0x180049502  lea     r8, aSS; "%s%s"
0x180049509  mov     rcx, rbx; unsigned __int16 *
0x18004950c  mov     edx, 105h; unsigned __int64
0x180049511  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180049516  jmp     short loc_18004951D
0x180049518  mov     eax, 80004005h
0x18004951d  add     rsp, 30h
0x180049521  pop     rbx
0x180049522  retn
```
