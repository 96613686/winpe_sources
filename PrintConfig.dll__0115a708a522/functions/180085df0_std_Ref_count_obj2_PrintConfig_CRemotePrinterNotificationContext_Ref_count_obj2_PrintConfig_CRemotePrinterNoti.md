# std::_Ref_count_obj2<PrintConfig::CRemotePrinterNotificationContext>::_Ref_count_obj2<PrintConfig::CRemotePrinterNotificationContext>(void)

- ea: `0x180085df0`
- end: `0x180085f47`
- name: `??$?0$$V@?$_Ref_count_obj2@VCRemotePrinterNotificationContext@PrintConfig@@@std@@QEAA@XZ`
- size: `343`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180088ad4`

## callees

- `0x180004564`
- `0x18000f830`
- `0x180085df0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180085e5e`
- `KERNEL32!CloseHandle` at `0x180085ec0`
- `KERNEL32!CloseHandle` at `0x180085e5e`
- `KERNEL32!CloseHandle` at `0x180085ec0`
- `KERNEL32!GetLastError` at `0x180085e7a`
- `KERNEL32!GetLastError` at `0x180085edb`
- `KERNEL32!GetLastError` at `0x180085e7a`
- `KERNEL32!GetLastError` at `0x180085edb`
- `KERNEL32!CreateEventW` at `0x180085e41`
- `KERNEL32!CreateEventW` at `0x180085ea4`
- `KERNEL32!CreateEventW` at `0x180085e41`
- `KERNEL32!CreateEventW` at `0x180085ea4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Ref_count_obj2<PrintConfig::CRemotePrinterNotificationContext>::_Ref_count_obj2<PrintConfig::CRemotePrinterNotificationContext>(
        __int64 a1)
{
  __int64 v2; // rbx
  HANDLE EventW; // rdi
  char *v4; // rcx
  signed int LastError; // eax
  bool v6; // sf
  HANDLE v7; // rdi
  signed int v8; // eax
  bool v9; // sf
  _BYTE pExceptionObject[48]; // [rsp+28h] [rbp-30h] BYREF

  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &std::_Ref_count_obj2<PrintConfig::CRemotePrinterNotificationContext>::`vftable';
  v2 = a1 + 16;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v4 = *(char **)(v2 + 8);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  *(_QWORD *)(v2 + 8) = EventW;
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v6 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v6 = LastError < 0;
    }
    if ( v6 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, LastError);
      throw (hr_error *)pExceptionObject;
    }
  }
  v7 = CreateEventW(0, 0, 0, 0);
  if ( (unsigned __int64)(*(_QWORD *)v2 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(*(HANDLE *)v2);
  *(_QWORD *)v2 = v7;
  if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v8 = GetLastError();
    v9 = v8 < 0;
    if ( v8 > 0 )
    {
      v8 = (unsigned __int16)v8 | 0x80070000;
      v9 = v8 < 0;
    }
    if ( v9 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v8);
      throw (hr_error *)pExceptionObject;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180085df0  mov     r11, rsp
0x180085df3  push    rdi
0x180085df4  sub     rsp, 50h
0x180085df8  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x180085e00  mov     [r11+10h], rbx
0x180085e04  mov     [r11+18h], rsi
0x180085e08  mov     rsi, rcx
0x180085e0b  mov     eax, 1
0x180085e10  mov     [rcx+8], eax
0x180085e13  mov     [rcx+0Ch], eax
0x180085e16  lea     rax, ??_7?$_Ref_count_obj2@VCRemotePrinterNotificationContext@PrintConfig@@@std@@6B@; const std::_Ref_count_obj2<PrintConfig::CRemotePrinterNotificationContext>::`vftable'
0x180085e1d  mov     [rcx], rax
0x180085e20  lea     rbx, [rcx+10h]
0x180085e24  mov     [r11+8], rbx
0x180085e28  mov     qword ptr [rbx], 0
0x180085e2f  mov     qword ptr [rbx+8], 0
0x180085e37  xor     r9d, r9d; lpName
0x180085e3a  xor     r8d, r8d; bInitialState
0x180085e3d  xor     edx, edx; bManualReset
0x180085e3f  xor     ecx, ecx; lpEventAttributes
0x180085e41  call    cs:__imp_CreateEventW
0x180085e48  nop     dword ptr [rax+rax+00h]
0x180085e4d  mov     rdi, rax
0x180085e50  mov     rcx, [rbx+8]; hObject
0x180085e54  lea     rdx, [rcx-1]
0x180085e58  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180085e5c  ja      short loc_180085E6A
0x180085e5e  call    cs:__imp_CloseHandle
0x180085e65  nop     dword ptr [rax+rax+00h]
0x180085e6a  mov     [rbx+8], rdi
0x180085e6e  lea     rax, [rdi+1]
0x180085e72  test    rax, 0FFFFFFFFFFFFFFFEh
0x180085e78  jnz     short loc_180085E9A
0x180085e7a  call    cs:__imp_GetLastError
0x180085e81  nop     dword ptr [rax+rax+00h]
0x180085e86  test    eax, eax
0x180085e88  jle     short loc_180085E94
0x180085e8a  movzx   eax, ax
0x180085e8d  or      eax, 80070000h
0x180085e92  test    eax, eax
0x180085e94  js      loc_180085F29
0x180085e9a  xor     r9d, r9d; lpName
0x180085e9d  xor     r8d, r8d; bInitialState
0x180085ea0  xor     edx, edx; bManualReset
0x180085ea2  xor     ecx, ecx; lpEventAttributes
0x180085ea4  call    cs:__imp_CreateEventW
0x180085eab  nop     dword ptr [rax+rax+00h]
0x180085eb0  mov     rdi, rax
0x180085eb3  mov     rcx, [rbx]; hObject
0x180085eb6  lea     rdx, [rcx-1]
0x180085eba  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180085ebe  ja      short loc_180085ECC
0x180085ec0  call    cs:__imp_CloseHandle
0x180085ec7  nop     dword ptr [rax+rax+00h]
0x180085ecc  mov     [rbx], rdi
0x180085ecf  lea     rax, [rdi+1]
0x180085ed3  test    rax, 0FFFFFFFFFFFFFFFEh
0x180085ed9  jnz     short loc_180085EF7
0x180085edb  call    cs:__imp_GetLastError
0x180085ee2  nop     dword ptr [rax+rax+00h]
0x180085ee7  test    eax, eax
0x180085ee9  jle     short loc_180085EF5
0x180085eeb  movzx   eax, ax
0x180085eee  or      eax, 80070000h
0x180085ef3  test    eax, eax
0x180085ef5  js      short loc_180085F0B
0x180085ef7  mov     rax, rsi
0x180085efa  mov     rbx, [rsp+58h+arg_8]
0x180085eff  mov     rsi, [rsp+58h+arg_10]
0x180085f04  add     rsp, 50h
0x180085f08  pop     rdi
0x180085f09  retn
0x180085f0b  mov     edx, eax; int
0x180085f0d  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180085f12  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180085f17  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180085f1e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180085f23  call    _CxxThrowException_0
0x180085f29  mov     edx, eax; int
0x180085f2b  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180085f30  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180085f35  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180085f3c  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180085f41  call    _CxxThrowException_0
```
