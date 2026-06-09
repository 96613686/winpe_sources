# SID_MAPPER::DoDeleteMappings(void)

- ea: `0x1800024ac`
- end: `0x1800025f1`
- name: `?DoDeleteMappings@SID_MAPPER@@AEAAJXZ`
- size: `325`
- prototype: `__int64 __fastcall(SID_MAPPER *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800027c0`

## callees

- `0x180001048`
- `0x18000154c`
- `0x1800024ac`
- `0x180007afc`
- `0x180007f40`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x180002555`
- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x180002555`
- `ntdll!RtlInitUnicodeString` at `0x180002531`
- `ntdll!RtlInitUnicodeString` at `0x180002542`
- `ntdll!RtlInitUnicodeString` at `0x180002531`
- `ntdll!RtlInitUnicodeString` at `0x180002542`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800025ac`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800025ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SID_MAPPER::DoDeleteMappings(SID_MAPPER *this)
{
  APP_POOL_HASH_MAPPER *v1; // r12
  int DeletionList; // r14d
  struct APP_POOL_SID_DATA *v3; // rdi
  unsigned int v4; // ebx
  unsigned int v6; // esi
  unsigned __int64 v7; // r15
  struct _UNICODE_STRING DestinationString[3]; // [rsp+30h] [rbp-30h] BYREF
  const unsigned __int16 *v9; // [rsp+A0h] [rbp+40h] BYREF
  struct APP_POOL_SID_DATA *v10; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int *v11; // [rsp+B0h] [rbp+50h] BYREF

  LODWORD(v9) = 0;
  v10 = 0;
  memset(DestinationString, 0, sizeof(DestinationString));
  v11 = 0;
  v1 = (SID_MAPPER *)((char *)this + 32);
  DeletionList = APP_POOL_HASH_MAPPER::GetDeletionList((SID_MAPPER *)((char *)this + 32), (unsigned int *)&v9, &v10);
  v3 = v10;
  if ( DeletionList >= 0 )
  {
    v4 = (unsigned int)v9;
    if ( !(_DWORD)v9 )
      return 0;
    v6 = 0;
    while ( 1 )
    {
      v7 = (unsigned __int64)v6 << 6;
      RtlInitUnicodeString(&DestinationString[1], *(PCWSTR *)((char *)v3 + v7 + 32));
      RtlInitUnicodeString(DestinationString, L"IIS APPPOOL");
      if ( (int)LsaManageSidNameMapping(1, DestinationString, &v11) < 0 )
        break;
      APP_POOL_HASH_MAPPER::DeleteAppPool(v1, *(const unsigned __int16 **)((char *)v3 + v7 + 32));
      if ( ++v6 >= v4 )
        goto LABEL_9;
    }
    v9 = 0;
    v9 = *(const unsigned __int16 **)((char *)v3 + v7 + 32);
    EVENT_LOG::LogEvent((APP_HOST_SERVICE *)((char *)g_pAppHostService + 136), 0xC000232B, 1u, &v9, *v11);
    DeletionList = -2147467259;
  }
LABEL_9:
  if ( v3 )
  {
    `eh vector destructor iterator'(
      v3,
      0x40u,
      *((_QWORD *)v3 - 1),
      (void (*)(void *))APP_POOL_SID_DATA::~APP_POOL_SID_DATA);
    operator delete((char *)v3 - 8);
  }
  return (unsigned int)DeletionList;
}

