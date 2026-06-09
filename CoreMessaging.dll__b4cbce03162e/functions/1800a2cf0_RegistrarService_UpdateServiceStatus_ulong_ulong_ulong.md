# RegistrarService::UpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x1800a2cf0`
- end: `0x1800a2d7b`
- name: `?UpdateServiceStatus@RegistrarService@@AEAAXKKK@Z`
- size: `139`
- prototype: `void __fastcall(RegistrarService *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800a2c50`

## callees

- `0x18003950c`
- `0x18008cc78`
- `0x18009d670`
- `0x1800a2cf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d25`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800a2d1b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800a2d1b`

## pseudocode

```c
void __fastcall RegistrarService::UpdateServiceStatus(RegistrarService *this, DWORD a2, __int64 a3, int a4)
{
  struct _SERVICE_STATUS *v5; // rdx
  SERVICE_STATUS_HANDLE v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  signed int LastError; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-28h] BYREF

  *((_DWORD *)this + 21) = 0;
  v5 = (struct _SERVICE_STATUS *)((char *)this + 72);
  *((_DWORD *)this + 24) = a4;
  v6 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 13);
  v5->dwCurrentState = a2;
  if ( !SetServiceStatus(v6, v5) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CFlat::Abandonment::FailWithHR(LastError, 0, 0);
  }
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v7, &CoreUIService_UpdateServiceStatus, v8, 1u, &v10);
}

```

## disassembly

```asm
0x1800a2cf0  sub     rsp, 58h
0x1800a2cf4  mov     rax, cs:__security_cookie
0x1800a2cfb  xor     rax, rsp
0x1800a2cfe  mov     [rsp+58h+var_18], rax
0x1800a2d03  mov     eax, edx
0x1800a2d05  mov     dword ptr [rcx+54h], 0
0x1800a2d0c  lea     rdx, [rcx+48h]; lpServiceStatus
0x1800a2d10  mov     [rcx+60h], r9d
0x1800a2d14  mov     rcx, [rcx+68h]; hServiceStatus
0x1800a2d18  mov     [rdx+4], eax
0x1800a2d1b  call    cs:__imp_SetServiceStatus
0x1800a2d21  test    eax, eax
0x1800a2d23  jnz     short loc_1800A2D44
0x1800a2d25  call    cs:__imp_GetLastError
0x1800a2d2b  test    eax, eax
0x1800a2d2d  jle     short loc_1800A2D37
0x1800a2d2f  movzx   eax, ax
0x1800a2d32  or      eax, 80070000h
0x1800a2d37  xor     r8d, r8d; int
0x1800a2d3a  xor     edx, edx; void *
0x1800a2d3c  mov     ecx, eax; int
0x1800a2d3e  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x1800a2d44  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 4
0x1800a2d4b  jz      short loc_1800A2D69
0x1800a2d4d  lea     rax, [rsp+58h+var_28]
0x1800a2d52  mov     r9d, 1
0x1800a2d58  lea     rdx, CoreUIService_UpdateServiceStatus
0x1800a2d5f  mov     [rsp+58h+var_38], rax
0x1800a2d64  call    McGenEventWrite_EventWriteTransfer
0x1800a2d69  mov     rcx, [rsp+58h+var_18]
0x1800a2d6e  xor     rcx, rsp; StackCookie
0x1800a2d71  call    __security_check_cookie
0x1800a2d76  add     rsp, 58h
0x1800a2d7a  retn
```
