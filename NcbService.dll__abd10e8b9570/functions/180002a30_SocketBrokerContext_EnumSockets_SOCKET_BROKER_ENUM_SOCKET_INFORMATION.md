# SocketBrokerContext::EnumSockets(_SOCKET_BROKER_ENUM_SOCKET_INFORMATION * *)

- ea: `0x180002a30`
- end: `0x180002bc1`
- name: `?EnumSockets@SocketBrokerContext@@QEAAKPEAPEAU_SOCKET_BROKER_ENUM_SOCKET_INFORMATION@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(SocketBrokerContext *this, struct _SOCKET_BROKER_ENUM_SOCKET_INFORMATION **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800039a0`

## callees

- `0x180002a30`
- `0x180002bc8`
- `0x1800031cc`
- `0x180003ed0`
- `0x18000a0a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b6e`

## string_xrefs

- `0x180002b9f`: `EnumSocketsEnumSockets: failed to create SOCKET_BROKER_ENUM_SOCKET_INFORMATION`
- `0x180002bb0`: `EnumSocketsEnumSockets: SocketId copy failed`

## pseudocode

```c
__int64 __fastcall SocketBrokerContext::EnumSockets(
        SocketBrokerContext *this,
        struct _SOCKET_BROKER_ENUM_SOCKET_INFORMATION **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r12
  unsigned int v4; // r14d
  _QWORD *v5; // rsi
  _QWORD *v6; // rax
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  struct _SOCKET_BROKER_ENUM_SOCKET_INFORMATION *v10; // rdi
  unsigned int v11; // ebx
  _QWORD *v12; // r15
  unsigned int i; // ebp
  _OWORD *v14; // rdx
  __int64 v15; // rbx
  __int64 v16; // rcx
  _WORD *v17; // r8
  _WORD *v18; // rax
  __int64 v19; // rdx
  _WORD *v20; // rcx
  struct _SOCKET_BROKER_ENUM_SOCKET_INFORMATION *v22; // [rsp+60h] [rbp+8h] BYREF
  struct _SOCKET_BROKER_ENUM_SOCKET_INFORMATION **v23; // [rsp+68h] [rbp+10h]

  v23 = a2;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  v22 = 0;
  v4 = 0;
  *a2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v5 = (_QWORD *)((char *)this + 104);
  v6 = (_QWORD *)*((_QWORD *)this + 13);
  while ( v6 != v5 )
  {
    v6 = (_QWORD *)*v6;
    ++v4;
  }
  v7 = NcbUtilsAllocateEnumSocketInformation(v4, &v22);
  v10 = v22;
  v11 = v7;
  if ( v7 || !v22 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v9,
        v8,
        L"EnumSocketsEnumSockets: failed to create SOCKET_BROKER_ENUM_SOCKET_INFORMATION",
        v7);
  }
  else
  {
    v12 = (_QWORD *)*v5;
    for ( i = 0; v12 != v5 && i < v4; ++i )
    {
      v14 = (_OWORD *)*((_QWORD *)this + 15);
      if ( v14 )
        *(_OWORD *)((char *)v10 + 536 * i + 4) = *v14;
      v15 = 536LL * i;
      *(_DWORD *)((char *)v10 + v15 + 536) = SharedSocket::GetSocketType(v12 - 1);
      v16 = 2147483646;
      v17 = (_WORD *)v12[12];
      v18 = (_WORD *)((char *)v10 + v15 + 20);
      v19 = 257;
      do
      {
        if ( !v16 )
          break;
        if ( !*v17 )
          break;
        *v18++ = *v17++;
        --v16;
        --v19;
      }
      while ( v19 );
      v20 = v18 - 1;
      if ( v19 )
        v20 = v18;
      *v20 = 0;
      v11 = v19 == 0 ? 0x7A : 0;
      if ( !v19 )
      {
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          McTemplateU0zq_EventWriteTransfer(v20, 0, L"EnumSocketsEnumSockets: SocketId copy failed", 122);
        break;
      }
      v12 = (_QWORD *)*v12;
    }
    *v23 = v10;
    v10 = 0;
  }
  LeaveCriticalSection(v2);
  VpnFree(v10);
  return v11;
}

```

## disassembly

