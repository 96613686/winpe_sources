# IUnknownList_CreateInstance(IUnknownList * *)

- ea: `0x180011040`
- end: `0x1800110af`
- name: `?IUnknownList_CreateInstance@@YAJPEAPEAUIUnknownList@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(struct IUnknownList **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001f7c`
- `0x180010ae0`
- `0x180010f04`
- `0x180011040`

## pseudocode

```c
__int64 __fastcall IUnknownList_CreateInstance(struct IUnknownList **a1)
{
  void *v2; // rdi
  unsigned int v3; // edx
  int Instance; // esi
  __int64 result; // rax

  v2 = operator new(0x18u);
  if ( v2 )
  {
    *((_QWORD *)v2 + 1) = 0;
    *(_QWORD *)v2 = &CUnknownList::`vftable';
    *((_DWORD *)v2 + 4) = 1;
  }
  else
  {
    v2 = 0;
  }
  Instance = IVoidPtrList_CreateInstance((struct IVoidPtrList **)v2 + 1);
  if ( !*((_QWORD *)v2 + 1) )
  {
    CUnknownList::`scalar deleting destructor'((CUnknownList *)v2, v3);
    v2 = 0;
  }
  result = (unsigned int)Instance;
  if ( Instance < 0 )
    v2 = 0;
  *a1 = (struct IUnknownList *)v2;
  return result;
}

```

## disassembly

```asm
0x180011040  push    rbx
0x180011042  push    rsi
0x180011043  push    rdi
0x180011044  push    r14
0x180011046  sub     rsp, 28h
0x18001104a  mov     r14, rcx
0x18001104d  mov     ecx, 18h; Size
0x180011052  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011057  mov     rdi, rax
0x18001105a  test    rax, rax
0x18001105d  jz      short loc_18001107A
0x18001105f  lea     rax, ??_7CUnknownList@@6B@; const CUnknownList::`vftable'
0x180011066  mov     qword ptr [rdi+8], 0
0x18001106e  mov     [rdi], rax
0x180011071  mov     dword ptr [rdi+10h], 1
0x180011078  jmp     short loc_18001107C
0x18001107a  xor     edi, edi
0x18001107c  lea     rcx, [rdi+8]; struct IVoidPtrList **
0x180011080  call    ?IVoidPtrList_CreateInstance@@YAJPEAPEAUIVoidPtrList@@@Z; IVoidPtrList_CreateInstance(IVoidPtrList * *)
0x180011085  cmp     qword ptr [rdi+8], 0
0x18001108a  mov     esi, eax
0x18001108c  jnz     short loc_180011098
0x18001108e  mov     rcx, rdi; this
0x180011091  call    ??_GCUnknownList@@QEAAPEAXI@Z; CUnknownList::`scalar deleting destructor'(uint)
0x180011096  xor     edi, edi
0x180011098  xor     ecx, ecx
0x18001109a  mov     eax, esi
0x18001109c  test    esi, esi
0x18001109e  cmovs   rdi, rcx
0x1800110a2  mov     [r14], rdi
0x1800110a5  add     rsp, 28h
0x1800110a9  pop     r14
0x1800110ab  pop     rdi
0x1800110ac  pop     rsi
0x1800110ad  pop     rbx
0x1800110ae  retn
```
