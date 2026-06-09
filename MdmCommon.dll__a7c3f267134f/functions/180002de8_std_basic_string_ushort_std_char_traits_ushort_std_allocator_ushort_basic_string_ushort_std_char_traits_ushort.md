# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180002de8`
- end: `0x180002e4d`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `72`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002e54`
- `0x180002f1c`
- `0x180003010`
- `0x1800030c0`
- `0x1800036d0`
- `0x1800040d0`
- `0x1800050a0`
- `0x1800058b0`
- `0x180005ea0`
- `0x180006200`
- `0x18000a528`
- `0x18000c6e8`
- `0x18000edc0`
- `0x180010eb4`
- `0x18001134c`
- `0x180011800`
- `0x180011e50`
- `0x180012414`
- `0x1800146d4`
- `0x180015270`
- `0x180016080`
- `0x18001ae24`
- `0x18001b924`
- `0x18001bd20`
- `0x18001be50`
- `0x18001c8d0`
- `0x18001cc30`
- `0x18001dd9e`
- `0x18001ddb0`
- `0x18001ddc2`
- `0x18001ddd4`
- `0x18001dde6`
- `0x18001ddf8`
- `0x18001de0a`
- `0x18001de76`
- `0x18001df6f`
- `0x18001df81`
- `0x18001df93`
- `0x18001dfb7`
- `0x18001dfc9`
- `0x18001dfdb`
- `0x18001dfff`
- `0x18001e011`
- `0x18001e023`
- `0x18001e047`
- `0x18001e059`
- `0x18001e06b`
- `0x18001e08f`
- `0x18001e0a1`
- `0x18001e0b3`

## callees

- `0x180001544`
- `0x180002de8`

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
0x180002de8  push    rbx
0x180002dea  sub     rsp, 20h
0x180002dee  mov     rdx, [rcx+18h]
0x180002df2  mov     rbx, rcx
0x180002df5  cmp     rdx, 7
0x180002df9  jbe     short loc_180002E35
0x180002dfb  mov     rax, [rcx]
0x180002dfe  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180002e06  cmp     rdx, 1000h
0x180002e0d  jb      short loc_180002E2D
0x180002e0f  mov     rcx, [rax-8]
0x180002e13  sub     rax, rcx
0x180002e16  sub     rax, 8
0x180002e1a  cmp     rax, 1Fh
0x180002e1e  ja      short loc_180002E26
0x180002e20  add     rdx, 27h ; '''
0x180002e24  jmp     short loc_180002E30
0x180002e26  mov     ecx, 5
0x180002e2b  int     29h; Win8: RtlFailFast(ecx)
0x180002e2d  mov     rcx, rax; void *
0x180002e30  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002e35  xor     eax, eax
0x180002e37  mov     qword ptr [rbx+18h], 7
0x180002e3f  mov     [rbx+10h], rax
0x180002e43  mov     [rbx], ax
0x180002e46  add     rsp, 20h
0x180002e4a  pop     rbx
0x180002e4b  retn
```
