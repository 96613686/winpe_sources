# _hypothesis_builder::DoDetach(tagHYPOTHESIS * *)

- ea: `0x180007958`
- end: `0x1800079b2`
- name: `?DoDetach@_hypothesis_builder@@IEAAXPEAPEAUtagHYPOTHESIS@@@Z`
- size: `90`
- prototype: `void __fastcall(_hypothesis_builder *__hidden this, struct tagHYPOTHESIS **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007714`
- `0x1800078ac`

## callees

- `0x180007958`

## pseudocode

```c
void __fastcall _hypothesis_builder::DoDetach(_hypothesis_builder *this, struct tagHYPOTHESIS **a2)
{
  _QWORD *v3; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdx

  v3 = (_QWORD *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    *v3 = *(_QWORD *)this;
    v5 = *((_QWORD *)this + 4);
    v6 = *((_QWORD *)this + 1);
    *(_QWORD *)this = 0;
    *(_QWORD *)(v5 + 8) = v6;
    *((_QWORD *)this + 1) = 0;
    LODWORD(v5) = *((_DWORD *)this + 4);
    v7 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 4) = 0;
    *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = v5;
    *(_QWORD *)(*((_QWORD *)this + 4) + 24LL) = v7;
    *a2 = (struct tagHYPOTHESIS *)*((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = 0;
  }
  else
  {
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x180007958  mov     r8, rcx
0x18000795b  xor     r10d, r10d
0x18000795e  mov     rcx, [rcx+20h]
0x180007962  mov     r9, rdx
0x180007965  test    rcx, rcx
0x180007968  jnz     short loc_18000796E
0x18000796a  mov     [rdx], r10
0x18000796d  retn
0x18000796e  mov     rax, [r8]
0x180007971  mov     [rcx], rax
0x180007974  mov     rcx, [r8+20h]
0x180007978  mov     rax, [r8+8]
0x18000797c  mov     [r8], r10
0x18000797f  mov     [rcx+8], rax
0x180007983  mov     [r8+8], r10
0x180007987  mov     ecx, [r8+10h]
0x18000798b  mov     rdx, [r8+18h]
0x18000798f  mov     [r8+18h], r10
0x180007993  mov     [r8+10h], r10d
0x180007997  mov     rax, [r8+20h]
0x18000799b  mov     [rax+10h], ecx
0x18000799e  mov     rax, [r8+20h]
0x1800079a2  mov     [rax+18h], rdx
0x1800079a6  mov     rax, [r8+20h]
0x1800079aa  mov     [r9], rax
0x1800079ad  mov     [r8+20h], r10
0x1800079b1  retn
```
