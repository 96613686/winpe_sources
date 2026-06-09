# HttpCreateUrlGroup

- ea: `0x180003bc0`
- end: `0x180003cf4`
- name: `HttpCreateUrlGroup`
- size: `308`
- prototype: `ULONG __stdcall(HTTP_SERVER_SESSION_ID ServerSessionId, PHTTP_URL_GROUP_ID pUrlGroupId, ULONG Reserved)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002b40`
- `0x180003bc0`
- `0x18000a5f0`
- `0x18000b080`
- `0x18000b0b8`

## pseudocode

```c
ULONG __stdcall HttpCreateUrlGroup(
        HTTP_SERVER_SESSION_ID ServerSessionId,
        PHTTP_URL_GROUP_ID pUrlGroupId,
        ULONG Reserved)
{
  __int64 v6; // rcx
  ULONG v7; // edi
  __int64 v8; // r9
  __m256i InputBuffer; // [rsp+40h] [rbp-58h] BYREF
  _OWORD v11[2]; // [rsp+60h] [rbp-38h] BYREF

  memset(&InputBuffer, 0, 28);
  memset(v11, 0, 28);
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_I(ServerSessionId, 13, WPP_55e47224c694357c3f55ac6b1be9ef3f_Traceguids, ServerSessionId);
  if ( pUrlGroupId && !Reserved )
  {
    InputBuffer.m256i_i64[1] = ServerSessionId;
    InputBuffer.m256i_i64[0] = 0;
    *(_OWORD *)&InputBuffer.m256i_u64[2] = 0;
    v7 = HttpApiSynchronousDeviceControl(g_CommunicationChannel, 0x128010u, &InputBuffer, 0x20u, v11, 0x20u, 0);
    if ( !v7 )
    {
      v8 = *(_QWORD *)&v11[1];
      *pUrlGroupId = *(_QWORD *)&v11[1];
      if ( (byte_1800126A3 & 4) == 0 )
        return v7;
      WPP_SF_I(v6, 14, WPP_55e47224c694357c3f55ac6b1be9ef3f_Traceguids, v8);
    }
    if ( (byte_1800126A3 & 4) != 0 )
      WPP_SF_d(1050, 15, WPP_55e47224c694357c3f55ac6b1be9ef3f_Traceguids, v7);
    return v7;
  }
  return 87;
}

```

## disassembly

```asm
0x180003bc0  mov     [rsp+arg_10], rbx
0x180003bc5  mov     [rsp+arg_18], rsi
0x180003bca  push    rdi
0x180003bcb  sub     rsp, 90h
0x180003bd2  mov     rax, cs:__security_cookie
0x180003bd9  xor     rax, rsp
0x180003bdc  mov     [rsp+98h+var_18], rax
0x180003be4  xorps   xmm0, xmm0
0x180003be7  mov     esi, r8d
0x180003bea  movups  [rsp+98h+InputBuffer], xmm0
0x180003bef  mov     rbx, rdx
0x180003bf2  mov     rdi, rcx
0x180003bf5  movups  [rsp+98h+var_38], xmm0
0x180003bfa  xor     eax, eax
0x180003bfc  movups  [rsp+98h+InputBuffer+0Ch], xmm0
0x180003c01  movups  [rsp+98h+var_38+0Ch], xmm0
0x180003c06  test    cs:byte_1800126A3, 4
0x180003c0d  jz      short loc_180003C23
0x180003c0f  mov     edx, 0Dh
0x180003c14  lea     r8, WPP_55e47224c694357c3f55ac6b1be9ef3f_Traceguids
0x180003c1b  mov     r9, rcx
0x180003c1e  call    WPP_SF_I
0x180003c23  test    rbx, rbx
0x180003c26  jz      loc_180003CCA
0x180003c2c  test    esi, esi
0x180003c2e  jnz     loc_180003CCA
0x180003c34  mov     rcx, cs:g_CommunicationChannel; FileHandle
0x180003c3b  lea     r8, [rsp+98h+InputBuffer]; InputBuffer
0x180003c40  xor     eax, eax
0x180003c42  mov     qword ptr [rsp+98h+InputBuffer+8], rdi
0x180003c47  mov     [rsp+98h+var_68], rax; __int64
0x180003c4c  xorps   xmm0, xmm0
0x180003c4f  mov     qword ptr [rsp+98h+InputBuffer], rax
0x180003c54  mov     r9d, 20h ; ' '; InputBufferLength
0x180003c5a  lea     rax, [rsp+98h+var_38]
0x180003c5f  mov     [rsp+98h+var_70], 20h ; ' '; ULONG
0x180003c67  mov     edx, 128010h; IoControlCode
0x180003c6c  mov     [rsp+98h+var_78], rax; PVOID
0x180003c71  movdqu  [rsp+98h+var_48], xmm0
0x180003c77  call    HttpApiSynchronousDeviceControl
0x180003c7c  mov     edi, eax
0x180003c7e  test    eax, eax
0x180003c80  jnz     short loc_180003CA4
0x180003c82  mov     r9, [rsp+98h+var_28]
0x180003c87  mov     [rbx], r9
0x180003c8a  test    cs:byte_1800126A3, 4
0x180003c91  jz      short loc_180003CC6
0x180003c93  mov     edx, 0Eh
0x180003c98  lea     r8, WPP_55e47224c694357c3f55ac6b1be9ef3f_Traceguids
0x180003c9f  call    WPP_SF_I
0x180003ca4  test    cs:byte_1800126A3, 4
0x180003cab  jz      short loc_180003CC6
0x180003cad  mov     edx, 0Fh
0x180003cb2  lea     r8, WPP_55e47224c694357c3f55ac6b1be9ef3f_Traceguids
0x180003cb9  mov     ecx, 41Ah
0x180003cbe  mov     r9d, edi
0x180003cc1  call    WPP_SF_d
0x180003cc6  mov     eax, edi
0x180003cc8  jmp     short loc_180003CCF
0x180003cca  mov     eax, 57h ; 'W'
0x180003ccf  mov     rcx, [rsp+98h+var_18]
0x180003cd7  xor     rcx, rsp; StackCookie
0x180003cda  call    __security_check_cookie
0x180003cdf  lea     r11, [rsp+98h+var_8]
0x180003ce7  mov     rbx, [r11+20h]
0x180003ceb  mov     rsi, [r11+28h]
0x180003cef  mov     rsp, r11
0x180003cf2  pop     rdi
0x180003cf3  retn
```
