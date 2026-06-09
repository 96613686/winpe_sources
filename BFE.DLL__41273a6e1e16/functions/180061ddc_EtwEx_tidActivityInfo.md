# EtwEx_tidActivityInfo

- ea: `0x180061ddc`
- end: `0x180061ed9`
- name: `EtwEx_tidActivityInfo`
- size: `253`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f840`
- `0x1800467d0`

## callees

- `0x18005aa60`
- `0x180061ddc`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180061e86`
- `ntdll!EtwEventWrite` at `0x180061e86`
- `ntdll!EtwEventActivityIdControl` at `0x180061e35`
- `ntdll!EtwEventActivityIdControl` at `0x180061eae`
- `ntdll!EtwEventActivityIdControl` at `0x180061e35`
- `ntdll!EtwEventActivityIdControl` at `0x180061eae`

## pseudocode

```c
__int64 __fastcall EtwEx_tidActivityInfo(__int64 a1, _WORD *a2, __int128 *a3)
{
  __int64 v3; // rdi
  __int128 *v5; // r9
  __int64 v6; // r8
  unsigned int v7; // edi
  int v9; // [rsp+20h] [rbp-30h] BYREF
  __int128 v10; // [rsp+28h] [rbp-28h] BYREF
  int *v11; // [rsp+38h] [rbp-18h]
  __int64 v12; // [rsp+40h] [rbp-10h]

  v3 = Microsoft_Windows_Networking_CorrelationHandle;
  v9 = 0;
  if ( *a2 == 0xEA61 )
  {
    v10 = 0;
    if ( a3 )
      v10 = *a3;
    EtwEventActivityIdControl(2, &v10);
  }
  if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
  {
    *((_QWORD *)&v10 + 1) = 16;
    *(_QWORD *)&v10 = &Microsoft_Windows_Networking_ProviderId;
    v5 = &v10;
    v12 = 4;
    v11 = &v9;
    v6 = 2;
  }
  else
  {
    v5 = 0;
    v6 = 0;
  }
  v7 = EtwEventWrite(v3, a2, v6, v5);
  if ( *a2 == 0xEA62 )
  {
    v10 = 0;
    EtwEventActivityIdControl(2, &v10);
  }
  return v7;
}

```

## disassembly

```asm
0x180061ddc  mov     [rsp-8+arg_0], rbx
0x180061de1  mov     [rsp-8+arg_18], rdi
0x180061de6  push    rbp
0x180061de7  mov     rbp, rsp
0x180061dea  sub     rsp, 50h
0x180061dee  mov     rax, cs:__security_cookie
0x180061df5  xor     rax, rsp
0x180061df8  mov     [rbp+var_8], rax
0x180061dfc  mov     rdi, cs:Microsoft_Windows_Networking_CorrelationHandle
0x180061e03  mov     eax, 0EA61h
0x180061e08  mov     rbx, rdx
0x180061e0b  mov     [rbp+var_30], 0
0x180061e12  cmp     [rdx], ax
0x180061e15  jnz     short loc_180061E41
0x180061e17  xorps   xmm0, xmm0
0x180061e1a  movups  [rbp+var_28], xmm0
0x180061e1e  test    r8, r8
0x180061e21  jz      short loc_180061E2C
0x180061e23  movups  xmm0, xmmword ptr [r8]
0x180061e27  movdqu  [rbp+var_28], xmm0
0x180061e2c  lea     rdx, [rbp+var_28]
0x180061e30  mov     ecx, 2
0x180061e35  call    cs:__imp_EtwEventActivityIdControl
0x180061e3c  nop     dword ptr [rax+rax+00h]
0x180061e41  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x180061e47  mov     rdx, rbx
0x180061e4a  mov     rcx, rdi
0x180061e4d  test    eax, eax
0x180061e4f  jz      short loc_180061E80
0x180061e51  lea     rax, Microsoft_Windows_Networking_ProviderId
0x180061e58  mov     qword ptr [rbp+var_28+8], 10h
0x180061e60  mov     qword ptr [rbp+var_28], rax
0x180061e64  lea     r9, [rbp+var_28]
0x180061e68  lea     rax, [rbp+var_30]
0x180061e6c  mov     [rbp+var_10], 4
0x180061e74  mov     [rbp+var_18], rax
0x180061e78  mov     r8d, 2
0x180061e7e  jmp     short loc_180061E86
0x180061e80  xor     r9d, r9d
0x180061e83  xor     r8d, r8d
0x180061e86  call    cs:__imp_EtwEventWrite
0x180061e8d  nop     dword ptr [rax+rax+00h]
0x180061e92  mov     edi, eax
0x180061e94  mov     eax, 0EA62h
0x180061e99  cmp     [rbx], ax
0x180061e9c  jnz     short loc_180061EBA
0x180061e9e  xorps   xmm0, xmm0
0x180061ea1  lea     rdx, [rbp+var_28]
0x180061ea5  mov     ecx, 2
0x180061eaa  movups  [rbp+var_28], xmm0
0x180061eae  call    cs:__imp_EtwEventActivityIdControl
0x180061eb5  nop     dword ptr [rax+rax+00h]
0x180061eba  mov     eax, edi
0x180061ebc  mov     rcx, [rbp+var_8]
0x180061ec0  xor     rcx, rsp; StackCookie
0x180061ec3  call    __security_check_cookie
0x180061ec8  mov     rbx, [rsp+50h+arg_0]
0x180061ecd  mov     rdi, [rsp+50h+arg_18]
0x180061ed2  add     rsp, 50h
0x180061ed6  pop     rbp
0x180061ed7  retn
```
