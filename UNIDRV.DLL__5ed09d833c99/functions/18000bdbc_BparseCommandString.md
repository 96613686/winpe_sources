# BparseCommandString

- ea: `0x18000bdbc`
- end: `0x18000bf16`
- name: `BparseCommandString`
- size: `346`
- prototype: `_BOOL8 __fastcall(__int64, int *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000aafc`

## callees

- `0x180007150`
- `0x18000af00`
- `0x18000bdbc`
- `0x18000c14c`
- `0x18000c184`
- `0x1800745c8`

## string_xrefs

- `0x18000bed1`: `CmdInvocation: command string segment must begin with '"' or '%'.`
- `0x18000beb8`: `BparseCommandString`
- `0x18000beb1`: `CmdInvocation: Unidrv imposes a max limit of 14 parameters per command.`
- `0x18000bec8`: `CmdInvocation: missing terminating '"'  in command string.`

## pseudocode

```c
_BOOL8 __fastcall BparseCommandString(__int64 a1, int *a2, __int64 a3)
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
  int v18; // [rsp+60h] [rbp+8h] BYREF

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
          (__int64)"BparseCommandString",
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
          (__int64)"BparseCommandString",
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
        WriteDbgTraceErrorGpd(
          (__int64)"BparseCommandString",
          "CmdInvocation: missing terminating '\"'  in command string.");
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
        if ( *v12 == asc_18007E920[j] && (v15 != 34 && v15 != 60 || v13 >= v11 || *(v12 - 1) != 37) )
          break;
      }
      *(_QWORD *)&v17 = v10;
      *(_QWORD *)i = v12 + 1;
      DWORD2(v17) = v11 - v13;
      *(_DWORD *)(i + 8) = v13 - 1;
      v9 = BparseStrSegment((__int64)&v17, a2, a3);
    }
    if ( !v9 )
      return 0;
  }
  return (unsigned int)BwriteToHeap(&v18, &dword_18007ED2C, 1u, 1u, a3) != 0;
}

```

## disassembly

```asm
0x18000bdbc  mov     [rsp+arg_8], rbx
0x18000bdc1  mov     [rsp+arg_10], rbp
0x18000bdc6  push    rsi
0x18000bdc7  push    rdi
0x18000bdc8  push    r14
0x18000bdca  sub     rsp, 40h
0x18000bdce  xorps   xmm0, xmm0
0x18000bdd1  xor     edi, edi
0x18000bdd3  movups  [rsp+58h+var_28], xmm0
0x18000bdd8  mov     [rdx], edi
0x18000bdda  mov     rsi, r8
0x18000bddd  mov     r14, rdx
0x18000bde0  mov     rbx, rcx
0x18000bde3  call    BeatLeadingWhiteSpaces
0x18000bde8  mov     eax, [rbx+8]
0x18000bdeb  test    eax, eax
0x18000bded  jz      loc_18000BEDA
0x18000bdf3  mov     rcx, [rbx]
0x18000bdf6  cmp     byte ptr [rcx], 25h ; '%'
0x18000bdf9  jnz     short loc_18000BE19
0x18000bdfb  inc     edi
0x18000bdfd  cmp     edi, 0Eh
0x18000be00  ja      loc_18000BEB1
0x18000be06  mov     r8, rsi
0x18000be09  mov     rdx, r14
0x18000be0c  mov     rcx, rbx
0x18000be0f  call    BprocessParam
0x18000be14  jmp     loc_18000BEA5
0x18000be19  cmp     byte ptr [rcx], 22h ; '"'
0x18000be1c  jnz     loc_18000BED1
0x18000be22  lea     r11, [rcx+1]
0x18000be26  lea     r10d, [rax-1]
0x18000be2a  mov     [rbx], r11
0x18000be2d  mov     [rbx+8], r10d
0x18000be31  mov     rdx, r11
0x18000be34  mov     ecx, r10d
0x18000be37  test    ecx, ecx
0x18000be39  jz      loc_18000BEC8
0x18000be3f  xor     r8d, r8d
0x18000be42  cmp     r8d, 1
0x18000be46  jnb     short loc_18000BE74
0x18000be48  mov     r9b, [rdx]
0x18000be4b  lea     rbp, asc_18007E920; "\""
0x18000be52  cmp     r9b, [r8+rbp]
0x18000be56  jnz     short loc_18000BE6F
0x18000be58  cmp     r9b, 22h ; '"'
0x18000be5c  jz      short loc_18000BE64
0x18000be5e  cmp     r9b, 3Ch ; '<'
0x18000be62  jnz     short loc_18000BE7B
0x18000be64  cmp     ecx, r10d
0x18000be67  jnb     short loc_18000BE7B
0x18000be69  cmp     byte ptr [rdx-1], 25h ; '%'
0x18000be6d  jnz     short loc_18000BE7B
0x18000be6f  inc     r8d
0x18000be72  jmp     short loc_18000BE42
0x18000be74  inc     rdx
0x18000be77  dec     ecx
0x18000be79  jmp     short loc_18000BE37
0x18000be7b  lea     rax, [rdx+1]
0x18000be7f  mov     qword ptr [rsp+58h+var_28], r11
0x18000be84  sub     r10d, ecx
0x18000be87  mov     [rbx], rax
0x18000be8a  lea     eax, [rcx-1]
0x18000be8d  mov     dword ptr [rsp+58h+var_28+8], r10d
0x18000be92  lea     rcx, [rsp+58h+var_28]
0x18000be97  mov     [rbx+8], eax
0x18000be9a  mov     r8, rsi
0x18000be9d  mov     rdx, r14
0x18000bea0  call    BparseStrSegment
0x18000bea5  test    eax, eax
0x18000bea7  jz      short loc_18000BEC4
0x18000bea9  mov     rcx, rbx
0x18000beac  jmp     loc_18000BDE3
0x18000beb1  lea     rdx, aCmdinvocationU; "CmdInvocation: Unidrv imposes a max lim"...
0x18000beb8  lea     rcx, aBparsecommands; "BparseCommandString"
0x18000bebf  call    WriteDbgTraceErrorGpd
0x18000bec4  xor     eax, eax
0x18000bec6  jmp     short loc_18000BF02
0x18000bec8  lea     rdx, aCmdinvocationM; "CmdInvocation: missing terminating '\"'"...
0x18000becf  jmp     short loc_18000BEB8
0x18000bed1  lea     rdx, aCmdinvocationC; "CmdInvocation: command string segment m"...
0x18000bed8  jmp     short loc_18000BEB8
0x18000beda  mov     r9d, 1
0x18000bee0  mov     [rsp+58h+var_38], rsi
0x18000bee5  mov     r8d, r9d
0x18000bee8  lea     rdx, dword_18007ED2C
0x18000beef  lea     rcx, [rsp+58h+arg_0]
0x18000bef4  call    BwriteToHeap
0x18000bef9  xor     ecx, ecx
0x18000befb  test    eax, eax
0x18000befd  setnz   cl
0x18000bf00  mov     eax, ecx
0x18000bf02  mov     rbx, [rsp+58h+arg_8]
0x18000bf07  mov     rbp, [rsp+58h+arg_10]
0x18000bf0c  add     rsp, 40h
0x18000bf10  pop     r14
0x18000bf12  pop     rdi
0x18000bf13  pop     rsi
0x18000bf14  retn
```
