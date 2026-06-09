# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140013a2c`
- end: `0x140013a90`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `42`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140013aec`
- `0x140013c1c`
- `0x140014310`
- `0x140014a98`
- `0x140015464`
- `0x1400154d4`
- `0x140015708`
- `0x140016270`
- `0x1400168b4`
- `0x14001747c`
- `0x1400177a0`
- `0x140017ca4`
- `0x140019f94`
- `0x14001a878`
- `0x14001a9ac`
- `0x14001ab2c`
- `0x14001aec0`
- `0x14001afc0`
- `0x14001b130`
- `0x14001c056`
- `0x14001c0e3`
- `0x14001c212`
- `0x14001c269`
- `0x14001c27b`
- `0x14001c291`
- `0x14001c2a7`
- `0x14001c2bd`
- `0x14001c2fa`
- `0x14001c30c`
- `0x14001c31e`
- `0x14001c330`
- `0x14001c342`
- `0x14001c3ae`
- `0x14001c40c`
- `0x14001c4c0`
- `0x14001c730`
- `0x14001c750`
- `0x14001c770`
- `0x14001c790`
- `0x14001c7b0`
- `0x14001c7d0`
- `0x14001c7f0`

## callees

- `0x1400028d8`
- `0x140013a2c`

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
0x140013a2c  push    rbx
0x140013a2e  sub     rsp, 20h
0x140013a32  mov     rdx, [rcx+18h]
0x140013a36  mov     rbx, rcx
0x140013a39  cmp     rdx, 7
0x140013a3d  jbe     short loc_140013A79
0x140013a3f  mov     rax, [rcx]
0x140013a42  lea     rdx, ds:2[rdx*2]
0x140013a4a  cmp     rdx, 1000h
0x140013a51  jb      short loc_140013A71
0x140013a53  mov     rcx, [rax-8]
0x140013a57  sub     rax, rcx
0x140013a5a  sub     rax, 8
0x140013a5e  cmp     rax, 1Fh
0x140013a62  ja      short loc_140013A6A
0x140013a64  add     rdx, 27h ; '''
0x140013a68  jmp     short loc_140013A74
0x140013a6a  mov     ecx, 5
0x140013a6f  int     29h; Win8: RtlFailFast(ecx)
0x140013a71  mov     rcx, rax; Block
0x140013a74  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140013a79  xor     eax, eax
0x140013a7b  mov     qword ptr [rbx+18h], 7
0x140013a83  mov     [rbx+10h], rax
0x140013a87  mov     [rbx], ax
0x140013a8a  add     rsp, 20h
0x140013a8e  pop     rbx
0x140013a8f  retn
```
