# Broker::BILayer::NotificationChannel::UnpackUserSid(unsigned __int64,void const *,void * &)

- ea: `0x180011658`
- end: `0x180011680`
- name: `?UnpackUserSid@NotificationChannel@BILayer@Broker@@CAX_KPEBXAEAPEAX@Z`
- size: `40`
- prototype: `static void(unsigned __int64, const void *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a584`

## callees

- `0x180011658`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180011667`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180011667`

## pseudocode

```c
void __fastcall Broker::BILayer::NotificationChannel::UnpackUserSid(__int64 a1, void *a2, void **a3)
{
  *a3 = a2;
  if ( !IsValidSid(a2) )
    *a3 = 0;
}

```

## disassembly

```asm
0x180011658  push    rbx
0x18001165a  sub     rsp, 20h
0x18001165e  mov     rcx, rdx; pSid
0x180011661  mov     [r8], rdx
0x180011664  mov     rbx, r8
0x180011667  call    cs:__imp_IsValidSid
0x18001166d  test    eax, eax
0x18001166f  jz      short loc_180011677
0x180011671  add     rsp, 20h
0x180011675  pop     rbx
0x180011676  retn
0x180011677  mov     qword ptr [rbx], 0
0x18001167e  jmp     short loc_180011671
```
