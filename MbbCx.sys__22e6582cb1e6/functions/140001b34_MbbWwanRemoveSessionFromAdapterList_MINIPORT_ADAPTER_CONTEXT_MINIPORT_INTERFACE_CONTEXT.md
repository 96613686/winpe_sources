# MbbWwanRemoveSessionFromAdapterList(_MINIPORT_ADAPTER_CONTEXT *,_MINIPORT_INTERFACE_CONTEXT *)

- ea: `0x140001b34`
- end: `0x140001cac`
- name: `?MbbWwanRemoveSessionFromAdapterList@@YA_NPEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_MINIPORT_INTERFACE_CONTEXT@@@Z`
- size: `376`
- prototype: `bool __fastcall(PKSPIN_LOCK SpinLock, struct _MINIPORT_INTERFACE_CONTEXT *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400099cc`
- `0x14000ca94`
- `0x1400212ec`

## callees

- `0x140001008`
- `0x1400018f0`
- `0x140001b34`
- `0x140001db8`
- `0x140001ea4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140001c3e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001c3e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001b4c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001b4c`

## string_xrefs

- `0x140001c64`: `RemoveSessionFromAdapterList`

## pseudocode

```c
char __fastcall MbbWwanRemoveSessionFromAdapterList(KSPIN_LOCK *SpinLock, struct _MINIPORT_INTERFACE_CONTEXT *a2)
{
  char v4; // si
  unsigned int v5; // edx
  KSPIN_LOCK v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int v11; // [rsp+40h] [rbp+8h] BYREF
  const wchar_t *v12; // [rsp+50h] [rbp+18h] BYREF

  v4 = 0;
  *((_BYTE *)SpinLock + 8) = KeAcquireSpinLockRaiseToDpc(SpinLock);
  if ( a2 && (v5 = *((_DWORD *)a2 + 17), v5 < *((_DWORD *)SpinLock + 10)) )
  {
    v6 = SpinLock[143];
    if ( *(struct _MINIPORT_INTERFACE_CONTEXT **)(v6 + 16LL * v5) == a2
      && *(_BYTE *)(v6 + 16LL * v5 + 8)
      && *((_DWORD *)SpinLock + 284) )
    {
      *(_QWORD *)(v6 + 16LL * v5) = 0;
      *(_BYTE *)(SpinLock[143] + 16LL * *((unsigned int *)a2 + 17) + 8) = 0;
      v4 = 1;
      *((_DWORD *)a2 + 17) = 256;
      --*((_DWORD *)SpinLock + 284);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        11,
        10,
        (__int64)WPP_3e743e9cf306369b6f01400f328c7e6b_Traceguids,
        *((_DWORD *)a2 + 17));
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_i(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      11,
      11,
      (__int64)WPP_3e743e9cf306369b6f01400f328c7e6b_Traceguids,
      (char)a2);
  }
  KeReleaseSpinLock(SpinLock, *((_BYTE *)SpinLock + 8));
  if ( v4 )
  {
    DereferenceSession(a2);
  }
  else if ( (unsigned int)dword_14005E0C8 > 5 )
  {
    v11 = -1071448043;
    v12 = L"RemoveSessionFromAdapterList";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v7,
      (__int64)byte_140058411,
      v8,
      v9,
      (__int64)&v11,
      &v12);
  }
  return v4;
}

```

## disassembly

