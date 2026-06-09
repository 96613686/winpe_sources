# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1400032f4`
- end: `0x140003358`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140004f6c`
- `0x14000945d`
- `0x14000946f`

## callees

- `0x14000175c`
- `0x1400032f4`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  char *v4; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    if ( 2 * v1 + 2 < 0x1000 )
    {
      v4 = *a1;
    }
    else
    {
      v4 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v4 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v4);
  }
  result = 0;
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1400032f4  push    rbx
0x1400032f6  sub     rsp, 20h
0x1400032fa  mov     rdx, [rcx+18h]
0x1400032fe  mov     rbx, rcx
0x140003301  cmp     rdx, 7
0x140003305  jbe     short loc_140003341
0x140003307  mov     rax, [rcx]
0x14000330a  lea     rdx, ds:2[rdx*2]
0x140003312  cmp     rdx, 1000h
0x140003319  jb      short loc_140003339
0x14000331b  mov     rcx, [rax-8]
0x14000331f  sub     rax, rcx
0x140003322  sub     rax, 8
0x140003326  cmp     rax, 1Fh
0x14000332a  ja      short loc_140003332
0x14000332c  add     rdx, 27h ; '''
0x140003330  jmp     short loc_14000333C
0x140003332  mov     ecx, 5
0x140003337  int     29h; Win8: RtlFailFast(ecx)
0x140003339  mov     rcx, rax; Block
0x14000333c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003341  xor     eax, eax
0x140003343  mov     qword ptr [rbx+18h], 7
0x14000334b  mov     [rbx+10h], rax
0x14000334f  mov     [rbx], ax
0x140003352  add     rsp, 20h
0x140003356  pop     rbx
0x140003357  retn
```
