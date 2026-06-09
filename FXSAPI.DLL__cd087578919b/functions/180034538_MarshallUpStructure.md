# MarshallUpStructure

- ea: `0x180034538`
- end: `0x180034663`
- name: `MarshallUpStructure`
- size: `299`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `14`
- callee_count: `6`
- tags: ``

## callers

- `0x18000d680`
- `0x18000da10`
- `0x18000e170`
- `0x18000e830`
- `0x18000f6a0`
- `0x180015690`
- `0x180017c48`
- `0x180018278`
- `0x18001d460`
- `0x18001dd90`
- `0x1800234a0`
- `0x1800238f0`
- `0x18002ad8c`
- `0x180033ea4`

## callees

- `0x18003372c`
- `0x1800339c8`
- `0x180033a24`
- `0x180033c2c`
- `0x180033d48`
- `0x180034538`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18003463a`
- `KERNEL32!SetLastError` at `0x18003463a`

## pseudocode

```c
__int64 __fastcall MarshallUpStructure(
        unsigned __int8 **a1,
        unsigned int *a2,
        struct _FieldInfo *a3,
        unsigned __int64 a4,
        int a5,
        int a6)
{
  unsigned int v6; // r15d
  unsigned int v11; // esi
  unsigned __int64 v12; // r14
  unsigned __int64 v14; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+8h] BYREF

  v6 = 0;
  if ( !a1 || !a3 )
  {
    SetLastError(0x57u);
    return v6;
  }
  v11 = 0;
  v14 = 0;
  v15 = 0;
  if ( (unsigned int)GetShrinkedSize(a3, &v14) )
  {
    v12 = v14;
    if ( v14 != a4 && a6 && !(unsigned int)IsBufferSizeEnough((unsigned int)*a1, (_DWORD)a3, 1, v14, a4, *a2) )
    {
      if ( !(unsigned int)AllocateNewBuffer((_DWORD)a1, (_DWORD)a2, 1, a4, v12, (__int64)&v15) )
        return v6;
      v11 = v15;
    }
    v6 = CustomMarshallUpEntry(*a1, *a1, a3, a4, v12);
    if ( a5 )
      *(_DWORD *)*a1 = a4;
    if ( v11 )
      AdjustPointersInStructuresArray((unsigned int)*a1, 1, (_DWORD)a3, a4, v11);
  }
  return v6;
}

```

## disassembly

```asm
0x180034538  mov     rax, rsp
0x18003453b  mov     [rax+10h], rbx
0x18003453f  mov     [rax+18h], rbp
0x180034543  push    rsi
0x180034544  push    rdi
0x180034545  push    r12
0x180034547  push    r14
0x180034549  push    r15
0x18003454b  sub     rsp, 40h
0x18003454f  xor     r15d, r15d
0x180034552  mov     rbx, r9
0x180034555  mov     rbp, r8
0x180034558  mov     r12, rdx
0x18003455b  mov     rdi, rcx
0x18003455e  test    rcx, rcx
0x180034561  jz      loc_180034635
0x180034567  test    r8, r8
0x18003456a  jz      loc_180034635
0x180034570  xor     esi, esi
0x180034572  mov     [rax-38h], r15
0x180034576  lea     rdx, [rax-38h]
0x18003457a  mov     [rax+8], esi
0x18003457d  mov     rcx, r8
0x180034580  call    GetShrinkedSize
0x180034585  test    eax, eax
0x180034587  jz      loc_180034646
0x18003458d  mov     r14, [rsp+68h+var_38]
0x180034592  cmp     r14, rbx
0x180034595  jz      short loc_1800345ED
0x180034597  cmp     [rsp+68h+arg_28], esi
0x18003459e  jz      short loc_1800345ED
0x1800345a0  mov     eax, [r12]
0x1800345a4  lea     r8d, [r15+1]
0x1800345a8  mov     rcx, [rdi]
0x1800345ab  mov     r9, r14
0x1800345ae  mov     [rsp+68h+var_40], rax
0x1800345b3  mov     rdx, rbp
0x1800345b6  mov     [rsp+68h+var_48], rbx
0x1800345bb  call    IsBufferSizeEnough
0x1800345c0  test    eax, eax
0x1800345c2  jnz     short loc_1800345ED
0x1800345c4  lea     rax, [rsp+68h+arg_0]
0x1800345c9  mov     r9, rbx
0x1800345cc  mov     [rsp+68h+var_40], rax
0x1800345d1  lea     r8d, [r15+1]
0x1800345d5  mov     rdx, r12
0x1800345d8  mov     [rsp+68h+var_48], r14
0x1800345dd  mov     rcx, rdi
0x1800345e0  call    AllocateNewBuffer
0x1800345e5  test    eax, eax
0x1800345e7  jz      short loc_180034646
0x1800345e9  mov     esi, [rsp+68h+arg_0]
0x1800345ed  mov     rdx, [rdi]; unsigned __int8 *
0x1800345f0  mov     r9, rbx; unsigned __int64
0x1800345f3  mov     rcx, rdx; Src
0x1800345f6  mov     [rsp+68h+var_48], r14; unsigned __int64
0x1800345fb  mov     r8, rbp; struct _FieldInfo *
0x1800345fe  call    ?CustomMarshallUpEntry@@YAHPEAE0PEAU_FieldInfo@@_K2@Z; CustomMarshallUpEntry(uchar *,uchar *,_FieldInfo *,unsigned __int64,unsigned __int64)
0x180034603  cmp     [rsp+68h+arg_20], 0
0x18003460b  mov     r15d, eax
0x18003460e  jz      short loc_180034615
0x180034610  mov     rcx, [rdi]
0x180034613  mov     [rcx], ebx
0x180034615  test    esi, esi
0x180034617  jz      short loc_180034646
0x180034619  mov     ecx, esi
0x18003461b  mov     r9, rbx
0x18003461e  mov     [rsp+68h+var_48], rcx
0x180034623  mov     r8, rbp
0x180034626  mov     rcx, [rdi]
0x180034629  mov     edx, 1
0x18003462e  call    AdjustPointersInStructuresArray
0x180034633  jmp     short loc_180034646
0x180034635  mov     ecx, 57h ; 'W'; dwErrCode
0x18003463a  call    cs:__imp_SetLastError
0x180034641  nop     dword ptr [rax+rax+00h]
0x180034646  lea     r11, [rsp+68h+var_28]
0x18003464b  mov     eax, r15d
0x18003464e  mov     rbx, [r11+38h]
0x180034652  mov     rbp, [r11+40h]
0x180034656  mov     rsp, r11
0x180034659  pop     r15
0x18003465b  pop     r14
0x18003465d  pop     r12
0x18003465f  pop     rdi
0x180034660  pop     rsi
0x180034661  retn
```
