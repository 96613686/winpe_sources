# CodeAuthzReloadCacheTables

- ea: `0x1800346fc`
- end: `0x180034808`
- name: `CodeAuthzReloadCacheTables`
- size: `268`
- prototype: `__int64 __fastcall(void *, ULONG)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800346d0`

## callees

- `0x18000ffb0`
- `0x18001001c`
- `0x1800346fc`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800347d3`
- `ntdll!NtOpenKey` at `0x1800347d3`
- `ntdll!NtClose` at `0x180034747`
- `ntdll!NtClose` at `0x180034747`
- `ntdll!RtlLeaveCriticalSection` at `0x1800347f5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800347f5`
- `ntdll!RtlEnterCriticalSection` at `0x180034725`
- `ntdll!RtlEnterCriticalSection` at `0x180034725`

## pseudocode

```c
__int64 __fastcall CodeAuthzReloadCacheTables(void *a1, ULONG a2)
{
  NTSTATUS v4; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-38h] BYREF

  if ( g_bInitializedFirstTime )
  {
    RtlEnterCriticalSection(&g_TableCritSec);
    CodeAuthzLevelObjpEntireTableFree();
    CodeAuthzGuidIdentsEntireTableFree();
    ++g_dwLevelHandleSequence;
    if ( g_hKeyCustomRoot )
    {
      NtClose(g_hKeyCustomRoot);
      g_hKeyCustomRoot = 0;
    }
    g_DefaultCodeLevelUser = 0;
    g_DefaultCodeLevelMachine = 0;
    g_DefaultCodeLevel = 0;
    g_bHonorScopeUser = 0;
    g_bNeedCacheReload = 0;
    g_dwKeyOptions = 0;
    if ( a1 )
    {
      *(_QWORD *)&ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)qword_18007E130;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = a1;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v4 = NtOpenKey(&g_hKeyCustomRoot, 0x20019u, &ObjectAttributes);
      if ( v4 < 0 )
      {
LABEL_9:
        RtlLeaveCriticalSection(&g_TableCritSec);
        return (unsigned int)v4;
      }
      g_dwKeyOptions = a2;
    }
    g_bNeedCacheReload = 1;
    v4 = 0;
    goto LABEL_9;
  }
  return (unsigned int)-1073741823;
}

```

## disassembly

```asm
0x1800346fc  mov     [rsp+arg_0], rbx
0x180034701  push    rdi
0x180034702  sub     rsp, 50h
0x180034706  cmp     cs:g_bInitializedFirstTime, 0
0x18003470d  mov     edi, edx
0x18003470f  mov     rbx, rcx
0x180034712  jnz     short loc_18003471E
0x180034714  mov     ebx, 0C0000001h
0x180034719  jmp     loc_1800347FB
0x18003471e  lea     rcx, g_TableCritSec; CriticalSection
0x180034725  call    cs:__imp_RtlEnterCriticalSection
0x18003472b  call    CodeAuthzLevelObjpEntireTableFree
0x180034730  call    CodeAuthzGuidIdentsEntireTableFree
0x180034735  mov     rcx, cs:g_hKeyCustomRoot; Handle
0x18003473c  inc     cs:g_dwLevelHandleSequence
0x180034742  test    rcx, rcx
0x180034745  jz      short loc_180034758
0x180034747  call    cs:__imp_NtClose
0x18003474d  mov     cs:g_hKeyCustomRoot, 0
0x180034758  mov     cs:g_DefaultCodeLevelUser, 0
0x180034763  mov     cs:g_DefaultCodeLevelMachine, 0
0x18003476e  mov     cs:g_DefaultCodeLevel, 0
0x180034779  mov     cs:g_bHonorScopeUser, 0
0x180034780  mov     cs:g_bNeedCacheReload, 0
0x180034787  mov     cs:g_dwKeyOptions, 0
0x180034791  test    rbx, rbx
0x180034794  jz      short loc_1800347E5
0x180034796  lea     rax, qword_18007E130
0x18003479d  mov     qword ptr [rsp+58h+ObjectAttributes.Length], 30h ; '0'
0x1800347a6  xorps   xmm0, xmm0
0x1800347a9  mov     [rsp+58h+ObjectAttributes.ObjectName], rax
0x1800347ae  lea     r8, [rsp+58h+ObjectAttributes]; ObjectAttributes
0x1800347b3  mov     qword ptr [rsp+58h+ObjectAttributes.Attributes], 40h ; '@'
0x1800347bc  mov     edx, 20019h; DesiredAccess
0x1800347c1  mov     [rsp+58h+ObjectAttributes.RootDirectory], rbx
0x1800347c6  lea     rcx, g_hKeyCustomRoot; KeyHandle
0x1800347cd  movdqu  xmmword ptr [rsp+58h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800347d3  call    cs:__imp_NtOpenKey
0x1800347d9  mov     ebx, eax
0x1800347db  test    eax, eax
0x1800347dd  js      short loc_1800347EE
0x1800347df  mov     cs:g_dwKeyOptions, edi
0x1800347e5  mov     cs:g_bNeedCacheReload, 1
0x1800347ec  xor     ebx, ebx
0x1800347ee  lea     rcx, g_TableCritSec; CriticalSection
0x1800347f5  call    cs:__imp_RtlLeaveCriticalSection
0x1800347fb  mov     eax, ebx
0x1800347fd  mov     rbx, [rsp+58h+arg_0]
0x180034802  add     rsp, 50h
0x180034806  pop     rdi
0x180034807  retn
```
