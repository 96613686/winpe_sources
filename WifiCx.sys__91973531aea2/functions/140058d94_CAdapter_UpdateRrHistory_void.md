# CAdapter::UpdateRrHistory(void)

- ea: `0x140058d94`
- end: `0x140058f3a`
- name: `?UpdateRrHistory@CAdapter@@QEAAXXZ`
- size: `422`
- prototype: `void __fastcall(CAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140055d18`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x14002ed50`
- `0x140058d94`
- `0x140059278`
- `0x14006ea14`
- `0x14006ecec`
- `0x1400dfd00`
- `0x1400dfd40`
- `0x1400dfe00`

## pseudocode

```c
void __fastcall CAdapter::UpdateRrHistory(CAdapter *this)
{
  int v1; // edx
  unsigned __int64 CurrentTime; // rsi
  unsigned int v3; // ebx
  __int64 v4; // rdi
  __int64 v5; // rax
  int v6; // ebx
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // edx
  unsigned int v10; // [rsp+30h] [rbp-69h] BYREF
  __int64 v11; // [rsp+38h] [rbp-61h] BYREF
  __int64 v12; // [rsp+40h] [rbp-59h]
  unsigned __int8 v13[8]; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int8 v14[40]; // [rsp+78h] [rbp-21h] BYREF

  v11 = *((_QWORD *)this + 10);
  v12 = 0;
  CurrentTime = CSystem::get_CurrentTime();
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v1) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v1,
      1,
      84,
      (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids);
  }
  v10 = 40;
  if ( CRegistryHelper::ReadAdapterRegistryBinaries((CRegistryHelper *)&v11, L"ResetRecoveryHistory", &v10, v13)
    || !v10
    || (v10 & 7) != 0 )
  {
    v4 = 0;
    goto LABEL_14;
  }
  v3 = v10 >> 3;
  v4 = 0;
  if ( v10 >> 3 > 5 )
  {
LABEL_14:
    v3 = 0;
    goto LABEL_15;
  }
  if ( v3 )
  {
    do
    {
      if ( *(_QWORD *)&v13[8 * (unsigned int)v4] + get_reset_recovery_period() > CurrentTime )
        break;
      v4 = (unsigned int)(v4 + 1);
    }
    while ( (unsigned int)v4 < v3 );
  }
LABEL_15:
  v5 = v3;
  v6 = v3 - v4;
  *(_QWORD *)&v13[8 * v5] = CurrentTime;
  if ( (unsigned int)(v6 + 1) <= 5 )
    ++v6;
  else
    v4 = 1;
  v7 = 8 * v6;
  memmove(v14, &v13[8 * v4], v7);
  v8 = CRegistryHelper::WriteAdapterRegistryBinaries((CRegistryHelper *)&v11, L"ResetRecoveryHistory", v7, v14);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      1,
      85,
      (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
      v8);
  }
  if ( v12 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01031 + 1848))(WdfDriverGlobals);
}

