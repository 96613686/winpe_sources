# jsonUnescapeOneChar

- ea: `0x18007864c`
- end: `0x18007885c`
- name: `jsonUnescapeOneChar`
- size: `528`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800753cc`
- `0x180076974`
- `0x18007864c`
- `0x180078bb4`

## callees

- `0x180073984`
- `0x1800750c0`
- `0x18007864c`
- `0x180088190`

## pseudocode

```c
__int64 __fastcall jsonUnescapeOneChar(unsigned __int8 *a1, unsigned int a2, int *a3)
{
  unsigned int v6; // r9d
  __int64 result; // rax
  unsigned int v8; // r9d
  unsigned int v9; // r9d
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  unsigned int v12; // r9d
  unsigned int v13; // r9d
  int v14; // eax
  int v15; // esi
  unsigned __int8 *v16; // rcx
  __int64 v17; // rdx
  int Limited; // eax
  int v19; // esi
  __int16 v20; // ax
  int v21; // esi

  if ( a2 < 2 )
    goto LABEL_46;
  v6 = a1[1];
  if ( v6 > 0x66 )
  {
    v8 = v6 - 110;
    if ( !v8 )
    {
      *a3 = 10;
      return 2;
    }
    v9 = v8 - 4;
    if ( !v9 )
    {
      *a3 = 13;
      return 2;
    }
    v10 = v9 - 2;
    if ( !v10 )
    {
      *a3 = 9;
      return 2;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      if ( a2 >= 6 )
      {
        v19 = jsonHexToInt4(a1 + 2);
        if ( (v19 & 0xFC00) == 0xD800
          && a2 >= 0xC
          && a1[6] == 92
          && a1[7] == 117
          && (v20 = jsonHexToInt4(a1 + 8), (v20 & 0xFC00) == 0xDC00) )
        {
          v21 = (v20 & 0x3FF) + (((v19 & 0x3FF) + 64) << 10);
          result = 12;
          *a3 = v21;
        }
        else
        {
          *a3 = v19;
          return 6;
        }
        return result;
      }
LABEL_46:
      *a3 = 629145;
      return a2;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      *a3 = 11;
      return 2;
    }
    v13 = v12 - 2;
    if ( !v13 )
    {
      if ( a2 >= 4 )
      {
        result = 4;
        *a3 = (a1[3] - 7 * (((char)a1[3] >> 6) & 1)) & 0xF | (16 * ((a1[2] - 7 * (((char)a1[2] >> 6) & 1)) & 0xF));
        return result;
      }
      goto LABEL_46;
    }
    if ( v13 != 106 )
      goto LABEL_24;
  }
  else
  {
    if ( v6 == 102 )
    {
      *a3 = 12;
      return 2;
    }
    if ( v6 != 10 && v6 != 13 )
    {
      switch ( v6 )
      {
        case '"':
        case '\'':
        case '/':
          goto LABEL_15;
        case '0':
          *a3 = 0;
          return 2;
        case '\\':
LABEL_15:
          *a3 = (char)v6;
          return 2;
        case 'b':
          *a3 = 8;
          return 2;
      }
LABEL_24:
      *a3 = 629145;
      return 2;
    }
  }
  v14 = jsonBytesToBypass(a1, a2);
  v15 = v14;
  if ( !v14 )
    goto LABEL_46;
  if ( v14 == a2 )
  {
    *a3 = 0;
    return a2;
  }
  v16 = &a1[v14];
  v17 = a2 - v14;
  if ( *v16 == 92 )
    Limited = jsonUnescapeOneChar(v16, v17, a3);
  else
    Limited = sqlite3Utf8ReadLimited(v16, v17, a3);
  return (unsigned int)(v15 + Limited);
}

