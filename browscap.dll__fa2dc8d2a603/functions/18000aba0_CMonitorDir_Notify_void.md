# CMonitorDir::Notify(void)

- ea: `0x18000aba0`
- end: `0x18000ac3c`
- name: `?Notify@CMonitorDir@@UEAAXXZ`
- size: `156`
- prototype: `void __fastcall(CMonitorDir *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000a8ac`
- `0x18000aba0`
- `0x18000d010`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x18000abe9`
- `KERNEL32!CompareFileTime` at `0x18000abe9`
- `KERNEL32!FindNextChangeNotification` at `0x18000ac35`

## pseudocode

```c
void __fastcall CMonitorDir::Notify(CMonitorDir *this)
{
  __int64 v1; // rdx
  __int64 i; // rbp
  __int64 v4; // rsi
  __int64 v5; // rcx
  FILETIME FileTime1; // [rsp+50h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 5);
  for ( i = 0; (unsigned int)i < (unsigned __int64)((*((_QWORD *)this + 6) - v1) >> 3); v1 = *((_QWORD *)this + 5) )
  {
    v4 = *(_QWORD *)(v1 + 8 * i);
    FileTime1 = 0;
    if ( !CMonitorFile::GetFileTime((CMonitorFile *)v4, &FileTime1)
      || CompareFileTime(&FileTime1, (const FILETIME *)(v4 + 16)) )
    {
      v5 = *(_QWORD *)(v4 + 40);
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    }
    i = (unsigned int)(i + 1);
    *(FILETIME *)(v4 + 16) = FileTime1;
  }
  FindNextChangeNotification(*((HANDLE *)this + 7));
}

```

## disassembly

```asm
0x18000aba0  push    rbx
0x18000aba2  push    rbp
0x18000aba3  push    rsi
0x18000aba4  push    rdi
0x18000aba5  sub     rsp, 28h
0x18000aba9  mov     rdx, [rcx+28h]
0x18000abad  xor     ebp, ebp
0x18000abaf  mov     rax, [rcx+30h]
0x18000abb3  mov     rdi, rcx
0x18000abb6  sub     rax, rdx
0x18000abb9  sar     rax, 3
0x18000abbd  test    rax, rax
0x18000abc0  jz      short loc_18000AC29
0x18000abc2  mov     rsi, [rdx+rbp*8]
0x18000abc6  lea     rdx, [rsp+48h+FileTime1]; struct _FILETIME *
0x18000abcb  mov     rcx, rsi; this
0x18000abce  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], 0
0x18000abd7  call    ?GetFileTime@CMonitorFile@@AEAA_NAEAU_FILETIME@@@Z; CMonitorFile::GetFileTime(_FILETIME &)
0x18000abdc  test    al, al
0x18000abde  jz      short loc_18000ABF3
0x18000abe0  lea     rdx, [rsi+10h]; lpFileTime2
0x18000abe4  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x18000abe9  call    cs:__imp_CompareFileTime
0x18000abef  test    eax, eax
0x18000abf1  jz      short loc_18000AC08
0x18000abf3  mov     rcx, [rsi+28h]
0x18000abf7  test    rcx, rcx
0x18000abfa  jz      short loc_18000AC08
0x18000abfc  mov     rax, [rcx]
0x18000abff  mov     rax, [rax+8]
0x18000ac03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac08  mov     rax, qword ptr [rsp+48h+FileTime1.dwLowDateTime]
0x18000ac0d  inc     ebp
0x18000ac0f  mov     [rsi+10h], rax
0x18000ac13  mov     rdx, [rdi+28h]
0x18000ac17  mov     rcx, [rdi+30h]
0x18000ac1b  sub     rcx, rdx
0x18000ac1e  mov     eax, ebp
0x18000ac20  sar     rcx, 3
0x18000ac24  cmp     rax, rcx
0x18000ac27  jb      short loc_18000ABC2
0x18000ac29  mov     rcx, [rdi+38h]
0x18000ac2d  add     rsp, 28h
0x18000ac31  pop     rdi
0x18000ac32  pop     rsi
0x18000ac33  pop     rbp
0x18000ac34  pop     rbx
0x18000ac35  jmp     cs:__imp_FindNextChangeNotification
```
