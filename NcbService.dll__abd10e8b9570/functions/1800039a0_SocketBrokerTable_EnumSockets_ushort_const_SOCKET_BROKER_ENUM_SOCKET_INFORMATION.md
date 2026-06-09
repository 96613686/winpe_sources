# SocketBrokerTable::EnumSockets(ushort const *,_SOCKET_BROKER_ENUM_SOCKET_INFORMATION * *)

- ea: `0x1800039a0`
- end: `0x180003b59`
- name: `?EnumSockets@SocketBrokerTable@@QEAAKPEBGPEAPEAU_SOCKET_BROKER_ENUM_SOCKET_INFORMATION@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(SocketBrokerTable *this, const unsigned __int16 *, struct _SOCKET_BROKER_ENUM_SOCKET_INFORMATION **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018bd0`

## callees

- `0x180002a30`
- `0x180003264`
- `0x1800039a0`
- `0x180003c7c`
- `0x180003d00`
- `0x180003ed0`
- `0x18000a0a0`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x180003a73`
- `ntdll!RtlLookupEntryHashTable` at `0x180003a73`
- `ntdll!RtlGetNextEntryHashTable` at `0x180003ab1`
- `ntdll!RtlGetNextEntryHashTable` at `0x180003ab1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003a17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003a17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a2e`

## string_xrefs

- `0x180003b16`: `SocketBrokerTable: Failed to get Hash index`
- `0x180003b4b`: `SocketBrokerTable: EnumSockets failed`
- `0x180003b37`: `SocketBrokerTable: NcbUtilsMergeSocketInformation failed`

## pseudocode

```c
__int64 __fastcall SocketBrokerTable::EnumSockets(
        SocketBrokerTable *this,
        const unsigned __int16 *a2,
        struct _SOCKET_BROKER_ENUM_SOCKET_INFORMATION **a3)
{
  LPCRITICAL_SECTION v3; // rsi
  void *v4; // rdi
  char v7; // r15
  SocketBrokerTable *v8; // rcx
  unsigned int Hash; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // ebx
  SocketBrokerContext *i; // rax
  __int64 v15; // rdx
  const unsigned __int16 *v16; // rcx
  __int64 v17; // rdx
  int v18; // r9d
  int v19; // r8d
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int128 v26; // [rsp+20h] [rbp-20h] BYREF
  __int64 v27; // [rsp+30h] [rbp-10h]
  unsigned int v28; // [rsp+80h] [rbp+40h] BYREF
  int v29; // [rsp+84h] [rbp+44h]
  LPVOID lpMem; // [rsp+90h] [rbp+50h] BYREF
  struct _SOCKET_BROKER_ENUM_SOCKET_INFORMATION *v31; // [rsp+98h] [rbp+58h] BYREF

  v29 = HIDWORD(this);
  v3 = g_SocketBrokerTable;
  v28 = 0;
  v4 = 0;
  v27 = 0;
  v31 = 0;
  lpMem = 0;
  v7 = 0;
  v26 = 0;
  SocketBrokerTable::Initialize(g_SocketBrokerTable);
  *a3 = 0;
  Hash = SocketBrokerTable::GetHash(v8, a2, &v28);
  v12 = Hash;
  if ( Hash )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v11, v10, L"SocketBrokerTable: Failed to get Hash index", Hash);
  }
  else
  {
    v26 = 0;
    EnterCriticalSection(v3);
    if ( LOBYTE(v3[2].DebugInfo) )
    {
      for ( i = (SocketBrokerContext *)RtlLookupEntryHashTable(&v3[1], v28, &v26);
            i;
            i = (SocketBrokerContext *)RtlGetNextEntryHashTable(&v3[1], &v26) )
      {
        v15 = *((_QWORD *)i + 6);
        if ( v15 )
        {
          v16 = a2;
          v17 = v15 - (_QWORD)a2;
          do
          {
            v18 = *(const unsigned __int16 *)((char *)v16 + v17);
            v19 = *v16 - v18;
            if ( v19 )
              break;
            ++v16;
          }
          while ( v18 );
          if ( !v19 )
          {
            v7 = 1;
            v20 = SocketBrokerContext::EnumSockets(i, (struct _SOCKET_BROKER_ENUM_SOCKET_INFORMATION **)&lpMem);
            v12 = v20;
            if ( v20 )
            {
              if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
                McTemplateU0zq_EventWriteTransfer(v22, v21, L"SocketBrokerTable: EnumSockets failed", v20);
              v4 = lpMem;
              break;
            }
            v4 = lpMem;
            v23 = NcbUtilsMergeSocketInformation(&v31, lpMem);
            v12 = v23;
            if ( v23 )
            {
              if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
                McTemplateU0zq_EventWriteTransfer(
                  v25,
                  v24,
                  L"SocketBrokerTable: NcbUtilsMergeSocketInformation failed",
                  v23);
              break;
            }
            VpnFree(v4);
            v4 = 0;
            lpMem = 0;
          }
        }
      }
    }
    *a3 = v31;
    LeaveCriticalSection(v3);
  }
  VpnFree(v4);
  VpnFree(0);
  if ( !v7 )
    return 1168;
  return v12;
}

