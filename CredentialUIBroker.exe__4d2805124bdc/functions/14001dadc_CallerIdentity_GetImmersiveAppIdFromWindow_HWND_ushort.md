# CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)

- ea: `0x14001dadc`
- end: `0x14001dbe0`
- name: `?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z`
- size: `260`
- prototype: `__int64 __fastcall(CallerIdentity *this, HWND, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14001d968`

## callees

- `0x140009064`
- `0x14000d9e8`
- `0x1400136dc`
- `0x1400136fc`
- `0x14001d320`
- `0x14001dadc`
- `0x14001dc30`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x14001db2d`
- `KERNEL32!OpenProcess` at `0x14001db2d`
- `USER32!GetWindowThreadProcessId` at `0x14001dafe`
- `USER32!GetWindowThreadProcessId` at `0x14001dafe`
- `USER32!__imp_GetProcessUIContextInformation` at `0x14001db5e`
- `USER32!__imp_GetProcessUIContextInformation` at `0x14001db5e`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetImmersiveAppIdFromWindow(CallerIdentity *this, HWND a2, unsigned __int16 **a3)
{
  const char *v5; // r9
  wil::details *v7; // rcx
  HANDLE v8; // rbx
  int ProcessAppId; // eax
  unsigned __int16 **v10; // r8
  const char *v11; // r9
  unsigned int v12; // ebx
  int WeakWindowAppId; // eax
  int v14; // esi
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD dwProcessId; // [rsp+48h] [rbp+10h] BYREF
  __int64 v18; // [rsp+50h] [rbp+18h] BYREF
  HANDLE v19; // [rsp+58h] [rbp+20h] BYREF

  *(_QWORD *)a2 = 0;
  dwProcessId = 0;
  if ( !GetWindowThreadProcessId((HWND)this, &dwProcessId) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x6C,
             (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_window.cpp",
             v5);
  v8 = OpenProcess(0x1000u, 0, dwProcessId);
  v19 = v8;
  if ( (((unsigned __int64)v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v18 = 0;
    if ( (unsigned int)GetProcessUIContextInformation(v8, &v18) )
    {
      if ( (_DWORD)v18 == 2 )
      {
        WeakWindowAppId = CallerIdentity::GetWeakWindowAppId(this, a2, v10);
        v14 = WeakWindowAppId;
        if ( WeakWindowAppId < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x79,
            (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_window.cpp",
            (const char *)(unsigned int)WeakWindowAppId,
            v15);
          v12 = v14;
          goto LABEL_14;
        }
      }
      if ( *(_QWORD *)a2 || (ProcessAppId = CallerIdentity::GetProcessAppId(v8, a2, v10), ProcessAppId >= 0) )
      {
        v12 = 0;
        goto LABEL_14;
      }
    }
    else
    {
      ProcessAppId = wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       (void *)0x72,
                       (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_window.cpp",
                       v11);
    }
  }
  else
  {
    ProcessAppId = wil::details::GetLastErrorFailHr(v7);
  }
  v12 = ProcessAppId;
LABEL_14:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
  return v12;
}

```

## disassembly

```asm
0x14001dadc  push    rbx
0x14001dade  push    rsi
0x14001dadf  push    rdi; int
0x14001dae0  sub     rsp, 20h
0x14001dae4  mov     rdi, rdx
0x14001dae7  mov     qword ptr [rdx], 0
0x14001daee  lea     rdx, [rsp+38h+dwProcessId]; lpdwProcessId
0x14001daf3  mov     [rsp+38h+dwProcessId], 0
0x14001dafb  mov     rsi, rcx
0x14001dafe  call    cs:__imp_GetWindowThreadProcessId
0x14001db04  test    eax, eax
0x14001db06  jnz     short loc_14001DB21
0x14001db08  mov     rcx, [rsp+38h]; this
0x14001db0d  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x14001db14  lea     edx, [rax+6Ch]; void *
0x14001db17  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001db1c  jmp     loc_14001DBD8
0x14001db21  mov     r8d, [rsp+38h+dwProcessId]; dwProcessId
0x14001db26  xor     edx, edx; bInheritHandle
0x14001db28  mov     ecx, 1000h; dwDesiredAccess
0x14001db2d  call    cs:__imp_OpenProcess
0x14001db33  mov     rbx, rax
0x14001db36  mov     [rsp+38h+arg_18], rax
0x14001db3b  inc     rax
0x14001db3e  test    rax, 0FFFFFFFFFFFFFFFEh
0x14001db44  jnz     short loc_14001DB4D
0x14001db46  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14001db4b  jmp     short loc_14001DB7C
0x14001db4d  lea     rdx, [rsp+38h+arg_10]
0x14001db52  mov     [rsp+38h+arg_10], 0
0x14001db5b  mov     rcx, rbx
0x14001db5e  call    cs:__imp_GetProcessUIContextInformation
0x14001db64  test    eax, eax
0x14001db66  jnz     short loc_14001DB80
0x14001db68  mov     rcx, [rsp+38h]; this
0x14001db6d  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x14001db74  lea     edx, [rax+72h]; void *
0x14001db77  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001db7c  mov     ebx, eax
0x14001db7e  jmp     short loc_14001DBCC
0x14001db80  cmp     dword ptr [rsp+38h+arg_10], 2
0x14001db85  jnz     short loc_14001DBB5
0x14001db87  mov     rdx, rdi; HWND
0x14001db8a  mov     rcx, rsi; this
0x14001db8d  call    ?GetWeakWindowAppId@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetWeakWindowAppId(HWND__ *,ushort * *)
0x14001db92  mov     esi, eax
0x14001db94  test    eax, eax
0x14001db96  jns     short loc_14001DBB5
0x14001db98  mov     rcx, [rsp+38h]; this
0x14001db9d  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x14001dba4  mov     r9d, eax; char *
0x14001dba7  mov     edx, 79h ; 'y'; void *
0x14001dbac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001dbb1  mov     ebx, esi
0x14001dbb3  jmp     short loc_14001DBCC
0x14001dbb5  cmp     qword ptr [rdi], 0
0x14001dbb9  jnz     short loc_14001DBCA
0x14001dbbb  mov     rdx, rdi; void *
0x14001dbbe  mov     rcx, rbx; ProcessHandle
0x14001dbc1  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x14001dbc6  test    eax, eax
0x14001dbc8  js      short loc_14001DB7C
0x14001dbca  xor     ebx, ebx
0x14001dbcc  lea     rcx, [rsp+38h+arg_18]
0x14001dbd1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14001dbd6  mov     eax, ebx
0x14001dbd8  add     rsp, 20h
0x14001dbdc  pop     rdi
0x14001dbdd  pop     rsi
0x14001dbde  pop     rbx
0x14001dbdf  retn
```
