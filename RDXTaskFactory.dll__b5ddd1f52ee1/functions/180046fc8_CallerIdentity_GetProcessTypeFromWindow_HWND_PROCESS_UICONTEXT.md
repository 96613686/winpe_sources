# CallerIdentity::GetProcessTypeFromWindow(HWND__ *,PROCESS_UICONTEXT *)

- ea: `0x180046fc8`
- end: `0x180047065`
- name: `?GetProcessTypeFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAW4PROCESS_UICONTEXT@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, HWND, enum PROCESS_UICONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180038590`

## callees

- `0x180025cd8`
- `0x180046fc8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004704d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004704d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180047007`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180047007`
- `USER32!GetWindowThreadProcessId` at `0x180046fe6`
- `USER32!GetWindowThreadProcessId` at `0x180046fe6`
- `USER32!__imp_GetProcessUIContextInformation` at `0x180047031`
- `USER32!__imp_GetProcessUIContextInformation` at `0x180047031`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetProcessTypeFromWindow(
        CallerIdentity *this,
        _DWORD *a2,
        enum PROCESS_UICONTEXT *a3)
{
  int Error; // ebx
  HANDLE v5; // rdi
  DWORD dwProcessId; // [rsp+40h] [rbp+18h] BYREF
  __int64 v8; // [rsp+48h] [rbp+20h] BYREF

  dwProcessId = 0;
  if ( GetWindowThreadProcessId((HWND)this, &dwProcessId) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    v5 = OpenProcess(0x1000u, 0, dwProcessId);
    if ( v5 || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      v8 = 0;
      if ( (unsigned int)GetProcessUIContextInformation(v5, &v8) )
      {
        Error = 0;
        *a2 = v8;
      }
      else
      {
        Error = -2147024890;
      }
      CloseHandle(v5);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180046fc8  mov     rax, rsp
0x180046fcb  mov     [rax+8], rbx
0x180046fcf  mov     [rax+10h], rsi
0x180046fd3  push    rdi
0x180046fd4  sub     rsp, 20h
0x180046fd8  mov     rsi, rdx
0x180046fdb  mov     dword ptr [rax+18h], 0
0x180046fe2  lea     rdx, [rax+18h]; lpdwProcessId
0x180046fe6  call    cs:__imp_GetWindowThreadProcessId
0x180046fec  test    eax, eax
0x180046fee  jnz     short loc_180046FFB
0x180046ff0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180046ff5  mov     ebx, eax
0x180046ff7  test    eax, eax
0x180046ff9  js      short loc_180047053
0x180046ffb  mov     r8d, [rsp+28h+dwProcessId]; dwProcessId
0x180047000  xor     edx, edx; bInheritHandle
0x180047002  mov     ecx, 1000h; dwDesiredAccess
0x180047007  call    cs:__imp_OpenProcess
0x18004700d  mov     rdi, rax
0x180047010  test    rax, rax
0x180047013  jnz     short loc_180047020
0x180047015  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004701a  mov     ebx, eax
0x18004701c  test    eax, eax
0x18004701e  js      short loc_180047053
0x180047020  lea     rdx, [rsp+28h+arg_18]
0x180047025  mov     [rsp+28h+arg_18], 0
0x18004702e  mov     rcx, rdi
0x180047031  call    cs:__imp_GetProcessUIContextInformation
0x180047037  test    eax, eax
0x180047039  jz      short loc_180047045
0x18004703b  mov     eax, dword ptr [rsp+28h+arg_18]
0x18004703f  xor     ebx, ebx
0x180047041  mov     [rsi], eax
0x180047043  jmp     short loc_18004704A
0x180047045  mov     ebx, 80070006h
0x18004704a  mov     rcx, rdi; hObject
0x18004704d  call    cs:__imp_CloseHandle
0x180047053  mov     rsi, [rsp+28h+arg_8]
0x180047058  mov     eax, ebx
0x18004705a  mov     rbx, [rsp+28h+arg_0]
0x18004705f  add     rsp, 20h
0x180047063  pop     rdi
0x180047064  retn
```
