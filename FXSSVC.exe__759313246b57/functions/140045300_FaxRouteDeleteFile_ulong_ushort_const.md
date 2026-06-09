# FaxRouteDeleteFile(ulong,ushort const *)

- ea: `0x140045300`
- end: `0x1400454f2`
- name: `?FaxRouteDeleteFile@@YAJKPEBG@Z`
- size: `498`
- prototype: `int(unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x140045300`
- `0x14006998c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14004531c`
- `KERNEL32!SetLastError` at `0x140045421`
- `KERNEL32!SetLastError` at `0x14004531c`
- `KERNEL32!SetLastError` at `0x140045421`
- `KERNEL32!DeleteFileW` at `0x140045462`
- `KERNEL32!DeleteFileW` at `0x140045462`
- `KERNEL32!EnterCriticalSection` at `0x140045337`
- `KERNEL32!EnterCriticalSection` at `0x14004534a`
- `KERNEL32!EnterCriticalSection` at `0x1400453d0`
- `KERNEL32!EnterCriticalSection` at `0x140045495`
- `KERNEL32!EnterCriticalSection` at `0x1400454a8`
- `KERNEL32!EnterCriticalSection` at `0x140045337`
- `KERNEL32!EnterCriticalSection` at `0x14004534a`
- `KERNEL32!EnterCriticalSection` at `0x1400453d0`
- `KERNEL32!EnterCriticalSection` at `0x140045495`
- `KERNEL32!EnterCriticalSection` at `0x1400454a8`
- `KERNEL32!LeaveCriticalSection` at `0x14004537c`
- `KERNEL32!LeaveCriticalSection` at `0x14004538f`
- `KERNEL32!LeaveCriticalSection` at `0x140045403`
- `KERNEL32!LeaveCriticalSection` at `0x140045430`
- `KERNEL32!LeaveCriticalSection` at `0x140045482`
- `KERNEL32!LeaveCriticalSection` at `0x1400454c1`
- `KERNEL32!LeaveCriticalSection` at `0x1400454d4`
- `KERNEL32!LeaveCriticalSection` at `0x14004537c`
- `KERNEL32!LeaveCriticalSection` at `0x14004538f`
- `KERNEL32!LeaveCriticalSection` at `0x140045403`
- `KERNEL32!LeaveCriticalSection` at `0x140045430`
- `KERNEL32!LeaveCriticalSection` at `0x140045482`
- `KERNEL32!LeaveCriticalSection` at `0x1400454c1`
- `KERNEL32!LeaveCriticalSection` at `0x1400454d4`
- `msvcrt!_wcsicmp` at `0x1400453e6`
- `msvcrt!_wcsicmp` at `0x1400453e6`

## pseudocode

```c
__int64 __fastcall FaxRouteDeleteFile(int a1, const unsigned __int16 *a2)
{
  DWORD v4; // ecx
  struct _LIST_ENTRY *i; // rbx
  const wchar_t **Flink; // rdi
  unsigned int v8; // ebp
  const wchar_t *v9; // r12
  const wchar_t **v10; // rax
  const wchar_t *v11; // rdx
  const WCHAR *v12; // rcx

  if ( !a2 )
  {
    v4 = 87;
LABEL_3:
    SetLastError(v4);
    return 0xFFFFFFFFLL;
  }
  EnterCriticalSection(&g_CsJob);
  EnterCriticalSection(&g_CsQueue);
  for ( i = g_QueueListHead.Flink; i != &g_QueueListHead; i = i->Flink )
  {
    if ( LODWORD(i[2].Flink) == a1 )
      goto LABEL_10;
  }
  i = 0;
LABEL_10:
  LeaveCriticalSection(&g_CsQueue);
  LeaveCriticalSection(&g_CsJob);
  if ( !i )
  {
    v4 = 13;
    goto LABEL_3;
  }
  Flink = (const wchar_t **)i[106].Flink;
  if ( Flink == (const wchar_t **)&i[106] )
  {
    v4 = 18;
    goto LABEL_3;
  }
  v8 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)&i[107].Blink);
  while ( 1 )
  {
    v9 = *Flink;
    if ( !_wcsicmp(a2, Flink[2]) )
      break;
    ++v8;
    Flink = (const wchar_t **)v9;
    if ( v9 == (const wchar_t *)&i[106] )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)&i[107].Blink);
      v4 = 2;
      goto LABEL_3;
    }
  }
  if ( v8 == 1 )
  {
    SetLastError(0xDu);
    LeaveCriticalSection((LPCRITICAL_SECTION)&i[107].Blink);
    return 0xFFFFFFFFLL;
  }
  v10 = (const wchar_t **)Flink[1];
  v11 = *Flink;
  *v10 = *Flink;
  *((_QWORD *)v11 + 1) = v10;
  v12 = Flink[2];
  *Flink = 0;
  Flink[1] = 0;
  DeleteFileW(v12);
  pMemFree((LPVOID)Flink[2]);
  pMemFree(Flink);
  LeaveCriticalSection((LPCRITICAL_SECTION)&i[107].Blink);
  EnterCriticalSection(&g_CsJob);
  EnterCriticalSection(&g_CsQueue);
  --LODWORD(i[107].Flink);
  LeaveCriticalSection(&g_CsQueue);
  LeaveCriticalSection(&g_CsJob);
  return v8;
}

```

## disassembly

