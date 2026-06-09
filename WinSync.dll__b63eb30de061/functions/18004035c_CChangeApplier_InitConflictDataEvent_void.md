# CChangeApplier::InitConflictDataEvent(void)

- ea: `0x18004035c`
- end: `0x18004042c`
- name: `?InitConflictDataEvent@CChangeApplier@@AEAAJXZ`
- size: `208`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180041720`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18004035c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800403c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800403c6`

## pseudocode

```c
__int64 __fastcall CChangeApplier::InitConflictDataEvent(CChangeApplier *this)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  HANDLE EventW; // rax
  bool v5; // zf

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      323,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::InitConflictDataEvent");
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( !*((_QWORD *)this + 76) )
  {
    EventW = CreateEventW(0, 1, 1, 0);
    v5 = *((_QWORD *)this + 44) == 0;
    *((_QWORD *)this + 76) = EventW;
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( v5 )
      v3 = -2147024882;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v2[2],
      324,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::InitConflictDataEvent",
      v3);
  return v3;
}

```

## disassembly

```asm
0x18004035c  mov     [rsp+arg_0], rbx
0x180040361  mov     [rsp+arg_8], rsi
0x180040366  push    rdi
0x180040367  sub     rsp, 30h
0x18004036b  mov     rdi, rcx
0x18004036e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040375  lea     rsi, WPP_GLOBAL_Control
0x18004037c  cmp     rcx, rsi
0x18004037f  jz      short loc_1800403B0
0x180040381  test    byte ptr [rcx+1Ch], 8
0x180040385  jz      short loc_1800403B0
0x180040387  cmp     byte ptr [rcx+19h], 5
0x18004038b  jb      short loc_1800403B0
0x18004038d  mov     rcx, [rcx+10h]
0x180040391  lea     r9, aCchangeapplier_10; "CChangeApplier::InitConflictDataEvent"
0x180040398  mov     edx, 143h
0x18004039d  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800403a4  call    WPP_SF_s
0x1800403a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800403b0  xor     ebx, ebx
0x1800403b2  cmp     [rdi+260h], rbx
0x1800403b9  jnz     short loc_1800403E9
0x1800403bb  lea     edx, [rbx+1]; bManualReset
0x1800403be  xor     r9d, r9d; lpName
0x1800403c1  mov     r8d, edx; bInitialState
0x1800403c4  xor     ecx, ecx; lpEventAttributes
0x1800403c6  call    cs:__imp_CreateEventW
0x1800403cc  cmp     [rdi+160h], rbx
0x1800403d3  mov     [rdi+260h], rax
0x1800403da  mov     eax, 8007000Eh
0x1800403df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800403e6  cmovz   ebx, eax
0x1800403e9  cmp     rcx, rsi
0x1800403ec  jz      short loc_18004041A
0x1800403ee  test    byte ptr [rcx+1Ch], 8
0x1800403f2  jz      short loc_18004041A
0x1800403f4  cmp     byte ptr [rcx+19h], 5
0x1800403f8  jb      short loc_18004041A
0x1800403fa  mov     rcx, [rcx+10h]
0x1800403fe  lea     r9, aCchangeapplier_10; "CChangeApplier::InitConflictDataEvent"
0x180040405  mov     edx, 144h
0x18004040a  mov     [rsp+38h+var_18], ebx
0x18004040e  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180040415  call    WPP_SF_sD
0x18004041a  mov     rsi, [rsp+38h+arg_8]
0x18004041f  mov     eax, ebx
0x180040421  mov     rbx, [rsp+38h+arg_0]
0x180040426  add     rsp, 30h
0x18004042a  pop     rdi
0x18004042b  retn
```
