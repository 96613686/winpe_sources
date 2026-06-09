# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::operator=(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x180009168`
- end: `0x180009201`
- name: `??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `153`
- prototype: `char **__fastcall(char **, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006aec`
- `0x18000865c`
- `0x18000aa84`
- `0x18000b4e8`

## callees

- `0x1800025d0`
- `0x180009168`

## pseudocode

```c
char **__fastcall std::wstring::operator=(char **a1, __int64 a2)
{
  unsigned __int64 v4; // rdx
  char *v5; // rax
  char *v6; // rcx

  if ( a1 != (char **)a2 )
  {
    v4 = (unsigned __int64)a1[3];
    if ( v4 > 7 )
    {
      v5 = *a1;
      if ( 2 * v4 + 2 < 0x1000 )
      {
        v6 = *a1;
      }
      else
      {
        v6 = (char *)*((_QWORD *)v5 - 1);
        if ( (unsigned __int64)(v5 - v6 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v6);
    }
    a1[2] = 0;
    *(_WORD *)a1 = 0;
    a1[3] = (char *)7;
    *(_OWORD *)a1 = *(_OWORD *)a2;
    *((_OWORD *)a1 + 1) = *(_OWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 7;
    *(_WORD *)a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180009168  mov     [rsp+arg_0], rbx
0x18000916d  push    rdi
0x18000916e  sub     rsp, 20h
0x180009172  mov     rdi, rdx
0x180009175  mov     rbx, rcx
0x180009178  cmp     rcx, rdx
0x18000917b  jz      short loc_1800091F3
0x18000917d  mov     rdx, [rcx+18h]
0x180009181  cmp     rdx, 7
0x180009185  jbe     short loc_1800091C1
0x180009187  mov     rax, [rcx]
0x18000918a  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180009192  cmp     rdx, 1000h
0x180009199  jb      short loc_1800091B9
0x18000919b  mov     rcx, [rax-8]
0x18000919f  sub     rax, rcx
0x1800091a2  sub     rax, 8
0x1800091a6  cmp     rax, 1Fh
0x1800091aa  ja      short loc_1800091B2
0x1800091ac  add     rdx, 27h ; '''
0x1800091b0  jmp     short loc_1800091BC
0x1800091b2  mov     ecx, 5
0x1800091b7  int     29h; Win8: RtlFailFast(ecx)
0x1800091b9  mov     rcx, rax; void *
0x1800091bc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800091c1  mov     qword ptr [rbx+10h], 0
0x1800091c9  xor     eax, eax
0x1800091cb  mov     [rbx], ax
0x1800091ce  mov     qword ptr [rbx+18h], 7
0x1800091d6  movups  xmm0, xmmword ptr [rdi]
0x1800091d9  movups  xmmword ptr [rbx], xmm0
0x1800091dc  movups  xmm1, xmmword ptr [rdi+10h]
0x1800091e0  movups  xmmword ptr [rbx+10h], xmm1
0x1800091e4  mov     [rdi+10h], rax
0x1800091e8  mov     qword ptr [rdi+18h], 7
0x1800091f0  mov     [rdi], ax
0x1800091f3  mov     rax, rbx
0x1800091f6  mov     rbx, [rsp+28h+arg_0]
0x1800091fb  add     rsp, 20h
0x1800091ff  pop     rdi
0x180009200  retn
```
