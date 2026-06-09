# RetrieveDataRanges(void *,ulong,KSMULTIPLE_ITEM * *,ulong *)

- ea: `0x1800480b0`
- end: `0x1800481ae`
- name: `?RetrieveDataRanges@@YAJPEAXKPEAPEAUKSMULTIPLE_ITEM@@PEAK@Z`
- size: `254`
- prototype: `__int64 __fastcall(void *, unsigned int, struct KSMULTIPLE_ITEM **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180025ca0`
- `0x18003f728`

## callees

- `0x180005044`
- `0x18000b394`
- `0x180047e9c`
- `0x1800480b0`

## string_xrefs

- `0x1800480fd`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`
- `0x180048137`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`
- `0x180048178`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`

## pseudocode

```c
__int64 __fastcall RetrieveDataRanges(void *a1, unsigned int a2, struct KSMULTIPLE_ITEM **a3, unsigned int *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  unsigned int v9; // eax
  void *v10; // rcx
  void *v11; // rbx
  int v12; // [rsp+20h] [rbp-28h]
  unsigned int v13; // [rsp+30h] [rbp-18h] BYREF
  void *Block; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Block = 0;
  v13 = 0;
  v6 = PinPropertyAllocate(a1, a2, (const struct _GUID *)a3, 3u, &Block, &v13);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v9 = v13;
    if ( v13 >= 8 )
    {
      v11 = Block;
      if ( *((_DWORD *)Block + 1) )
      {
        *a3 = (struct KSMULTIPLE_ITEM *)Block;
        *a4 = v9;
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x159,
        (unsigned int)"avcore\\midi2\\libs\\midikscommon\\midikscommon.cpp",
        (const char *)0x8007065ELL,
        v12);
      v10 = v11;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x158,
        (unsigned int)"avcore\\midi2\\libs\\midikscommon\\midikscommon.cpp",
        (const char *)0x8007065ELL,
        v12);
      v10 = Block;
      if ( !Block )
        return 2147944030LL;
    }
    operator delete(v10);
    return 2147944030LL;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x156,
    (unsigned int)"avcore\\midi2\\libs\\midikscommon\\midikscommon.cpp",
    (const char *)(unsigned int)v6,
    v12);
  if ( Block )
    operator delete(Block);
  return v7;
}

```

## disassembly

```asm
0x1800480b0  mov     r11, rsp
0x1800480b3  mov     [r11+8], rbx
0x1800480b7  mov     [r11+10h], rsi
0x1800480bb  push    r14
0x1800480bd  sub     rsp, 40h
0x1800480c1  lea     rax, [r11-18h]
0x1800480c5  mov     qword ptr [r11-10h], 0
0x1800480cd  mov     [r11-20h], rax
0x1800480d1  mov     rsi, r9
0x1800480d4  lea     rax, [r11-10h]
0x1800480d8  mov     [rsp+48h+var_18], 0
0x1800480e0  mov     r9d, 3; unsigned int
0x1800480e6  mov     [r11-28h], rax
0x1800480ea  mov     r14, r8
0x1800480ed  call    ?PinPropertyAllocate@@YAJPEAXKAEBU_GUID@@KPEAPEAXPEAK@Z; PinPropertyAllocate(void *,ulong,_GUID const &,ulong,void * *,ulong *)
0x1800480f2  mov     ebx, eax
0x1800480f4  test    eax, eax
0x1800480f6  jns     short loc_180048129
0x1800480f8  mov     rcx, [rsp+48h]; this
0x1800480fd  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x180048104  mov     r9d, eax; char *
0x180048107  mov     edx, 156h; void *
0x18004810c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048111  mov     rcx, [rsp+48h+Block]; Block
0x180048116  test    rcx, rcx
0x180048119  jz      short loc_180048125
0x18004811b  mov     edx, 8
0x180048120  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048125  mov     eax, ebx
0x180048127  jmp     short loc_18004819D
0x180048129  mov     eax, [rsp+48h+var_18]
0x18004812d  cmp     eax, 8
0x180048130  jnb     short loc_180048168
0x180048132  mov     rcx, [rsp+48h]; this
0x180048137  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x18004813e  mov     esi, 8007065Eh
0x180048143  mov     edx, 158h; void *
0x180048148  mov     r9d, esi; char *
0x18004814b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048150  mov     rcx, [rsp+48h+Block]; Block
0x180048155  test    rcx, rcx
0x180048158  jz      short loc_180048164
0x18004815a  mov     edx, 8
0x18004815f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048164  mov     eax, esi
0x180048166  jmp     short loc_18004819D
0x180048168  mov     rbx, [rsp+48h+Block]
0x18004816d  cmp     dword ptr [rbx+4], 0
0x180048171  jnz     short loc_180048196
0x180048173  mov     rcx, [rsp+48h]; this
0x180048178  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x18004817f  mov     esi, 8007065Eh
0x180048184  mov     edx, 159h; void *
0x180048189  mov     r9d, esi; char *
0x18004818c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048191  mov     rcx, rbx
0x180048194  jmp     short loc_18004815A
0x180048196  mov     [r14], rbx
0x180048199  mov     [rsi], eax
0x18004819b  xor     eax, eax
0x18004819d  mov     rbx, [rsp+48h+arg_0]
0x1800481a2  mov     rsi, [rsp+48h+arg_8]
0x1800481a7  add     rsp, 40h
0x1800481ab  pop     r14
0x1800481ad  retn
```
