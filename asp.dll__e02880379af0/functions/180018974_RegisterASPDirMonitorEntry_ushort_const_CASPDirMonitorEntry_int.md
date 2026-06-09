# RegisterASPDirMonitorEntry(ushort const *,CASPDirMonitorEntry * *,int)

- ea: `0x180018974`
- end: `0x180018b27`
- name: `?RegisterASPDirMonitorEntry@@YAHPEBGPEAPEAVCASPDirMonitorEntry@@H@Z`
- size: `435`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CASPDirMonitorEntry **, int)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180009180`
- `0x180013604`
- `0x180034fc0`
- `0x18004877c`

## callees

- `0x180018974`
- `0x180018b30`
- `0x180023d86`
- `0x180023dd0`
- `0x180064010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18002ed0a`
- `msvcrt!wcscpy_s` at `0x18002ed0a`
- `KERNEL32!HeapAlloc` at `0x180018a4d`
- `KERNEL32!HeapAlloc` at `0x180018a4d`
- `KERNEL32!GetLastError` at `0x18002ed65`
- `KERNEL32!GetLastError` at `0x18002ed65`
- `iisutil!?ReadLock@CLKRHashTable@@QEBAXXZ` at `0x180018a04`
- `iisutil!?ReadLock@CLKRHashTable@@QEBAXXZ` at `0x180018a04`
- `iisutil!?ReadUnlock@CLKRHashTable@@QEBAXXZ` at `0x180018a31`
- `iisutil!?ReadUnlock@CLKRHashTable@@QEBAXXZ` at `0x180018a31`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180018a1a`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180018a1a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002ece9`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002ece9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002ecfc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002ed15`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002ecfc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002ed15`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800189c8`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800189c8`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180018ada`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180018b1d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180018ada`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180018b1d`

## pseudocode

```c
__int64 __fastcall RegisterASPDirMonitorEntry(const unsigned __int16 *a1, struct CASPDirMonitorEntry **a2, int a3)
{
  __int64 v6; // rdi
  int i; // r14d
  CLKRHashTable *v8; // rdi
  struct CASPDirMonitorEntry *v9; // rbx
  struct CASPDirMonitorEntry *v10; // rax
  CDirMonitor *v11; // rcx
  wchar_t *Ptr; // rax
  struct CASPDirMonitorEntry *v14; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[56]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 v16[256]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(v16, 0, sizeof(v16));
  BUFFER::BUFFER((BUFFER *)v15, v16, 0x100u);
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  if ( (_DWORD)v6 && a1[(unsigned int)(v6 - 1)] != 92 )
  {
    if ( !BUFFER::Resize((BUFFER *)v15, 2 * (v6 + 2)) )
      goto LABEL_13;
    Ptr = (wchar_t *)BUFFER::QueryPtr((BUFFER *)v15);
    wcscpy_s(Ptr, (unsigned int)(v6 + 2), a1);
    a1 = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v15);
    a1[(unsigned int)v6] = 92;
    a1[(unsigned int)(v6 + 1)] = 0;
  }
  for ( i = 0; ; i = 1 )
  {
    v8 = g_pDirMonitor;
    CLKRHashTable::ReadLock(g_pDirMonitor);
    v14 = 0;
    CLKRHashTable::FindKey(v8, a1, &v14);
    v9 = v14;
    if ( v14 )
    {
      if ( *((_DWORD *)v14 + 26) )
        v9 = 0;
      else
        (*(void (__fastcall **)(struct CASPDirMonitorEntry *))(*(_QWORD *)v14 + 8LL))(v14);
    }
    CLKRHashTable::ReadUnlock(v8);
    if ( v9 )
      goto LABEL_10;
    v10 = (struct CASPDirMonitorEntry *)HeapAlloc(g_hDenaliHeap, 0, 0x78u);
    v9 = v10;
    if ( !v10 )
      break;
    *((_DWORD *)v10 + 2) = 0;
    *(_QWORD *)v10 = &CDirMonitorEntry::`vftable';
    *((_QWORD *)v10 + 2) = 0;
    *(_QWORD *)v10 = &CASPDirMonitorEntry::`vftable';
    *((_QWORD *)v10 + 3) = 0;
    *((_QWORD *)v10 + 4) = 0;
    *((_QWORD *)v10 + 5) = -1;
    *((_QWORD *)v10 + 6) = 0;
    *((_DWORD *)v10 + 22) = 0;
    *((_QWORD *)v10 + 12) = 0;
    *((_DWORD *)v10 + 26) = 0;
    *((_DWORD *)v10 + 28) = 0;
    CASPDirMonitorEntry::AddRef(v10);
    (*(void (__fastcall **)(struct CASPDirMonitorEntry *, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, 0);
    if ( (unsigned int)CDirMonitor::Monitor(v11, v9, a1, a3) )
    {
LABEL_10:
      *a2 = v9;
      BUFFER::~BUFFER((BUFFER *)v15);
      return 1;
    }
    (*(void (__fastcall **)(struct CASPDirMonitorEntry *))(*(_QWORD *)v9 + 16LL))(v9);
    if ( GetLastError() != 183 || i )
      break;
  }
  *a2 = 0;
LABEL_13:
  BUFFER::~BUFFER((BUFFER *)v15);
  return 0;
}

```

