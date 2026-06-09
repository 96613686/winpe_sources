# Apx::ApfDeinitialize(void)

- ea: `0x180009a9c`
- end: `0x180009bda`
- name: `?ApfDeinitialize@Apx@@YAXXZ`
- size: `318`
- prototype: `void __fastcall(Apx *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18002576c`

## callees

- `0x18000163c`
- `0x180001d30`
- `0x180009a9c`
- `0x180009d28`
- `0x18000a12c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009b25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009b25`

## pseudocode

```c
void __fastcall Apx::ApfDeinitialize(Apx *this)
{
  __int64 v1; // rbx
  __int64 v2; // [rsp+30h] [rbp-68h] BYREF
  __int64 v3; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v4[32]; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v5; // [rsp+60h] [rbp-38h]
  __int64 v6; // [rsp+68h] [rbp-30h]
  __int64 *v7; // [rsp+70h] [rbp-28h]
  __int64 v8; // [rsp+78h] [rbp-20h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e7f4676a90f13cc1e51a487b56d48ac7_Traceguids);
  }
  v1 = *((_QWORD *)ApxTelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v1 > 4u
    && (*(_QWORD *)(v1 + 16) & 0x400000000001LL) != 0
    && (*(_QWORD *)(v1 + 24) & 0x400000000001LL) == *(_QWORD *)(v1 + 24) )
  {
    LODWORD(v2) = GetCurrentProcessId();
    v8 = 4;
    v7 = &v2;
    v6 = 8;
    v5 = &v3;
    ((void (__fastcall *)(__int64, char *, _QWORD, _QWORD, int, _BYTE *, __int64, __int64))tlgWriteTransfer_EventWriteTransfer)(
      v1,
      byte_18002E091,
      0,
      0,
      4,
      v4,
      v2,
      2048);
  }
  g_ApfFrameworkInitialized = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e7f4676a90f13cc1e51a487b56d48ac7_Traceguids);
  }
}

```

## disassembly

```asm
0x180009a9c  mov     [rsp+arg_0], rbx
0x180009aa1  push    rdi
0x180009aa2  sub     rsp, 90h
0x180009aa9  mov     rax, cs:__security_cookie
0x180009ab0  xor     rax, rsp
0x180009ab3  mov     [rsp+98h+var_18], rax
0x180009abb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ac2  lea     rdi, WPP_GLOBAL_Control
0x180009ac9  cmp     rcx, rdi
0x180009acc  jz      short loc_180009AEF
0x180009ace  test    byte ptr [rcx+1Ch], 1
0x180009ad2  jz      short loc_180009AEF
0x180009ad4  cmp     byte ptr [rcx+19h], 5
0x180009ad8  jb      short loc_180009AEF
0x180009ada  mov     rcx, [rcx+10h]
0x180009ade  lea     r8, WPP_e7f4676a90f13cc1e51a487b56d48ac7_Traceguids
0x180009ae5  mov     edx, 0Ch
0x180009aea  call    WPP_SF_
0x180009aef  call    ?Instance@ApxTelemetryProvider@@KAPEAV1@XZ; ApxTelemetryProvider::Instance(void)
0x180009af4  mov     rbx, [rax+8]
0x180009af8  mov     eax, [rbx]
0x180009afa  cmp     eax, 4
0x180009afd  jbe     loc_180009B85
0x180009b03  mov     rcx, [rbx+18h]
0x180009b07  mov     rdx, 400000000001h
0x180009b11  mov     rax, [rbx+10h]
0x180009b15  test    rdx, rax
0x180009b18  jz      short loc_180009B85
0x180009b1a  mov     rax, rcx
0x180009b1d  and     rax, rdx
0x180009b20  cmp     rax, rcx
0x180009b23  jnz     short loc_180009B85
0x180009b25  call    cs:__imp_GetCurrentProcessId
0x180009b2b  xor     r9d, r9d
0x180009b2e  mov     [rsp+98h+var_60], 800h
0x180009b37  mov     dword ptr [rsp+98h+var_68], eax
0x180009b3b  lea     rdx, byte_18002E091
0x180009b42  lea     rax, [rsp+98h+var_68]
0x180009b47  mov     [rsp+98h+var_20], 4
0x180009b50  mov     [rsp+98h+var_28], rax
0x180009b55  xor     r8d, r8d
0x180009b58  lea     rax, [rsp+98h+var_60]
0x180009b5d  mov     [rsp+98h+var_30], 8
0x180009b66  mov     [rsp+98h+var_38], rax
0x180009b6b  mov     rcx, rbx
0x180009b6e  lea     rax, [rsp+98h+var_58]
0x180009b73  mov     [rsp+98h+var_70], rax
0x180009b78  mov     [rsp+98h+var_78], 4
0x180009b80  call    _tlgWriteTransfer_EventWriteTransfer
0x180009b85  mov     cs:?g_ApfFrameworkInitialized@@3_NA, 0; bool g_ApfFrameworkInitialized
0x180009b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b93  cmp     rcx, rdi
0x180009b96  jz      short loc_180009BB9
0x180009b98  test    byte ptr [rcx+1Ch], 1
0x180009b9c  jz      short loc_180009BB9
0x180009b9e  cmp     byte ptr [rcx+19h], 5
0x180009ba2  jb      short loc_180009BB9
0x180009ba4  mov     rcx, [rcx+10h]
0x180009ba8  lea     r8, WPP_e7f4676a90f13cc1e51a487b56d48ac7_Traceguids
0x180009baf  mov     edx, 0Dh
0x180009bb4  call    WPP_SF_
0x180009bb9  mov     rcx, [rsp+98h+var_18]
0x180009bc1  xor     rcx, rsp; StackCookie
0x180009bc4  call    __security_check_cookie
0x180009bc9  mov     rbx, [rsp+98h+arg_0]
0x180009bd1  add     rsp, 90h
0x180009bd8  pop     rdi
0x180009bd9  retn
```
