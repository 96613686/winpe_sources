# Broker::BackgroundTaskCapabilityWrapper::CheckCapability(void *,ulong,int)

- ea: `0x18000c700`
- end: `0x18000c7af`
- name: `?CheckCapability@BackgroundTaskCapabilityWrapper@Broker@@QEAA_NPEAXKH@Z`
- size: `175`
- prototype: `bool __fastcall(Broker::BackgroundTaskCapabilityWrapper *__hidden this, void *, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c69c`

## callees

- `0x18000c700`
- `0x180013978`
- `0x1800199e8`
- `0x18001c010`

## pseudocode

```c
bool __fastcall Broker::BackgroundTaskCapabilityWrapper::CheckCapability(
        Broker::BackgroundTaskCapabilityWrapper *this,
        void *a2,
        unsigned int a3,
        int a4)
{
  __int64 v4; // rcx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned __int16 v9; // bx
  void **pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int128 v12; // [rsp+38h] [rbp-30h]
  int v13; // [rsp+48h] [rbp-20h]
  int v14; // [rsp+50h] [rbp-18h]
  int v15; // [rsp+88h] [rbp+20h] BYREF

  v15 = a4;
  v4 = *(_QWORD *)this;
  v15 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, _QWORD, int *))(*(_QWORD *)v4 + 24LL))(v4, a2, 0, a3, &v15);
  v9 = v6;
  if ( v6 < 0 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_ddl(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, a3, v6);
    v13 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v14 = v9;
    v12 = 0;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  return v15 != 0;
}

```

## disassembly

```asm
0x18000c700  mov     r11, rsp
0x18000c703  mov     [r11+8], rbx
0x18000c707  mov     [r11+20h], r9d
0x18000c70b  push    rdi
0x18000c70c  sub     rsp, 60h
0x18000c710  mov     rcx, [rcx]
0x18000c713  mov     edi, r8d
0x18000c716  lea     r8, [r11+20h]
0x18000c71a  mov     dword ptr [r11+20h], 0
0x18000c722  mov     [r11-48h], r8
0x18000c726  mov     r9d, edi
0x18000c729  xor     r8d, r8d
0x18000c72c  mov     rax, [rcx]
0x18000c72f  mov     rax, [rax+18h]
0x18000c733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c738  mov     ebx, eax
0x18000c73a  test    eax, eax
0x18000c73c  js      short loc_18000C754
0x18000c73e  cmp     [rsp+68h+arg_18], 0
0x18000c746  mov     rbx, [rsp+68h+arg_0]
0x18000c74b  setnz   al
0x18000c74e  add     rsp, 60h
0x18000c752  pop     rdi
0x18000c753  retn
0x18000c754  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c75b  test    dword ptr [rcx+1Ch], 400h
0x18000c762  jz      short loc_18000C77A
0x18000c764  cmp     byte ptr [rcx+19h], 2
0x18000c768  jb      short loc_18000C77A
0x18000c76a  mov     rcx, [rcx+10h]
0x18000c76e  mov     r9d, edi
0x18000c771  mov     [rsp+68h+var_48], ebx
0x18000c775  call    WPP_SF_ddl
0x18000c77a  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000c781  mov     [rsp+68h+var_20], 1
0x18000c789  mov     [rsp+68h+pExceptionObject], rax
0x18000c78e  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000c795  movzx   eax, bx
0x18000c798  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000c79d  xorps   xmm0, xmm0
0x18000c7a0  mov     [rsp+68h+var_18], eax
0x18000c7a4  movups  [rsp+68h+var_30], xmm0
0x18000c7a9  call    _CxxThrowException_0
```
