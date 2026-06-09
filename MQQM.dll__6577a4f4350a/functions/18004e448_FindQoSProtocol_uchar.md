# FindQoSProtocol(uchar * *)

- ea: `0x18004e448`
- end: `0x18004e64c`
- name: `?FindQoSProtocol@@YAPEAU_WSAPROTOCOL_INFOW@@PEAPEAE@Z`
- size: `516`
- prototype: `struct _WSAPROTOCOL_INFOW *__fastcall(unsigned __int8 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004e654`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x18002c61c`
- `0x18002c6c8`
- `0x18004e448`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x18004e5b6`
- `msvcrt!free` at `0x18004e5e6`
- `msvcrt!free` at `0x18004e63b`
- `msvcrt!free` at `0x18004e5b6`
- `msvcrt!free` at `0x18004e5e6`
- `msvcrt!free` at `0x18004e63b`
- `WSOCK32!__imp_WSAGetLastError` at `0x18004e4d4`
- `WSOCK32!__imp_WSAGetLastError` at `0x18004e561`
- `WSOCK32!__imp_WSAGetLastError` at `0x18004e4d4`
- `WSOCK32!__imp_WSAGetLastError` at `0x18004e561`
- `WS2_32!WSAEnumProtocolsW` at `0x18004e475`
- `WS2_32!WSAEnumProtocolsW` at `0x18004e553`
- `WS2_32!WSAEnumProtocolsW` at `0x18004e475`
- `WS2_32!WSAEnumProtocolsW` at `0x18004e553`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct _WSAPROTOCOL_INFOW *__fastcall FindQoSProtocol(struct _WSAPROTOCOL_INFOW **a1)
{
  unsigned int v2; // eax
  unsigned int Error; // eax
  int v4; // ebx
  struct _WSAPROTOCOL_INFOW *v5; // rbx
  unsigned int v6; // r8d
  unsigned int v7; // eax
  int v8; // edi
  unsigned int i; // edx
  struct _WSAPROTOCOL_INFOW *v10; // rdi
  DWORD dwBufferLength; // [rsp+40h] [rbp+8h] BYREF
  __int64 iProtocols; // [rsp+48h] [rbp+10h] BYREF
  struct _WSAPROTOCOL_INFOW *v14; // [rsp+50h] [rbp+18h]

  *a1 = 0;
  iProtocols = 6;
  dwBufferLength = 0;
  v2 = WSAEnumProtocolsW((LPINT)&iProtocols, 0, &dwBufferLength);
  if ( v2 == -1 )
  {
    Error = WSAGetLastError();
    v4 = Error;
    if ( Error == 10055 )
    {
      v5 = (struct _WSAPROTOCOL_INFOW *)MmAllocate(dwBufferLength);
      v14 = v5;
      v6 = WSAEnumProtocolsW((LPINT)&iProtocols, v5, &dwBufferLength);
      if ( v6 == -1 )
      {
        v7 = WSAGetLastError();
        v8 = v7;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, &WPP_7b2816af51693d9cc24ea94b8aa01c04_Traceguids, v7);
        if ( v8 )
          LogMsgNTStatus(v8, (wchar_t *)L"QoS", 0x1Eu);
        free(v5);
      }
      else
      {
        for ( i = 0; i < v6; ++i )
        {
          v10 = &v5[i];
          if ( (v10->dwServiceFlags1 & 0x2000) != 0 )
          {
            *a1 = v5;
            free(0);
            return v10;
          }
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 13, &WPP_7b2816af51693d9cc24ea94b8aa01c04_Traceguids);
        LogMsgHR(-1072824319, (wchar_t *)L"QoS", 0x28u);
        free(v5);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, &WPP_7b2816af51693d9cc24ea94b8aa01c04_Traceguids, Error);
      if ( v4 )
        LogMsgNTStatus(v4, (wchar_t *)L"QoS", 0x14u);
    }
  }
  else if ( v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, &WPP_7b2816af51693d9cc24ea94b8aa01c04_Traceguids, v2);
    LogMsgHR(-1072824319, (wchar_t *)L"QoS", 0xAu);
  }
  return 0;
}

