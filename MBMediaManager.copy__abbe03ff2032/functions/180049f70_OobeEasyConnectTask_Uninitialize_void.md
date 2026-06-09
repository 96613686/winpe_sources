# OobeEasyConnectTask::Uninitialize(void)

- ea: `0x180049f70`
- end: `0x18004a022`
- name: `?Uninitialize@OobeEasyConnectTask@@QEAAJXZ`
- size: `178`
- prototype: `__int64 __fastcall(OobeEasyConnectTask *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019940`

## callees

- `0x180002150`
- `0x18000ad20`
- `0x180049f70`
- `0x180059010`

## import_xrefs

- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x180049f9e`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x180049f9e`

## string_xrefs

- `0x180049f89`: `OobeEasyConnectTask::Uninitialize`

## pseudocode

```c
__int64 __fastcall OobeEasyConnectTask::Uninitialize(OobeEasyConnectTask *this)
{
  const char *v2; // r9
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  MBSettingUXLogging::Info("OobeEasyConnectTask::Uninitialize", 52, "Enter");
  if ( *((_QWORD *)this + 15) )
  {
    UnregisterWaitUntilOOBECompleted();
    *((_QWORD *)this + 15) = 0;
  }
  try
  {
    v3 = *((_QWORD *)this + 9);
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 40LL))(v3, 0);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 72);
    }
    v4 = *((_QWORD *)this + 8);
    if ( v4 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 32LL))(v4);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 64);
    }
    v5 = *((_QWORD *)this + 17);
    if ( v5 && *((_QWORD *)this + 18) )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 96LL))(v5);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4B,
                           (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x180049f70  mov     [rsp+arg_8], rbx
0x180049f75  push    rdi
0x180049f76  sub     rsp, 20h
0x180049f7a  mov     rbx, rcx
0x180049f7d  lea     r8, aEnter; "Enter"
0x180049f84  mov     edx, 34h ; '4'; unsigned int
0x180049f89  lea     rcx, aOobeeasyconnec_11; "OobeEasyConnectTask::Uninitialize"
0x180049f90  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180049f95  mov     rcx, [rbx+78h]
0x180049f99  test    rcx, rcx
0x180049f9c  jz      short loc_180049FAC
0x180049f9e  call    cs:__imp_UnregisterWaitUntilOOBECompleted
0x180049fa4  mov     qword ptr [rbx+78h], 0
0x180049fac  mov     rcx, [rbx+48h]
0x180049fb0  test    rcx, rcx
0x180049fb3  jz      short loc_180049FCC
0x180049fb5  mov     rax, [rcx]
0x180049fb8  xor     edx, edx
0x180049fba  mov     rax, [rax+28h]
0x180049fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049fc3  lea     rcx, [rbx+48h]
0x180049fc7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049fcc  mov     rcx, [rbx+40h]
0x180049fd0  test    rcx, rcx
0x180049fd3  jz      short loc_180049FEA
0x180049fd5  mov     rax, [rcx]
0x180049fd8  mov     rax, [rax+20h]
0x180049fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049fe1  lea     rcx, [rbx+40h]
0x180049fe5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049fea  mov     rcx, [rbx+88h]
0x180049ff1  test    rcx, rcx
0x180049ff4  jz      short loc_18004A00E
0x180049ff6  mov     rdx, [rbx+90h]
0x180049ffd  test    rdx, rdx
0x18004a000  jz      short loc_18004A00E
0x18004a002  mov     rax, [rcx]
0x18004a005  mov     rax, [rax+60h]
0x18004a009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a00e  xor     eax, eax
0x18004a010  jmp     short loc_18004A016
0x18004a012  mov     eax, [rsp+28h+arg_0]
0x18004a016  mov     rbx, [rsp+28h+arg_8]
0x18004a01b  add     rsp, 20h
0x18004a01f  pop     rdi
0x18004a020  retn
```
