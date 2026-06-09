# CWorkspaceNotifier::GetGlobalNotifierLock(void)

- ea: `0x18003f270`
- end: `0x18003f32f`
- name: `?GetGlobalNotifierLock@CWorkspaceNotifier@@AEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(CWorkspaceNotifier *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003f910`

## callees

- `0x18000b1d8`
- `0x18000ec94`
- `0x18003f270`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f308`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003f308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f2b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f2ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f2b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f2ef`
- `KERNEL32!CreateMutexW` at `0x18003f284`
- `KERNEL32!CreateMutexW` at `0x18003f284`

## pseudocode

```c
signed int __fastcall CWorkspaceNotifier::GetGlobalNotifierLock(CWorkspaceNotifier *this)
{
  HANDLE MutexW; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int result; // eax
  DWORD v7; // eax

  MutexW = CreateMutexW(0, 0, L"Local\\workspace_status_notifier");
  *((_QWORD *)this + 10) = MutexW;
  if ( MutexW )
  {
    v7 = WaitForSingleObject(MutexW, 0);
    if ( !v7 || v7 == 128 )
      return 0;
    if ( v7 == 258 )
      return -2147220991;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids,
      CurrentThreadActivityIdPrefix,
      v4);
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003f270  push    rbx
0x18003f272  sub     rsp, 30h
0x18003f276  mov     rbx, rcx
0x18003f279  lea     r8, Name; "Local\\workspace_status_notifier"
0x18003f280  xor     ecx, ecx; lpMutexAttributes
0x18003f282  xor     edx, edx; bInitialOwner
0x18003f284  call    cs:__imp_CreateMutexW
0x18003f28a  mov     [rbx+50h], rax
0x18003f28e  test    rax, rax
0x18003f291  jnz     short loc_18003F303
0x18003f293  mov     rax, cs:WPP_GLOBAL_Control
0x18003f29a  lea     rcx, WPP_GLOBAL_Control
0x18003f2a1  cmp     rax, rcx
0x18003f2a4  jz      short loc_18003F2EF
0x18003f2a6  test    byte ptr [rax+1Ch], 8
0x18003f2aa  jz      short loc_18003F2EF
0x18003f2ac  cmp     byte ptr [rax+19h], 2
0x18003f2b0  jb      short loc_18003F2EF
0x18003f2b2  call    cs:__imp_GetLastError
0x18003f2b8  mov     ebx, eax
0x18003f2ba  test    eax, eax
0x18003f2bc  jle     short loc_18003F2C7
0x18003f2be  movzx   ebx, ax
0x18003f2c1  or      ebx, 80070000h
0x18003f2c7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003f2cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f2d3  lea     r8, WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids
0x18003f2da  mov     edx, 0Ah
0x18003f2df  mov     [rsp+38h+var_18], ebx
0x18003f2e3  mov     r9d, eax
0x18003f2e6  mov     rcx, [rcx+10h]
0x18003f2ea  call    WPP_SF_Dd
0x18003f2ef  call    cs:__imp_GetLastError
0x18003f2f5  test    eax, eax
0x18003f2f7  jle     short loc_18003F329
0x18003f2f9  movzx   eax, ax
0x18003f2fc  or      eax, 80070000h
0x18003f301  jmp     short loc_18003F329
0x18003f303  xor     edx, edx; dwMilliseconds
0x18003f305  mov     rcx, rax; hHandle
0x18003f308  call    cs:__imp_WaitForSingleObject
0x18003f30e  test    eax, eax
0x18003f310  jz      short loc_18003F327
0x18003f312  cmp     eax, 80h
0x18003f317  jz      short loc_18003F327
0x18003f319  cmp     eax, 102h
0x18003f31e  jnz     short loc_18003F2EF
0x18003f320  mov     eax, 80040201h
0x18003f325  jmp     short loc_18003F329
0x18003f327  xor     eax, eax
0x18003f329  add     rsp, 30h
0x18003f32d  pop     rbx
0x18003f32e  retn
```
