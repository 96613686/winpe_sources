# SID_MAPPER::DoAddMappings(void)

- ea: `0x180002348`
- end: `0x1800024a6`
- name: `?DoAddMappings@SID_MAPPER@@AEAAJXZ`
- size: `350`
- prototype: `__int64 __fastcall(SID_MAPPER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800027c0`

## callees

- `0x180001048`
- `0x18000154c`
- `0x180002348`
- `0x180007c5c`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x1800023f1`
- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x1800023f1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000240e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000246a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000240e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000246a`
- `ntdll!RtlInitUnicodeString` at `0x1800023b7`
- `ntdll!RtlInitUnicodeString` at `0x1800023d8`
- `ntdll!RtlInitUnicodeString` at `0x1800023b7`
- `ntdll!RtlInitUnicodeString` at `0x1800023d8`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180002455`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180002455`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SID_MAPPER::DoAddMappings(SID_MAPPER *this)
{
  int AdditionList; // r14d
  struct APP_POOL_SID_DATA *v2; // rdi
  unsigned int v4; // ebx
  unsigned __int64 v5; // r15
  int v6; // eax
  PVOID v7; // rcx
  unsigned int v8; // edx
  _UNICODE_STRING DestinationString[3]; // [rsp+30h] [rbp-30h] BYREF
  const unsigned __int16 *v10; // [rsp+90h] [rbp+30h] BYREF
  PVOID Buffer; // [rsp+98h] [rbp+38h] BYREF
  struct APP_POOL_SID_DATA *v12; // [rsp+A0h] [rbp+40h] BYREF

  LODWORD(v10) = 0;
  v12 = 0;
  memset(DestinationString, 0, sizeof(DestinationString));
  Buffer = 0;
  AdditionList = APP_POOL_HASH_MAPPER::GetAdditionList((SID_MAPPER *)((char *)this + 32), (unsigned int *)&v10, &v12);
  v2 = v12;
  if ( AdditionList < 0 )
    goto LABEL_13;
  if ( !(_DWORD)v10 )
    return 0;
  RtlInitUnicodeString(DestinationString, L"IIS APPPOOL");
  v4 = 0;
  if ( (_DWORD)v10 )
  {
    while ( 1 )
    {
      v5 = (unsigned __int64)v4 << 6;
      RtlInitUnicodeString(&DestinationString[1], *(PCWSTR *)((char *)v2 + v5 + 32));
      *(_QWORD *)&DestinationString[2].Length = *(_QWORD *)((char *)v2 + v5 + 56);
      v6 = LsaManageSidNameMapping(0, DestinationString, &Buffer);
      v7 = Buffer;
      if ( v6 < 0 )
      {
        v8 = *(_DWORD *)Buffer;
        if ( *(_DWORD *)Buffer != 3 )
        {
          v10 = 0;
          v10 = *(const unsigned __int16 **)((char *)v2 + v5 + 32);
          EVENT_LOG::LogEvent((APP_HOST_SERVICE *)((char *)g_pAppHostService + 136), 0xC000232D, 1u, &v10, v8);
          AdditionList = -2147467259;
          break;
        }
        AdditionList = 0;
      }
      if ( Buffer )
      {
        LsaFreeMemory(Buffer);
        v7 = 0;
        Buffer = 0;
      }
      if ( ++v4 >= (unsigned int)v10 )
        goto LABEL_14;
    }
  }
LABEL_13:
  v7 = Buffer;
LABEL_14:
  if ( v7 )
    LsaFreeMemory(v7);
  if ( v2 )
  {
    `eh vector destructor iterator'(
      v2,
      0x40u,
      *((_QWORD *)v2 - 1),
      (void (*)(void *))APP_POOL_SID_DATA::~APP_POOL_SID_DATA);
    operator delete((char *)v2 - 8);
  }
  return (unsigned int)AdditionList;
}

```

## disassembly

```asm
0x180002348  push    rbp
0x18000234a  push    rbx
0x18000234b  push    rdi
0x18000234c  push    r14
0x18000234e  push    r15
0x180002350  mov     rbp, rsp
0x180002353  sub     rsp, 60h
0x180002357  mov     dword ptr [rbp+arg_0], 0
0x18000235e  mov     [rbp+arg_10], 0
0x180002366  xor     eax, eax
0x180002368  mov     [rbp+DestinationString.Length], ax
0x18000236c  xorps   xmm0, xmm0
0x18000236f  movups  xmmword ptr [rbp+DestinationString.MaximumLength], xmm0
0x180002373  movups  xmmword ptr [rbp+var_20+2], xmm0
0x180002377  movups  xmmword ptr [rbp+var_20+10h], xmm0
0x18000237b  mov     [rbp+Buffer], rax
0x18000237f  add     rcx, 20h ; ' '; this
0x180002383  lea     r8, [rbp+arg_10]; struct APP_POOL_SID_DATA **
0x180002387  lea     rdx, [rbp+arg_0]; unsigned int *
0x18000238b  call    ?GetAdditionList@APP_POOL_HASH_MAPPER@@QEAAJPEAKPEAPEAUAPP_POOL_SID_DATA@@@Z; APP_POOL_HASH_MAPPER::GetAdditionList(ulong *,APP_POOL_SID_DATA * *)
0x180002390  mov     r14d, eax
0x180002393  mov     rdi, [rbp+arg_10]
0x180002397  test    eax, eax
0x180002399  js      loc_180002461
0x18000239f  cmp     dword ptr [rbp+arg_0], 0
0x1800023a3  jnz     short loc_1800023AC
0x1800023a5  xor     eax, eax
0x1800023a7  jmp     loc_18000249A
0x1800023ac  lea     rdx, SourceString; "IIS APPPOOL"
0x1800023b3  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800023b7  call    cs:__imp_RtlInitUnicodeString
0x1800023bd  xor     ebx, ebx
0x1800023bf  cmp     dword ptr [rbp+arg_0], ebx
0x1800023c2  jbe     loc_180002461
0x1800023c8  mov     r15d, ebx
0x1800023cb  shl     r15, 6
0x1800023cf  mov     rdx, [r15+rdi+20h]; SourceString
0x1800023d4  lea     rcx, [rbp+var_20]; DestinationString
0x1800023d8  call    cs:__imp_RtlInitUnicodeString
0x1800023de  mov     rax, [r15+rdi+38h]
0x1800023e3  mov     qword ptr [rbp+var_20+10h], rax
0x1800023e7  lea     r8, [rbp+Buffer]
0x1800023eb  lea     rdx, [rbp+DestinationString]
0x1800023ef  xor     ecx, ecx
0x1800023f1  call    cs:__imp_LsaManageSidNameMapping
0x1800023f7  mov     rcx, [rbp+Buffer]; Buffer
0x1800023fb  test    eax, eax
0x1800023fd  jns     short loc_180002409
0x1800023ff  mov     edx, [rcx]
0x180002401  cmp     edx, 3
0x180002404  jnz     short loc_180002423
0x180002406  xor     r14d, r14d
0x180002409  test    rcx, rcx
0x18000240c  jz      short loc_18000241A
0x18000240e  call    cs:__imp_LsaFreeMemory
0x180002414  xor     ecx, ecx
0x180002416  mov     [rbp+Buffer], rcx
0x18000241a  inc     ebx
0x18000241c  cmp     ebx, dword ptr [rbp+arg_0]
0x18000241f  jb      short loc_1800023C8
0x180002421  jmp     short loc_180002465
0x180002423  mov     [rbp+arg_0], 0
0x18000242b  mov     rax, [r15+rdi+20h]
0x180002430  mov     [rbp+arg_0], rax
0x180002434  mov     r8d, 1
0x18000243a  mov     rcx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x180002441  add     rcx, 88h
0x180002448  mov     [rsp+60h+var_40], edx
0x18000244c  lea     r9, [rbp+arg_0]
0x180002450  mov     edx, 0C000232Dh
0x180002455  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000245b  mov     r14d, 80004005h
0x180002461  mov     rcx, [rbp+Buffer]; Buffer
0x180002465  test    rcx, rcx
0x180002468  jz      short loc_180002470
0x18000246a  call    cs:__imp_LsaFreeMemory
0x180002470  test    rdi, rdi
0x180002473  jz      short loc_180002497
0x180002475  lea     r9, ??1APP_POOL_SID_DATA@@QEAA@XZ; void (*)(void *)
0x18000247c  mov     r8, [rdi-8]; unsigned __int64
0x180002480  mov     edx, 40h ; '@'; unsigned __int64
0x180002485  mov     rcx, rdi; void *
0x180002488  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000248d  lea     rcx, [rdi-8]; Block
0x180002491  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002496  nop
0x180002497  mov     eax, r14d
0x18000249a  add     rsp, 60h
0x18000249e  pop     r15
0x1800024a0  pop     r14
0x1800024a2  pop     rdi
0x1800024a3  pop     rbx
0x1800024a4  pop     rbp
0x1800024a5  retn
```