```

## disassembly

```asm
0x1800039a0  mov     [rsp-38h+arg_8], rbx
0x1800039a5  mov     qword ptr [rsp-38h+arg_0], rcx
0x1800039aa  push    rbp
0x1800039ab  push    rsi
0x1800039ac  push    rdi
0x1800039ad  push    r12
0x1800039af  push    r13
0x1800039b1  push    r14
0x1800039b3  push    r15
0x1800039b5  mov     rbp, rsp
0x1800039b8  sub     rsp, 40h
0x1800039bc  mov     rsi, cs:?g_SocketBrokerTable@@3PEAVSocketBrokerTable@@EA; SocketBrokerTable * g_SocketBrokerTable
0x1800039c3  xor     eax, eax
0x1800039c5  xorps   xmm0, xmm0
0x1800039c8  mov     [rbp+arg_0], 0
0x1800039cf  xor     edi, edi
0x1800039d1  mov     [rbp+var_10], rax
0x1800039d5  mov     rcx, rsi; lpCriticalSection
0x1800039d8  mov     [rbp+arg_18], rax
0x1800039dc  mov     r13, r8
0x1800039df  mov     [rbp+lpMem], rdi
0x1800039e3  mov     r12, rdx
0x1800039e6  xor     r15b, r15b
0x1800039e9  movups  [rbp+var_20], xmm0
0x1800039ed  call    ?Initialize@SocketBrokerTable@@QEAAKXZ; SocketBrokerTable::Initialize(void)
0x1800039f2  lea     r8, [rbp+arg_0]; unsigned int *
0x1800039f6  mov     [r13+0], rdi
0x1800039fa  mov     rdx, r12; unsigned __int16 *
0x1800039fd  call    ?GetHash@SocketBrokerTable@@AEAAKPEBGPEAK@Z; SocketBrokerTable::GetHash(ushort const *,ulong *)
0x180003a02  mov     ebx, eax
0x180003a04  test    eax, eax
0x180003a06  jnz     loc_180003B06
0x180003a0c  xorps   xmm0, xmm0
0x180003a0f  mov     rcx, rsi; lpCriticalSection
0x180003a12  movdqu  [rbp+var_20], xmm0
0x180003a17  call    cs:__imp_EnterCriticalSection
0x180003a1d  cmp     [rsi+50h], dil
0x180003a21  jnz     short loc_180003A68
0x180003a23  mov     rdx, [rbp+arg_18]
0x180003a27  mov     rcx, rsi; lpCriticalSection
0x180003a2a  mov     [r13+0], rdx
0x180003a2e  call    cs:__imp_LeaveCriticalSection
0x180003a34  mov     rcx, rdi; lpMem
0x180003a37  call    VpnFree
0x180003a3c  xor     ecx, ecx; lpMem
0x180003a3e  call    VpnFree
0x180003a43  mov     eax, 490h
0x180003a48  test    r15b, r15b
0x180003a4b  cmovz   ebx, eax
0x180003a4e  mov     eax, ebx
0x180003a50  mov     rbx, [rsp+40h+arg_8]
0x180003a58  add     rsp, 40h
0x180003a5c  pop     r15
0x180003a5e  pop     r14
0x180003a60  pop     r13
0x180003a62  pop     r12
0x180003a64  pop     rdi
0x180003a65  pop     rsi
0x180003a66  pop     rbp
0x180003a67  retn
0x180003a68  mov     edx, [rbp+arg_0]
0x180003a6b  lea     r8, [rbp+var_20]
0x180003a6f  lea     rcx, [rsi+28h]
0x180003a73  call    cs:__imp_RtlLookupEntryHashTable
0x180003a79  test    rax, rax
0x180003a7c  jz      short loc_180003A23
0x180003a7e  mov     rdx, [rax+30h]
0x180003a82  test    rdx, rdx
0x180003a85  jz      short loc_180003AA9
0x180003a87  mov     rcx, r12
0x180003a8a  sub     rdx, r12
0x180003a8d  movzx   r8d, word ptr [rcx]
0x180003a91  movzx   r9d, word ptr [rcx+rdx]
0x180003a96  sub     r8d, r9d
0x180003a99  jnz     short loc_180003AA4
0x180003a9b  add     rcx, 2
0x180003a9f  test    r9d, r9d
0x180003aa2  jnz     short loc_180003A8D
0x180003aa4  test    r8d, r8d
0x180003aa7  jz      short loc_180003AB9
0x180003aa9  lea     rdx, [rbp+var_20]
0x180003aad  lea     rcx, [rsi+28h]
0x180003ab1  call    cs:__imp_RtlGetNextEntryHashTable
0x180003ab7  jmp     short loc_180003A79
0x180003ab9  lea     rdx, [rbp+lpMem]; struct _SOCKET_BROKER_ENUM_SOCKET_INFORMATION **
0x180003abd  mov     rcx, rax; this
0x180003ac0  mov     r15b, 1
0x180003ac3  call    ?EnumSockets@SocketBrokerContext@@QEAAKPEAPEAU_SOCKET_BROKER_ENUM_SOCKET_INFORMATION@@@Z; SocketBrokerContext::EnumSockets(_SOCKET_BROKER_ENUM_SOCKET_INFORMATION * *)
0x180003ac8  mov     ebx, eax
0x180003aca  test    eax, eax
0x180003acc  jnz     short loc_180003AF4
0x180003ace  mov     rdi, [rbp+lpMem]
0x180003ad2  lea     rcx, [rbp+arg_18]
0x180003ad6  mov     rdx, rdi
0x180003ad9  call    NcbUtilsMergeSocketInformation
0x180003ade  mov     ebx, eax
0x180003ae0  test    eax, eax
0x180003ae2  jnz     short loc_180003B27
0x180003ae4  mov     rcx, rdi; lpMem
0x180003ae7  call    VpnFree
0x180003aec  xor     edi, edi
0x180003aee  mov     [rbp+lpMem], rdi
0x180003af2  jmp     short loc_180003AA9
0x180003af4  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, r15b
0x180003afb  jnz     short loc_180003B48
0x180003afd  mov     rdi, [rbp+lpMem]
0x180003b01  jmp     loc_180003A23
0x180003b06  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180003b0d  jz      loc_180003A34
0x180003b13  mov     r9d, eax
0x180003b16  lea     r8, aSocketbrokerta_0; "SocketBrokerTable: Failed to get Hash i"...
0x180003b1d  call    McTemplateU0zq_EventWriteTransfer
0x180003b22  jmp     loc_180003A34
0x180003b27  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, r15b
0x180003b2e  jz      loc_180003A23
0x180003b34  mov     r9d, eax
0x180003b37  lea     r8, aSocketbrokerta_1; "SocketBrokerTable: NcbUtilsMergeSocketI"...
0x180003b3e  call    McTemplateU0zq_EventWriteTransfer
0x180003b43  jmp     loc_180003A23
0x180003b48  mov     r9d, eax
0x180003b4b  lea     r8, aSocketbrokerta_3; "SocketBrokerTable: EnumSockets failed"
0x180003b52  call    McTemplateU0zq_EventWriteTransfer
0x180003b57  jmp     short loc_180003AFD
```
