# CPort::IncorporateBSSEntryList(ArrayOfElements<_WDI_BSS_ENTRY_CONTAINER> *,ulong *,DOT11_NWF_BSSID_CANDIDATE *)

- ea: `0x140025d50`
- end: `0x140026000`
- name: `?IncorporateBSSEntryList@CPort@@AEAAHPEAU?$ArrayOfElements@U_WDI_BSS_ENTRY_CONTAINER@@@@PEAKPEAUDOT11_NWF_BSSID_CANDIDATE@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(CPort *this)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140003110`
- `0x140084a9c`

## callees

- `0x140004d48`
- `0x14000c778`
- `0x14000d054`
- `0x14000d750`
- `0x140017130`
- `0x140017a90`
- `0x140025d50`
- `0x14004bab0`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140025ee9`
- `ntoskrnl!RtlCompareMemory` at `0x140025ee9`

## pseudocode

```c
__int64 __fastcall CPort::IncorporateBSSEntryList(CPort *this, __int64 a2, unsigned int *a3, __int64 a4)
{
  unsigned int v4; // r13d
  bool v5; // zf
  __int64 v6; // rdi
  unsigned int *v7; // rbp
  CBSSListManager *v8; // rdi
  unsigned int v9; // r12d
  unsigned int v10; // esi
  __int64 v11; // rbx
  CPort *v12; // r14
  wificx::utils *v13; // rcx
  unsigned __int64 SystemTime; // rax
  __int64 v15; // rcx
  CPropertyCache *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r15
  struct CBSSEntry *v19; // rbp
  struct DOT11_CONNECTION_INFO *CurrentConnectionInfo; // rax
  struct DOT11_CONNECTION_INFO *v21; // rdi
  __int64 v22; // rbx
  char *v23; // rcx
  unsigned __int8 v25[4]; // [rsp+30h] [rbp-68h] BYREF
  unsigned int v26; // [rsp+34h] [rbp-64h]
  struct CBSSEntry *v27; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int64 v28; // [rsp+40h] [rbp-58h]
  CBSSListManager *v29; // [rsp+48h] [rbp-50h]
  __int64 v31; // [rsp+A8h] [rbp+10h]

  v31 = a2;
  v4 = 0;
  v5 = (*((_DWORD *)this + 38) & 0x11) == 0;
  v27 = 0;
  v6 = 1336;
  if ( v5 )
    v6 = 1736;
  v7 = a3;
  v8 = (CBSSListManager *)(*((_QWORD *)this + 17) + v6);
  v9 = 0;
  v10 = 0;
  v29 = v8;
  v26 = 0;
  v11 = a2;
  v25[0] = 0;
  v12 = this;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      259,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
  }
  if ( v7 )
  {
    v10 = *v7;
    v26 = *v7;
  }
  if ( (unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline() )
    SystemTime = wificx::utils::QuerySystemTime(v13);
  else
    SystemTime = MEMORY[0xFFFFF78000000014];
  v15 = *((_QWORD *)v12 + 17) + 8LL;
  v28 = SystemTime;
  v16 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  CPropertyCache::GetPropertyBoolean(v16, 0x87u, v25);
  v18 = 0;
  if ( *(_DWORD *)v11 )
  {
    do
    {
      v4 = CBSSListManager::ReceiveBeaconOrProbe(v8, *(_QWORD *)(v11 + 8) + 144 * v18, v28, v25[0], &v27);
      if ( v4 )
        break;
      v19 = v27;
      if ( v27 )
      {
        CurrentConnectionInfo = CPort::GetCurrentConnectionInfo(v12, 1);
        v21 = CurrentConnectionInfo;
        if ( CurrentConnectionInfo && *((int *)v19 + 148) < 0 )
        {
          v22 = 0;
          if ( *((_DWORD *)CurrentConnectionInfo + 26) )
          {
            while ( RtlCompareMemory((char *)v21 + 48 * v22 + 123, (char *)v19 + 32, 6u) != 6 )
            {
              v22 = (unsigned int)(v22 + 1);
              if ( (unsigned int)v22 >= *((_DWORD *)v21 + 26) )
                goto LABEL_22;
            }
            *((_DWORD *)v21 + 12 * v22 + 37) = *((_DWORD *)v19 + 148);
LABEL_22:
            v12 = this;
            v10 = v26;
          }
          v11 = v31;
        }
        if ( v10 > v9 )
        {
          v23 = (char *)v19 + 32;
          v17 = 16LL * v9 + a4;
          *(_DWORD *)v17 = *((_DWORD *)v19 + 8);
          *(_WORD *)(v17 + 4) = *((_WORD *)v19 + 18);
          if ( *((_BYTE *)v19 + 44) )
            v23 = (char *)v19 + 38;
          ++v9;
          *(_DWORD *)(v17 + 6) = *(_DWORD *)v23;
          *(_WORD *)(v17 + 10) = *((_WORD *)v23 + 2);
          *(_DWORD *)(v17 + 12) = *((_DWORD *)v19 + 222);
        }
        v8 = v29;
      }
      v18 = (unsigned int)(v18 + 1);
      v27 = 0;
    }
    while ( (unsigned int)v18 < *(_DWORD *)v11 );
    v7 = a3;
  }
  if ( v7 )
    *v7 = v9;
  *((_DWORD *)v8 + 12) += *(_DWORD *)v11;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v17) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      1,
      260,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      v4);
  }
  return v4;
}

