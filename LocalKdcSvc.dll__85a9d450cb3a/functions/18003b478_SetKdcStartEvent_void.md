# SetKdcStartEvent(void)

- ea: `0x18003b478`
- end: `0x18003b553`
- name: `?SetKdcStartEvent@@YAXXZ`
- size: `219`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003a5fc`

## callees

- `0x180010278`
- `0x180037d1c`
- `0x18003b478`
- `0x180040308`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003b497`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003b497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4de`

## string_xrefs

- `0x18003b47c`: `\Security\KdcStartEvent`
- `0x18003b4c2`: `\Security\KdcStartEvent`
- `0x18003b53b`: `\Security\KdcStartEvent`

## pseudocode

```c
void __fastcall SetKdcStartEvent(__int64 a1, __int64 a2)
{
  void *v2; // rax
  DWORD LastError; // r8d

  v2 = KdcOpenEvent(a1, a2, L"\\Security\\KdcStartEvent");
  hKdcStartEvent = v2;
  if ( v2 )
  {
    SetEvent(v2);
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
        L"\\Security\\KdcStartEvent");
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 2 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          (unsigned int)WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
          (unsigned int)L"\\Security\\KdcStartEvent",
          2);
    }
    else if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
        (unsigned int)L"\\Security\\KdcStartEvent",
        LastError);
    }
  }
}

```

## disassembly

```asm
0x18003b478  sub     rsp, 38h
0x18003b47c  lea     r8, aSecurityKdcsta; "\\Security\\KdcStartEvent"
0x18003b483  call    ?KdcOpenEvent@@YAPEAXKHPEAG@Z; KdcOpenEvent(ulong,int,ushort *)
0x18003b488  mov     cs:?hKdcStartEvent@@3PEAXEA, rax; void * hKdcStartEvent
0x18003b48f  test    rax, rax
0x18003b492  jz      short loc_18003B4DE
0x18003b494  mov     rcx, rax; hEvent
0x18003b497  call    cs:__imp_SetEvent
0x18003b49d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b4a4  lea     rax, WPP_GLOBAL_Control
0x18003b4ab  cmp     rcx, rax
0x18003b4ae  jz      loc_18003B54E
0x18003b4b4  test    byte ptr [rcx+1Ch], 4
0x18003b4b8  jz      loc_18003B54E
0x18003b4be  mov     rcx, [rcx+10h]
0x18003b4c2  lea     r9, aSecurityKdcsta; "\\Security\\KdcStartEvent"
0x18003b4c9  mov     edx, 1Ch
0x18003b4ce  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x18003b4d5  add     rsp, 38h
0x18003b4d9  jmp     WPP_SF_S
0x18003b4de  call    cs:__imp_GetLastError
0x18003b4e4  mov     r8d, eax
0x18003b4e7  cmp     eax, 2
0x18003b4ea  jz      short loc_18003B511
0x18003b4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b4f3  lea     rax, WPP_GLOBAL_Control
0x18003b4fa  cmp     rcx, rax
0x18003b4fd  jz      short loc_18003B54E
0x18003b4ff  test    byte ptr [rcx+1Ch], 1
0x18003b503  jz      short loc_18003B54E
0x18003b505  mov     edx, 1Dh
0x18003b50a  mov     [rsp+38h+var_18], r8d
0x18003b50f  jmp     short loc_18003B537
0x18003b511  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b518  lea     rax, WPP_GLOBAL_Control
0x18003b51f  cmp     rcx, rax
0x18003b522  jz      short loc_18003B54E
0x18003b524  test    byte ptr [rcx+1Ch], 4
0x18003b528  jz      short loc_18003B54E
0x18003b52a  mov     edx, 1Eh
0x18003b52f  mov     [rsp+38h+var_18], 2
0x18003b537  mov     rcx, [rcx+10h]
0x18003b53b  lea     r9, aSecurityKdcsta; "\\Security\\KdcStartEvent"
0x18003b542  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x18003b549  call    WPP_SF_Sd
0x18003b54e  add     rsp, 38h
0x18003b552  retn
```
