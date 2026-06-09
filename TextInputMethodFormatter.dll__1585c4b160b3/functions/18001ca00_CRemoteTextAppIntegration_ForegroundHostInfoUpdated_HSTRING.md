# CRemoteTextAppIntegration::ForegroundHostInfoUpdated(HSTRING__ *)

- ea: `0x18001ca00`
- end: `0x18001cabc`
- name: `?ForegroundHostInfoUpdated@CRemoteTextAppIntegration@@UEAAJPEAUHSTRING__@@@Z`
- size: `188`
- prototype: `int(CRemoteTextAppIntegration *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1800132f0`
- `0x18001ca00`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ca30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ca30`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18001ca57`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18001ca8c`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18001ca57`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18001ca8c`
- `CoreMessaging!MsgStringCreateShared` at `0x18001ca42`
- `CoreMessaging!MsgStringCreateShared` at `0x18001ca42`
- `CoreMessaging!MsgRelease` at `0x18001caa9`
- `CoreMessaging!MsgRelease` at `0x18001caa9`

## pseudocode

```c
__int64 __fastcall CRemoteTextAppIntegration::ForegroundHostInfoUpdated(CRemoteTextAppIntegration *this, HSTRING a2)
{
  unsigned int v2; // ebx
  PCWSTR StringRawBuffer; // rax
  int v5; // eax
  unsigned __int64 v6; // r8
  int v7; // eax
  unsigned __int64 retaddr; // [rsp+28h] [rbp+0h]
  UINT32 length; // [rsp+30h] [rbp+8h] BYREF
  __int64 v11; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  v11 = 0;
  if ( *((_QWORD *)this + 16) )
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, &length);
    v5 = MsgStringCreateShared(StringRawBuffer, length, &v11);
    v2 = v5;
    if ( v5 < 0 )
    {
      if ( v5 == -2147024882 )
        TerminateProcessOnMemoryExhaustion(0);
      v6 = 1238;
LABEL_10:
      FailFastWithHR(v2, retaddr, v6);
      goto LABEL_11;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 16) + 40LL))(*((_QWORD *)this + 16), v11);
    v2 = v7;
    if ( v7 < 0 )
    {
      if ( v7 == -2147024882 )
        TerminateProcessOnMemoryExhaustion(0);
      v6 = 1240;
      goto LABEL_10;
    }
  }
LABEL_11:
  MsgRelease(v11);
  return v2;
}

```

## disassembly

```asm
0x18001ca00  mov     [rsp+arg_8], rbx
0x18001ca05  push    rdi
0x18001ca06  sub     rsp, 20h
0x18001ca0a  xor     ebx, ebx
0x18001ca0c  mov     rax, rdx
0x18001ca0f  mov     rdi, rcx
0x18001ca12  mov     [rsp+28h+arg_10], rbx
0x18001ca17  cmp     [rcx+80h], rbx
0x18001ca1e  jz      loc_18001CAA4
0x18001ca24  lea     rdx, [rsp+28h+length]; length
0x18001ca29  mov     [rsp+28h+length], ebx
0x18001ca2d  mov     rcx, rax; string
0x18001ca30  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ca36  mov     edx, [rsp+28h+length]
0x18001ca3a  lea     r8, [rsp+28h+arg_10]
0x18001ca3f  mov     rcx, rax
0x18001ca42  call    cs:__imp_MsgStringCreateShared
0x18001ca48  mov     ebx, eax
0x18001ca4a  test    eax, eax
0x18001ca4c  jns     short loc_18001CA65
0x18001ca4e  cmp     eax, 8007000Eh
0x18001ca53  jnz     short loc_18001CA5D
0x18001ca55  xor     ecx, ecx; FailedAllocationSize
0x18001ca57  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x18001ca5d  mov     r8d, 4D6h
0x18001ca63  jmp     short loc_18001CA98
0x18001ca65  mov     rcx, [rdi+80h]
0x18001ca6c  mov     rdx, [rsp+28h+arg_10]
0x18001ca71  mov     rax, [rcx]
0x18001ca74  mov     rax, [rax+28h]
0x18001ca78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca7d  mov     ebx, eax
0x18001ca7f  test    eax, eax
0x18001ca81  jns     short loc_18001CAA4
0x18001ca83  cmp     eax, 8007000Eh
0x18001ca88  jnz     short loc_18001CA92
0x18001ca8a  xor     ecx, ecx; FailedAllocationSize
0x18001ca8c  call    cs:__imp_TerminateProcessOnMemoryExhaustion
0x18001ca92  mov     r8d, 4D8h; unsigned __int64
0x18001ca98  mov     rdx, [rsp+28h]; unsigned __int64
0x18001ca9d  mov     ecx, ebx; int
0x18001ca9f  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x18001caa4  mov     rcx, [rsp+28h+arg_10]
0x18001caa9  call    cs:__imp_MsgRelease
0x18001caaf  mov     eax, ebx
0x18001cab1  mov     rbx, [rsp+28h+arg_8]
0x18001cab6  add     rsp, 20h
0x18001caba  pop     rdi
0x18001cabb  retn
```
