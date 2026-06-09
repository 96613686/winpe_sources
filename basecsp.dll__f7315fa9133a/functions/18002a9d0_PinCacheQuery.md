# PinCacheQuery

- ea: `0x18002a9d0`
- end: `0x18002ab32`
- name: `PinCacheQuery`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002a814`

## callees

- `0x18000a766`
- `0x18002a020`
- `0x18002a310`
- `0x18002a9d0`

## import_xrefs

- `msvcrt!time` at `0x18002aa3a`
- `msvcrt!time` at `0x18002aa3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ab04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ab04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002aaf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002aaf4`

## pseudocode

```c
__int64 __fastcall PinCacheQuery(__int64 a1, int a2, __int64 a3, void *a4, _DWORD *a5, _DWORD *a6)
{
  _DWORD *v8; // rdi
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rbp
  _DWORD *v13; // r14
  _DWORD *v14; // rax
  int v15; // ecx
  _BYTE *v16; // rax
  __int64 v17; // rcx
  HANDLE ProcessHeap; // rax
  void *Src; // [rsp+20h] [rbp-28h] BYREF
  time_t Time; // [rsp+28h] [rbp-20h] BYREF
  size_t Size; // [rsp+50h] [rbp+8h] BYREF

  Src = 0;
  LODWORD(Size) = 0;
  Time = 0;
  if ( (unsigned int)(a2 - 1) > 7 )
    return 160;
  if ( a1 && (v8 = *(_DWORD **)(a1 + 8LL * (unsigned int)(a2 - 1))) != 0 )
  {
    if ( a3
      && *(_DWORD *)(a3 + 24) == 1
      && ((time(&Time), (unsigned int)Time < v8[10]) || (unsigned int)(Time - v8[10]) > v8[12]) )
    {
      return (unsigned int)-2146435022;
    }
    else
    {
      v10 = I_PinCacheLookup(v8);
      v9 = v10;
      if ( v10 )
      {
        if ( v10 == 4306 )
          *a5 = 0;
      }
      else
      {
        v11 = I_PinCacheDecryptPin(v8, &Src, &Size);
        v12 = (unsigned int)Size;
        v9 = v11;
        if ( !v11 )
        {
          v13 = a5;
          if ( a4 )
          {
            if ( *a5 < (unsigned int)Size )
              v9 = 234;
            else
              memcpy_0(a4, Src, (unsigned int)Size);
          }
          v14 = a6;
          v15 = v8[8];
          *v13 = v12;
          *v14 = v15;
        }
        if ( Src )
        {
          v16 = Src;
          v17 = v12;
          if ( (_DWORD)v12 )
          {
            do
            {
              *v16++ = 0;
              --v17;
            }
            while ( v17 );
          }
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, Src);
        }
      }
    }
    return v9;
  }
  else
  {
    *a5 = 0;
    return 4306;
  }
}

