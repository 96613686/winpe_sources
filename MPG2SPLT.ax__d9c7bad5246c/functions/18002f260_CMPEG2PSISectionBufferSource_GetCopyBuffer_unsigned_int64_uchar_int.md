# CMPEG2PSISectionBufferSource::GetCopyBuffer(unsigned __int64 *,uchar * *,int *)

- ea: `0x18002f260`
- end: `0x18002f303`
- name: `?GetCopyBuffer@CMPEG2PSISectionBufferSource@@UEAAJPEA_KPEAPEAEPEAH@Z`
- size: `163`
- prototype: `__int64 __fastcall(CMPEG2PSISectionBufferSource *__hidden this, unsigned __int64 *, unsigned __int8 **, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001008`
- `0x18002f260`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002f2ba`
- `KERNEL32!LeaveCriticalSection` at `0x18002f2ba`
- `KERNEL32!EnterCriticalSection` at `0x18002f286`
- `KERNEL32!EnterCriticalSection` at `0x18002f286`

## pseudocode

```c
__int64 __fastcall CMPEG2PSISectionBufferSource::GetCopyBuffer(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned __int64 *a2,
        unsigned __int8 **a3,
        int *a4)
{
  char *OwningThread; // rbx
  _QWORD *v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // ecx

  if ( *a4 > 4136 )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    EnterCriticalSection(this + 2);
    if ( LODWORD(this[1].SpinCount) )
    {
      OwningThread = (char *)this[1].OwningThread;
      v9 = (_QWORD *)*((_QWORD *)OwningThread + 1);
      v10 = *(_QWORD *)OwningThread;
      *v9 = *(_QWORD *)OwningThread;
      *(_QWORD *)(v10 + 8) = v9;
      --LODWORD(this[1].SpinCount);
    }
    else
    {
      OwningThread = (char *)operator new(0x1048u);
    }
    LeaveCriticalSection(this + 2);
    if ( OwningThread )
    {
      ++HIDWORD(this[1].SpinCount);
      *((_DWORD *)OwningThread + 1040) = 1;
      v11 = 0;
      *a2 = (unsigned __int64)OwningThread;
      *a3 = (unsigned __int8 *)(OwningThread + 24);
      *a4 = 4136;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18002f260  push    rbx
0x18002f262  push    rbp
0x18002f263  push    rsi
0x18002f264  push    rdi
0x18002f265  push    r14
0x18002f267  push    r15
0x18002f269  sub     rsp, 28h
0x18002f26d  cmp     dword ptr [r9], 1028h
0x18002f274  mov     r14, r9
0x18002f277  mov     r15, r8
0x18002f27a  mov     rbp, rdx
0x18002f27d  mov     rdi, rcx
0x18002f280  jg      short loc_18002F2EF
0x18002f282  add     rcx, 50h ; 'P'; lpCriticalSection
0x18002f286  call    cs:__imp_EnterCriticalSection
0x18002f28c  cmp     dword ptr [rdi+48h], 0
0x18002f290  jbe     short loc_18002F2A9
0x18002f292  mov     rbx, [rdi+38h]
0x18002f296  mov     rax, [rbx+8]
0x18002f29a  mov     rcx, [rbx]
0x18002f29d  mov     [rax], rcx
0x18002f2a0  mov     [rcx+8], rax
0x18002f2a4  dec     dword ptr [rdi+48h]
0x18002f2a7  jmp     short loc_18002F2B6
0x18002f2a9  mov     ecx, 1048h; Size
0x18002f2ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f2b3  mov     rbx, rax
0x18002f2b6  lea     rcx, [rdi+50h]; lpCriticalSection
0x18002f2ba  call    cs:__imp_LeaveCriticalSection
0x18002f2c0  test    rbx, rbx
0x18002f2c3  jnz     short loc_18002F2CC
0x18002f2c5  mov     ecx, 8007000Eh
0x18002f2ca  jmp     short loc_18002F2F4
0x18002f2cc  inc     dword ptr [rdi+4Ch]
0x18002f2cf  lea     rax, [rbx+18h]
0x18002f2d3  mov     dword ptr [rbx+1040h], 1
0x18002f2dd  xor     ecx, ecx
0x18002f2df  mov     [rbp+0], rbx
0x18002f2e3  mov     [r15], rax
0x18002f2e6  mov     dword ptr [r14], 1028h
0x18002f2ed  jmp     short loc_18002F2F4
0x18002f2ef  mov     ecx, 80004005h
0x18002f2f4  mov     eax, ecx
0x18002f2f6  add     rsp, 28h
0x18002f2fa  pop     r15
0x18002f2fc  pop     r14
0x18002f2fe  pop     rdi
0x18002f2ff  pop     rsi
0x18002f300  pop     rbp
0x18002f301  pop     rbx
0x18002f302  retn
```
