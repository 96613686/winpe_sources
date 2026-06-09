# SystemSettings::PenSettings::IsOemAumidAlreadyDisplayed(ushort const *)

- ea: `0x180054394`
- end: `0x1800543eb`
- name: `?IsOemAumidAlreadyDisplayed@PenSettings@SystemSettings@@YA_NPEBG@Z`
- size: `87`
- prototype: `bool __fastcall(LPCWCH lpString1, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027350`
- `0x180028910`
- `0x18002faf0`

## callees

- `0x180054394`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800543c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800543c9`

## pseudocode

```c
char __fastcall SystemSettings::PenSettings::IsOemAumidAlreadyDisplayed(LPCWCH lpString1, const unsigned __int16 *a2)
{
  LPCWCH *i; // rbx

  for ( i = (LPCWCH *)off_180063C90; i != (LPCWCH *)&qword_180063CA8; ++i )
  {
    if ( CompareStringOrdinal(lpString1, -1, *i, -1, 1) == 2 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180054394  mov     [rsp+arg_0], rbx
0x180054399  push    rdi
0x18005439a  sub     rsp, 30h
0x18005439e  mov     rdi, rcx
0x1800543a1  lea     rbx, off_180063C90; "Microsoft.Whiteboard_8wekyb3d8bbwe!Whit"...
0x1800543a8  lea     rax, qword_180063CA8
0x1800543af  cmp     rbx, rax
0x1800543b2  jz      short loc_1800543DE
0x1800543b4  mov     r8, [rbx]; lpString2
0x1800543b7  or      r9d, 0FFFFFFFFh; cchCount2
0x1800543bb  or      edx, r9d; cchCount1
0x1800543be  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800543c6  mov     rcx, rdi; lpString1
0x1800543c9  call    cs:__imp_CompareStringOrdinal
0x1800543cf  cmp     eax, 2
0x1800543d2  jz      short loc_1800543DA
0x1800543d4  add     rbx, 8
0x1800543d8  jmp     short loc_1800543A8
0x1800543da  xor     al, al
0x1800543dc  jmp     short loc_1800543E0
0x1800543de  mov     al, 1
0x1800543e0  mov     rbx, [rsp+38h+arg_0]
0x1800543e5  add     rsp, 30h
0x1800543e9  pop     rdi
0x1800543ea  retn
```