```asm
0x140001b34  mov     [rsp+arg_8], rbx
0x140001b39  mov     [rsp+arg_18], rsi
0x140001b3e  push    rdi
0x140001b3f  sub     rsp, 30h
0x140001b43  mov     rdi, rdx
0x140001b46  mov     rbx, rcx
0x140001b49  xor     sil, sil
0x140001b4c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001b53  nop     dword ptr [rax+rax+00h]
0x140001b58  mov     [rbx+8], al
0x140001b5b  test    rdi, rdi
0x140001b5e  jz      loc_140001BFC
0x140001b64  mov     edx, [rdi+44h]
0x140001b67  cmp     edx, [rbx+28h]
0x140001b6a  jnb     loc_140001BFC
0x140001b70  mov     rcx, [rbx+478h]
0x140001b77  mov     eax, edx
0x140001b79  add     rax, rax
0x140001b7c  cmp     [rcx+rax*8], rdi
0x140001b80  jnz     short loc_140001BBE
0x140001b82  cmp     [rcx+rax*8+8], sil
0x140001b87  jz      short loc_140001BBE
0x140001b89  cmp     dword ptr [rbx+470h], 0
0x140001b90  jz      short loc_140001BBE
0x140001b92  mov     qword ptr [rcx+rax*8], 0
0x140001b9a  mov     ecx, [rdi+44h]
0x140001b9d  mov     rax, [rbx+478h]
0x140001ba4  add     rcx, rcx
0x140001ba7  mov     [rax+rcx*8+8], sil
0x140001bac  mov     sil, 1
0x140001baf  mov     dword ptr [rdi+44h], 100h
0x140001bb6  dec     dword ptr [rbx+470h]
0x140001bbc  jmp     short loc_140001C38
0x140001bbe  lea     rax, WPP_RECORDER_INITIALIZED
0x140001bc5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001bcc  jz      short loc_140001C38
0x140001bce  mov     rcx, cs:WPP_GLOBAL_Control
0x140001bd5  lea     rax, WPP_3e743e9cf306369b6f01400f328c7e6b_Traceguids
0x140001bdc  mov     dword ptr [rsp+38h+var_10], edx
0x140001be0  mov     r9d, 0Ah
0x140001be6  mov     dl, 2
0x140001be8  mov     [rsp+38h+var_18], rax
0x140001bed  mov     rcx, [rcx+40h]
0x140001bf1  lea     r8d, [r9+1]
0x140001bf5  call    WPP_RECORDER_SF_d
0x140001bfa  jmp     short loc_140001C38
0x140001bfc  lea     rax, WPP_RECORDER_INITIALIZED
0x140001c03  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001c0a  jz      short loc_140001C38
0x140001c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c13  lea     rax, WPP_3e743e9cf306369b6f01400f328c7e6b_Traceguids
0x140001c1a  mov     r8d, 0Bh
0x140001c20  mov     [rsp+38h+var_10], rdi
0x140001c25  mov     r9d, r8d
0x140001c28  mov     [rsp+38h+var_18], rax
0x140001c2d  mov     dl, 2
0x140001c2f  mov     rcx, [rcx+40h]
0x140001c33  call    WPP_RECORDER_SF_i
0x140001c38  mov     dl, [rbx+8]; NewIrql
0x140001c3b  mov     rcx, rbx; SpinLock
0x140001c3e  call    cs:__imp_KeReleaseSpinLock
0x140001c45  nop     dword ptr [rax+rax+00h]
0x140001c4a  test    sil, sil
0x140001c4d  jz      short loc_140001C59
0x140001c4f  mov     rcx, rdi; struct _MINIPORT_INTERFACE_CONTEXT *
0x140001c52  call    ?DereferenceSession@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@@Z; DereferenceSession(_MINIPORT_INTERFACE_CONTEXT *)
0x140001c57  jmp     short loc_140001C98
0x140001c59  mov     eax, cs:dword_14005E0C8
0x140001c5f  cmp     eax, 5
0x140001c62  jbe     short loc_140001C98
0x140001c64  lea     rax, aRemovesessionf; "RemoveSessionFromAdapterList"
0x140001c6b  mov     [rsp+38h+arg_0], 0C0230015h
0x140001c73  mov     [rsp+38h+arg_10], rax
0x140001c78  lea     rdx, byte_140058411
0x140001c7f  lea     rax, [rsp+38h+arg_10]
0x140001c84  mov     [rsp+38h+var_10], rax
0x140001c89  lea     rax, [rsp+38h+arg_0]
0x140001c8e  mov     [rsp+38h+var_18], rax
0x140001c93  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x140001c98  mov     rbx, [rsp+38h+arg_8]
0x140001c9d  mov     al, sil
0x140001ca0  mov     rsi, [rsp+38h+arg_18]
0x140001ca5  add     rsp, 30h
0x140001ca9  pop     rdi
0x140001caa  retn
```
