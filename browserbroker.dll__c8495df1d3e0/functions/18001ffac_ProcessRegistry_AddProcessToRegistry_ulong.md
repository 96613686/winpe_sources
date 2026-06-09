# ProcessRegistry::AddProcessToRegistry(ulong)

- ea: `0x18001ffac`
- end: `0x180020186`
- name: `?AddProcessToRegistry@ProcessRegistry@@QEAAJK@Z`
- size: `474`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, DWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000b920`
- `0x18000b970`

## callees

- `0x180002d3c`
- `0x18001fa78`
- `0x18001faa0`
- `0x18001ff20`
- `0x18001ffac`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800200c1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800200c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020139`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020139`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ffcf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ffcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020165`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020165`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001fff5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001fff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020141`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002001c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002001c`

## pseudocode

```c
__int64 __fastcall ProcessRegistry::AddProcessToRegistry(RTL_SRWLOCK *this, DWORD a2)
{
  RTL_SRWLOCK *v4; // r15
  HANDLE *Ptr; // rbx
  HANDLE *i; // rdi
  HANDLE v7; // rbp
  _QWORD *v8; // rdi
  __int64 v9; // rcx
  void *v10; // rax
  __int64 v11; // rdx
  RTL_SRWLOCK *v12; // rcx
  signed int v13; // ebx
  signed int LastError; // eax
  signed int v15; // eax
  __int128 v17; // [rsp+30h] [rbp-48h] BYREF
  void *v18; // [rsp+40h] [rbp-38h]
  void *phNewWaitObject; // [rsp+80h] [rbp+8h] BYREF
  RTL_SRWLOCK *v20; // [rsp+90h] [rbp+18h]

  v4 = this + 2;
  AcquireSRWLockExclusive(this + 2);
  v20 = v4;
  Ptr = (HANDLE *)this[4].Ptr;
  for ( i = (HANDLE *)this[3].Ptr; i != Ptr && (a2 != *(_DWORD *)i || !WaitForSingleObject(i[1], 0)); i += 3 )
    ;
  if ( i == this[4].Ptr )
  {
    v7 = OpenProcess(0x100001u, 0, a2);
    if ( v7 )
    {
      v8 = operator new(0x20u);
      phNewWaitObject = v8;
      *(_DWORD *)v8 = 0;
      v8[1] = 0;
      v8[2] = 0;
      v8[3] = 0;
      if ( this )
      {
        (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 1))(this);
        v9 = v8[3];
        v8[3] = this;
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      phNewWaitObject = 0;
      if ( RegisterWaitForSingleObject(
             &phNewWaitObject,
             v7,
             ProcessRegistry::s_ProcessTerminated_Callback,
             v8,
             0xFFFFFFFF,
             8u) )
      {
        LODWORD(v17) = a2;
        *((_QWORD *)&v17 + 1) = v7;
        v10 = phNewWaitObject;
        v18 = phNewWaitObject;
        *(_OWORD *)v8 = v17;
        v8[2] = v10;
        v11 = (__int64)this[4].Ptr;
        v12 = this + 3;
        if ( (PVOID)v11 == this[5].Ptr )
          std::vector<ProcessRegistry::Process>::_Emplace_reallocate<ProcessRegistry::Process const &>(v12, v11, &v17);
        else
          std::vector<ProcessRegistry::Process>::_Emplace_back_with_unused_capacity<ProcessRegistry::Process const &>(
            (__int64)v12,
            (__int64)&v17);
        v13 = 0;
      }
      else
      {
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        if ( v13 < 0 )
        {
          ProcessRegistry::ProcessCallbackData::`scalar deleting destructor'((ProcessRegistry::ProcessCallbackData *)v8);
          CloseHandle(v7);
        }
      }
    }
    else
    {
      v15 = GetLastError();
      v13 = v15;
      if ( v15 > 0 )
        v13 = (unsigned __int16)v15 | 0x80070000;
    }
  }
  else
  {
    v13 = -2147024713;
  }
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001ffac  mov     [rsp+arg_8], rbx
0x18001ffb1  mov     [rsp+arg_18], rbp
0x18001ffb6  push    rsi
0x18001ffb7  push    rdi
0x18001ffb8  push    r12
0x18001ffba  push    r14
0x18001ffbc  push    r15
0x18001ffbe  sub     rsp, 50h
0x18001ffc2  mov     r12d, edx
0x18001ffc5  mov     r14, rcx
0x18001ffc8  lea     r15, [rcx+10h]
0x18001ffcc  mov     rcx, r15; SRWLock
0x18001ffcf  call    cs:__imp_AcquireSRWLockExclusive
0x18001ffd5  mov     [rsp+78h+arg_10], r15
0x18001ffdd  lea     rsi, [r14+18h]
0x18001ffe1  mov     rbx, [rsi+8]
0x18001ffe5  mov     rdi, [rsi]
0x18001ffe8  jmp     short loc_180020003
0x18001ffea  cmp     r12d, [rdi]
0x18001ffed  jnz     short loc_18001FFFF
0x18001ffef  xor     edx, edx; dwMilliseconds
0x18001fff1  mov     rcx, [rdi+8]; hHandle
0x18001fff5  call    cs:__imp_WaitForSingleObject
0x18001fffb  test    eax, eax
0x18001fffd  jnz     short loc_180020008
0x18001ffff  add     rdi, 18h
0x180020003  cmp     rdi, rbx
0x180020006  jnz     short loc_18001FFEA
0x180020008  cmp     rdi, [rsi+8]
0x18002000c  jnz     loc_180020158
0x180020012  mov     r8d, r12d; dwProcessId
0x180020015  xor     edx, edx; bInheritHandle
0x180020017  mov     ecx, 100001h; dwDesiredAccess
0x18002001c  call    cs:__imp_OpenProcess
0x180020022  mov     rbp, rax
0x180020025  test    rax, rax
0x180020028  jz      loc_180020141
0x18002002e  mov     ecx, 20h ; ' '; Size
0x180020033  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020038  mov     rdi, rax
0x18002003b  mov     [rsp+78h+phNewWaitObject], rax
0x180020043  mov     dword ptr [rax], 0
0x180020049  mov     qword ptr [rax+8], 0
0x180020051  mov     qword ptr [rax+10h], 0
0x180020059  mov     qword ptr [rax+18h], 0
0x180020061  test    r14, r14
0x180020064  jz      short loc_180020090
0x180020066  mov     rcx, [r14]
0x180020069  mov     rax, [rcx+8]
0x18002006d  mov     rcx, r14
0x180020070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020075  nop
0x180020076  mov     rcx, [rdi+18h]
0x18002007a  mov     [rdi+18h], r14
0x18002007e  test    rcx, rcx
0x180020081  jz      short loc_180020090
0x180020083  mov     rax, [rcx]
0x180020086  mov     rax, [rax+10h]
0x18002008a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002008f  nop
0x180020090  mov     [rsp+78h+phNewWaitObject], 0
0x18002009c  mov     [rsp+78h+dwFlags], 8; dwFlags
0x1800200a4  mov     [rsp+78h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1800200ac  mov     r9, rdi; Context
0x1800200af  lea     r8, ?s_ProcessTerminated_Callback@ProcessRegistry@@CAXPEAXE@Z; Callback
0x1800200b6  mov     rdx, rbp; hObject
0x1800200b9  lea     rcx, [rsp+78h+phNewWaitObject]; phNewWaitObject
0x1800200c1  call    cs:__imp_RegisterWaitForSingleObject
0x1800200c7  test    eax, eax
0x1800200c9  jz      short loc_180020115
0x1800200cb  mov     dword ptr [rsp+78h+var_48], r12d
0x1800200d0  mov     qword ptr [rsp+78h+var_48+8], rbp
0x1800200d5  mov     rax, [rsp+78h+phNewWaitObject]
0x1800200dd  mov     [rsp+78h+var_38], rax
0x1800200e2  movups  xmm0, [rsp+78h+var_48]
0x1800200e7  movups  xmmword ptr [rdi], xmm0
0x1800200ea  mov     [rdi+10h], rax
0x1800200ee  mov     rdx, [rsi+8]
0x1800200f2  mov     rcx, rsi
0x1800200f5  cmp     rdx, [rsi+10h]
0x1800200f9  jz      short loc_180020107
0x1800200fb  lea     rdx, [rsp+78h+var_48]
0x180020100  call    ??$_Emplace_back_with_unused_capacity@AEBUProcess@ProcessRegistry@@@?$vector@UProcess@ProcessRegistry@@V?$allocator@UProcess@ProcessRegistry@@@std@@@std@@AEAAAEAUProcess@ProcessRegistry@@AEBU23@@Z; std::vector<ProcessRegistry::Process>::_Emplace_back_with_unused_capacity<ProcessRegistry::Process const &>(ProcessRegistry::Process const &)
0x180020105  jmp     short loc_180020111
0x180020107  lea     r8, [rsp+78h+var_48]
0x18002010c  call    ??$_Emplace_reallocate@AEBUProcess@ProcessRegistry@@@?$vector@UProcess@ProcessRegistry@@V?$allocator@UProcess@ProcessRegistry@@@std@@@std@@AEAAPEAUProcess@ProcessRegistry@@QEAU23@AEBU23@@Z; std::vector<ProcessRegistry::Process>::_Emplace_reallocate<ProcessRegistry::Process const &>(ProcessRegistry::Process * const,ProcessRegistry::Process const &)
0x180020111  xor     ebx, ebx
0x180020113  jmp     short loc_18002015D
0x180020115  call    cs:__imp_GetLastError
0x18002011b  mov     ebx, eax
0x18002011d  test    eax, eax
0x18002011f  jle     short loc_18002012A
0x180020121  movzx   ebx, ax
0x180020124  or      ebx, 80070000h
0x18002012a  test    ebx, ebx
0x18002012c  jns     short loc_18002015D
0x18002012e  mov     rcx, rdi; this
0x180020131  call    ??_GProcessCallbackData@ProcessRegistry@@QEAAPEAXI@Z; ProcessRegistry::ProcessCallbackData::`scalar deleting destructor'(uint)
0x180020136  mov     rcx, rbp; hObject
0x180020139  call    cs:__imp_CloseHandle
0x18002013f  jmp     short loc_18002015D
0x180020141  call    cs:__imp_GetLastError
0x180020147  mov     ebx, eax
0x180020149  test    eax, eax
0x18002014b  jle     short loc_18002015D
0x18002014d  movzx   ebx, ax
0x180020150  or      ebx, 80070000h
0x180020156  jmp     short loc_18002015D
0x180020158  mov     ebx, 800700B7h
0x18002015d  test    r15, r15
0x180020160  jz      short loc_18002016B
0x180020162  mov     rcx, r15; SRWLock
0x180020165  call    cs:__imp_ReleaseSRWLockExclusive
0x18002016b  mov     eax, ebx
0x18002016d  lea     r11, [rsp+78h+var_28]
0x180020172  mov     rbx, [r11+38h]
0x180020176  mov     rbp, [r11+48h]
0x18002017a  mov     rsp, r11
0x18002017d  pop     r15
0x18002017f  pop     r14
0x180020181  pop     r12
0x180020183  pop     rdi
0x180020184  pop     rsi
0x180020185  retn
```
