# CxsStopClient(_GIP_WLAN_CLIENT *)

- ea: `0x18000a450`
- end: `0x18000a537`
- name: `?CxsStopClient@@YAXPEAU_GIP_WLAN_CLIENT@@@Z`
- size: `231`
- prototype: `void __fastcall(struct _GIP_WLAN_CLIENT *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800044a4`
- `0x180004610`
- `0x180005670`
- `0x18000a264`

## callees

- `0x180002158`
- `0x180002b48`
- `0x180002b70`
- `0x18000a450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a48e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a48e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a483`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a483`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a46a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a46a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4e9`

## pseudocode

```c
void __fastcall CxsStopClient(struct _GIP_WLAN_CLIENT *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  DWORD LastError; // eax
  void *v5; // rcx

  v2 = (void *)*((_QWORD *)a1 + 6);
  if ( v2 )
  {
    SetEvent(v2);
    v3 = (void *)*((_QWORD *)a1 + 7);
    if ( v3 )
    {
      if ( WaitForSingleObject(v3, 0xFFFFFFFF) == -1 )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids, LastError);
        }
      }
      CloseHandle(*((HANDLE *)a1 + 7));
      *((_QWORD *)a1 + 7) = 0;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 8));
    v5 = (void *)*((_QWORD *)a1 + 6);
    if ( v5 )
      CloseHandle(v5);
    memset_0(a1, 0, 0xA8u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x18000a450  mov     [rsp+arg_0], rbx
0x18000a455  push    rsi
0x18000a456  sub     rsp, 20h
0x18000a45a  mov     rbx, rcx
0x18000a45d  mov     rcx, [rcx+30h]; hEvent
0x18000a461  test    rcx, rcx
0x18000a464  jz      loc_18000A52C
0x18000a46a  call    cs:__imp_SetEvent
0x18000a470  mov     rcx, [rbx+38h]; hHandle
0x18000a474  lea     rsi, WPP_GLOBAL_Control
0x18000a47b  test    rcx, rcx
0x18000a47e  jz      short loc_18000A4D6
0x18000a480  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a483  call    cs:__imp_WaitForSingleObject
0x18000a489  cmp     eax, 0FFFFFFFFh
0x18000a48c  jnz     short loc_18000A4C4
0x18000a48e  call    cs:__imp_GetLastError
0x18000a494  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a49b  cmp     rcx, rsi
0x18000a49e  jz      short loc_18000A4C4
0x18000a4a0  test    byte ptr [rcx+1Ch], 1
0x18000a4a4  jz      short loc_18000A4C4
0x18000a4a6  cmp     byte ptr [rcx+19h], 2
0x18000a4aa  jb      short loc_18000A4C4
0x18000a4ac  mov     rcx, [rcx+10h]
0x18000a4b0  lea     r8, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids
0x18000a4b7  mov     edx, 2Ah ; '*'
0x18000a4bc  mov     r9d, eax
0x18000a4bf  call    WPP_SF_D
0x18000a4c4  mov     rcx, [rbx+38h]; hObject
0x18000a4c8  call    cs:__imp_CloseHandle
0x18000a4ce  mov     qword ptr [rbx+38h], 0
0x18000a4d6  lea     rcx, [rbx+8]; lpCriticalSection
0x18000a4da  call    cs:__imp_DeleteCriticalSection
0x18000a4e0  mov     rcx, [rbx+30h]; hObject
0x18000a4e4  test    rcx, rcx
0x18000a4e7  jz      short loc_18000A4EF
0x18000a4e9  call    cs:__imp_CloseHandle
0x18000a4ef  xor     edx, edx; Val
0x18000a4f1  mov     r8d, 0A8h; Size
0x18000a4f7  mov     rcx, rbx; void *
0x18000a4fa  call    memset_0
0x18000a4ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a506  cmp     rcx, rsi
0x18000a509  jz      short loc_18000A52C
0x18000a50b  test    byte ptr [rcx+1Ch], 4
0x18000a50f  jz      short loc_18000A52C
0x18000a511  cmp     byte ptr [rcx+19h], 5
0x18000a515  jb      short loc_18000A52C
0x18000a517  mov     rcx, [rcx+10h]
0x18000a51b  lea     r8, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids
0x18000a522  mov     edx, 2Bh ; '+'
0x18000a527  call    WPP_SF_
0x18000a52c  mov     rbx, [rsp+28h+arg_0]
0x18000a531  add     rsp, 20h
0x18000a535  pop     rsi
0x18000a536  retn
```
