# CAVIStream::CS::WriteData(ulong,void *,long)

- ea: `0x18000c970`
- end: `0x18000ca43`
- name: `?WriteData@CS@CAVIStream@@UEAAJKPEAXJ@Z`
- size: `211`
- prototype: `__int64 __fastcall(CAVIStream::CS *__hidden this, unsigned int, void *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c970`
- `0x18000d36c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c999`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c999`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c9b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c9ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ca30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c9b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c9ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ca30`

## pseudocode

```c
__int64 __fastcall CAVIStream::CS::WriteData(CAVIStream::CS *this, int a2, void *a3, int a4)
{
  __int64 v4; // rsi
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  __int64 v9; // r10
  _DWORD *v11; // rdx
  unsigned int v12; // edi

  v4 = *((_QWORD *)this + 1);
  v8 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(v4 + 272) + 1264LL);
  EnterCriticalSection(v8);
  v9 = *(_QWORD *)(v4 + 272);
  if ( (*(_BYTE *)(v9 + 660) & 3) != 0 )
  {
    v11 = (_DWORD *)(v9 + 136);
    if ( *(int *)(v9 + 704) <= 0 || a4 + *v11 + 8 <= *(_DWORD *)(v9 + 672) )
    {
      *v11 += a4 + 12;
      *(_DWORD *)(*(_QWORD *)(v4 + 272) + 728LL) = 1;
      v12 = WriteExtra(v4 + 1368, a2, a3, a4);
      if ( v8 )
        LeaveCriticalSection(v8);
      return v12;
    }
    else
    {
      if ( v8 )
        LeaveCriticalSection(v8);
      return 2147762277LL;
    }
  }
  else
  {
    if ( v8 )
      LeaveCriticalSection(v8);
    return 2147762290LL;
  }
}

```

## disassembly

```asm
0x18000c970  push    rbx
0x18000c972  push    rbp
0x18000c973  push    rsi
0x18000c974  push    rdi
0x18000c975  push    r14
0x18000c977  sub     rsp, 20h
0x18000c97b  mov     rsi, [rcx+8]
0x18000c97f  mov     edi, r9d
0x18000c982  mov     rbp, r8
0x18000c985  mov     r14d, edx
0x18000c988  mov     rbx, [rsi+110h]
0x18000c98f  add     rbx, 4F0h
0x18000c996  mov     rcx, rbx; lpCriticalSection
0x18000c999  call    cs:__imp_EnterCriticalSection
0x18000c99f  mov     r10, [rsi+110h]
0x18000c9a6  test    byte ptr [r10+294h], 3
0x18000c9ae  jnz     short loc_18000C9C5
0x18000c9b0  test    rbx, rbx
0x18000c9b3  jz      short loc_18000C9BE
0x18000c9b5  mov     rcx, rbx; lpCriticalSection
0x18000c9b8  call    cs:__imp_LeaveCriticalSection
0x18000c9be  mov     eax, 80044072h
0x18000c9c3  jmp     short loc_18000CA38
0x18000c9c5  cmp     dword ptr [r10+2C0h], 0
0x18000c9cd  lea     rdx, [r10+88h]
0x18000c9d4  jle     short loc_18000C9FB
0x18000c9d6  mov     ecx, [rdx]
0x18000c9d8  add     ecx, 8
0x18000c9db  add     ecx, edi
0x18000c9dd  cmp     ecx, [r10+2A0h]
0x18000c9e4  jle     short loc_18000C9FB
0x18000c9e6  test    rbx, rbx
0x18000c9e9  jz      short loc_18000C9F4
0x18000c9eb  mov     rcx, rbx; lpCriticalSection
0x18000c9ee  call    cs:__imp_LeaveCriticalSection
0x18000c9f4  mov     eax, 80044065h
0x18000c9f9  jmp     short loc_18000CA38
0x18000c9fb  lea     eax, [rdi+0Ch]
0x18000c9fe  mov     r9d, edi
0x18000ca01  add     [rdx], eax
0x18000ca03  lea     rcx, [rsi+558h]
0x18000ca0a  mov     rax, [rsi+110h]
0x18000ca11  mov     r8, rbp
0x18000ca14  mov     edx, r14d
0x18000ca17  mov     dword ptr [rax+2D8h], 1
0x18000ca21  call    WriteExtra
0x18000ca26  mov     edi, eax
0x18000ca28  test    rbx, rbx
0x18000ca2b  jz      short loc_18000CA36
0x18000ca2d  mov     rcx, rbx; lpCriticalSection
0x18000ca30  call    cs:__imp_LeaveCriticalSection
0x18000ca36  mov     eax, edi
0x18000ca38  add     rsp, 20h
0x18000ca3c  pop     r14
0x18000ca3e  pop     rdi
0x18000ca3f  pop     rsi
0x18000ca40  pop     rbp
0x18000ca41  pop     rbx
0x18000ca42  retn
```
