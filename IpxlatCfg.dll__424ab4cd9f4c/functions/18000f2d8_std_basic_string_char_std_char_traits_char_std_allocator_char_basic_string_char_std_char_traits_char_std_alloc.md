# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x18000f2d8`
- end: `0x18000f339`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(char **)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ed18`
- `0x18000f184`
- `0x1800186ed`
- `0x1800186ff`
- `0x180018711`

## callees

- `0x180002110`
- `0x18000f2d8`

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
0x18000f2d8  push    rbx
0x18000f2da  sub     rsp, 20h
0x18000f2de  mov     rdx, [rcx+18h]
0x18000f2e2  mov     rbx, rcx
0x18000f2e5  cmp     rdx, 0Fh
0x18000f2e9  jbe     short loc_18000F320
0x18000f2eb  mov     rax, [rcx]
0x18000f2ee  inc     rdx; unsigned __int64
0x18000f2f1  cmp     rdx, 1000h
0x18000f2f8  jb      short loc_18000F318
0x18000f2fa  mov     rcx, [rax-8]
0x18000f2fe  sub     rax, rcx
0x18000f301  sub     rax, 8
0x18000f305  cmp     rax, 1Fh
0x18000f309  ja      short loc_18000F311
0x18000f30b  add     rdx, 27h ; '''
0x18000f30f  jmp     short loc_18000F31B
0x18000f311  mov     ecx, 5
0x18000f316  int     29h; Win8: RtlFailFast(ecx)
0x18000f318  mov     rcx, rax; void *
0x18000f31b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f320  mov     qword ptr [rbx+10h], 0
0x18000f328  mov     qword ptr [rbx+18h], 0Fh
0x18000f330  mov     byte ptr [rbx], 0
0x18000f333  add     rsp, 20h
0x18000f337  pop     rbx
0x18000f338  retn
```
