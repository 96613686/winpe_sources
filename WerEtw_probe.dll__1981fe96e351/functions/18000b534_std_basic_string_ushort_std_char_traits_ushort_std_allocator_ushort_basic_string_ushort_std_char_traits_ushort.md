# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000b534`
- end: `0x18000b598`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `42`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000b7b0`
- `0x18000bf98`
- `0x18000c1bc`
- `0x18000e050`
- `0x18000e234`
- `0x18000e3d0`
- `0x18000e474`
- `0x18000e530`
- `0x18000e6cc`
- `0x18000e8b4`
- `0x18000e8ec`
- `0x18000e914`
- `0x18000e920`
- `0x18000e9b0`
- `0x18000edc4`
- `0x18000f1d8`
- `0x18000f5dc`
- `0x1800111f8`
- `0x180011394`
- `0x1800127d0`
- `0x180013890`
- `0x180018a9c`
- `0x180018bc4`
- `0x18001a8e0`
- `0x18001b4fc`
- `0x18001b878`
- `0x18001c584`
- `0x18001da60`
- `0x180028004`
- `0x18002804c`
- `0x18002805e`
- `0x180028327`
- `0x180028339`
- `0x180028381`
- `0x180028393`
- `0x1800283c9`
- `0x18002849e`
- `0x1800284b0`
- `0x18002855f`
- `0x180028571`
- `0x180028a0f`
- `0x180028a21`

## callees

- `0x180001894`
- `0x18000b534`

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
0x18000b534  push    rbx
0x18000b536  sub     rsp, 20h
0x18000b53a  mov     rdx, [rcx+18h]
0x18000b53e  mov     rbx, rcx
0x18000b541  cmp     rdx, 7
0x18000b545  jbe     short loc_18000B581
0x18000b547  mov     rax, [rcx]
0x18000b54a  lea     rdx, ds:2[rdx*2]
0x18000b552  cmp     rdx, 1000h
0x18000b559  jb      short loc_18000B579
0x18000b55b  mov     rcx, [rax-8]
0x18000b55f  sub     rax, rcx
0x18000b562  sub     rax, 8
0x18000b566  cmp     rax, 1Fh
0x18000b56a  ja      short loc_18000B572
0x18000b56c  add     rdx, 27h ; '''
0x18000b570  jmp     short loc_18000B57C
0x18000b572  mov     ecx, 5
0x18000b577  int     29h; Win8: RtlFailFast(ecx)
0x18000b579  mov     rcx, rax; Block
0x18000b57c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b581  xor     eax, eax
0x18000b583  mov     qword ptr [rbx+18h], 7
0x18000b58b  mov     [rbx+10h], rax
0x18000b58f  mov     [rbx], ax
0x18000b592  add     rsp, 20h
0x18000b596  pop     rbx
0x18000b597  retn
```
