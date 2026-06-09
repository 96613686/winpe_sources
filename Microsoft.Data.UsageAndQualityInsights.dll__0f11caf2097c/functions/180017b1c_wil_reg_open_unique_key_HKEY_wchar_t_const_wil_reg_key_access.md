# wil::reg::open_unique_key(HKEY__ *,wchar_t const *,wil::reg::key_access)

- ea: `0x180017b1c`
- end: `0x180017bda`
- name: `?open_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEB_WW4key_access@12@@Z`
- size: `190`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015930`
- `0x1800485a0`

## callees

- `0x1800079a4`
- `0x180016628`
- `0x180017b1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017b8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017b8a`

## string_xrefs

- `0x180017bb1`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180017bc8`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY *__fastcall wil::reg::open_unique_key(HKEY *a1, __int64 a2, const WCHAR *a3, int a4)
{
  int v5; // r9d
  const char *v6; // r9
  REGSAM v7; // r9d
  int v8; // eax
  bool v9; // sf
  int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  if ( a4 )
  {
    v5 = a4 - 1;
    if ( v5 )
    {
      v6 = (const char *)(unsigned int)(v5 - 1);
      if ( (_DWORD)v6 )
      {
        if ( (_DWORD)v6 != 1 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x77,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
            v6);
        v7 = 983359;
      }
      else
      {
        v7 = 131353;
      }
    }
    else
    {
      v7 = 983103;
    }
  }
  else
  {
    v7 = 131097;
  }
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, v7, a1);
  v9 = v8 < 0;
  if ( v8 > 0 )
  {
    v8 = (unsigned __int16)v8 | 0x80070000;
    v9 = v8 < 0;
  }
  if ( v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v8,
      phkResult);
  return a1;
}

```

## disassembly

```asm
0x180017b1c  mov     [rsp+arg_0], rcx
0x180017b21  push    rbx
0x180017b22  sub     rsp, 40h
0x180017b26  mov     r10, r8
0x180017b29  mov     rbx, rcx
0x180017b2c  mov     [rsp+48h+var_18], 0
0x180017b34  mov     [rsp+48h+var_18], 1
0x180017b3c  mov     qword ptr [rcx], 0
0x180017b43  test    r9d, r9d
0x180017b46  jz      short loc_180017B72
0x180017b48  sub     r9d, 1
0x180017b4c  jz      short loc_180017B6A
0x180017b4e  sub     r9d, 1; char *
0x180017b52  jz      short loc_180017B62
0x180017b54  cmp     r9d, 1
0x180017b58  jnz     short loc_180017BC3
0x180017b5a  mov     r9d, 0F013Fh
0x180017b60  jmp     short loc_180017B78
0x180017b62  mov     r9d, 20119h
0x180017b68  jmp     short loc_180017B78
0x180017b6a  mov     r9d, 0F003Fh
0x180017b70  jmp     short loc_180017B78
0x180017b72  mov     r9d, 20019h; samDesired
0x180017b78  mov     qword ptr [rsp+48h+phkResult], rbx; int
0x180017b7d  xor     r8d, r8d; ulOptions
0x180017b80  mov     rdx, r10; lpSubKey
0x180017b83  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017b8a  call    cs:__imp_RegOpenKeyExW
0x180017b90  test    eax, eax
0x180017b92  jle     short loc_180017B9E
0x180017b94  movzx   eax, ax
0x180017b97  or      eax, 80070000h
0x180017b9c  test    eax, eax
0x180017b9e  js      short loc_180017BA9
0x180017ba0  mov     rax, rbx
0x180017ba3  add     rsp, 40h
0x180017ba7  pop     rbx
0x180017ba8  retn
0x180017ba9  mov     rcx, [rsp+48h]; this
0x180017bae  mov     r9d, eax; char *
0x180017bb1  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017bb8  mov     edx, 1CBEh; void *
0x180017bbd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017bc3  mov     rcx, [rsp+48h]; this
0x180017bc8  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017bcf  mov     edx, 77h ; 'w'; void *
0x180017bd4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
