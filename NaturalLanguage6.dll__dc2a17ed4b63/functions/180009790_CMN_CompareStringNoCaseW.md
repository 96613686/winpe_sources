# CMN_CompareStringNoCaseW

- ea: `0x180009790`
- end: `0x180009888`
- name: `CMN_CompareStringNoCaseW`
- size: `248`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800154a0`
- `0x180038660`
- `0x180038a4c`
- `0x18003b8d0`
- `0x1800420dc`
- `0x180050310`
- `0x180050c40`
- `0x180057d00`
- `0x180058050`
- `0x1800581c0`
- `0x180058330`
- `0x18005e510`

## callees

- `0x180009790`
- `0x18000a550`
- `0x18000a740`

## pseudocode

```c
__int64 __fastcall CMN_CompareStringNoCaseW(unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned __int16 v4; // bx
  unsigned __int16 v5; // di
  unsigned __int16 v6; // bx
  unsigned __int16 v7; // cx
  __int64 result; // rax

  while ( 1 )
  {
    v4 = *a1;
    if ( (*a1 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v4) & 0x100000) == 0 )
        goto LABEL_3;
      v5 = ConvertCaseHighUnicode(v4, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v4) & 1) == 0
           || (v5 = v4 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v4 + 32)) & 2) == 0) )
    {
LABEL_3:
      v5 = v4;
    }
    v6 = *a2;
    if ( (*a2 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v6) & 0x100000) == 0 )
        goto LABEL_6;
      v7 = ConvertCaseHighUnicode(v6, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v6) & 1) == 0
           || (v7 = v6 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v6 + 32)) & 2) == 0) )
    {
LABEL_6:
      v7 = v6;
    }
    if ( v5 != v7 )
      break;
    ++a1;
    ++a2;
    if ( !v5 )
      return 0;
  }
  result = 1;
  if ( v5 <= v7 )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x180009790  push    rbx
0x180009792  push    rbp
0x180009793  push    rsi
0x180009794  push    rdi
0x180009795  push    r12
0x180009797  push    r14
0x180009799  push    r15
0x18000979b  sub     rsp, 20h
0x18000979f  mov     r14, rdx
0x1800097a2  lea     rbp, k_rgbLexTab1
0x1800097a9  mov     rsi, rcx
0x1800097ac  mov     r15d, 0FF00h
0x1800097b2  mov     r12d, 0FFFFFFFFh
0x1800097b8  nop     dword ptr [rax+rax+00000000h]
0x1800097c0  movzx   ebx, word ptr [rsi]
0x1800097c3  test    r15w, bx
0x1800097c7  jnz     short loc_18000982F
0x1800097c9  movzx   eax, bl
0x1800097cc  test    byte ptr [rax+rbp], 1
0x1800097d0  jnz     short loc_180009812
0x1800097d2  movzx   edi, bx
0x1800097d5  movzx   ebx, word ptr [r14]
0x1800097d9  test    r15w, bx
0x1800097dd  jnz     short loc_180009853
0x1800097df  movzx   eax, bl
0x1800097e2  test    byte ptr [rax+rbp], 1
0x1800097e6  jnz     short loc_180009821
0x1800097e8  movzx   ecx, bx
0x1800097eb  cmp     di, cx
0x1800097ee  jnz     loc_18000987A
0x1800097f4  add     rsi, 2
0x1800097f8  add     r14, 2
0x1800097fc  test    di, di
0x1800097ff  jnz     short loc_1800097C0
0x180009801  xor     eax, eax
0x180009803  add     rsp, 20h
0x180009807  pop     r15
0x180009809  pop     r14
0x18000980b  pop     r12
0x18000980d  pop     rdi
0x18000980e  pop     rsi
0x18000980f  pop     rbp
0x180009810  pop     rbx
0x180009811  retn
0x180009812  lea     edi, [rbx+20h]
0x180009815  movzx   eax, dil
0x180009819  test    byte ptr [rax+rbp], 2
0x18000981d  jnz     short loc_1800097D5
0x18000981f  jmp     short loc_1800097D2
0x180009821  lea     ecx, [rbx+20h]
0x180009824  movzx   eax, cl
0x180009827  test    byte ptr [rax+rbp], 2
0x18000982b  jnz     short loc_1800097EB
0x18000982d  jmp     short loc_1800097E8
0x18000982f  movzx   ecx, bx
0x180009832  call    _UlGetTypeFlags
0x180009837  bt      eax, 14h
0x18000983b  jnb     short loc_1800097D2
0x18000983d  mov     r8d, 200000h
0x180009843  mov     edx, r12d
0x180009846  movzx   ecx, bx
0x180009849  call    ConvertCaseHighUnicode
0x18000984e  movzx   edi, ax
0x180009851  jmp     short loc_1800097D5
0x180009853  movzx   ecx, bx
0x180009856  call    _UlGetTypeFlags
0x18000985b  bt      eax, 14h
0x18000985f  jnb     short loc_1800097E8
0x180009861  mov     r8d, 200000h
0x180009867  mov     edx, r12d
0x18000986a  movzx   ecx, bx
0x18000986d  call    ConvertCaseHighUnicode
0x180009872  movzx   ecx, ax
0x180009875  jmp     loc_1800097EB
0x18000987a  mov     eax, 1
0x18000987f  cmovbe  eax, r12d
0x180009883  jmp     loc_180009803
```
