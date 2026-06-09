# SocketBrokerTable::Remove(_GUID *,ushort const *,SocketBrokerContext *)

- ea: `0x18002688c`
- end: `0x18002693a`
- name: `?Remove@SocketBrokerTable@@QEAAKPEAU_GUID@@PEBGPEAVSocketBrokerContext@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct _GUID *, const unsigned __int16 *, struct SocketBrokerContext *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800261d8`
- `0x180028250`

## callees

- `0x180001ebc`
- `0x180003b60`
- `0x18000a0a0`
- `0x180017804`
- `0x18002688c`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180026908`
- `ntdll!RtlRemoveEntryHashTable` at `0x180026908`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800268ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800268ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026929`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026929`

## string_xrefs

- `0x1800268d3`: `SocketBrokerTable: Remove: Object is not in hash table`

## pseudocode

```c
__int64 __fastcall SocketBrokerTable::Remove(
        LPCRITICAL_SECTION lpCriticalSection,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        struct SocketBrokerContext *a4)
{
  struct _GUID *v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int v11; // esi
  __int64 v12; // r9
  SocketBrokerContext *v13; // rbx
  SocketBrokerContext *v15; // [rsp+58h] [rbp+10h] BYREF

  v15 = 0;
  EnterCriticalSection(lpCriticalSection);
  v8 = SocketBrokerTable::Find(lpCriticalSection, v7, a3, &v15);
  v11 = v8;
  if ( v8 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v12 = v8;
LABEL_4:
      McTemplateU0zq_EventWriteTransfer(v10, v9, L"SocketBrokerTable: Remove: Object is not in hash table", v12);
    }
  }
  else
  {
    v13 = v15;
    if ( !a4 || a4 == v15 )
    {
      RtlRemoveEntryHashTable(&lpCriticalSection[1], v15, 0);
      SocketBrokerContext::CleanupSockets(v13);
      SocketBrokerContext::ReleaseRef(v13);
      SocketBrokerContext::ReleaseRef(v13);
      goto LABEL_10;
    }
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v12 = 0;
      goto LABEL_4;
    }
  }
LABEL_10:
  LeaveCriticalSection(lpCriticalSection);
  return v11;
}

```

## disassembly

```asm
0x18002688c  mov     [rsp+arg_8], rdx
0x180026891  push    rbx
0x180026892  push    rbp
0x180026893  push    rsi
0x180026894  push    rdi
0x180026895  sub     rsp, 28h
0x180026899  mov     rbp, r9
0x18002689c  mov     [rsp+48h+arg_8], 0
0x1800268a5  mov     rbx, r8
0x1800268a8  mov     rdi, rcx
0x1800268ab  call    cs:__imp_EnterCriticalSection
0x1800268b1  lea     r9, [rsp+48h+arg_8]; struct SocketBrokerContext **
0x1800268b6  mov     r8, rbx; unsigned __int16 *
0x1800268b9  mov     rcx, rdi; lpCriticalSection
0x1800268bc  call    ?Find@SocketBrokerTable@@QEAAKPEAU_GUID@@PEBGPEAPEAVSocketBrokerContext@@@Z; SocketBrokerTable::Find(_GUID *,ushort const *,SocketBrokerContext * *)
0x1800268c1  mov     esi, eax
0x1800268c3  test    eax, eax
0x1800268c5  jz      short loc_1800268E1
0x1800268c7  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800268ce  jz      short loc_180026926
0x1800268d0  mov     r9d, eax
0x1800268d3  lea     r8, aSocketbrokerta_4; "SocketBrokerTable: Remove: Object is no"...
0x1800268da  call    McTemplateU0zq_EventWriteTransfer
0x1800268df  jmp     short loc_180026926
0x1800268e1  mov     rbx, [rsp+48h+arg_8]
0x1800268e6  test    rbp, rbp
0x1800268e9  jz      short loc_1800268FE
0x1800268eb  cmp     rbp, rbx
0x1800268ee  jz      short loc_1800268FE
0x1800268f0  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800268f7  jz      short loc_180026926
0x1800268f9  xor     r9d, r9d
0x1800268fc  jmp     short loc_1800268D3
0x1800268fe  lea     rcx, [rdi+28h]
0x180026902  xor     r8d, r8d
0x180026905  mov     rdx, rbx
0x180026908  call    cs:__imp_RtlRemoveEntryHashTable
0x18002690e  mov     rcx, rbx; this
0x180026911  call    ?CleanupSockets@SocketBrokerContext@@QEAAXXZ; SocketBrokerContext::CleanupSockets(void)
0x180026916  mov     rcx, rbx; this
0x180026919  call    ?ReleaseRef@SocketBrokerContext@@QEAAXXZ; SocketBrokerContext::ReleaseRef(void)
0x18002691e  mov     rcx, rbx; this
0x180026921  call    ?ReleaseRef@SocketBrokerContext@@QEAAXXZ; SocketBrokerContext::ReleaseRef(void)
0x180026926  mov     rcx, rdi; lpCriticalSection
0x180026929  call    cs:__imp_LeaveCriticalSection
0x18002692f  mov     eax, esi
0x180026931  add     rsp, 28h
0x180026935  pop     rdi
0x180026936  pop     rsi
0x180026937  pop     rbp
0x180026938  pop     rbx
0x180026939  retn
```
