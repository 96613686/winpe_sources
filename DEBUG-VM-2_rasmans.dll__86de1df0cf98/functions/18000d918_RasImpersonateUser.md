# RasImpersonateUser

- ea: `0x18000d918`
- end: `0x18000da54`
- name: `RasImpersonateUser`
- size: `316`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000db90`
- `0x180050534`
- `0x180052a20`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000d918`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18000d9be`
- `ntdll!NtSetInformationThread` at `0x18000d9be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d982`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000d978`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000d978`

## pseudocode

```c
__int64 __fastcall RasImpersonateUser(HANDLE ExistingTokenHandle)
{
  DWORD LastError; // eax
  DWORD v3; // ebx
  struct _LIST_ENTRY *v4; // rcx
  __int64 v5; // rdx
  void *DuplicateTokenHandle; // [rsp+38h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 10, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
  }
  DuplicateTokenHandle = 0;
  if ( DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
  {
    LastError = NtSetInformationThread(
                  (HANDLE)0xFFFFFFFFFFFFFFFELL,
                  ThreadImpersonationToken,
                  &DuplicateTokenHandle,
                  8u);
    v3 = LastError;
    if ( !LastError )
    {
LABEL_16:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v5 = 12;
      goto LABEL_15;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v5 = 11;
LABEL_15:
      WPP_SF_d(v4[1].Flink, v5, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, LastError);
      goto LABEL_16;
    }
  }
LABEL_17:
  if ( DuplicateTokenHandle )
  {
    CloseHandle(DuplicateTokenHandle);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 6u )
  {
    WPP_SF_d(v4[1].Flink, 13, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x18000d918  mov     [rsp+arg_0], rbx
0x18000d91d  mov     [rsp+arg_10], rsi
0x18000d922  push    rdi
0x18000d923  sub     rsp, 20h
0x18000d927  mov     rbx, rcx
0x18000d92a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d931  lea     rsi, WPP_GLOBAL_Control
0x18000d938  mov     edi, 2000h
0x18000d93d  cmp     rcx, rsi
0x18000d940  jz      short loc_18000D962
0x18000d942  test    [rcx+1Ch], edi
0x18000d945  jz      short loc_18000D962
0x18000d947  cmp     byte ptr [rcx+19h], 6
0x18000d94b  jb      short loc_18000D962
0x18000d94d  mov     rcx, [rcx+10h]
0x18000d951  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000d958  mov     edx, 0Ah
0x18000d95d  call    WPP_SF_
0x18000d962  lea     r8, [rsp+28h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18000d967  mov     [rsp+28h+DuplicateTokenHandle], 0
0x18000d970  mov     edx, 2; ImpersonationLevel
0x18000d975  mov     rcx, rbx; ExistingTokenHandle
0x18000d978  call    cs:__imp_DuplicateToken
0x18000d97e  test    eax, eax
0x18000d980  jnz     short loc_18000D9A8
0x18000d982  call    cs:__imp_GetLastError
0x18000d988  mov     ebx, eax
0x18000d98a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d991  cmp     rcx, rsi
0x18000d994  jz      short loc_18000DA00
0x18000d996  test    [rcx+1Ch], edi
0x18000d999  jz      short loc_18000DA00
0x18000d99b  cmp     byte ptr [rcx+19h], 2
0x18000d99f  jb      short loc_18000DA00
0x18000d9a1  mov     edx, 0Bh
0x18000d9a6  jmp     short loc_18000D9E6
0x18000d9a8  mov     r9d, 8; ThreadInformationLength
0x18000d9ae  lea     r8, [rsp+28h+DuplicateTokenHandle]; ThreadInformation
0x18000d9b3  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000d9ba  lea     edx, [r9-3]; ThreadInformationClass
0x18000d9be  call    cs:__imp_NtSetInformationThread
0x18000d9c4  mov     ebx, eax
0x18000d9c6  test    eax, eax
0x18000d9c8  jz      short loc_18000D9F9
0x18000d9ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9d1  cmp     rcx, rsi
0x18000d9d4  jz      short loc_18000DA00
0x18000d9d6  test    [rcx+1Ch], edi
0x18000d9d9  jz      short loc_18000DA00
0x18000d9db  cmp     byte ptr [rcx+19h], 2
0x18000d9df  jb      short loc_18000DA00
0x18000d9e1  mov     edx, 0Ch
0x18000d9e6  mov     rcx, [rcx+10h]
0x18000d9ea  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000d9f1  mov     r9d, eax
0x18000d9f4  call    WPP_SF_d
0x18000d9f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da00  mov     rax, [rsp+28h+DuplicateTokenHandle]
0x18000da05  test    rax, rax
0x18000da08  jz      short loc_18000DA1A
0x18000da0a  mov     rcx, rax; hObject
0x18000da0d  call    cs:__imp_CloseHandle
0x18000da13  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da1a  cmp     rcx, rsi
0x18000da1d  jz      short loc_18000DA42
0x18000da1f  test    [rcx+1Ch], edi
0x18000da22  jz      short loc_18000DA42
0x18000da24  cmp     byte ptr [rcx+19h], 6
0x18000da28  jb      short loc_18000DA42
0x18000da2a  mov     rcx, [rcx+10h]
0x18000da2e  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000da35  mov     edx, 0Dh
0x18000da3a  mov     r9d, ebx
0x18000da3d  call    WPP_SF_d
0x18000da42  mov     rsi, [rsp+28h+arg_10]
0x18000da47  mov     eax, ebx
0x18000da49  mov     rbx, [rsp+28h+arg_0]
0x18000da4e  add     rsp, 20h
0x18000da52  pop     rdi
0x18000da53  retn
```
