# MbbUtilInternalCIDCompletion(void *,_MBB_REQUEST_CONTEXT *,int)

- ea: `0x14001f3f0`
- end: `0x14001f4e8`
- name: `?MbbUtilInternalCIDCompletion@@YAXPEAXPEAU_MBB_REQUEST_CONTEXT@@H@Z`
- size: `248`
- prototype: `void __fastcall(void *, struct _MBB_REQUEST_CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140019f78`
- `0x14001f3f0`
- `0x14002473c`
- `0x14003e100`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001f4c3`
- `ntoskrnl!KeSetEvent` at `0x14001f4c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f47a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f4a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f47a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f4a3`

## pseudocode

```c
void __fastcall MbbUtilInternalCIDCompletion(void *a1, struct _MBB_REQUEST_CONTEXT *a2, unsigned int a3)
{
  void (__fastcall *v5)(struct _MBB_REQUEST_CONTEXT *, _QWORD); // rax
  int v6; // edx
  int v7; // r8d
  void *v8; // rcx
  void *v9; // rcx

  v5 = *(void (__fastcall **)(struct _MBB_REQUEST_CONTEXT *, _QWORD))(*((_QWORD *)a2 + 10) + 80LL);
  if ( v5 )
    v5(a2, a3);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    MbbUtilGetCommandString((struct _MBB_COMMAND *)(*((_QWORD *)a2 + 10) + 48LL));
    WPP_RECORDER_SF_Dsdq(WPP_GLOBAL_Control->DeviceExtension, v6, v7, 28);
  }
  v8 = (void *)*((_QWORD *)a2 + 70);
  if ( v8 )
  {
    ExFreePoolWithTag(v8, 0);
    *((_QWORD *)a2 + 70) = 0;
  }
  if ( a3 )
  {
    v9 = (void *)*((_QWORD *)a2 + 71);
    if ( v9 )
    {
      ExFreePoolWithTag(v9, 0);
      *((_QWORD *)a2 + 71) = 0;
    }
    KeSetEvent((PRKEVENT)((char *)a2 + 56), 0, 0);
    MbbReqMgrDerefRequest(a2);
  }
}

```

## disassembly

```asm
0x14001f3f0  mov     [rsp+arg_0], rbx
0x14001f3f5  mov     [rsp+arg_8], rsi
0x14001f3fa  push    rdi
0x14001f3fb  sub     rsp, 50h
0x14001f3ff  mov     rax, [rdx+50h]
0x14001f403  mov     esi, r8d
0x14001f406  mov     rdi, rdx
0x14001f409  mov     rax, [rax+50h]
0x14001f40d  test    rax, rax
0x14001f410  jz      short loc_14001F41D
0x14001f412  mov     edx, r8d
0x14001f415  mov     rcx, rdi
0x14001f418  call    _guard_dispatch_icall
0x14001f41d  lea     rax, WPP_RECORDER_INITIALIZED
0x14001f424  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001f42b  jz      short loc_14001F46C
0x14001f42d  mov     rcx, [rdi+50h]
0x14001f431  mov     rbx, [rdi+230h]
0x14001f438  add     rcx, 30h ; '0'; Source1
0x14001f43c  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14001f441  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f448  mov     r9d, 1Ch
0x14001f44e  mov     [rsp+58h+var_18], rbx
0x14001f453  mov     [rsp+58h+var_20], esi
0x14001f457  mov     [rsp+58h+var_28], rax
0x14001f45c  mov     eax, [rdi+10h]
0x14001f45f  mov     rcx, [rcx+40h]
0x14001f463  mov     [rsp+58h+var_30], eax
0x14001f467  call    WPP_RECORDER_SF_Dsdq
0x14001f46c  mov     rcx, [rdi+230h]; P
0x14001f473  test    rcx, rcx
0x14001f476  jz      short loc_14001F491
0x14001f478  xor     edx, edx; Tag
0x14001f47a  call    cs:__imp_ExFreePoolWithTag
0x14001f481  nop     dword ptr [rax+rax+00h]
0x14001f486  mov     qword ptr [rdi+230h], 0
0x14001f491  test    esi, esi
0x14001f493  jz      short loc_14001F4D7
0x14001f495  mov     rcx, [rdi+238h]; P
0x14001f49c  test    rcx, rcx
0x14001f49f  jz      short loc_14001F4BA
0x14001f4a1  xor     edx, edx; Tag
0x14001f4a3  call    cs:__imp_ExFreePoolWithTag
0x14001f4aa  nop     dword ptr [rax+rax+00h]
0x14001f4af  mov     qword ptr [rdi+238h], 0
0x14001f4ba  lea     rcx, [rdi+38h]; Event
0x14001f4be  xor     r8d, r8d; Wait
0x14001f4c1  xor     edx, edx; Increment
0x14001f4c3  call    cs:__imp_KeSetEvent
0x14001f4ca  nop     dword ptr [rax+rax+00h]
0x14001f4cf  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x14001f4d2  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x14001f4d7  mov     rbx, [rsp+58h+arg_0]
0x14001f4dc  mov     rsi, [rsp+58h+arg_8]
0x14001f4e1  add     rsp, 50h
0x14001f4e5  pop     rdi
0x14001f4e6  retn
```
