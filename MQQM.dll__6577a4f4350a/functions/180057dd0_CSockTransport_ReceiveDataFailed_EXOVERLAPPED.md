# CSockTransport::ReceiveDataFailed(EXOVERLAPPED *)

- ea: `0x180057dd0`
- end: `0x180057e9d`
- name: `?ReceiveDataFailed@CSockTransport@@CAXPEAVEXOVERLAPPED@@@Z`
- size: `205`
- prototype: `void __fastcall(struct EXOVERLAPPED *Block)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180057eb0`

## callees

- `0x180010b88`
- `0x18004b990`
- `0x180057dd0`
- `0x18008ce70`
- `0x1800e4010`

## import_xrefs

- `msvcrt!free` at `0x180057e7c`
- `msvcrt!free` at `0x180057e86`
- `msvcrt!free` at `0x180057e7c`
- `msvcrt!free` at `0x180057e86`
- `KERNEL32!GetCurrentThreadId` at `0x180057e05`
- `KERNEL32!GetCurrentThreadId` at `0x180057e05`
- `KERNEL32!GetTickCount` at `0x180057dfd`
- `KERNEL32!GetTickCount` at `0x180057dfd`

## string_xrefs

- `0x180057e41`: `Read packet from socket Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CSockTransport::ReceiveDataFailed(struct EXOVERLAPPED *Block, __int64 a2, __int64 a3)
{
  int v4; // edi
  DWORD TickCount; // ebx
  DWORD CurrentThreadId; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    v4 = *(_DWORD *)Block;
    TickCount = GetTickCount();
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_DDd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      58,
      &WPP_83e630141f6f36d68a76ab21f96db63d_Traceguids,
      CurrentThreadId,
      v4,
      TickCount);
  }
  LOBYTE(a3) = 1;
  (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)Block + 6) + 8LL))(
    *((_QWORD *)Block + 6),
    L"Read packet from socket Failed",
    a3);
  CReference::Release(*((CReference **)Block + 6));
  if ( *((__int64 (__fastcall **)(struct CSockTransport::QMOV_ReadSession *))Block + 11) == CSockTransport::ReadUserMsgCompleted )
    QmAcFreePacket(*((_QWORD *)Block + 8), 0, 1);
  else
    free(*((void **)Block + 7));
  free(Block);
}

```

## disassembly

```asm
0x180057dd0  mov     [rsp+arg_8], rbx
0x180057dd5  mov     [rsp+arg_10], rsi
0x180057dda  push    rdi
0x180057ddb  sub     rsp, 30h
0x180057ddf  mov     rsi, rcx
0x180057de2  lea     rcx, WPP_GLOBAL_Control
0x180057de9  mov     rax, cs:WPP_GLOBAL_Control
0x180057df0  cmp     rax, rcx
0x180057df3  jz      short loc_180057E32
0x180057df5  test    byte ptr [rax+6Ch], 2
0x180057df9  jz      short loc_180057E32
0x180057dfb  mov     edi, [rsi]
0x180057dfd  call    cs:__imp_GetTickCount
0x180057e03  mov     ebx, eax
0x180057e05  call    cs:__imp_GetCurrentThreadId
0x180057e0b  mov     edx, 3Ah ; ':'
0x180057e10  mov     [rsp+38h+var_10], ebx
0x180057e14  mov     [rsp+38h+var_18], edi
0x180057e18  mov     r9d, eax
0x180057e1b  lea     r8, WPP_83e630141f6f36d68a76ab21f96db63d_Traceguids
0x180057e22  mov     rcx, cs:WPP_GLOBAL_Control
0x180057e29  mov     rcx, [rcx+60h]
0x180057e2d  call    WPP_SF_DDd
0x180057e32  mov     [rsp+38h+arg_0], rsi
0x180057e37  mov     rcx, [rsi+30h]
0x180057e3b  mov     rax, [rcx]
0x180057e3e  mov     r8b, 1
0x180057e41  lea     rdx, aReadPacketFrom; "Read packet from socket Failed"
0x180057e48  mov     rax, [rax+8]
0x180057e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e51  mov     rcx, [rsi+30h]; this
0x180057e55  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x180057e5a  lea     rax, ?ReadUserMsgCompleted@CSockTransport@@CAJPEAUQMOV_ReadSession@1@@Z; CSockTransport::ReadUserMsgCompleted(CSockTransport::QMOV_ReadSession *)
0x180057e61  cmp     [rsi+58h], rax
0x180057e65  jnz     short loc_180057E78
0x180057e67  xor     edx, edx
0x180057e69  lea     r8d, [rdx+1]
0x180057e6d  mov     rcx, [rsi+40h]
0x180057e71  call    ?QmAcFreePacket@@YAXPEAVCPacket@@GW4DeferOnFailureEnum@@@Z; QmAcFreePacket(CPacket *,ushort,DeferOnFailureEnum)
0x180057e76  jmp     short loc_180057E83
0x180057e78  mov     rcx, [rsi+38h]; Block
0x180057e7c  call    cs:__imp_free
0x180057e82  nop
0x180057e83  mov     rcx, rsi; Block
0x180057e86  call    cs:__imp_free
0x180057e8c  nop
0x180057e8d  mov     rbx, [rsp+38h+arg_8]
0x180057e92  mov     rsi, [rsp+38h+arg_10]
0x180057e97  add     rsp, 30h
0x180057e9b  pop     rdi
0x180057e9c  retn
```
