# CAdapter::UpdateRrHistory(void)

- ea: `0x1400a4124`
- end: `0x1400a42c1`
- name: `?UpdateRrHistory@CAdapter@@QEAAXXZ`
- size: `413`
- prototype: `void __fastcall(CAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1400a29d0`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x14007a86c`
- `0x1400a4124`
- `0x1400a42c8`
- `0x1400a7c70`
- `0x1400da4f0`
- `0x1400dac80`

## import_xrefs

- `NDIS!NdisCloseConfiguration` at `0x1400a4294`
- `NDIS!NdisCloseConfiguration` at `0x1400a4294`

## pseudocode

```c
void __fastcall CAdapter::UpdateRrHistory(CAdapter *this)
{
  unsigned __int64 v1; // rsi
  unsigned int v2; // ebx
  __int64 v3; // rdi
  __int64 v4; // rax
  int v5; // ebx
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // edx
  int v9; // [rsp+28h] [rbp-71h]
  unsigned int v10; // [rsp+30h] [rbp-69h] BYREF
  void *m_MiniportAdapterHandle; // [rsp+38h] [rbp-61h] BYREF
  NDIS_HANDLE ConfigurationHandle; // [rsp+40h] [rbp-59h]
  unsigned __int8 v13[8]; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int8 v14[40]; // [rsp+78h] [rbp-21h] BYREF

  m_MiniportAdapterHandle = this->m_MiniportAdapterHandle;
  ConfigurationHandle = 0;
  v1 = MEMORY[0xFFFFF78000000014];
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      201,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  v10 = 40;
  if ( CRegistryHelper::ReadAdapterRegistryBinaries(
         (CRegistryHelper *)&m_MiniportAdapterHandle,
         L"ResetRecoveryHistory",
         &v10,
         v13)
    || !v10
    || (v10 & 7) != 0 )
  {
    v3 = 0;
    goto LABEL_14;
  }
  v2 = v10 >> 3;
  v3 = 0;
  if ( v10 >> 3 > 5 )
  {
LABEL_14:
    v2 = 0;
    goto LABEL_15;
  }
  if ( v2 )
  {
    do
    {
      if ( *(_QWORD *)&v13[8 * (unsigned int)v3] + get_reset_recovery_period() > v1 )
        break;
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < v2 );
  }
LABEL_15:
  v4 = v2;
  v5 = v2 - v3;
  *(_QWORD *)&v13[8 * v4] = v1;
  if ( (unsigned int)(v5 + 1) <= 5 )
    ++v5;
  else
    v3 = 1;
  v6 = 8 * v5;
  memmove(v14, &v13[8 * v3], v6);
  v7 = CRegistryHelper::WriteAdapterRegistryBinaries(
         (CRegistryHelper *)&m_MiniportAdapterHandle,
         L"ResetRecoveryHistory",
         v6,
         v14);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    v9 = v7;
    LOBYTE(v8) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      1,
      202,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      v9);
  }
  if ( ConfigurationHandle )
    NdisCloseConfiguration(ConfigurationHandle);
}

