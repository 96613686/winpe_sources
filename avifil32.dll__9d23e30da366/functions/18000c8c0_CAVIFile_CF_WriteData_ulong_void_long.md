# CAVIFile::CF::WriteData(ulong,void *,long)

- ea: `0x18000c8c0`
- end: `0x18000c960`
- name: `?WriteData@CF@CAVIFile@@UEAAJKPEAXJ@Z`
- size: `160`
- prototype: `__int64 __fastcall(CAVIFile::CF *__hidden this, unsigned int, void *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c8c0`
- `0x18000d36c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c8e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c8e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c902`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c938`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c94a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c902`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c938`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c94a`

## pseudocode

```c
__int64 __fastcall CAVIFile::CF::WriteData(CAVIFile::CF *this, int a2, void *a3, int a4)
{
  __int64 v4; // rdi
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  unsigned int v10; // edi

  v4 = *((_QWORD *)this + 1);
  v8 = (struct _RTL_CRITICAL_SECTION *)(v4 + 1264);
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 1264));
  if ( a3 && a4 )
  {
    if ( (*(_BYTE *)(v4 + 660) & 3) != 0 )
    {
      *(_DWORD *)(v4 + 728) = 1;
      v10 = WriteExtra(v4 + 712, a2, a3, a4);
      if ( v8 )
        LeaveCriticalSection(v8);
      return v10;
    }
    else
    {
      if ( v4 != -1264 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 1264));
      return 2147762290LL;
    }
  }
  else
  {
    if ( v4 != -1264 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 1264));
    return 2147762282LL;
  }
}

```

## disassembly

```asm
0x18000c8c0  push    rbx
0x18000c8c2  push    rbp
0x18000c8c3  push    rsi
0x18000c8c4  push    rdi
0x18000c8c5  push    r14
0x18000c8c7  sub     rsp, 20h
0x18000c8cb  mov     rdi, [rcx+8]
0x18000c8cf  mov     esi, r9d
0x18000c8d2  mov     rbp, r8
0x18000c8d5  mov     r14d, edx
0x18000c8d8  lea     rbx, [rdi+4F0h]
0x18000c8df  mov     rcx, rbx; lpCriticalSection
0x18000c8e2  call    cs:__imp_EnterCriticalSection
0x18000c8e8  test    rbp, rbp
0x18000c8eb  jz      short loc_18000C942
0x18000c8ed  test    esi, esi
0x18000c8ef  jz      short loc_18000C942
0x18000c8f1  test    byte ptr [rdi+294h], 3
0x18000c8f8  jnz     short loc_18000C90F
0x18000c8fa  test    rbx, rbx
0x18000c8fd  jz      short loc_18000C908
0x18000c8ff  mov     rcx, rbx; lpCriticalSection
0x18000c902  call    cs:__imp_LeaveCriticalSection
0x18000c908  mov     eax, 80044072h
0x18000c90d  jmp     short loc_18000C955
0x18000c90f  lea     rcx, [rdi+2C8h]
0x18000c916  mov     dword ptr [rdi+2D8h], 1
0x18000c920  mov     r9d, esi
0x18000c923  mov     r8, rbp
0x18000c926  mov     edx, r14d
0x18000c929  call    WriteExtra
0x18000c92e  mov     edi, eax
0x18000c930  test    rbx, rbx
0x18000c933  jz      short loc_18000C93E
0x18000c935  mov     rcx, rbx; lpCriticalSection
0x18000c938  call    cs:__imp_LeaveCriticalSection
0x18000c93e  mov     eax, edi
0x18000c940  jmp     short loc_18000C955
0x18000c942  test    rbx, rbx
0x18000c945  jz      short loc_18000C950
0x18000c947  mov     rcx, rbx; lpCriticalSection
0x18000c94a  call    cs:__imp_LeaveCriticalSection
0x18000c950  mov     eax, 8004406Ah
0x18000c955  add     rsp, 20h
0x18000c959  pop     r14
0x18000c95b  pop     rdi
0x18000c95c  pop     rsi
0x18000c95d  pop     rbp
0x18000c95e  pop     rbx
0x18000c95f  retn
```
