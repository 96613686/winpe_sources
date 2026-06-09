# RegistrarService::Initialize(void)

- ea: `0x1800a2c50`
- end: `0x1800a2cd6`
- name: `?Initialize@RegistrarService@@AEAAXXZ`
- size: `134`
- prototype: `void __fastcall(RegistrarService *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1800a2bcc`

## callees

- `0x18003950c`
- `0x1800a2c50`
- `0x1800a2cf0`
- `0x1800a388c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2c80`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800a2c71`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800a2c71`

## pseudocode

```c
void __fastcall RegistrarService::Initialize(RegistrarService *this)
{
  SERVICE_STATUS_HANDLE v2; // rax
  unsigned int v3; // r8d
  signed int LastError; // eax
  unsigned int v5; // r8d

  *((_DWORD *)this + 18) = 32;
  v2 = RegisterServiceCtrlHandlerExW(L"CoreMessagingRegistrar", RegistrarService::ServiceControlHandler, this);
  *((_QWORD *)this + 13) = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CFlat::Abandonment::FailWithHR(LastError, 0, 0);
  }
  RegistrarService::UpdateServiceStatus(this, 2u, v3, 0x2710u);
  RegistrarHost::Initialize((__int64)this, 0, 0, 0);
  RegistrarService::UpdateServiceStatus(this, 4u, v5, 0);
}

```

## disassembly

```asm
0x1800a2c50  push    rbx
0x1800a2c52  sub     rsp, 20h
0x1800a2c56  mov     rbx, rcx
0x1800a2c59  mov     dword ptr [rcx+48h], 20h ; ' '
0x1800a2c60  mov     r8, rcx; lpContext
0x1800a2c63  lea     rdx, ?ServiceControlHandler@RegistrarService@@CAKKKPEAX0@Z; lpHandlerProc
0x1800a2c6a  lea     rcx, ServiceName; "CoreMessagingRegistrar"
0x1800a2c71  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800a2c77  mov     [rbx+68h], rax
0x1800a2c7b  test    rax, rax
0x1800a2c7e  jnz     short loc_1800A2C9F
0x1800a2c80  call    cs:__imp_GetLastError
0x1800a2c86  test    eax, eax
0x1800a2c88  jle     short loc_1800A2C92
0x1800a2c8a  movzx   eax, ax
0x1800a2c8d  or      eax, 80070000h
0x1800a2c92  xor     r8d, r8d; int
0x1800a2c95  xor     edx, edx; void *
0x1800a2c97  mov     ecx, eax; int
0x1800a2c99  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x1800a2c9f  mov     edx, 2; unsigned int
0x1800a2ca4  mov     r9d, 2710h; unsigned int
0x1800a2caa  mov     rcx, rbx; this
0x1800a2cad  call    ?UpdateServiceStatus@RegistrarService@@AEAAXKKK@Z; RegistrarService::UpdateServiceStatus(ulong,ulong,ulong)
0x1800a2cb2  xor     r9d, r9d
0x1800a2cb5  xor     r8d, r8d
0x1800a2cb8  xor     edx, edx
0x1800a2cba  mov     rcx, rbx
0x1800a2cbd  call    ?Initialize@RegistrarHost@@IEAAXW4ServiceRunMode@Registrar@CoreUI@Microsoft@@PEBU_GUID@@1@Z; RegistrarHost::Initialize(Microsoft::CoreUI::Registrar::ServiceRunMode,_GUID const *,_GUID const *)
0x1800a2cc2  xor     r9d, r9d; unsigned int
0x1800a2cc5  mov     rcx, rbx; this
0x1800a2cc8  lea     edx, [r9+4]; unsigned int
0x1800a2ccc  add     rsp, 20h
0x1800a2cd0  pop     rbx
0x1800a2cd1  jmp     ?UpdateServiceStatus@RegistrarService@@AEAAXKKK@Z; RegistrarService::UpdateServiceStatus(ulong,ulong,ulong)
```
