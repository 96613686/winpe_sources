# __crtCompareStringW

- ea: `0x1801f7024`
- end: `0x1801f70f1`
- name: `__crtCompareStringW`
- size: `205`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpLocaleName@<rcx>, DWORD dwCmpFlags@<edx>, wchar_t *Source@<r8>, wchar_t *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1801f69b0`

## callees

- `0x1801f7024`
- `0x18020c790`

## import_xrefs

- `KERNEL32!CompareStringEx` at `0x1801f70b7`
- `KERNEL32!CompareStringEx` at `0x1801f70b7`

## pseudocode

```c
int __fastcall _crtCompareStringW(
        LPCWSTR lpLocaleName,
        DWORD dwCmpFlags,
        wchar_t *Source,
        int a4,
        wchar_t *Sourcea,
        int a6)
{
  int v6; // ebx
  int cchCount2; // eax
  int result; // eax
  int v12; // ebx

  v6 = a4;
  if ( a4 > 0 )
  {
    _mm_lfence();
    v6 = wcsnlen(Source, a4);
  }
  cchCount2 = a6;
  if ( a6 > 0 )
  {
    _mm_lfence();
    cchCount2 = wcsnlen(Sourcea, a6);
  }
  if ( v6 && cchCount2 )
    return CompareStringEx(lpLocaleName, dwCmpFlags, Source, v6, Sourcea, cchCount2, 0, 0, 0);
  v12 = v6 - cchCount2;
  result = ((v12 >> 31) & 0xFFFFFFFE) + 3;
  if ( !v12 )
    return 2;
  return result;
}

```

## disassembly

```asm
0x1801f7024  mov     rax, rsp
0x1801f7027  mov     [rax+8], rbx
0x1801f702b  mov     [rax+10h], rbp
0x1801f702f  mov     [rax+18h], rsi
0x1801f7033  mov     [rax+20h], rdi
0x1801f7037  push    r14
0x1801f7039  sub     rsp, 50h
0x1801f703d  movsxd  rbx, r9d
0x1801f7040  mov     rsi, r8
0x1801f7043  mov     ebp, edx
0x1801f7045  mov     r14, rcx
0x1801f7048  test    r9d, r9d
0x1801f704b  jle     short loc_1801F705E
0x1801f704d  lfence
0x1801f7050  mov     rdx, rbx; MaxCount
0x1801f7053  mov     rcx, r8; Source
0x1801f7056  call    wcsnlen
0x1801f705b  mov     rbx, rax
0x1801f705e  movsxd  rax, [rsp+58h+arg_28]
0x1801f7066  mov     rdi, [rsp+58h+Source]
0x1801f706e  test    eax, eax
0x1801f7070  jle     short loc_1801F7080
0x1801f7072  lfence
0x1801f7075  mov     rdx, rax; MaxCount
0x1801f7078  mov     rcx, rdi; Source
0x1801f707b  call    wcsnlen
0x1801f7080  test    ebx, ebx
0x1801f7082  jz      short loc_1801F70BF
0x1801f7084  test    eax, eax
0x1801f7086  jz      short loc_1801F70BF
0x1801f7088  mov     [rsp+58h+lParam], 0; lParam
0x1801f7091  mov     r9d, ebx; cchCount1
0x1801f7094  mov     [rsp+58h+lpReserved], 0; lpReserved
0x1801f709d  mov     r8, rsi; lpString1
0x1801f70a0  mov     [rsp+58h+lpVersionInformation], 0; lpVersionInformation
0x1801f70a9  mov     edx, ebp; dwCmpFlags
0x1801f70ab  mov     [rsp+58h+cchCount2], eax; cchCount2
0x1801f70af  mov     rcx, r14; lpLocaleName
0x1801f70b2  mov     [rsp+58h+lpString2], rdi; lpString2
0x1801f70b7  call    cs:__imp_CompareStringEx
0x1801f70bd  jmp     short loc_1801F70D6
0x1801f70bf  sub     ebx, eax
0x1801f70c1  mov     ecx, 2
0x1801f70c6  mov     eax, ebx
0x1801f70c8  sar     eax, 1Fh
0x1801f70cb  and     eax, 0FFFFFFFEh
0x1801f70ce  add     eax, 3
0x1801f70d1  test    ebx, ebx
0x1801f70d3  cmovz   eax, ecx
0x1801f70d6  mov     rbx, [rsp+58h+arg_0]
0x1801f70db  mov     rbp, [rsp+58h+arg_8]
0x1801f70e0  mov     rsi, [rsp+58h+arg_10]
0x1801f70e5  mov     rdi, [rsp+58h+arg_18]
0x1801f70ea  add     rsp, 50h
0x1801f70ee  pop     r14
0x1801f70f0  retn
```
