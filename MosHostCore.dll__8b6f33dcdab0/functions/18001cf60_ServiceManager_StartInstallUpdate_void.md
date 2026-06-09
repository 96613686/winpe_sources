# ServiceManager::StartInstallUpdate(void)

- ea: `0x18001cf60`
- end: `0x18001d068`
- name: `?StartInstallUpdate@ServiceManager@@UEAAJXZ`
- size: `264`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18001b1a4`

## callees

- `0x18001b068`
- `0x18001cf60`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001d034`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001d034`

## string_xrefs

- `0x18001d02d`: `ServiceManager::StartInstallUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::StartInstallUpdate(struct _RTL_CRITICAL_SECTION *this)
{
  char v2; // si
  int v3; // r8d
  int v4; // ecx
  bool *v5; // rax
  bool v6; // cl
  struct _RTL_CRITICAL_SECTION_DEBUG *SpinCount; // rax
  HANDLE OwningThread; // rax
  int updated; // eax
  int v10; // edi
  _BYTE v12[24]; // [rsp+20h] [rbp-18h] BYREF

  v2 = 0;
  CriticalSectionWithConditionVariable::Lock(this + 85, (__int64)v12);
  if ( (unsigned int)(this[88].LockCount - 4) <= 1 )
  {
    if ( LODWORD(this[88].DebugInfo) || HIDWORD(this[88].DebugInfo) )
    {
      v3 = 1152;
      v4 = -2147024567;
    }
    else
    {
      v5 = (bool *)&this[107].SpinCount + 2;
      v6 = this[108].LockCount == 5 || *v5;
      *v5 = v6;
      SpinCount = (struct _RTL_CRITICAL_SECTION_DEBUG *)this[86].SpinCount;
      if ( SpinCount != this[87].DebugInfo )
        this[87].DebugInfo = SpinCount;
      OwningThread = this[87].OwningThread;
      if ( OwningThread != this[87].LockSemaphore )
        this[87].LockSemaphore = OwningThread;
      updated = ServiceManager::ProcessPackageOrUpdateOperation((ServiceManager *)this);
      if ( updated >= 0 )
      {
        v10 = 0;
        goto LABEL_20;
      }
      v2 = 1;
      v3 = 1163;
      v4 = updated;
    }
  }
  else
  {
    v3 = 1151;
    v4 = -2147024875;
  }
  v10 = ZTraceReportOrigination(v4, "ServiceManager::StartInstallUpdate", v3, this);
  if ( v10 < 0 && v2 )
    BYTE2(this[107].SpinCount) = 0;
LABEL_20:
  RelockableGate::~RelockableGate((RelockableGate *)v12);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001cf60  mov     [rsp+arg_0], rbx
0x18001cf65  mov     [rsp+arg_8], rsi
0x18001cf6a  push    rdi
0x18001cf6b  sub     rsp, 30h
0x18001cf6f  mov     rbx, rcx
0x18001cf72  xor     sil, sil
0x18001cf75  add     rcx, 0D48h
0x18001cf7c  lea     rdx, [rsp+38h+var_18]
0x18001cf81  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001cf86  nop
0x18001cf87  mov     eax, [rbx+0DC8h]
0x18001cf8d  sub     eax, 4
0x18001cf90  cmp     eax, 1
0x18001cf93  jbe     short loc_18001CFA5
0x18001cf95  mov     r8d, 47Fh
0x18001cf9b  mov     ecx, 80070015h
0x18001cfa0  jmp     loc_18001D02A
0x18001cfa5  cmp     dword ptr [rbx+0DC0h], 0
0x18001cfac  jnz     short loc_18001D01F
0x18001cfae  cmp     dword ptr [rbx+0DC4h], 0
0x18001cfb5  jnz     short loc_18001D01F
0x18001cfb7  lea     rax, [rbx+10DAh]
0x18001cfbe  cmp     dword ptr [rbx+10E8h], 5
0x18001cfc5  jz      short loc_18001CFD0
0x18001cfc7  cmp     byte ptr [rax], 0
0x18001cfca  jnz     short loc_18001CFD0
0x18001cfcc  xor     cl, cl
0x18001cfce  jmp     short loc_18001CFD2
0x18001cfd0  mov     cl, 1
0x18001cfd2  mov     [rax], cl
0x18001cfd4  mov     rax, [rbx+0D90h]
0x18001cfdb  cmp     rax, [rbx+0D98h]
0x18001cfe2  jz      short loc_18001CFEB
0x18001cfe4  mov     [rbx+0D98h], rax
0x18001cfeb  mov     rax, [rbx+0DA8h]
0x18001cff2  cmp     rax, [rbx+0DB0h]
0x18001cff9  jz      short loc_18001D002
0x18001cffb  mov     [rbx+0DB0h], rax
0x18001d002  mov     rcx, rbx; this
0x18001d005  call    ?ProcessPackageOrUpdateOperation@ServiceManager@@AEAAJXZ; ServiceManager::ProcessPackageOrUpdateOperation(void)
0x18001d00a  test    eax, eax
0x18001d00c  jns     short loc_18001D01B
0x18001d00e  mov     sil, 1
0x18001d011  mov     r8d, 48Bh
0x18001d017  mov     ecx, eax
0x18001d019  jmp     short loc_18001D02A
0x18001d01b  xor     edi, edi
0x18001d01d  jmp     short loc_18001D04C
0x18001d01f  mov     r8d, 480h
0x18001d025  mov     ecx, 80070149h
0x18001d02a  mov     r9, rbx
0x18001d02d  lea     rdx, aServicemanager_1; "ServiceManager::StartInstallUpdate"
0x18001d034  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001d03a  mov     edi, eax
0x18001d03c  test    eax, eax
0x18001d03e  jns     short loc_18001D04C
0x18001d040  test    sil, sil
0x18001d043  jz      short loc_18001D04C
0x18001d045  mov     byte ptr [rbx+10DAh], 0
0x18001d04c  lea     rcx, [rsp+38h+var_18]; this
0x18001d051  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001d056  mov     eax, edi
0x18001d058  mov     rbx, [rsp+38h+arg_0]
0x18001d05d  mov     rsi, [rsp+38h+arg_8]
0x18001d062  add     rsp, 30h
0x18001d066  pop     rdi
0x18001d067  retn
```
