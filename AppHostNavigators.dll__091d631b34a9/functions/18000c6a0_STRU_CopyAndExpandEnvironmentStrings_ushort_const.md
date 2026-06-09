# STRU::CopyAndExpandEnvironmentStrings(ushort const *)

- ea: `0x18000c6a0`
- end: `0x18000c76a`
- name: `?CopyAndExpandEnvironmentStrings@STRU@@QEAAJPEBG@Z`
- size: `202`
- prototype: `signed int __fastcall(STRU *this, LPCWSTR lpSrc)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d6bc`
- `0x180010068`

## callees

- `0x180005770`
- `0x18000c6a0`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000c6d0`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000c731`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000c6d0`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000c731`
- `KERNEL32!GetLastError` at `0x18000c6dc`
- `KERNEL32!GetLastError` at `0x18000c6dc`

## pseudocode

```c
signed int __fastcall STRU::CopyAndExpandEnvironmentStrings(STRU *this, LPCWSTR lpSrc)
{
  unsigned int v4; // r8d
  WCHAR *v5; // rdx
  DWORD v6; // eax
  int v7; // r8d
  signed int result; // eax
  DWORD v9; // eax
  __int64 v10; // rax

  **((_WORD **)this + 1) = 0;
  v4 = *((_DWORD *)this + 1);
  v5 = (WCHAR *)*((_QWORD *)this + 1);
  *((_DWORD *)this + 4) = 0;
  v6 = ExpandEnvironmentStringsW(lpSrc, v5, v4 >> 1);
  if ( !v6 )
    goto LABEL_2;
  if ( v6 <= *((_DWORD *)this + 1) >> 1 )
    goto LABEL_11;
  if ( 2 * (unsigned __int64)v6 > 0xFFFFFFFF )
    return -2147024362;
  if ( !BUFFER::Resize(this, 2 * v6, v7) )
    return -2147024882;
  v9 = ExpandEnvironmentStringsW(lpSrc, *((LPWSTR *)this + 1), *((_DWORD *)this + 1) >> 1);
  if ( v9 && v9 <= *((_DWORD *)this + 1) >> 1 )
  {
LABEL_11:
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(*((_QWORD *)this + 1) + 2 * v10) );
    *((_DWORD *)this + 4) = v10;
    return 0;
  }
  else
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000c6a0  mov     [rsp+arg_0], rbx
0x18000c6a5  mov     [rsp+arg_8], rsi
0x18000c6aa  push    rdi
0x18000c6ab  sub     rsp, 20h
0x18000c6af  mov     r8, [rcx+8]
0x18000c6b3  mov     rdi, rdx
0x18000c6b6  xor     esi, esi
0x18000c6b8  mov     rbx, rcx
0x18000c6bb  mov     [r8], si
0x18000c6bf  mov     r8d, [rcx+4]
0x18000c6c3  mov     rdx, [rcx+8]; lpDst
0x18000c6c7  mov     [rcx+10h], esi
0x18000c6ca  mov     rcx, rdi; lpSrc
0x18000c6cd  shr     r8d, 1; nSize
0x18000c6d0  call    cs:__imp_ExpandEnvironmentStringsW
0x18000c6d6  mov     ecx, eax
0x18000c6d8  test    eax, eax
0x18000c6da  jnz     short loc_18000C6F0
0x18000c6dc  call    cs:__imp_GetLastError
0x18000c6e2  test    eax, eax
0x18000c6e4  jle     short loc_18000C75A
0x18000c6e6  movzx   eax, ax
0x18000c6e9  or      eax, 80070000h
0x18000c6ee  jmp     short loc_18000C75A
0x18000c6f0  mov     eax, [rbx+4]
0x18000c6f3  shr     eax, 1
0x18000c6f5  cmp     ecx, eax
0x18000c6f7  jbe     short loc_18000C744
0x18000c6f9  mov     rdx, rcx
0x18000c6fc  mov     eax, 0FFFFFFFFh
0x18000c701  add     rdx, rdx; unsigned int
0x18000c704  cmp     rdx, rax
0x18000c707  jbe     short loc_18000C710
0x18000c709  mov     eax, 80070216h
0x18000c70e  jmp     short loc_18000C75A
0x18000c710  mov     rcx, rbx; this
0x18000c713  call    ?Resize@BUFFER@@QEAAHKH@Z; BUFFER::Resize(ulong,int)
0x18000c718  test    eax, eax
0x18000c71a  jnz     short loc_18000C723
0x18000c71c  mov     eax, 8007000Eh
0x18000c721  jmp     short loc_18000C75A
0x18000c723  mov     r8d, [rbx+4]
0x18000c727  mov     rcx, rdi; lpSrc
0x18000c72a  mov     rdx, [rbx+8]; lpDst
0x18000c72e  shr     r8d, 1; nSize
0x18000c731  call    cs:__imp_ExpandEnvironmentStringsW
0x18000c737  test    eax, eax
0x18000c739  jz      short loc_18000C6DC
0x18000c73b  mov     ecx, [rbx+4]
0x18000c73e  shr     ecx, 1
0x18000c740  cmp     eax, ecx
0x18000c742  ja      short loc_18000C6DC
0x18000c744  mov     rcx, [rbx+8]
0x18000c748  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c74c  inc     rax
0x18000c74f  cmp     [rcx+rax*2], si
0x18000c753  jnz     short loc_18000C74C
0x18000c755  mov     [rbx+10h], eax
0x18000c758  mov     eax, esi
0x18000c75a  mov     rbx, [rsp+28h+arg_0]
0x18000c75f  mov     rsi, [rsp+28h+arg_8]
0x18000c764  add     rsp, 20h
0x18000c768  pop     rdi
0x18000c769  retn
```
