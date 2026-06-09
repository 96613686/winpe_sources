# IEventContext::CreateInstance(IEventContext * *)

- ea: `0x1400520a8`
- end: `0x14005219e`
- name: `?CreateInstance@IEventContext@@SAHPEAPEAV1@@Z`
- size: `246`
- prototype: `__int64 __fastcall(struct IEventContext **)`
- caller_count: `11`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14002c514`
- `0x14002c7dc`
- `0x14002cb2c`
- `0x14002ce2c`
- `0x14002d0e0`
- `0x14002d3b4`
- `0x14002d660`
- `0x14002d934`
- `0x1400541b8`
- `0x140055990`
- `0x1400cd040`

## callees

- `0x140004d48`
- `0x140009420`
- `0x14000c778`
- `0x14000d054`
- `0x1400520a8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140052123`
- `ntoskrnl!KeInitializeEvent` at `0x140052123`
- `NDIS!NdisInitializeEvent` at `0x14005213c`
- `NDIS!NdisInitializeEvent` at `0x14005213c`

## pseudocode

```c
__int64 __fastcall IEventContext::CreateInstance(struct IEventContext **a1)
{
  int v2; // edx
  char *v3; // rbx
  __int64 v4; // rcx
  unsigned int v5; // edi

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      17,
      (__int64)WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids);
  }
  v3 = (char *)operator new(0x38u);
  if ( v3 )
  {
    *(_QWORD *)v3 = &CWaitEvent::`vftable';
    KeInitializeEvent((PRKEVENT)(v3 + 32), NotificationEvent, 0);
    if ( !(unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline(v4) )
      NdisInitializeEvent((PNDIS_EVENT)(v3 + 8));
    v5 = 0;
    *a1 = (struct IEventContext *)v3;
  }
  else
  {
    v5 = -1073741670;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v2) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v2,
      1,
      18,
      (__int64)WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids,
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x1400520a8  push    rbx
0x1400520aa  push    rbp
0x1400520ab  push    rsi
0x1400520ac  push    rdi
0x1400520ad  push    r12
0x1400520af  push    r14
0x1400520b1  sub     rsp, 38h
0x1400520b5  mov     rsi, rcx
0x1400520b8  lea     r14, WPP_RECORDER_INITIALIZED
0x1400520bf  xor     ebp, ebp
0x1400520c1  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400520c8  lea     r12, WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids
0x1400520cf  jz      short loc_1400520FE
0x1400520d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400520d8  cmp     byte ptr [rcx+29h], 5
0x1400520dc  jnb     short loc_1400520E4
0x1400520de  cmp     [rcx+48h], bp
0x1400520e2  jz      short loc_1400520FE
0x1400520e4  mov     rcx, [rcx+40h]
0x1400520e8  mov     r9d, 11h
0x1400520ee  mov     dl, 5
0x1400520f0  mov     [rsp+68h+var_48], r12
0x1400520f5  lea     r8d, [r9-10h]
0x1400520f9  call    WPP_RECORDER_SF_
0x1400520fe  mov     ecx, 38h ; '8'; unsigned __int64
0x140052103  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140052108  mov     rbx, rax
0x14005210b  test    rax, rax
0x14005210e  jz      short loc_14005214F
0x140052110  lea     rax, ??_7CWaitEvent@@6B@; const CWaitEvent::`vftable'
0x140052117  xor     r8d, r8d; State
0x14005211a  lea     rcx, [rbx+20h]; Event
0x14005211e  mov     [rbx], rax
0x140052121  xor     edx, edx; Type
0x140052123  call    cs:__imp_KeInitializeEvent
0x14005212a  nop     dword ptr [rax+rax+00h]
0x14005212f  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x140052134  test    eax, eax
0x140052136  jnz     short loc_140052148
0x140052138  lea     rcx, [rbx+8]; Event
0x14005213c  call    cs:__imp_NdisInitializeEvent
0x140052143  nop     dword ptr [rax+rax+00h]
0x140052148  mov     edi, ebp
0x14005214a  mov     [rsi], rbx
0x14005214d  jmp     short loc_140052154
0x14005214f  mov     edi, 0C000009Ah
0x140052154  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005215b  jz      short loc_14005218E
0x14005215d  mov     rcx, cs:WPP_GLOBAL_Control
0x140052164  cmp     byte ptr [rcx+29h], 5
0x140052168  jnb     short loc_140052170
0x14005216a  cmp     [rcx+48h], bp
0x14005216e  jz      short loc_14005218E
0x140052170  mov     rcx, [rcx+40h]
0x140052174  mov     r9d, 12h
0x14005217a  mov     [rsp+68h+var_40], edi
0x14005217e  mov     dl, 5
0x140052180  mov     [rsp+68h+var_48], r12
0x140052185  lea     r8d, [r9-11h]
0x140052189  call    WPP_RECORDER_SF_d
0x14005218e  mov     eax, edi
0x140052190  add     rsp, 38h
0x140052194  pop     r14
0x140052196  pop     r12
0x140052198  pop     rdi
0x140052199  pop     rsi
0x14005219a  pop     rbp
0x14005219b  pop     rbx
0x14005219c  retn
```
