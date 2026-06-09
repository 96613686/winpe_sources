# UpdateReserveManager::TagSnapshots(void)

- ea: `0x180020200`
- end: `0x1800203c1`
- name: `?TagSnapshots@UpdateReserveManager@@AEAAJXZ`
- size: `449`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800155e0`

## callees

- `0x180003870`
- `0x180008140`
- `0x18000fafc`
- `0x180015ad0`
- `0x18001a8f0`
- `0x180020200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002025c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020396`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002025c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020376`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800202b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800202b0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180020347`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180020347`

## string_xrefs

- `0x1800202c6`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800202d1`: `UpdateReserveManager::TagSnapshots`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::TagSnapshots(UpdateReserveManager *this)
{
  int ValueW; // ebx
  HANDLE *v4; // [rsp+40h] [rbp-19h] BYREF
  char v5; // [rsp+48h] [rbp-11h]
  _QWORD v6[5]; // [rsp+50h] [rbp-9h] BYREF
  int pvData; // [rsp+78h] [rbp+1Fh] BYREF
  DWORD pcbData; // [rsp+7Ch] [rbp+23h] BYREF
  int InBuffer; // [rsp+80h] [rbp+27h] BYREF

  v6[4] = -2;
  v4 = (HANDLE *)((char *)this + 1192);
  v5 = 0;
  ValueW = AutoMutexLocker::Lock(&v4);
  if ( ValueW < 0 || (ValueW = UpdateReserveManager::EnsureNotInSafeMode(this), ValueW < 0) )
  {
LABEL_2:
    if ( v5 )
    {
      if ( *v4 )
        ReleaseMutex(*v4);
    }
    return (unsigned int)ValueW;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             *((HKEY *)this + 13),
             L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
             L"DisableSnapshotsInReserves",
             0x10u,
             0,
             &pvData,
             &pcbData);
  if ( ValueW == 2 )
  {
    pvData = 0;
  }
  else
  {
    if ( ValueW )
    {
      v6[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v6[1] = "UpdateReserveManager::TagSnapshots";
      v6[2] = 1771;
      v6[3] = "RetValue";
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
      RtlReportErrorOrigination(v6, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
      goto LABEL_2;
    }
    if ( pvData )
      goto LABEL_21;
  }
  InBuffer = 1;
  if ( !DeviceIoControl(*((HANDLE *)this + 16), 0x53C0B0u, &InBuffer, 4u, 0, 0, 0, 0) )
  {
    if ( GetLastError() )
    {
      ValueW = GetLastError();
      if ( !ValueW )
        INTERNAL_ERROR_ACTION(-1073741595);
    }
    else
    {
      ValueW = 14077;
    }
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_2;
  }
LABEL_21:
  if ( v5 && *v4 )
    ReleaseMutex(*v4);
  return 0;
}

```

## disassembly

