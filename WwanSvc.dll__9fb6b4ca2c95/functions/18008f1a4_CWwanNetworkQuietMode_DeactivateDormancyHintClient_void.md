# CWwanNetworkQuietMode::DeactivateDormancyHintClient(void)

- ea: `0x18008f1a4`
- end: `0x18008f25c`
- name: `?DeactivateDormancyHintClient@CWwanNetworkQuietMode@@AEAAKXZ`
- size: `184`
- prototype: `unsigned int __fastcall(CWwanNetworkQuietMode *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180040c78`
- `0x18008f330`

## callees

- `0x180012300`
- `0x180014f1c`
- `0x18008f1a4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18008f200`
- `ntdll!RtlNtStatusToDosError` at `0x18008f200`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x18008f1f8`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x18008f1f8`
- `MobileNetworking!AcquireWriteLock` at `0x18008f1cd`
- `MobileNetworking!AcquireWriteLock` at `0x18008f1cd`
- `MobileNetworking!ReleaseWriteLock` at `0x18008f244`
- `MobileNetworking!ReleaseWriteLock` at `0x18008f244`

## pseudocode

```c
__int64 __fastcall CWwanNetworkQuietMode::DeactivateDormancyHintClient(CWwanNetworkQuietMode *this)
{
  ULONG v2; // edi
  NTSTATUS v3; // eax
  ULONG v4; // eax

  v2 = 0;
  AcquireWriteLock(
    *((_QWORD *)this + 15),
    (char *)this + 16,
    "CWwanNetworkQuietMode::DeactivateDormancyHintClient",
    308);
  if ( *((_QWORD *)this + 18) )
  {
    WwanLog::Info("CWwanNetworkQuietMode::DeactivateDormancyHintClient", 0, L"Deactivate WwanDormancyHint");
    v3 = Pdcv2ActivationClientDeactivate(*((_QWORD *)this + 18));
    v4 = RtlNtStatusToDosError(v3);
    v2 = v4;
    if ( v4 )
      WwanLog::Error("CWwanNetworkQuietMode::DeactivateDormancyHintClient", 0, L"Failed to release PDC ref, [0x%x]", v4);
    *((_QWORD *)this + 18) = 0;
  }
  ReleaseWriteLock(
    *((_QWORD *)this + 15),
    (char *)this + 16,
    "CWwanNetworkQuietMode::DeactivateDormancyHintClient",
    319);
  return v2;
}

```

## disassembly

```asm
0x18008f1a4  mov     [rsp+arg_0], rbx
0x18008f1a9  mov     [rsp+arg_8], rsi
0x18008f1ae  push    rdi
0x18008f1af  sub     rsp, 20h
0x18008f1b3  mov     rbx, rcx
0x18008f1b6  lea     rdx, [rcx+10h]
0x18008f1ba  mov     rcx, [rcx+78h]
0x18008f1be  lea     r8, aCwwannetworkqu_3; "CWwanNetworkQuietMode::DeactivateDorman"...
0x18008f1c5  mov     r9d, 134h
0x18008f1cb  xor     edi, edi
0x18008f1cd  call    cs:__imp_AcquireWriteLock
0x18008f1d3  cmp     [rbx+90h], rdi
0x18008f1da  jz      short loc_18008F22F
0x18008f1dc  lea     r8, aDeactivateWwan; "Deactivate WwanDormancyHint"
0x18008f1e3  xor     edx, edx; struct _GUID *
0x18008f1e5  lea     rcx, aCwwannetworkqu_3; "CWwanNetworkQuietMode::DeactivateDorman"...
0x18008f1ec  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18008f1f1  mov     rcx, [rbx+90h]
0x18008f1f8  call    cs:__imp_Pdcv2ActivationClientDeactivate
0x18008f1fe  mov     ecx, eax; Status
0x18008f200  call    cs:__imp_RtlNtStatusToDosError
0x18008f206  mov     edi, eax
0x18008f208  test    eax, eax
0x18008f20a  jz      short loc_18008F224
0x18008f20c  mov     r9d, eax
0x18008f20f  lea     r8, aFailedToReleas; "Failed to release PDC ref, [0x%x]"
0x18008f216  xor     edx, edx; struct _GUID *
0x18008f218  lea     rcx, aCwwannetworkqu_3; "CWwanNetworkQuietMode::DeactivateDorman"...
0x18008f21f  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18008f224  mov     qword ptr [rbx+90h], 0
0x18008f22f  mov     rcx, [rbx+78h]
0x18008f233  lea     r8, aCwwannetworkqu_3; "CWwanNetworkQuietMode::DeactivateDorman"...
0x18008f23a  mov     r9d, 13Fh
0x18008f240  lea     rdx, [rbx+10h]
0x18008f244  call    cs:__imp_ReleaseWriteLock
0x18008f24a  mov     rbx, [rsp+28h+arg_0]
0x18008f24f  mov     eax, edi
0x18008f251  mov     rsi, [rsp+28h+arg_8]
0x18008f256  add     rsp, 20h
0x18008f25a  pop     rdi
0x18008f25b  retn
```
