# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140004670`
- end: `0x1400046d4`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(char **)`
- caller_count: `33`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140007f3c`
- `0x1400097e0`
- `0x14000a120`
- `0x14000bc5c`
- `0x14000e9c4`
- `0x14000f3ec`
- `0x14000f744`
- `0x14000fa3c`
- `0x140010a24`
- `0x140010c94`
- `0x1400121b4`
- `0x140012220`
- `0x140012244`
- `0x140012256`
- `0x140012268`
- `0x14001227a`
- `0x14001228c`
- `0x14001229e`
- `0x1400122b0`
- `0x1400122c2`
- `0x1400122d4`
- `0x140012328`
- `0x14001233a`
- `0x140012370`
- `0x140012390`
- `0x1400123b0`
- `0x140012470`
- `0x140012490`
- `0x1400124b0`
- `0x1400124d0`
- `0x1400124f0`
- `0x140012510`
- `0x140012530`

## callees

- `0x140002dd8`
- `0x140004670`

## pseudocode

```c
void __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  char *v4; // rcx

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
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
}

```

## disassembly

```asm
0x140004670  push    rbx
0x140004672  sub     rsp, 20h
0x140004676  mov     rdx, [rcx+18h]
0x14000467a  mov     rbx, rcx
0x14000467d  cmp     rdx, 7
0x140004681  jbe     short loc_1400046BD
0x140004683  mov     rax, [rcx]
0x140004686  lea     rdx, ds:2[rdx*2]
0x14000468e  cmp     rdx, 1000h
0x140004695  jb      short loc_1400046B5
0x140004697  mov     rcx, [rax-8]
0x14000469b  sub     rax, rcx
0x14000469e  sub     rax, 8
0x1400046a2  cmp     rax, 1Fh
0x1400046a6  ja      short loc_1400046AE
0x1400046a8  add     rdx, 27h ; '''
0x1400046ac  jmp     short loc_1400046B8
0x1400046ae  mov     ecx, 5
0x1400046b3  int     29h; Win8: RtlFailFast(ecx)
0x1400046b5  mov     rcx, rax; Block
0x1400046b8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400046bd  xor     eax, eax
0x1400046bf  mov     qword ptr [rbx+18h], 7
0x1400046c7  mov     [rbx+10h], rax
0x1400046cb  mov     [rbx], ax
0x1400046ce  add     rsp, 20h
0x1400046d2  pop     rbx
0x1400046d3  retn
```
