# BwriteToHeap

- ea: `0x18000af00`
- end: `0x18000afa3`
- name: `BwriteToHeap`
- size: `163`
- prototype: `__int64 __fastcall(_DWORD *, const void *, unsigned int, unsigned int, __int64)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a0b0`
- `0x18000aafc`
- `0x18000b518`
- `0x18000bdbc`
- `0x18000c2dc`
- `0x18000c6f8`
- `0x18000c920`
- `0x180042800`
- `0x180043090`
- `0x18004880c`
- `0x180072be0`
- `0x180073660`
- `0x1800745c8`

## callees

- `0x180007150`
- `0x18000af00`
- `0x180076660`

## string_xrefs

- `0x18000af69`: `BwriteToHeap: out of heap - restarting.`
- `0x18000af70`: `BwriteToHeap`

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
    WriteDbgTraceErrorGpd((__int64)"BwriteToHeap", "BwriteToHeap: out of heap - restarting.");
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
0x18000af00  mov     [rsp+arg_0], rbx
0x18000af05  mov     [rsp+arg_8], rsi
0x18000af0a  push    rdi
0x18000af0b  sub     rsp, 20h
0x18000af0f  mov     rbx, [rsp+28h+arg_20]
0x18000af14  mov     r10, rdx
0x18000af17  xor     edx, edx
0x18000af19  mov     edi, r8d
0x18000af1c  mov     rsi, rcx
0x18000af1f  mov     eax, [rbx+0Ch]
0x18000af22  dec     eax
0x18000af24  add     eax, r9d
0x18000af27  div     r9d
0x18000af2a  imul    eax, r9d
0x18000af2e  mov     [rbx+0Ch], eax
0x18000af31  lea     r9d, [rax+rdi]
0x18000af35  cmp     r9d, [rbx+8]
0x18000af39  ja      short loc_18000AF69
0x18000af3b  mov     ecx, eax
0x18000af3d  mov     r8d, edi; Size
0x18000af40  add     rcx, [rbx]; void *
0x18000af43  mov     rdx, r10; Src
0x18000af46  call    memcpy_0
0x18000af4b  mov     eax, [rbx+0Ch]
0x18000af4e  mov     [rsi], eax
0x18000af50  mov     eax, 1
0x18000af55  add     [rbx+0Ch], edi
0x18000af58  mov     rbx, [rsp+28h+arg_0]
0x18000af5d  mov     rsi, [rsp+28h+arg_8]
0x18000af62  add     rsp, 20h
0x18000af66  pop     rdi
0x18000af67  retn
0x18000af69  lea     rdx, aBwritetoheapOu; "BwriteToHeap: out of heap - restarting."
0x18000af70  lea     rcx, aBwritetoheap; "BwriteToHeap"
0x18000af77  call    WriteDbgTraceErrorGpd
0x18000af7c  mov     eax, 2
0x18000af81  cmp     [rbx+8ACh], eax
0x18000af87  jge     short loc_18000AF9F
0x18000af89  mov     [rbx+8ACh], eax
0x18000af8f  mov     [rbx+8B0h], eax
0x18000af95  mov     dword ptr [rbx+8A8h], 0
0x18000af9f  xor     eax, eax
0x18000afa1  jmp     short loc_18000AF58
```