```

## disassembly

```asm
0x140058d94  push    rbp
0x140058d96  push    rbx
0x140058d97  push    rsi
0x140058d98  push    rdi
0x140058d99  push    r12
0x140058d9b  push    r13
0x140058d9d  push    r14
0x140058d9f  push    r15
0x140058da1  lea     rbp, [rsp-1Fh]
0x140058da6  sub     rsp, 0B8h
0x140058dad  mov     rax, cs:__security_cookie
0x140058db4  xor     rax, rsp
0x140058db7  mov     [rbp+57h+var_50], rax
0x140058dbb  mov     rax, [rcx+50h]
0x140058dbf  xor     r14d, r14d
0x140058dc2  mov     [rbp+57h+var_B8], rax
0x140058dc6  mov     [rbp+57h+var_B0], r14
0x140058dca  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x140058dcf  mov     rsi, rax
0x140058dd2  lea     r13, WPP_RECORDER_INITIALIZED
0x140058dd9  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140058de0  lea     r12, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x140058de7  lea     r15d, [r14+1]
0x140058deb  jz      short loc_140058E1A
0x140058ded  mov     rcx, cs:WPP_GLOBAL_Control
0x140058df4  cmp     byte ptr [rcx+29h], 5
0x140058df8  jnb     short loc_140058E01
0x140058dfa  cmp     [rcx+48h], r14w
0x140058dff  jz      short loc_140058E1A
0x140058e01  mov     rcx, [rcx+40h]
0x140058e05  mov     r9d, 54h ; 'T'
0x140058e0b  mov     r8d, r15d
0x140058e0e  mov     [rsp+0F0h+var_D0], r12
0x140058e13  mov     dl, 5
0x140058e15  call    WPP_RECORDER_SF_
0x140058e1a  lea     r9, [rbp+57h+var_A8]; unsigned __int8 *
0x140058e1e  mov     [rbp+57h+var_C0], 28h ; '('
0x140058e25  lea     r8, [rbp+57h+var_C0]; unsigned int *
0x140058e29  lea     rdx, aResetrecoveryh; "ResetRecoveryHistory"
0x140058e30  lea     rcx, [rbp+57h+var_B8]; this
0x140058e34  call    ?ReadAdapterRegistryBinaries@CRegistryHelper@@QEAAHPEBGPEAKPEAE@Z; CRegistryHelper::ReadAdapterRegistryBinaries(ushort const *,ulong *,uchar *)
0x140058e39  test    eax, eax
0x140058e3b  jnz     short loc_140058E72
0x140058e3d  mov     ebx, [rbp+57h+var_C0]
0x140058e40  test    ebx, ebx
0x140058e42  jz      short loc_140058E72
0x140058e44  test    bl, 7
0x140058e47  jnz     short loc_140058E72
0x140058e49  shr     ebx, 3
0x140058e4c  mov     edi, r14d
0x140058e4f  cmp     ebx, 5
0x140058e52  ja      short loc_140058E75
0x140058e54  test    ebx, ebx
0x140058e56  jz      short loc_140058E78
0x140058e58  call    ?get_reset_recovery_period@@YA_KXZ; get_reset_recovery_period(void)
0x140058e5d  mov     ecx, edi
0x140058e5f  add     rax, qword ptr [rbp+rcx*8+57h+var_A8]
0x140058e64  cmp     rax, rsi
0x140058e67  ja      short loc_140058E78
0x140058e69  add     edi, r15d
0x140058e6c  cmp     edi, ebx
0x140058e6e  jb      short loc_140058E58
0x140058e70  jmp     short loc_140058E78
0x140058e72  mov     edi, r14d
0x140058e75  mov     ebx, r14d
0x140058e78  mov     eax, ebx
0x140058e7a  lea     rdx, [rbp+57h+var_A8]
0x140058e7e  sub     ebx, edi
0x140058e80  lea     rcx, [rbp+57h+var_78]; void *
0x140058e84  mov     qword ptr [rbp+rax*8+57h+var_A8], rsi
0x140058e89  lea     eax, [rbx+1]
0x140058e8c  cmp     eax, 5
0x140058e8f  cmova   edi, r15d
0x140058e93  cmovbe  ebx, eax
0x140058e96  shl     ebx, 3
0x140058e99  mov     r8d, ebx; Size
0x140058e9c  lea     rdx, [rdx+rdi*8]; Src
0x140058ea0  call    memmove
0x140058ea5  lea     r9, [rbp+57h+var_78]; unsigned __int8 *
0x140058ea9  mov     r8d, ebx; unsigned int
0x140058eac  lea     rdx, aResetrecoveryh; "ResetRecoveryHistory"
0x140058eb3  lea     rcx, [rbp+57h+var_B8]; this
0x140058eb7  call    ?WriteAdapterRegistryBinaries@CRegistryHelper@@QEAAHPEBGKPEAE@Z; CRegistryHelper::WriteAdapterRegistryBinaries(ushort const *,ulong,uchar *)
0x140058ebc  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140058ec3  jz      short loc_140058EF6
0x140058ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x140058ecc  cmp     byte ptr [rcx+29h], 5
0x140058ed0  jnb     short loc_140058ED9
0x140058ed2  cmp     [rcx+48h], r14w
0x140058ed7  jz      short loc_140058EF6
0x140058ed9  mov     rcx, [rcx+40h]
0x140058edd  mov     r9d, 55h ; 'U'
0x140058ee3  mov     [rsp+0F0h+var_C8], eax
0x140058ee7  mov     r8d, r15d
0x140058eea  mov     dl, 5
0x140058eec  mov     [rsp+0F0h+var_D0], r12
0x140058ef1  call    WPP_RECORDER_SF_d
0x140058ef6  mov     rdx, [rbp+57h+var_B0]
0x140058efa  test    rdx, rdx
0x140058efd  jz      short loc_140058F19
0x140058eff  mov     rax, cs:WdfFunctions_01031
0x140058f06  mov     rcx, cs:WdfDriverGlobals
0x140058f0d  mov     rax, [rax+738h]
0x140058f14  call    _guard_dispatch_icall
0x140058f19  mov     rcx, [rbp+57h+var_50]
0x140058f1d  xor     rcx, rsp; StackCookie
0x140058f20  call    __security_check_cookie
0x140058f25  add     rsp, 0B8h
0x140058f2c  pop     r15
0x140058f2e  pop     r14
0x140058f30  pop     r13
0x140058f32  pop     r12
0x140058f34  pop     rdi
0x140058f35  pop     rsi
0x140058f36  pop     rbx
0x140058f37  pop     rbp
0x140058f38  retn
```
