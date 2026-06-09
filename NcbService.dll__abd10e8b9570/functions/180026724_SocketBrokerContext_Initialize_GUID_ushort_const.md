# SocketBrokerContext::Initialize(_GUID *,ushort const *)

- ea: `0x180026724`
- end: `0x1800267cf`
- name: `?Initialize@SocketBrokerContext@@QEAAKPEAU_GUID@@PEBG@Z`
- size: `171`
- prototype: `__int64 __fastcall(SocketBrokerContext *this, struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026374`

## callees

- `0x18000a0a0`
- `0x180012900`
- `0x180026724`
- `0x180026aa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002673c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002673c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800267bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800267bc`

## string_xrefs

- `0x1800267ac`: `SocketBrokerContext::Initialize called with empty eventId or empty application name`
- `0x180026773`: `SocketBrokerContext: Failed to create copy of application name`

## pseudocode

```c
__int64 __fastcall SocketBrokerContext::Initialize(
        SocketBrokerContext *this,
        struct _GUID *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  const wchar_t *v11; // r8

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( a2 && a3 )
  {
    *(struct _GUID *)((char *)this + 28) = *a2;
    v8 = NcbUtilsAllocCopyString(a3, (char *)this + 48);
    v9 = v8;
    if ( v8 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v10 = v8;
        v11 = L"SocketBrokerContext: Failed to create copy of application name";
LABEL_10:
        McTemplateU0zq_EventWriteTransfer(v7, v6, v11, v10);
      }
    }
    else if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      McTemplateU0jz_EventWriteTransfer(v7, SbStartTriggerNotifications, (char *)this + 28, *((_QWORD *)this + 6));
    }
  }
  else
  {
    v9 = 87;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v10 = 87;
      v11 = L"SocketBrokerContext::Initialize called with empty eventId or empty application name";
      goto LABEL_10;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return v9;
}

```

## disassembly

```asm
0x180026724  push    rbx
0x180026726  push    rbp
0x180026727  push    rsi
0x180026728  push    rdi
0x180026729  push    r14
0x18002672b  sub     rsp, 20h
0x18002672f  mov     rsi, rcx
0x180026732  mov     rbx, r8
0x180026735  add     rcx, 40h ; '@'; lpCriticalSection
0x180026739  mov     rbp, rdx
0x18002673c  call    cs:__imp_EnterCriticalSection
0x180026742  test    rbp, rbp
0x180026745  jz      short loc_18002679B
0x180026747  test    rbx, rbx
0x18002674a  jz      short loc_18002679B
0x18002674c  movups  xmm0, xmmword ptr [rbp+0]
0x180026750  lea     rdx, [rsi+30h]
0x180026754  mov     rcx, rbx
0x180026757  movdqu  xmmword ptr [rsi+1Ch], xmm0
0x18002675c  call    NcbUtilsAllocCopyString
0x180026761  mov     ebx, eax
0x180026763  test    eax, eax
0x180026765  jz      short loc_18002677C
0x180026767  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18002676e  jz      short loc_1800267B8
0x180026770  mov     r9d, eax
0x180026773  lea     r8, aSocketbrokerco_0; "SocketBrokerContext: Failed to create c"...
0x18002677a  jmp     short loc_1800267B3
0x18002677c  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180026783  jz      short loc_1800267B8
0x180026785  mov     r9, [rsi+30h]
0x180026789  lea     r8, [rsi+1Ch]
0x18002678d  lea     rdx, SbStartTriggerNotifications
0x180026794  call    McTemplateU0jz_EventWriteTransfer
0x180026799  jmp     short loc_1800267B8
0x18002679b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800267a2  mov     ebx, 57h ; 'W'
0x1800267a7  jz      short loc_1800267B8
0x1800267a9  mov     r9d, ebx
0x1800267ac  lea     r8, aSocketbrokerco_2; "SocketBrokerContext::Initialize called "...
0x1800267b3  call    McTemplateU0zq_EventWriteTransfer
0x1800267b8  lea     rcx, [rsi+40h]; lpCriticalSection
0x1800267bc  call    cs:__imp_LeaveCriticalSection
0x1800267c2  mov     eax, ebx
0x1800267c4  add     rsp, 20h
0x1800267c8  pop     r14
0x1800267ca  pop     rdi
0x1800267cb  pop     rsi
0x1800267cc  pop     rbp
0x1800267cd  pop     rbx
0x1800267ce  retn
```
