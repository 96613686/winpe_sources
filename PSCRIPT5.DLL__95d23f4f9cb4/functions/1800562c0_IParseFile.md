# IParseFile

- ea: `0x1800562c0`
- end: `0x180056447`
- name: `IParseFile`
- size: `391`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800564d8`
- `0x1800595d0`

## callees

- `0x180001ee0`
- `0x1800562c0`
- `0x18005b53c`
- `0x18005b5e4`
- `0x18005b740`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x180056308`
- `KERNEL32!GetFullPathNameW` at `0x180056352`
- `KERNEL32!GetFullPathNameW` at `0x180056308`
- `KERNEL32!GetFullPathNameW` at `0x180056352`
- `KERNEL32!HeapAlloc` at `0x18005632d`
- `KERNEL32!HeapAlloc` at `0x18005632d`

## pseudocode

```c
__int64 __fastcall IParseFile(__int64 a1, WCHAR *a2)
{
  DWORD FullPathNameW; // eax
  DWORD v5; // esi
  char *v6; // rax
  _QWORD *v7; // rbx
  DWORD v8; // eax
  __int64 v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rdx
  int v12; // r14d
  __int64 v13; // r8
  unsigned __int8 *v14; // r9
  __int64 v15; // rax
  bool v16; // zf
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int v21; // ebp
  unsigned int v22; // ebx
  LPWSTR FilePart[2]; // [rsp+20h] [rbp-248h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-238h] BYREF

  FilePart[0] = 0;
  FullPathNameW = GetFullPathNameW(a2, 0x104u, Buffer, FilePart);
  v5 = FullPathNameW;
  if ( !FullPathNameW )
    return 4294967294LL;
  v6 = (char *)HeapAlloc(*(HANDLE *)(a1 + 8), 8u, 2 * FullPathNameW + 2 + 16LL);
  v7 = v6;
  if ( !v6 )
    return 4294967294LL;
  *((_QWORD *)v6 + 1) = v6 + 16;
  v8 = GetFullPathNameW(a2, v5 + 1, (LPWSTR)v6 + 8, FilePart);
  if ( !v8 )
    return 4294967294LL;
  if ( v8 > v5 )
    return 4294967294LL;
  *v7 = *(_QWORD *)(a1 + 64);
  *(_QWORD *)(a1 + 64) = v7;
  v9 = PCreateFileObj(a2);
  v10 = v9;
  if ( !v9 )
    return 4294967294LL;
  v11 = *(unsigned __int16 *)(a1 + 524);
  v12 = 0;
  *(_QWORD *)(a1 + 16) = v9;
  v13 = *(unsigned int *)(v9 + 40);
  v14 = *(unsigned __int8 **)(v9 + 16);
  if ( (_DWORD)v13 )
  {
    do
    {
      v15 = *v14++;
      LOWORD(v11) = *((_WORD *)qword_18006B7E0 + (v15 ^ ((unsigned __int64)(unsigned __int16)v11 >> 8)))
                  ^ ((_WORD)v11 << 8);
      v16 = (_DWORD)v13 == 1;
      v13 = (unsigned int)(v13 - 1);
    }
    while ( !v16 );
  }
  *(_WORD *)(a1 + 524) = v11;
  v17 = IParseEntry(a1, v11, v13, v14);
  v21 = -3;
  while ( 1 )
  {
    v22 = v17;
    if ( v17 == -4 )
      break;
    if ( v17 == -3 )
    {
      ++v12;
    }
    else if ( v17 )
    {
      VDeleteFileObj(v10);
      return v22;
    }
    v17 = IParseEntry(a1, v18, v19, v20);
  }
  VDeleteFileObj(v10);
  if ( v12 <= 0 )
    return 0;
  return v21;
}

```

## disassembly