```asm
0x140045300  push    rbx
0x140045302  push    rbp
0x140045303  push    rsi
0x140045304  push    rdi
0x140045305  push    r12
0x140045307  push    r14
0x140045309  push    r15
0x14004530b  sub     rsp, 20h
0x14004530f  mov     r15, rdx
0x140045312  mov     edi, ecx
0x140045314  test    rdx, rdx
0x140045317  jnz     short loc_140045330
0x140045319  lea     ecx, [rdx+57h]; dwErrCode
0x14004531c  call    cs:__imp_SetLastError
0x140045323  nop     dword ptr [rax+rax+00h]
0x140045328  or      eax, 0FFFFFFFFh
0x14004532b  jmp     loc_1400454E2
0x140045330  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140045337  call    cs:__imp_EnterCriticalSection
0x14004533e  nop     dword ptr [rax+rax+00h]
0x140045343  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004534a  call    cs:__imp_EnterCriticalSection
0x140045351  nop     dword ptr [rax+rax+00h]
0x140045356  mov     rbx, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x14004535d  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x140045364  jmp     short loc_14004536E
0x140045366  cmp     [rbx+20h], edi
0x140045369  jz      short loc_140045375
0x14004536b  mov     rbx, [rbx]
0x14004536e  cmp     rbx, rax
0x140045371  jnz     short loc_140045366
0x140045373  xor     ebx, ebx
0x140045375  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004537c  call    cs:__imp_LeaveCriticalSection
0x140045383  nop     dword ptr [rax+rax+00h]
0x140045388  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004538f  call    cs:__imp_LeaveCriticalSection
0x140045396  nop     dword ptr [rax+rax+00h]
0x14004539b  test    rbx, rbx
0x14004539e  jnz     short loc_1400453A8
0x1400453a0  lea     ecx, [rbx+0Dh]
0x1400453a3  jmp     loc_14004531C
0x1400453a8  lea     r14, [rbx+6A0h]
0x1400453af  mov     rdi, [r14]
0x1400453b2  cmp     rdi, r14
0x1400453b5  jnz     short loc_1400453C1
0x1400453b7  mov     ecx, 12h
0x1400453bc  jmp     loc_14004531C
0x1400453c1  lea     rsi, [rbx+6B8h]
0x1400453c8  mov     ebp, 1
0x1400453cd  mov     rcx, rsi; lpCriticalSection
0x1400453d0  call    cs:__imp_EnterCriticalSection
0x1400453d7  nop     dword ptr [rax+rax+00h]
0x1400453dc  mov     rdx, [rdi+10h]; String2
0x1400453e0  mov     rcx, r15; String1
0x1400453e3  mov     r12, [rdi]
0x1400453e6  call    cs:__imp__wcsicmp
0x1400453ed  nop     dword ptr [rax+rax+00h]
0x1400453f2  test    eax, eax
0x1400453f4  jz      short loc_140045419
0x1400453f6  inc     ebp
0x1400453f8  mov     rdi, r12
0x1400453fb  cmp     r12, r14
0x1400453fe  jnz     short loc_1400453DC
0x140045400  mov     rcx, rsi; lpCriticalSection
0x140045403  call    cs:__imp_LeaveCriticalSection
0x14004540a  nop     dword ptr [rax+rax+00h]
0x14004540f  mov     ecx, 2
0x140045414  jmp     loc_14004531C
0x140045419  cmp     ebp, 1
0x14004541c  jnz     short loc_140045441
0x14004541e  lea     ecx, [rbp+0Ch]; dwErrCode
0x140045421  call    cs:__imp_SetLastError
0x140045428  nop     dword ptr [rax+rax+00h]
0x14004542d  mov     rcx, rsi; lpCriticalSection
0x140045430  call    cs:__imp_LeaveCriticalSection
0x140045437  nop     dword ptr [rax+rax+00h]
0x14004543c  jmp     loc_140045328
0x140045441  mov     rax, [rdi+8]
0x140045445  mov     rdx, [rdi]
0x140045448  mov     [rax], rdx
0x14004544b  mov     [rdx+8], rax
0x14004544f  mov     rcx, [rdi+10h]; lpFileName
0x140045453  mov     qword ptr [rdi], 0
0x14004545a  mov     qword ptr [rdi+8], 0
0x140045462  call    cs:__imp_DeleteFileW
0x140045469  nop     dword ptr [rax+rax+00h]
0x14004546e  mov     rcx, [rdi+10h]; lpMem
0x140045472  call    pMemFree
0x140045477  mov     rcx, rdi; lpMem
0x14004547a  call    pMemFree
0x14004547f  mov     rcx, rsi; lpCriticalSection
0x140045482  call    cs:__imp_LeaveCriticalSection
0x140045489  nop     dword ptr [rax+rax+00h]
0x14004548e  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140045495  call    cs:__imp_EnterCriticalSection
0x14004549c  nop     dword ptr [rax+rax+00h]
0x1400454a1  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400454a8  call    cs:__imp_EnterCriticalSection
0x1400454af  nop     dword ptr [rax+rax+00h]
0x1400454b4  dec     dword ptr [rbx+6B0h]
0x1400454ba  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400454c1  call    cs:__imp_LeaveCriticalSection
0x1400454c8  nop     dword ptr [rax+rax+00h]
0x1400454cd  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400454d4  call    cs:__imp_LeaveCriticalSection
0x1400454db  nop     dword ptr [rax+rax+00h]
0x1400454e0  mov     eax, ebp
0x1400454e2  add     rsp, 20h
0x1400454e6  pop     r15
0x1400454e8  pop     r14
0x1400454ea  pop     r12
0x1400454ec  pop     rdi
0x1400454ed  pop     rsi
0x1400454ee  pop     rbp
0x1400454ef  pop     rbx
0x1400454f0  retn
```
