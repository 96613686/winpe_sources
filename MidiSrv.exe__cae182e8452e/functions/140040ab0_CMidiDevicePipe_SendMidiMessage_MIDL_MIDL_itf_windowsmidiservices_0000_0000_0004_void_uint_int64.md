# CMidiDevicePipe::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x140040ab0`
- end: `0x140040bad`
- name: `?SendMidiMessage@CMidiDevicePipe@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `253`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, unsigned int, __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x14000a6b4`
- `0x140040ab0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140040b6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140040b7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140040b8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140040b6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140040b7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140040b8f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140040ad5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140040ad5`

## string_xrefs

- `0x140040b51`: `avcore\midi2\service\exe\mididevicepipe.cpp`

## pseudocode

```c
__int64 __fastcall CMidiDevicePipe::SendMidiMessage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        int a5)
{
  RTL_SRWLOCK *v9; // rbx
  PVOID Ptr; // rcx
  int v11; // edi
  __int64 v12; // rdx
  PVOID v13; // rcx
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v9 = a1 + 15;
  AcquireSRWLockShared(a1 + 15);
  Ptr = a1[18].Ptr;
  if ( Ptr )
  {
    v15 = a5;
    v11 = (*(__int64 (__fastcall **)(PVOID, _QWORD, __int64, _QWORD))(*(_QWORD *)Ptr + 40LL))(Ptr, a2, a3, a4);
    if ( v11 < 0 )
    {
      v12 = 247;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
        (const char *)(unsigned int)v11,
        v15);
      if ( v9 )
        ReleaseSRWLockShared(v9);
      return (unsigned int)v11;
    }
LABEL_10:
    if ( v9 )
      ReleaseSRWLockShared(v9);
    return 0;
  }
  v13 = a1[20].Ptr;
  if ( v13 )
  {
    v15 = a5;
    v11 = (*(__int64 (__fastcall **)(PVOID, _QWORD, __int64, _QWORD))(*(_QWORD *)v13 + 40LL))(v13, a2, a3, a4);
    if ( v11 < 0 )
    {
      v12 = 254;
      goto LABEL_7;
    }
    goto LABEL_10;
  }
  if ( v9 )
    ReleaseSRWLockShared(v9);
  return 2147500036LL;
}

```

## disassembly

```asm
0x140040ab0  mov     [rsp+arg_8], rbx
0x140040ab5  mov     [rsp+arg_10], rbp
0x140040aba  push    rsi
0x140040abb  push    rdi
0x140040abc  push    r14
0x140040abe  sub     rsp, 30h
0x140040ac2  mov     esi, r9d
0x140040ac5  mov     rbp, r8
0x140040ac8  mov     r14d, edx
0x140040acb  mov     rdi, rcx
0x140040ace  lea     rbx, [rcx+78h]
0x140040ad2  mov     rcx, rbx; SRWLock
0x140040ad5  call    cs:__imp_AcquireSRWLockShared
0x140040adb  mov     [rsp+48h+arg_0], rbx
0x140040ae0  mov     rcx, [rdi+90h]
0x140040ae7  test    rcx, rcx
0x140040aea  jz      short loc_140040B18
0x140040aec  mov     rax, [rcx]
0x140040aef  mov     rdx, qword ptr [rsp+48h+arg_20]
0x140040af4  mov     qword ptr [rsp+48h+var_28], rdx
0x140040af9  mov     r9d, esi
0x140040afc  mov     r8, rbp
0x140040aff  mov     edx, r14d
0x140040b02  mov     rax, [rax+28h]
0x140040b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040b0b  mov     edi, eax
0x140040b0d  test    eax, eax
0x140040b0f  jns     short loc_140040B75
0x140040b11  mov     edx, 0F7h
0x140040b16  jmp     short loc_140040B4E
0x140040b18  mov     rcx, [rdi+0A0h]
0x140040b1f  test    rcx, rcx
0x140040b22  jz      short loc_140040B87
0x140040b24  mov     rax, [rcx]
0x140040b27  mov     rdx, qword ptr [rsp+48h+arg_20]
0x140040b2c  mov     qword ptr [rsp+48h+var_28], rdx; int
0x140040b31  mov     r9d, esi
0x140040b34  mov     r8, rbp
0x140040b37  mov     edx, r14d
0x140040b3a  mov     rax, [rax+28h]
0x140040b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040b43  mov     edi, eax
0x140040b45  test    eax, eax
0x140040b47  jns     short loc_140040B75
0x140040b49  mov     edx, 0FEh; void *
0x140040b4e  mov     r9d, edi; char *
0x140040b51  lea     r8, aAvcoreMidi2Ser_11; "avcore\\midi2\\service\\exe\\mididevice"...
0x140040b58  mov     rcx, [rsp+48h]; this
0x140040b5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040b62  nop
0x140040b63  test    rbx, rbx
0x140040b66  jz      short loc_140040B71
0x140040b68  mov     rcx, rbx; SRWLock
0x140040b6b  call    cs:__imp_ReleaseSRWLockShared
0x140040b71  mov     eax, edi
0x140040b73  jmp     short loc_140040B9A
0x140040b75  test    rbx, rbx
0x140040b78  jz      short loc_140040B83
0x140040b7a  mov     rcx, rbx; SRWLock
0x140040b7d  call    cs:__imp_ReleaseSRWLockShared
0x140040b83  xor     eax, eax
0x140040b85  jmp     short loc_140040B9A
0x140040b87  test    rbx, rbx
0x140040b8a  jz      short loc_140040B95
0x140040b8c  mov     rcx, rbx; SRWLock
0x140040b8f  call    cs:__imp_ReleaseSRWLockShared
0x140040b95  mov     eax, 80004004h
0x140040b9a  mov     rbx, [rsp+48h+arg_8]
0x140040b9f  mov     rbp, [rsp+48h+arg_10]
0x140040ba4  add     rsp, 30h
0x140040ba8  pop     r14
0x140040baa  pop     rdi
0x140040bab  pop     rsi
0x140040bac  retn
```
