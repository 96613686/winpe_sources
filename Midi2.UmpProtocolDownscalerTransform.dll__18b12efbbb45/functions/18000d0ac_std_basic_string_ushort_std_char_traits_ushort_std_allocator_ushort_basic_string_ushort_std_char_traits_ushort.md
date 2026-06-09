# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000d0ac`
- end: `0x18000d110`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000bc5c`
- `0x18000d36c`
- `0x18000e640`
- `0x18000e950`
- `0x1800125c2`

## callees

- `0x180002e94`
- `0x18000d0ac`

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
0x18000d0ac  push    rbx
0x18000d0ae  sub     rsp, 20h
0x18000d0b2  mov     rdx, [rcx+18h]
0x18000d0b6  mov     rbx, rcx
0x18000d0b9  cmp     rdx, 7
0x18000d0bd  jbe     short loc_18000D0F9
0x18000d0bf  mov     rax, [rcx]
0x18000d0c2  lea     rdx, ds:2[rdx*2]
0x18000d0ca  cmp     rdx, 1000h
0x18000d0d1  jb      short loc_18000D0F1
0x18000d0d3  mov     rcx, [rax-8]
0x18000d0d7  sub     rax, rcx
0x18000d0da  sub     rax, 8
0x18000d0de  cmp     rax, 1Fh
0x18000d0e2  ja      short loc_18000D0EA
0x18000d0e4  add     rdx, 27h ; '''
0x18000d0e8  jmp     short loc_18000D0F4
0x18000d0ea  mov     ecx, 5
0x18000d0ef  int     29h; Win8: RtlFailFast(ecx)
0x18000d0f1  mov     rcx, rax; Block
0x18000d0f4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d0f9  xor     eax, eax
0x18000d0fb  mov     qword ptr [rbx+18h], 7
0x18000d103  mov     [rbx+10h], rax
0x18000d107  mov     [rbx], ax
0x18000d10a  add     rsp, 20h
0x18000d10e  pop     rbx
0x18000d10f  retn
```
