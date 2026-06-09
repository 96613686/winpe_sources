# CPhotoPropertyStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x1800025e0`
- end: `0x1800027eb`
- name: `?GetValue@CPhotoPropertyStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `523`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800025e0`
- `0x180002eb0`
- `0x180002f30`
- `0x1800044e0`
- `0x18001186c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000267a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000278b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000267a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000278b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000260f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002642`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000260f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002642`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000271b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000271b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002632`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800026a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002632`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800026a3`

## pseudocode

```c
__int64 __fastcall CPhotoPropertyStore::GetValue(
        struct _RTL_CRITICAL_SECTION *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3)
{
  const struct _GUID *v6; // rcx
  unsigned __int64 v7; // r8
  HRESULT v8; // edi
  const struct _GUID *v9; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  unsigned __int64 v11; // r8

  if ( !a3 )
    return 2147500035LL;
  EnterCriticalSection(this + 2);
  v7 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v7 )
    ShellPrivateTraceEvent(v6, 6u, v7, 1u);
  PropVariantClear(a3);
  EnterCriticalSection(this + 2);
  if ( !LODWORD(this[4].DebugInfo) )
  {
    v8 = -2147418113;
LABEL_30:
    LeaveCriticalSection(this + 2);
    goto LABEL_12;
  }
  if ( HIDWORD(this[4].DebugInfo) )
  {
    v8 = -2147467259;
    goto LABEL_30;
  }
  v8 = 0;
  if ( !this[4].LockCount )
  {
    v8 = CMetadataContainer::ReadInMetadata((CMetadataContainer *)&this[4].LockSemaphore);
    if ( v8 >= 0 )
    {
      this[4].LockCount = 1;
      LeaveCriticalSection(this + 2);
LABEL_8:
      if ( LOBYTE(this[5].RecursionCount)
        && !BYTE1(this[5].RecursionCount)
        && (int)CContainerMasks::EnsureContainerMasksLoaded() >= 0 )
      {
        CMetadataContainer::_ReadMetadataFromImageFrame((struct _GUID *)&this[4].LockSemaphore);
        BYTE1(this[5].RecursionCount) = 1;
      }
      PropVariantClear(a3);
      DebugInfo = this[7].DebugInfo;
      if ( !DebugInfo )
        goto LABEL_11;
      do
      {
        if ( LODWORD(DebugInfo->ProcessLocksList.Flink) == a2->pid )
        {
          v9 = (const struct _GUID *)(*(_QWORD *)&DebugInfo->Type - *(_QWORD *)&a2->fmtid.Data1);
          if ( *(_QWORD *)&DebugInfo->Type == *(_QWORD *)&a2->fmtid.Data1 )
            v9 = (const struct _GUID *)((char *)DebugInfo->CriticalSection - *(_QWORD *)a2->fmtid.Data4);
          if ( !v9 )
            break;
        }
        DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)DebugInfo[1].CriticalSection;
      }
      while ( DebugInfo );
      if ( DebugInfo )
        v8 = PropVariantCopy(a3, (const PROPVARIANT *)&DebugInfo->ProcessLocksList.Blink);
      else
LABEL_11:
        v8 = 0;
      goto LABEL_12;
    }
  }
  LeaveCriticalSection(this + 2);
  if ( v8 >= 0 )
    goto LABEL_8;
LABEL_12:
  v11 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v11 )
    ShellPrivateTraceEvent(v9, 6u, v11, 2u);
  LeaveCriticalSection(this + 2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800025e0  mov     [rsp+arg_10], rbx
0x1800025e5  mov     [rsp+arg_18], rbp
0x1800025ea  push    rsi
0x1800025eb  sub     rsp, 20h
0x1800025ef  mov     rbp, r8
0x1800025f2  mov     rsi, rdx
0x1800025f5  mov     rbx, rcx
0x1800025f8  test    r8, r8
0x1800025fb  jz      loc_18000279C
0x180002601  mov     [rsp+28h+arg_0], rdi
0x180002606  add     rcx, 50h ; 'P'; lpCriticalSection
0x18000260a  mov     [rsp+28h+arg_8], r14
0x18000260f  call    cs:__imp_EnterCriticalSection
0x180002616  nop     dword ptr [rax+rax+00h]
0x18000261b  mov     rax, cs:WPP_GLOBAL_Control
0x180002622  mov     r8, [rax+38h]; unsigned __int64
0x180002626  test    r8, r8
0x180002629  jnz     loc_1800027A6
0x18000262f  mov     rcx, rbp; pvar
0x180002632  call    cs:__imp_PropVariantClear
0x180002639  nop     dword ptr [rax+rax+00h]
0x18000263e  lea     rcx, [rbx+50h]; lpCriticalSection
0x180002642  call    cs:__imp_EnterCriticalSection
0x180002649  nop     dword ptr [rax+rax+00h]
0x18000264e  cmp     dword ptr [rbx+0A0h], 0
0x180002655  jz      loc_1800027B8
0x18000265b  cmp     dword ptr [rbx+0A4h], 0
0x180002662  jnz     loc_1800027BF
0x180002668  xor     edi, edi
0x18000266a  cmp     [rbx+0A8h], edi
0x180002670  jz      loc_180002767
0x180002676  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000267a  call    cs:__imp_LeaveCriticalSection
0x180002681  nop     dword ptr [rax+rax+00h]
0x180002686  test    edi, edi
0x180002688  js      short loc_1800026BD
0x18000268a  cmp     byte ptr [rbx+0D4h], 0
0x180002691  jz      short loc_1800026A0
0x180002693  cmp     byte ptr [rbx+0D5h], 0
0x18000269a  jz      loc_180002742
0x1800026a0  mov     rcx, rbp; pvar
0x1800026a3  call    cs:__imp_PropVariantClear
0x1800026aa  nop     dword ptr [rax+rax+00h]
0x1800026af  mov     rdx, [rbx+118h]
0x1800026b6  test    rdx, rdx
0x1800026b9  jnz     short loc_1800026FE
0x1800026bb  xor     edi, edi
0x1800026bd  mov     r8, cs:WPP_GLOBAL_Control
0x1800026c4  mov     r8, [r8+38h]; unsigned __int64
0x1800026c8  test    r8, r8
0x1800026cb  jnz     loc_1800027D9
0x1800026d1  lea     rcx, [rbx+50h]; lpCriticalSection
0x1800026d5  call    cs:__imp_LeaveCriticalSection
0x1800026dc  nop     dword ptr [rax+rax+00h]
0x1800026e1  mov     r14, [rsp+28h+arg_8]
0x1800026e6  mov     eax, edi
0x1800026e8  mov     rdi, [rsp+28h+arg_0]
0x1800026ed  mov     rbx, [rsp+28h+arg_10]
0x1800026f2  mov     rbp, [rsp+28h+arg_18]
0x1800026f7  add     rsp, 20h
0x1800026fb  pop     rsi
0x1800026fc  retn
0x1800026fe  mov     eax, [rsi+10h]
0x180002701  cmp     [rdx+10h], eax
0x180002704  jz      short loc_18000272B
0x180002706  mov     rdx, [rdx+38h]
0x18000270a  test    rdx, rdx
0x18000270d  jnz     short loc_180002701
0x18000270f  test    rdx, rdx
0x180002712  jz      short loc_1800026BB
0x180002714  add     rdx, 18h; pvarSrc
0x180002718  mov     rcx, rbp; pvarDest
0x18000271b  call    cs:__imp_PropVariantCopy
0x180002722  nop     dword ptr [rax+rax+00h]
0x180002727  mov     edi, eax
0x180002729  jmp     short loc_1800026BD
0x18000272b  mov     rcx, [rdx]
0x18000272e  sub     rcx, [rsi]
0x180002731  jnz     short loc_18000273B
0x180002733  mov     rcx, [rdx+8]
0x180002737  sub     rcx, [rsi+8]
0x18000273b  test    rcx, rcx
0x18000273e  jnz     short loc_180002706
0x180002740  jmp     short loc_18000270F
0x180002742  call    ?EnsureContainerMasksLoaded@CContainerMasks@@SAJXZ; CContainerMasks::EnsureContainerMasksLoaded(void)
0x180002747  test    eax, eax
0x180002749  js      loc_1800026A0
0x18000274f  lea     rcx, [rbx+0B8h]; this
0x180002756  call    ?_ReadMetadataFromImageFrame@CMetadataContainer@@AEAAJI@Z; CMetadataContainer::_ReadMetadataFromImageFrame(uint)
0x18000275b  mov     byte ptr [rbx+0D5h], 1
0x180002762  jmp     loc_1800026A0
0x180002767  lea     rcx, [rbx+0B8h]; this
0x18000276e  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x180002773  mov     edi, eax
0x180002775  test    eax, eax
0x180002777  js      loc_180002676
0x18000277d  lea     rcx, [rbx+50h]; lpCriticalSection
0x180002781  mov     dword ptr [rbx+0A8h], 1
0x18000278b  call    cs:__imp_LeaveCriticalSection
0x180002792  nop     dword ptr [rax+rax+00h]
0x180002797  jmp     loc_18000268A
0x18000279c  mov     eax, 80004003h
0x1800027a1  jmp     loc_1800026ED
0x1800027a6  mov     r9b, 1; unsigned __int8
0x1800027a9  mov     edx, 6; unsigned int
0x1800027ae  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x1800027b3  jmp     loc_18000262F
0x1800027b8  mov     edi, 8000FFFFh
0x1800027bd  jmp     short loc_1800027C4
0x1800027bf  mov     edi, 80004005h
0x1800027c4  lea     rcx, [rbx+50h]; lpCriticalSection
0x1800027c8  call    cs:__imp_LeaveCriticalSection
0x1800027cf  nop     dword ptr [rax+rax+00h]
0x1800027d4  jmp     loc_1800026BD
0x1800027d9  mov     r9b, 2; unsigned __int8
0x1800027dc  mov     edx, 6; unsigned int
0x1800027e1  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x1800027e6  jmp     loc_1800026D1
```
