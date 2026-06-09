# BiUpdateObjectReferenceInEfiEntry

- ea: `0x140025368`
- end: `0x1400254c9`
- name: `BiUpdateObjectReferenceInEfiEntry`
- size: `353`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x140022cb8`

## callees

- `0x1400140c4`
- `0x140020720`
- `0x1400242bc`
- `0x140025368`
- `0x1400265d6`
- `0x1400265e2`
- `0x140026650`

## import_xrefs

- `msvcrt!wcsstr` at `0x14002544a`
- `msvcrt!wcsstr` at `0x14002544a`
- `msvcrt!_wcsupr` at `0x14002543a`
- `msvcrt!_wcsupr` at `0x14002543a`
- `ntdll!RtlAllocateHeap` at `0x140025413`
- `ntdll!RtlAllocateHeap` at `0x140025413`
- `ntdll!RtlFreeHeap` at `0x14002549d`
- `ntdll!RtlFreeHeap` at `0x14002549d`

## pseudocode

```c
__int64 __fastcall BiUpdateObjectReferenceInEfiEntry(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  int ObjectReferenceFromEfiEntry; // ebx
  __int64 v6; // r8
  SIZE_T v7; // rdi
  wchar_t *Heap; // rax
  wchar_t *v9; // rsi
  wchar_t *v10; // rdi
  __int64 v12; // [rsp+20h] [rbp-49h] BYREF
  void *Src; // [rsp+28h] [rbp-41h]
  __int128 Buf2; // [rsp+30h] [rbp-39h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-29h] BYREF
  char v16; // [rsp+50h] [rbp-19h] BYREF

  v12 = 5111808;
  Src = &v16;
  Buf2 = 0;
  Buf1 = 0;
  ObjectReferenceFromEfiEntry = BiGetObjectReferenceFromEfiEntry(a1, &Buf1);
  if ( ObjectReferenceFromEfiEntry >= 0 )
  {
    ObjectReferenceFromEfiEntry = BcdQueryObject(a2, v4, v6, (__int64)&Buf2);
    if ( ObjectReferenceFromEfiEntry >= 0 )
    {
      if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
      {
        v7 = (unsigned int)(*(_DWORD *)(a1 + 40) - 20);
        Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
        v9 = Heap;
        if ( Heap )
        {
          memcpy_0(Heap, (const void *)(a1 + 48), v7);
          _wcsupr(v9);
          v10 = wcsstr(v9, L"BCDOBJECT=");
          if ( v10 )
          {
            BiStringFromGUID((unsigned int *)&Buf2, (__int64)&v12);
            memcpy_0((void *)(a1 + 68 + 2 * ((unsigned __int64)(v10 - v9) >> 1)), Src, (unsigned __int16)v12);
          }
          else
          {
            ObjectReferenceFromEfiEntry = -1073741275;
          }
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
        }
        else
        {
          return (unsigned int)-1073741670;
        }
      }
    }
  }
  return (unsigned int)ObjectReferenceFromEfiEntry;
}

