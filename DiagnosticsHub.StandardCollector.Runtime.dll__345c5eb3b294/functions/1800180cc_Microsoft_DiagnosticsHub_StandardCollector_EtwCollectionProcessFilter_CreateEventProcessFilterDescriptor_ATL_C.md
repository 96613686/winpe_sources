# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::CreateEventProcessFilterDescriptor(ATL::CHeapPtr<_EVENT_FILTER_DESCRIPTOR,ATL::CCRTAllocator> &)

- ea: `0x1800180cc`
- end: `0x180018213`
- name: `?CreateEventProcessFilterDescriptor@EtwCollectionProcessFilter@StandardCollector@DiagnosticsHub@Microsoft@@IEBAJAEAV?$CHeapPtr@U_EVENT_FILTER_DESCRIPTOR@@VCCRTAllocator@ATL@@@ATL@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020ccc`
- `0x18002259c`

## callees

- `0x1800180cc`
- `0x180027d7c`
- `0x18003d864`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x18001814c`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001814c`
- `KERNEL32!AcquireSRWLockShared` at `0x180018109`
- `KERNEL32!AcquireSRWLockShared` at `0x180018109`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180018176`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180018176`

## string_xrefs

- `0x18001812d`: `Max filterable process count exceeded (%d processes currently targeted). Process filter descriptor will not be used.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::CreateEventProcessFilterDescriptor(
        __int64 a1,
        __int64 a2,
        unsigned __int16 a3)
{
  unsigned int v5; // ebx
  unsigned __int64 v7; // rax
  int v8; // r8d
  int v9; // r14d
  char *v10; // rax
  char *v11; // r10
  int v12; // r9d
  __int64 *v13; // rax
  __int64 **v14; // rdx
  __int64 *i; // rcx
  __int64 *j; // rdx

  v5 = 0;
  if ( !IsWindowsVersionOrGreater(a1, 3u, a3) )
    return 1;
  AcquireSRWLockShared((PSRWLOCK)(a1 + 48));
  v7 = *(_QWORD *)(a1 + 24);
  if ( !v7 )
    goto LABEL_6;
  if ( v7 > 8 )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionProcessFilter.cpp",
      L"Max filterable process count exceeded (%d processes currently targeted). Process filter descriptor will not be used.",
      *(_QWORD *)(a1 + 24),
      a1 + 48,
      0);
LABEL_6:
    v8 = 1;
    goto LABEL_7;
  }
  v9 = 4 * v7;
  v10 = (char *)malloc((unsigned int)(4 * v7) + 16LL);
  *(_QWORD *)a2 = v10;
  if ( v10 )
  {
    v11 = v10 + 16;
    v12 = 0;
    v13 = **(__int64 ***)(a1 + 16);
    while ( !*((_BYTE *)v13 + 25) )
    {
      *(_DWORD *)&v11[4 * v12++] = *((_DWORD *)v13 + 7);
      v14 = (__int64 **)v13[2];
      if ( *((_BYTE *)v14 + 25) )
      {
        for ( i = (__int64 *)v13[1]; !*((_BYTE *)i + 25) && v13 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v13 = i;
        v13 = i;
      }
      else
      {
        v13 = (__int64 *)v13[2];
        for ( j = *v14; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v13 = j;
      }
    }
    **(_QWORD **)a2 = v11;
    *(_DWORD *)(*(_QWORD *)a2 + 8LL) = v9;
    *(_DWORD *)(*(_QWORD *)a2 + 12LL) = -2147483644;
    goto LABEL_8;
  }
  v8 = -2147024882;
LABEL_7:
  v5 = v8;
LABEL_8:
  ReleaseSRWLockShared((PSRWLOCK)(a1 + 48));
  return v5;
}

```

## disassembly

