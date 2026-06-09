# XPathNameTable::Add(ushort const *,ushort const * *)

- ea: `0x1800128d0`
- end: `0x180012975`
- name: `?Add@XPathNameTable@@UEAAJPEBGPEAPEBG@Z`
- size: `165`
- prototype: `int(XPathNameTable *__hidden this, const unsigned __int16 *, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007300`
- `0x1800127d0`

## callees

- `0x1800128d0`
- `0x180012ae4`
- `0x180012c1c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800128ee`
- `KERNEL32!GetProcessHeap` at `0x1800128ee`
- `KERNEL32!HeapAlloc` at `0x180012902`
- `KERNEL32!HeapAlloc` at `0x180012902`

## pseudocode

```c
int __fastcall XPathNameTable::Add(XPathNameTable *this, const unsigned __int16 *a2, const unsigned __int16 **a3)
{
  StringTable *v3; // rbp
  HANDLE ProcessHeap; // rax
  LPVOID v8; // rax
  int result; // eax
  int v10; // ebx

  v3 = (XPathNameTable *)((char *)this + 24);
  if ( *((_BYTE *)this + 12) )
  {
    v10 = 0;
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 8u, 0x1000u);
    *((_QWORD *)this + 4) = v8;
    if ( !v8 )
      return -2147024888;
    *((_DWORD *)this + 10) = 512;
    result = StringTable::Add(v3, &qword_1800181B0, (const unsigned __int16 **)this + 2);
    v10 = result;
    if ( result < 0 )
      return result;
    *((_BYTE *)this + 12) = 1;
  }
  HASH_TABLE<unsigned short const,unsigned short const *>::FindKey(v3, a2, a3);
  if ( *a3 )
    return v10;
  result = StringTable::Add(v3, a2, a3);
  v10 = result;
  if ( result >= 0 )
    return v10;
  return result;
}

```

## disassembly

```asm
0x1800128d0  push    rbx
0x1800128d2  push    rbp
0x1800128d3  push    rsi
0x1800128d4  push    rdi
0x1800128d5  push    r14
0x1800128d7  sub     rsp, 20h
0x1800128db  cmp     byte ptr [rcx+0Ch], 0
0x1800128df  lea     rbp, [rcx+18h]
0x1800128e3  mov     rsi, r8
0x1800128e6  mov     r14, rdx
0x1800128e9  mov     rdi, rcx
0x1800128ec  jnz     short loc_18001293E
0x1800128ee  call    cs:__imp_GetProcessHeap
0x1800128f4  mov     edx, 8; dwFlags
0x1800128f9  mov     r8d, 1000h; dwBytes
0x1800128ff  mov     rcx, rax; hHeap
0x180012902  call    cs:__imp_HeapAlloc
0x180012908  mov     [rdi+20h], rax
0x18001290c  test    rax, rax
0x18001290f  jz      short loc_180012937
0x180012911  lea     r8, [rdi+10h]; unsigned __int16 **
0x180012915  mov     dword ptr [rdi+28h], 200h
0x18001291c  lea     rdx, qword_1800181B0; unsigned __int16 *
0x180012923  mov     rcx, rbp; this
0x180012926  call    ?Add@StringTable@@QEAAJPEBGPEAPEBG@Z; StringTable::Add(ushort const *,ushort const * *)
0x18001292b  mov     ebx, eax
0x18001292d  test    eax, eax
0x18001292f  js      short loc_18001296A
0x180012931  mov     byte ptr [rdi+0Ch], 1
0x180012935  jmp     short loc_180012940
0x180012937  mov     eax, 80070008h
0x18001293c  jmp     short loc_18001296A
0x18001293e  xor     ebx, ebx
0x180012940  mov     r8, rsi
0x180012943  mov     rdx, r14
0x180012946  mov     rcx, rbp
0x180012949  call    ?FindKey@?$HASH_TABLE@$$CBGPEBG@@QEAAXPEBGPEAPEBG@Z; HASH_TABLE<ushort const,ushort const *>::FindKey(ushort const *,ushort const * *)
0x18001294e  cmp     qword ptr [rsi], 0
0x180012952  jnz     short loc_180012968
0x180012954  mov     r8, rsi; unsigned __int16 **
0x180012957  mov     rdx, r14; unsigned __int16 *
0x18001295a  mov     rcx, rbp; this
0x18001295d  call    ?Add@StringTable@@QEAAJPEBGPEAPEBG@Z; StringTable::Add(ushort const *,ushort const * *)
0x180012962  mov     ebx, eax
0x180012964  test    eax, eax
0x180012966  js      short loc_18001296A
0x180012968  mov     eax, ebx
0x18001296a  add     rsp, 20h
0x18001296e  pop     r14
0x180012970  pop     rdi
0x180012971  pop     rsi
0x180012972  pop     rbp
0x180012973  pop     rbx
0x180012974  retn
```
