# Broker::BILayer::WnfNotification::~WnfNotification(void)

- ea: `0x180019960`
- end: `0x1800199e2`
- name: `??1WnfNotification@BILayer@Broker@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(Broker::BILayer::WnfNotification *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800165a0`

## callees

- `0x180003800`
- `0x180019960`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180019980`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180019980`

## pseudocode

```c
void __fastcall Broker::BILayer::WnfNotification::~WnfNotification(Broker::BILayer::WnfNotification *this)
{
  PPEB_LDR_DATA Ldr; // rdx
  int v3; // eax
  char *v4; // rcx
  char *v5; // rbx

  Ldr = NtCurrentPeb()->Ldr;
  if ( !Ldr->ShutdownInProgress )
  {
    v3 = RtlUnsubscribeWnfNotificationWaitForCompletion(*((_QWORD *)this + 1));
    if ( v3 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids,
        (unsigned int)v3);
  }
  v4 = (char *)*((_QWORD *)this + 9);
  v5 = (char *)this + 16;
  if ( v4 )
  {
    LOBYTE(Ldr) = v4 != v5;
    (*(void (__fastcall **)(char *, PPEB_LDR_DATA))(*(_QWORD *)v4 + 32LL))(v4, Ldr);
    *((_QWORD *)v5 + 7) = 0;
  }
}

```

## disassembly

```asm
0x180019960  push    rbx
0x180019962  sub     rsp, 20h
0x180019966  mov     rax, gs:60h
0x18001996f  mov     rbx, rcx
0x180019972  mov     rdx, [rax+18h]
0x180019976  cmp     byte ptr [rdx+48h], 0
0x18001997a  jnz     short loc_1800199B5
0x18001997c  mov     rcx, [rcx+8]
0x180019980  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180019986  test    eax, eax
0x180019988  jns     short loc_1800199B5
0x18001998a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019991  test    byte ptr [rcx+1Ch], 1
0x180019995  jz      short loc_1800199B5
0x180019997  cmp     byte ptr [rcx+19h], 2
0x18001999b  jb      short loc_1800199B5
0x18001999d  mov     rcx, [rcx+10h]
0x1800199a1  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x1800199a8  mov     edx, 27h ; '''
0x1800199ad  mov     r9d, eax
0x1800199b0  call    WPP_SF_d
0x1800199b5  mov     rcx, [rbx+48h]
0x1800199b9  add     rbx, 10h
0x1800199bd  test    rcx, rcx
0x1800199c0  jz      short loc_1800199DC
0x1800199c2  mov     rax, [rcx]
0x1800199c5  cmp     rcx, rbx
0x1800199c8  setnz   dl
0x1800199cb  mov     rax, [rax+20h]
0x1800199cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199d4  mov     qword ptr [rbx+38h], 0
0x1800199dc  add     rsp, 20h
0x1800199e0  pop     rbx
0x1800199e1  retn
```
