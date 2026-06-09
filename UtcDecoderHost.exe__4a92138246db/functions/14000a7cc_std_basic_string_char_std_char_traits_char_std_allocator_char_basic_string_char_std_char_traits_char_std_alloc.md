# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x14000a7cc`
- end: `0x14000a82d`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(char **)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000fccc`
- `0x14001131c`
- `0x1400176c4`
- `0x14001789b`
- `0x140017a20`
- `0x140017c80`
- `0x140017d60`

## callees

- `0x1400088f4`
- `0x14000a7cc`

## pseudocode

```c
void __fastcall std::string::~string(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  unsigned __int64 v4; // rdx
  char *v5; // rcx

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 0xF )
  {
    v3 = *a1;
    v4 = v1 + 1;
    if ( v4 < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v5 - 8) > 0x1F )
        __fastfail(5u);
      v4 += 39LL;
    }
    operator delete(v5, v4);
  }
  a1[2] = 0;
  a1[3] = (char *)15;
  *(_BYTE *)a1 = 0;
}

```

## disassembly

```asm
0x14000a7cc  push    rbx
0x14000a7ce  sub     rsp, 20h
0x14000a7d2  mov     rdx, [rcx+18h]
0x14000a7d6  mov     rbx, rcx
0x14000a7d9  cmp     rdx, 0Fh
0x14000a7dd  jbe     short loc_14000A814
0x14000a7df  mov     rax, [rcx]
0x14000a7e2  inc     rdx; unsigned __int64
0x14000a7e5  cmp     rdx, 1000h
0x14000a7ec  jb      short loc_14000A80C
0x14000a7ee  mov     rcx, [rax-8]
0x14000a7f2  sub     rax, rcx
0x14000a7f5  sub     rax, 8
0x14000a7f9  cmp     rax, 1Fh
0x14000a7fd  ja      short loc_14000A805
0x14000a7ff  add     rdx, 27h ; '''
0x14000a803  jmp     short loc_14000A80F
0x14000a805  mov     ecx, 5
0x14000a80a  int     29h; Win8: RtlFailFast(ecx)
0x14000a80c  mov     rcx, rax; void *
0x14000a80f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000a814  mov     qword ptr [rbx+10h], 0
0x14000a81c  mov     qword ptr [rbx+18h], 0Fh
0x14000a824  mov     byte ptr [rbx], 0
0x14000a827  add     rsp, 20h
0x14000a82b  pop     rbx
0x14000a82c  retn
```
