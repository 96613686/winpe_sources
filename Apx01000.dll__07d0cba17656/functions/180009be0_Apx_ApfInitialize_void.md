# Apx::ApfInitialize(void)

- ea: `0x180009be0`
- end: `0x180009d20`
- name: `?ApfInitialize@Apx@@YAJXZ`
- size: `320`
- prototype: `__int64 __fastcall(Apx *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180025600`

## callees

- `0x18000163c`
- `0x180001d30`
- `0x180009be0`
- `0x180009d28`
- `0x18000a12c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009c69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009c69`

## pseudocode

```c
__int64 __fastcall Apx::ApfInitialize(Apx *this)
{
  __int64 v1; // rbx
  __int64 v3; // [rsp+30h] [rbp-68h] BYREF
  __int64 v4; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v5[32]; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v6; // [rsp+60h] [rbp-38h]
  __int64 v7; // [rsp+68h] [rbp-30h]
  __int64 *v8; // [rsp+70h] [rbp-28h]
  __int64 v9; // [rsp+78h] [rbp-20h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e7f4676a90f13cc1e51a487b56d48ac7_Traceguids);
  }
  v1 = *((_QWORD *)ApxTelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v1 > 4u
    && (*(_QWORD *)(v1 + 16) & 0x400000000001LL) != 0
    && (*(_QWORD *)(v1 + 24) & 0x400000000001LL) == *(_QWORD *)(v1 + 24) )
  {
    LODWORD(v3) = GetCurrentProcessId();
    v9 = 4;
    v8 = &v3;
    v7 = 8;
    v6 = &v4;
    ((void (__fastcall *)(__int64, void *, _QWORD, _QWORD, int, _BYTE *, __int64, __int64))tlgWriteTransfer_EventWriteTransfer)(
      v1,
      &unk_18002E0D0,
      0,
      0,
      4,
      v5,
      v3,
      2048);
  }
  g_ApfFrameworkInitialized = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e7f4676a90f13cc1e51a487b56d48ac7_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180009be0  mov     [rsp+arg_0], rbx
0x180009be5  push    rdi
0x180009be6  sub     rsp, 90h
0x180009bed  mov     rax, cs:__security_cookie
0x180009bf4  xor     rax, rsp
0x180009bf7  mov     [rsp+98h+var_18], rax
0x180009bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c06  lea     rdi, WPP_GLOBAL_Control
0x180009c0d  cmp     rcx, rdi
0x180009c10  jz      short loc_180009C33
0x180009c12  test    byte ptr [rcx+1Ch], 1
0x180009c16  jz      short loc_180009C33
0x180009c18  cmp     byte ptr [rcx+19h], 5
0x180009c1c  jb      short loc_180009C33
0x180009c1e  mov     rcx, [rcx+10h]
0x180009c22  lea     r8, WPP_e7f4676a90f13cc1e51a487b56d48ac7_Traceguids
0x180009c29  mov     edx, 0Ah
0x180009c2e  call    WPP_SF_
0x180009c33  call    ?Instance@ApxTelemetryProvider@@KAPEAV1@XZ; ApxTelemetryProvider::Instance(void)
0x180009c38  mov     rbx, [rax+8]
0x180009c3c  mov     eax, [rbx]
0x180009c3e  cmp     eax, 4
0x180009c41  jbe     loc_180009CC9
0x180009c47  mov     rcx, [rbx+18h]
0x180009c4b  mov     rdx, 400000000001h
0x180009c55  mov     rax, [rbx+10h]
0x180009c59  test    rdx, rax
0x180009c5c  jz      short loc_180009CC9
0x180009c5e  mov     rax, rcx
0x180009c61  and     rax, rdx
0x180009c64  cmp     rax, rcx
0x180009c67  jnz     short loc_180009CC9
0x180009c69  call    cs:__imp_GetCurrentProcessId
0x180009c6f  xor     r9d, r9d
0x180009c72  mov     [rsp+98h+var_60], 800h
0x180009c7b  mov     dword ptr [rsp+98h+var_68], eax
0x180009c7f  lea     rdx, unk_18002E0D0
0x180009c86  lea     rax, [rsp+98h+var_68]
0x180009c8b  mov     [rsp+98h+var_20], 4
0x180009c94  mov     [rsp+98h+var_28], rax
0x180009c99  xor     r8d, r8d
0x180009c9c  lea     rax, [rsp+98h+var_60]
0x180009ca1  mov     [rsp+98h+var_30], 8
0x180009caa  mov     [rsp+98h+var_38], rax
0x180009caf  mov     rcx, rbx
0x180009cb2  lea     rax, [rsp+98h+var_58]
0x180009cb7  mov     [rsp+98h+var_70], rax
0x180009cbc  mov     [rsp+98h+var_78], 4
0x180009cc4  call    _tlgWriteTransfer_EventWriteTransfer
0x180009cc9  mov     cs:?g_ApfFrameworkInitialized@@3_NA, 1; bool g_ApfFrameworkInitialized
0x180009cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cd7  cmp     rcx, rdi
0x180009cda  jz      short loc_180009CFD
0x180009cdc  test    byte ptr [rcx+1Ch], 1
0x180009ce0  jz      short loc_180009CFD
0x180009ce2  cmp     byte ptr [rcx+19h], 5
0x180009ce6  jb      short loc_180009CFD
0x180009ce8  mov     rcx, [rcx+10h]
0x180009cec  lea     r8, WPP_e7f4676a90f13cc1e51a487b56d48ac7_Traceguids
0x180009cf3  mov     edx, 0Bh
0x180009cf8  call    WPP_SF_
0x180009cfd  xor     eax, eax
0x180009cff  mov     rcx, [rsp+98h+var_18]
0x180009d07  xor     rcx, rsp; StackCookie
0x180009d0a  call    __security_check_cookie
0x180009d0f  mov     rbx, [rsp+98h+arg_0]
0x180009d17  add     rsp, 90h
0x180009d1e  pop     rdi
0x180009d1f  retn
```
