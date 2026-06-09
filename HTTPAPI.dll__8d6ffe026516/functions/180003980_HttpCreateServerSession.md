# HttpCreateServerSession

- ea: `0x180003980`
- end: `0x180003a8d`
- name: `HttpCreateServerSession`
- size: `269`
- prototype: `ULONG __stdcall(HTTPAPI_VERSION Version, PHTTP_SERVER_SESSION_ID ServerSessionId, ULONG Reserved)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002b40`
- `0x180003980`
- `0x18000a5f0`
- `0x18000b3d4`
- `0x18000b584`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
ULONG __stdcall HttpCreateServerSession(
        HTTPAPI_VERSION Version,
        PHTTP_SERVER_SESSION_ID ServerSessionId,
        ULONG Reserved)
{
  int HttpApiMinorVersion; // eax
  __int64 v5; // rcx
  ULONG v8; // ebx
  __int128 InputBuffer; // [rsp+40h] [rbp-48h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h]
  __int128 v12; // [rsp+58h] [rbp-30h] BYREF
  __int64 v13; // [rsp+68h] [rbp-20h]

  HttpApiMinorVersion = Version.HttpApiMinorVersion;
  v5 = 0;
  v11 = 0;
  v13 = 0;
  InputBuffer = 0;
  v12 = 0;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_llqL(
      1050,
      ServerSessionId,
      WPP_37f3e1f220f83c46a55611d8da7dd839_Traceguids,
      Version.HttpApiMajorVersion,
      HttpApiMinorVersion,
      ServerSessionId,
      Reserved);
  if ( !ServerSessionId || Reserved )
  {
    v8 = 87;
  }
  else
  {
    LODWORD(InputBuffer) = Version;
    *ServerSessionId = 0;
    v8 = HttpApiSynchronousDeviceControl(g_CommunicationChannel, 0x128000u, &InputBuffer, 0x18u, &v12, 0x18u, 0);
    if ( !v8 )
      *ServerSessionId = *((_QWORD *)&v12 + 1);
  }
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_DI(v5, ServerSessionId, *(_QWORD *)&Reserved, v8, *ServerSessionId);
  return v8;
}

```

## disassembly

```asm
0x180003980  mov     [rsp+arg_10], rbx
0x180003985  mov     [rsp+arg_18], rsi
0x18000398a  push    rdi
0x18000398b  sub     rsp, 80h
0x180003992  mov     rax, cs:__security_cookie
0x180003999  xor     rax, rsp
0x18000399c  mov     [rsp+88h+var_18], rax
0x1800039a1  mov     eax, ecx
0x1800039a3  mov     ebx, ecx
0x1800039a5  shr     eax, 10h
0x1800039a8  xorps   xmm0, xmm0
0x1800039ab  xor     ecx, ecx
0x1800039ad  xorps   xmm1, xmm1
0x1800039b0  mov     [rsp+88h+var_38], rcx
0x1800039b5  mov     esi, r8d
0x1800039b8  mov     [rsp+88h+var_20], rcx
0x1800039bd  mov     rdi, rdx
0x1800039c0  movups  [rsp+88h+InputBuffer], xmm0
0x1800039c5  movups  [rsp+88h+var_30], xmm1
0x1800039ca  test    cs:byte_1800126A3, 4
0x1800039d1  jz      short loc_1800039F6
0x1800039d3  mov     dword ptr [rsp+88h+var_58], r8d
0x1800039d8  mov     ecx, 41Ah
0x1800039dd  mov     qword ptr [rsp+88h+var_60], rdx
0x1800039e2  lea     r8, WPP_37f3e1f220f83c46a55611d8da7dd839_Traceguids
0x1800039e9  movzx   r9d, bx
0x1800039ed  mov     dword ptr [rsp+88h+var_68], eax
0x1800039f1  call    WPP_SF_llqL
0x1800039f6  test    rdi, rdi
0x1800039f9  jz      short loc_180003A4B
0x1800039fb  test    esi, esi
0x1800039fd  jnz     short loc_180003A4B
0x1800039ff  xor     eax, eax
0x180003a01  mov     dword ptr [rsp+88h+InputBuffer], ebx
0x180003a05  mov     [rsp+88h+var_58], rax; __int64
0x180003a0a  lea     r8, [rsp+88h+InputBuffer]; InputBuffer
0x180003a0f  mov     [rdi], rax
0x180003a12  mov     r9d, 18h; InputBufferLength
0x180003a18  mov     rcx, cs:g_CommunicationChannel; FileHandle
0x180003a1f  lea     rax, [rsp+88h+var_30]
0x180003a24  mov     [rsp+88h+var_60], 18h; ULONG
0x180003a2c  mov     edx, 128000h; IoControlCode
0x180003a31  mov     [rsp+88h+var_68], rax; PVOID
0x180003a36  call    HttpApiSynchronousDeviceControl
0x180003a3b  mov     ebx, eax
0x180003a3d  test    eax, eax
0x180003a3f  jnz     short loc_180003A50
0x180003a41  mov     rax, qword ptr [rsp+88h+var_30+8]
0x180003a46  mov     [rdi], rax
0x180003a49  jmp     short loc_180003A50
0x180003a4b  mov     ebx, 57h ; 'W'
0x180003a50  test    cs:byte_1800126A3, 4
0x180003a57  jz      short loc_180003A69
0x180003a59  mov     rax, [rdi]
0x180003a5c  mov     r9d, ebx
0x180003a5f  mov     [rsp+88h+var_68], rax
0x180003a64  call    WPP_SF_DI
0x180003a69  mov     eax, ebx
0x180003a6b  mov     rcx, [rsp+88h+var_18]
0x180003a70  xor     rcx, rsp; StackCookie
0x180003a73  call    __security_check_cookie
0x180003a78  lea     r11, [rsp+88h+var_8]
0x180003a80  mov     rbx, [r11+20h]
0x180003a84  mov     rsi, [r11+28h]
0x180003a88  mov     rsp, r11
0x180003a8b  pop     rdi
0x180003a8c  retn
```
