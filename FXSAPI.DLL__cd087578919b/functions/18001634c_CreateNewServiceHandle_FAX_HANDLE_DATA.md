# CreateNewServiceHandle(_FAX_HANDLE_DATA *)

- ea: `0x18001634c`
- end: `0x18001641b`
- name: `?CreateNewServiceHandle@@YAPEAU_HANDLE_ENTRY@@PEAU_FAX_HANDLE_DATA@@@Z`
- size: `207`
- prototype: `struct _HANDLE_ENTRY *__fastcall(struct _FAX_HANDLE_DATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180015040`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180016278`
- `0x18001634c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180016397`
- `KERNEL32!InitializeCriticalSection` at `0x180016397`
- `KERNEL32!DeleteCriticalSection` at `0x180016401`
- `KERNEL32!DeleteCriticalSection` at `0x180016401`
- `KERNEL32!GetLastError` at `0x1800163bb`
- `KERNEL32!GetLastError` at `0x1800163bb`

## pseudocode

```c
struct _HANDLE_ENTRY *__fastcall CreateNewServiceHandle(struct _FAX_HANDLE_DATA *a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 NewHandle; // rdi
  DWORD LastError; // eax
  DWORD v5; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_09bf480e846a3bc6581fd59195b9f412_Traceguids);
  }
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 24);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 24));
  NewHandle = CreateNewHandle(a1, 0, 0, 0);
  if ( !NewHandle )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_09bf480e846a3bc6581fd59195b9f412_Traceguids, LastError);
    }
    if ( v5 )
      DeleteCriticalSection(v2);
  }
  return (struct _HANDLE_ENTRY *)NewHandle;
}

```

## disassembly

```asm
0x18001634c  push    rbx
0x18001634e  push    rsi
0x18001634f  push    rdi
0x180016350  push    r14
0x180016352  sub     rsp, 28h
0x180016356  mov     rbx, rcx
0x180016359  mov     rcx, cs:WPP_GLOBAL_Control
0x180016360  lea     r14, WPP_GLOBAL_Control
0x180016367  cmp     rcx, r14
0x18001636a  jz      short loc_180016390
0x18001636c  test    dword ptr [rcx+1Ch], 1000h
0x180016373  jz      short loc_180016390
0x180016375  cmp     byte ptr [rcx+19h], 5
0x180016379  jb      short loc_180016390
0x18001637b  mov     rcx, [rcx+10h]
0x18001637f  lea     r8, WPP_09bf480e846a3bc6581fd59195b9f412_Traceguids
0x180016386  mov     edx, 0Bh
0x18001638b  call    WPP_SF_
0x180016390  lea     rsi, [rbx+18h]
0x180016394  mov     rcx, rsi; lpCriticalSection
0x180016397  call    cs:__imp_InitializeCriticalSection
0x18001639e  nop     dword ptr [rax+rax+00h]
0x1800163a3  xor     r9d, r9d
0x1800163a6  xor     r8d, r8d
0x1800163a9  xor     edx, edx
0x1800163ab  mov     rcx, rbx
0x1800163ae  call    ?CreateNewHandle@@YAPEAU_HANDLE_ENTRY@@PEAU_FAX_HANDLE_DATA@@W4FaxHandleType@@KPEAX@Z; CreateNewHandle(_FAX_HANDLE_DATA *,FaxHandleType,ulong,void *)
0x1800163b3  mov     rdi, rax
0x1800163b6  test    rax, rax
0x1800163b9  jnz     short loc_18001640D
0x1800163bb  call    cs:__imp_GetLastError
0x1800163c2  nop     dword ptr [rax+rax+00h]
0x1800163c7  mov     ebx, eax
0x1800163c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163d0  cmp     rcx, r14
0x1800163d3  jz      short loc_1800163FA
0x1800163d5  test    dword ptr [rcx+1Ch], 1000h
0x1800163dc  jz      short loc_1800163FA
0x1800163de  cmp     byte ptr [rcx+19h], 2
0x1800163e2  jb      short loc_1800163FA
0x1800163e4  mov     rcx, [rcx+10h]
0x1800163e8  lea     edx, [rdi+0Ch]
0x1800163eb  mov     r9d, eax
0x1800163ee  lea     r8, WPP_09bf480e846a3bc6581fd59195b9f412_Traceguids
0x1800163f5  call    WPP_SF_d
0x1800163fa  test    ebx, ebx
0x1800163fc  jz      short loc_18001640D
0x1800163fe  mov     rcx, rsi; lpCriticalSection
0x180016401  call    cs:__imp_DeleteCriticalSection
0x180016408  nop     dword ptr [rax+rax+00h]
0x18001640d  mov     rax, rdi
0x180016410  add     rsp, 28h
0x180016414  pop     r14
0x180016416  pop     rdi
0x180016417  pop     rsi
0x180016418  pop     rbx
0x180016419  retn
```
