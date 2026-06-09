# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::IncomingLEOobPairing(void)

- ea: `0x18002e13c`
- end: `0x18002e2ab`
- name: `?IncomingLEOobPairing@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ`
- size: `367`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002ecb8`

## callees

- `0x1800024ac`
- `0x18001140c`
- `0x18002aec0`
- `0x18002c13c`
- `0x18002e13c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e1fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e1fc`
- `deviceassociation!DafCloseAssociationContext` at `0x18002e1f4`
- `deviceassociation!DafCloseAssociationContext` at `0x18002e1f4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::IncomingLEOobPairing(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *this,
        __int64 a2,
        __int64 a3)
{
  char v4; // di
  unsigned int v5; // ebx
  __int64 v6; // rbp
  DWORD LastError; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // edx
  int v11; // r8d
  int v12; // eax
  bool v13; // cf
  _QWORD v15[2]; // [rsp+60h] [rbp-38h] BYREF
  unsigned int v16; // [rsp+A0h] [rbp+8h] BYREF

  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((_QWORD *)WPP_GLOBAL_Control + 5));
  v15[0] = this;
  v15[1] = &v16;
  v5 = wil::ResultFromException__lambda_16d72a4e5775df5b079aaa4debecd85d___(v15, a2, a3);
  v16 = v5;
  v6 = *((_QWORD *)this + 255);
  if ( v6 )
  {
    LastError = GetLastError();
    DafCloseAssociationContext(v6, v8, v9);
    SetLastError(LastError);
    v5 = v16;
  }
  *((_QWORD *)this + 255) = 0;
  memset_0((char *)this + 152, 0, 0x760u);
  v12 = 0;
  if ( v5 )
    v13 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v13 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (LOBYTE(v12) = !v13, !v12) )
    v4 = 0;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = v4;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, *((_QWORD *)WPP_GLOBAL_Control + 5));
    return v16;
  }
  return v5;
}

```

## disassembly

```asm
0x18002e13c  mov     [rsp+arg_8], rbx
0x18002e141  mov     [rsp+arg_10], rbp
0x18002e146  push    rsi
0x18002e147  push    rdi
0x18002e148  push    r12
0x18002e14a  push    r14
0x18002e14c  push    r15
0x18002e14e  sub     rsp, 70h
0x18002e152  mov     rsi, rcx
0x18002e155  lea     r14, WPP_GLOBAL_Control
0x18002e15c  mov     dil, 1
0x18002e15f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e166  cmp     rcx, r14
0x18002e169  jz      short loc_18002E176
0x18002e16b  cmp     byte ptr [rcx+19h], 5
0x18002e16f  jb      short loc_18002E176
0x18002e171  mov     dl, dil
0x18002e174  jmp     short loc_18002E178
0x18002e176  xor     dl, dl
0x18002e178  lea     r15, WPP_RECORDER_INITIALIZED
0x18002e17f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002e186  setnz   r8b
0x18002e18a  lea     r12, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e191  test    dl, dl
0x18002e193  jnz     short loc_18002E19A
0x18002e195  test    r8b, r8b
0x18002e198  jz      short loc_18002E1B8
0x18002e19a  mov     [rsp+98h+var_50], rsi
0x18002e19f  mov     [rsp+98h+var_60], r12
0x18002e1a4  mov     [rsp+98h+var_68], 2Fh ; '/'
0x18002e1ab  mov     r9, [rcx+28h]
0x18002e1af  mov     rcx, [rcx+10h]
0x18002e1b3  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002e1b8  mov     [rsp+98h+var_38], rsi
0x18002e1bd  lea     rax, [rsp+98h+arg_0]
0x18002e1c5  mov     [rsp+98h+var_30], rax
0x18002e1ca  lea     rcx, [rsp+98h+var_38]
0x18002e1cf  call    wil__ResultFromException__lambda_16d72a4e5775df5b079aaa4debecd85d___
0x18002e1d4  mov     ebx, eax
0x18002e1d6  mov     [rsp+98h+arg_0], eax
0x18002e1dd  mov     rbp, [rsi+7F8h]
0x18002e1e4  test    rbp, rbp
0x18002e1e7  jz      short loc_18002E20A
0x18002e1e9  call    cs:__imp_GetLastError
0x18002e1ef  mov     ebx, eax
0x18002e1f1  mov     rcx, rbp
0x18002e1f4  call    cs:__imp_DafCloseAssociationContext
0x18002e1fa  mov     ecx, ebx; dwErrCode
0x18002e1fc  call    cs:__imp_SetLastError
0x18002e202  nop
0x18002e203  mov     ebx, [rsp+98h+arg_0]
0x18002e20a  mov     qword ptr [rsi+7F8h], 0
0x18002e215  lea     rcx, [rsi+98h]; void *
0x18002e21c  xor     edx, edx; Val
0x18002e21e  mov     r8d, 760h; Size
0x18002e224  call    memset_0
0x18002e229  xor     eax, eax
0x18002e22b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e232  test    ebx, ebx
0x18002e234  jnz     short loc_18002E23C
0x18002e236  cmp     byte ptr [rcx+19h], 5
0x18002e23a  jmp     short loc_18002E240
0x18002e23c  cmp     byte ptr [rcx+19h], 2
0x18002e240  setnb   al
0x18002e243  cmp     rcx, r14
0x18002e246  jz      short loc_18002E24C
0x18002e248  test    eax, eax
0x18002e24a  jnz     short loc_18002E24F
0x18002e24c  xor     dil, dil
0x18002e24f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002e256  setnz   r8b
0x18002e25a  test    dil, dil
0x18002e25d  jnz     short loc_18002E264
0x18002e25f  test    r8b, r8b
0x18002e262  jz      short loc_18002E290
0x18002e264  mov     [rsp+98h+var_48], ebx
0x18002e268  mov     [rsp+98h+var_50], rsi
0x18002e26d  mov     [rsp+98h+var_60], r12
0x18002e272  mov     [rsp+98h+var_68], 32h ; '2'
0x18002e279  mov     r9, [rcx+28h]
0x18002e27d  mov     dl, dil
0x18002e280  mov     rcx, [rcx+10h]
0x18002e284  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002e289  mov     ebx, [rsp+98h+arg_0]
0x18002e290  mov     eax, ebx
0x18002e292  lea     r11, [rsp+98h+var_28]
0x18002e297  mov     rbx, [r11+38h]
0x18002e29b  mov     rbp, [r11+40h]
0x18002e29f  mov     rsp, r11
0x18002e2a2  pop     r15
0x18002e2a4  pop     r14
0x18002e2a6  pop     r12
0x18002e2a8  pop     rdi
0x18002e2a9  pop     rsi
0x18002e2aa  retn
```
