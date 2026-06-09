# CGPOInfoList::Compare(ushort const *,ushort const *)

- ea: `0x18000e834`
- end: `0x18000e8e1`
- name: `?Compare@CGPOInfoList@@QEAAHPEBG0@Z`
- size: `173`
- prototype: `__int64 __fastcall(LPCWSTR *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003370`
- `0x180006c54`
- `0x18000f8bc`
- `0x1800101fc`

## callees

- `0x18000e834`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000e881`
- `KERNEL32!lstrcmpiW` at `0x18000e89a`
- `KERNEL32!lstrcmpiW` at `0x18000e881`
- `KERNEL32!lstrcmpiW` at `0x18000e89a`

## pseudocode

```c
__int64 __fastcall CGPOInfoList::Compare(LPCWSTR *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v5; // ecx
  int v7; // r14d
  int v8; // r15d
  LPCWSTR *v9; // rsi
  unsigned int v10; // edi
  int v11; // ebp
  int v12; // eax
  int v13; // ecx
  int v14; // eax

  v5 = -1;
  v7 = -1;
  v8 = 0;
  v9 = (LPCWSTR *)this[1];
  v10 = 1;
  this[3] = this[2];
  while ( 1 )
  {
    this[2] = (LPCWSTR)v9;
    v11 = v5;
    if ( v9 == this )
      v9 = 0;
    if ( !v9 )
      break;
    v12 = lstrcmpiW(v9[2], a2);
    v13 = v8;
    if ( v12 )
      v13 = v7;
    v7 = v13;
    v14 = lstrcmpiW(v9[2], a3);
    v5 = v8;
    if ( v14 )
      v5 = v11;
    ++v8;
    v9 = (LPCWSTR *)*((_QWORD *)this[2] + 1);
  }
  this[2] = this[3];
  if ( v7 == v5 )
  {
    return 0;
  }
  else if ( v7 < v5 )
  {
    return (unsigned int)-1;
  }
  return v10;
}

```

## disassembly

```asm
0x18000e834  push    rbx
0x18000e836  push    rbp
0x18000e837  push    rsi
0x18000e838  push    rdi
0x18000e839  push    r12
0x18000e83b  push    r13
0x18000e83d  push    r14
0x18000e83f  push    r15
0x18000e841  sub     rsp, 28h
0x18000e845  mov     rbx, rcx
0x18000e848  mov     r12, r8
0x18000e84b  or      ecx, 0FFFFFFFFh
0x18000e84e  mov     r13, rdx
0x18000e851  mov     r14d, ecx
0x18000e854  xor     r15d, r15d
0x18000e857  mov     rax, [rbx+10h]
0x18000e85b  mov     rsi, [rbx+8]
0x18000e85f  lea     edi, [rcx+2]
0x18000e862  mov     [rbx+18h], rax
0x18000e866  xor     eax, eax
0x18000e868  mov     [rbx+10h], rsi
0x18000e86c  cmp     rsi, rbx
0x18000e86f  mov     ebp, ecx
0x18000e871  cmovz   rsi, rax
0x18000e875  test    rsi, rsi
0x18000e878  jz      short loc_18000E8B5
0x18000e87a  mov     rcx, [rsi+10h]; lpString1
0x18000e87e  mov     rdx, r13; lpString2
0x18000e881  call    cs:__imp_lstrcmpiW
0x18000e887  mov     ecx, r15d
0x18000e88a  mov     rdx, r12; lpString2
0x18000e88d  test    eax, eax
0x18000e88f  cmovnz  ecx, r14d
0x18000e893  mov     r14d, ecx
0x18000e896  mov     rcx, [rsi+10h]; lpString1
0x18000e89a  call    cs:__imp_lstrcmpiW
0x18000e8a0  test    eax, eax
0x18000e8a2  mov     ecx, r15d
0x18000e8a5  mov     rax, [rbx+10h]
0x18000e8a9  cmovnz  ecx, ebp
0x18000e8ac  add     r15d, edi
0x18000e8af  mov     rsi, [rax+8]
0x18000e8b3  jmp     short loc_18000E866
0x18000e8b5  mov     rax, [rbx+18h]
0x18000e8b9  mov     [rbx+10h], rax
0x18000e8bd  cmp     r14d, ebp
0x18000e8c0  jnz     short loc_18000E8C6
0x18000e8c2  xor     edi, edi
0x18000e8c4  jmp     short loc_18000E8CE
0x18000e8c6  mov     eax, 0FFFFFFFFh
0x18000e8cb  cmovl   edi, eax
0x18000e8ce  mov     eax, edi
0x18000e8d0  add     rsp, 28h
0x18000e8d4  pop     r15
0x18000e8d6  pop     r14
0x18000e8d8  pop     r13
0x18000e8da  pop     r12
0x18000e8dc  pop     rdi
0x18000e8dd  pop     rsi
0x18000e8de  pop     rbp
0x18000e8df  pop     rbx
0x18000e8e0  retn
```
