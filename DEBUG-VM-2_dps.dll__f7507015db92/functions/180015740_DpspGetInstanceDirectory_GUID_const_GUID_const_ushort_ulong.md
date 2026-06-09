# DpspGetInstanceDirectory(_GUID const *,_GUID const *,ushort *,ulong)

- ea: `0x180015740`
- end: `0x180015853`
- name: `?DpspGetInstanceDirectory@@YAJPEBU_GUID@@0PEAGK@Z`
- size: `275`
- prototype: `int(const struct _GUID *, const struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800082a8`
- `0x18001585c`

## callees

- `0x180008ed0`
- `0x180009090`
- `0x18000c93c`
- `0x180015740`

## string_xrefs

- `0x18001582d`: `DpspGetInstanceDirectory`

## pseudocode

```c
__int64 __fastcall DpspGetInstanceDirectory(const struct _GUID *a1, const struct _GUID *a2, unsigned __int16 *a3)
{
  __int64 v3; // rbx
  unsigned int v7; // ebx
  int v8; // r8d
  __int64 v9; // r14
  int v10; // eax
  int v11; // eax
  int Args; // [rsp+20h] [rbp-58h]

  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)g_WdiDir + v3) );
  if ( !a1 )
  {
    v7 = -2147024809;
    Args = 87;
    v8 = 324;
LABEL_11:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
      (__int64)L"DpspGetInstanceDirectory",
      v8,
      (const wchar_t *)L"Error = %d",
      Args);
    return v7;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Args = 87;
    v8 = 325;
    goto LABEL_11;
  }
  memcpy_s(a3, 0x208u, g_WdiDir, 2 * v3 + 2);
  v9 = v3 + 1;
  a3[v3] = 92;
  v10 = WdipGuidToString(a1, &a3[v3 + 1], 260 - (v3 + 1));
  v7 = v10;
  if ( v10 < 0 )
  {
    v8 = 337;
    Args = (unsigned __int16)v10;
    goto LABEL_11;
  }
  a3[v9 + 38] = 92;
  v11 = WdipGuidToString(a2, &a3[v9 + 39], 260 - (v9 + 39));
  v7 = v11;
  if ( v11 < 0 )
  {
    v8 = 347;
    Args = (unsigned __int16)v11;
    goto LABEL_11;
  }
  return v7;
}

```

## disassembly

```asm
0x180015740  push    rbx
0x180015742  push    rbp
0x180015743  push    rsi
0x180015744  push    rdi
0x180015745  push    r12
0x180015747  push    r13
0x180015749  push    r14
0x18001574b  push    r15
0x18001574d  sub     rsp, 38h
0x180015751  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015755  mov     rdi, r8
0x180015758  mov     r8, cs:g_WdiDir; Source
0x18001575f  xor     r12d, r12d
0x180015762  mov     rbp, rdx
0x180015765  mov     r15, rcx
0x180015768  inc     rbx
0x18001576b  cmp     [r8+rbx*2], r12w
0x180015770  jnz     short loc_180015768
0x180015772  test    r15, r15
0x180015775  jnz     short loc_18001578F
0x180015777  mov     ebx, 80070057h
0x18001577c  mov     dword ptr [rsp+78h+Args], 57h ; 'W'
0x180015784  mov     r8d, 144h
0x18001578a  jmp     loc_180015826
0x18001578f  test    rbp, rbp
0x180015792  jnz     short loc_1800157A9
0x180015794  mov     ebx, 80070057h
0x180015799  mov     dword ptr [rsp+78h+Args], 57h ; 'W'
0x1800157a1  mov     r8d, 145h
0x1800157a7  jmp     short loc_180015826
0x1800157a9  lea     r9, ds:2[rbx*2]; SourceSize
0x1800157b1  mov     edx, 208h; DestinationSize
0x1800157b6  mov     rcx, rdi; Destination
0x1800157b9  call    memcpy_s
0x1800157be  lea     r14, [rbx+1]
0x1800157c2  mov     esi, 104h
0x1800157c7  mov     r8d, esi
0x1800157ca  lea     rdx, [rdi+r14*2]
0x1800157ce  mov     r13d, 5Ch ; '\'
0x1800157d4  sub     r8, r14
0x1800157d7  mov     rcx, r15
0x1800157da  mov     [rdi+rbx*2], r13w
0x1800157df  call    WdipGuidToString
0x1800157e4  mov     ebx, eax
0x1800157e6  test    eax, eax
0x1800157e8  jns     short loc_1800157F7
0x1800157ea  movzx   ecx, ax
0x1800157ed  lea     r8d, [rsi+4Dh]
0x1800157f1  mov     dword ptr [rsp+78h+Args], ecx
0x1800157f5  jmp     short loc_180015826
0x1800157f7  lea     rax, [r14+27h]
0x1800157fb  mov     [rdi+r14*2+4Ch], r13w
0x180015801  sub     rsi, rax
0x180015804  lea     rdx, [rdi+rax*2]
0x180015808  mov     r8, rsi
0x18001580b  mov     rcx, rbp
0x18001580e  call    WdipGuidToString
0x180015813  mov     ebx, eax
0x180015815  test    eax, eax
0x180015817  jns     short loc_180015840
0x180015819  movzx   eax, ax
0x18001581c  mov     r8d, 15Bh; int
0x180015822  mov     dword ptr [rsp+78h+Args], eax; Args
0x180015826  lea     r9, aErrorD; "Error = %d"
0x18001582d  lea     rdx, aDpspgetinstanc; "DpspGetInstanceDirectory"
0x180015834  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18001583b  call    WdipTraceError
0x180015840  mov     eax, ebx
0x180015842  add     rsp, 38h
0x180015846  pop     r15
0x180015848  pop     r14
0x18001584a  pop     r13
0x18001584c  pop     r12
0x18001584e  pop     rdi
0x18001584f  pop     rsi
0x180015850  pop     rbp
0x180015851  pop     rbx
0x180015852  retn
```
