# jsonTranslateBlobToPrettyText

- ea: `0x180077360`
- end: `0x180077506`
- name: `jsonTranslateBlobToPrettyText`
- size: `422`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800765e0`
- `0x180077360`

## callees

- `0x180072b08`
- `0x180072d28`
- `0x1800766ec`
- `0x180077360`
- `0x18007750c`
- `0x180078a58`

## pseudocode

```c
__int64 __fastcall jsonTranslateBlobToPrettyText(__int64 a1, unsigned int a2)
{
  __int64 *v2; // r14
  __int64 v3; // rbx
  __int64 *v5; // rcx
  __int64 v6; // rsi
  int v7; // ecx
  unsigned int v9; // esi
  unsigned int v10; // r15d
  unsigned int v11; // ebp
  char v12; // dl
  unsigned int v13; // r14d
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF

  v2 = *(__int64 **)a1;
  v3 = *(_QWORD *)(a1 + 8);
  v5 = *(__int64 **)a1;
  v6 = a2;
  v14 = 0;
  v7 = jsonbPayloadSize(v5, a2, &v14);
  if ( !v7 )
  {
    *(_BYTE *)(v3 + 33) |= 2u;
    return (unsigned int)(*((_DWORD *)v2 + 2) + 1);
  }
  if ( (*(_BYTE *)(v6 + *v2) & 0xF) == 0xB )
  {
    v13 = v7 + v6;
    v9 = v7 + v6 + v14;
    jsonAppendChar((_QWORD *)v3, 91);
    if ( v13 < v9 )
    {
      jsonAppendChar((_QWORD *)v3, 10);
      ++*(_DWORD *)(a1 + 28);
      while ( !*(_BYTE *)(v3 + 33) )
      {
        jsonPrettyIndent(a1);
        v13 = jsonTranslateBlobToPrettyText(a1, v13);
        if ( v13 >= v9 )
          break;
        jsonAppendRawNZ((_QWORD *)v3, ",\n", 2u);
      }
      jsonAppendChar((_QWORD *)v3, 10);
      --*(_DWORD *)(a1 + 28);
      jsonPrettyIndent(a1);
    }
    v12 = 93;
LABEL_22:
    jsonAppendChar((_QWORD *)v3, v12);
    return v9;
  }
  if ( (*(_BYTE *)(v6 + *v2) & 0xF) == 0xC )
  {
    v10 = v7 + v6;
    v9 = v7 + v6 + v14;
    jsonAppendChar((_QWORD *)v3, 123);
    if ( v10 < v9 )
    {
      jsonAppendChar((_QWORD *)v3, 10);
      ++*(_DWORD *)(a1 + 28);
      while ( !*(_BYTE *)(v3 + 33) )
      {
        jsonPrettyIndent(a1);
        v11 = jsonTranslateBlobToText(v2, v10, v3);
        if ( v11 > v9 )
        {
          *(_BYTE *)(v3 + 33) |= 2u;
          break;
        }
        jsonAppendRawNZ((_QWORD *)v3, ": ", 2u);
        v10 = jsonTranslateBlobToPrettyText(a1, v11);
        if ( v10 >= v9 )
          break;
        jsonAppendRawNZ((_QWORD *)v3, ",\n", 2u);
      }
      jsonAppendChar((_QWORD *)v3, 10);
      --*(_DWORD *)(a1 + 28);
      jsonPrettyIndent(a1);
    }
    v12 = 125;
    goto LABEL_22;
  }
  return (unsigned int)jsonTranslateBlobToText(v2, (unsigned int)v6, v3);
}

