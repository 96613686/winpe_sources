# CAxisServModule::HandleGPNotifications(void)

- ea: `0x18000bbfc`
- end: `0x18000bcf7`
- name: `?HandleGPNotifications@CAxisServModule@@QEAAJXZ`
- size: `251`
- prototype: `__int64 __fastcall(CAxisServModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180010e80`

## callees

- `0x180004364`
- `0x18000725c`
- `0x18000bbfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bca1`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000bc38`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000bc38`

## string_xrefs

- `0x18000bcd3`: `Exiting Policy Watch Thread`
- `0x18000bc8d`: `Successfully updated Policy `

## pseudocode

```c
__int64 __fastcall CAxisServModule::HandleGPNotifications(CAxisServModule *this)
{
  unsigned int v1; // ebx
  DWORD v3; // eax
  DWORD v4; // esi
  int updated; // eax
  signed int LastError; // eax
  __int64 v8; // [rsp+20h] [rbp-48h]
  HANDLE Handles[7]; // [rsp+30h] [rbp-38h] BYREF

  v1 = 0;
  Handles[0] = *((HANDLE *)this + 10);
  Handles[1] = *((HANDLE *)this + 11);
  while ( 1 )
  {
    v3 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    v4 = v3;
    if ( !v3 )
    {
      AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 5u, L"Exiting Policy Watch Thread");
      return v1;
    }
    if ( v3 != 1 )
      break;
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 5u, L"GP Event triggeed.");
    updated = CPolicyCheck::UpdatePolicyFromGP((HKEY *)this + 162);
    if ( updated >= 0 )
    {
      AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 4u, L"Successfully updated Policy ");
    }
    else
    {
      LODWORD(v8) = updated;
      AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, v4 + 1, L"Error Updating Policy from GP 0x%x", v8);
    }
  }
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  LODWORD(v8) = v4;
  AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 5u, L"Unknown Error in HandleGPNotifications %d", v8);
  return v1;
}

```

## disassembly

```asm
0x18000bbfc  push    rbx
0x18000bbfe  push    rbp
0x18000bbff  push    rsi
0x18000bc00  push    rdi
0x18000bc01  push    r14
0x18000bc03  sub     rsp, 40h
0x18000bc07  mov     rax, [rcx+50h]
0x18000bc0b  lea     r14, qword_180021AD8
0x18000bc12  xor     ebx, ebx
0x18000bc14  mov     [rsp+68h+Handles], rax
0x18000bc19  mov     rax, [rcx+58h]
0x18000bc1d  mov     rdi, rcx
0x18000bc20  mov     [rsp+68h+var_30], rax
0x18000bc25  lea     ebp, [rbx+8]
0x18000bc28  xor     r8d, r8d; bWaitAll
0x18000bc2b  lea     rdx, [rsp+68h+Handles]; lpHandles
0x18000bc30  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000bc34  lea     ecx, [r8+2]; nCount
0x18000bc38  call    cs:__imp_WaitForMultipleObjects
0x18000bc3e  mov     esi, eax
0x18000bc40  test    eax, eax
0x18000bc42  jz      loc_18000BCD3
0x18000bc48  cmp     eax, 1
0x18000bc4b  jnz     short loc_18000BCA1
0x18000bc4d  lea     r9, aGpEventTriggee; "GP Event triggeed."
0x18000bc54  mov     edx, ebp; unsigned int
0x18000bc56  lea     r8d, [rax+4]; unsigned __int8
0x18000bc5a  mov     rcx, r14; this
0x18000bc5d  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000bc62  lea     rcx, [rdi+510h]; this
0x18000bc69  call    ?UpdatePolicyFromGP@CPolicyCheck@@QEAAJXZ; CPolicyCheck::UpdatePolicyFromGP(void)
0x18000bc6e  mov     edx, ebp; unsigned int
0x18000bc70  mov     rcx, r14; this
0x18000bc73  test    eax, eax
0x18000bc75  jns     short loc_18000BC8D
0x18000bc77  lea     r9, aErrorUpdatingP; "Error Updating Policy from GP 0x%x"
0x18000bc7e  mov     [rsp+68h+var_48], eax
0x18000bc82  lea     r8d, [rsi+1]; unsigned __int8
0x18000bc86  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000bc8b  jmp     short loc_18000BC28
0x18000bc8d  lea     r9, aSuccessfullyUp; "Successfully updated Policy "
0x18000bc94  mov     r8d, 4; unsigned __int8
0x18000bc9a  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000bc9f  jmp     short loc_18000BC28
0x18000bca1  call    cs:__imp_GetLastError
0x18000bca7  mov     ebx, eax
0x18000bca9  test    eax, eax
0x18000bcab  jle     short loc_18000BCB6
0x18000bcad  movzx   ebx, ax
0x18000bcb0  or      ebx, 80070000h
0x18000bcb6  lea     r9, aUnknownErrorIn; "Unknown Error in HandleGPNotifications "...
0x18000bcbd  mov     [rsp+68h+var_48], esi
0x18000bcc1  mov     r8d, 5; unsigned __int8
0x18000bcc7  mov     edx, ebp; unsigned int
0x18000bcc9  mov     rcx, r14; this
0x18000bccc  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000bcd1  jmp     short loc_18000BCEA
0x18000bcd3  lea     r9, aExitingPolicyW; "Exiting Policy Watch Thread"
0x18000bcda  mov     r8d, 5; unsigned __int8
0x18000bce0  mov     edx, ebp; unsigned int
0x18000bce2  mov     rcx, r14; this
0x18000bce5  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000bcea  mov     eax, ebx
0x18000bcec  add     rsp, 40h
0x18000bcf0  pop     r14
0x18000bcf2  pop     rdi
0x18000bcf3  pop     rsi
0x18000bcf4  pop     rbp
0x18000bcf5  pop     rbx
0x18000bcf6  retn
```
