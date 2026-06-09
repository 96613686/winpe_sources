# CServiceModule::ServiceMain(ulong,ushort * *)

- ea: `0x180025ae0`
- end: `0x180025bb6`
- name: `?ServiceMain@CServiceModule@@SAXKPEAPEAG@Z`
- size: `214`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x18001fcbc`
- `0x180022d74`
- `0x180025ae0`
- `0x180025bbc`
- `0x180026c8c`
- `0x180027420`
- `0x18002b710`
- `0x18002b7f8`

## pseudocode

```c
void __fastcall CServiceModule::ServiceMain(unsigned int a1, unsigned __int16 **a2)
{
  const unsigned __int16 *v4; // rdx
  CServiceModule *v5; // rcx
  CServiceModule *v6; // rcx
  unsigned int v7; // edx
  unsigned int v8; // r8d
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  qword_180041C00 = 0;
  WPP_MAIN_CB = (__int64)&qword_180041C18;
  qword_180041C08 = 1;
  qword_180041C28 = 0;
  qword_180041C18 = 0;
  qword_180041C30 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ControlGuid;
  qword_180041BE8 = (__int64)WPP_ThisDir_CTLGUID_MobTabPerfTraceProvider;
  WPP_GLOBAL_Control = (struct _GUID *)&WPP_MAIN_CB;
  WppInitUm();
  try
  {
    if ( (unsigned int)CServiceModule::Init(v5, v4, a1, a2) && CServiceModule::Start(v6) )
    {
      if ( CServiceModule::ServiceMainBegin((CServiceModule *)&_Module) )
        return;
      CServiceModule::Stop((CServiceModule *)&_Module, v7);
    }
    CServiceModule::Destroy((CServiceModule *)&_Module);
    WppCleanupUm();
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0xA3D, v8, v9);
  }
}

```

## disassembly

```asm
0x180025ae0  mov     [rsp+arg_0], rbx
0x180025ae5  push    rdi
0x180025ae6  sub     rsp, 20h
0x180025aea  mov     rbx, rdx
0x180025aed  mov     edi, ecx
0x180025aef  mov     cs:qword_180041C00, 0
0x180025afa  lea     rax, qword_180041C18
0x180025b01  mov     cs:WPP_MAIN_CB, rax
0x180025b08  mov     cs:qword_180041C08, 1
0x180025b13  mov     cs:qword_180041C28, 0
0x180025b1e  mov     cs:qword_180041C18, 0
0x180025b29  mov     cs:qword_180041C30, 1
0x180025b34  lea     rax, WPP_ThisDir_CTLGUID_ControlGuid
0x180025b3b  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180025b42  lea     rax, WPP_ThisDir_CTLGUID_MobTabPerfTraceProvider
0x180025b49  mov     cs:qword_180041BE8, rax
0x180025b50  lea     rax, WPP_MAIN_CB
0x180025b57  mov     cs:WPP_GLOBAL_Control, rax
0x180025b5e  call    WppInitUm
0x180025b63  mov     r9, rbx; unsigned __int16 **
0x180025b66  mov     r8d, edi; unsigned int
0x180025b69  call    ?Init@CServiceModule@@QEAAHPEAUHINSTANCE__@@KPEAPEAG@Z; CServiceModule::Init(HINSTANCE__ *,ulong,ushort * *)
0x180025b6e  test    eax, eax
0x180025b70  jz      short loc_180025B97
0x180025b72  call    ?Start@CServiceModule@@QEAAHXZ; CServiceModule::Start(void)
0x180025b77  test    eax, eax
0x180025b79  jz      short loc_180025B97
0x180025b7b  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x180025b82  call    ?ServiceMainBegin@CServiceModule@@QEAAHXZ; CServiceModule::ServiceMainBegin(void)
0x180025b87  test    eax, eax
0x180025b89  jnz     short loc_180025BA9
0x180025b8b  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x180025b92  call    ?Stop@CServiceModule@@QEAAXXZ; CServiceModule::Stop(void)
0x180025b97  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x180025b9e  call    ?Destroy@CServiceModule@@QEAAXXZ; CServiceModule::Destroy(void)
0x180025ba3  call    WppCleanupUm
0x180025ba8  nop
0x180025ba9  jmp     short $+2
0x180025bab  mov     rbx, [rsp+28h+arg_0]
0x180025bb0  add     rsp, 20h
0x180025bb4  pop     rdi
0x180025bb5  retn
```
