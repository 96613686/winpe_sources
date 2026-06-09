# wil::reg::set_value<unsigned __int64>(HKEY__ *,wchar_t const *,unsigned __int64 const &)

- ea: `0x180012940`
- end: `0x180012991`
- name: `??$set_value@_K@reg@wil@@YAXPEAUHKEY__@@PEB_WAEB_K@Z`
- size: `81`
- prototype: `int __fastcall(HKEY, const WCHAR *, const void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180015930`
- `0x180023530`

## callees

- `0x180012940`
- `0x180016628`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001295c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001295c`

## string_xrefs

- `0x18001297c`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
int __fastcall wil::reg::set_value<unsigned __int64>(HKEY a1, const WCHAR *a2, const void *a3)
{
  int result; // eax
  bool v4; // sf
  int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  result = RegSetKeyValueW(a1, 0, a2, 0xBu, a3, 8u);
  v4 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v4 = result < 0;
  }
  if ( v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)result,
      lpData);
  return result;
}

```

## disassembly

```asm
0x180012940  sub     rsp, 38h
0x180012944  mov     [rsp+38h+cbData], 8; cbData
0x18001294c  mov     r9d, 0Bh; dwType
0x180012952  mov     [rsp+38h+lpData], r8; int
0x180012957  mov     r8, rdx; lpValueName
0x18001295a  xor     edx, edx; lpSubKey
0x18001295c  call    cs:__imp_RegSetKeyValueW
0x180012962  test    eax, eax
0x180012964  jle     short loc_180012970
0x180012966  movzx   eax, ax
0x180012969  or      eax, 80070000h
0x18001296e  test    eax, eax
0x180012970  js      short loc_180012977
0x180012972  add     rsp, 38h
0x180012976  retn
0x180012977  mov     rcx, [rsp+38h]; this
0x18001297c  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012983  mov     r9d, eax; char *
0x180012986  mov     edx, 1CBEh; void *
0x18001298b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
