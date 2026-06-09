# Broker::BILayer::WnfNotification::~WnfNotification(void)

- ea: `0x180011ad0`
- end: `0x180011b52`
- name: `??1WnfNotification@BILayer@Broker@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(Broker::BILayer::WnfNotification *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a6d0`

## callees

- `0x180009e94`
- `0x180011ad0`
- `0x18001e010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180011af0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180011af0`

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
        &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids,
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
0x180011ad0  push    rbx
0x180011ad2  sub     rsp, 20h
0x180011ad6  mov     rax, gs:60h
0x180011adf  mov     rbx, rcx
0x180011ae2  mov     rdx, [rax+18h]
0x180011ae6  cmp     byte ptr [rdx+48h], 0
0x180011aea  jnz     short loc_180011B25
0x180011aec  mov     rcx, [rcx+8]
0x180011af0  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180011af6  test    eax, eax
0x180011af8  jns     short loc_180011B25
0x180011afa  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b01  test    byte ptr [rcx+1Ch], 1
0x180011b05  jz      short loc_180011B25
0x180011b07  cmp     byte ptr [rcx+19h], 2
0x180011b0b  jb      short loc_180011B25
0x180011b0d  mov     rcx, [rcx+10h]
0x180011b11  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids
0x180011b18  mov     edx, 27h ; '''
0x180011b1d  mov     r9d, eax
0x180011b20  call    WPP_SF_d
0x180011b25  mov     rcx, [rbx+48h]
0x180011b29  add     rbx, 10h
0x180011b2d  test    rcx, rcx
0x180011b30  jz      short loc_180011B4C
0x180011b32  mov     rax, [rcx]
0x180011b35  cmp     rcx, rbx
0x180011b38  setnz   dl
0x180011b3b  mov     rax, [rax+20h]
0x180011b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b44  mov     qword ptr [rbx+38h], 0
0x180011b4c  add     rsp, 20h
0x180011b50  pop     rbx
0x180011b51  retn
```
