# CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)

- ea: `0x18000b448`
- end: `0x18000b4e4`
- name: `??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z`
- size: `156`
- prototype: `__int64 __fastcall(_WORD *, _DWORD *)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bb10`
- `0x180011e90`
- `0x180011fac`
- `0x1800133e0`
- `0x180013780`
- `0x1800142f8`
- `0x180018388`
- `0x1800188f8`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000b448`

## pseudocode

```c
__int64 __fastcall CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(_WORD *a1, _DWORD *a2)
{
  __int64 v3; // r8
  unsigned int v4; // ebx
  __int64 v5; // rcx
  int v6; // edi

  if ( !a1 )
  {
    v4 = -2147024809;
LABEL_12:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_13;
  }
  v3 = 0x7FFFFFFF;
  do
  {
    if ( !*a1 )
      break;
    ++a1;
    --v3;
  }
  while ( v3 );
  v4 = v3 == 0 ? 0x80070057 : 0;
  if ( !v3 )
    goto LABEL_12;
  v6 = v3 != 0 ? 0x7FFFFFFF - v3 : 0;
  v5 = (0x7FFFFFFF - v3) & -(__int64)(v3 != 0);
  if ( v5 == (unsigned int)v5 )
  {
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v4 = 0;
  }
  else
  {
    v4 = -2147024362;
    v6 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_12;
  *a2 = v6;
LABEL_13:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x18000b448  push    rbx
0x18000b44a  push    rbp
0x18000b44b  push    rsi
0x18000b44c  push    rdi
0x18000b44d  sub     rsp, 28h
0x18000b451  xor     ebp, ebp
0x18000b453  mov     rsi, rdx
0x18000b456  test    rcx, rcx
0x18000b459  jz      short loc_18000B4C6
0x18000b45b  mov     r9d, 7FFFFFFFh
0x18000b461  mov     r8d, r9d
0x18000b464  cmp     [rcx], bp
0x18000b467  jz      short loc_18000B473
0x18000b469  add     rcx, 2
0x18000b46d  sub     r8, 1
0x18000b471  jnz     short loc_18000B464
0x18000b473  mov     rax, r8
0x18000b476  neg     rax
0x18000b479  mov     rax, r8
0x18000b47c  sbb     ebx, ebx
0x18000b47e  sub     r9, r8
0x18000b481  not     ebx
0x18000b483  and     ebx, 80070057h
0x18000b489  neg     rax
0x18000b48c  sbb     rcx, rcx
0x18000b48f  and     rcx, r9
0x18000b492  test    r8, r8
0x18000b495  jz      short loc_18000B4CB
0x18000b497  mov     edi, ecx
0x18000b499  cmp     rcx, rdi
0x18000b49c  jz      short loc_18000B4AE
0x18000b49e  mov     ebx, 80070216h
0x18000b4a3  mov     edi, ebp
0x18000b4a5  mov     ecx, ebx
0x18000b4a7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b4ac  jmp     short loc_18000B4B7
0x18000b4ae  xor     ecx, ecx
0x18000b4b0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b4b5  mov     ebx, ebp
0x18000b4b7  mov     ecx, ebx
0x18000b4b9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b4be  test    ebx, ebx
0x18000b4c0  js      short loc_18000B4CB
0x18000b4c2  mov     [rsi], edi
0x18000b4c4  jmp     short loc_18000B4D2
0x18000b4c6  mov     ebx, 80070057h
0x18000b4cb  mov     ecx, ebx
0x18000b4cd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b4d2  mov     ecx, ebx
0x18000b4d4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b4d9  mov     eax, ebx
0x18000b4db  add     rsp, 28h
0x18000b4df  pop     rdi
0x18000b4e0  pop     rsi
0x18000b4e1  pop     rbp
0x18000b4e2  pop     rbx
0x18000b4e3  retn
```
