# ServiceManager::UseDefaultExternalStorage(int *)

- ea: `0x18001e290`
- end: `0x18001e34e`
- name: `?UseDefaultExternalStorage@ServiceManager@@UEAAJPEAH@Z`
- size: `190`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180009c88`
- `0x18001e290`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `MosStorage!MosStorageUseDefaultExternalStorage` at `0x18001e306`
- `MosStorage!MosStorageUseDefaultExternalStorage` at `0x18001e306`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e322`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e322`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001e2dc`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001e2dc`

## string_xrefs

- `0x18001e2d0`: `ServiceManager::UseDefaultExternalStorage`
- `0x18001e319`: `ServiceManager::UseDefaultExternalStorage`

## pseudocode

```c
__int64 __fastcall ServiceManager::UseDefaultExternalStorage(ServiceManager *this, int *a2)
{
  int v4; // r8d
  unsigned int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  _BYTE v9[24]; // [rsp+20h] [rbp-18h] BYREF
  bool v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = 0;
  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v9);
  if ( ClientsTracker::HasClientsRequiringServiceInitialized((LPCRITICAL_SECTION)((char *)this + 3816)) )
  {
    v4 = 3769;
LABEL_3:
    v5 = ZTraceReportOrigination(-2080374784, "ServiceManager::UseDefaultExternalStorage", v4, this);
    goto LABEL_4;
  }
  if ( *((_DWORD *)this + 882) )
  {
    v4 = 3770;
    goto LABEL_3;
  }
  v7 = MosStorageUseDefaultExternalStorage(&v10);
  if ( v7 >= 0 )
  {
    v6 = 0;
    RelockableGate::~RelockableGate((RelockableGate *)v9);
    *a2 = v10;
    return v6;
  }
  v5 = ZTraceReportPropagation(v7, "ServiceManager::UseDefaultExternalStorage", 3772, this);
LABEL_4:
  v6 = v5;
  RelockableGate::~RelockableGate((RelockableGate *)v9);
  return v6;
}

```

## disassembly

```asm
0x18001e290  mov     [rsp+arg_8], rbx
0x18001e295  push    rdi
0x18001e296  sub     rsp, 30h
0x18001e29a  mov     rdi, rdx
0x18001e29d  mov     rbx, rcx
0x18001e2a0  mov     [rsp+38h+arg_0], 0
0x18001e2a5  add     rcx, 0D48h
0x18001e2ac  lea     rdx, [rsp+38h+var_18]
0x18001e2b1  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001e2b6  nop
0x18001e2b7  lea     rcx, [rbx+0EE8h]; lpCriticalSection
0x18001e2be  call    ?HasClientsRequiringServiceInitialized@ClientsTracker@@QEAA_NXZ; ClientsTracker::HasClientsRequiringServiceInitialized(void)
0x18001e2c3  test    al, al
0x18001e2c5  jz      short loc_18001E2F0
0x18001e2c7  mov     r8d, 0EB9h
0x18001e2cd  mov     r9, rbx
0x18001e2d0  lea     rdx, aServicemanager_3; "ServiceManager::UseDefaultExternalStora"...
0x18001e2d7  mov     ecx, 84000000h
0x18001e2dc  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001e2e2  mov     ebx, eax
0x18001e2e4  lea     rcx, [rsp+38h+var_18]; this
0x18001e2e9  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001e2ee  jmp     short loc_18001E341
0x18001e2f0  cmp     dword ptr [rbx+0DC8h], 0
0x18001e2f7  jz      short loc_18001E301
0x18001e2f9  mov     r8d, 0EBAh
0x18001e2ff  jmp     short loc_18001E2CD
0x18001e301  lea     rcx, [rsp+38h+arg_0]
0x18001e306  call    cs:__imp_?MosStorageUseDefaultExternalStorage@@YAJPEA_N@Z; MosStorageUseDefaultExternalStorage(bool *)
0x18001e30c  test    eax, eax
0x18001e30e  jns     short loc_18001E32A
0x18001e310  mov     r9, rbx
0x18001e313  mov     r8d, 0EBCh
0x18001e319  lea     rdx, aServicemanager_3; "ServiceManager::UseDefaultExternalStora"...
0x18001e320  mov     ecx, eax
0x18001e322  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001e328  jmp     short loc_18001E2E2
0x18001e32a  xor     ebx, ebx
0x18001e32c  lea     rcx, [rsp+38h+var_18]; this
0x18001e331  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001e336  xor     eax, eax
0x18001e338  cmp     [rsp+38h+arg_0], al
0x18001e33c  setnz   al
0x18001e33f  mov     [rdi], eax
0x18001e341  mov     eax, ebx
0x18001e343  mov     rbx, [rsp+38h+arg_8]
0x18001e348  add     rsp, 30h
0x18001e34c  pop     rdi
0x18001e34d  retn
```