```asm
0x1800180cc  mov     [rsp+arg_10], rbx
0x1800180d1  mov     [rsp+arg_18], rbp
0x1800180d6  push    rsi
0x1800180d7  push    rdi
0x1800180d8  push    r14
0x1800180da  sub     rsp, 30h
0x1800180de  mov     rsi, rdx
0x1800180e1  mov     rdi, rcx
0x1800180e4  mov     edx, 3; unsigned __int16
0x1800180e9  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800180ee  xor     ebx, ebx
0x1800180f0  test    al, al
0x1800180f2  jnz     short loc_1800180F9
0x1800180f4  lea     eax, [rbx+1]
0x1800180f7  jmp     short loc_180018154
0x1800180f9  lea     rbp, [rdi+30h]
0x1800180fd  mov     [rsp+48h+var_28], rbp
0x180018102  mov     [rsp+48h+var_20], ebx
0x180018106  mov     rcx, rbp; SRWLock
0x180018109  call    cs:__imp_AcquireSRWLockShared
0x18001810f  nop
0x180018110  mov     rax, [rdi+18h]
0x180018114  test    rax, rax
0x180018117  jz      short loc_180018140
0x180018119  cmp     rax, 8
0x18001811d  jbe     short loc_180018167
0x18001811f  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180018126  add     rcx, 38h ; '8'; this
0x18001812a  mov     r9, rax
0x18001812d  lea     r8, aMaxFilterableP; "Max filterable process count exceeded ("...
0x180018134  lea     rdx, aDAWork1SSource_0; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001813b  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180018140  mov     r8d, 1
0x180018146  mov     ebx, r8d
0x180018149  mov     rcx, rbp; SRWLock
0x18001814c  call    cs:__imp_ReleaseSRWLockShared
0x180018152  mov     eax, ebx
0x180018154  mov     rbx, [rsp+48h+arg_10]
0x180018159  mov     rbp, [rsp+48h+arg_18]
0x18001815e  add     rsp, 30h
0x180018162  pop     r14
0x180018164  pop     rdi
0x180018165  pop     rsi
0x180018166  retn
0x180018167  lea     r14d, ds:0[rax*4]
0x18001816f  mov     ecx, r14d
0x180018172  add     rcx, 10h; Size
0x180018176  call    cs:__imp_malloc
0x18001817c  mov     [rsi], rax
0x18001817f  test    rax, rax
0x180018182  jnz     short loc_18001818C
0x180018184  mov     r8d, 8007000Eh
0x18001818a  jmp     short loc_180018146
0x18001818c  lea     r10, [rax+10h]
0x180018190  mov     r9d, ebx
0x180018193  mov     rax, [rdi+10h]
0x180018197  mov     rax, [rax]
0x18001819a  cmp     [rax+19h], bl
0x18001819d  jnz     short loc_1800181F6
0x18001819f  mov     r8d, 1
0x1800181a5  mov     edx, r9d
0x1800181a8  mov     ecx, [rax+1Ch]
0x1800181ab  mov     [r10+rdx*4], ecx
0x1800181af  add     r9d, r8d
0x1800181b2  mov     rdx, [rax+10h]
0x1800181b6  cmp     [rdx+19h], bl
0x1800181b9  jz      short loc_1800181D8
0x1800181bb  mov     rcx, [rax+8]
0x1800181bf  jmp     short loc_1800181CE
0x1800181c1  cmp     rax, [rcx+10h]
0x1800181c5  jnz     short loc_1800181D3
0x1800181c7  mov     rax, rcx
0x1800181ca  mov     rcx, [rcx+8]
0x1800181ce  cmp     [rcx+19h], bl
0x1800181d1  jz      short loc_1800181C1
0x1800181d3  mov     rax, rcx
0x1800181d6  jmp     short loc_1800181F1
0x1800181d8  mov     rax, rdx
0x1800181db  mov     rdx, [rdx]
0x1800181de  cmp     [rdx+19h], bl
0x1800181e1  jnz     short loc_1800181F1
0x1800181e3  mov     rax, rdx
0x1800181e6  mov     rcx, [rdx]
0x1800181e9  mov     rdx, rcx
0x1800181ec  cmp     [rcx+19h], bl
0x1800181ef  jz      short loc_1800181E3
0x1800181f1  cmp     [rax+19h], bl
0x1800181f4  jz      short loc_1800181A5
0x1800181f6  mov     rax, [rsi]
0x1800181f9  mov     [rax], r10
0x1800181fc  mov     rax, [rsi]
0x1800181ff  mov     [rax+8], r14d
0x180018203  mov     rax, [rsi]
0x180018206  mov     dword ptr [rax+0Ch], 80000004h
0x18001820d  jmp     loc_180018149
```
