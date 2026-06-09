# RtlTrimNtPathSegment

- ea: `0x180024598`
- end: `0x180024652`
- name: `RtlTrimNtPathSegment`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x180023c40`

## callees

- `0x18000f7cc`
- `0x18000fafc`
- `0x180024598`

## string_xrefs

- `0x1800245b6`: `onecore\base\lstring\path.cpp`
- `0x1800245d2`: `RtlTrimNtPathSegment`

## pseudocode

```c
__int64 __fastcall RtlTrimNtPathSegment(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v4; // rcx
  __int64 v5; // r8
  _QWORD *v6; // r11
  __int64 result; // rax
  __int16 *v8; // r10
  __int64 v9; // r9
  __int16 *v10; // rdx
  __int16 *v11; // rcx
  __int16 v12; // ax
  _QWORD v13[5]; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  *a3 = 0;
  if ( (unsigned __int8)RtlIsLUnicodeStringValid() )
  {
    v8 = (__int16 *)v4[2];
    v9 = v5;
    v10 = v8;
    v11 = (__int16 *)((char *)v8 + *v4);
    if ( v8 < v11 )
    {
      do
      {
        v12 = *v10++;
        if ( v12 != 92 )
          break;
        v9 += 2;
      }
      while ( v10 < v11 );
      if ( v10 < v11 )
      {
        do
        {
          if ( *--v11 != 92 )
            break;
          v5 += 2;
        }
        while ( v11 > v8 );
      }
    }
    *v6 = v9;
    result = 0;
    *a3 = v5;
  }
  else
  {
    v13[2] = 548;
    v13[0] = "onecore\\base\\lstring\\path.cpp";
    v13[1] = "RtlTrimNtPathSegment";
    v13[3] = "RtlIsLUnicodeStringValid(Segment)";
    RtlReportErrorOrigination(v13, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  return result;
}

```

## disassembly

```asm
0x180024598  push    rbx
0x18002459a  sub     rsp, 40h
0x18002459e  mov     rbx, r8
0x1800245a1  mov     r11, rdx
0x1800245a4  xor     r8d, r8d
0x1800245a7  mov     [rdx], r8
0x1800245aa  mov     [rbx], r8
0x1800245ad  call    RtlIsLUnicodeStringValid
0x1800245b2  test    al, al
0x1800245b4  jnz     short loc_180024601
0x1800245b6  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800245bd  mov     [rsp+48h+var_18], 224h
0x1800245c6  mov     [rsp+48h+var_28], rax
0x1800245cb  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800245d2  lea     rax, aRtltrimntpaths; "RtlTrimNtPathSegment"
0x1800245d9  mov     r8d, 0C000000Dh
0x1800245df  mov     [rsp+48h+var_20], rax
0x1800245e4  lea     rcx, [rsp+48h+var_28]
0x1800245e9  lea     rax, aRtlislunicodes; "RtlIsLUnicodeStringValid(Segment)"
0x1800245f0  mov     [rsp+48h+var_10], rax
0x1800245f5  call    RtlReportErrorOrigination
0x1800245fa  mov     eax, 0C000000Dh
0x1800245ff  jmp     short loc_18002464C
0x180024601  mov     r10, [rcx+10h]
0x180024605  mov     r9, r8
0x180024608  mov     rcx, [rcx]
0x18002460b  mov     rdx, r10
0x18002460e  add     rcx, r10
0x180024611  cmp     r10, rcx
0x180024614  jnb     short loc_180024644
0x180024616  movzx   eax, word ptr [rdx]
0x180024619  add     rdx, 2
0x18002461d  cmp     ax, 5Ch ; '\'
0x180024621  jnz     short loc_18002462C
0x180024623  add     r9, 2
0x180024627  cmp     rdx, rcx
0x18002462a  jb      short loc_180024616
0x18002462c  cmp     rdx, rcx
0x18002462f  jnb     short loc_180024644
0x180024631  sub     rcx, 2
0x180024635  cmp     word ptr [rcx], 5Ch ; '\'
0x180024639  jnz     short loc_180024644
0x18002463b  add     r8, 2
0x18002463f  cmp     rcx, r10
0x180024642  ja      short loc_180024631
0x180024644  mov     [r11], r9
0x180024647  xor     eax, eax
0x180024649  mov     [rbx], r8
0x18002464c  add     rsp, 40h
0x180024650  pop     rbx
0x180024651  retn
```
