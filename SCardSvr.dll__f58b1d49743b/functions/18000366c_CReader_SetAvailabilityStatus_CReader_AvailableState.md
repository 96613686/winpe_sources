# CReader::SetAvailabilityStatus(CReader::AvailableState)

- ea: `0x18000366c`
- end: `0x180003716`
- name: `?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x180001950`
- `0x180003ff0`
- `0x18000ecb0`
- `0x18000f1c0`
- `0x180018d4c`
- `0x18002a970`
- `0x18002ab4c`
- `0x18002d928`
- `0x180032e80`
- `0x180032ed0`
- `0x180032f20`
- `0x180032f70`
- `0x180032fc0`
- `0x180033010`
- `0x18003611a`

## callees

- `0x18000366c`
- `0x1800037b8`
- `0x180037010`

## import_xrefs

- `SCardBi!?Instance@SmartCardBiManager@@SAPEAV1@XZ` at `0x180003688`
- `SCardBi!?Instance@SmartCardBiManager@@SAPEAV1@XZ` at `0x180003688`

## pseudocode

```c
void __fastcall CReader::SetAvailabilityStatus(__int64 a1, int a2)
{
  int v2; // esi
  __int64 v5; // rcx
  const WCHAR *v6; // rax
  const WCHAR *v7; // r8
  __int64 v8; // r9

  v2 = *(_DWORD *)(a1 + 192);
  if ( v2 != a2 )
  {
    v5 = SmartCardBiManager::Instance();
    if ( v5 && v2 == 1 && a2 == 5 )
    {
      if ( *(_DWORD *)(a1 + 28) )
      {
        v7 = *(const WCHAR **)(a1 + 16);
        v6 = v7;
      }
      else
      {
        v6 = &Data;
        v7 = &Data;
      }
      v8 = -1;
      do
        ++v8;
      while ( v6[v8] );
      (*(void (__fastcall **)(__int64, __int64, const WCHAR *, _QWORD))(*(_QWORD *)v5 + 8LL))(
        v5,
        5,
        v7,
        (unsigned int)(2 * v8 + 2));
      *(_DWORD *)(a1 + 192) = 5;
    }
    else
    {
      *(_DWORD *)(a1 + 192) = a2;
      if ( a2 > 5 )
      {
LABEL_13:
        CMultiEvent::Signal((CMultiEvent *)(a1 + 416));
        return;
      }
    }
    *(_QWORD *)(a1 + 216) = 0;
    *(_DWORD *)(a1 + 224) = 0;
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x18000366c  push    rbx
0x18000366e  push    rbp
0x18000366f  push    rsi
0x180003670  push    rdi
0x180003671  sub     rsp, 38h
0x180003675  mov     esi, [rcx+0C0h]
0x18000367b  mov     edi, edx
0x18000367d  mov     rbx, rcx
0x180003680  cmp     esi, edx
0x180003682  jz      loc_18000370D
0x180003688  call    cs:__imp_?Instance@SmartCardBiManager@@SAPEAV1@XZ; SmartCardBiManager::Instance(void)
0x18000368e  xor     ebp, ebp
0x180003690  mov     rcx, rax
0x180003693  test    rax, rax
0x180003696  jz      short loc_1800036E9
0x180003698  cmp     esi, 1
0x18000369b  jnz     short loc_1800036E9
0x18000369d  cmp     edi, 5
0x1800036a0  jnz     short loc_1800036E9
0x1800036a2  cmp     [rbx+1Ch], ebp
0x1800036a5  ja      short loc_1800036B3
0x1800036a7  lea     rax, Data
0x1800036ae  mov     r8, rax
0x1800036b1  jmp     short loc_1800036BA
0x1800036b3  mov     r8, [rbx+10h]
0x1800036b7  mov     rax, r8
0x1800036ba  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800036be  inc     r9
0x1800036c1  cmp     [rax+r9*2], bp
0x1800036c6  jnz     short loc_1800036BE
0x1800036c8  mov     rax, [rcx]
0x1800036cb  lea     r9d, ds:2[r9*2]
0x1800036d3  mov     edx, 5
0x1800036d8  mov     rax, [rax+8]
0x1800036dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036e1  mov     [rbx+0C0h], edi
0x1800036e7  jmp     short loc_1800036F4
0x1800036e9  mov     [rbx+0C0h], edi
0x1800036ef  cmp     edi, 5
0x1800036f2  jg      short loc_180003701
0x1800036f4  mov     [rbx+0D8h], rbp
0x1800036fb  mov     [rbx+0E0h], ebp
0x180003701  lea     rcx, [rbx+1A0h]; this
0x180003708  call    ?Signal@CMultiEvent@@QEAAXXZ; CMultiEvent::Signal(void)
0x18000370d  add     rsp, 38h
0x180003711  pop     rdi
0x180003712  pop     rsi
0x180003713  pop     rbp
0x180003714  pop     rbx
0x180003715  retn
```
