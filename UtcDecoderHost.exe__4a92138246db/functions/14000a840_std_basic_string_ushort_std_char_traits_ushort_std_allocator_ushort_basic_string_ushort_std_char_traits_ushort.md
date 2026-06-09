# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x14000a840`
- end: `0x14000a8a4`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(char **)`
- caller_count: `23`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000d958`
- `0x14000ec68`
- `0x14000f6cc`
- `0x14000f758`
- `0x14000f918`
- `0x14000fccc`
- `0x14001071c`
- `0x140011ea4`
- `0x140012104`
- `0x140012470`
- `0x140012fa0`
- `0x14001766a`
- `0x14001768e`
- `0x1400176b2`
- `0x140017758`
- `0x1400177d8`
- `0x140017931`
- `0x140017943`
- `0x140017955`
- `0x140017a40`
- `0x140017ca0`
- `0x140017d20`
- `0x140017d40`

## callees

- `0x1400088f4`
- `0x14000a840`

## pseudocode

```c
void __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  unsigned __int64 v4; // rdx
  char *v5; // rcx

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
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
}

```

## disassembly

```asm
0x14000a840  push    rbx
0x14000a842  sub     rsp, 20h
0x14000a846  mov     rdx, [rcx+18h]
0x14000a84a  mov     rbx, rcx
0x14000a84d  cmp     rdx, 7
0x14000a851  jbe     short loc_14000A88D
0x14000a853  mov     rax, [rcx]
0x14000a856  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x14000a85e  cmp     rdx, 1000h
0x14000a865  jb      short loc_14000A885
0x14000a867  mov     rcx, [rax-8]
0x14000a86b  sub     rax, rcx
0x14000a86e  sub     rax, 8
0x14000a872  cmp     rax, 1Fh
0x14000a876  ja      short loc_14000A87E
0x14000a878  add     rdx, 27h ; '''
0x14000a87c  jmp     short loc_14000A888
0x14000a87e  mov     ecx, 5
0x14000a883  int     29h; Win8: RtlFailFast(ecx)
0x14000a885  mov     rcx, rax; void *
0x14000a888  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000a88d  xor     eax, eax
0x14000a88f  mov     qword ptr [rbx+18h], 7
0x14000a897  mov     [rbx+10h], rax
0x14000a89b  mov     [rbx], ax
0x14000a89e  add     rsp, 20h
0x14000a8a2  pop     rbx
0x14000a8a3  retn
```