```

## disassembly

```asm
0x140025d50  mov     [rsp+arg_18], r9
0x140025d55  mov     [rsp+arg_10], r8
0x140025d5a  mov     [rsp+arg_8], rdx
0x140025d5f  mov     [rsp+arg_0], rcx
0x140025d64  push    rbx
0x140025d65  push    rbp
0x140025d66  push    rsi
0x140025d67  push    rdi
0x140025d68  push    r12
0x140025d6a  push    r13
0x140025d6c  push    r14
0x140025d6e  push    r15
0x140025d70  sub     rsp, 58h
0x140025d74  mov     eax, [rcx+98h]
0x140025d7a  xor     r13d, r13d
0x140025d7d  test    al, 11h
0x140025d7f  mov     [rsp+98h+var_60], r13
0x140025d84  mov     eax, 6C8h
0x140025d89  mov     edi, 538h
0x140025d8e  cmovz   edi, eax
0x140025d91  mov     rbp, r8
0x140025d94  add     rdi, [rcx+88h]
0x140025d9b  xor     r12d, r12d
0x140025d9e  xor     esi, esi
0x140025da0  mov     [rsp+98h+var_50], rdi
0x140025da5  mov     [rsp+98h+var_64], esi
0x140025da9  mov     rbx, rdx
0x140025dac  mov     [rsp+98h+var_68], sil
0x140025db1  mov     r14, rcx
0x140025db4  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025dbb  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025dc2  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140025dc9  jz      short loc_140025DFA
0x140025dcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140025dd2  cmp     byte ptr [rcx+29h], 5
0x140025dd6  jnb     short loc_140025DDE
0x140025dd8  cmp     [rcx+48h], si
0x140025ddc  jz      short loc_140025DFA
0x140025dde  mov     rcx, [rcx+40h]
0x140025de2  mov     r9d, 103h
0x140025de8  mov     r8d, 1
0x140025dee  mov     [rsp+98h+var_78], rax
0x140025df3  mov     dl, 5
0x140025df5  call    WPP_RECORDER_SF_
0x140025dfa  test    rbp, rbp
0x140025dfd  jz      short loc_140025E06
0x140025dff  mov     esi, [rbp+0]
0x140025e02  mov     [rsp+98h+var_64], esi
0x140025e06  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x140025e0b  test    eax, eax
0x140025e0d  jnz     short loc_140025E1E
0x140025e0f  mov     rax, 0FFFFF78000000014h
0x140025e19  mov     rax, [rax]
0x140025e1c  jmp     short loc_140025E23
0x140025e1e  call    ?QuerySystemTime@utils@wificx@@YA_KXZ; wificx::utils::QuerySystemTime(void)
0x140025e23  mov     rcx, [r14+88h]
0x140025e2a  add     rcx, 8
0x140025e2e  mov     [rsp+98h+var_58], rax
0x140025e33  mov     rdx, [rcx]
0x140025e36  mov     rax, [rdx+8]
0x140025e3a  call    _guard_dispatch_icall
0x140025e3f  lea     r8, [rsp+98h+var_68]; unsigned __int8 *
0x140025e44  mov     edx, 87h; unsigned int
0x140025e49  mov     rcx, rax; this
0x140025e4c  call    ?GetPropertyBoolean@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyBoolean(ulong,uchar *)
0x140025e51  xor     r15d, r15d
0x140025e54  cmp     [rbx], r12d
0x140025e57  jbe     loc_140025F91
0x140025e5d  nop     dword ptr [rax]
0x140025e60  movzx   r9d, [rsp+98h+var_68]; unsigned __int8
0x140025e66  lea     rax, [rsp+98h+var_60]
0x140025e6b  mov     r8, [rsp+98h+var_58]; unsigned __int64
0x140025e70  lea     rdx, [r15+r15*8]
0x140025e74  shl     rdx, 4
0x140025e78  mov     rcx, rdi; this
0x140025e7b  add     rdx, [rbx+8]; struct _WDI_BSS_ENTRY_CONTAINER *
0x140025e7f  mov     [rsp+98h+var_78], rax; struct CBSSEntry **
0x140025e84  call    ?ReceiveBeaconOrProbe@CBSSListManager@@QEAAHPEAU_WDI_BSS_ENTRY_CONTAINER@@_KEPEAPEAVCBSSEntry@@@Z; CBSSListManager::ReceiveBeaconOrProbe(_WDI_BSS_ENTRY_CONTAINER *,unsigned __int64,uchar,CBSSEntry * *)
0x140025e89  mov     r13d, eax
0x140025e8c  test    eax, eax
0x140025e8e  jnz     loc_140025F89
0x140025e94  mov     rbp, [rsp+98h+var_60]
0x140025e99  test    rbp, rbp
0x140025e9c  jz      loc_140025F74
0x140025ea2  mov     dl, 1; bool
0x140025ea4  mov     rcx, r14; this
0x140025ea7  call    ?GetCurrentConnectionInfo@CPort@@QEAAPEAUDOT11_CONNECTION_INFO@@_N@Z; CPort::GetCurrentConnectionInfo(bool)
0x140025eac  mov     rdi, rax
0x140025eaf  test    rax, rax
0x140025eb2  jz      short loc_140025F25
0x140025eb4  cmp     [rbp+250h], r13d
0x140025ebb  jge     short loc_140025F25
0x140025ebd  xor     ebx, ebx
0x140025ebf  cmp     [rax+68h], ebx
0x140025ec2  jbe     short loc_140025F1D
0x140025ec4  nop     dword ptr [rax+00h]
0x140025ec8  nop     dword ptr [rax+rax+00000000h]
0x140025ed0  lea     rsi, [rbx+rbx*2]
0x140025ed4  mov     r8d, 6; Length
0x140025eda  shl     rsi, 4
0x140025ede  lea     rdx, [rbp+20h]; Source2
0x140025ee2  lea     rcx, [rsi+7Bh]
0x140025ee6  add     rcx, rdi; Source1
0x140025ee9  call    cs:__imp_RtlCompareMemory
0x140025ef0  nop     dword ptr [rax+rax+00h]
0x140025ef5  cmp     rax, 6
0x140025ef9  jz      short loc_140025F04
0x140025efb  inc     ebx
0x140025efd  cmp     ebx, [rdi+68h]
0x140025f00  jb      short loc_140025ED0
0x140025f02  jmp     short loc_140025F11
0x140025f04  mov     eax, [rbp+250h]
0x140025f0a  mov     [rsi+rdi+94h], eax
0x140025f11  mov     r14, [rsp+98h+arg_0]
0x140025f19  mov     esi, [rsp+98h+var_64]
0x140025f1d  mov     rbx, [rsp+98h+arg_8]
0x140025f25  cmp     esi, r12d
0x140025f28  jbe     short loc_140025F6F
0x140025f2a  mov     rdx, [rsp+98h+arg_18]
0x140025f32  lea     rcx, [rbp+20h]
0x140025f36  mov     eax, r12d
0x140025f39  shl     rax, 4
0x140025f3d  add     rdx, rax
0x140025f40  mov     eax, [rcx]
0x140025f42  mov     [rdx], eax
0x140025f44  movzx   eax, word ptr [rcx+4]
0x140025f48  mov     [rdx+4], ax
0x140025f4c  cmp     byte ptr [rbp+2Ch], 0
0x140025f50  jz      short loc_140025F56
0x140025f52  lea     rcx, [rbp+26h]
0x140025f56  mov     eax, [rcx]
0x140025f58  inc     r12d
0x140025f5b  mov     [rdx+6], eax
0x140025f5e  movzx   eax, word ptr [rcx+4]
0x140025f62  mov     [rdx+0Ah], ax
0x140025f66  mov     eax, [rbp+378h]
0x140025f6c  mov     [rdx+0Ch], eax
0x140025f6f  mov     rdi, [rsp+98h+var_50]
0x140025f74  inc     r15d
0x140025f77  mov     [rsp+98h+var_60], 0
0x140025f80  cmp     r15d, [rbx]
0x140025f83  jb      loc_140025E60
0x140025f89  mov     rbp, [rsp+98h+arg_10]
0x140025f91  test    rbp, rbp
0x140025f94  jz      short loc_140025F9A
0x140025f96  mov     [rbp+0], r12d
0x140025f9a  mov     eax, [rbx]
0x140025f9c  add     [rdi+30h], eax
0x140025f9f  lea     rax, WPP_RECORDER_INITIALIZED
0x140025fa6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140025fad  jz      short loc_140025FEB
0x140025faf  mov     rcx, cs:WPP_GLOBAL_Control
0x140025fb6  cmp     byte ptr [rcx+29h], 5
0x140025fba  jnb     short loc_140025FC3
0x140025fbc  cmp     word ptr [rcx+48h], 0
0x140025fc1  jz      short loc_140025FEB
0x140025fc3  mov     rcx, [rcx+40h]
0x140025fc7  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140025fce  mov     r9d, 104h
0x140025fd4  mov     [rsp+98h+var_70], r13d
0x140025fd9  mov     r8d, 1
0x140025fdf  mov     [rsp+98h+var_78], rax
0x140025fe4  mov     dl, 5
0x140025fe6  call    WPP_RECORDER_SF_d
0x140025feb  mov     eax, r13d
0x140025fee  add     rsp, 58h
0x140025ff2  pop     r15
0x140025ff4  pop     r14
0x140025ff6  pop     r13
0x140025ff8  pop     r12
0x140025ffa  pop     rdi
0x140025ffb  pop     rsi
0x140025ffc  pop     rbp
0x140025ffd  pop     rbx
0x140025ffe  retn
```
