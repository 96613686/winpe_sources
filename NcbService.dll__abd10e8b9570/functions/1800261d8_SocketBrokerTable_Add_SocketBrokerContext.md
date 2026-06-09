# SocketBrokerTable::Add(SocketBrokerContext *)

- ea: `0x1800261d8`
- end: `0x1800262b7`
- name: `?Add@SocketBrokerTable@@QEAAKPEAVSocketBrokerContext@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(SocketBrokerTable *this, struct SocketBrokerContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180026374`

## callees

- `0x180001ebc`
- `0x180003b60`
- `0x180003d00`
- `0x18000a0a0`
- `0x1800261d8`
- `0x18002688c`

## import_xrefs

- `ntdll!RtlInsertEntryHashTable` at `0x180026295`
- `ntdll!RtlInsertEntryHashTable` at `0x180026295`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026280`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800262a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800262a2`

## string_xrefs

- `0x18002625a`: `SocketBrokerTable: Failed to get Hash index`
- `0x18002626c`: `SocketBrokerTable: Add: Object allready exists`

## pseudocode

```c
__int64 __fastcall SocketBrokerTable::Add(SocketBrokerTable *this, struct SocketBrokerContext *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  const unsigned __int16 *v3; // r8
  unsigned int Hash; // eax
  struct _GUID *v6; // rdx
  SocketBrokerTable *v7; // rcx
  unsigned int v8; // ebx
  SocketBrokerContext *v9; // rdi
  const wchar_t *v10; // r8
  SocketBrokerTable *v12; // [rsp+40h] [rbp+8h] BYREF
  SocketBrokerContext *v13; // [rsp+48h] [rbp+10h] BYREF

  v12 = this;
  v2 = g_SocketBrokerTable;
  v3 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
  v13 = 0;
  LODWORD(v12) = 0;
  Hash = SocketBrokerTable::Find(g_SocketBrokerTable, (struct _GUID *)a2, v3, &v13);
  v8 = Hash;
  if ( Hash == 1168 )
  {
LABEL_4:
    Hash = SocketBrokerTable::GetHash(v7, *((const unsigned __int16 **)a2 + 6), (unsigned int *)&v12);
    v8 = Hash;
    if ( !Hash )
    {
      EnterCriticalSection(v2);
      RtlInsertEntryHashTable(&v2[1], a2, (unsigned int)v12, 0);
      _InterlockedIncrement((volatile signed __int32 *)a2 + 6);
      LeaveCriticalSection(v2);
      return v8;
    }
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v10 = L"SocketBrokerTable: Failed to get Hash index";
LABEL_9:
      McTemplateU0zq_EventWriteTransfer(v7, v6, v10, Hash);
      return v8;
    }
    return v8;
  }
  v9 = v13;
  if ( v13 )
  {
    SocketBrokerTable::Remove(v2, v6, *((const unsigned __int16 **)v13 + 6), v13);
    SocketBrokerContext::ReleaseRef(v9);
    goto LABEL_4;
  }
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v10 = L"SocketBrokerTable: Add: Object allready exists";
    goto LABEL_9;
  }
  return v8;
}

```

## disassembly

```asm
0x1800261d8  mov     rax, rsp
0x1800261db  mov     [rax+18h], rbx
0x1800261df  mov     [rax+8], rcx
0x1800261e3  push    rbp
0x1800261e4  push    rsi
0x1800261e5  push    rdi
0x1800261e6  sub     rsp, 20h
0x1800261ea  mov     rbp, cs:?g_SocketBrokerTable@@3PEAVSocketBrokerTable@@EA; SocketBrokerTable * g_SocketBrokerTable
0x1800261f1  lea     r9, [rax+10h]; struct SocketBrokerContext **
0x1800261f5  mov     r8, [rdx+30h]; unsigned __int16 *
0x1800261f9  mov     rcx, rbp; lpCriticalSection
0x1800261fc  mov     rsi, rdx
0x1800261ff  mov     qword ptr [rax+10h], 0
0x180026207  mov     dword ptr [rax+8], 0
0x18002620e  call    ?Find@SocketBrokerTable@@QEAAKPEAU_GUID@@PEBGPEAPEAVSocketBrokerContext@@@Z; SocketBrokerTable::Find(_GUID *,ushort const *,SocketBrokerContext * *)
0x180026213  mov     ebx, eax
0x180026215  cmp     eax, 490h
0x18002621a  jz      short loc_18002623D
0x18002621c  mov     rdi, [rsp+38h+arg_8]
0x180026221  test    rdi, rdi
0x180026224  jz      short loc_180026263
0x180026226  mov     r8, [rdi+30h]; unsigned __int16 *
0x18002622a  mov     r9, rdi; struct SocketBrokerContext *
0x18002622d  mov     rcx, rbp; lpCriticalSection
0x180026230  call    ?Remove@SocketBrokerTable@@QEAAKPEAU_GUID@@PEBGPEAVSocketBrokerContext@@@Z; SocketBrokerTable::Remove(_GUID *,ushort const *,SocketBrokerContext *)
0x180026235  mov     rcx, rdi; this
0x180026238  call    ?ReleaseRef@SocketBrokerContext@@QEAAXXZ; SocketBrokerContext::ReleaseRef(void)
0x18002623d  mov     rdx, [rsi+30h]; unsigned __int16 *
0x180026241  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x180026246  call    ?GetHash@SocketBrokerTable@@AEAAKPEBGPEAK@Z; SocketBrokerTable::GetHash(ushort const *,ulong *)
0x18002624b  mov     ebx, eax
0x18002624d  test    eax, eax
0x18002624f  jz      short loc_18002627D
0x180026251  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180026258  jz      short loc_1800262A8
0x18002625a  lea     r8, aSocketbrokerta_0; "SocketBrokerTable: Failed to get Hash i"...
0x180026261  jmp     short loc_180026273
0x180026263  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18002626a  jz      short loc_1800262A8
0x18002626c  lea     r8, aSocketbrokerta_2; "SocketBrokerTable: Add: Object allready"...
0x180026273  mov     r9d, eax
0x180026276  call    McTemplateU0zq_EventWriteTransfer
0x18002627b  jmp     short loc_1800262A8
0x18002627d  mov     rcx, rbp; lpCriticalSection
0x180026280  call    cs:__imp_EnterCriticalSection
0x180026286  mov     r8d, dword ptr [rsp+38h+arg_0]
0x18002628b  lea     rcx, [rbp+28h]
0x18002628f  xor     r9d, r9d
0x180026292  mov     rdx, rsi
0x180026295  call    cs:__imp_RtlInsertEntryHashTable
0x18002629b  lock inc dword ptr [rsi+18h]
0x18002629f  mov     rcx, rbp; lpCriticalSection
0x1800262a2  call    cs:__imp_LeaveCriticalSection
0x1800262a8  mov     eax, ebx
0x1800262aa  mov     rbx, [rsp+38h+arg_10]
0x1800262af  add     rsp, 20h
0x1800262b3  pop     rdi
0x1800262b4  pop     rsi
0x1800262b5  pop     rbp
0x1800262b6  retn
```
