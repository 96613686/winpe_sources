# CONFIG_SEARCH_OBJECT::SerializeText(ushort *,ulong)

- ea: `0x18001e020`
- end: `0x18001e0ef`
- name: `?SerializeText@CONFIG_SEARCH_OBJECT@@UEAAJPEAGK@Z`
- size: `207`
- prototype: `int(CONFIG_SEARCH_OBJECT *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000d654`
- `0x18001e020`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001e091`
- `msvcrt!_wcsicmp` at `0x18001e091`

## string_xrefs

- `0x18001e097`: `CONFIGSEARCH`
- `0x18001e039`: `CONFIGSEARCH.PATH`

## pseudocode

```c
__int64 __fastcall CONFIG_SEARCH_OBJECT::SerializeText(
        CONFIG_SEARCH_OBJECT *this,
        unsigned __int16 *a2,
        unsigned int a3)
{
  __int64 v3; // rax
  __int64 result; // rax
  wchar_t *String1; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+58h] [rbp+20h] BYREF

  v3 = *(_QWORD *)this;
  v9 = 0;
  String1 = 0;
  result = (*(__int64 (__fastcall **)(CONFIG_SEARCH_OBJECT *, const unsigned __int16 *, __int64 *))(v3 + 80))(
             this,
             L"CONFIGSEARCH.PATH",
             &v9);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(CONFIG_SEARCH_OBJECT *, const unsigned __int16 *, wchar_t **))(*(_QWORD *)this + 80LL))(
               this,
               L"status",
               &String1);
    if ( (int)result >= 0 )
    {
      if ( _wcsicmp(String1, L"0") )
        return StringCchPrintfW(a2, a3, L"%ws \"%ws\" (FAILED:%ws)", L"CONFIGSEARCH", v9, String1);
      else
        return StringCchPrintfW(a2, a3, L"%ws \"%ws\"", L"CONFIGSEARCH", v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001e020  mov     r11, rsp
0x18001e023  mov     [r11+10h], rbx
0x18001e027  mov     [r11+18h], rsi
0x18001e02b  push    rdi
0x18001e02c  sub     rsp, 30h
0x18001e030  mov     rax, [rcx]
0x18001e033  mov     rdi, rdx
0x18001e036  mov     esi, r8d
0x18001e039  lea     rdx, aConfigsearchPa; "CONFIGSEARCH.PATH"
0x18001e040  lea     r8, [r11+20h]
0x18001e044  mov     qword ptr [r11+20h], 0
0x18001e04c  mov     rbx, rcx
0x18001e04f  mov     qword ptr [r11+8], 0
0x18001e057  mov     rax, [rax+50h]
0x18001e05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e060  test    eax, eax
0x18001e062  js      short loc_18001E0DF
0x18001e064  mov     rax, [rbx]
0x18001e067  lea     r8, [rsp+38h+String1]
0x18001e06c  lea     rdx, aStatus; "status"
0x18001e073  mov     rcx, rbx
0x18001e076  mov     rax, [rax+50h]
0x18001e07a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e07f  test    eax, eax
0x18001e081  js      short loc_18001E0DF
0x18001e083  mov     rcx, [rsp+38h+String1]; String1
0x18001e088  lea     rdx, a0; "0"
0x18001e08f  mov     ebx, esi
0x18001e091  call    cs:__imp__wcsicmp
0x18001e097  lea     r9, aConfigsearch; "CONFIGSEARCH"
0x18001e09e  mov     edx, ebx; unsigned __int64
0x18001e0a0  mov     rcx, rdi; unsigned __int16 *
0x18001e0a3  test    eax, eax
0x18001e0a5  jnz     short loc_18001E0BF
0x18001e0a7  mov     rax, [rsp+38h+arg_18]
0x18001e0ac  lea     r8, aWsWs; "%ws \"%ws\""
0x18001e0b3  mov     [rsp+38h+var_18], rax
0x18001e0b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e0bd  jmp     short loc_18001E0DF
0x18001e0bf  mov     rax, [rsp+38h+String1]
0x18001e0c4  lea     r8, aWsWsFailedWs; "%ws \"%ws\" (FAILED:%ws)"
0x18001e0cb  mov     [rsp+38h+var_10], rax
0x18001e0d0  mov     rax, [rsp+38h+arg_18]
0x18001e0d5  mov     [rsp+38h+var_18], rax
0x18001e0da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e0df  mov     rbx, [rsp+38h+arg_8]
0x18001e0e4  mov     rsi, [rsp+38h+arg_10]
0x18001e0e9  add     rsp, 30h
0x18001e0ed  pop     rdi
0x18001e0ee  retn
```