```

## disassembly

```asm
0x1800024ac  push    rbp
0x1800024ae  push    rbx
0x1800024af  push    rsi
0x1800024b0  push    rdi
0x1800024b1  push    r12
0x1800024b3  push    r14
0x1800024b5  push    r15
0x1800024b7  mov     rbp, rsp
0x1800024ba  sub     rsp, 60h
0x1800024be  mov     dword ptr [rbp+arg_0], 0
0x1800024c5  mov     [rbp+arg_8], 0
0x1800024cd  xor     eax, eax
0x1800024cf  mov     word ptr [rbp+DestinationString], ax
0x1800024d3  xorps   xmm0, xmm0
0x1800024d6  movups  xmmword ptr [rbp+DestinationString+2], xmm0
0x1800024da  movups  xmmword ptr [rbp+var_1E], xmm0
0x1800024de  movups  xmmword ptr [rbp+var_1E+0Eh], xmm0
0x1800024e2  mov     [rbp+arg_10], rax
0x1800024e6  lea     r12, [rcx+20h]
0x1800024ea  lea     r8, [rbp+arg_8]; struct APP_POOL_SID_DATA **
0x1800024ee  lea     rdx, [rbp+arg_0]; unsigned int *
0x1800024f2  mov     rcx, r12; this
0x1800024f5  call    ?GetDeletionList@APP_POOL_HASH_MAPPER@@QEAAJPEAKPEAPEAUAPP_POOL_SID_DATA@@@Z; APP_POOL_HASH_MAPPER::GetDeletionList(ulong *,APP_POOL_SID_DATA * *)
0x1800024fa  mov     r14d, eax
0x1800024fd  mov     rdi, [rbp+arg_8]
0x180002501  test    eax, eax
0x180002503  js      loc_1800025B8
0x180002509  mov     ebx, dword ptr [rbp+arg_0]
0x18000250c  test    ebx, ebx
0x18000250e  jnz     short loc_180002517
0x180002510  xor     eax, eax
0x180002512  jmp     loc_1800025E2
0x180002517  xor     esi, esi
0x180002519  test    ebx, ebx
0x18000251b  jz      loc_1800025B8
0x180002521  mov     r15d, esi
0x180002524  shl     r15, 6
0x180002528  mov     rdx, [r15+rdi+20h]; SourceString
0x18000252d  lea     rcx, [rbp+DestinationString+10h]; DestinationString
0x180002531  call    cs:__imp_RtlInitUnicodeString
0x180002537  lea     rdx, SourceString; "IIS APPPOOL"
0x18000253e  lea     rcx, [rbp+DestinationString]; DestinationString
0x180002542  call    cs:__imp_RtlInitUnicodeString
0x180002548  lea     r8, [rbp+arg_10]
0x18000254c  lea     rdx, [rbp+DestinationString]
0x180002550  mov     ecx, 1
0x180002555  call    cs:__imp_LsaManageSidNameMapping
0x18000255b  test    eax, eax
0x18000255d  js      short loc_180002574
0x18000255f  mov     rdx, [r15+rdi+20h]; unsigned __int16 *
0x180002564  mov     rcx, r12; this
0x180002567  call    ?DeleteAppPool@APP_POOL_HASH_MAPPER@@QEAAJPEBG@Z; APP_POOL_HASH_MAPPER::DeleteAppPool(ushort const *)
0x18000256c  inc     esi
0x18000256e  cmp     esi, ebx
0x180002570  jb      short loc_180002521
0x180002572  jmp     short loc_1800025B8
0x180002574  mov     [rbp+arg_0], 0
0x18000257c  mov     rax, [r15+rdi+20h]
0x180002581  mov     [rbp+arg_0], rax
0x180002585  mov     r8d, 1
0x18000258b  mov     rcx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x180002592  add     rcx, 88h
0x180002599  mov     rax, [rbp+arg_10]
0x18000259d  mov     edx, [rax]
0x18000259f  mov     [rsp+60h+var_40], edx
0x1800025a3  lea     r9, [rbp+arg_0]
0x1800025a7  mov     edx, 0C000232Bh
0x1800025ac  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x1800025b2  mov     r14d, 80004005h
0x1800025b8  test    rdi, rdi
0x1800025bb  jz      short loc_1800025DF
0x1800025bd  lea     r9, ??1APP_POOL_SID_DATA@@QEAA@XZ; void (*)(void *)
0x1800025c4  mov     r8, [rdi-8]; unsigned __int64
0x1800025c8  mov     edx, 40h ; '@'; unsigned __int64
0x1800025cd  mov     rcx, rdi; void *
0x1800025d0  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800025d5  lea     rcx, [rdi-8]; Block
0x1800025d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800025de  nop
0x1800025df  mov     eax, r14d
0x1800025e2  add     rsp, 60h
0x1800025e6  pop     r15
0x1800025e8  pop     r14
0x1800025ea  pop     r12
0x1800025ec  pop     rdi
0x1800025ed  pop     rsi
0x1800025ee  pop     rbx
0x1800025ef  pop     rbp
0x1800025f0  retn
```