```

## disassembly

```asm
0x18002a9d0  mov     rax, rsp
0x18002a9d3  mov     [rax+10h], rbx
0x18002a9d7  mov     [rax+18h], rbp
0x18002a9db  push    rdi
0x18002a9dc  push    r14
0x18002a9de  push    r15
0x18002a9e0  sub     rsp, 30h
0x18002a9e4  mov     qword ptr [rax-28h], 0
0x18002a9ec  mov     r15, r9
0x18002a9ef  mov     dword ptr [rax+8], 0
0x18002a9f6  mov     qword ptr [rax-20h], 0
0x18002a9fe  lea     eax, [rdx-1]
0x18002aa01  cmp     eax, 7
0x18002aa04  jbe     short loc_18002AA10
0x18002aa06  mov     eax, 0A0h
0x18002aa0b  jmp     loc_18002AB1E
0x18002aa10  test    rcx, rcx
0x18002aa13  jz      loc_18002AB0E
0x18002aa19  lea     eax, [rdx-1]
0x18002aa1c  mov     rdi, [rcx+rax*8]
0x18002aa20  test    rdi, rdi
0x18002aa23  jz      loc_18002AB0E
0x18002aa29  test    r8, r8
0x18002aa2c  jz      short loc_18002AA5C
0x18002aa2e  cmp     dword ptr [r8+18h], 1
0x18002aa33  jnz     short loc_18002AA5C
0x18002aa35  lea     rcx, [rsp+48h+Time]; Time
0x18002aa3a  call    cs:__imp_time
0x18002aa40  mov     rax, [rsp+48h+Time]
0x18002aa45  cmp     eax, [rdi+28h]
0x18002aa48  jb      short loc_18002AA52
0x18002aa4a  sub     eax, [rdi+28h]
0x18002aa4d  cmp     eax, [rdi+30h]
0x18002aa50  jbe     short loc_18002AA5C
0x18002aa52  mov     ebx, 80100032h
0x18002aa57  jmp     loc_18002AB0A
0x18002aa5c  mov     rcx, rdi
0x18002aa5f  call    I_PinCacheLookup
0x18002aa64  mov     ebx, eax
0x18002aa66  test    eax, eax
0x18002aa68  jz      short loc_18002AA85
0x18002aa6a  cmp     eax, 10D2h
0x18002aa6f  jnz     loc_18002AB0A
0x18002aa75  mov     rcx, [rsp+48h+arg_20]
0x18002aa7a  mov     dword ptr [rcx], 0
0x18002aa80  jmp     loc_18002AB0A
0x18002aa85  lea     r8, [rsp+48h+Size]
0x18002aa8a  mov     rcx, rdi
0x18002aa8d  lea     rdx, [rsp+48h+Src]
0x18002aa92  call    I_PinCacheDecryptPin
0x18002aa97  mov     ebp, dword ptr [rsp+48h+Size]
0x18002aa9b  mov     ebx, eax
0x18002aa9d  test    eax, eax
0x18002aa9f  jnz     short loc_18002AAD4
0x18002aaa1  mov     r14, [rsp+48h+arg_20]
0x18002aaa6  test    r15, r15
0x18002aaa9  jz      short loc_18002AAC7
0x18002aaab  cmp     [r14], ebp
0x18002aaae  jb      short loc_18002AAC2
0x18002aab0  mov     rdx, [rsp+48h+Src]; Src
0x18002aab5  mov     r8d, ebp; Size
0x18002aab8  mov     rcx, r15; void *
0x18002aabb  call    memcpy_0
0x18002aac0  jmp     short loc_18002AAC7
0x18002aac2  mov     ebx, 0EAh
0x18002aac7  mov     rax, [rsp+48h+arg_28]
0x18002aacc  mov     ecx, [rdi+20h]
0x18002aacf  mov     [r14], ebp
0x18002aad2  mov     [rax], ecx
0x18002aad4  cmp     [rsp+48h+Src], 0
0x18002aada  jz      short loc_18002AB0A
0x18002aadc  mov     rax, [rsp+48h+Src]
0x18002aae1  mov     rcx, rbp
0x18002aae4  test    ebp, ebp
0x18002aae6  jz      short loc_18002AAF4
0x18002aae8  mov     byte ptr [rax], 0
0x18002aaeb  inc     rax
0x18002aaee  sub     rcx, 1
0x18002aaf2  jnz     short loc_18002AAE8
0x18002aaf4  call    cs:__imp_GetProcessHeap
0x18002aafa  mov     r8, [rsp+48h+Src]; lpMem
0x18002aaff  xor     edx, edx; dwFlags
0x18002ab01  mov     rcx, rax; hHeap
0x18002ab04  call    cs:__imp_HeapFree
0x18002ab0a  mov     eax, ebx
0x18002ab0c  jmp     short loc_18002AB1E
0x18002ab0e  mov     rax, [rsp+48h+arg_20]
0x18002ab13  mov     dword ptr [rax], 0
0x18002ab19  mov     eax, 10D2h
0x18002ab1e  mov     rbx, [rsp+48h+arg_8]
0x18002ab23  mov     rbp, [rsp+48h+arg_10]
0x18002ab28  add     rsp, 30h
0x18002ab2c  pop     r15
0x18002ab2e  pop     r14
0x18002ab30  pop     rdi
0x18002ab31  retn
```
