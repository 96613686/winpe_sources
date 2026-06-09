# FaxGetExtensionDataA

- ea: `0x180022fb0`
- end: `0x18002305f`
- name: `FaxGetExtensionDataA`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000abe4`
- `0x180022fb0`
- `0x180023070`
- `0x18002bb58`
- `0x18002bc50`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180023005`
- `KERNEL32!SetLastError` at `0x180023005`

## pseudocode

```c
__int64 __fastcall FaxGetExtensionDataA(__int64 a1, int a2, const CHAR *a3, _QWORD *a4, __int64 a5)
{
  DWORD v9; // ecx
  WCHAR *v11; // rdi
  unsigned int ExtensionDataW; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids);
  }
  if ( !a3 )
  {
    v9 = 87;
LABEL_7:
    SetLastError(v9);
    return 0;
  }
  v11 = AnsiStringToUnicodeString(a3);
  if ( !v11 )
  {
    v9 = 8;
    goto LABEL_7;
  }
  ExtensionDataW = FaxGetExtensionDataW(a1, a2, v11, a4, a5);
  pMemFree(v11);
  return ExtensionDataW;
}

```

## disassembly

```asm
0x180022fb0  push    rbx
0x180022fb2  push    rbp
0x180022fb3  push    rsi
0x180022fb4  push    rdi
0x180022fb5  push    r14
0x180022fb7  sub     rsp, 30h
0x180022fbb  mov     rsi, r9
0x180022fbe  mov     rbx, r8
0x180022fc1  mov     ebp, edx
0x180022fc3  mov     r14, rcx
0x180022fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fcd  lea     rax, WPP_GLOBAL_Control
0x180022fd4  cmp     rcx, rax
0x180022fd7  jz      short loc_180022FFD
0x180022fd9  test    dword ptr [rcx+1Ch], 1000h
0x180022fe0  jz      short loc_180022FFD
0x180022fe2  cmp     byte ptr [rcx+19h], 5
0x180022fe6  jb      short loc_180022FFD
0x180022fe8  mov     rcx, [rcx+10h]
0x180022fec  lea     r8, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids
0x180022ff3  mov     edx, 5Ch ; '\'
0x180022ff8  call    WPP_SF_
0x180022ffd  test    rbx, rbx
0x180023000  jnz     short loc_180023015
0x180023002  lea     ecx, [rbx+57h]; dwErrCode
0x180023005  call    cs:__imp_SetLastError
0x18002300c  nop     dword ptr [rax+rax+00h]
0x180023011  xor     eax, eax
0x180023013  jmp     short loc_180023053
0x180023015  mov     rcx, rbx; lpMultiByteStr
0x180023018  call    AnsiStringToUnicodeString
0x18002301d  mov     rdi, rax
0x180023020  test    rax, rax
0x180023023  jnz     short loc_18002302A
0x180023025  lea     ecx, [rax+8]
0x180023028  jmp     short loc_180023005
0x18002302a  mov     rax, [rsp+58h+arg_20]
0x180023032  mov     r9, rsi
0x180023035  mov     r8, rdi
0x180023038  mov     [rsp+58h+var_38], rax
0x18002303d  mov     edx, ebp
0x18002303f  mov     rcx, r14
0x180023042  call    FaxGetExtensionDataW
0x180023047  mov     rcx, rdi; lpMem
0x18002304a  mov     ebx, eax
0x18002304c  call    pMemFree
0x180023051  mov     eax, ebx
0x180023053  add     rsp, 30h
0x180023057  pop     r14
0x180023059  pop     rdi
0x18002305a  pop     rsi
0x18002305b  pop     rbp
0x18002305c  pop     rbx
0x18002305d  retn
```
