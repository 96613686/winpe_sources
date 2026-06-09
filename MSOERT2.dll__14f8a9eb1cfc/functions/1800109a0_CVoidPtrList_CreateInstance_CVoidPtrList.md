# CVoidPtrList::CreateInstance(CVoidPtrList * *)

- ea: `0x1800109a0`
- end: `0x180010a2c`
- name: `?CreateInstance@CVoidPtrList@@SAJPEAPEAV1@@Z`
- size: `140`
- prototype: `__int64 __fastcall(struct CVoidPtrList **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010ae0`

## callees

- `0x180001f7c`
- `0x1800109a0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180010a07`
- `KERNEL32!InitializeCriticalSection` at `0x180010a07`

## pseudocode

```c
__int64 __fastcall CVoidPtrList::CreateInstance(struct CVoidPtrList **a1)
{
  char *v2; // rbx
  __int64 result; // rax

  v2 = (char *)operator new(0x70u);
  if ( v2 )
  {
    *((_DWORD *)v2 + 6) = 0;
    *(_QWORD *)v2 = &CVoidPtrList::`vftable';
    *((_QWORD *)v2 + 4) = 0;
    *((_DWORD *)v2 + 10) = 1;
    *((_QWORD *)v2 + 6) = 0;
    *((_QWORD *)v2 + 7) = 0;
    v2[104] = 0;
    *((_QWORD *)v2 + 1) = 0;
    *((_QWORD *)v2 + 2) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v2 + 64));
  }
  else
  {
    v2 = 0;
  }
  *a1 = (struct CVoidPtrList *)v2;
  result = 2147942414LL;
  if ( v2 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800109a0  mov     [rsp+arg_0], rbx
0x1800109a5  push    rdi
0x1800109a6  sub     rsp, 20h
0x1800109aa  mov     rdi, rcx
0x1800109ad  mov     ecx, 70h ; 'p'; Size
0x1800109b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800109b7  mov     rbx, rax
0x1800109ba  test    rax, rax
0x1800109bd  jz      short loc_180010A0F
0x1800109bf  lea     rax, ??_7CVoidPtrList@@6B@; const CVoidPtrList::`vftable'
0x1800109c6  mov     dword ptr [rbx+18h], 0
0x1800109cd  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800109d1  mov     [rbx], rax
0x1800109d4  mov     qword ptr [rbx+20h], 0
0x1800109dc  mov     dword ptr [rbx+28h], 1
0x1800109e3  mov     qword ptr [rbx+30h], 0
0x1800109eb  mov     qword ptr [rbx+38h], 0
0x1800109f3  mov     byte ptr [rbx+68h], 0
0x1800109f7  mov     qword ptr [rbx+8], 0
0x1800109ff  mov     qword ptr [rbx+10h], 0
0x180010a07  call    cs:__imp_InitializeCriticalSection
0x180010a0d  jmp     short loc_180010A11
0x180010a0f  xor     ebx, ebx
0x180010a11  xor     ecx, ecx
0x180010a13  mov     [rdi], rbx
0x180010a16  test    rbx, rbx
0x180010a19  mov     eax, 8007000Eh
0x180010a1e  mov     rbx, [rsp+28h+arg_0]
0x180010a23  cmovnz  eax, ecx
0x180010a26  add     rsp, 20h
0x180010a2a  pop     rdi
0x180010a2b  retn
```
