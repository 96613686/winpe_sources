# CTypeLib2::HnameOfStrAIfExistsWithHashVal(char *,ulong,uint *)

- ea: `0x180017468`
- end: `0x18001755f`
- name: `?HnameOfStrAIfExistsWithHashVal@CTypeLib2@@QEAAKPEADKPEAI@Z`
- size: `247`
- prototype: `unsigned int(CTypeLib2 *__hidden this, char *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800173cc`

## callees

- `0x180016630`
- `0x180017468`
- `0x180017570`

## import_xrefs

- `KERNELBASE!CompareStringA` at `0x180017500`
- `KERNELBASE!CompareStringA` at `0x180017500`

## pseudocode

```c
__int64 __fastcall CTypeLib2::HnameOfStrAIfExistsWithHashVal(CTypeLib2 *this, char *a2, ULONG a3, unsigned int *a4)
{
  ULONG v4; // ebp
  unsigned int i; // esi
  __int64 v8; // rdi
  ULONG v10; // eax

  v4 = a3;
  if ( !a3 )
    goto LABEL_2;
  v10 = *((_DWORD *)this + 134);
  if ( !v10 )
  {
    v10 = LHashValOfNameSys((SYSKIND)(*((_WORD *)this + 202) & 3), *((_DWORD *)this + 99), L" ");
    *((_DWORD *)this + 134) = v10;
  }
  if ( ((v4 ^ v10) & 0xFF0000) != 0 )
LABEL_2:
    v4 = LHashValOfNameSysA((SYSKIND)(*((_WORD *)this + 202) & 3), *((_DWORD *)this + 99), a2);
  for ( i = *(_DWORD *)(*((_QWORD *)this + 24) + 4LL * (v4 % *((_DWORD *)this + 115))); i != -1; i = *(_DWORD *)(v8 + 4) )
  {
    v8 = i >= *((_DWORD *)this + 51) ? 0LL : *((_QWORD *)this + 27) + i;
    if ( *(_WORD *)(v8 + 10) == (_WORD)v4
      && CompareStringA(*((_DWORD *)this + 99), 0x30001u, (PCNZCH)(v8 + 12), *(_WORD *)(v8 + 8) & 0x3FF, a2, -1) == 2 )
    {
      break;
    }
  }
  return i;
}

```

## disassembly

```asm
0x180017468  push    rbx
0x18001746a  push    rbp
0x18001746b  push    rsi
0x18001746c  push    rdi
0x18001746d  push    r14
0x18001746f  sub     rsp, 30h
0x180017473  mov     ebp, r8d
0x180017476  mov     r14, rdx
0x180017479  mov     rbx, rcx
0x18001747c  test    r8d, r8d
0x18001747f  jnz     loc_180017518
0x180017485  movzx   ecx, word ptr [rbx+194h]
0x18001748c  mov     r8, r14; szName
0x18001748f  mov     edx, [rbx+18Ch]; lcid
0x180017495  and     ecx, 3; syskind
0x180017498  call    LHashValOfNameSysA
0x18001749d  mov     ebp, eax
0x18001749f  xor     edx, edx
0x1800174a1  mov     eax, ebp
0x1800174a3  div     dword ptr [rbx+1CCh]
0x1800174a9  mov     rax, [rbx+0C0h]
0x1800174b0  mov     esi, [rax+rdx*4]
0x1800174b3  cmp     esi, 0FFFFFFFFh
0x1800174b6  jz      short loc_18001750B
0x1800174b8  cmp     esi, [rbx+0CCh]
0x1800174be  jnb     loc_180017558
0x1800174c4  mov     edi, esi
0x1800174c6  add     rdi, [rbx+0D8h]
0x1800174cd  cmp     [rdi+0Ah], bp
0x1800174d1  jz      short loc_1800174D8
0x1800174d3  mov     esi, [rdi+4]
0x1800174d6  jmp     short loc_1800174B3
0x1800174d8  movzx   r9d, word ptr [rdi+8]
0x1800174dd  lea     r8, [rdi+0Ch]; lpString1
0x1800174e1  mov     ecx, [rbx+18Ch]; Locale
0x1800174e7  and     r9d, 3FFh; cchCount1
0x1800174ee  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800174f6  mov     edx, 30001h; dwCmpFlags
0x1800174fb  mov     [rsp+58h+lpString2], r14; lpString2
0x180017500  call    cs:__imp_CompareStringA
0x180017506  cmp     eax, 2
0x180017509  jnz     short loc_1800174D3
0x18001750b  mov     eax, esi
0x18001750d  add     rsp, 30h
0x180017511  pop     r14
0x180017513  pop     rdi
0x180017514  pop     rsi
0x180017515  pop     rbp
0x180017516  pop     rbx
0x180017517  retn
0x180017518  mov     eax, [rcx+218h]
0x18001751e  test    eax, eax
0x180017520  jz      short loc_180017534
0x180017522  xor     eax, ebp
0x180017524  test    eax, 0FF0000h
0x180017529  jz      loc_18001749F
0x18001752f  jmp     loc_180017485
0x180017534  movzx   ecx, word ptr [rcx+194h]
0x18001753b  lea     r8, szName; " "
0x180017542  mov     edx, [rbx+18Ch]; lcid
0x180017548  and     ecx, 3; syskind
0x18001754b  call    LHashValOfNameSys
0x180017550  mov     [rbx+218h], eax
0x180017556  jmp     short loc_180017522
0x180017558  xor     edi, edi
0x18001755a  jmp     loc_1800174CD
```
