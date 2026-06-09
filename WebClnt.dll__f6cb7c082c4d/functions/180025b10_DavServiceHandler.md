# DavServiceHandler

- ea: `0x180025b10`
- end: `0x180025bef`
- name: `DavServiceHandler`
- size: `223`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000c2b8`
- `0x180025b10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bcc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025bac`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025bac`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180025b66`

## pseudocode

```c
void __fastcall DavServiceHandler(DWORD dwControl)
{
  __int64 v1; // rbx
  DWORD LastError; // eax

  if ( dwControl == 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3c901703a5983ce609c0997329a96280_Traceguids);
    UpdateServiceStatus(3u);
    if ( !SetEvent(g_DavstopServiceEvent)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v1 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v1, 11, WPP_3c901703a5983ce609c0997329a96280_Traceguids, LastError);
    }
  }
  else
  {
    if ( dwControl != 4
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_3c901703a5983ce609c0997329a96280_Traceguids, dwControl);
    }
    SetServiceStatus(g_hStatus, &g_status);
  }
}

```

## disassembly

```asm
0x180025b10  push    rbx
0x180025b12  sub     rsp, 20h
0x180025b16  mov     eax, ecx
0x180025b18  mov     r9d, ecx
0x180025b1b  sub     eax, 1
0x180025b1e  jz      short loc_180025B6D
0x180025b20  cmp     eax, 3
0x180025b23  jz      short loc_180025B53
0x180025b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b2c  lea     rbx, WPP_GLOBAL_Control
0x180025b33  cmp     rcx, rbx
0x180025b36  jz      short loc_180025B53
0x180025b38  test    byte ptr [rcx+1Ch], 10h
0x180025b3c  jz      short loc_180025B53
0x180025b3e  mov     rcx, [rcx+10h]
0x180025b42  lea     r8, WPP_3c901703a5983ce609c0997329a96280_Traceguids
0x180025b49  mov     edx, 0Ch
0x180025b4e  call    WPP_SF_d
0x180025b53  mov     rcx, cs:g_hStatus
0x180025b5a  lea     rdx, g_status
0x180025b61  add     rsp, 20h
0x180025b65  pop     rbx
0x180025b66  jmp     cs:__imp_SetServiceStatus
0x180025b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b74  lea     rbx, WPP_GLOBAL_Control
0x180025b7b  cmp     rcx, rbx
0x180025b7e  jz      short loc_180025B9B
0x180025b80  test    byte ptr [rcx+1Ch], 10h
0x180025b84  jz      short loc_180025B9B
0x180025b86  mov     rcx, [rcx+10h]
0x180025b8a  lea     r8, WPP_3c901703a5983ce609c0997329a96280_Traceguids
0x180025b91  mov     edx, 0Ah
0x180025b96  call    WPP_SF_
0x180025b9b  mov     ecx, 3
0x180025ba0  call    UpdateServiceStatus
0x180025ba5  mov     rcx, cs:g_DavstopServiceEvent; hEvent
0x180025bac  call    cs:__imp_SetEvent
0x180025bb2  test    eax, eax
0x180025bb4  jnz     short loc_180025BE9
0x180025bb6  mov     rax, cs:WPP_GLOBAL_Control
0x180025bbd  cmp     rax, rbx
0x180025bc0  jz      short loc_180025BE9
0x180025bc2  test    byte ptr [rax+1Ch], 1
0x180025bc6  jz      short loc_180025BE9
0x180025bc8  mov     rbx, [rax+10h]
0x180025bcc  call    cs:__imp_GetLastError
0x180025bd2  mov     edx, 0Bh
0x180025bd7  lea     r8, WPP_3c901703a5983ce609c0997329a96280_Traceguids
0x180025bde  mov     r9d, eax
0x180025be1  mov     rcx, rbx
0x180025be4  call    WPP_SF_d
0x180025be9  add     rsp, 20h
0x180025bed  pop     rbx
0x180025bee  retn
```