```asm
0x180020200  push    rbp
0x180020202  push    rbx
0x180020203  push    rsi
0x180020204  push    rdi
0x180020205  lea     rbp, [rsp-3Fh]
0x18002020a  sub     rsp, 98h
0x180020211  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x180020219  mov     rax, cs:__security_cookie
0x180020220  xor     rax, rsp
0x180020223  mov     [rbp+57h+var_28], rax
0x180020227  mov     rdi, rcx
0x18002022a  lea     rax, [rcx+4A8h]
0x180020231  mov     [rbp+57h+var_70], rax
0x180020235  xor     esi, esi
0x180020237  mov     [rbp+57h+var_68], sil
0x18002023b  lea     rcx, [rbp+57h+var_70]; this
0x18002023f  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x180020244  mov     ebx, eax
0x180020246  test    eax, eax
0x180020248  jns     short loc_180020269
0x18002024a  cmp     [rbp+57h+var_68], sil
0x18002024e  jz      short loc_180020262
0x180020250  mov     rcx, [rbp+57h+var_70]
0x180020254  mov     rcx, [rcx]; hMutex
0x180020257  test    rcx, rcx
0x18002025a  jz      short loc_180020262
0x18002025c  call    cs:__imp_ReleaseMutex
0x180020262  mov     eax, ebx
0x180020264  jmp     loc_18002039E
0x180020269  mov     rcx, rdi; this
0x18002026c  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x180020271  mov     ebx, eax
0x180020273  test    eax, eax
0x180020275  js      short loc_18002024A
0x180020277  mov     [rbp+57h+var_38], esi
0x18002027a  mov     [rbp+57h+var_34], 4
0x180020281  lea     rax, [rbp+57h+var_34]
0x180020285  mov     [rsp+0B0h+pcbData], rax; pcbData
0x18002028a  lea     rax, [rbp+57h+var_38]
0x18002028e  mov     [rsp+0B0h+pvData], rax; pvData
0x180020293  mov     [rsp+0B0h+pdwType], rsi; pdwType
0x180020298  mov     r9d, 10h; dwFlags
0x18002029e  lea     r8, aDisablesnapsho; "DisableSnapshotsInReserves"
0x1800202a5  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x1800202ac  mov     rcx, [rdi+68h]; hkey
0x1800202b0  call    cs:__imp_RegGetValueW
0x1800202b6  mov     ebx, eax
0x1800202b8  cmp     eax, 2
0x1800202bb  jnz     short loc_1800202C2
0x1800202bd  mov     [rbp+57h+var_38], esi
0x1800202c0  jmp     short loc_180020317
0x1800202c2  test    ebx, ebx
0x1800202c4  jz      short loc_180020312
0x1800202c6  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800202cd  mov     [rbp+57h+var_60], rax
0x1800202d1  lea     rax, aUpdatereservem_7; "UpdateReserveManager::TagSnapshots"
0x1800202d8  mov     [rbp+57h+var_58], rax
0x1800202dc  mov     [rbp+57h+var_50], 6EBh
0x1800202e4  lea     rax, aRetvalue; "RetValue"
0x1800202eb  mov     [rbp+57h+var_48], rax
0x1800202ef  jle     short loc_1800202FA
0x1800202f1  movzx   ebx, bx
0x1800202f4  or      ebx, 80070000h
0x1800202fa  mov     r8d, ebx
0x1800202fd  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180020304  lea     rcx, [rbp+57h+var_60]
0x180020308  call    RtlReportErrorOrigination
0x18002030d  jmp     loc_18002024A
0x180020312  cmp     [rbp+57h+var_38], esi
0x180020315  jnz     short loc_180020384
0x180020317  mov     [rbp+57h+InBuffer], 1
0x18002031e  mov     [rsp+0B0h+lpOverlapped], rsi; lpOverlapped
0x180020323  mov     [rsp+0B0h+pcbData], rsi; lpBytesReturned
0x180020328  mov     dword ptr [rsp+0B0h+pvData], esi; nOutBufferSize
0x18002032c  mov     [rsp+0B0h+pdwType], rsi; lpOutBuffer
0x180020331  mov     r9d, 4; nInBufferSize
0x180020337  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18002033b  mov     edx, 53C0B0h; dwIoControlCode
0x180020340  mov     rcx, [rdi+80h]; hDevice
0x180020347  call    cs:__imp_DeviceIoControl
0x18002034d  test    eax, eax
0x18002034f  jnz     short loc_180020384
0x180020351  call    cs:__imp_GetLastError
0x180020357  test    eax, eax
0x180020359  jnz     short loc_180020376
0x18002035b  mov     ebx, 36FDh
0x180020360  test    ebx, ebx
0x180020362  jle     loc_18002024A
0x180020368  movzx   ebx, bx
0x18002036b  or      ebx, 80070000h
0x180020371  jmp     loc_18002024A
0x180020376  call    cs:__imp_GetLastError
0x18002037c  mov     ebx, eax
0x18002037e  test    eax, eax
0x180020380  jz      short loc_1800203B6
0x180020382  jmp     short loc_180020360
0x180020384  cmp     [rbp+57h+var_68], sil
0x180020388  jz      short loc_18002039C
0x18002038a  mov     rax, [rbp+57h+var_70]
0x18002038e  mov     rcx, [rax]; hMutex
0x180020391  test    rcx, rcx
0x180020394  jz      short loc_18002039C
0x180020396  call    cs:__imp_ReleaseMutex
0x18002039c  xor     eax, eax
0x18002039e  mov     rcx, [rbp+57h+var_28]
0x1800203a2  xor     rcx, rsp; StackCookie
0x1800203a5  call    __security_check_cookie
0x1800203aa  add     rsp, 98h
0x1800203b1  pop     rdi
0x1800203b2  pop     rsi
0x1800203b3  pop     rbx
0x1800203b4  pop     rbp
0x1800203b5  retn
0x1800203b6  mov     ecx, 0C00000E5h; int
0x1800203bb  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
