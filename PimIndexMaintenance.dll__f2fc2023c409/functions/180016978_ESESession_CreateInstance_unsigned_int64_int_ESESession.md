# ESESession::CreateInstance(unsigned __int64,int,ESESession * *)

- ea: `0x180016978`
- end: `0x180016a69`
- name: `?CreateInstance@ESESession@@SAJ_KHPEAPEAV1@@Z`
- size: `241`
- prototype: `__int64 __fastcall(unsigned __int64, int, struct ESESession **)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000ee40`
- `0x180011f70`
- `0x180013768`
- `0x18001626c`

## callees

- `0x1800012fc`
- `0x180002da8`
- `0x18000d180`
- `0x18000e544`
- `0x180016978`
- `0x180018e18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800169d2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800169d2`

## string_xrefs

- `0x180016a1f`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180016a4a`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::CreateInstance(unsigned __int64 a1, int a2, struct ESESession **a3)
{
  char *v6; // rax
  char *v7; // rbx
  int v8; // eax
  unsigned int v9; // edi

  v6 = (char *)operator new(0x170u);
  v7 = v6;
  if ( v6 )
  {
    *(_QWORD *)v6 = &ESESession::`vftable';
    *((_QWORD *)v6 + 2) = 0xFFFFFFFFLL;
    *((_DWORD *)v6 + 6) = -1;
    *((_QWORD *)v6 + 4) = -1;
    *((_QWORD *)v6 + 5) = -1;
    *((_QWORD *)v6 + 6) = -1;
    *((_QWORD *)v6 + 7) = -1;
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v6 + 64), 0, 0);
    `vector constructor iterator'(v7 + 104, 0x30u, 5u, (void *(*)(void *))ESESession::TableInfo::TableInfo);
    *((_QWORD *)v7 + 44) = 0;
    *((_DWORD *)v7 + 90) = 0;
    v8 = ESESession::_Init((ESESession *)v7, a2, a1);
    v9 = v8;
    if ( v8 >= 0 )
    {
      *a3 = (struct ESESession *)v7;
      return 0;
    }
    else
    {
      Log_HREvent(
        (unsigned int)v8,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
        130);
      tlx::_delete<ESESession>(v7);
      return v9;
    }
  }
  else
  {
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      128);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180016978  push    rbx
0x18001697a  push    rbp
0x18001697b  push    rsi
0x18001697c  push    rdi
0x18001697d  sub     rsp, 38h
0x180016981  mov     rbp, rcx
0x180016984  mov     rsi, r8
0x180016987  mov     ecx, 170h; Size
0x18001698c  mov     edi, edx
0x18001698e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016993  xor     edx, edx; dwSpinCount
0x180016995  mov     rbx, rax
0x180016998  test    rax, rax
0x18001699b  jz      loc_180016A45
0x1800169a1  lea     rax, ??_7ESESession@@6B@; const ESESession::`vftable'
0x1800169a8  xor     r8d, r8d; Flags
0x1800169ab  mov     [rbx], rax
0x1800169ae  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800169b2  mov     eax, 0FFFFFFFFh
0x1800169b7  mov     [rbx+10h], rax
0x1800169bb  mov     [rbx+18h], eax
0x1800169be  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800169c2  mov     [rbx+20h], rax
0x1800169c6  mov     [rbx+28h], rax
0x1800169ca  mov     [rbx+30h], rax
0x1800169ce  mov     [rbx+38h], rax
0x1800169d2  call    cs:__imp_InitializeCriticalSectionEx
0x1800169d8  mov     edx, 30h ; '0'; unsigned __int64
0x1800169dd  lea     rcx, [rbx+68h]; void *
0x1800169e1  lea     r9, ??0TableInfo@ESESession@@QEAA@XZ; void *(*)(void *)
0x1800169e8  lea     r8d, [rdx-2Bh]; unsigned __int64
0x1800169ec  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800169f1  mov     r8, rbp; unsigned __int64
0x1800169f4  mov     qword ptr [rbx+160h], 0
0x1800169ff  mov     edx, edi; int
0x180016a01  mov     dword ptr [rbx+168h], 0
0x180016a0b  mov     rcx, rbx; this
0x180016a0e  call    ?_Init@ESESession@@AEAAJH_K@Z; ESESession::_Init(int,unsigned __int64)
0x180016a13  mov     edi, eax
0x180016a15  test    eax, eax
0x180016a17  jns     short loc_180016A3E
0x180016a19  mov     r9d, 82h
0x180016a1f  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016a26  mov     edx, 1
0x180016a2b  mov     ecx, eax
0x180016a2d  call    Log_HREvent
0x180016a32  mov     rcx, rbx
0x180016a35  call    ??$_delete@VESESession@@@tlx@@YAXPEAVESESession@@@Z; tlx::_delete<ESESession>(ESESession *)
0x180016a3a  mov     eax, edi
0x180016a3c  jmp     short loc_180016A60
0x180016a3e  mov     [rsi], rbx
0x180016a41  xor     eax, eax
0x180016a43  jmp     short loc_180016A60
0x180016a45  mov     ebx, 8007000Eh
0x180016a4a  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016a51  mov     ecx, ebx
0x180016a53  mov     r9d, 80h
0x180016a59  call    Log_HREvent
0x180016a5e  mov     eax, ebx
0x180016a60  add     rsp, 38h
0x180016a64  pop     rdi
0x180016a65  pop     rsi
0x180016a66  pop     rbp
0x180016a67  pop     rbx
0x180016a68  retn
```
