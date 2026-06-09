# Broker::SystemTimer::SetNonWakeEnabledTimer(_LARGE_INTEGER)

- ea: `0x18000809c`
- end: `0x180008162`
- name: `?SetNonWakeEnabledTimer@SystemTimer@Broker@@AEAAXT_LARGE_INTEGER@@@Z`
- size: `198`
- prototype: `void __fastcall(void **this, union _LARGE_INTEGER, int, void (*)(void *, unsigned int, unsigned int))`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007c60`
- `0x18000d2a8`

## callees

- `0x180003800`
- `0x18000809c`
- `0x18000ee8c`
- `0x180013876`
- `0x180013978`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080eb`

## pseudocode

```c
void __fastcall Broker::SystemTimer::SetNonWakeEnabledTimer(
        void **this,
        union _LARGE_INTEGER a2,
        int a3,
        void (*a4)(void *, unsigned int, unsigned int))
{
  DWORD LastError; // eax
  void *v5; // [rsp+20h] [rbp-60h]
  int v6; // [rsp+28h] [rbp-58h]
  __int128 v7; // [rsp+38h] [rbp-48h] BYREF
  int v8; // [rsp+48h] [rbp-38h]
  DWORD v9; // [rsp+50h] [rbp-30h]
  void **pExceptionObject; // [rsp+58h] [rbp-28h] BYREF
  __int128 v11; // [rsp+60h] [rbp-20h]
  int v12; // [rsp+70h] [rbp-10h]
  DWORD v13; // [rsp+78h] [rbp-8h]
  union _LARGE_INTEGER v14; // [rsp+98h] [rbp+18h] BYREF

  v14 = a2;
  if ( !(unsigned int)BciSetWaitableTimer(*this, &v14, a3, a4, v5, v6) )
  {
    v7 = 0;
    v8 = 1;
    LastError = GetLastError();
    v9 = LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids, LastError);
    pExceptionObject = &std::exception::`vftable';
    v11 = 0;
    o___std_exception_copy_0(&v7);
    v12 = v8;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v13 = v9;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18000809c  mov     [rsp-8+arg_0], rbx
0x1800080a1  mov     qword ptr [rsp-8+arg_8], rdx
0x1800080a6  push    rbp
0x1800080a7  mov     rbp, rsp
0x1800080aa  sub     rsp, 80h
0x1800080b1  lea     rdx, [rbp+arg_8]; union _LARGE_INTEGER *
0x1800080b5  mov     rcx, [rcx]; void *
0x1800080b8  call    ?BciSetWaitableTimer@@YAHPEAXPEBT_LARGE_INTEGER@@JP6AX0KK@Z0H@Z; BciSetWaitableTimer(void *,_LARGE_INTEGER const *,long,void (*)(void *,ulong,ulong),void *,int)
0x1800080bd  test    eax, eax
0x1800080bf  jz      short loc_1800080D2
0x1800080c1  mov     rbx, [rsp+80h+arg_0]
0x1800080c9  add     rsp, 80h
0x1800080d0  pop     rbp
0x1800080d1  retn
0x1800080d2  xorps   xmm0, xmm0
0x1800080d5  movups  [rbp+var_48], xmm0
0x1800080d9  mov     [rbp+var_38], 1
0x1800080e0  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800080e7  mov     [rbp+var_50], rbx
0x1800080eb  call    cs:__imp_GetLastError
0x1800080f1  mov     [rbp+var_30], eax
0x1800080f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080fb  test    byte ptr [rcx+1Ch], 4
0x1800080ff  jnz     short loc_180008141
0x180008101  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180008108  mov     [rbp+pExceptionObject], rax
0x18000810c  xorps   xmm0, xmm0
0x18000810f  movups  [rbp+var_20], xmm0
0x180008113  lea     rdx, [rbp+var_20]
0x180008117  lea     rcx, [rbp+var_48]
0x18000811b  call    _o___std_exception_copy_0
0x180008120  mov     eax, [rbp+var_38]
0x180008123  mov     [rbp+var_10], eax
0x180008126  mov     [rbp+pExceptionObject], rbx
0x18000812a  mov     eax, [rbp+var_30]
0x18000812d  mov     [rbp+var_8], eax
0x180008130  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180008137  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000813b  call    _CxxThrowException_0
0x180008141  cmp     byte ptr [rcx+19h], 2
0x180008145  jb      short loc_180008101
0x180008147  mov     edx, 0Fh
0x18000814c  mov     r9d, eax
0x18000814f  lea     r8, WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids
0x180008156  mov     rcx, [rcx+10h]
0x18000815a  call    WPP_SF_d
0x18000815f  jmp     short loc_180008101
```