```

## disassembly

```asm
0x180077360  push    rbx
0x180077362  push    rbp
0x180077363  push    rsi
0x180077364  push    rdi
0x180077365  push    r14
0x180077367  push    r15
0x180077369  sub     rsp, 28h
0x18007736d  mov     r14, [rcx]
0x180077370  lea     r8, [rsp+58h+arg_0]
0x180077375  mov     rbx, [rcx+8]
0x180077379  mov     rdi, rcx
0x18007737c  mov     rcx, r14
0x18007737f  mov     esi, edx
0x180077381  mov     [rsp+58h+arg_0], 0
0x180077389  call    jsonbPayloadSize
0x18007738e  mov     ecx, eax
0x180077390  test    eax, eax
0x180077392  jnz     short loc_1800773A3
0x180077394  or      byte ptr [rbx+21h], 2
0x180077398  mov     eax, [r14+8]
0x18007739c  inc     eax
0x18007739e  jmp     loc_1800774F9
0x1800773a3  mov     rax, [r14]
0x1800773a6  movzx   r8d, byte ptr [rsi+rax]
0x1800773ab  and     r8d, 0Fh
0x1800773af  sub     r8d, 0Bh
0x1800773b3  jz      loc_18007747A
0x1800773b9  cmp     r8d, 1
0x1800773bd  jz      short loc_1800773D3
0x1800773bf  mov     r8, rbx
0x1800773c2  mov     edx, esi
0x1800773c4  mov     rcx, r14
0x1800773c7  call    jsonTranslateBlobToText
0x1800773cc  mov     esi, eax
0x1800773ce  jmp     loc_1800774F7
0x1800773d3  lea     r15d, [rcx+rsi]
0x1800773d7  mov     dl, 7Bh ; '{'
0x1800773d9  mov     esi, [rsp+58h+arg_0]
0x1800773dd  mov     rcx, rbx
0x1800773e0  add     esi, r15d
0x1800773e3  call    jsonAppendChar
0x1800773e8  cmp     r15d, esi
0x1800773eb  jnb     loc_180077476
0x1800773f1  mov     dl, 0Ah
0x1800773f3  mov     rcx, rbx
0x1800773f6  call    jsonAppendChar
0x1800773fb  inc     dword ptr [rdi+1Ch]
0x1800773fe  cmp     byte ptr [rbx+21h], 0
0x180077402  jnz     short loc_180077461
0x180077404  mov     rcx, rdi
0x180077407  call    jsonPrettyIndent
0x18007740c  mov     r8, rbx
0x18007740f  mov     edx, r15d
0x180077412  mov     rcx, r14
0x180077415  call    jsonTranslateBlobToText
0x18007741a  mov     ebp, eax
0x18007741c  cmp     eax, esi
0x18007741e  ja      short loc_18007745D
0x180077420  mov     r8d, 2
0x180077426  lea     rdx, asc_1800A6204; ": "
0x18007742d  mov     rcx, rbx
0x180077430  call    jsonAppendRawNZ
0x180077435  mov     edx, ebp
0x180077437  mov     rcx, rdi
0x18007743a  call    jsonTranslateBlobToPrettyText
0x18007743f  mov     r15d, eax
0x180077442  cmp     eax, esi
0x180077444  jnb     short loc_180077461
0x180077446  mov     r8d, 2
0x18007744c  lea     rdx, asc_1800A6200; ",\n"
0x180077453  mov     rcx, rbx
0x180077456  call    jsonAppendRawNZ
0x18007745b  jmp     short loc_1800773FE
0x18007745d  or      byte ptr [rbx+21h], 2
0x180077461  mov     dl, 0Ah
0x180077463  mov     rcx, rbx
0x180077466  call    jsonAppendChar
0x18007746b  dec     dword ptr [rdi+1Ch]
0x18007746e  mov     rcx, rdi
0x180077471  call    jsonPrettyIndent
0x180077476  mov     dl, 7Dh ; '}'
0x180077478  jmp     short loc_1800774EF
0x18007747a  lea     r14d, [rcx+rsi]
0x18007747e  mov     dl, 5Bh ; '['
0x180077480  mov     esi, [rsp+58h+arg_0]
0x180077484  mov     rcx, rbx
0x180077487  add     esi, r14d
0x18007748a  call    jsonAppendChar
0x18007748f  cmp     r14d, esi
0x180077492  jnb     short loc_1800774ED
0x180077494  mov     dl, 0Ah
0x180077496  mov     rcx, rbx
0x180077499  call    jsonAppendChar
0x18007749e  inc     dword ptr [rdi+1Ch]
0x1800774a1  jmp     short loc_1800774D2
0x1800774a3  mov     rcx, rdi
0x1800774a6  call    jsonPrettyIndent
0x1800774ab  mov     edx, r14d
0x1800774ae  mov     rcx, rdi
0x1800774b1  call    jsonTranslateBlobToPrettyText
0x1800774b6  mov     r14d, eax
0x1800774b9  cmp     eax, esi
0x1800774bb  jnb     short loc_1800774D8
0x1800774bd  mov     r8d, 2
0x1800774c3  lea     rdx, asc_1800A6200; ",\n"
0x1800774ca  mov     rcx, rbx
0x1800774cd  call    jsonAppendRawNZ
0x1800774d2  cmp     byte ptr [rbx+21h], 0
0x1800774d6  jz      short loc_1800774A3
0x1800774d8  mov     dl, 0Ah
0x1800774da  mov     rcx, rbx
0x1800774dd  call    jsonAppendChar
0x1800774e2  dec     dword ptr [rdi+1Ch]
0x1800774e5  mov     rcx, rdi
0x1800774e8  call    jsonPrettyIndent
0x1800774ed  mov     dl, 5Dh ; ']'
0x1800774ef  mov     rcx, rbx
0x1800774f2  call    jsonAppendChar
0x1800774f7  mov     eax, esi
0x1800774f9  add     rsp, 28h
0x1800774fd  pop     r15
0x1800774ff  pop     r14
0x180077501  pop     rdi
0x180077502  pop     rsi
0x180077503  pop     rbp
0x180077504  pop     rbx
0x180077505  retn
```
