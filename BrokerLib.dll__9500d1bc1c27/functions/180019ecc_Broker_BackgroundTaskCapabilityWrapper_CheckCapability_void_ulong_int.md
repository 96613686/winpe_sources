# Broker::BackgroundTaskCapabilityWrapper::CheckCapability(void *,ulong,int)

- ea: `0x180019ecc`
- end: `0x180019f9f`
- name: `?CheckCapability@BackgroundTaskCapabilityWrapper@Broker@@QEAA_NPEAXKH@Z`
- size: `211`
- prototype: `bool __fastcall(Broker::BackgroundTaskCapabilityWrapper *__hidden this, void *, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016950`

## callees

- `0x1800165da`
- `0x180019ecc`
- `0x18001a0bc`
- `0x18001e010`

## pseudocode

```c
bool __fastcall Broker::BackgroundTaskCapabilityWrapper::CheckCapability(__int64 **this, void *a2, __int64 a3, int a4)
{
  __int64 *v4; // rcx
  unsigned int v6; // edi
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned __int16 v11; // bx
  void **pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int128 v14; // [rsp+38h] [rbp-30h]
  int v15; // [rsp+48h] [rbp-20h]
  int v16; // [rsp+50h] [rbp-18h]
  int v17; // [rsp+88h] [rbp+20h] BYREF

  v4 = *this;
  v17 = 0;
  v6 = a3;
  v7 = *v4;
  if ( a4 )
    v8 = (*(__int64 (__fastcall **)(__int64 *, void *, __int64, int *))(v7 + 48))(v4, a2, a3, &v17);
  else
    v8 = (*(__int64 (__fastcall **)(__int64 *, void *, _QWORD, _QWORD, int *))(v7 + 24))(
           v4,
           a2,
           0,
           (unsigned int)a3,
           &v17);
  v11 = v8;
  if ( v8 < 0 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_ddl(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, v6, v8, a4);
    v15 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v16 = v11;
    v14 = 0;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  return v17 != 0;
}

```

## disassembly

```asm
0x180019ecc  mov     r11, rsp
0x180019ecf  mov     [r11+8], rbx
0x180019ed3  mov     [r11+10h], rsi
0x180019ed7  push    rdi
0x180019ed8  sub     rsp, 60h
0x180019edc  mov     rcx, [rcx]
0x180019edf  mov     esi, r9d
0x180019ee2  mov     dword ptr [r11+20h], 0
0x180019eea  mov     edi, r8d
0x180019eed  mov     rax, [rcx]
0x180019ef0  test    r9d, r9d
0x180019ef3  jnz     short loc_180019F0E
0x180019ef5  mov     rax, [rax+18h]
0x180019ef9  lea     r8, [r11+20h]
0x180019efd  mov     [r11-48h], r8
0x180019f01  mov     r9d, edi
0x180019f04  xor     r8d, r8d
0x180019f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f0c  jmp     short loc_180019F1F
0x180019f0e  mov     rax, [rax+30h]
0x180019f12  lea     r9, [rsp+68h+arg_18]
0x180019f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f1f  mov     ebx, eax
0x180019f21  test    eax, eax
0x180019f23  jns     short loc_180019F84
0x180019f25  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f2c  test    dword ptr [rcx+1Ch], 400h
0x180019f33  jz      short loc_180019F4F
0x180019f35  cmp     byte ptr [rcx+19h], 2
0x180019f39  jb      short loc_180019F4F
0x180019f3b  mov     rcx, [rcx+10h]
0x180019f3f  mov     r9d, edi
0x180019f42  mov     [rsp+68h+var_40], esi
0x180019f46  mov     [rsp+68h+var_48], eax
0x180019f4a  call    WPP_SF_ddl
0x180019f4f  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180019f56  mov     [rsp+68h+var_20], 1
0x180019f5e  mov     [rsp+68h+pExceptionObject], rax
0x180019f63  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180019f6a  movzx   eax, bx
0x180019f6d  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180019f72  xorps   xmm0, xmm0
0x180019f75  mov     [rsp+68h+var_18], eax
0x180019f79  movups  [rsp+68h+var_30], xmm0
0x180019f7e  call    _CxxThrowException_0
0x180019f84  cmp     [rsp+68h+arg_18], 0
0x180019f8c  mov     rbx, [rsp+68h+arg_0]
0x180019f91  mov     rsi, [rsp+68h+arg_8]
0x180019f96  setnz   al
0x180019f99  add     rsp, 60h
0x180019f9d  pop     rdi
0x180019f9e  retn
```
