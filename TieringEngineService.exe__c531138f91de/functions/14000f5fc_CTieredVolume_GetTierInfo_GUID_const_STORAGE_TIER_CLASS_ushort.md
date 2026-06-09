# CTieredVolume::GetTierInfo(_GUID const *,_STORAGE_TIER_CLASS *,ushort *)

- ea: `0x14000f5fc`
- end: `0x14000f721`
- name: `?GetTierInfo@CTieredVolume@@QEAAJPEBU_GUID@@PEAW4_STORAGE_TIER_CLASS@@PEAG@Z`
- size: `293`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, const struct _GUID *, enum _STORAGE_TIER_CLASS *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003aa90`
- `0x14003b070`
- `0x14003cde0`
- `0x14003e49c`

## callees

- `0x14000f5fc`
- `0x140018378`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14000f653`
- `ntdll!RtlCompareMemory` at `0x14000f695`
- `ntdll!RtlCompareMemory` at `0x14000f6b6`
- `ntdll!RtlCompareMemory` at `0x14000f653`
- `ntdll!RtlCompareMemory` at `0x14000f695`
- `ntdll!RtlCompareMemory` at `0x14000f6b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000f67d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000f67d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000f62a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000f62a`

## pseudocode

```c
__int64 __fastcall CTieredVolume::GetTierInfo(
        RTL_SRWLOCK *this,
        const struct _GUID *a2,
        enum _STORAGE_TIER_CLASS *a3,
        unsigned __int16 *a4)
{
  char v4; // si
  RTL_SRWLOCK *v8; // rbx
  _QWORD *Ptr; // rax
  enum _STORAGE_TIER_CLASS *v10; // r14
  _QWORD *v11; // r15

  v4 = 0;
  if ( a3 )
    *a3 = StorageTierClassUnspecified;
  v8 = this + 3;
  AcquireSRWLockShared(this + 3);
  Ptr = this[4].Ptr;
  if ( Ptr )
  {
    while ( 1 )
    {
      v10 = (enum _STORAGE_TIER_CLASS *)Ptr[2];
      v11 = (_QWORD *)*Ptr;
      if ( RtlCompareMemory(v10 + 129, a2, 0x10u) == 16 )
        break;
      Ptr = v11;
      if ( !v11 )
        goto LABEL_10;
    }
    if ( a3 )
      *a3 = *v10;
    v4 = 1;
  }
LABEL_10:
  if ( v8 )
    ReleaseSRWLockShared(v8);
  if ( v4 )
    return 0;
  if ( RtlCompareMemory(&g_DiskTierTestGuid, a2, 0x10u) == 16 )
  {
    *a3 = StorageTierClassCapacity;
    v4 = 1;
  }
  if ( RtlCompareMemory(&g_FlashTierTestGuid, a2, 0x10u) == 16 )
  {
    *a3 = StorageTierClassPerformance;
    return 0;
  }
  if ( v4 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF__guid_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      244,
      &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
      a2,
      -2138898429);
  }
  return 2156068867LL;
}

```

## disassembly

```asm
0x14000f5fc  push    rbx
0x14000f5fe  push    rbp
0x14000f5ff  push    rsi
0x14000f600  push    rdi
0x14000f601  push    r12
0x14000f603  push    r14
0x14000f605  push    r15
0x14000f607  sub     rsp, 30h
0x14000f60b  xor     sil, sil
0x14000f60e  mov     rdi, r8
0x14000f611  mov     rbp, rdx
0x14000f614  mov     r14, rcx
0x14000f617  test    r8, r8
0x14000f61a  jz      short loc_14000F623
0x14000f61c  mov     dword ptr [r8], 0
0x14000f623  lea     rbx, [rcx+18h]
0x14000f627  mov     rcx, rbx; SRWLock
0x14000f62a  call    cs:__imp_AcquireSRWLockShared
0x14000f630  mov     rax, [r14+20h]
0x14000f634  mov     r12d, 10h
0x14000f63a  test    rax, rax
0x14000f63d  jz      short loc_14000F675
0x14000f63f  mov     r14, [rax+10h]
0x14000f643  mov     r8, r12; Length
0x14000f646  mov     r15, [rax]
0x14000f649  mov     rdx, rbp; Source2
0x14000f64c  lea     rcx, [r14+204h]; Source1
0x14000f653  call    cs:__imp_RtlCompareMemory
0x14000f659  cmp     rax, r12
0x14000f65c  jz      short loc_14000F668
0x14000f65e  mov     rax, r15
0x14000f661  test    r15, r15
0x14000f664  jnz     short loc_14000F63F
0x14000f666  jmp     short loc_14000F675
0x14000f668  test    rdi, rdi
0x14000f66b  jz      short loc_14000F672
0x14000f66d  mov     eax, [r14]
0x14000f670  mov     [rdi], eax
0x14000f672  mov     sil, 1
0x14000f675  test    rbx, rbx
0x14000f678  jz      short loc_14000F683
0x14000f67a  mov     rcx, rbx; SRWLock
0x14000f67d  call    cs:__imp_ReleaseSRWLockShared
0x14000f683  test    sil, sil
0x14000f686  jnz     short loc_14000F6C7
0x14000f688  mov     r8, r12; Length
0x14000f68b  lea     rcx, ?g_DiskTierTestGuid@@3U_GUID@@A; Source1
0x14000f692  mov     rdx, rbp; Source2
0x14000f695  call    cs:__imp_RtlCompareMemory
0x14000f69b  cmp     rax, r12
0x14000f69e  jnz     short loc_14000F6A9
0x14000f6a0  mov     dword ptr [rdi], 1
0x14000f6a6  mov     sil, 1
0x14000f6a9  mov     r8, r12; Length
0x14000f6ac  lea     rcx, ?g_FlashTierTestGuid@@3U_GUID@@A; Source1
0x14000f6b3  mov     rdx, rbp; Source2
0x14000f6b6  call    cs:__imp_RtlCompareMemory
0x14000f6bc  cmp     rax, r12
0x14000f6bf  jnz     short loc_14000F6D8
0x14000f6c1  mov     dword ptr [rdi], 2
0x14000f6c7  xor     eax, eax
0x14000f6c9  add     rsp, 30h
0x14000f6cd  pop     r15
0x14000f6cf  pop     r14
0x14000f6d1  pop     r12
0x14000f6d3  pop     rdi
0x14000f6d4  pop     rsi
0x14000f6d5  pop     rbp
0x14000f6d6  pop     rbx
0x14000f6d7  retn
0x14000f6d8  test    sil, sil
0x14000f6db  jnz     short loc_14000F6C7
0x14000f6dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f6e4  lea     rax, WPP_GLOBAL_Control
0x14000f6eb  mov     ebx, 80830003h
0x14000f6f0  cmp     rcx, rax
0x14000f6f3  jz      short loc_14000F71D
0x14000f6f5  test    byte ptr [rcx+1Ch], 1
0x14000f6f9  jz      short loc_14000F71D
0x14000f6fb  cmp     byte ptr [rcx+19h], 2
0x14000f6ff  jb      short loc_14000F71D
0x14000f701  mov     rcx, [rcx+10h]
0x14000f705  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000f70c  mov     edx, 0F4h
0x14000f711  mov     [rsp+68h+var_48], ebx
0x14000f715  mov     r9, rbp
0x14000f718  call    WPP_SF__guid_d
0x14000f71d  mov     eax, ebx
0x14000f71f  jmp     short loc_14000F6C9
```
