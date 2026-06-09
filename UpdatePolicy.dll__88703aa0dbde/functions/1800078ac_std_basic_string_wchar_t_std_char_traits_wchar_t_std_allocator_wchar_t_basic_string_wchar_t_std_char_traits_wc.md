# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x1800078ac`
- end: `0x18000791f`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `115`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `14`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000218c`
- `0x18000226c`
- `0x180002650`
- `0x1800026b4`
- `0x18000297c`
- `0x180002a14`
- `0x180002b10`
- `0x180002bd8`
- `0x180002d50`
- `0x180002db0`
- `0x180002f78`
- `0x180003128`
- `0x18001615d`
- `0x180016181`

## callees

- `0x1800078ac`
- `0x18000ed64`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007918`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007918`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  unsigned __int64 v1; // rdx
  _QWORD *v3; // rcx
  const struct std::nothrow_t *v4; // rdx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 7 )
  {
    v3 = *(_QWORD **)a1;
    v4 = (const struct std::nothrow_t *)(2 * v1 + 2);
    if ( (unsigned __int64)v4 >= 0x1000 )
    {
      v4 = (const struct std::nothrow_t *)((char *)v4 + 39);
      if ( (unsigned __int64)v3 - *(v3 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v3 = (_QWORD *)*(v3 - 1);
    }
    operator delete(v3, v4);
  }
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800078ac  push    rbx
0x1800078ae  sub     rsp, 30h
0x1800078b2  mov     rdx, [rcx+18h]
0x1800078b6  mov     rbx, rcx
0x1800078b9  cmp     rdx, 7
0x1800078bd  jbe     short loc_1800078F0
0x1800078bf  mov     rcx, [rcx]
0x1800078c2  lea     rdx, ds:2[rdx*2]
0x1800078ca  cmp     rdx, 1000h
0x1800078d1  jb      short loc_1800078EB
0x1800078d3  mov     rax, [rcx-8]
0x1800078d7  add     rdx, 27h ; '''; struct std::nothrow_t *
0x1800078db  sub     rcx, rax
0x1800078de  sub     rcx, 8
0x1800078e2  cmp     rcx, 1Fh
0x1800078e6  ja      short loc_180007907
0x1800078e8  mov     rcx, rax; void *
0x1800078eb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800078f0  xor     eax, eax
0x1800078f2  mov     qword ptr [rbx+18h], 7
0x1800078fa  mov     [rbx+10h], rax
0x1800078fe  mov     [rbx], ax
0x180007901  add     rsp, 30h
0x180007905  pop     rbx
0x180007906  retn
0x180007907  xor     eax, eax
0x180007909  xor     r9d, r9d; LineNo
0x18000790c  xor     r8d, r8d; FileName
0x18000790f  mov     [rsp+38h+Reserved], rax; Reserved
0x180007914  xor     edx, edx; FunctionName
0x180007916  xor     ecx, ecx; Expression
0x180007918  call    cs:__imp__invoke_watson
```
