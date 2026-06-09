# CloseFaxHandle(_HANDLE_ENTRY *)

- ea: `0x18001618c`
- end: `0x18001626f`
- name: `?CloseFaxHandle@@YAXPEAU_HANDLE_ENTRY@@@Z`
- size: `227`
- prototype: `void __fastcall(struct _HANDLE_ENTRY *lpMem)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180014d30`
- `0x180015040`
- `0x18001a368`
- `0x18001c4d0`

## callees

- `0x18000abe4`
- `0x18001618c`
- `0x18002bb58`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180016239`
- `KERNEL32!DeleteCriticalSection` at `0x180016239`
- `KERNEL32!EnterCriticalSection` at `0x1800161e0`
- `KERNEL32!EnterCriticalSection` at `0x1800161e0`
- `KERNEL32!LeaveCriticalSection` at `0x18001622a`
- `KERNEL32!LeaveCriticalSection` at `0x180016252`
- `KERNEL32!LeaveCriticalSection` at `0x18001622a`
- `KERNEL32!LeaveCriticalSection` at `0x180016252`

## pseudocode

```c
void __fastcall CloseFaxHandle(struct _HANDLE_ENTRY *lpMem)
{
  __int64 v2; // rdi
  __int64 v3; // rcx
  _QWORD *v4; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_09bf480e846a3bc6581fd59195b9f412_Traceguids);
  }
  v2 = *((_QWORD *)lpMem + 4);
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 24));
  v3 = *(_QWORD *)lpMem;
  v4 = (_QWORD *)*((_QWORD *)lpMem + 1);
  *v4 = *(_QWORD *)lpMem;
  *(_QWORD *)(v3 + 8) = v4;
  *(_QWORD *)lpMem = 0;
  *((_QWORD *)lpMem + 1) = 0;
  *((_DWORD *)lpMem + 4) = 0xFFFF;
  pMemFree(lpMem);
  if ( (*(_DWORD *)(v2 + 64))-- == 1 )
  {
    pMemFree(*(LPVOID *)(v2 + 72));
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 24));
    DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 24));
    pMemFree((LPVOID)v2);
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 24));
  }
}

```

## disassembly

```asm
0x18001618c  mov     [rsp+arg_8], rbx
0x180016191  mov     [rsp+arg_10], rsi
0x180016196  push    rdi
0x180016197  sub     rsp, 20h
0x18001619b  mov     rsi, rcx
0x18001619e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161a5  lea     rax, WPP_GLOBAL_Control
0x1800161ac  cmp     rcx, rax
0x1800161af  jz      short loc_1800161D5
0x1800161b1  test    dword ptr [rcx+1Ch], 1000h
0x1800161b8  jz      short loc_1800161D5
0x1800161ba  cmp     byte ptr [rcx+19h], 5
0x1800161be  jb      short loc_1800161D5
0x1800161c0  mov     rcx, [rcx+10h]
0x1800161c4  lea     r8, WPP_09bf480e846a3bc6581fd59195b9f412_Traceguids
0x1800161cb  mov     edx, 0Dh
0x1800161d0  call    WPP_SF_
0x1800161d5  mov     rdi, [rsi+20h]
0x1800161d9  lea     rbx, [rdi+18h]
0x1800161dd  mov     rcx, rbx; lpCriticalSection
0x1800161e0  call    cs:__imp_EnterCriticalSection
0x1800161e7  nop     dword ptr [rax+rax+00h]
0x1800161ec  mov     rcx, [rsi]
0x1800161ef  mov     rax, [rsi+8]
0x1800161f3  mov     [rax], rcx
0x1800161f6  mov     [rcx+8], rax
0x1800161fa  mov     rcx, rsi; lpMem
0x1800161fd  mov     qword ptr [rsi], 0
0x180016204  mov     qword ptr [rsi+8], 0
0x18001620c  mov     dword ptr [rsi+10h], 0FFFFh
0x180016213  call    pMemFree
0x180016218  add     dword ptr [rdi+40h], 0FFFFFFFFh
0x18001621c  jnz     short loc_18001624F
0x18001621e  mov     rcx, [rdi+48h]; lpMem
0x180016222  call    pMemFree
0x180016227  mov     rcx, rbx; lpCriticalSection
0x18001622a  call    cs:__imp_LeaveCriticalSection
0x180016231  nop     dword ptr [rax+rax+00h]
0x180016236  mov     rcx, rbx; lpCriticalSection
0x180016239  call    cs:__imp_DeleteCriticalSection
0x180016240  nop     dword ptr [rax+rax+00h]
0x180016245  mov     rcx, rdi; lpMem
0x180016248  call    pMemFree
0x18001624d  jmp     short loc_18001625E
0x18001624f  mov     rcx, rbx; lpCriticalSection
0x180016252  call    cs:__imp_LeaveCriticalSection
0x180016259  nop     dword ptr [rax+rax+00h]
0x18001625e  mov     rbx, [rsp+28h+arg_8]
0x180016263  mov     rsi, [rsp+28h+arg_10]
0x180016268  add     rsp, 20h
0x18001626c  pop     rdi
0x18001626d  retn
```
