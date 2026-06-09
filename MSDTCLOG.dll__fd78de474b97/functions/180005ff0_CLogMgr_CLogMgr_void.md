# CLogMgr::~CLogMgr(void)

- ea: `0x180005ff0`
- end: `0x1800061b7`
- name: `??1CLogMgr@@QEAA@XZ`
- size: `455`
- prototype: `void __fastcall(CLogMgr *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180006300`
- `0x180006ca0`
- `0x180008890`

## callees

- `0x180005ff0`
- `0x180006e80`
- `0x180006f8c`
- `0x18000e6fc`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006178`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000618d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000619c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006178`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000618d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000619c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800060e9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800060e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000608c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006150`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006163`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000608c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006150`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006163`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall CLogMgr::~CLogMgr(void (***this)(void))
{
  void (***v1)(void); // rbx
  int v2; // r14d
  char *v3; // rsi
  void (**v4)(void); // rcx
  BOOL v5; // eax
  unsigned __int16 *v6; // rdx
  void (**v7)(void); // rcx
  void (**v8)(void); // rcx
  int v9; // [rsp+20h] [rbp-38h] BYREF
  ulong v10; // [rsp+24h] [rbp-34h] BYREF
  int v11; // [rsp+28h] [rbp-30h]
  char *v12; // [rsp+30h] [rbp-28h]
  char *v14; // [rsp+68h] [rbp+10h]

  v1 = this;
  *this = (void (**)(void))&CLogMgr::`vftable';
  v2 = 1;
  v11 = 1;
  v3 = (char *)(this + 51);
  v14 = (char *)(this + 51);
  v12 = (char *)(this + 51);
  try
  {
    (*this[51])();
    if ( *((_DWORD *)v1 + 3) )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
    }
    else
    {
      *((_DWORD *)v1 + 3) = 1;
      if ( !v1[50] || !v1[49] || !v1[78] )
        *((_DWORD *)v1 + 4) = 1;
      v4 = v1[73];
      if ( v4 && (v5 = CloseHandle(v4), v1[73] = 0, !v5) && *((_DWORD *)v1 + 122) )
        v2 = 0;
      else
        *((_DWORD *)v1 + 122) = 1;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
      if ( !*((_DWORD *)v1 + 4) )
      {
        if ( v2 )
        {
          CLogMgr::_DoCheckpoint((CLogMgr *)v1, 1, 0);
        }
        else if ( WaitForSingleObjectEx(v1[58], 0xFFFFFFFF, 0) == -1 )
        {
          UtsemWin32Error(L"WaitForSingleObjectEx fails in CEventSem::Wait()", v6, 0x74u);
        }
      }
      v11 = 1;
      v12 = v3;
      (**(void (__fastcall ***)(char *))v3)(v3);
      CLogMgr::_Cleanup((CLogMgr *)v1);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  catch ( long v9 )
  {
    if ( v9 != -1073737699 )
      __int2c();
    v3 = v14;
    v1 = this;
  }
  catch ( ulong v10 )
  {
    if ( v10 != -1073737699 )
      __int2c();
    v3 = v14;
    v1 = this;
  }
  v7 = v1[60];
  if ( v7 )
    CloseHandle(v7);
  v8 = v1[58];
  if ( v8 )
    CloseHandle(v8);
  *(_QWORD *)v3 = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  v1[38] = (void (**)(void))&CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 39));
  v1[5] = (void (**)(void))&CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 6));
}

```

## disassembly

```asm
0x180005ff0  mov     r11, rsp
0x180005ff3  mov     [r11+18h], rbx
0x180005ff7  mov     [r11+20h], rsi
0x180005ffb  mov     [r11+8], rcx
0x180005fff  push    rdi
0x180006000  push    r14
0x180006002  push    r15
0x180006004  sub     rsp, 40h
0x180006008  mov     rbx, rcx
0x18000600b  lea     rax, ??_7CLogMgr@@6B@; const CLogMgr::`vftable'
0x180006012  mov     [rcx], rax
0x180006015  mov     r15d, 1
0x18000601b  mov     r14d, r15d
0x18000601e  mov     [r11-30h], r15d
0x180006022  lea     rsi, [rcx+198h]
0x180006029  mov     [rsp+58h+arg_8], rsi
0x18000602e  mov     [r11-28h], rsi
0x180006032  mov     rax, [rsi]
0x180006035  mov     rcx, rsi
0x180006038  mov     rax, [rax]
0x18000603b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006040  nop
0x180006041  xor     edi, edi
0x180006043  cmp     [rbx+0Ch], edi
0x180006046  jz      short loc_18000605D
0x180006048  mov     rax, [rsi]
0x18000604b  mov     rcx, rsi
0x18000604e  mov     rax, [rax+8]
0x180006052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006057  nop
0x180006058  jmp     loc_180006138
0x18000605d  mov     [rbx+0Ch], r15d
0x180006061  cmp     [rbx+190h], rdi
0x180006068  jz      short loc_18000607C
0x18000606a  cmp     [rbx+188h], rdi
0x180006071  jz      short loc_18000607C
0x180006073  cmp     [rbx+270h], rdi
0x18000607a  jnz     short loc_180006080
0x18000607c  mov     [rbx+10h], r15d
0x180006080  mov     rcx, [rbx+248h]; hObject
0x180006087  test    rcx, rcx
0x18000608a  jz      short loc_1800060AA
0x18000608c  call    cs:__imp_CloseHandle
0x180006092  mov     [rbx+248h], rdi
0x180006099  test    eax, eax
0x18000609b  jnz     short loc_1800060AA
0x18000609d  cmp     [rbx+1E8h], edi
0x1800060a3  jz      short loc_1800060AA
0x1800060a5  mov     r14d, edi
0x1800060a8  jmp     short loc_1800060B1
0x1800060aa  mov     [rbx+1E8h], r15d
0x1800060b1  mov     rax, [rsi]
0x1800060b4  mov     rcx, rsi
0x1800060b7  mov     rax, [rax+8]
0x1800060bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c0  nop
0x1800060c1  cmp     [rbx+10h], edi
0x1800060c4  jnz     short loc_180006106
0x1800060c6  xor     r8d, r8d; int
0x1800060c9  test    r14d, r14d
0x1800060cc  jz      short loc_1800060DB
0x1800060ce  mov     edx, r15d; int
0x1800060d1  mov     rcx, rbx; this
0x1800060d4  call    ?_DoCheckpoint@CLogMgr@@AEAAXHH@Z; CLogMgr::_DoCheckpoint(int,int)
0x1800060d9  jmp     short loc_180006106
0x1800060db  or      r14d, 0FFFFFFFFh
0x1800060df  mov     edx, r14d; dwMilliseconds
0x1800060e2  mov     rcx, [rbx+1D0h]; hHandle
0x1800060e9  call    cs:__imp_WaitForSingleObjectEx
0x1800060ef  cmp     eax, r14d
0x1800060f2  jnz     short loc_180006106
0x1800060f4  mov     r8d, 74h ; 't'; unsigned int
0x1800060fa  lea     rcx, aWaitforsingleo; "WaitForSingleObjectEx fails in CEventSe"...
0x180006101  call    ?UtsemWin32Error@@YAXPEAG0K@Z; UtsemWin32Error(ushort *,ushort *,ulong)
0x180006106  mov     [rsp+58h+var_30], r15d
0x18000610b  mov     [rsp+58h+var_28], rsi
0x180006110  mov     rax, [rsi]
0x180006113  mov     rcx, rsi
0x180006116  mov     rax, [rax]
0x180006119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000611e  nop
0x18000611f  mov     rcx, rbx; this
0x180006122  call    ?_Cleanup@CLogMgr@@AEAAXXZ; CLogMgr::_Cleanup(void)
0x180006127  nop
0x180006128  mov     rax, [rsi]
0x18000612b  mov     rcx, rsi
0x18000612e  mov     rax, [rax+8]
0x180006132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006137  nop
0x180006138  jmp     short loc_180006144
0x18000613a  mov     rsi, [rsp+58h+arg_8]
0x18000613f  mov     rbx, [rsp+58h+arg_0]
0x180006144  mov     rcx, [rbx+1E0h]; hObject
0x18000614b  test    rcx, rcx
0x18000614e  jz      short loc_180006157
0x180006150  call    cs:__imp_CloseHandle
0x180006156  nop
0x180006157  mov     rcx, [rbx+1D0h]; hObject
0x18000615e  test    rcx, rcx
0x180006161  jz      short loc_18000616A
0x180006163  call    cs:__imp_CloseHandle
0x180006169  nop
0x18000616a  lea     rdi, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x180006171  mov     [rsi], rdi
0x180006174  lea     rcx, [rsi+8]; lpCriticalSection
0x180006178  call    cs:__imp_DeleteCriticalSection
0x18000617e  nop
0x18000617f  mov     [rbx+130h], rdi
0x180006186  lea     rcx, [rbx+138h]; lpCriticalSection
0x18000618d  call    cs:__imp_DeleteCriticalSection
0x180006193  nop
0x180006194  mov     [rbx+28h], rdi
0x180006198  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000619c  call    cs:__imp_DeleteCriticalSection
0x1800061a2  nop
0x1800061a3  mov     rbx, [rsp+58h+arg_10]
0x1800061a8  mov     rsi, [rsp+58h+arg_18]
0x1800061ad  add     rsp, 40h
0x1800061b1  pop     r15
0x1800061b3  pop     r14
0x1800061b5  pop     rdi
0x1800061b6  retn
```
