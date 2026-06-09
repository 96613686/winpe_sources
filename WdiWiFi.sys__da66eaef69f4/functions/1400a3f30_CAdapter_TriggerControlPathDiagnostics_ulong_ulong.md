# CAdapter::TriggerControlPathDiagnostics(ulong,ulong)

- ea: `0x1400a3f30`
- end: `0x1400a411c`
- name: `?TriggerControlPathDiagnostics@CAdapter@@QEAAXKK@Z`
- size: `492`
- prototype: `void __fastcall(CAdapter *__hidden this, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400a23d0`
- `0x1400a61b0`
- `0x1400a6600`
- `0x1400a99c0`

## callees

- `0x1400176b0`
- `0x140017a90`
- `0x140034e04`
- `0x140034ec4`
- `0x1400a3c4c`
- `0x1400a3f30`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400a40bd`
- `ntoskrnl!DbgPrintEx` at `0x1400a40bd`

## pseudocode

```c
void __fastcall CAdapter::TriggerControlPathDiagnostics(CAdapter *this, unsigned int a2, unsigned int a3)
{
  unsigned int v4; // esi
  CMiniportDriver *m_MiniportDriver; // rax
  void (__fastcall *HangDiagnoseHandler)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // r14
  int PropertyULong; // eax
  int v9; // edx
  int v10; // r8d
  unsigned int v11; // esi
  int v12; // ebp
  int v13; // ebx
  int v14; // edx
  __int64 v15; // [rsp+28h] [rbp-50h]
  unsigned int v16; // [rsp+88h] [rbp+10h] BYREF

  v4 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      90,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  this->m_DebugDiagnosticsTriggerTime = MEMORY[0xFFFFF78000000014];
  m_MiniportDriver = this->m_MiniportDriver;
  this->m_DebugDiagnosticsTriggerCommand = a3;
  this->m_DebugDiagnosticsTriggerCode = v4;
  v16 = 1;
  HangDiagnoseHandler = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))m_MiniportDriver->m_MiniportWdiCharacteristics.HangDiagnoseHandler;
  PropertyULong = CPropertyCache::GetPropertyULong(&this->m_AdapterPropertyCache, 0x6Du, &v16);
  v11 = v16;
  v12 = PropertyULong;
  if ( PropertyULong )
    v11 = 1;
  if ( HangDiagnoseHandler )
  {
    v16 = 0;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        v10,
        91,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
        1);
    }
    v13 = MEMORY[0xFFFFF78000000014];
    HangDiagnoseHandler(this->m_MiniportAdapterContext, v11, 1024, this->m_DebugFirmwareBuffer, &v16);
    CAdapter::TraceLoggingDiagnosisDuration(this, (MEMORY[0xFFFFF78000000014] - v13) / 0x2710u);
  }
  else
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        92,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
    }
    DbgPrintEx(0, 0, "LE does not have Diagnose handler, level=%d\n", v11);
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v15) = v12;
    LOBYTE(v14) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      1,
      93,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      v15);
  }
}

