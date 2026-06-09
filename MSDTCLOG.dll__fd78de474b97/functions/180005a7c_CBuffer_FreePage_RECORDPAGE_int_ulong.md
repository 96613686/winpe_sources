# CBuffer::FreePage(_RECORDPAGE *,int,ulong)

- ea: `0x180005a7c`
- end: `0x180005b5b`
- name: `?FreePage@CBuffer@@QEAAXPEAU_RECORDPAGE@@HK@Z`
- size: `223`
- prototype: `void __fastcall(CBuffer *__hidden this, struct _RECORDPAGE *, int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cec8`
- `0x18000d3ec`
- `0x18000d694`

## callees

- `0x180005a7c`
- `0x18001266c`
- `0x180015010`

## pseudocode

```c
void __fastcall CBuffer::FreePage(struct _RECORDPAGE **this, struct _RECORDPAGE *a2, int a3, ulong a4)
{
  struct _RECORDPAGE *v5; // rcx
  bool v6; // zf
  ulong pExceptionObject; // [rsp+48h] [rbp+20h] BYREF

  pExceptionObject = a4;
  if ( a2 != this[7] )
  {
    pExceptionObject = -2147024809;
    throw &pExceptionObject;
  }
  if ( a3 )
  {
    if ( !*((_DWORD *)a2 + 6)
      && *((_DWORD *)a2 + 7)
      && (~(*((_DWORD *)this + 2) - 1) & *(_DWORD *)((_BYTE *)a2 + *((unsigned int *)a2 + 7) + 32)) == (~(*((_DWORD *)this + 2) - 1) & *(_DWORD *)((_BYTE *)a2 + *((unsigned int *)a2 + 7) + 52)) )
    {
      pExceptionObject = -1073737670;
      throw &pExceptionObject;
    }
    *((_DWORD *)a2 + 1) = ((__int64 (__fastcall *)(_QWORD, char *, void *))lpCalcCRC)(
                            (unsigned int)(*((_DWORD *)this + 2) - 8),
                            (char *)a2 + 8,
                            pulCRCTable);
    this[7] = (struct _RECORDPAGE *)((char *)this[7] + *((unsigned int *)this + 2));
    v5 = this[7];
    v6 = v5 == this[4];
    *((_DWORD *)this + 16) = v6;
    if ( v6 )
    {
      this[7] = 0;
    }
    else if ( !*((_DWORD *)this + 10) )
    {
      *(_DWORD *)v5 = 1146368594;
      *((_DWORD *)v5 + 6) = 8160;
    }
  }
}

```

## disassembly

```asm
0x180005a7c  mov     [rsp+arg_0], rbx
0x180005a81  mov     [rsp+pExceptionObject], r9d
0x180005a86  push    rdi
0x180005a87  sub     rsp, 20h
0x180005a8b  mov     rdi, rdx
0x180005a8e  mov     rbx, rcx
0x180005a91  cmp     rdx, [rcx+38h]
0x180005a95  jnz     loc_180005B27
0x180005a9b  test    r8d, r8d
0x180005a9e  jz      short loc_180005B1C
0x180005aa0  cmp     dword ptr [rdx+18h], 0
0x180005aa4  jnz     short loc_180005AC6
0x180005aa6  cmp     dword ptr [rdx+1Ch], 0
0x180005aaa  jbe     short loc_180005AC6
0x180005aac  mov     eax, [rdx+1Ch]
0x180005aaf  mov     edx, [rcx+8]
0x180005ab2  dec     edx
0x180005ab4  not     edx
0x180005ab6  mov     ecx, [rax+rdi+34h]
0x180005aba  mov     eax, [rax+rdi+20h]
0x180005abe  and     ecx, edx
0x180005ac0  and     eax, edx
0x180005ac2  cmp     eax, ecx
0x180005ac4  jz      short loc_180005B41
0x180005ac6  mov     ecx, [rbx+8]
0x180005ac9  lea     rdx, [rdi+8]
0x180005acd  mov     r8, cs:?pulCRCTable@@3PEAKEA; ulong * pulCRCTable
0x180005ad4  sub     ecx, 8
0x180005ad7  mov     rax, cs:?lpCalcCRC@@3P6AKIPEAEPEAK@ZEA; ulong (*lpCalcCRC)(uint,uchar *,ulong *)
0x180005ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae3  mov     [rdi+4], eax
0x180005ae6  mov     eax, [rbx+8]
0x180005ae9  add     [rbx+38h], rax
0x180005aed  xor     eax, eax
0x180005aef  mov     rcx, [rbx+38h]
0x180005af3  cmp     rcx, [rbx+20h]
0x180005af7  setz    al
0x180005afa  mov     [rbx+40h], eax
0x180005afd  jnz     short loc_180005B09
0x180005aff  mov     qword ptr [rbx+38h], 0
0x180005b07  jmp     short loc_180005B1C
0x180005b09  cmp     dword ptr [rbx+28h], 0
0x180005b0d  jnz     short loc_180005B1C
0x180005b0f  mov     dword ptr [rcx], 44543252h
0x180005b15  mov     dword ptr [rcx+18h], 1FE0h
0x180005b1c  mov     rbx, [rsp+28h+arg_0]
0x180005b21  add     rsp, 20h
0x180005b25  pop     rdi
0x180005b26  retn
0x180005b27  lea     rdx, _TI1K; pThrowInfo
0x180005b2e  mov     [rsp+28h+pExceptionObject], 80070057h
0x180005b36  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180005b3b  call    _CxxThrowException_0
0x180005b41  lea     rdx, _TI1K; pThrowInfo
0x180005b48  mov     [rsp+28h+pExceptionObject], 0C000103Ah
0x180005b50  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180005b55  call    _CxxThrowException_0
```
