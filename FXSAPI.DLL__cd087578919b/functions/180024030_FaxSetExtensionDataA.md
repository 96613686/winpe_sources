# FaxSetExtensionDataA

- ea: `0x180024030`
- end: `0x1800240dd`
- name: `FaxSetExtensionDataA`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000abe4`
- `0x180024030`
- `0x1800240f0`
- `0x18002bb58`
- `0x18002bc50`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180024085`
- `KERNEL32!SetLastError` at `0x180024085`

## pseudocode

```c
__int64 __fastcall FaxSetExtensionDataA(__int64 a1, int a2, const CHAR *a3, __int64 a4, int a5)
{
  DWORD v9; // ecx
  WCHAR *v11; // rdi
  unsigned int v12; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids);
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
  v12 = FaxSetExtensionDataW(a1, a2, v11, a4, a5);
  pMemFree(v11);
  return v12;
}

```

## disassembly

```asm
0x180024030  push    rbx
0x180024032  push    rbp
0x180024033  push    rsi
0x180024034  push    rdi
0x180024035  push    r14
0x180024037  sub     rsp, 30h
0x18002403b  mov     rsi, r9
0x18002403e  mov     rbx, r8
0x180024041  mov     ebp, edx
0x180024043  mov     r14, rcx
0x180024046  mov     rcx, cs:WPP_GLOBAL_Control
0x18002404d  lea     rax, WPP_GLOBAL_Control
0x180024054  cmp     rcx, rax
0x180024057  jz      short loc_18002407D
0x180024059  test    dword ptr [rcx+1Ch], 1000h
0x180024060  jz      short loc_18002407D
0x180024062  cmp     byte ptr [rcx+19h], 5
0x180024066  jb      short loc_18002407D
0x180024068  mov     rcx, [rcx+10h]
0x18002406c  lea     r8, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids
0x180024073  mov     edx, 5Fh ; '_'
0x180024078  call    WPP_SF_
0x18002407d  test    rbx, rbx
0x180024080  jnz     short loc_180024095
0x180024082  lea     ecx, [rbx+57h]; dwErrCode
0x180024085  call    cs:__imp_SetLastError
0x18002408c  nop     dword ptr [rax+rax+00h]
0x180024091  xor     eax, eax
0x180024093  jmp     short loc_1800240D1
0x180024095  mov     rcx, rbx; lpMultiByteStr
0x180024098  call    AnsiStringToUnicodeString
0x18002409d  mov     rdi, rax
0x1800240a0  test    rax, rax
0x1800240a3  jnz     short loc_1800240AA
0x1800240a5  lea     ecx, [rax+8]
0x1800240a8  jmp     short loc_180024085
0x1800240aa  mov     eax, [rsp+58h+arg_20]
0x1800240b1  mov     r9, rsi
0x1800240b4  mov     r8, rdi
0x1800240b7  mov     [rsp+58h+var_38], eax
0x1800240bb  mov     edx, ebp
0x1800240bd  mov     rcx, r14
0x1800240c0  call    FaxSetExtensionDataW
0x1800240c5  mov     rcx, rdi; lpMem
0x1800240c8  mov     ebx, eax
0x1800240ca  call    pMemFree
0x1800240cf  mov     eax, ebx
0x1800240d1  add     rsp, 30h
0x1800240d5  pop     r14
0x1800240d7  pop     rdi
0x1800240d8  pop     rsi
0x1800240d9  pop     rbp
0x1800240da  pop     rbx
0x1800240db  retn
```
