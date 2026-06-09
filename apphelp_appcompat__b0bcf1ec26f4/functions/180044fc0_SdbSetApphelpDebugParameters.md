# SdbSetApphelpDebugParameters

- ea: `0x180044fc0`
- end: `0x1800450b8`
- name: `SdbSetApphelpDebugParameters`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000f114`
- `0x180044fc0`

## import_xrefs

- `ntdll!RtlCreateUnicodeString` at `0x18004504c`
- `ntdll!RtlCreateUnicodeString` at `0x18004508f`
- `ntdll!RtlCreateUnicodeString` at `0x18004504c`
- `ntdll!RtlCreateUnicodeString` at `0x18004508f`
- `ntdll!RtlFreeUnicodeString` at `0x18004501f`
- `ntdll!RtlFreeUnicodeString` at `0x18004502f`
- `ntdll!RtlFreeUnicodeString` at `0x18004501f`
- `ntdll!RtlFreeUnicodeString` at `0x18004502f`

## string_xrefs

- `0x180045061`: `Failed to create unicode string from "%S"`

## pseudocode

```c
__int64 __fastcall SdbSetApphelpDebugParameters(
        __int64 a1,
        const wchar_t *a2,
        int a3,
        int a4,
        const wchar_t *SourceString)
{
  int v6; // edi

  v6 = a3;
  if ( !a1 )
    return 0;
  if ( a4 && !a3 )
  {
    AslLogCallPrintf(
      1,
      "SdbSetApphelpDebugParameters",
      2576,
      "Inconsistent parameters: when using html help -- offline content flag should also be set");
    v6 = 1;
  }
  RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 200));
  RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 184));
  *(_DWORD *)(a1 + 176) = v6;
  *(_DWORD *)(a1 + 180) = a4;
  if ( a2 && !RtlCreateUnicodeString((PUNICODE_STRING)(a1 + 200), a2) )
  {
    AslLogCallPrintf(1, "SdbSetApphelpDebugParameters", 2588, "Failed to create unicode string from \"%S\"", a2);
    return 0;
  }
  if ( SourceString && !RtlCreateUnicodeString((PUNICODE_STRING)(a1 + 184), SourceString) )
  {
    AslLogCallPrintf(
      1,
      "SdbSetApphelpDebugParameters",
      2595,
      "Failed to create unicode string from \"%S\"",
      SourceString);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180044fc0  push    rbx
0x180044fc2  push    rbp
0x180044fc3  push    rsi
0x180044fc4  push    rdi
0x180044fc5  push    r12
0x180044fc7  push    r14
0x180044fc9  push    r15
0x180044fcb  sub     rsp, 30h
0x180044fcf  mov     ebp, r9d
0x180044fd2  mov     edi, r8d
0x180044fd5  mov     rsi, rdx
0x180044fd8  mov     rbx, rcx
0x180044fdb  test    rcx, rcx
0x180044fde  jnz     short loc_180044FE7
0x180044fe0  xor     eax, eax
0x180044fe2  jmp     loc_1800450A9
0x180044fe7  mov     r12d, 1
0x180044fed  test    ebp, ebp
0x180044fef  jz      short loc_180045015
0x180044ff1  test    r8d, r8d
0x180044ff4  jnz     short loc_180045015
0x180044ff6  lea     r9, aInconsistentPa; "Inconsistent parameters: when using htm"...
0x180044ffd  mov     r8d, 0A10h
0x180045003  lea     rdx, aSdbsetapphelpd_0; "SdbSetApphelpDebugParameters"
0x18004500a  mov     ecx, r12d
0x18004500d  call    AslLogCallPrintf
0x180045012  mov     edi, r12d
0x180045015  lea     r14, [rbx+0C8h]
0x18004501c  mov     rcx, r14; UnicodeString
0x18004501f  call    cs:__imp_RtlFreeUnicodeString
0x180045025  lea     r15, [rbx+0B8h]
0x18004502c  mov     rcx, r15; UnicodeString
0x18004502f  call    cs:__imp_RtlFreeUnicodeString
0x180045035  mov     [rbx+0B0h], edi
0x18004503b  mov     [rbx+0B4h], ebp
0x180045041  test    rsi, rsi
0x180045044  jz      short loc_18004507C
0x180045046  mov     rdx, rsi; SourceString
0x180045049  mov     rcx, r14; DestinationString
0x18004504c  call    cs:__imp_RtlCreateUnicodeString
0x180045052  test    al, al
0x180045054  jnz     short loc_18004507C
0x180045056  mov     [rsp+68h+var_48], rsi
0x18004505b  mov     r8d, 0A1Ch
0x180045061  lea     r9, aFailedToCreate_2; "Failed to create unicode string from \""...
0x180045068  mov     ecx, r12d
0x18004506b  lea     rdx, aSdbsetapphelpd_0; "SdbSetApphelpDebugParameters"
0x180045072  call    AslLogCallPrintf
0x180045077  jmp     loc_180044FE0
0x18004507c  mov     rbx, [rsp+68h+SourceString]
0x180045084  test    rbx, rbx
0x180045087  jz      short loc_1800450A6
0x180045089  mov     rdx, rbx; SourceString
0x18004508c  mov     rcx, r15; DestinationString
0x18004508f  call    cs:__imp_RtlCreateUnicodeString
0x180045095  test    al, al
0x180045097  jnz     short loc_1800450A6
0x180045099  mov     [rsp+68h+var_48], rbx
0x18004509e  mov     r8d, 0A23h
0x1800450a4  jmp     short loc_180045061
0x1800450a6  mov     eax, r12d
0x1800450a9  add     rsp, 30h
0x1800450ad  pop     r15
0x1800450af  pop     r14
0x1800450b1  pop     r12
0x1800450b3  pop     rdi
0x1800450b4  pop     rsi
0x1800450b5  pop     rbp
0x1800450b6  pop     rbx
0x1800450b7  retn
```
