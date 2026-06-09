# Broker::SystemTimer::ClearWakeEnabledTimer(void)

- ea: `0x18000a474`
- end: `0x18000a52e`
- name: `?ClearWakeEnabledTimer@SystemTimer@Broker@@AEAAXXZ`
- size: `186`
- prototype: `void __fastcall(void **this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007c60`
- `0x18000d2a8`

## callees

- `0x180003800`
- `0x1800085a0`
- `0x18000a474`
- `0x180013876`
- `0x180013978`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4ac`

## pseudocode

```c
void __fastcall Broker::SystemTimer::ClearWakeEnabledTimer(void **this)
{
  DWORD LastError; // eax
  __int128 v2; // [rsp+28h] [rbp-48h] BYREF
  int v3; // [rsp+38h] [rbp-38h]
  DWORD v4; // [rsp+40h] [rbp-30h]
  void **pExceptionObject; // [rsp+48h] [rbp-28h] BYREF
  __int128 v6; // [rsp+50h] [rbp-20h]
  int v7; // [rsp+60h] [rbp-10h]
  DWORD v8; // [rsp+68h] [rbp-8h]

  if ( !(unsigned int)BciSetIRTimer(*this, 0) )
  {
    v2 = 0;
    v3 = 1;
    LastError = GetLastError();
    v4 = LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids, LastError);
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
0x18000a474  mov     [rsp-8+arg_0], rbx
0x18000a479  push    rbp
0x18000a47a  mov     rbp, rsp
0x18000a47d  sub     rsp, 70h
0x18000a481  xor     edx, edx; union _LARGE_INTEGER *
0x18000a483  mov     rcx, [rcx]; void *
0x18000a486  call    ?BciSetIRTimer@@YAHPEAXPEAT_LARGE_INTEGER@@@Z; BciSetIRTimer(void *,_LARGE_INTEGER *)
0x18000a48b  test    eax, eax
0x18000a48d  jnz     loc_18000A520
0x18000a493  xorps   xmm0, xmm0
0x18000a496  movups  [rbp+var_48], xmm0
0x18000a49a  mov     [rbp+var_38], 1
0x18000a4a1  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000a4a8  mov     [rbp+var_50], rbx
0x18000a4ac  call    cs:__imp_GetLastError
0x18000a4b2  mov     [rbp+var_30], eax
0x18000a4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4bc  test    byte ptr [rcx+1Ch], 4
0x18000a4c0  jz      short loc_18000A4E0
0x18000a4c2  cmp     byte ptr [rcx+19h], 2
0x18000a4c6  jb      short loc_18000A4E0
0x18000a4c8  mov     edx, 10h
0x18000a4cd  mov     r9d, eax
0x18000a4d0  lea     r8, WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids
0x18000a4d7  mov     rcx, [rcx+10h]
0x18000a4db  call    WPP_SF_d
0x18000a4e0  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18000a4e7  mov     [rbp+pExceptionObject], rax
0x18000a4eb  xorps   xmm0, xmm0
0x18000a4ee  movups  [rbp+var_20], xmm0
0x18000a4f2  lea     rdx, [rbp+var_20]
0x18000a4f6  lea     rcx, [rbp+var_48]
0x18000a4fa  call    _o___std_exception_copy_0
0x18000a4ff  mov     eax, [rbp+var_38]
0x18000a502  mov     [rbp+var_10], eax
0x18000a505  mov     [rbp+pExceptionObject], rbx
0x18000a509  mov     eax, [rbp+var_30]
0x18000a50c  mov     [rbp+var_8], eax
0x18000a50f  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000a516  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000a51a  call    _CxxThrowException_0
0x18000a520  mov     rbx, [rsp+70h+arg_0]
0x18000a528  add     rsp, 70h
0x18000a52c  pop     rbp
0x18000a52d  retn
```
