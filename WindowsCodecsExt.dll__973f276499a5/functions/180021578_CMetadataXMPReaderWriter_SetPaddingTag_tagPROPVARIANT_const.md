# CMetadataXMPReaderWriter::SetPaddingTag(tagPROPVARIANT const *)

- ea: `0x180021578`
- end: `0x1800215e2`
- name: `?SetPaddingTag@CMetadataXMPReaderWriter@@IEAAJPEBUtagPROPVARIANT@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001440`
- `0x180021430`

## callees

- `0x1800171c4`
- `0x180021578`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::SetPaddingTag(
        CMetadataXMPReaderWriter *this,
        const struct tagPROPVARIANT *a2)
{
  unsigned int v2; // ebx

  if ( a2->vt == 19 )
  {
    if ( a2->lVal <= 0x8000u )
    {
      v2 = 0;
      *((_DWORD *)this + 65) = 1;
      *((_DWORD *)this + 64) = a2->lVal;
      (*(void (__fastcall **)(CMetadataXMPReaderWriter *, __int64))(*(_QWORD *)this + 128LL))(this, 1);
      return v2;
    }
    v2 = -2003292411;
  }
  else
  {
    v2 = -2003292274;
  }
  if ( g_doStackCaptures )
    DoStackCapture(v2);
  return v2;
}

```

## disassembly

```asm
0x180021578  push    rbx
0x18002157a  sub     rsp, 20h
0x18002157e  cmp     word ptr [rdx], 13h
0x180021582  mov     r8, rcx
0x180021585  jz      short loc_18002159E
0x180021587  mov     ebx, 88982F8Eh
0x18002158c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180021593  jz      short loc_1800215DA
0x180021595  mov     ecx, ebx; int
0x180021597  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002159c  jmp     short loc_1800215DA
0x18002159e  cmp     dword ptr [rdx+8], 8000h
0x1800215a5  jbe     short loc_1800215AE
0x1800215a7  mov     ebx, 88982F05h
0x1800215ac  jmp     short loc_18002158C
0x1800215ae  xor     ebx, ebx
0x1800215b0  lea     r9d, [rbx+1]
0x1800215b4  mov     [rcx+104h], r9d
0x1800215bb  mov     ecx, [rdx+8]
0x1800215be  mov     edx, r9d
0x1800215c1  mov     [r8+100h], ecx
0x1800215c8  mov     rcx, [r8]
0x1800215cb  mov     rax, [rcx+80h]
0x1800215d2  mov     rcx, r8
0x1800215d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215da  mov     eax, ebx
0x1800215dc  add     rsp, 20h
0x1800215e0  pop     rbx
0x1800215e1  retn
```
