# CProcess::SendPBMNotification(__MIDL___MIDL_itf_audiosrv_0000_0000_0003)

- ea: `0x1800399cc`
- end: `0x180039a46`
- name: `?SendPBMNotification@CProcess@@QEAAJW4__MIDL___MIDL_itf_audiosrv_0000_0000_0003@@@Z`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180018204`
- `0x1800242f0`
- `0x180039230`

## callees

- `0x180031960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039a0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039a0c`
- `MMDevAPI!__imp_GenerateMediaEvent` at `0x180039a28`
- `MMDevAPI!__imp_GenerateMediaEvent` at `0x180039a28`

## pseudocode

```c
__int64 __fastcall CProcess::SendPBMNotification(__int64 a1, int a2)
{
  DWORD CurrentProcessId; // eax
  __int64 v5; // rdx
  _DWORD v7[2]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v8; // [rsp+28h] [rbp-30h]
  __int64 v9; // [rsp+38h] [rbp-20h]

  v9 = 0;
  v8 = 0;
  v7[0] = 32;
  v7[1] = 0x4000;
  CurrentProcessId = GetCurrentProcessId();
  v5 = *(unsigned int *)(a1 + 160);
  *(_QWORD *)&v8 = CurrentProcessId;
  LODWORD(v9) = a2;
  return GenerateMediaEvent(v7, v5);
}

```

## disassembly

```asm
0x1800399cc  mov     [rsp+arg_10], rbx
0x1800399d1  push    rdi
0x1800399d2  sub     rsp, 50h
0x1800399d6  mov     rax, cs:__security_cookie
0x1800399dd  xor     rax, rsp
0x1800399e0  mov     [rsp+58h+var_18], rax
0x1800399e5  xorps   xmm0, xmm0
0x1800399e8  mov     [rsp+58h+var_20], 0
0x1800399f1  movdqu  [rsp+58h+var_30], xmm0
0x1800399f7  mov     edi, edx
0x1800399f9  mov     [rsp+58h+var_38], 20h ; ' '
0x180039a01  mov     rbx, rcx
0x180039a04  mov     [rsp+58h+var_34], 4000h
0x180039a0c  call    cs:__imp_GetCurrentProcessId
0x180039a12  mov     edx, [rbx+0A0h]
0x180039a18  lea     rcx, [rsp+58h+var_38]
0x180039a1d  mov     eax, eax
0x180039a1f  mov     qword ptr [rsp+58h+var_30], rax
0x180039a24  mov     dword ptr [rsp+58h+var_20], edi
0x180039a28  call    cs:__imp_GenerateMediaEvent
0x180039a2e  mov     rcx, [rsp+58h+var_18]
0x180039a33  xor     rcx, rsp; StackCookie
0x180039a36  call    __security_check_cookie
0x180039a3b  mov     rbx, [rsp+58h+arg_10]
0x180039a40  add     rsp, 50h
0x180039a44  pop     rdi
0x180039a45  retn
```
