# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180002de4`
- end: `0x180002e48`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `72`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002e50`
- `0x180002f14`
- `0x180003010`
- `0x1800030c0`
- `0x1800036c0`
- `0x1800040c0`
- `0x180005070`
- `0x180005860`
- `0x180005e50`
- `0x1800061a8`
- `0x18000a314`
- `0x18000c38c`
- `0x18000e97c`
- `0x180010b0c`
- `0x180010f90`
- `0x18001142c`
- `0x180011a78`
- `0x180012038`
- `0x1800142c8`
- `0x180014e2c`
- `0x180015bf0`
- `0x18001a8d4`
- `0x18001b394`
- `0x18001b780`
- `0x18001b8b0`
- `0x18001c298`
- `0x18001c5f0`
- `0x18001d6be`
- `0x18001d6d0`
- `0x18001d6e2`
- `0x18001d6f4`
- `0x18001d706`
- `0x18001d718`
- `0x18001d72a`
- `0x18001d796`
- `0x18001d88f`
- `0x18001d8a1`
- `0x18001d8b3`
- `0x18001d8d7`
- `0x18001d8e9`
- `0x18001d8fb`
- `0x18001d91f`
- `0x18001d931`
- `0x18001d943`
- `0x18001d967`
- `0x18001d979`
- `0x18001d98b`
- `0x18001d9af`
- `0x18001d9c1`
- `0x18001d9d3`

## callees

- `0x180001544`
- `0x180002de4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  unsigned __int64 v4; // rdx
  char *v5; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    v4 = 2 * v1 + 2;
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
  result = 0;
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180002de4  push    rbx
0x180002de6  sub     rsp, 20h
0x180002dea  mov     rdx, [rcx+18h]
0x180002dee  mov     rbx, rcx
0x180002df1  cmp     rdx, 7
0x180002df5  jbe     short loc_180002E31
0x180002df7  mov     rax, [rcx]
0x180002dfa  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180002e02  cmp     rdx, 1000h
0x180002e09  jb      short loc_180002E29
0x180002e0b  mov     rcx, [rax-8]
0x180002e0f  sub     rax, rcx
0x180002e12  sub     rax, 8
0x180002e16  cmp     rax, 1Fh
0x180002e1a  ja      short loc_180002E22
0x180002e1c  add     rdx, 27h ; '''
0x180002e20  jmp     short loc_180002E2C
0x180002e22  mov     ecx, 5
0x180002e27  int     29h; Win8: RtlFailFast(ecx)
0x180002e29  mov     rcx, rax; void *
0x180002e2c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002e31  xor     eax, eax
0x180002e33  mov     qword ptr [rbx+18h], 7
0x180002e3b  mov     [rbx+10h], rax
0x180002e3f  mov     [rbx], ax
0x180002e42  add     rsp, 20h
0x180002e46  pop     rbx
0x180002e47  retn
```