```

## disassembly

```asm
0x18004e448  mov     rax, rsp
0x18004e44b  push    rbx
0x18004e44c  push    rsi
0x18004e44d  push    rdi
0x18004e44e  sub     rsp, 20h
0x18004e452  mov     rsi, rcx
0x18004e455  mov     qword ptr [rcx], 0
0x18004e45c  mov     qword ptr [rax+10h], 6
0x18004e464  mov     dword ptr [rax+8], 0
0x18004e46b  lea     r8, [rax+8]; lpdwBufferLength
0x18004e46f  xor     edx, edx; lpProtocolBuffer
0x18004e471  lea     rcx, [rax+10h]; lpiProtocols
0x18004e475  call    cs:__imp_WSAEnumProtocolsW
0x18004e47b  cmp     eax, 0FFFFFFFFh
0x18004e47e  jz      short loc_18004E4D4
0x18004e480  test    eax, eax
0x18004e482  jz      loc_18004E642
0x18004e488  lea     rdx, WPP_GLOBAL_Control
0x18004e48f  mov     ebx, 0Ah
0x18004e494  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e49b  cmp     rcx, rdx
0x18004e49e  jz      short loc_18004E4BB
0x18004e4a0  test    byte ptr [rcx+6Ch], 1
0x18004e4a4  jz      short loc_18004E4BB
0x18004e4a6  mov     edx, ebx
0x18004e4a8  mov     r9d, eax
0x18004e4ab  lea     r8, WPP_7b2816af51693d9cc24ea94b8aa01c04_Traceguids
0x18004e4b2  mov     rcx, [rcx+60h]
0x18004e4b6  call    WPP_SF_d
0x18004e4bb  mov     r8d, ebx; unsigned __int16
0x18004e4be  lea     rdx, aQos; "QoS"
0x18004e4c5  mov     ecx, 0C00E0001h; int
0x18004e4ca  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18004e4cf  jmp     loc_18004E642
0x18004e4d4  call    cs:__imp_WSAGetLastError
0x18004e4da  mov     ebx, eax
0x18004e4dc  cmp     eax, 2747h
0x18004e4e1  jz      short loc_18004E535
0x18004e4e3  lea     rdx, WPP_GLOBAL_Control
0x18004e4ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e4f1  cmp     rcx, rdx
0x18004e4f4  jz      short loc_18004E514
0x18004e4f6  test    byte ptr [rcx+6Ch], 1
0x18004e4fa  jz      short loc_18004E514
0x18004e4fc  mov     edx, 0Bh
0x18004e501  mov     r9d, eax
0x18004e504  lea     r8, WPP_7b2816af51693d9cc24ea94b8aa01c04_Traceguids
0x18004e50b  mov     rcx, [rcx+60h]
0x18004e50f  call    WPP_SF_d
0x18004e514  test    ebx, ebx
0x18004e516  jz      loc_18004E642
0x18004e51c  mov     r8d, 14h; unsigned __int16
0x18004e522  lea     rdx, aQos; "QoS"
0x18004e529  mov     ecx, ebx; int
0x18004e52b  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18004e530  jmp     loc_18004E642
0x18004e535  mov     ecx, [rsp+38h+dwBufferLength]; unsigned __int64
0x18004e539  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18004e53e  mov     rbx, rax
0x18004e541  mov     [rsp+38h+arg_10], rax
0x18004e546  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x18004e54b  mov     rdx, rax; lpProtocolBuffer
0x18004e54e  lea     rcx, [rsp+38h+iProtocols]; lpiProtocols
0x18004e553  call    cs:__imp_WSAEnumProtocolsW
0x18004e559  mov     r8d, eax
0x18004e55c  cmp     eax, 0FFFFFFFFh
0x18004e55f  jnz     short loc_18004E5C2
0x18004e561  call    cs:__imp_WSAGetLastError
0x18004e567  mov     edi, eax
0x18004e569  lea     rdx, WPP_GLOBAL_Control
0x18004e570  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e577  cmp     rcx, rdx
0x18004e57a  jz      short loc_18004E59A
0x18004e57c  test    byte ptr [rcx+6Ch], 1
0x18004e580  jz      short loc_18004E59A
0x18004e582  mov     edx, 0Ch
0x18004e587  mov     r9d, eax
0x18004e58a  lea     r8, WPP_7b2816af51693d9cc24ea94b8aa01c04_Traceguids
0x18004e591  mov     rcx, [rcx+60h]
0x18004e595  call    WPP_SF_d
0x18004e59a  test    edi, edi
0x18004e59c  jz      short loc_18004E5B3
0x18004e59e  mov     r8d, 1Eh; unsigned __int16
0x18004e5a4  lea     rdx, aQos; "QoS"
0x18004e5ab  mov     ecx, edi; int
0x18004e5ad  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18004e5b2  nop
0x18004e5b3  mov     rcx, rbx; Block
0x18004e5b6  call    cs:__imp_free
0x18004e5bc  nop
0x18004e5bd  jmp     loc_18004E642
0x18004e5c2  xor     edx, edx
0x18004e5c4  cmp     edx, r8d
0x18004e5c7  jnb     short loc_18004E5F2
0x18004e5c9  mov     eax, edx
0x18004e5cb  imul    rdi, rax, 274h
0x18004e5d2  add     rdi, rbx
0x18004e5d5  test    dword ptr [rdi], 2000h
0x18004e5db  jnz     short loc_18004E5E1
0x18004e5dd  inc     edx
0x18004e5df  jmp     short loc_18004E5C4
0x18004e5e1  mov     [rsi], rbx
0x18004e5e4  xor     ecx, ecx; Block
0x18004e5e6  call    cs:__imp_free
0x18004e5ec  nop
0x18004e5ed  mov     rax, rdi
0x18004e5f0  jmp     short loc_18004E644
0x18004e5f2  lea     rdx, WPP_GLOBAL_Control
0x18004e5f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e600  cmp     rcx, rdx
0x18004e603  jz      short loc_18004E620
0x18004e605  test    byte ptr [rcx+6Ch], 4
0x18004e609  jz      short loc_18004E620
0x18004e60b  mov     edx, 0Dh
0x18004e610  lea     r8, WPP_7b2816af51693d9cc24ea94b8aa01c04_Traceguids
0x18004e617  mov     rcx, [rcx+60h]
0x18004e61b  call    WPP_SF_
0x18004e620  mov     r8d, 28h ; '('; unsigned __int16
0x18004e626  lea     rdx, aQos; "QoS"
0x18004e62d  mov     ecx, 0C00E0001h; int
0x18004e632  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18004e637  nop
0x18004e638  mov     rcx, rbx; Block
0x18004e63b  call    cs:__imp_free
0x18004e641  nop
0x18004e642  xor     eax, eax
0x18004e644  add     rsp, 20h
0x18004e648  pop     rdi
0x18004e649  pop     rsi
0x18004e64a  pop     rbx
0x18004e64b  retn
```
