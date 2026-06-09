# AhcpCacheEntrySetDataFromStream

- ea: `0x140045c38`
- end: `0x140045d3c`
- name: `AhcpCacheEntrySetDataFromStream`
- size: `260`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x140028850`
- `0x1400440d8`
- `0x14004545c`
- `0x14004c3a0`
- `0x1400576e8`

## callees

- `0x14000436d`
- `0x140004553`
- `0x140007b40`
- `0x14003e364`
- `0x140045c38`
- `0x140045d44`

## string_xrefs

- `0x140045cf5`: `AhcpCacheEntrySetDataFromStream`
- `0x140045d1d`: `AhcpCacheEntrySetDataFromStream`
- `0x140045ce4`: `Failed to read stream [%x]`

## pseudocode

```c
__int64 __fastcall AhcpCacheEntrySetDataFromStream(__int64 a1, __int64 a2)
{
  void *v4; // rcx
  size_t v5; // rdi
  void *Pool2_0; // rax
  void *v7; // rbp
  size_t v8; // rax
  unsigned int v9; // ebx
  __int64 v11; // rcx

  v4 = *(void **)(a1 + 24);
  if ( v4 )
    ExFreePoolWithTag_0(v4, 0x74705041u);
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 16) = 0;
  v5 = *(_QWORD *)(a2 + 8);
  if ( !v5 )
    return 0;
  Pool2_0 = (void *)ExAllocatePool2_0(256, *(_QWORD *)(a2 + 8), 1953517633);
  v7 = Pool2_0;
  if ( !Pool2_0 )
  {
    v9 = -1073741801;
    AslLogCallPrintf(1, "AhcpCacheEntrySetDataFromStream", 402, "Out of memory");
    return v9;
  }
  *(_QWORD *)(a2 + 32) = 0;
  if ( v5 > *(_QWORD *)(a2 + 8) )
  {
    v9 = -1073741811;
    goto LABEL_11;
  }
  memmove(Pool2_0, *(const void **)(a2 + 40), v5);
  v8 = *(_QWORD *)(a2 + 32);
  if ( v8 + v5 < v8 )
  {
    *(_QWORD *)(a2 + 32) = -1;
    v9 = -1073741675;
LABEL_11:
    AslLogCallPrintf(1, "AhcpCacheEntrySetDataFromStream", 409, "Failed to read stream [%x]", v9);
    AslFree(v11, v7);
    return v9;
  }
  *(_QWORD *)(a2 + 32) = v8 + v5;
  *(_QWORD *)(a1 + 24) = v7;
  *(_DWORD *)(a1 + 16) = v5;
  return 0;
}

```

## disassembly

```asm
0x140045c38  push    rbx
0x140045c3a  push    rbp
0x140045c3b  push    rsi
0x140045c3c  push    rdi
0x140045c3d  sub     rsp, 38h
0x140045c41  mov     rsi, rcx
0x140045c44  mov     rbx, rdx
0x140045c47  mov     rcx, [rcx+18h]; P
0x140045c4b  mov     ebp, 74705041h
0x140045c50  test    rcx, rcx
0x140045c53  jz      short loc_140045C5C
0x140045c55  mov     edx, ebp; Tag
0x140045c57  call    ExFreePoolWithTag_0
0x140045c5c  mov     qword ptr [rsi+18h], 0
0x140045c64  mov     dword ptr [rsi+10h], 0
0x140045c6b  mov     rdi, [rbx+8]
0x140045c6f  test    rdi, rdi
0x140045c72  jz      short loc_140045CC9
0x140045c74  mov     r8d, ebp
0x140045c77  mov     rdx, rdi
0x140045c7a  mov     ecx, 100h
0x140045c7f  call    ExAllocatePool2_0
0x140045c84  mov     rbp, rax
0x140045c87  test    rax, rax
0x140045c8a  jz      loc_140045D10
0x140045c90  mov     qword ptr [rbx+20h], 0
0x140045c98  cmp     rdi, [rbx+8]
0x140045c9c  ja      loc_140045D35
0x140045ca2  mov     rdx, [rbx+28h]; Src
0x140045ca6  mov     r8, rdi; Size
0x140045ca9  mov     rcx, rax; void *
0x140045cac  call    memmove
0x140045cb1  mov     rax, [rbx+20h]
0x140045cb5  lea     rcx, [rax+rdi]
0x140045cb9  cmp     rcx, rax
0x140045cbc  jb      short loc_140045CD7
0x140045cbe  mov     [rbx+20h], rcx
0x140045cc2  mov     [rsi+18h], rbp
0x140045cc6  mov     [rsi+10h], edi
0x140045cc9  xor     ebx, ebx
0x140045ccb  mov     eax, ebx
0x140045ccd  add     rsp, 38h
0x140045cd1  pop     rdi
0x140045cd2  pop     rsi
0x140045cd3  pop     rbp
0x140045cd4  pop     rbx
0x140045cd5  retn
0x140045cd7  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x140045cdf  mov     ebx, 0C0000095h
0x140045ce4  lea     r9, aFailedToReadSt; "Failed to read stream [%x]"
0x140045ceb  mov     [rsp+58h+var_38], ebx
0x140045cef  mov     r8d, 199h
0x140045cf5  lea     rdx, aAhcpcacheentry_2; "AhcpCacheEntrySetDataFromStream"
0x140045cfc  mov     ecx, 1
0x140045d01  call    AslLogCallPrintf
0x140045d06  mov     rdx, rbp
0x140045d09  call    AslFree
0x140045d0e  jmp     short loc_140045CCB
0x140045d10  lea     r9, aOutOfMemory; "Out of memory"
0x140045d17  mov     r8d, 192h
0x140045d1d  lea     rdx, aAhcpcacheentry_2; "AhcpCacheEntrySetDataFromStream"
0x140045d24  mov     ecx, 1
0x140045d29  mov     ebx, 0C0000017h
0x140045d2e  call    AslLogCallPrintf
0x140045d33  jmp     short loc_140045CCB
0x140045d35  mov     ebx, 0C000000Dh
0x140045d3a  jmp     short loc_140045CE4
```
