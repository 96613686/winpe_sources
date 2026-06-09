# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x14000877c`
- end: `0x1400087dd`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(char **)`
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140008058`
- `0x14000869c`
- `0x1400089b4`
- `0x140009150`
- `0x140009d9c`
- `0x14000ae48`
- `0x14000aebc`
- `0x14000aece`
- `0x14000b006`
- `0x14000b032`
- `0x14000b044`
- `0x14000b056`

## callees

- `0x1400023b4`
- `0x14000877c`

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
0x14000877c  push    rbx
0x14000877e  sub     rsp, 20h
0x140008782  mov     rdx, [rcx+18h]
0x140008786  mov     rbx, rcx
0x140008789  cmp     rdx, 0Fh
0x14000878d  jbe     short loc_1400087C4
0x14000878f  mov     rax, [rcx]
0x140008792  inc     rdx; unsigned __int64
0x140008795  cmp     rdx, 1000h
0x14000879c  jb      short loc_1400087BC
0x14000879e  mov     rcx, [rax-8]
0x1400087a2  sub     rax, rcx
0x1400087a5  sub     rax, 8
0x1400087a9  cmp     rax, 1Fh
0x1400087ad  ja      short loc_1400087B5
0x1400087af  add     rdx, 27h ; '''
0x1400087b3  jmp     short loc_1400087BF
0x1400087b5  mov     ecx, 5
0x1400087ba  int     29h; Win8: RtlFailFast(ecx)
0x1400087bc  mov     rcx, rax; void *
0x1400087bf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400087c4  mov     qword ptr [rbx+10h], 0
0x1400087cc  mov     qword ptr [rbx+18h], 0Fh
0x1400087d4  mov     byte ptr [rbx], 0
0x1400087d7  add     rsp, 20h
0x1400087db  pop     rbx
0x1400087dc  retn
```
