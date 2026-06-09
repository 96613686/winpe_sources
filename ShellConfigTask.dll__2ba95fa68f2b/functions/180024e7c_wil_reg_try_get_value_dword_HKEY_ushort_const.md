# wil::reg::try_get_value_dword(HKEY__ *,ushort const *)

- ea: `0x180024e7c`
- end: `0x180024f1f`
- name: `?try_get_value_dword@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG@Z`
- size: `163`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001a570`
- `0x18001cea8`
- `0x18001fd50`
- `0x18002b864`

## callees

- `0x18002065c`
- `0x180024e7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024ec0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024ec0`

## string_xrefs

- `0x180024f0d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall wil::reg::try_get_value_dword(__int64 a1, HKEY a2, const WCHAR *a3)
{
  LSTATUS ValueW; // eax
  unsigned __int64 v5; // r9
  char v6; // cl
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v10; // [rsp+58h] [rbp+10h] BYREF
  DWORD v11; // [rsp+68h] [rbp+20h] BYREF

  v10 = 0;
  v11 = 4;
  ValueW = RegGetValueW(a2, 0, a3, 0x10u, 0, &v10, &v11);
  v5 = (unsigned int)ValueW;
  if ( ValueW > 0 )
    v5 = (unsigned __int16)ValueW | 0x80070000;
  v6 = 1;
  if ( (v5 & 0x80000000) != 0LL )
  {
    if ( (unsigned int)(v5 + 2147024894) > 1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)v5,
        v8);
    v6 = 0;
  }
  else
  {
    *(_DWORD *)a1 = v10;
  }
  result = a1;
  *(_BYTE *)(a1 + 4) = v6;
  return result;
}

```

## disassembly

```asm
0x180024e7c  mov     r11, rsp
0x180024e7f  mov     [r11+8], rbx
0x180024e83  push    rdi
0x180024e84  sub     rsp, 40h
0x180024e88  mov     rbx, rcx
0x180024e8b  mov     [rsp+48h+arg_8], 0
0x180024e93  lea     rcx, [r11+20h]
0x180024e97  mov     rax, rdx
0x180024e9a  mov     [r11-18h], rcx
0x180024e9e  mov     edi, 4
0x180024ea3  lea     rcx, [r11+10h]
0x180024ea7  mov     [rsp+48h+arg_18], edi
0x180024eab  mov     [r11-20h], rcx
0x180024eaf  xor     edx, edx; lpSubKey
0x180024eb1  mov     rcx, rax; hkey
0x180024eb4  mov     qword ptr [r11-28h], 0
0x180024ebc  lea     r9d, [rdi+0Ch]; dwFlags
0x180024ec0  call    cs:__imp_RegGetValueW
0x180024ec6  mov     r9d, eax
0x180024ec9  test    eax, eax
0x180024ecb  jle     short loc_180024ED8
0x180024ecd  movzx   r9d, ax
0x180024ed1  or      r9d, 80070000h; char *
0x180024ed8  mov     ecx, 1
0x180024edd  test    r9d, r9d
0x180024ee0  js      short loc_180024EEA
0x180024ee2  mov     eax, [rsp+48h+arg_8]
0x180024ee6  mov     [rbx], eax
0x180024ee8  jmp     short loc_180024EF7
0x180024eea  lea     eax, [r9+7FF8FFFEh]
0x180024ef1  cmp     eax, ecx
0x180024ef3  ja      short loc_180024F08
0x180024ef5  xor     cl, cl
0x180024ef7  mov     rax, rbx
0x180024efa  mov     [rbx+rdi], cl
0x180024efd  mov     rbx, [rsp+48h+arg_0]
0x180024f02  add     rsp, 40h
0x180024f06  pop     rdi
0x180024f07  retn
0x180024f08  mov     rcx, [rsp+48h]; this
0x180024f0d  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024f14  mov     edx, 1CBEh; void *
0x180024f19  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
