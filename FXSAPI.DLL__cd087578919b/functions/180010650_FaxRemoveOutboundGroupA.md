# FaxRemoveOutboundGroupA

- ea: `0x180010650`
- end: `0x180010713`
- name: `FaxRemoveOutboundGroupA`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180010650`
- `0x180010720`
- `0x18002bb58`
- `0x18002bc50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800106c2`
- `KERNEL32!GetLastError` at `0x1800106c2`

## pseudocode

```c
__int64 __fastcall FaxRemoveOutboundGroupA(__int64 a1, const CHAR *a2)
{
  WCHAR *v4; // rax
  WCHAR *v5; // rdi
  DWORD LastError; // eax
  unsigned int v8; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  v4 = AnsiStringToUnicodeString(a2);
  v5 = v4;
  if ( v4 )
  {
    v8 = FaxRemoveOutboundGroupW(a1, v4);
    pMemFree(v5);
    return v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, LastError);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180010650  push    rbx
0x180010652  push    rsi
0x180010653  push    rdi
0x180010654  push    r14
0x180010656  sub     rsp, 28h
0x18001065a  mov     rbx, rdx
0x18001065d  mov     rsi, rcx
0x180010660  mov     rcx, cs:WPP_GLOBAL_Control
0x180010667  lea     r14, WPP_GLOBAL_Control
0x18001066e  cmp     rcx, r14
0x180010671  jz      short loc_180010697
0x180010673  test    dword ptr [rcx+1Ch], 1000h
0x18001067a  jz      short loc_180010697
0x18001067c  cmp     byte ptr [rcx+19h], 5
0x180010680  jb      short loc_180010697
0x180010682  mov     rcx, [rcx+10h]
0x180010686  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18001068d  mov     edx, 0E6h
0x180010692  call    WPP_SF_
0x180010697  mov     rcx, rbx; lpMultiByteStr
0x18001069a  call    AnsiStringToUnicodeString
0x18001069f  mov     rdi, rax
0x1800106a2  test    rax, rax
0x1800106a5  jnz     short loc_1800106F1
0x1800106a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800106ae  cmp     rax, r14
0x1800106b1  jz      short loc_1800106ED
0x1800106b3  test    dword ptr [rax+1Ch], 1000h
0x1800106ba  jz      short loc_1800106ED
0x1800106bc  cmp     byte ptr [rax+19h], 2
0x1800106c0  jb      short loc_1800106ED
0x1800106c2  call    cs:__imp_GetLastError
0x1800106c9  nop     dword ptr [rax+rax+00h]
0x1800106ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106d5  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x1800106dc  mov     edx, 0E7h
0x1800106e1  mov     r9d, eax
0x1800106e4  mov     rcx, [rcx+10h]
0x1800106e8  call    WPP_SF_d
0x1800106ed  xor     eax, eax
0x1800106ef  jmp     short loc_180010708
0x1800106f1  mov     rdx, rdi
0x1800106f4  mov     rcx, rsi
0x1800106f7  call    FaxRemoveOutboundGroupW
0x1800106fc  mov     rcx, rdi; lpMem
0x1800106ff  mov     ebx, eax
0x180010701  call    pMemFree
0x180010706  mov     eax, ebx
0x180010708  add     rsp, 28h
0x18001070c  pop     r14
0x18001070e  pop     rdi
0x18001070f  pop     rsi
0x180010710  pop     rbx
0x180010711  retn
```
