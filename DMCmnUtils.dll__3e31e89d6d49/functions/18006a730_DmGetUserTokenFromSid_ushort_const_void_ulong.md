# DmGetUserTokenFromSid(ushort const *,void * *,ulong *)

- ea: `0x18006a730`
- end: `0x18006a856`
- name: `?DmGetUserTokenFromSid@@YAJPEBGPEAPEAXPEAK@Z`
- size: `294`
- prototype: `int(const unsigned __int16 *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180071b24`

## callees

- `0x18005ccbc`
- `0x18006a730`
- `0x18006c63c`
- `0x18006c710`
- `0x18006c910`
- `0x18006cea8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006a7a5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006a7a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a804`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18006a7f4`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18006a7f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006a7e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006a7e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a834`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a834`

## pseudocode

```c
__int64 __fastcall DmGetUserTokenFromSid(const unsigned __int16 *a1, void **a2, unsigned int *a3)
{
  void *v3; // rdi
  int UserTokenFromSid; // ebx
  int CurrentUserSid; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  WINBOOL IsMember; // [rsp+48h] [rbp+10h] BYREF
  void *v15; // [rsp+50h] [rbp+18h] BYREF

  v3 = 0;
  IsMember = 0;
  v15 = 0;
  *a2 = 0;
  if ( a3 )
    *a3 = -1;
  UserTokenFromSid = IsRunningInSystemContext(&IsMember);
  if ( UserTokenFromSid >= 0 )
  {
    if ( IsMember )
    {
      UserTokenFromSid = GetUserTokenFromSid((__int64)a1, a2, a3);
    }
    else
    {
      CurrentUserSid = GetCurrentUserSid(&v15);
      v3 = v15;
      UserTokenFromSid = CurrentUserSid;
      if ( CurrentUserSid >= 0 )
      {
        if ( (unsigned int)_o__wcsicmp(v15, a1) )
        {
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x4000) != 0 )
            McTemplateU0zz_EventWriteTransfer(v10, v9, v3, a1);
          UserTokenFromSid = -2147024891;
        }
        else
        {
          UserTokenFromSid = GetCurrentUserToken(a2);
          if ( UserTokenFromSid >= 0 )
          {
            if ( a3 )
            {
              CurrentProcessId = GetCurrentProcessId();
              if ( !ProcessIdToSessionId(CurrentProcessId, a3) )
              {
                LastError = GetLastError();
                UserTokenFromSid = LastError;
                if ( LastError > 0 )
                  UserTokenFromSid = (unsigned __int16)LastError | 0x80070000;
              }
            }
          }
        }
      }
    }
  }
  LocalFree(v3);
  return (unsigned int)UserTokenFromSid;
}

```

## disassembly

```asm
0x18006a730  mov     rax, rsp
0x18006a733  mov     [rax+8], rbx
0x18006a737  mov     [rax+20h], rbp
0x18006a73b  push    rsi
0x18006a73c  push    rdi
0x18006a73d  push    r14
0x18006a73f  sub     rsp, 20h
0x18006a743  xor     edi, edi
0x18006a745  mov     dword ptr [rax+10h], 0
0x18006a74c  mov     [rax+18h], rdi
0x18006a750  mov     rsi, r8
0x18006a753  mov     [rdx], rdi
0x18006a756  mov     r14, rdx
0x18006a759  mov     rbp, rcx
0x18006a75c  test    r8, r8
0x18006a75f  jz      short loc_18006A768
0x18006a761  mov     dword ptr [r8], 0FFFFFFFFh
0x18006a768  lea     rcx, [rsp+38h+IsMember]; IsMember
0x18006a76d  call    IsRunningInSystemContext
0x18006a772  mov     ebx, eax
0x18006a774  test    eax, eax
0x18006a776  js      loc_18006A831
0x18006a77c  cmp     [rsp+38h+IsMember], edi
0x18006a780  jnz     loc_18006A821
0x18006a786  lea     rcx, [rsp+38h+arg_10]
0x18006a78b  call    GetCurrentUserSid
0x18006a790  mov     rdi, [rsp+38h+arg_10]
0x18006a795  mov     ebx, eax
0x18006a797  test    eax, eax
0x18006a799  js      loc_18006A831
0x18006a79f  mov     rdx, rbp
0x18006a7a2  mov     rcx, rdi
0x18006a7a5  call    cs:__imp__o__wcsicmp
0x18006a7ac  nop     dword ptr [rax+rax+00h]
0x18006a7b1  test    eax, eax
0x18006a7b3  jz      short loc_18006A7D0
0x18006a7b5  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits+1, 40h
0x18006a7bc  jz      short loc_18006A7C9
0x18006a7be  mov     r9, rbp
0x18006a7c1  mov     r8, rdi
0x18006a7c4  call    McTemplateU0zz_EventWriteTransfer
0x18006a7c9  mov     ebx, 80070005h
0x18006a7ce  jmp     short loc_18006A831
0x18006a7d0  mov     rcx, r14; TokenHandle
0x18006a7d3  call    GetCurrentUserToken
0x18006a7d8  mov     ebx, eax
0x18006a7da  test    eax, eax
0x18006a7dc  js      short loc_18006A831
0x18006a7de  test    rsi, rsi
0x18006a7e1  jz      short loc_18006A831
0x18006a7e3  call    cs:__imp_GetCurrentProcessId
0x18006a7ea  nop     dword ptr [rax+rax+00h]
0x18006a7ef  mov     ecx, eax; dwProcessId
0x18006a7f1  mov     rdx, rsi; pSessionId
0x18006a7f4  call    cs:__imp_ProcessIdToSessionId
0x18006a7fb  nop     dword ptr [rax+rax+00h]
0x18006a800  test    eax, eax
0x18006a802  jnz     short loc_18006A831
0x18006a804  call    cs:__imp_GetLastError
0x18006a80b  nop     dword ptr [rax+rax+00h]
0x18006a810  mov     ebx, eax
0x18006a812  test    eax, eax
0x18006a814  jle     short loc_18006A831
0x18006a816  movzx   ebx, ax
0x18006a819  or      ebx, 80070000h
0x18006a81f  jmp     short loc_18006A831
0x18006a821  mov     r8, rsi
0x18006a824  mov     rdx, r14
0x18006a827  mov     rcx, rbp
0x18006a82a  call    GetUserTokenFromSid
0x18006a82f  mov     ebx, eax
0x18006a831  mov     rcx, rdi; hMem
0x18006a834  call    cs:__imp_LocalFree
0x18006a83b  nop     dword ptr [rax+rax+00h]
0x18006a840  mov     rbp, [rsp+38h+arg_18]
0x18006a845  mov     eax, ebx
0x18006a847  mov     rbx, [rsp+38h+arg_0]
0x18006a84c  add     rsp, 20h
0x18006a850  pop     r14
0x18006a852  pop     rdi
0x18006a853  pop     rsi
0x18006a854  retn
```