```

## disassembly

```asm
0x1400a3f30  push    rbx
0x1400a3f32  push    rbp
0x1400a3f33  push    rsi
0x1400a3f34  push    rdi
0x1400a3f35  push    r12
0x1400a3f37  push    r13
0x1400a3f39  push    r14
0x1400a3f3b  push    r15
0x1400a3f3d  sub     rsp, 38h
0x1400a3f41  mov     ebx, r8d
0x1400a3f44  mov     esi, edx
0x1400a3f46  mov     rdi, rcx
0x1400a3f49  xor     r12d, r12d; __annotation("TMF:",
0x1400a3f4c  lea     r13, WPP_RECORDER_INITIALIZED
0x1400a3f53  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a3f5a  lea     rax, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400a3f61  lea     r15d, [r12+1]
0x1400a3f66  jz      short loc_1400A3F95
0x1400a3f68  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3f6f  cmp     byte ptr [rcx+29h], 5
0x1400a3f73  jnb     short loc_1400A3F7C
0x1400a3f75  cmp     [rcx+48h], r12w
0x1400a3f7a  jz      short loc_1400A3F95
0x1400a3f7c  mov     rcx, [rcx+40h]
0x1400a3f80  mov     r9d, 5Ah ; 'Z'
0x1400a3f86  mov     r8d, r15d
0x1400a3f89  mov     [rsp+78h+var_58], rax
0x1400a3f8e  mov     dl, 5
0x1400a3f90  call    WPP_RECORDER_SF_
0x1400a3f95  mov     rax, 0FFFFF78000000014h
0x1400a3f9f  lea     rcx, [rdi+78h]; this
0x1400a3fa3  lea     r8, [rsp+78h+arg_8]; unsigned int *
0x1400a3fab  mov     edx, 6Dh ; 'm'; unsigned int
0x1400a3fb0  mov     rax, [rax]
0x1400a3fb3  mov     [rdi+28h], rax
0x1400a3fb7  mov     rax, [rdi+68h]
0x1400a3fbb  mov     [rdi+30h], ebx
0x1400a3fbe  mov     [rdi+34h], esi
0x1400a3fc1  mov     [rsp+78h+arg_8], r15d
0x1400a3fc9  mov     r14, [rax+118h]
0x1400a3fd0  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400a3fd5  mov     esi, [rsp+78h+arg_8]
0x1400a3fdc  test    eax, eax
0x1400a3fde  mov     ebp, eax
0x1400a3fe0  cmovnz  esi, r15d
0x1400a3fe4  test    r14, r14
0x1400a3fe7  jz      loc_1400A407F
0x1400a3fed  mov     [rsp+78h+arg_8], r12d
0x1400a3ff5  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400a3ffc  jz      short loc_1400A4027
0x1400a3ffe  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a4005  lea     rax, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400a400c  mov     r9d, 5Bh ; '['
0x1400a4012  mov     dword ptr [rsp+78h+var_50], r15d
0x1400a4017  mov     dl, 4
0x1400a4019  mov     [rsp+78h+var_58], rax
0x1400a401e  mov     rcx, [rcx+40h]
0x1400a4022  call    WPP_RECORDER_SF_d
0x1400a4027  lea     rax, [rsp+78h+arg_8]
0x1400a402f  mov     rbx, 0FFFFF78000000014h
0x1400a4039  mov     [rsp+78h+var_58], rax
0x1400a403e  lea     r9, [rdi+0E34h]
0x1400a4045  mov     r8d, 400h
0x1400a404b  mov     edx, esi
0x1400a404d  mov     rax, r14
0x1400a4050  mov     rbx, [rbx]
0x1400a4053  mov     rcx, [rdi+60h]
0x1400a4057  call    _guard_dispatch_icall
0x1400a405c  mov     rax, 0FFFFF78000000014h
0x1400a4066  mov     rcx, [rax]
0x1400a4069  mov     eax, 0D1B71759h
0x1400a406e  sub     ecx, ebx
0x1400a4070  mul     ecx
0x1400a4072  mov     rcx, rdi; this
0x1400a4075  shr     edx, 0Dh; unsigned int
0x1400a4078  call    ?TraceLoggingDiagnosisDuration@CAdapter@@QEAAXK@Z; CAdapter::TraceLoggingDiagnosisDuration(ulong)
0x1400a407d  jmp     short loc_1400A40C9
0x1400a407f  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400a4086  jz      short loc_1400A40AF
0x1400a4088  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a408f  lea     rax, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400a4096  mov     r9d, 5Ch ; '\'
0x1400a409c  mov     [rsp+78h+var_58], rax
0x1400a40a1  mov     r8d, r15d
0x1400a40a4  mov     dl, 2
0x1400a40a6  mov     rcx, [rcx+40h]
0x1400a40aa  call    WPP_RECORDER_SF_
0x1400a40af  mov     r9d, esi
0x1400a40b2  lea     r8, aLeDoesNotHaveD; "LE does not have Diagnose handler, leve"...
0x1400a40b9  xor     edx, edx; Level
0x1400a40bb  xor     ecx, ecx; ComponentId
0x1400a40bd  call    cs:__imp_DbgPrintEx
0x1400a40c4  nop     dword ptr [rax+rax+00h]
0x1400a40c9  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400a40d0  jz      short loc_1400A410A
0x1400a40d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a40d9  cmp     byte ptr [rcx+29h], 5
0x1400a40dd  jnb     short loc_1400A40E6
0x1400a40df  cmp     [rcx+48h], r12w
0x1400a40e4  jz      short loc_1400A410A
0x1400a40e6  mov     rcx, [rcx+40h]
0x1400a40ea  lea     rax, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400a40f1  mov     r9d, 5Dh ; ']'
0x1400a40f7  mov     dword ptr [rsp+78h+var_50], ebp
0x1400a40fb  mov     r8d, r15d
0x1400a40fe  mov     [rsp+78h+var_58], rax
0x1400a4103  mov     dl, 5
0x1400a4105  call    WPP_RECORDER_SF_D
0x1400a410a  add     rsp, 38h
0x1400a410e  pop     r15
0x1400a4110  pop     r14
0x1400a4112  pop     r13
0x1400a4114  pop     r12
0x1400a4116  pop     rdi
0x1400a4117  pop     rsi
0x1400a4118  pop     rbp
0x1400a4119  pop     rbx
0x1400a411a  retn
```
