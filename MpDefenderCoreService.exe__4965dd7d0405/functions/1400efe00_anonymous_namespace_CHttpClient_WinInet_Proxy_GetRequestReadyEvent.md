# _anonymous_namespace_::CHttpClient_WinInet_Proxy::GetRequestReadyEvent

- ea: `0x1400efe00`
- end: `0x1400f00e0`
- name: `_anonymous_namespace_::CHttpClient_WinInet_Proxy::GetRequestReadyEvent`
- size: `736`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x14001cd4c`
- `0x14001cd94`
- `0x14001cdc0`
- `0x14003a5c0`
- `0x1400efe00`
- `0x1400f2cc0`
- `0x140166250`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1400efed5`
- `KERNEL32!SetEvent` at `0x1400efed5`
- `KERNEL32!CreateEventW` at `0x1400efead`
- `KERNEL32!CreateEventW` at `0x1400efead`
- `KERNEL32!DuplicateHandle` at `0x1400eff30`
- `KERNEL32!DuplicateHandle` at `0x1400eff30`
- `KERNEL32!OpenProcess` at `0x1400efef1`
- `KERNEL32!OpenProcess` at `0x1400efef1`
- `KERNEL32!GetCurrentProcess` at `0x1400eff0c`
- `KERNEL32!GetCurrentProcess` at `0x1400eff0c`
- `KERNEL32!CloseHandle` at `0x1400efec0`
- `KERNEL32!CloseHandle` at `0x1400eff45`
- `KERNEL32!CloseHandle` at `0x1400eff9e`
- `KERNEL32!CloseHandle` at `0x1400efec0`
- `KERNEL32!CloseHandle` at `0x1400eff45`
- `KERNEL32!CloseHandle` at `0x1400eff9e`
- `KERNEL32!GetLastError` at `0x1400effa4`
- `KERNEL32!GetLastError` at `0x1400effa4`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::CHttpClient_WinInet_Proxy::GetRequestReadyEvent(__int64 a1, HANDLE *a2)
{
  unsigned int v2; // esi
  __int64 v6; // r14
  HANDLE EventW; // rax
  void *v8; // rcx
  void *v9; // rcx
  HANDLE v10; // rbx
  void *v11; // rdi
  HANDLE CurrentProcess; // rax
  volatile signed __int32 *v13; // rdi
  signed int LastError; // eax
  unsigned int v15; // ebp
  volatile signed __int32 *v16; // rdi
  volatile signed __int32 *v17; // rdi
  volatile signed __int32 *v18; // rdi
  __int128 v19; // [rsp+40h] [rbp-48h] BYREF
  HANDLE TargetHandle; // [rsp+50h] [rbp-38h] BYREF

  v2 = 0;
  if ( !a2 )
    return 2147942487LL;
  v6 = a1 + 8;
  if ( Mtx_lock((_Mtx_t)(a1 + 8)) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v6 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v6 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v19 = 0;
  child_process::child_manager(&v19);
  if ( *(_DWORD *)(a1 + 320) && (_QWORD)v19 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v19 + 8LL))(v19) )
  {
    if ( !*(_QWORD *)(a1 + 104) )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      v8 = *(void **)(a1 + 104);
      *(_QWORD *)(a1 + 104) = EventW;
      if ( v8 )
        CloseHandle(v8);
      v9 = *(void **)(a1 + 104);
      if ( v9 && *(_QWORD *)(a1 + 96) )
        SetEvent(v9);
      if ( !*(_QWORD *)(a1 + 104) )
      {
        v17 = (volatile signed __int32 *)*((_QWORD *)&v19 + 1);
        if ( *((_QWORD *)&v19 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
            if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
          }
        }
        v2 = -2147024882;
        goto LABEL_34;
      }
    }
    v10 = OpenProcess(0x40u, 0, *(_DWORD *)(a1 + 320));
    if ( v10 )
    {
      v11 = *(void **)(a1 + 104);
      TargetHandle = 0;
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(CurrentProcess, v11, v10, &TargetHandle, 0x100000u, 0, 0) )
      {
        *a2 = TargetHandle;
        CloseHandle(v10);
        v13 = (volatile signed __int32 *)*((_QWORD *)&v19 + 1);
        if ( *((_QWORD *)&v19 + 1)
          && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
LABEL_34:
        Mtx_unlock((_Mtx_t)v6);
        return v2;
      }
      CloseHandle(v10);
    }
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    v16 = (volatile signed __int32 *)*((_QWORD *)&v19 + 1);
    if ( *((_QWORD *)&v19 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    v2 = v15;
    goto LABEL_34;
  }
  v18 = (volatile signed __int32 *)*((_QWORD *)&v19 + 1);
  if ( *((_QWORD *)&v19 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  Mtx_unlock((_Mtx_t)v6);
  return 2147942405LL;
}

```

## disassembly

```asm
0x1400efe00  mov     [rsp+arg_10], rbx
0x1400efe05  push    rbp
0x1400efe06  push    rsi
0x1400efe07  push    rdi
0x1400efe08  push    r14
0x1400efe0a  push    r15
0x1400efe0c  sub     rsp, 60h
0x1400efe10  mov     rax, cs:__security_cookie
0x1400efe17  xor     rax, rsp
0x1400efe1a  mov     [rsp+88h+var_30], rax
0x1400efe1f  xor     esi, esi
0x1400efe21  mov     r15, rdx
0x1400efe24  mov     rdi, rcx
0x1400efe27  test    rdx, rdx
0x1400efe2a  jnz     short loc_1400EFE36
0x1400efe2c  mov     eax, 80070057h
0x1400efe31  jmp     loc_1400F00A1
0x1400efe36  lea     r14, [rcx+8]
0x1400efe3a  mov     rcx, r14; _Mtx_t
0x1400efe3d  call    _Mtx_lock
0x1400efe42  test    eax, eax
0x1400efe44  jnz     loc_1400F00D5
0x1400efe4a  cmp     dword ptr [r14+4Ch], 7FFFFFFFh
0x1400efe52  jz      loc_1400F00C2
0x1400efe58  xorps   xmm0, xmm0
0x1400efe5b  lea     rcx, [rsp+88h+var_48]
0x1400efe60  movups  [rsp+88h+var_48], xmm0
0x1400efe65  call    ?child_manager@child_process@@YA?AV?$shared_ptr@Umanager_t@child_process@@@std@@XZ; child_process::child_manager(void)
0x1400efe6a  mov     edx, [rdi+140h]
0x1400efe70  test    edx, edx
0x1400efe72  jz      loc_1400F0052
0x1400efe78  mov     rcx, qword ptr [rsp+88h+var_48]
0x1400efe7d  test    rcx, rcx
0x1400efe80  jz      loc_1400F0052
0x1400efe86  mov     rax, [rcx]
0x1400efe89  mov     rax, [rax+8]
0x1400efe8d  call    cs:__guard_dispatch_icall_fptr
0x1400efe93  test    al, al
0x1400efe95  jz      loc_1400F0052
0x1400efe9b  cmp     [rdi+68h], rsi
0x1400efe9f  jnz     short loc_1400EFEE5
0x1400efea1  xor     r9d, r9d; lpName
0x1400efea4  xor     r8d, r8d; bInitialState
0x1400efea7  xor     ecx, ecx; lpEventAttributes
0x1400efea9  lea     edx, [r9+1]; bManualReset
0x1400efead  call    cs:__imp_CreateEventW
0x1400efeb3  mov     rcx, [rdi+68h]; hObject
0x1400efeb7  mov     [rdi+68h], rax
0x1400efebb  test    rcx, rcx
0x1400efebe  jz      short loc_1400EFEC6
0x1400efec0  call    cs:__imp_CloseHandle
0x1400efec6  mov     rcx, [rdi+68h]; hEvent
0x1400efeca  test    rcx, rcx
0x1400efecd  jz      short loc_1400EFEDB
0x1400efecf  cmp     [rdi+60h], rsi
0x1400efed3  jbe     short loc_1400EFEDB
0x1400efed5  call    cs:__imp_SetEvent
0x1400efedb  cmp     [rdi+68h], rsi
0x1400efedf  jz      loc_1400EFFFF
0x1400efee5  mov     r8d, [rdi+140h]; dwProcessId
0x1400efeec  xor     edx, edx; bInheritHandle
0x1400efeee  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1400efef1  call    cs:__imp_OpenProcess
0x1400efef7  mov     rbx, rax
0x1400efefa  test    rax, rax
0x1400efefd  jz      loc_1400EFFA4
0x1400eff03  mov     rdi, [rdi+68h]
0x1400eff07  mov     [rsp+88h+TargetHandle], rsi
0x1400eff0c  call    cs:__imp_GetCurrentProcess
0x1400eff12  mov     [rsp+88h+dwOptions], esi; dwOptions
0x1400eff16  lea     r9, [rsp+88h+TargetHandle]; lpTargetHandle
0x1400eff1b  mov     rcx, rax; hSourceProcessHandle
0x1400eff1e  mov     [rsp+88h+bInheritHandle], esi; bInheritHandle
0x1400eff22  mov     r8, rbx; hTargetProcessHandle
0x1400eff25  mov     [rsp+88h+dwDesiredAccess], 100000h; dwDesiredAccess
0x1400eff2d  mov     rdx, rdi; hSourceHandle
0x1400eff30  call    cs:__imp_DuplicateHandle
0x1400eff36  mov     rcx, rbx; hObject
0x1400eff39  test    eax, eax
0x1400eff3b  jz      short loc_1400EFF9E
0x1400eff3d  mov     rax, [rsp+88h+TargetHandle]
0x1400eff42  mov     [r15], rax
0x1400eff45  call    cs:__imp_CloseHandle
0x1400eff4b  mov     rdi, qword ptr [rsp+88h+var_48+8]
0x1400eff50  test    rdi, rdi
0x1400eff53  jz      loc_1400F0046
0x1400eff59  or      ebx, 0FFFFFFFFh
0x1400eff5c  mov     eax, ebx
0x1400eff5e  lock xadd [rdi+8], eax
0x1400eff63  add     eax, ebx
0x1400eff65  jnz     loc_1400F0046
0x1400eff6b  mov     rax, [rdi]
0x1400eff6e  mov     rcx, rdi
0x1400eff71  mov     rax, [rax]
0x1400eff74  call    cs:__guard_dispatch_icall_fptr
0x1400eff7a  mov     eax, ebx
0x1400eff7c  lock xadd [rdi+0Ch], eax
0x1400eff81  add     eax, ebx
0x1400eff83  jnz     loc_1400F0046
0x1400eff89  mov     rax, [rdi]
0x1400eff8c  mov     rcx, rdi
0x1400eff8f  mov     rax, [rax+8]
0x1400eff93  call    cs:__guard_dispatch_icall_fptr
0x1400eff99  jmp     loc_1400F0046
0x1400eff9e  call    cs:__imp_CloseHandle
0x1400effa4  call    cs:__imp_GetLastError
0x1400effaa  mov     ebp, eax
0x1400effac  test    eax, eax
0x1400effae  jle     short loc_1400EFFB9
0x1400effb0  movzx   ebp, ax
0x1400effb3  or      ebp, 80070000h
0x1400effb9  mov     rdi, qword ptr [rsp+88h+var_48+8]
0x1400effbe  test    rdi, rdi
0x1400effc1  jz      short loc_1400EFFFB
0x1400effc3  or      ebx, 0FFFFFFFFh
0x1400effc6  mov     eax, ebx
0x1400effc8  lock xadd [rdi+8], eax
0x1400effcd  add     eax, ebx
0x1400effcf  jnz     short loc_1400EFFFB
0x1400effd1  mov     rax, [rdi]
0x1400effd4  mov     rcx, rdi
0x1400effd7  mov     rax, [rax]
0x1400effda  call    cs:__guard_dispatch_icall_fptr
0x1400effe0  mov     eax, ebx
0x1400effe2  lock xadd [rdi+0Ch], eax
0x1400effe7  add     eax, ebx
0x1400effe9  jnz     short loc_1400EFFFB
0x1400effeb  mov     rax, [rdi]
0x1400effee  mov     rcx, rdi
0x1400efff1  mov     rax, [rax+8]
0x1400efff5  call    cs:__guard_dispatch_icall_fptr
0x1400efffb  mov     esi, ebp
0x1400efffd  jmp     short loc_1400F0046
0x1400effff  mov     rdi, qword ptr [rsp+88h+var_48+8]
0x1400f0004  test    rdi, rdi
0x1400f0007  jz      short loc_1400F0041
0x1400f0009  or      ebx, 0FFFFFFFFh
0x1400f000c  mov     eax, ebx
0x1400f000e  lock xadd [rdi+8], eax
0x1400f0013  add     eax, ebx
0x1400f0015  jnz     short loc_1400F0041
0x1400f0017  mov     rax, [rdi]
0x1400f001a  mov     rcx, rdi
0x1400f001d  mov     rax, [rax]
0x1400f0020  call    cs:__guard_dispatch_icall_fptr
0x1400f0026  mov     eax, ebx
0x1400f0028  lock xadd [rdi+0Ch], eax
0x1400f002d  add     eax, ebx
0x1400f002f  jnz     short loc_1400F0041
0x1400f0031  mov     rax, [rdi]
0x1400f0034  mov     rcx, rdi
0x1400f0037  mov     rax, [rax+8]
0x1400f003b  call    cs:__guard_dispatch_icall_fptr
0x1400f0041  mov     esi, 8007000Eh
0x1400f0046  mov     rcx, r14; _Mtx_t
0x1400f0049  call    _Mtx_unlock
0x1400f004e  mov     eax, esi
0x1400f0050  jmp     short loc_1400F00A1
0x1400f0052  mov     rdi, qword ptr [rsp+88h+var_48+8]
0x1400f0057  test    rdi, rdi
0x1400f005a  jz      short loc_1400F0094
0x1400f005c  or      ebx, 0FFFFFFFFh
0x1400f005f  mov     eax, ebx
0x1400f0061  lock xadd [rdi+8], eax
0x1400f0066  add     eax, ebx
0x1400f0068  jnz     short loc_1400F0094
0x1400f006a  mov     rax, [rdi]
0x1400f006d  mov     rcx, rdi
0x1400f0070  mov     rax, [rax]
0x1400f0073  call    cs:__guard_dispatch_icall_fptr
0x1400f0079  mov     eax, ebx
0x1400f007b  lock xadd [rdi+0Ch], eax
0x1400f0080  add     eax, ebx
0x1400f0082  jnz     short loc_1400F0094
0x1400f0084  mov     rax, [rdi]
0x1400f0087  mov     rcx, rdi
0x1400f008a  mov     rax, [rax+8]
0x1400f008e  call    cs:__guard_dispatch_icall_fptr
0x1400f0094  mov     rcx, r14; _Mtx_t
0x1400f0097  call    _Mtx_unlock
0x1400f009c  mov     eax, 80070005h
0x1400f00a1  mov     rcx, [rsp+88h+var_30]
0x1400f00a6  xor     rcx, rsp; StackCookie
0x1400f00a9  call    __security_check_cookie
0x1400f00ae  mov     rbx, [rsp+88h+arg_10]
0x1400f00b6  add     rsp, 60h
0x1400f00ba  pop     r15
0x1400f00bc  pop     r14
0x1400f00be  pop     rdi
0x1400f00bf  pop     rsi
0x1400f00c0  pop     rbp
0x1400f00c1  retn
0x1400f00c2  mov     ecx, 6; int
0x1400f00c7  mov     dword ptr [r14+4Ch], 7FFFFFFEh
0x1400f00cf  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1400f00d5  mov     ecx, 5; int
0x1400f00da  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
