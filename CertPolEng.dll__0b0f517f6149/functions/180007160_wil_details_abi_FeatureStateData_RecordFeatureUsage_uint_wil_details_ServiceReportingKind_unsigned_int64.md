# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180007160`
- end: `0x18000721d`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `189`
- prototype: `char __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000b9b0`

## callees

- `0x180007160`
- `0x180007230`
- `0x180010eb0`
- `0x180010ee4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800071a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800071a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800071fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800071fa`

## pseudocode

```c
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  int v9; // eax
  char v10; // di

  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage((PSRWLOCK)a1);
    return 1;
  }
  else if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1);
    if ( a3 <= 7 && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(a1 + 8, a3, a2);
      v10 = *(_BYTE *)(a1 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              a1 + 72,
              a3,
              a2,
              a4);
    }
    if ( a1 )
      ReleaseSRWLockExclusive((PSRWLOCK)a1);
    return v10;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180007160  push    rbx
0x180007162  push    rbp
0x180007163  push    rsi
0x180007164  push    rdi
0x180007165  sub     rsp, 28h
0x180007169  mov     rbp, r9
0x18000716c  mov     edi, r8d
0x18000716f  mov     esi, edx
0x180007171  mov     rbx, rcx
0x180007174  cmp     r8d, 0FEh
0x18000717b  jz      loc_18000720D
0x180007181  cmp     r8d, 0C8h
0x180007188  jb      short loc_1800071A0
0x18000718a  cmp     r8d, 100h
0x180007191  jl      short loc_18000719C
0x180007193  cmp     r8d, 200h
0x18000719a  jb      short loc_1800071A0
0x18000719c  xor     al, al
0x18000719e  jmp     short loc_180007214
0x1800071a0  mov     [rsp+48h+arg_0], r14
0x1800071a5  call    cs:__imp_AcquireSRWLockExclusive
0x1800071ab  cmp     edi, 7
0x1800071ae  ja      short loc_1800071BA
0x1800071b0  mov     eax, 0CCh
0x1800071b5  bt      eax, edi
0x1800071b8  jb      short loc_1800071DB
0x1800071ba  lea     eax, [rdi-100h]
0x1800071c0  cmp     eax, 7Fh
0x1800071c3  jbe     short loc_1800071DB
0x1800071c5  mov     r9d, ebp
0x1800071c8  lea     rcx, [rbx+48h]
0x1800071cc  mov     r8d, esi
0x1800071cf  mov     edx, edi
0x1800071d1  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800071d6  movzx   edi, al
0x1800071d9  jmp     short loc_1800071ED
0x1800071db  mov     r8d, esi
0x1800071de  lea     rcx, [rbx+8]
0x1800071e2  mov     edx, edi
0x1800071e4  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800071e9  movzx   edi, byte ptr [rbx+40h]
0x1800071ed  mov     r14, [rsp+48h+arg_0]
0x1800071f2  test    rbx, rbx
0x1800071f5  jz      short loc_180007200
0x1800071f7  mov     rcx, rbx; SRWLock
0x1800071fa  call    cs:__imp_ReleaseSRWLockExclusive
0x180007200  movzx   eax, dil
0x180007204  add     rsp, 28h
0x180007208  pop     rdi
0x180007209  pop     rsi
0x18000720a  pop     rbp
0x18000720b  pop     rbx
0x18000720c  retn
0x18000720d  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007212  mov     al, 1
0x180007214  add     rsp, 28h
0x180007218  pop     rdi
0x180007219  pop     rsi
0x18000721a  pop     rbp
0x18000721b  pop     rbx
0x18000721c  retn
```