```asm
0x1800562c0  mov     [rsp+arg_10], rbx
0x1800562c5  mov     [rsp+arg_18], rbp
0x1800562ca  push    rsi
0x1800562cb  push    rdi
0x1800562cc  push    r14
0x1800562ce  sub     rsp, 250h
0x1800562d5  mov     rax, cs:__security_cookie
0x1800562dc  xor     rax, rsp
0x1800562df  mov     [rsp+268h+var_28], rax
0x1800562e7  mov     rbp, rdx
0x1800562ea  mov     [rsp+268h+FilePart], 0
0x1800562f3  mov     rdi, rcx
0x1800562f6  lea     r9, [rsp+268h+FilePart]; lpFilePart
0x1800562fb  mov     rcx, rbp; lpFileName
0x1800562fe  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x180056303  mov     edx, 104h; nBufferLength
0x180056308  call    cs:__imp_GetFullPathNameW
0x18005630e  mov     esi, eax
0x180056310  test    eax, eax
0x180056312  jz      loc_18005641A
0x180056318  mov     rcx, [rdi+8]; hHeap
0x18005631c  lea     r8d, ds:2[rax*2]
0x180056324  add     r8, 10h; dwBytes
0x180056328  mov     edx, 8; dwFlags
0x18005632d  call    cs:__imp_HeapAlloc
0x180056333  mov     rbx, rax
0x180056336  test    rax, rax
0x180056339  jz      loc_18005641A
0x18005633f  lea     r8, [rax+10h]; lpBuffer
0x180056343  mov     rcx, rbp; lpFileName
0x180056346  lea     edx, [rsi+1]; nBufferLength
0x180056349  mov     [rax+8], r8
0x18005634d  lea     r9, [rsp+268h+FilePart]; lpFilePart
0x180056352  call    cs:__imp_GetFullPathNameW
0x180056358  test    eax, eax
0x18005635a  jz      loc_18005641A
0x180056360  cmp     eax, esi
0x180056362  ja      loc_18005641A
0x180056368  mov     rax, [rdi+40h]
0x18005636c  mov     rcx, rbp; Src
0x18005636f  mov     [rbx], rax
0x180056372  mov     [rdi+40h], rbx
0x180056376  call    PCreateFileObj
0x18005637b  mov     rsi, rax
0x18005637e  test    rax, rax
0x180056381  jz      loc_18005641A
0x180056387  movzx   edx, word ptr [rdi+20Ch]
0x18005638e  xor     r14d, r14d
0x180056391  mov     [rdi+10h], rax
0x180056395  mov     r8d, [rax+28h]
0x180056399  mov     r9, [rax+10h]
0x18005639d  test    r8d, r8d
0x1800563a0  jz      short loc_1800563C8
0x1800563a2  movzx   eax, byte ptr [r9]
0x1800563a6  inc     r9
0x1800563a9  movzx   ecx, dx
0x1800563ac  shr     rcx, 8
0x1800563b0  xor     rcx, rax
0x1800563b3  shl     dx, 8
0x1800563b7  lea     rax, qword_18006B7E0
0x1800563be  xor     dx, [rax+rcx*2]
0x1800563c2  add     r8d, 0FFFFFFFFh
0x1800563c6  jnz     short loc_1800563A2
0x1800563c8  mov     rcx, rdi
0x1800563cb  mov     [rdi+20Ch], dx
0x1800563d2  call    IParseEntry
0x1800563d7  mov     ebp, 0FFFFFFFDh
0x1800563dc  jmp     short loc_1800563F3
0x1800563de  cmp     ebx, ebp
0x1800563e0  jnz     short loc_1800563E7
0x1800563e2  inc     r14d
0x1800563e5  jmp     short loc_1800563EB
0x1800563e7  test    ebx, ebx
0x1800563e9  jnz     short loc_18005640E
0x1800563eb  mov     rcx, rdi
0x1800563ee  call    IParseEntry
0x1800563f3  mov     ebx, eax
0x1800563f5  cmp     eax, 0FFFFFFFCh
0x1800563f8  jnz     short loc_1800563DE
0x1800563fa  mov     rcx, rsi
0x1800563fd  call    VDeleteFileObj
0x180056402  xor     ecx, ecx
0x180056404  test    r14d, r14d
0x180056407  cmovle  ebp, ecx
0x18005640a  mov     eax, ebp
0x18005640c  jmp     short loc_18005641F
0x18005640e  mov     rcx, rsi
0x180056411  call    VDeleteFileObj
0x180056416  mov     eax, ebx
0x180056418  jmp     short loc_18005641F
0x18005641a  mov     eax, 0FFFFFFFEh
0x18005641f  mov     rcx, [rsp+268h+var_28]
0x180056427  xor     rcx, rsp; StackCookie
0x18005642a  call    __security_check_cookie
0x18005642f  lea     r11, [rsp+268h+var_18]
0x180056437  mov     rbx, [r11+30h]
0x18005643b  mov     rbp, [r11+38h]
0x18005643f  mov     rsp, r11
0x180056442  pop     r14
0x180056444  pop     rdi
0x180056445  pop     rsi
0x180056446  retn
```