```

## disassembly

```asm
0x1400a4124  push    rbp
0x1400a4126  push    rbx
0x1400a4127  push    rsi
0x1400a4128  push    rdi
0x1400a4129  push    r12
0x1400a412b  push    r13
0x1400a412d  push    r14
0x1400a412f  push    r15
0x1400a4131  lea     rbp, [rsp-1Fh]
0x1400a4136  sub     rsp, 0B8h
0x1400a413d  mov     rax, cs:__security_cookie
0x1400a4144  xor     rax, rsp
0x1400a4147  mov     [rbp+57h+var_50], rax
0x1400a414b  mov     rax, [rcx+58h]
0x1400a414f  mov     rsi, 0FFFFF78000000014h
0x1400a4159  xor     r14d, r14d
0x1400a415c  mov     [rbp+57h+var_B8], rax
0x1400a4160  mov     [rbp+57h+ConfigurationHandle], r14
0x1400a4164  mov     rsi, [rsi]
0x1400a4167  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a416e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a4175  lea     r12, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400a417c  lea     r15d, [r14+1]
0x1400a4180  jz      short loc_1400A41AF
0x1400a4182  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a4189  cmp     byte ptr [rcx+29h], 5
0x1400a418d  jnb     short loc_1400A4196
0x1400a418f  cmp     [rcx+48h], r14w
0x1400a4194  jz      short loc_1400A41AF
0x1400a4196  mov     rcx, [rcx+40h]
0x1400a419a  mov     r9d, 0C9h
0x1400a41a0  mov     r8d, r15d
0x1400a41a3  mov     [rsp+0F0h+var_D0], r12
0x1400a41a8  mov     dl, 5
0x1400a41aa  call    WPP_RECORDER_SF_
0x1400a41af  lea     r9, [rbp+57h+var_A8]; unsigned __int8 *
0x1400a41b3  mov     [rbp+57h+var_C0], 28h ; '('
0x1400a41ba  lea     r8, [rbp+57h+var_C0]; unsigned int *
0x1400a41be  lea     rdx, aResetrecoveryh; "ResetRecoveryHistory"
0x1400a41c5  lea     rcx, [rbp+57h+var_B8]; this
0x1400a41c9  call    ?ReadAdapterRegistryBinaries@CRegistryHelper@@QEAAHPEBGPEAKPEAE@Z; CRegistryHelper::ReadAdapterRegistryBinaries(ushort const *,ulong *,uchar *)
0x1400a41ce  test    eax, eax
0x1400a41d0  jnz     short loc_1400A4207
0x1400a41d2  mov     ebx, [rbp+57h+var_C0]
0x1400a41d5  test    ebx, ebx
0x1400a41d7  jz      short loc_1400A4207
0x1400a41d9  test    bl, 7
0x1400a41dc  jnz     short loc_1400A4207
0x1400a41de  shr     ebx, 3
0x1400a41e1  mov     edi, r14d
0x1400a41e4  cmp     ebx, 5
0x1400a41e7  ja      short loc_1400A420A
0x1400a41e9  test    ebx, ebx
0x1400a41eb  jz      short loc_1400A420D
0x1400a41ed  call    ?get_reset_recovery_period@@YA_KXZ; get_reset_recovery_period(void)
0x1400a41f2  mov     ecx, edi
0x1400a41f4  add     rax, qword ptr [rbp+rcx*8+57h+var_A8]
0x1400a41f9  cmp     rax, rsi
0x1400a41fc  ja      short loc_1400A420D
0x1400a41fe  add     edi, r15d
0x1400a4201  cmp     edi, ebx
0x1400a4203  jb      short loc_1400A41ED
0x1400a4205  jmp     short loc_1400A420D
0x1400a4207  mov     edi, r14d
0x1400a420a  mov     ebx, r14d
0x1400a420d  mov     eax, ebx
0x1400a420f  lea     rdx, [rbp+57h+var_A8]
0x1400a4213  sub     ebx, edi
0x1400a4215  lea     rcx, [rbp+57h+var_78]; void *
0x1400a4219  mov     qword ptr [rbp+rax*8+57h+var_A8], rsi
0x1400a421e  lea     eax, [rbx+1]
0x1400a4221  cmp     eax, 5
0x1400a4224  cmova   edi, r15d
0x1400a4228  cmovbe  ebx, eax
0x1400a422b  shl     ebx, 3
0x1400a422e  mov     r8d, ebx; Size
0x1400a4231  lea     rdx, [rdx+rdi*8]; Src
0x1400a4235  call    memmove
0x1400a423a  lea     r9, [rbp+57h+var_78]; unsigned __int8 *
0x1400a423e  mov     r8d, ebx; unsigned int
0x1400a4241  lea     rdx, aResetrecoveryh; "ResetRecoveryHistory"
0x1400a4248  lea     rcx, [rbp+57h+var_B8]; this
0x1400a424c  call    ?WriteAdapterRegistryBinaries@CRegistryHelper@@QEAAHPEBGKPEAE@Z; CRegistryHelper::WriteAdapterRegistryBinaries(ushort const *,ulong,uchar *)
0x1400a4251  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400a4258  jz      short loc_1400A428B
0x1400a425a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a4261  cmp     byte ptr [rcx+29h], 5
0x1400a4265  jnb     short loc_1400A426E
0x1400a4267  cmp     [rcx+48h], r14w
0x1400a426c  jz      short loc_1400A428B
0x1400a426e  mov     rcx, [rcx+40h]
0x1400a4272  mov     r9d, 0CAh
0x1400a4278  mov     [rsp+0F0h+var_C8], eax
0x1400a427c  mov     r8d, r15d
0x1400a427f  mov     dl, 5
0x1400a4281  mov     [rsp+0F0h+var_D0], r12
0x1400a4286  call    WPP_RECORDER_SF_D
0x1400a428b  mov     rcx, [rbp+57h+ConfigurationHandle]; ConfigurationHandle
0x1400a428f  test    rcx, rcx
0x1400a4292  jz      short loc_1400A42A0
0x1400a4294  call    cs:__imp_NdisCloseConfiguration
0x1400a429b  nop     dword ptr [rax+rax+00h]
0x1400a42a0  mov     rcx, [rbp+57h+var_50]
0x1400a42a4  xor     rcx, rsp; StackCookie
0x1400a42a7  call    __security_check_cookie
0x1400a42ac  add     rsp, 0B8h
0x1400a42b3  pop     r15
0x1400a42b5  pop     r14
0x1400a42b7  pop     r13
0x1400a42b9  pop     r12
0x1400a42bb  pop     rdi
0x1400a42bc  pop     rsi
0x1400a42bd  pop     rbx
0x1400a42be  pop     rbp
0x1400a42bf  retn
```