```

## disassembly

```asm
0x18007864c  push    rbx
0x18007864e  push    rbp
0x18007864f  push    rsi
0x180078650  push    rdi
0x180078651  sub     rsp, 28h
0x180078655  mov     edi, edx
0x180078657  mov     rbx, r8
0x18007865a  mov     edx, 2
0x18007865f  mov     rbp, rcx
0x180078662  cmp     edi, edx
0x180078664  jb      loc_18007884B
0x18007866a  movzx   r9d, byte ptr [rcx+1]
0x18007866f  cmp     r9d, 66h ; 'f'
0x180078673  ja      short loc_1800786D3
0x180078675  jz      short loc_1800786CA
0x180078677  mov     ecx, r9d
0x18007867a  sub     ecx, 0Ah
0x18007867d  jz      loc_180078718
0x180078683  sub     ecx, 3
0x180078686  jz      loc_180078718
0x18007868c  sub     ecx, 15h
0x18007868f  jz      short loc_1800786C1
0x180078691  sub     ecx, 5
0x180078694  jz      short loc_1800786C1
0x180078696  sub     ecx, 8
0x180078699  jz      short loc_1800786C1
0x18007869b  sub     ecx, 1
0x18007869e  jz      short loc_1800786B8
0x1800786a0  sub     ecx, 2Ch ; ','
0x1800786a3  jz      short loc_1800786C1
0x1800786a5  cmp     ecx, 6
0x1800786a8  jnz     short loc_18007870F
0x1800786aa  mov     dword ptr [r8], 8
0x1800786b1  mov     eax, edx
0x1800786b3  jmp     loc_180078853
0x1800786b8  mov     dword ptr [r8], 0
0x1800786bf  jmp     short loc_1800786B1
0x1800786c1  movsx   eax, r9b
0x1800786c5  mov     [r8], eax
0x1800786c8  jmp     short loc_1800786B1
0x1800786ca  mov     dword ptr [r8], 0Ch
0x1800786d1  jmp     short loc_1800786B1
0x1800786d3  sub     r9d, 6Eh ; 'n'
0x1800786d7  jz      loc_18007883F
0x1800786dd  sub     r9d, 4
0x1800786e1  jz      loc_180078833
0x1800786e7  sub     r9d, edx
0x1800786ea  jz      loc_180078827
0x1800786f0  sub     r9d, 1
0x1800786f4  jz      loc_1800787B7
0x1800786fa  sub     r9d, 1
0x1800786fe  jz      loc_1800787AB
0x180078704  sub     r9d, edx
0x180078707  jz      short loc_18007875E
0x180078709  cmp     r9d, 6Ah ; 'j'
0x18007870d  jz      short loc_180078718
0x18007870f  mov     dword ptr [r8], 99999h
0x180078716  jmp     short loc_1800786B1
0x180078718  mov     edx, edi
0x18007871a  mov     rcx, rbp
0x18007871d  call    jsonBytesToBypass
0x180078722  mov     esi, eax
0x180078724  test    eax, eax
0x180078726  jz      loc_18007884B
0x18007872c  cmp     esi, edi
0x18007872e  jnz     short loc_18007873B
0x180078730  mov     dword ptr [rbx], 0
0x180078736  jmp     loc_180078851
0x18007873b  sub     edi, esi
0x18007873d  lea     rcx, [rsi+rbp]
0x180078741  cmp     byte ptr [rcx], 5Ch ; '\'
0x180078744  mov     r8, rbx
0x180078747  mov     edx, edi
0x180078749  jnz     short loc_180078757
0x18007874b  call    jsonUnescapeOneChar
0x180078750  add     eax, esi
0x180078752  jmp     loc_180078853
0x180078757  call    sqlite3Utf8ReadLimited
0x18007875c  jmp     short loc_180078750
0x18007875e  cmp     edi, 4
0x180078761  jb      loc_18007884B
0x180078767  mov     al, [rcx+2]
0x18007876a  mov     r8b, [rbp+2]
0x18007876e  sar     al, 6
0x180078771  and     al, 1
0x180078773  movzx   eax, al
0x180078776  imul    ecx, eax, 7
0x180078779  mov     eax, 4
0x18007877e  sub     r8b, cl
0x180078781  mov     cl, [rbp+3]
0x180078784  sar     cl, 6
0x180078787  and     r8d, 0Fh
0x18007878b  and     cl, 1
0x18007878e  shl     r8d, 4
0x180078792  movzx   ecx, cl
0x180078795  imul    edx, ecx, 7
0x180078798  mov     cl, [rbp+3]
0x18007879b  sub     cl, dl
0x18007879d  and     ecx, 0Fh
0x1800787a0  or      r8d, ecx
0x1800787a3  mov     [rbx], r8d
0x1800787a6  jmp     loc_180078853
0x1800787ab  mov     dword ptr [r8], 0Bh
0x1800787b2  jmp     loc_1800786B1
0x1800787b7  cmp     edi, 6
0x1800787ba  jb      loc_18007884B
0x1800787c0  add     rcx, rdx
0x1800787c3  call    jsonHexToInt4
0x1800787c8  mov     ecx, eax
0x1800787ca  mov     esi, eax
0x1800787cc  and     ecx, 0FC00h
0x1800787d2  cmp     ecx, 0D800h
0x1800787d8  jnz     short loc_18007881E
0x1800787da  cmp     edi, 0Ch
0x1800787dd  jb      short loc_18007881E
0x1800787df  cmp     byte ptr [rbp+6], 5Ch ; '\'
0x1800787e3  jnz     short loc_18007881E
0x1800787e5  cmp     byte ptr [rbp+7], 75h ; 'u'
0x1800787e9  jnz     short loc_18007881E
0x1800787eb  lea     rcx, [rbp+8]
0x1800787ef  call    jsonHexToInt4
0x1800787f4  mov     ecx, eax
0x1800787f6  and     ecx, 0FC00h
0x1800787fc  cmp     ecx, 0DC00h
0x180078802  jnz     short loc_18007881E
0x180078804  mov     ecx, 3FFh
0x180078809  and     esi, ecx
0x18007880b  and     eax, ecx
0x18007880d  add     esi, 40h ; '@'
0x180078810  shl     esi, 0Ah
0x180078813  add     esi, eax
0x180078815  mov     eax, 0Ch
0x18007881a  mov     [rbx], esi
0x18007881c  jmp     short loc_180078853
0x18007881e  mov     [rbx], esi
0x180078820  mov     eax, 6
0x180078825  jmp     short loc_180078853
0x180078827  mov     dword ptr [r8], 9
0x18007882e  jmp     loc_1800786B1
0x180078833  mov     dword ptr [r8], 0Dh
0x18007883a  jmp     loc_1800786B1
0x18007883f  mov     dword ptr [r8], 0Ah
0x180078846  jmp     loc_1800786B1
0x18007884b  mov     dword ptr [rbx], 99999h
0x180078851  mov     eax, edi
0x180078853  add     rsp, 28h
0x180078857  pop     rdi
0x180078858  pop     rsi
0x180078859  pop     rbp
0x18007885a  pop     rbx
0x18007885b  retn
```
