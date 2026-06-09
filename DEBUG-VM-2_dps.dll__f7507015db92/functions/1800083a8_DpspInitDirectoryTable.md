# DpspInitDirectoryTable

- ea: `0x1800083a8`
- end: `0x18000846e`
- name: `DpspInitDirectoryTable`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015b84`

## callees

- `0x1800013a0`
- `0x1800083a8`
- `0x180009090`

## string_xrefs

- `0x1800083de`: `DpspInitDirectoryTable`

## pseudocode

```c
__int64 __fastcall DpspInitDirectoryTable(__int64 a1, unsigned int a2, int a3)
{
  unsigned int v6; // ebx
  int v7; // r8d
  __int64 v8; // rax
  unsigned int i; // edx
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  int Args; // [rsp+20h] [rbp-18h]

  if ( !a1 )
  {
    v6 = -2147024809;
    Args = 87;
    v7 = 982;
LABEL_3:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
      (__int64)L"DpspInitDirectoryTable",
      v7,
      (const wchar_t *)L"Error = %d",
      Args);
    return v6;
  }
  if ( (a2 & 0xFFFFFFF) != a2 )
  {
    v6 = -2147024362;
    Args = 534;
    v7 = 992;
    goto LABEL_3;
  }
  v8 = WdipAlloc(16 * a2);
  *(_QWORD *)a1 = v8;
  if ( !v8 )
  {
    v6 = -2147024882;
    Args = 14;
    v7 = 996;
    goto LABEL_3;
  }
  for ( i = 0; i < a2; *v11 = v11 )
  {
    v10 = i++;
    v11 = (_QWORD *)(v8 + 16 * v10);
    v11[1] = v11;
  }
  *(_DWORD *)(a1 + 8) = a2;
  v6 = 0;
  *(_DWORD *)(a1 + 12) = a3;
  return v6;
}

```

## disassembly

```asm
0x1800083a8  mov     [rsp+arg_0], rbx
0x1800083ad  mov     [rsp+arg_8], rsi
0x1800083b2  push    rdi
0x1800083b3  sub     rsp, 30h
0x1800083b7  mov     esi, r8d
0x1800083ba  mov     ebx, edx
0x1800083bc  mov     rdi, rcx
0x1800083bf  test    rcx, rcx
0x1800083c2  jnz     short loc_1800083F3
0x1800083c4  mov     ebx, 80070057h
0x1800083c9  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x1800083d1  mov     r8d, 3D6h; int
0x1800083d7  lea     r9, aErrorD; "Error = %d"
0x1800083de  lea     rdx, aDpspinitdirect; "DpspInitDirectoryTable"
0x1800083e5  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800083ec  call    WdipTraceError
0x1800083f1  jmp     short loc_18000845C
0x1800083f3  mov     ecx, ebx
0x1800083f5  shl     ecx, 4
0x1800083f8  mov     eax, ecx
0x1800083fa  shr     eax, 4
0x1800083fd  cmp     eax, ebx
0x1800083ff  jz      short loc_180008416
0x180008401  mov     ebx, 80070216h
0x180008406  mov     dword ptr [rsp+38h+Args], 216h
0x18000840e  mov     r8d, 3E0h
0x180008414  jmp     short loc_1800083D7
0x180008416  call    WdipAlloc
0x18000841b  mov     [rdi], rax
0x18000841e  test    rax, rax
0x180008421  jnz     short loc_180008438
0x180008423  mov     ebx, 8007000Eh
0x180008428  mov     dword ptr [rsp+38h+Args], 0Eh
0x180008430  mov     r8d, 3E4h
0x180008436  jmp     short loc_1800083D7
0x180008438  xor     edx, edx
0x18000843a  test    ebx, ebx
0x18000843c  jz      short loc_180008454
0x18000843e  mov     ecx, edx
0x180008440  inc     edx
0x180008442  shl     rcx, 4
0x180008446  add     rcx, rax
0x180008449  mov     [rcx+8], rcx
0x18000844d  mov     [rcx], rcx
0x180008450  cmp     edx, ebx
0x180008452  jb      short loc_18000843E
0x180008454  mov     [rdi+8], ebx
0x180008457  xor     ebx, ebx
0x180008459  mov     [rdi+0Ch], esi
0x18000845c  mov     rsi, [rsp+38h+arg_8]
0x180008461  mov     eax, ebx
0x180008463  mov     rbx, [rsp+38h+arg_0]
0x180008468  add     rsp, 30h
0x18000846c  pop     rdi
0x18000846d  retn
```