```

## disassembly

```asm
0x140025368  mov     [rsp-8+arg_10], rbx
0x14002536d  mov     [rsp-8+arg_18], rsi
0x140025372  push    rbp
0x140025373  push    rdi
0x140025374  push    r14
0x140025376  lea     rbp, [rsp-47h]
0x14002537b  sub     rsp, 0B0h
0x140025382  mov     rax, cs:__security_cookie
0x140025389  xor     rax, rsp
0x14002538c  mov     [rbp+57h+var_20], rax
0x140025390  mov     rdi, rdx
0x140025393  mov     [rbp+57h+var_A0], 4E0000h
0x14002539b  xorps   xmm0, xmm0
0x14002539e  lea     rax, [rbp+57h+var_70]
0x1400253a2  xorps   xmm1, xmm1
0x1400253a5  mov     [rbp+57h+Src], rax
0x1400253a9  lea     rdx, [rbp+57h+Buf1]
0x1400253ad  mov     r14, rcx
0x1400253b0  movups  [rbp+57h+Buf2], xmm0
0x1400253b4  movups  [rbp+57h+Buf1], xmm1
0x1400253b8  call    BiGetObjectReferenceFromEfiEntry
0x1400253bd  mov     ebx, eax
0x1400253bf  test    eax, eax
0x1400253c1  js      loc_1400254A3
0x1400253c7  lea     r9, [rbp+57h+Buf2]
0x1400253cb  mov     rcx, rdi
0x1400253ce  call    BcdQueryObject
0x1400253d3  mov     ebx, eax
0x1400253d5  test    eax, eax
0x1400253d7  js      loc_1400254A3
0x1400253dd  mov     r8d, 10h; Size
0x1400253e3  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1400253e7  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1400253eb  call    memcmp_0
0x1400253f0  test    eax, eax
0x1400253f2  jz      loc_1400254A3
0x1400253f8  mov     rcx, gs:60h
0x140025401  xor     edx, edx; Flags
0x140025403  mov     eax, [r14+28h]
0x140025407  sub     eax, 14h
0x14002540a  mov     r8d, eax; Size
0x14002540d  mov     rcx, [rcx+30h]; HeapHandle
0x140025411  mov     edi, eax
0x140025413  call    cs:__imp_RtlAllocateHeap
0x140025419  mov     rsi, rax
0x14002541c  test    rax, rax
0x14002541f  jnz     short loc_140025428
0x140025421  mov     ebx, 0C000009Ah
0x140025426  jmp     short loc_1400254A3
0x140025428  lea     rdx, [r14+30h]; Src
0x14002542c  mov     r8, rdi; Size
0x14002542f  mov     rcx, rsi; void *
0x140025432  call    memcpy_0
0x140025437  mov     rcx, rsi; String
0x14002543a  call    cs:__imp__wcsupr
0x140025440  lea     rdx, aBcdobject; "BCDOBJECT="
0x140025447  mov     rcx, rsi; Str
0x14002544a  call    cs:__imp_wcsstr
0x140025450  mov     rdi, rax
0x140025453  test    rax, rax
0x140025456  jnz     short loc_14002545F
0x140025458  mov     ebx, 0C0000225h
0x14002545d  jmp     short loc_14002548B
0x14002545f  lea     rdx, [rbp+57h+var_A0]
0x140025463  lea     rcx, [rbp+57h+Buf2]
0x140025467  call    BiStringFromGUID
0x14002546c  movzx   r8d, word ptr [rbp+57h+var_A0]; Size
0x140025471  lea     rcx, [r14+44h]
0x140025475  mov     rdx, [rbp+57h+Src]; Src
0x140025479  sub     rdi, rsi
0x14002547c  sar     rdi, 1
0x14002547f  shr     rdi, 1
0x140025482  lea     rcx, [rcx+rdi*2]; void *
0x140025486  call    memcpy_0
0x14002548b  mov     rcx, gs:60h
0x140025494  mov     r8, rsi; P
0x140025497  xor     edx, edx; Flags
0x140025499  mov     rcx, [rcx+30h]; HeapHandle
0x14002549d  call    cs:__imp_RtlFreeHeap
0x1400254a3  mov     eax, ebx
0x1400254a5  mov     rcx, [rbp+57h+var_20]
0x1400254a9  xor     rcx, rsp; StackCookie
0x1400254ac  call    __security_check_cookie
0x1400254b1  lea     r11, [rsp+0C0h+var_10]
0x1400254b9  mov     rbx, [r11+30h]
0x1400254bd  mov     rsi, [r11+38h]
0x1400254c1  mov     rsp, r11
0x1400254c4  pop     r14
0x1400254c6  pop     rdi
0x1400254c7  pop     rbp
0x1400254c8  retn
```
