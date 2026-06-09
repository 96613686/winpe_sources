# Broker::SystemTimer::SetWakeEnabledTimer(_LARGE_INTEGER)

- ea: `0x180008168`
- end: `0x180008228`
- name: `?SetWakeEnabledTimer@SystemTimer@Broker@@AEAAXT_LARGE_INTEGER@@@Z`
- size: `192`
- prototype: `void __fastcall(void **this, union _LARGE_INTEGER)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007c60`
- `0x18000d2a8`

## callees

- `0x180003800`
- `0x180008168`
- `0x1800085a0`
- `0x180013876`
- `0x180013978`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081b1`

## pseudocode

```c
void __fastcall Broker::SystemTimer::SetWakeEnabledTimer(void **this, union _LARGE_INTEGER a2)
{
  DWORD LastError; // eax
  __int128 v3; // [rsp+28h] [rbp-48h] BYREF
  int v4; // [rsp+38h] [rbp-38h]
  DWORD v5; // [rsp+40h] [rbp-30h]
  void **pExceptionObject; // [rsp+48h] [rbp-28h] BYREF
  __int128 v7; // [rsp+50h] [rbp-20h]
  int v8; // [rsp+60h] [rbp-10h]
  DWORD v9; // [rsp+68h] [rbp-8h]
  union _LARGE_INTEGER v10; // [rsp+88h] [rbp+18h] BYREF

  v10 = a2;
  if ( !(unsigned int)BciSetIRTimer(*this, &v10) )
  {
    v3 = 0;
    v4 = 1;
    LastError = GetLastError();
    v5 = LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids, LastError);
    pExceptionObject = &std::exception::`vftable';
    v7 = 0;
    o___std_exception_copy_0(&v3);
    v8 = v4;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v9 = v5;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180008168  mov     [rsp-8+arg_0], rbx
0x18000816d  mov     qword ptr [rsp-8+arg_8], rdx
0x180008172  push    rbp
0x180008173  mov     rbp, rsp
0x180008176  sub     rsp, 70h
0x18000817a  lea     rdx, [rbp+arg_8]; union _LARGE_INTEGER *
0x18000817e  mov     rcx, [rcx]; void *
0x180008181  call    ?BciSetIRTimer@@YAHPEAXPEAT_LARGE_INTEGER@@@Z; BciSetIRTimer(void *,_LARGE_INTEGER *)
0x180008186  test    eax, eax
0x180008188  jz      short loc_180008198
0x18000818a  mov     rbx, [rsp+70h+arg_0]
0x180008192  add     rsp, 70h
0x180008196  pop     rbp
0x180008197  retn
0x180008198  xorps   xmm0, xmm0
0x18000819b  movups  [rbp+var_48], xmm0
0x18000819f  mov     [rbp+var_38], 1
0x1800081a6  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800081ad  mov     [rbp+var_50], rbx
0x1800081b1  call    cs:__imp_GetLastError
0x1800081b7  mov     [rbp+var_30], eax
0x1800081ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081c1  test    byte ptr [rcx+1Ch], 4
0x1800081c5  jnz     short loc_180008207
0x1800081c7  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800081ce  mov     [rbp+pExceptionObject], rax
0x1800081d2  xorps   xmm0, xmm0
0x1800081d5  movups  [rbp+var_20], xmm0
0x1800081d9  lea     rdx, [rbp+var_20]
0x1800081dd  lea     rcx, [rbp+var_48]
0x1800081e1  call    _o___std_exception_copy_0
0x1800081e6  mov     eax, [rbp+var_38]
0x1800081e9  mov     [rbp+var_10], eax
0x1800081ec  mov     [rbp+pExceptionObject], rbx
0x1800081f0  mov     eax, [rbp+var_30]
0x1800081f3  mov     [rbp+var_8], eax
0x1800081f6  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800081fd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180008201  call    _CxxThrowException_0
0x180008207  cmp     byte ptr [rcx+19h], 2
0x18000820b  jb      short loc_1800081C7
0x18000820d  mov     edx, 0Eh
0x180008212  mov     r9d, eax
0x180008215  lea     r8, WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids
0x18000821c  mov     rcx, [rcx+10h]
0x180008220  call    WPP_SF_d
0x180008225  jmp     short loc_1800081C7
```
