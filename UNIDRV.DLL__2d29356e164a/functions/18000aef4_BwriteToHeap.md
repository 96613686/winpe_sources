# BwriteToHeap

- ea: `0x18000aef4`
- end: `0x18000af96`
- name: `BwriteToHeap`
- size: `162`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a0b8`
- `0x18000aafc`
- `0x18000b504`
- `0x18000bdc8`
- `0x18000c2e8`
- `0x18000c700`
- `0x18000c924`
- `0x18004165c`
- `0x180041eec`
- `0x180047384`
- `0x180070b74`
- `0x1800715e0`
- `0x180072540`

## callees

- `0x180007220`
- `0x18000aef4`
- `0x180074580`

## string_xrefs

- `0x18000af5c`: `BwriteToHeap: out of heap - restarting.`
- `0x18000af63`: `BwriteToHeap`

## pseudocode

```c
__int64 __fastcall BwriteToHeap(_DWORD *a1, const void *a2, unsigned int a3, unsigned int a4, __int64 a5)
{
  unsigned int v7; // eax
  __int64 result; // rax

  v7 = a4 * ((a4 + *(_DWORD *)(a5 + 12) - 1) / a4);
  *(_DWORD *)(a5 + 12) = v7;
  if ( v7 + a3 > *(_DWORD *)(a5 + 8) )
  {
    WriteDbgTraceErrorGpd("BwriteToHeap", "BwriteToHeap: out of heap - restarting.");
    if ( *(int *)(a5 + 2220) < 2 )
    {
      *(_DWORD *)(a5 + 2220) = 2;
      *(_DWORD *)(a5 + 2224) = 2;
      *(_DWORD *)(a5 + 2216) = 0;
    }
    return 0;
  }
  else
  {
    memcpy_0((void *)(*(_QWORD *)a5 + v7), a2, a3);
    *a1 = *(_DWORD *)(a5 + 12);
    result = 1;
    *(_DWORD *)(a5 + 12) += a3;
  }
  return result;
}

```

## disassembly

```asm
0x18000aef4  mov     [rsp+arg_0], rbx
0x18000aef9  mov     [rsp+arg_8], rsi
0x18000aefe  push    rdi
0x18000aeff  sub     rsp, 20h
0x18000af03  mov     rbx, [rsp+28h+arg_20]
0x18000af08  mov     r10, rdx
0x18000af0b  xor     edx, edx
0x18000af0d  mov     edi, r8d
0x18000af10  mov     rsi, rcx
0x18000af13  mov     eax, [rbx+0Ch]
0x18000af16  dec     eax
0x18000af18  add     eax, r9d
0x18000af1b  div     r9d
0x18000af1e  imul    eax, r9d
0x18000af22  mov     [rbx+0Ch], eax
0x18000af25  lea     r9d, [rax+rdi]
0x18000af29  cmp     r9d, [rbx+8]
0x18000af2d  ja      short loc_18000AF5C
0x18000af2f  mov     ecx, eax
0x18000af31  mov     r8d, edi; Size
0x18000af34  add     rcx, [rbx]; void *
0x18000af37  mov     rdx, r10; Src
0x18000af3a  call    memcpy_0
0x18000af3f  mov     eax, [rbx+0Ch]
0x18000af42  mov     [rsi], eax
0x18000af44  mov     eax, 1
0x18000af49  add     [rbx+0Ch], edi
0x18000af4c  mov     rbx, [rsp+28h+arg_0]
0x18000af51  mov     rsi, [rsp+28h+arg_8]
0x18000af56  add     rsp, 20h
0x18000af5a  pop     rdi
0x18000af5b  retn
0x18000af5c  lea     rdx, aBwritetoheapOu; "BwriteToHeap: out of heap - restarting."
0x18000af63  lea     rcx, aBwritetoheap; "BwriteToHeap"
0x18000af6a  call    WriteDbgTraceErrorGpd
0x18000af6f  mov     eax, 2
0x18000af74  cmp     [rbx+8ACh], eax
0x18000af7a  jge     short loc_18000AF92
0x18000af7c  mov     [rbx+8ACh], eax
0x18000af82  mov     [rbx+8B0h], eax
0x18000af88  mov     dword ptr [rbx+8A8h], 0
0x18000af92  xor     eax, eax
0x18000af94  jmp     short loc_18000AF4C
```
