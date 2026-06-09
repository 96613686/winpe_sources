# CspGenerateControlEvent

- ea: `0x14001dc28`
- end: `0x14001dd45`
- name: `CspGenerateControlEvent`
- size: `285`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14001d83c`
- `0x14001fa30`

## callees

- `0x14001dc28`

## import_xrefs

- `ntdll!LdrGetProcedureAddress` at `0x14001dca8`
- `ntdll!LdrGetProcedureAddress` at `0x14001dca8`
- `ntdll!LdrGetDllHandle` at `0x14001dc8f`
- `ntdll!LdrGetDllHandle` at `0x14001dc8f`
- `ntdll!RtlAcquireSRWLockShared` at `0x14001dcc4`
- `ntdll!RtlAcquireSRWLockShared` at `0x14001dcc4`
- `ntdll!RtlReleaseSRWLockShared` at `0x14001dd3e`
- `ntdll!RtlCreateUserThread` at `0x14001dd19`
- `ntdll!RtlCreateUserThread` at `0x14001dd19`

## string_xrefs

- `0x14001dc53`: `KernelBase.dll`

## pseudocode

```c
__int64 __fastcall CspGenerateControlEvent(__int64 a1, unsigned int a2)
{
  unsigned __int64 Reserved6; // r14
  __int64 v4; // rsi
  _QWORD *v5; // rdi
  _QWORD *i; // rbx
  void *v7; // rcx
  struct _UNICODE_STRING DllName; // [rsp+50h] [rbp-20h] BYREF
  _STRING Name; // [rsp+60h] [rbp-10h] BYREF
  PVOID DllHandle; // [rsp+90h] [rbp+20h] BYREF
  PVOID ProcedureAddress; // [rsp+A0h] [rbp+30h] BYREF

  Name.Buffer = "CtrlRoutine";
  Reserved6 = a2;
  DllName.Buffer = L"KernelBase.dll";
  ProcedureAddress = 0;
  *(_QWORD *)&Name.Length = 786443;
  DllHandle = 0;
  *(_QWORD *)&DllName.Length = 1966108;
  if ( !CspControlRoutine
    && LdrGetDllHandle(0, 0, &DllName, &DllHandle) >= 0
    && LdrGetProcedureAddress(DllHandle, &Name, 0, &ProcedureAddress) >= 0 )
  {
    CspControlRoutine = ProcedureAddress;
  }
  v4 = a1 + 48;
  RtlAcquireSRWLockShared(a1 + 48);
  v5 = (_QWORD *)(a1 + 64);
  for ( i = (_QWORD *)*v5; i != v5; i = (_QWORD *)*i )
  {
    v7 = (void *)i[3];
    if ( v7 )
      RtlCreateUserThread(v7, 0, 0, 0, 0, 0, CspControlRoutine, (PVOID)Reserved6, 0, 0);
  }
  return RtlReleaseSRWLockShared(v4);
}

```

## disassembly

```asm
0x14001dc28  mov     [rsp-18h+arg_8], rbx
0x14001dc2d  mov     [rsp-18h+arg_18], rsi
0x14001dc32  push    rbp
0x14001dc33  push    rdi
0x14001dc34  push    r14
0x14001dc36  mov     rbp, rsp
0x14001dc39  sub     rsp, 70h
0x14001dc3d  cmp     cs:CspControlRoutine, 0
0x14001dc45  lea     rax, aCtrlroutine; "CtrlRoutine"
0x14001dc4c  mov     [rbp+Name.Buffer], rax
0x14001dc50  mov     rdi, rcx
0x14001dc53  lea     rax, aKernelbaseDll_0; "KernelBase.dll"
0x14001dc5a  mov     r14d, edx
0x14001dc5d  mov     [rbp+DllName.Buffer], rax
0x14001dc61  mov     [rbp+ProcedureAddress], 0
0x14001dc69  mov     qword ptr [rbp+Name.Length], 0C000Bh
0x14001dc71  mov     [rbp+DllHandle], 0
0x14001dc79  mov     qword ptr [rbp+DllName.Length], 1E001Ch
0x14001dc81  jnz     short loc_14001DCBD
0x14001dc83  lea     r9, [rbp+DllHandle]; DllHandle
0x14001dc87  xor     edx, edx; DllCharacteristics
0x14001dc89  lea     r8, [rbp+DllName]; DllName
0x14001dc8d  xor     ecx, ecx; DllPath
0x14001dc8f  call    cs:__imp_LdrGetDllHandle
0x14001dc95  test    eax, eax
0x14001dc97  js      short loc_14001DCBD
0x14001dc99  mov     rcx, [rbp+DllHandle]; BaseAddress
0x14001dc9d  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x14001dca1  xor     r8d, r8d; Ordinal
0x14001dca4  lea     rdx, [rbp+Name]; Name
0x14001dca8  call    cs:__imp_LdrGetProcedureAddress
0x14001dcae  test    eax, eax
0x14001dcb0  js      short loc_14001DCBD
0x14001dcb2  mov     rax, [rbp+ProcedureAddress]
0x14001dcb6  mov     cs:CspControlRoutine, rax
0x14001dcbd  lea     rsi, [rdi+30h]
0x14001dcc1  mov     rcx, rsi
0x14001dcc4  call    cs:__imp_RtlAcquireSRWLockShared
0x14001dcca  add     rdi, 40h ; '@'
0x14001dcce  mov     rbx, [rdi]
0x14001dcd1  jmp     short loc_14001DD22
0x14001dcd3  mov     rcx, [rbx+18h]; ThreadContext
0x14001dcd7  test    rcx, rcx
0x14001dcda  jz      short loc_14001DD1F
0x14001dcdc  mov     rax, cs:CspControlRoutine
0x14001dce3  xor     r9d, r9d; Reserved2
0x14001dce6  mov     [rsp+70h+Reserved8], 0; Reserved8
0x14001dcef  xor     r8d, r8d; Reserved1
0x14001dcf2  mov     [rsp+70h+Reserved7], 0; Reserved7
0x14001dcfb  xor     edx, edx; OutThreadHandle
0x14001dcfd  mov     [rsp+70h+Reserved6], r14; Reserved6
0x14001dd02  mov     [rsp+70h+Reserved5], rax; Reserved5
0x14001dd07  mov     [rsp+70h+Reserved4], 0; Reserved4
0x14001dd10  mov     [rsp+70h+Reserved3], 0; Reserved3
0x14001dd19  call    cs:__imp_RtlCreateUserThread
0x14001dd1f  mov     rbx, [rbx]
0x14001dd22  cmp     rbx, rdi
0x14001dd25  jnz     short loc_14001DCD3
0x14001dd27  mov     rcx, rsi
0x14001dd2a  lea     r11, [rsp+70h+var_s0]
0x14001dd2f  mov     rbx, [r11+28h]
0x14001dd33  mov     rsi, [r11+38h]
0x14001dd37  mov     rsp, r11
0x14001dd3a  pop     r14
0x14001dd3c  pop     rdi
0x14001dd3d  pop     rbp
0x14001dd3e  jmp     cs:__imp_RtlReleaseSRWLockShared
```
