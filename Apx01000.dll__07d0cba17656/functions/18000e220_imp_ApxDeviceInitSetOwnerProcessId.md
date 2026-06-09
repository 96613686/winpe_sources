# imp_ApxDeviceInitSetOwnerProcessId

- ea: `0x18000e220`
- end: `0x18000e2ff`
- name: `imp_ApxDeviceInitSetOwnerProcessId`
- size: `223`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x18000a12c`
- `0x18000a1b4`
- `0x18000a8e8`
- `0x18000a948`
- `0x18000e220`

## pseudocode

```c
__int64 __fastcall imp_ApxDeviceInitSetOwnerProcessId(
        Apx::ApfVerify *this,
        Apx::ApfVerify *a2,
        const unsigned __int16 *a3)
{
  int v3; // edi
  __int64 result; // rax
  const unsigned __int16 *v7; // r8
  _QWORD *v8; // rcx

  v3 = (int)a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_8cbab79fda8a3463012735886db38dbe_Traceguids);
  }
  result = Apx::ApfVerify::IsNull(this, L"Globals", a3);
  if ( (int)result < 0 )
    goto LABEL_13;
  result = Apx::ApfVerify::IsNotNull(a2, L"DeviceInit", v7);
  if ( (int)result < 0 )
    goto LABEL_13;
  if ( v3 )
  {
    *(_DWORD *)(75LL - (_QWORD)a2) = v3;
    goto LABEL_13;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    result = WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_8cbab79fda8a3463012735886db38dbe_Traceguids);
LABEL_13:
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    return WPP_SF_(v8[2], 16, WPP_8cbab79fda8a3463012735886db38dbe_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18000e220  push    rbx
0x18000e222  push    rbp
0x18000e223  push    rsi
0x18000e224  push    rdi
0x18000e225  sub     rsp, 28h
0x18000e229  mov     edi, r8d
0x18000e22c  mov     rbx, rdx
0x18000e22f  mov     rsi, rcx
0x18000e232  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e239  lea     rbp, WPP_GLOBAL_Control
0x18000e240  cmp     rcx, rbp
0x18000e243  jz      short loc_18000E266
0x18000e245  test    byte ptr [rcx+1Ch], 1
0x18000e249  jz      short loc_18000E266
0x18000e24b  cmp     byte ptr [rcx+19h], 5
0x18000e24f  jb      short loc_18000E266
0x18000e251  mov     rcx, [rcx+10h]
0x18000e255  lea     r8, WPP_8cbab79fda8a3463012735886db38dbe_Traceguids
0x18000e25c  mov     edx, 0Eh
0x18000e261  call    WPP_SF_
0x18000e266  lea     rdx, aGlobals; "Globals"
0x18000e26d  mov     rcx, rsi; this
0x18000e270  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18000e275  test    eax, eax
0x18000e277  js      short loc_18000E2C9
0x18000e279  lea     rdx, aDeviceinit; "DeviceInit"
0x18000e280  mov     rcx, rbx; this
0x18000e283  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18000e288  test    eax, eax
0x18000e28a  js      short loc_18000E2C9
0x18000e28c  test    edi, edi
0x18000e28e  jnz     short loc_18000E2C3
0x18000e290  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e297  cmp     rcx, rbp
0x18000e29a  jz      short loc_18000E2F6
0x18000e29c  test    byte ptr [rcx+1Ch], 40h
0x18000e2a0  jz      short loc_18000E2D0
0x18000e2a2  cmp     byte ptr [rcx+19h], 2
0x18000e2a6  jb      short loc_18000E2D0
0x18000e2a8  mov     rcx, [rcx+10h]
0x18000e2ac  lea     edx, [rdi+0Fh]
0x18000e2af  mov     r9d, 80070057h
0x18000e2b5  lea     r8, WPP_8cbab79fda8a3463012735886db38dbe_Traceguids
0x18000e2bc  call    WPP_SF_d
0x18000e2c1  jmp     short loc_18000E2C9
0x18000e2c3  not     rbx
0x18000e2c6  mov     [rbx+4Ch], edi
0x18000e2c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2d0  cmp     rcx, rbp
0x18000e2d3  jz      short loc_18000E2F6
0x18000e2d5  test    byte ptr [rcx+1Ch], 1
0x18000e2d9  jz      short loc_18000E2F6
0x18000e2db  cmp     byte ptr [rcx+19h], 5
0x18000e2df  jb      short loc_18000E2F6
0x18000e2e1  mov     rcx, [rcx+10h]
0x18000e2e5  lea     r8, WPP_8cbab79fda8a3463012735886db38dbe_Traceguids
0x18000e2ec  mov     edx, 10h
0x18000e2f1  call    WPP_SF_
0x18000e2f6  add     rsp, 28h
0x18000e2fa  pop     rdi
0x18000e2fb  pop     rsi
0x18000e2fc  pop     rbp
0x18000e2fd  pop     rbx
0x18000e2fe  retn
```
