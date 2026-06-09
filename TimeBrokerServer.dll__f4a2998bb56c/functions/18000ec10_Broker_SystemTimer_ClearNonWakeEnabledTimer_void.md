# Broker::SystemTimer::ClearNonWakeEnabledTimer(void)

- ea: `0x18000ec10`
- end: `0x18000ecc8`
- name: `?ClearNonWakeEnabledTimer@SystemTimer@Broker@@AEAAXXZ`
- size: `184`
- prototype: `void __fastcall(void **this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007c60`
- `0x18000d2a8`

## callees

- `0x180003800`
- `0x18000ec10`
- `0x18000ecd0`
- `0x180013876`
- `0x180013978`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec46`

## pseudocode

```c
void __fastcall Broker::SystemTimer::ClearNonWakeEnabledTimer(void **this)
{
  DWORD LastError; // eax
  __int128 v2; // [rsp+28h] [rbp-48h] BYREF
  int v3; // [rsp+38h] [rbp-38h]
  DWORD v4; // [rsp+40h] [rbp-30h]
  void **pExceptionObject; // [rsp+48h] [rbp-28h] BYREF
  __int128 v6; // [rsp+50h] [rbp-20h]
  int v7; // [rsp+60h] [rbp-10h]
  DWORD v8; // [rsp+68h] [rbp-8h]

  if ( !(unsigned int)BciCancelWaitableTimer(*this) )
  {
    v2 = 0;
    v3 = 1;
    LastError = GetLastError();
    v4 = LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids, LastError);
    pExceptionObject = &std::exception::`vftable';
    v6 = 0;
    o___std_exception_copy_0(&v2);
    v7 = v3;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v8 = v4;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18000ec10  mov     [rsp-8+arg_0], rbx
0x18000ec15  push    rbp
0x18000ec16  mov     rbp, rsp
0x18000ec19  sub     rsp, 70h
0x18000ec1d  mov     rcx, [rcx]; void *
0x18000ec20  call    ?BciCancelWaitableTimer@@YAHPEAX@Z; BciCancelWaitableTimer(void *)
0x18000ec25  test    eax, eax
0x18000ec27  jnz     loc_18000ECBA
0x18000ec2d  xorps   xmm0, xmm0
0x18000ec30  movups  [rbp+var_48], xmm0
0x18000ec34  mov     [rbp+var_38], 1
0x18000ec3b  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000ec42  mov     [rbp+var_50], rbx
0x18000ec46  call    cs:__imp_GetLastError
0x18000ec4c  mov     [rbp+var_30], eax
0x18000ec4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec56  test    byte ptr [rcx+1Ch], 4
0x18000ec5a  jz      short loc_18000EC7A
0x18000ec5c  cmp     byte ptr [rcx+19h], 2
0x18000ec60  jb      short loc_18000EC7A
0x18000ec62  mov     edx, 11h
0x18000ec67  mov     r9d, eax
0x18000ec6a  lea     r8, WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids
0x18000ec71  mov     rcx, [rcx+10h]
0x18000ec75  call    WPP_SF_d
0x18000ec7a  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18000ec81  mov     [rbp+pExceptionObject], rax
0x18000ec85  xorps   xmm0, xmm0
0x18000ec88  movups  [rbp+var_20], xmm0
0x18000ec8c  lea     rdx, [rbp+var_20]
0x18000ec90  lea     rcx, [rbp+var_48]
0x18000ec94  call    _o___std_exception_copy_0
0x18000ec99  mov     eax, [rbp+var_38]
0x18000ec9c  mov     [rbp+var_10], eax
0x18000ec9f  mov     [rbp+pExceptionObject], rbx
0x18000eca3  mov     eax, [rbp+var_30]
0x18000eca6  mov     [rbp+var_8], eax
0x18000eca9  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000ecb0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ecb4  call    _CxxThrowException_0
0x18000ecba  mov     rbx, [rsp+70h+arg_0]
0x18000ecc2  add     rsp, 70h
0x18000ecc6  pop     rbp
0x18000ecc7  retn
```
