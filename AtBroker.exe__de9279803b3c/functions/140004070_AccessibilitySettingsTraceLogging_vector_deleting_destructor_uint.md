# AccessibilitySettingsTraceLogging::`vector deleting destructor'(uint)

- ea: `0x140004070`
- end: `0x1400040c0`
- name: `??_EAccessibilitySettingsTraceLogging@@UEAAPEAXI@Z`
- size: `80`
- prototype: `AccessibilitySettingsTraceLogging *__fastcall(AccessibilitySettingsTraceLogging *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x140001e44`
- `0x140004070`

## import_xrefs

- `ADVAPI32!EventUnregister` at `0x14000409e`
- `ADVAPI32!EventUnregister` at `0x14000409e`

## pseudocode

```c
AccessibilitySettingsTraceLogging *__fastcall AccessibilitySettingsTraceLogging::`vector deleting destructor'(
        AccessibilitySettingsTraceLogging *this,
        char a2)
{
  __int64 v4; // rax
  REGHANDLE v5; // rcx

  *(_QWORD *)this = &wil::details::FeatureLogging::`vftable';
  if ( *((_BYTE *)this + 16) )
  {
    v4 = *((_QWORD *)this + 1);
    v5 = *(_QWORD *)(v4 + 32);
    *(_DWORD *)v4 = 0;
    *(_QWORD *)(v4 + 32) = 0;
    EventUnregister(v5);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140004070  mov     [rsp+arg_0], rbx
0x140004075  push    rdi
0x140004076  sub     rsp, 20h
0x14000407a  mov     edi, edx
0x14000407c  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x140004083  xor     edx, edx
0x140004085  mov     [rcx], rax
0x140004088  mov     rbx, rcx
0x14000408b  cmp     [rcx+10h], dl
0x14000408e  jz      short loc_1400040A4
0x140004090  mov     rax, [rcx+8]
0x140004094  mov     rcx, [rax+20h]; RegHandle
0x140004098  mov     [rax], edx
0x14000409a  mov     [rax+20h], rdx
0x14000409e  call    cs:__imp_EventUnregister
0x1400040a4  test    dil, 1
0x1400040a8  jz      short loc_1400040B2
0x1400040aa  mov     rcx, rbx; Block
0x1400040ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400040b2  mov     rax, rbx
0x1400040b5  mov     rbx, [rsp+28h+arg_0]
0x1400040ba  add     rsp, 20h
0x1400040be  pop     rdi
0x1400040bf  retn
```
