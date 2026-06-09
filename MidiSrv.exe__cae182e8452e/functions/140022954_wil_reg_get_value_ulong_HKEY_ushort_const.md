# wil::reg::get_value<ulong>(HKEY__ *,ushort const *)

- ea: `0x140022954`
- end: `0x1400229cf`
- name: `??$get_value@K@reg@wil@@YAKPEAUHKEY__@@PEBG@Z`
- size: `123`
- prototype: `__int64 __fastcall(HKEY, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400238a4`

## callees

- `0x140022954`
- `0x1400261b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140022996`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140022996`

## string_xrefs

- `0x1400229ba`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::reg::get_value<unsigned long>(HKEY a1, __int64 a2)
{
  int ValueW; // eax
  bool v3; // sf
  int v5; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD v7; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v8; // [rsp+58h] [rbp+10h] BYREF
  int v9; // [rsp+5Ch] [rbp+14h]

  v9 = HIDWORD(a2);
  v8 = 0;
  v7 = 4;
  ValueW = RegGetValueW(a1, 0, L"Enabled", 0x10u, 0, &v8, &v7);
  v3 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    v3 = ValueW < 0;
  }
  if ( v3 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)ValueW,
      v5);
  return v8;
}

```

## disassembly

```asm
0x140022954  mov     r11, rsp
0x140022957  mov     [r11+10h], rdx
0x14002295b  sub     rsp, 48h
0x14002295f  lea     rax, [r11+8]
0x140022963  mov     [rsp+48h+arg_8], 0
0x14002296b  mov     [r11-18h], rax
0x14002296f  lea     r8, Value; "Enabled"
0x140022976  lea     rax, [r11+10h]
0x14002297a  mov     [rsp+48h+arg_0], 4
0x140022982  mov     [r11-20h], rax
0x140022986  mov     r9d, 10h; dwFlags
0x14002298c  xor     edx, edx; lpSubKey
0x14002298e  mov     qword ptr [r11-28h], 0
0x140022996  call    cs:__imp_RegGetValueW
0x14002299c  test    eax, eax
0x14002299e  jle     short loc_1400229AA
0x1400229a0  movzx   eax, ax
0x1400229a3  or      eax, 80070000h
0x1400229a8  test    eax, eax
0x1400229aa  js      short loc_1400229B5
0x1400229ac  mov     eax, [rsp+48h+arg_8]
0x1400229b0  add     rsp, 48h
0x1400229b4  retn
0x1400229b5  mov     rcx, [rsp+48h]; this
0x1400229ba  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400229c1  mov     r9d, eax; char *
0x1400229c4  mov     edx, 1CBEh; void *
0x1400229c9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
