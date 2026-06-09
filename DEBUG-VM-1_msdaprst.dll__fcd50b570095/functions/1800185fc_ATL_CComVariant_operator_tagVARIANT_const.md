# ATL::CComVariant::operator==(tagVARIANT const &)

- ea: `0x1800185fc`
- end: `0x18001870d`
- name: `??8CComVariant@ATL@@QEAA_NAEBUtagVARIANT@@@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002c118`

## callees

- `0x1800185fc`
- `0x18002e006`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x18001868b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180018697`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800186a7`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001868b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180018697`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800186a7`

## pseudocode

```c
char __fastcall ATL::CComVariant::operator==(unsigned __int16 *a1, __int64 a2)
{
  unsigned int v4; // eax
  char v6; // di
  bool v7; // zf
  UINT v9; // ebx
  UINT v10; // eax

  if ( a1 != (unsigned __int16 *)a2 )
  {
    v4 = *a1;
    if ( (_WORD)v4 != *(_WORD *)a2 )
      return 0;
    if ( v4 > 8 )
    {
      if ( v4 != 9 )
      {
        if ( v4 == 10 )
          return *((_DWORD *)a1 + 2) == *(_DWORD *)(a2 + 8);
        if ( v4 == 11 )
          return a1[4] == *(_WORD *)(a2 + 8);
        if ( v4 != 13 )
        {
          if ( v4 == 17 )
            return *((_BYTE *)a1 + 8) == *(_BYTE *)(a2 + 8);
          if ( v4 != 20 )
            return 0;
        }
      }
      return *((_QWORD *)a1 + 1) == *(_QWORD *)(a2 + 8);
    }
    if ( v4 == 8 )
    {
      v9 = SysStringByteLen(*(BSTR *)(a2 + 8));
      v6 = 0;
      if ( SysStringByteLen(*((BSTR *)a1 + 1)) != v9 )
        return v6;
      v10 = SysStringByteLen(*((BSTR *)a1 + 1));
      v7 = memcmp_0(*((const void **)a1 + 1), *(const void **)(a2 + 8), v10) == 0;
LABEL_14:
      if ( v7 )
        return 1;
      return v6;
    }
    v6 = 0;
    if ( *a1 && v4 != 1 )
    {
      if ( v4 != 2 )
      {
        if ( v4 != 3 )
        {
          if ( v4 == 4 )
          {
            v7 = *((float *)a1 + 2) == *(float *)(a2 + 8);
          }
          else
          {
            if ( v4 != 5 )
              return 0;
            v7 = *((double *)a1 + 1) == *(double *)(a2 + 8);
          }
          goto LABEL_14;
        }
        return *((_DWORD *)a1 + 2) == *(_DWORD *)(a2 + 8);
      }
      return a1[4] == *(_WORD *)(a2 + 8);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800185fc  push    rbx
0x1800185fe  push    rbp
0x1800185ff  push    rsi
0x180018600  push    rdi
0x180018601  sub     rsp, 28h
0x180018605  mov     rbp, rdx
0x180018608  mov     rsi, rcx
0x18001860b  cmp     rcx, rdx
0x18001860e  jz      loc_180018702
0x180018614  movzx   eax, word ptr [rcx]
0x180018617  cmp     ax, [rdx]
0x18001861a  jz      short loc_180018623
0x18001861c  xor     al, al
0x18001861e  jmp     loc_180018704
0x180018623  mov     ecx, eax
0x180018625  cmp     eax, 8
0x180018628  ja      loc_1800186C1
0x18001862e  jz      short loc_180018687
0x180018630  xor     edi, edi
0x180018632  test    eax, eax
0x180018634  jz      loc_180018702
0x18001863a  sub     ecx, 1
0x18001863d  jz      loc_180018702
0x180018643  sub     ecx, 1
0x180018646  jz      loc_1800186F5
0x18001864c  sub     ecx, 1
0x18001864f  jz      short loc_18001867F
0x180018651  sub     ecx, 1
0x180018654  jz      short loc_180018667
0x180018656  cmp     ecx, 1
0x180018659  jnz     short loc_18001861C
0x18001865b  movsd   xmm0, qword ptr [rsi+8]
0x180018660  ucomisd xmm0, qword ptr [rdx+8]
0x180018665  jmp     short loc_180018670
0x180018667  movss   xmm0, dword ptr [rsi+8]
0x18001866c  ucomiss xmm0, dword ptr [rdx+8]
0x180018670  jp      short loc_180018677
0x180018672  jnz     short loc_180018677
0x180018674  mov     dil, 1
0x180018677  mov     al, dil
0x18001867a  jmp     loc_180018704
0x18001867f  mov     eax, [rdx+8]
0x180018682  cmp     [rsi+8], eax
0x180018685  jmp     short loc_1800186FD
0x180018687  mov     rcx, [rdx+8]; bstr
0x18001868b  call    cs:__imp_SysStringByteLen
0x180018691  mov     rcx, [rsi+8]; bstr
0x180018695  mov     ebx, eax
0x180018697  call    cs:__imp_SysStringByteLen
0x18001869d  xor     edi, edi
0x18001869f  cmp     eax, ebx
0x1800186a1  jnz     short loc_180018677
0x1800186a3  mov     rcx, [rsi+8]; bstr
0x1800186a7  call    cs:__imp_SysStringByteLen
0x1800186ad  mov     rdx, [rbp+8]; Buf2
0x1800186b1  mov     rcx, [rsi+8]; Buf1
0x1800186b5  mov     r8d, eax; Size
0x1800186b8  call    memcmp_0
0x1800186bd  test    eax, eax
0x1800186bf  jmp     short loc_180018672
0x1800186c1  sub     ecx, 9
0x1800186c4  jz      short loc_1800186E3
0x1800186c6  sub     ecx, 1
0x1800186c9  jz      short loc_18001867F
0x1800186cb  sub     ecx, 1
0x1800186ce  jz      short loc_1800186F5
0x1800186d0  sub     ecx, 2
0x1800186d3  jz      short loc_1800186E3
0x1800186d5  sub     ecx, 4
0x1800186d8  jz      short loc_1800186ED
0x1800186da  cmp     ecx, 3
0x1800186dd  jnz     loc_18001861C
0x1800186e3  mov     rax, [rdx+8]
0x1800186e7  cmp     [rsi+8], rax
0x1800186eb  jmp     short loc_1800186FD
0x1800186ed  mov     al, [rdx+8]
0x1800186f0  cmp     [rsi+8], al
0x1800186f3  jmp     short loc_1800186FD
0x1800186f5  movzx   eax, word ptr [rdx+8]
0x1800186f9  cmp     [rsi+8], ax
0x1800186fd  setz    al
0x180018700  jmp     short loc_180018704
0x180018702  mov     al, 1
0x180018704  add     rsp, 28h
0x180018708  pop     rdi
0x180018709  pop     rsi
0x18001870a  pop     rbp
0x18001870b  pop     rbx
0x18001870c  retn
```
