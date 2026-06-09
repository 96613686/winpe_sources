# BparseCommandString

- ea: `0x18000bdc8`
- end: `0x18000bf21`
- name: `BparseCommandString`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000aafc`

## callees

- `0x180007220`
- `0x18000aef4`
- `0x18000bdc8`
- `0x18000c15c`
- `0x18000c190`
- `0x180072540`

## string_xrefs

- `0x18000bedd`: `CmdInvocation: command string segment must begin with '"' or '%'.`
- `0x18000bec4`: `BparseCommandString`
- `0x18000bebd`: `CmdInvocation: Unidrv imposes a max limit of 14 parameters per command.`
- `0x18000bed4`: `CmdInvocation: missing terminating '"'  in command string.`

## pseudocode

```c
_BOOL8 __fastcall BparseCommandString(__int64 a1, _DWORD *a2, __int64 a3)
{
  int v3; // edi
  __int64 i; // rbx
  int v7; // eax
  _BYTE *v8; // rcx
  int v9; // eax
  _BYTE *v10; // r11
  unsigned int v11; // r10d
  char *v12; // rdx
  unsigned int v13; // ecx
  __int64 j; // r8
  char v15; // r9
  __int128 v17; // [rsp+30h] [rbp-28h] BYREF
  char v18; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  v17 = 0;
  *a2 = 0;
  for ( i = a1; ; a1 = i )
  {
    BeatLeadingWhiteSpaces(a1);
    v7 = *(_DWORD *)(i + 8);
    if ( !v7 )
      break;
    v8 = *(_BYTE **)i;
    if ( **(_BYTE **)i == 37 )
    {
      if ( (unsigned int)++v3 > 0xE )
      {
        WriteDbgTraceErrorGpd(
          "BparseCommandString",
          "CmdInvocation: Unidrv imposes a max limit of 14 parameters per command.");
        return 0;
      }
      v9 = BprocessParam(i, a2, a3);
    }
    else
    {
      if ( *v8 != 34 )
      {
        WriteDbgTraceErrorGpd(
          "BparseCommandString",
          "CmdInvocation: command string segment must begin with '\"' or '%'.");
        return 0;
      }
      v10 = v8 + 1;
      v11 = v7 - 1;
      *(_QWORD *)i = v8 + 1;
      *(_DWORD *)(i + 8) = v7 - 1;
      v12 = v8 + 1;
      v13 = v7 - 1;
LABEL_8:
      if ( !v13 )
      {
        WriteDbgTraceErrorGpd("BparseCommandString", "CmdInvocation: missing terminating '\"'  in command string.");
        return 0;
      }
      for ( j = 0; ; j = 1 )
      {
        if ( (_DWORD)j )
        {
          ++v12;
          --v13;
          goto LABEL_8;
        }
        v15 = *v12;
        if ( *v12 == asc_18007C920[j] && (v15 != 34 && v15 != 60 || v13 >= v11 || *(v12 - 1) != 37) )
          break;
      }
      *(_QWORD *)&v17 = v10;
      *(_QWORD *)i = v12 + 1;
      DWORD2(v17) = v11 - v13;
      *(_DWORD *)(i + 8) = v13 - 1;
      v9 = BparseStrSegment(&v17, a2, a3);
    }
    if ( !v9 )
      return 0;
  }
  return (unsigned int)BwriteToHeap(&v18, &dword_18007CD2C, 1, 1, a3) != 0;
}