```asm
0x180002a30  mov     [rsp+arg_18], rbx
0x180002a35  mov     [rsp+arg_8], rdx
0x180002a3a  push    rbp
0x180002a3b  push    rsi
0x180002a3c  push    rdi
0x180002a3d  push    r12
0x180002a3f  push    r13
0x180002a41  push    r14
0x180002a43  push    r15
0x180002a45  sub     rsp, 20h
0x180002a49  lea     r12, [rcx+40h]
0x180002a4d  mov     [rsp+58h+arg_0], 0
0x180002a56  mov     r13, rcx
0x180002a59  xor     r14d, r14d
0x180002a5c  mov     rcx, r12; lpCriticalSection
0x180002a5f  mov     [rdx], r14
0x180002a62  call    cs:__imp_EnterCriticalSection
0x180002a68  lea     rsi, [r13+68h]
0x180002a6c  mov     rax, [rsi]
0x180002a6f  jmp     short loc_180002A77
0x180002a71  mov     rax, [rax]
0x180002a74  inc     r14d
0x180002a77  cmp     rax, rsi
0x180002a7a  jnz     short loc_180002A71
0x180002a7c  lea     rdx, [rsp+58h+arg_0]
0x180002a81  mov     ecx, r14d
0x180002a84  call    NcbUtilsAllocateEnumSocketInformation
0x180002a89  mov     rdi, [rsp+58h+arg_0]
0x180002a8e  xor     r10d, r10d
0x180002a91  mov     ebx, eax
0x180002a93  test    eax, eax
0x180002a95  jnz     loc_180002B93
0x180002a9b  test    rdi, rdi
0x180002a9e  jz      loc_180002B93
0x180002aa4  mov     r15, [rsi]
0x180002aa7  mov     ebp, r10d
0x180002aaa  cmp     r15, rsi
0x180002aad  jz      loc_180002B60
0x180002ab3  cmp     ebp, r14d
0x180002ab6  jnb     loc_180002B60
0x180002abc  mov     rdx, [r13+78h]
0x180002ac0  test    rdx, rdx
0x180002ac3  jz      short loc_180002AD7
0x180002ac5  movups  xmm0, xmmword ptr [rdx]
0x180002ac8  mov     eax, ebp
0x180002aca  imul    rcx, rax, 218h
0x180002ad1  movdqu  xmmword ptr [rcx+rdi+4], xmm0
0x180002ad7  mov     eax, ebp
0x180002ad9  lea     rcx, [r15-8]
0x180002add  imul    rbx, rax, 218h
0x180002ae4  call    ?GetSocketType@SharedSocket@@QEAA?AW4_SOCKET_BROKER_SOCKET_TYPE@@XZ; SharedSocket::GetSocketType(void)
0x180002ae9  mov     [rbx+rdi+218h], eax
0x180002af0  mov     ecx, 7FFFFFFEh
0x180002af5  mov     r8, [r15+60h]
0x180002af9  lea     rax, [rdi+14h]
0x180002afd  add     rax, rbx
0x180002b00  mov     edx, 101h
0x180002b05  xor     r10d, r10d
0x180002b08  test    rcx, rcx
0x180002b0b  jz      short loc_180002B2C
0x180002b0d  movzx   r9d, word ptr [r8]
0x180002b11  test    r9w, r9w
0x180002b15  jz      short loc_180002B2C
0x180002b17  mov     [rax], r9w
0x180002b1b  add     r8, 2
0x180002b1f  add     rax, 2
0x180002b23  dec     rcx
0x180002b26  sub     rdx, 1
0x180002b2a  jnz     short loc_180002B08
0x180002b2c  test    rdx, rdx
0x180002b2f  lea     rcx, [rax-2]
0x180002b33  cmovnz  rcx, rax
0x180002b37  mov     rax, rdx
0x180002b3a  neg     rax
0x180002b3d  sbb     ebx, ebx
0x180002b3f  not     ebx
0x180002b41  mov     [rcx], r10w
0x180002b45  and     ebx, 7Ah
0x180002b48  test    rdx, rdx
0x180002b4b  jz      short loc_180002B57
0x180002b4d  mov     r15, [r15]
0x180002b50  inc     ebp
0x180002b52  jmp     loc_180002AAA
0x180002b57  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180002b5e  jnz     short loc_180002BAD
0x180002b60  mov     rax, [rsp+58h+arg_8]
0x180002b65  mov     [rax], rdi
0x180002b68  mov     rdi, r10
0x180002b6b  mov     rcx, r12; lpCriticalSection
0x180002b6e  call    cs:__imp_LeaveCriticalSection
0x180002b74  mov     rcx, rdi; lpMem
0x180002b77  call    VpnFree
0x180002b7c  mov     eax, ebx
0x180002b7e  mov     rbx, [rsp+58h+arg_18]
0x180002b83  add     rsp, 20h
0x180002b87  pop     r15
0x180002b89  pop     r14
0x180002b8b  pop     r13
0x180002b8d  pop     r12
0x180002b8f  pop     rdi
0x180002b90  pop     rsi
0x180002b91  pop     rbp
0x180002b92  retn
0x180002b93  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180002b9a  jz      short loc_180002B6B
0x180002b9c  mov     r9d, eax
0x180002b9f  lea     r8, aEnumsocketsenu_0; "EnumSocketsEnumSockets: failed to creat"...
0x180002ba6  call    McTemplateU0zq_EventWriteTransfer
0x180002bab  jmp     short loc_180002B6B
0x180002bad  mov     r9d, ebx
0x180002bb0  lea     r8, aEnumsocketsenu; "EnumSocketsEnumSockets: SocketId copy f"...
0x180002bb7  call    McTemplateU0zq_EventWriteTransfer
0x180002bbc  xor     r10d, r10d
0x180002bbf  jmp     short loc_180002B60
```
