# CPropertyCache::addproperty(ushort *,ulong,ulong,_iistype *)

- ea: `0x1800109ec`
- end: `0x180010a6e`
- name: `?addproperty@CPropertyCache@@QEAAJPEAGKKPEAU_iistype@@@Z`
- size: `130`
- prototype: `int(CPropertyCache *__hidden this, unsigned __int16 *, unsigned int, unsigned int, struct _iistype *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800032a0`
- `0x1800035a0`
- `0x180006f60`
- `0x180007300`
- `0x1800103bc`
- `0x1800110bc`

## callees

- `0x1800109ec`
- `0x18001d66a`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180010a53`
- `msvcrt!wcscpy_s` at `0x180010a53`
- `ACTIVEDS!__imp_ReallocADsMem` at `0x180010a0c`
- `ACTIVEDS!__imp_ReallocADsMem` at `0x180010a0c`

## pseudocode

```c
__int64 __fastcall CPropertyCache::addproperty(CPropertyCache *this, unsigned __int16 *a2)
{
  void *v2; // rbx
  char *v5; // rax
  unsigned int v6; // esi
  char *v7; // rbx

  v2 = (void *)*((_QWORD *)this + 4);
  v5 = (char *)ReallocADsMem(v2, *((_DWORD *)this + 11), *((_DWORD *)this + 11) + 544);
  *((_QWORD *)this + 4) = v5;
  if ( v5 )
  {
    v6 = 0;
    v7 = &v5[544 * *((unsigned int *)this + 2)];
    memset_0(v7, 0, 0x220u);
    wcscpy_s((wchar_t *)v7, 0x104u, a2);
    ++*((_DWORD *)this + 2);
    *((_DWORD *)this + 11) += 544;
  }
  else
  {
    *((_QWORD *)this + 4) = v2;
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x1800109ec  push    rbx
0x1800109ee  push    rbp
0x1800109ef  push    rsi
0x1800109f0  push    rdi
0x1800109f1  sub     rsp, 28h
0x1800109f5  mov     rbx, [rcx+20h]
0x1800109f9  mov     rbp, rdx
0x1800109fc  mov     edx, [rcx+2Ch]; cbOld
0x1800109ff  mov     rdi, rcx
0x180010a02  mov     rcx, rbx; pOldMem
0x180010a05  lea     r8d, [rdx+220h]; cbNew
0x180010a0c  call    cs:__imp_ReallocADsMem
0x180010a12  mov     [rdi+20h], rax
0x180010a16  mov     r8, rax
0x180010a19  test    rax, rax
0x180010a1c  jnz     short loc_180010A29
0x180010a1e  mov     [rdi+20h], rbx
0x180010a22  mov     esi, 8007000Eh
0x180010a27  jmp     short loc_180010A63
0x180010a29  mov     eax, [rdi+8]
0x180010a2c  xor     edx, edx; Val
0x180010a2e  imul    rbx, rax, 220h
0x180010a35  xor     esi, esi
0x180010a37  add     rbx, r8
0x180010a3a  mov     r8d, 220h; Size
0x180010a40  mov     rcx, rbx; void *
0x180010a43  call    memset_0
0x180010a48  mov     r8, rbp; Source
0x180010a4b  mov     edx, 104h; SizeInWords
0x180010a50  mov     rcx, rbx; Destination
0x180010a53  call    cs:__imp_wcscpy_s
0x180010a59  inc     dword ptr [rdi+8]
0x180010a5c  add     dword ptr [rdi+2Ch], 220h
0x180010a63  mov     eax, esi
0x180010a65  add     rsp, 28h
0x180010a69  pop     rdi
0x180010a6a  pop     rsi
0x180010a6b  pop     rbp
0x180010a6c  pop     rbx
0x180010a6d  retn
```