```

## disassembly

```asm
0x18000bdc8  mov     [rsp+arg_8], rbx
0x18000bdcd  mov     [rsp+arg_10], rbp
0x18000bdd2  push    rsi
0x18000bdd3  push    rdi
0x18000bdd4  push    r14
0x18000bdd6  sub     rsp, 40h
0x18000bdda  xorps   xmm0, xmm0
0x18000bddd  xor     edi, edi
0x18000bddf  movups  [rsp+58h+var_28], xmm0
0x18000bde4  mov     [rdx], edi
0x18000bde6  mov     rsi, r8
0x18000bde9  mov     r14, rdx
0x18000bdec  mov     rbx, rcx
0x18000bdef  call    BeatLeadingWhiteSpaces
0x18000bdf4  mov     eax, [rbx+8]
0x18000bdf7  test    eax, eax
0x18000bdf9  jz      loc_18000BEE6
0x18000bdff  mov     rcx, [rbx]
0x18000be02  cmp     byte ptr [rcx], 25h ; '%'
0x18000be05  jnz     short loc_18000BE25
0x18000be07  inc     edi
0x18000be09  cmp     edi, 0Eh
0x18000be0c  ja      loc_18000BEBD
0x18000be12  mov     r8, rsi
0x18000be15  mov     rdx, r14
0x18000be18  mov     rcx, rbx
0x18000be1b  call    BprocessParam
0x18000be20  jmp     loc_18000BEB1
0x18000be25  cmp     byte ptr [rcx], 22h ; '"'
0x18000be28  jnz     loc_18000BEDD
0x18000be2e  lea     r11, [rcx+1]
0x18000be32  lea     r10d, [rax-1]
0x18000be36  mov     [rbx], r11
0x18000be39  mov     [rbx+8], r10d
0x18000be3d  mov     rdx, r11
0x18000be40  mov     ecx, r10d
0x18000be43  test    ecx, ecx
0x18000be45  jz      loc_18000BED4
0x18000be4b  xor     r8d, r8d
0x18000be4e  cmp     r8d, 1
0x18000be52  jnb     short loc_18000BE80
0x18000be54  mov     r9b, [rdx]
0x18000be57  lea     rbp, asc_18007C920; "\""
0x18000be5e  cmp     r9b, [r8+rbp]
0x18000be62  jnz     short loc_18000BE7B
0x18000be64  cmp     r9b, 22h ; '"'
0x18000be68  jz      short loc_18000BE70
0x18000be6a  cmp     r9b, 3Ch ; '<'
0x18000be6e  jnz     short loc_18000BE87
0x18000be70  cmp     ecx, r10d
0x18000be73  jnb     short loc_18000BE87
0x18000be75  cmp     byte ptr [rdx-1], 25h ; '%'
0x18000be79  jnz     short loc_18000BE87
0x18000be7b  inc     r8d
0x18000be7e  jmp     short loc_18000BE4E
0x18000be80  inc     rdx
0x18000be83  dec     ecx
0x18000be85  jmp     short loc_18000BE43
0x18000be87  lea     rax, [rdx+1]
0x18000be8b  mov     qword ptr [rsp+58h+var_28], r11
0x18000be90  sub     r10d, ecx
0x18000be93  mov     [rbx], rax
0x18000be96  lea     eax, [rcx-1]
0x18000be99  mov     dword ptr [rsp+58h+var_28+8], r10d
0x18000be9e  lea     rcx, [rsp+58h+var_28]
0x18000bea3  mov     [rbx+8], eax
0x18000bea6  mov     r8, rsi
0x18000bea9  mov     rdx, r14
0x18000beac  call    BparseStrSegment
0x18000beb1  test    eax, eax
0x18000beb3  jz      short loc_18000BED0
0x18000beb5  mov     rcx, rbx
0x18000beb8  jmp     loc_18000BDEF
0x18000bebd  lea     rdx, aCmdinvocationU; "CmdInvocation: Unidrv imposes a max lim"...
0x18000bec4  lea     rcx, aBparsecommands; "BparseCommandString"
0x18000becb  call    WriteDbgTraceErrorGpd
0x18000bed0  xor     eax, eax
0x18000bed2  jmp     short loc_18000BF0E
0x18000bed4  lea     rdx, aCmdinvocationM; "CmdInvocation: missing terminating '\"'"...
0x18000bedb  jmp     short loc_18000BEC4
0x18000bedd  lea     rdx, aCmdinvocationC; "CmdInvocation: command string segment m"...
0x18000bee4  jmp     short loc_18000BEC4
0x18000bee6  mov     r9d, 1
0x18000beec  mov     [rsp+58h+var_38], rsi
0x18000bef1  mov     r8d, r9d
0x18000bef4  lea     rdx, dword_18007CD2C
0x18000befb  lea     rcx, [rsp+58h+arg_0]
0x18000bf00  call    BwriteToHeap
0x18000bf05  xor     ecx, ecx
0x18000bf07  test    eax, eax
0x18000bf09  setnz   cl
0x18000bf0c  mov     eax, ecx
0x18000bf0e  mov     rbx, [rsp+58h+arg_8]
0x18000bf13  mov     rbp, [rsp+58h+arg_10]
0x18000bf18  add     rsp, 40h
0x18000bf1c  pop     r14
0x18000bf1e  pop     rdi
0x18000bf1f  pop     rsi
0x18000bf20  retn
```
