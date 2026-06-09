# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140003010`
- end: `0x140003086`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `29`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140001388`
- `0x140001e40`
- `0x140007d50`
- `0x14000993c`
- `0x140009ce4`
- `0x140009f90`
- `0x14000a298`
- `0x14000a40c`
- `0x14000a42c`
- `0x14000b7b4`
- `0x14000d7fc`
- `0x14000dc64`
- `0x14000e060`
- `0x14000e130`
- `0x14000f510`
- `0x14001526e`
- `0x14001527a`
- `0x1400152ea`
- `0x140015401`
- `0x140015419`
- `0x140015431`
- `0x140015492`
- `0x140015547`
- `0x140015583`
- `0x1400155bf`
- `0x1400155fb`
- `0x140015637`
- `0x140015700`
- `0x140015809`

## callees

- `0x140003010`
- `0x14001382c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x14000307f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x14000307f`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  unsigned __int64 v1; // rdx
  _QWORD *v3; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 7 )
  {
    v3 = *(_QWORD **)a1;
    if ( 2 * v1 + 2 >= 0x1000 )
    {
      if ( (unsigned __int64)v3 - *(v3 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v3 = (_QWORD *)*(v3 - 1);
    }
    _mm_lfence();
    operator delete(v3);
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
0x140003010  push    rbx
0x140003012  sub     rsp, 30h
0x140003016  mov     rdx, [rcx+18h]
0x14000301a  mov     rbx, rcx
0x14000301d  cmp     rdx, 7
0x140003021  jbe     short loc_140003057
0x140003023  mov     rcx, [rcx]
0x140003026  lea     rdx, ds:2[rdx*2]
0x14000302e  cmp     rdx, 1000h
0x140003035  jb      short loc_14000304F
0x140003037  mov     rax, [rcx-8]
0x14000303b  add     rdx, 27h ; '''
0x14000303f  sub     rcx, rax
0x140003042  sub     rcx, 8
0x140003046  cmp     rcx, 1Fh
0x14000304a  ja      short loc_14000306E
0x14000304c  mov     rcx, rax; Block
0x14000304f  lfence
0x140003052  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003057  xor     eax, eax
0x140003059  mov     qword ptr [rbx+18h], 7
0x140003061  mov     [rbx+10h], rax
0x140003065  mov     [rbx], ax
0x140003068  add     rsp, 30h
0x14000306c  pop     rbx
0x14000306d  retn
0x14000306e  xor     eax, eax
0x140003070  xor     r9d, r9d; LineNo
0x140003073  xor     r8d, r8d; FileName
0x140003076  mov     [rsp+38h+Reserved], rax; Reserved
0x14000307b  xor     edx, edx; FunctionName
0x14000307d  xor     ecx, ecx; Expression
0x14000307f  call    cs:__imp__invoke_watson
```