## disassembly

```asm
0x180018974  mov     [rsp-8+arg_10], rbx
0x180018979  push    rbp
0x18001897a  push    rsi
0x18001897b  push    rdi
0x18001897c  push    r12
0x18001897e  push    r13
0x180018980  push    r14
0x180018982  push    r15
0x180018984  lea     rbp, [rsp-80h]
0x180018989  sub     rsp, 180h
0x180018990  mov     rax, cs:__security_cookie
0x180018997  xor     rax, rsp
0x18001899a  mov     [rbp+0B0h+var_40], rax
0x18001899e  mov     r12d, r8d
0x1800189a1  mov     r15, rdx
0x1800189a4  mov     rsi, rcx
0x1800189a7  mov     ebx, 100h
0x1800189ac  mov     r8d, ebx; Size
0x1800189af  lea     rcx, [rsp+1B0h+var_140]; void *
0x1800189b4  xor     edx, edx; Val
0x1800189b6  call    memset_0
0x1800189bb  mov     r8d, ebx
0x1800189be  lea     rdx, [rsp+1B0h+var_140]
0x1800189c3  lea     rcx, [rsp+1B0h+var_178]
0x1800189c8  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x1800189ce  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800189d2  xor     r13d, r13d
0x1800189d5  inc     rdi
0x1800189d8  cmp     [rsi+rdi*2], r13w
0x1800189dd  jnz     short loc_1800189D5
0x1800189df  test    edi, edi
0x1800189e1  jz      short loc_1800189F7
0x1800189e3  lea     eax, [rdi-1]
0x1800189e6  mov     r14d, 5Ch ; '\'
0x1800189ec  cmp     [rsi+rax*2], r14w
0x1800189f1  jnz     loc_18002ECDE
0x1800189f7  mov     r14d, r13d
0x1800189fa  mov     rdi, cs:?g_pDirMonitor@@3PEAVCDirMonitor@@EA; CDirMonitor * g_pDirMonitor
0x180018a01  mov     rcx, rdi
0x180018a04  call    cs:__imp_?ReadLock@CLKRHashTable@@QEBAXXZ; CLKRHashTable::ReadLock(void)
0x180018a0a  lea     r8, [rsp+1B0h+var_180]
0x180018a0f  mov     [rsp+1B0h+var_180], r13
0x180018a14  mov     rdx, rsi
0x180018a17  mov     rcx, rdi
0x180018a1a  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180018a20  mov     rbx, [rsp+1B0h+var_180]
0x180018a25  test    rbx, rbx
0x180018a28  jnz     loc_18002ED32
0x180018a2e  mov     rcx, rdi
0x180018a31  call    cs:__imp_?ReadUnlock@CLKRHashTable@@QEBAXXZ; CLKRHashTable::ReadUnlock(void)
0x180018a37  test    rbx, rbx
0x180018a3a  jnz     loc_180018AD2
0x180018a40  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180018a47  lea     r8d, [rbx+78h]; dwBytes
0x180018a4b  xor     edx, edx; dwFlags
0x180018a4d  call    cs:__imp_HeapAlloc
0x180018a53  mov     rbx, rax
0x180018a56  test    rax, rax
0x180018a59  jz      loc_180018B15
0x180018a5f  lea     rax, ??_7CDirMonitorEntry@@6B@; const CDirMonitorEntry::`vftable'
0x180018a66  mov     [rbx+8], r13d
0x180018a6a  mov     [rbx], rax
0x180018a6d  mov     rcx, rbx
0x180018a70  lea     rax, ??_7CASPDirMonitorEntry@@6B@; const CASPDirMonitorEntry::`vftable'
0x180018a77  mov     [rbx+10h], r13
0x180018a7b  mov     [rbx], rax
0x180018a7e  mov     rax, [rax+8]
0x180018a82  mov     [rbx+18h], r13
0x180018a86  mov     [rbx+20h], r13
0x180018a8a  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180018a92  mov     [rbx+30h], r13
0x180018a96  mov     [rbx+58h], r13d
0x180018a9a  mov     [rbx+60h], r13
0x180018a9e  mov     [rbx+68h], r13d
0x180018aa2  mov     [rbx+70h], r13d
0x180018aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018aab  mov     rax, [rbx]
0x180018aae  xor     edx, edx
0x180018ab0  mov     rcx, rbx
0x180018ab3  mov     rax, [rax+18h]
0x180018ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018abc  mov     r9d, r12d; int
0x180018abf  mov     r8, rsi; unsigned __int16 *
0x180018ac2  mov     rdx, rbx; struct CDirMonitorEntry *
0x180018ac5  call    ?Monitor@CDirMonitor@@QEAAHPEAVCDirMonitorEntry@@PEBGHKK@Z; CDirMonitor::Monitor(CDirMonitorEntry *,ushort const *,int,ulong,ulong)
0x180018aca  test    eax, eax
0x180018acc  jz      loc_18002ED56
0x180018ad2  lea     rcx, [rsp+1B0h+var_178]
0x180018ad7  mov     [r15], rbx
0x180018ada  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180018ae0  mov     eax, 1
0x180018ae5  mov     rcx, [rbp+0B0h+var_40]
0x180018ae9  xor     rcx, rsp; StackCookie
0x180018aec  call    __security_check_cookie
0x180018af1  mov     rbx, [rsp+1B0h+arg_10]
0x180018af9  add     rsp, 180h
0x180018b00  pop     r15
0x180018b02  pop     r14
0x180018b04  pop     r13
0x180018b06  pop     r12
0x180018b08  pop     rdi
0x180018b09  pop     rsi
0x180018b0a  pop     rbp
0x180018b0b  retn
0x180018b0c  test    r14d, r14d
0x180018b0f  jz      loc_18002ED7B
0x180018b15  mov     [r15], r13
0x180018b18  lea     rcx, [rsp+1B0h+var_178]
0x180018b1d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180018b23  xor     eax, eax
0x180018b25  jmp     short loc_180018AE5
0x18002ecde  lea     ebx, [rdi+2]
0x18002ece1  lea     edx, [rbx+rbx]
0x18002ece4  lea     rcx, [rsp+1B0h+var_178]
0x18002ece9  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002ecef  lea     rcx, [rsp+1B0h+var_178]
0x18002ecf4  test    al, al
0x18002ecf6  jz      loc_180018B1D
0x18002ecfc  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002ed02  mov     r8, rsi; Source
0x18002ed05  mov     edx, ebx; SizeInWords
0x18002ed07  mov     rcx, rax; Destination
0x18002ed0a  call    cs:__imp_wcscpy_s
0x18002ed10  lea     rcx, [rsp+1B0h+var_178]
0x18002ed15  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002ed1b  mov     ecx, edi
0x18002ed1d  mov     rsi, rax
0x18002ed20  mov     [rax+rcx*2], r14w
0x18002ed25  lea     ecx, [rdi+1]
0x18002ed28  mov     [rax+rcx*2], r13w
0x18002ed2d  jmp     loc_1800189F7
0x18002ed32  mov     eax, [rbx+68h]
0x18002ed35  test    eax, eax
0x18002ed37  jz      short loc_18002ED41
0x18002ed39  mov     rbx, r13
0x18002ed3c  jmp     loc_180018A2E
0x18002ed41  mov     rax, [rbx]
0x18002ed44  mov     rcx, rbx
0x18002ed47  mov     rax, [rax+8]
0x18002ed4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed50  nop
0x18002ed51  jmp     loc_180018A2E
0x18002ed56  mov     rax, [rbx]
0x18002ed59  mov     rcx, rbx
0x18002ed5c  mov     rax, [rax+10h]
0x18002ed60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed65  call    cs:__imp_GetLastError
0x18002ed6b  cmp     eax, 0B7h
0x18002ed70  jnz     loc_180018B15
0x18002ed76  jmp     loc_180018B0C
0x18002ed7b  mov     r14d, 1
0x18002ed81  jmp     loc_1800189FA
```
