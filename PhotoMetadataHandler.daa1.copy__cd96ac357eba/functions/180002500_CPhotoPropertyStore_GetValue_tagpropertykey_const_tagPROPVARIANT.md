# CPhotoPropertyStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x180002500`
- end: `0x1800026e5`
- name: `?GetValue@CPhotoPropertyStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `485`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002500`
- `0x180002d50`
- `0x180002dc0`
- `0x180004490`
- `0x1800110b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002588`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002684`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002588`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002684`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000252f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002556`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000252f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002556`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000261a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000261a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000254c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800025ab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000254c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800025ab`

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
  if ( LODWORD(this[4].DebugInfo) )
  {
    if ( HIDWORD(this[4].DebugInfo) )
    {
      v8 = -2147467259;
      LeaveCriticalSection(this + 2);
    }
    else
    {
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
    }
  }
  else
  {
    v8 = -2147418113;
    LeaveCriticalSection(this + 2);
  }
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
0x180002500  mov     [rsp+arg_10], rbx
0x180002505  mov     [rsp+arg_18], rbp
0x18000250a  push    rsi
0x18000250b  sub     rsp, 20h
0x18000250f  mov     rbp, r8
0x180002512  mov     rsi, rdx
0x180002515  mov     rbx, rcx
0x180002518  test    r8, r8
0x18000251b  jz      loc_18000268F
0x180002521  mov     [rsp+28h+arg_0], rdi
0x180002526  add     rcx, 50h ; 'P'; lpCriticalSection
0x18000252a  mov     [rsp+28h+arg_8], r14
0x18000252f  call    cs:__imp_EnterCriticalSection
0x180002535  mov     rax, cs:WPP_GLOBAL_Control
0x18000253c  mov     r8, [rax+38h]; unsigned __int64
0x180002540  test    r8, r8
0x180002543  jnz     loc_180002699
0x180002549  mov     rcx, rbp; pvar
0x18000254c  call    cs:__imp_PropVariantClear
0x180002552  lea     rcx, [rbx+50h]; lpCriticalSection
0x180002556  call    cs:__imp_EnterCriticalSection
0x18000255c  cmp     dword ptr [rbx+0A0h], 0
0x180002563  jz      loc_1800026AB
0x180002569  cmp     dword ptr [rbx+0A4h], 0
0x180002570  jnz     loc_1800026BF
0x180002576  xor     edi, edi
0x180002578  cmp     [rbx+0A8h], edi
0x18000257e  jz      loc_180002660
0x180002584  lea     rcx, [rbx+50h]; lpCriticalSection
0x180002588  call    cs:__imp_LeaveCriticalSection
0x18000258e  test    edi, edi
0x180002590  js      short loc_1800025BF
0x180002592  cmp     byte ptr [rbx+0D4h], 0
0x180002599  jz      short loc_1800025A8
0x18000259b  cmp     byte ptr [rbx+0D5h], 0
0x1800025a2  jz      loc_18000263B
0x1800025a8  mov     rcx, rbp; pvar
0x1800025ab  call    cs:__imp_PropVariantClear
0x1800025b1  mov     rdx, [rbx+118h]
0x1800025b8  test    rdx, rdx
0x1800025bb  jnz     short loc_1800025F9
0x1800025bd  xor     edi, edi
0x1800025bf  mov     r8, cs:WPP_GLOBAL_Control
0x1800025c6  mov     r8, [r8+38h]; unsigned __int64
0x1800025ca  test    r8, r8
0x1800025cd  jnz     loc_1800026D3
0x1800025d3  lea     rcx, [rbx+50h]; lpCriticalSection
0x1800025d7  call    cs:__imp_LeaveCriticalSection
0x1800025dd  mov     r14, [rsp+28h+arg_8]
0x1800025e2  mov     eax, edi
0x1800025e4  mov     rdi, [rsp+28h+arg_0]
0x1800025e9  mov     rbx, [rsp+28h+arg_10]
0x1800025ee  mov     rbp, [rsp+28h+arg_18]
0x1800025f3  add     rsp, 20h
0x1800025f7  pop     rsi
0x1800025f8  retn
0x1800025f9  mov     eax, [rsi+10h]
0x1800025fc  nop     dword ptr [rax+00h]
0x180002600  cmp     [rdx+10h], eax
0x180002603  jz      short loc_180002624
0x180002605  mov     rdx, [rdx+38h]
0x180002609  test    rdx, rdx
0x18000260c  jnz     short loc_180002600
0x18000260e  test    rdx, rdx
0x180002611  jz      short loc_1800025BD
0x180002613  add     rdx, 18h; pvarSrc
0x180002617  mov     rcx, rbp; pvarDest
0x18000261a  call    cs:__imp_PropVariantCopy
0x180002620  mov     edi, eax
0x180002622  jmp     short loc_1800025BF
0x180002624  mov     rcx, [rdx]
0x180002627  sub     rcx, [rsi]
0x18000262a  jnz     short loc_180002634
0x18000262c  mov     rcx, [rdx+8]
0x180002630  sub     rcx, [rsi+8]
0x180002634  test    rcx, rcx
0x180002637  jnz     short loc_180002605
0x180002639  jmp     short loc_18000260E
0x18000263b  call    ?EnsureContainerMasksLoaded@CContainerMasks@@SAJXZ; CContainerMasks::EnsureContainerMasksLoaded(void)
0x180002640  test    eax, eax
0x180002642  js      loc_1800025A8
0x180002648  lea     rcx, [rbx+0B8h]; this
0x18000264f  call    ?_ReadMetadataFromImageFrame@CMetadataContainer@@AEAAJI@Z; CMetadataContainer::_ReadMetadataFromImageFrame(uint)
0x180002654  mov     byte ptr [rbx+0D5h], 1
0x18000265b  jmp     loc_1800025A8
0x180002660  lea     rcx, [rbx+0B8h]; this
0x180002667  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18000266c  mov     edi, eax
0x18000266e  test    eax, eax
0x180002670  js      loc_180002584
0x180002676  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000267a  mov     dword ptr [rbx+0A8h], 1
0x180002684  call    cs:__imp_LeaveCriticalSection
0x18000268a  jmp     loc_180002592
0x18000268f  mov     eax, 80004003h
0x180002694  jmp     loc_1800025E9
0x180002699  mov     r9b, 1; unsigned __int8
0x18000269c  mov     edx, 6; unsigned int
0x1800026a1  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x1800026a6  jmp     loc_180002549
0x1800026ab  lea     rcx, [rbx+50h]; lpCriticalSection
0x1800026af  mov     edi, 8000FFFFh
0x1800026b4  call    cs:__imp_LeaveCriticalSection
0x1800026ba  jmp     loc_1800025BF
0x1800026bf  lea     rcx, [rbx+50h]; lpCriticalSection
0x1800026c3  mov     edi, 80004005h
0x1800026c8  call    cs:__imp_LeaveCriticalSection
0x1800026ce  jmp     loc_1800025BF
0x1800026d3  mov     r9b, 2; unsigned __int8
0x1800026d6  mov     edx, 6; unsigned int
0x1800026db  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x1800026e0  jmp     loc_1800025D3
```
