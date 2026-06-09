# StopService(void)

- ea: `0x180012974`
- end: `0x180012a36`
- name: `?StopService@@YAJXZ`
- size: `194`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180011c20`
- `0x180012de0`

## callees

- `0x18000a644`
- `0x18000a778`
- `0x180012974`
- `0x180012c9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800129fc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800129fc`

## pseudocode

```c
__int64 __fastcall StopService(__int64 a1, int a2)
{
  int updated; // ebx
  _QWORD *v3; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
  updated = UpdateServiceStatus(3u, a2);
  if ( updated >= 0 )
    goto LABEL_8;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
LABEL_8:
    v3 = WPP_GLOBAL_Control;
  }
  if ( g_hServiceStopEvent )
  {
    SetEvent(g_hServiceStopEvent);
    v3 = WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x20) != 0 )
    WPP_SF_(v3[2], 47, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180012974  mov     [rsp+arg_0], rbx
0x180012979  push    rdi
0x18001297a  sub     rsp, 20h
0x18001297e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012985  lea     rdi, WPP_GLOBAL_Control
0x18001298c  cmp     rcx, rdi
0x18001298f  jz      short loc_1800129AC
0x180012991  test    byte ptr [rcx+1Ch], 20h
0x180012995  jz      short loc_1800129AC
0x180012997  mov     rcx, [rcx+10h]
0x18001299b  lea     r8, WPP_3f50365df99735211a88e8fb382b12e7_Traceguids
0x1800129a2  mov     edx, 2Dh ; '-'
0x1800129a7  call    WPP_SF_
0x1800129ac  mov     ecx, 3; unsigned int
0x1800129b1  call    ?UpdateServiceStatus@@YAJKJ@Z; UpdateServiceStatus(ulong,long)
0x1800129b6  mov     ebx, eax
0x1800129b8  test    eax, eax
0x1800129ba  jns     short loc_1800129E6
0x1800129bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129c3  cmp     rcx, rdi
0x1800129c6  jz      short loc_1800129ED
0x1800129c8  test    byte ptr [rcx+1Ch], 2
0x1800129cc  jz      short loc_1800129ED
0x1800129ce  mov     rcx, [rcx+10h]
0x1800129d2  lea     r8, WPP_3f50365df99735211a88e8fb382b12e7_Traceguids
0x1800129d9  mov     edx, 2Eh ; '.'
0x1800129de  mov     r9d, eax
0x1800129e1  call    WPP_SF_d
0x1800129e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129ed  mov     rax, cs:?g_hServiceStopEvent@@3PEAXEA; void * g_hServiceStopEvent
0x1800129f4  test    rax, rax
0x1800129f7  jz      short loc_180012A09
0x1800129f9  mov     rcx, rax; hEvent
0x1800129fc  call    cs:__imp_SetEvent
0x180012a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a09  cmp     rcx, rdi
0x180012a0c  jz      short loc_180012A29
0x180012a0e  test    byte ptr [rcx+1Ch], 20h
0x180012a12  jz      short loc_180012A29
0x180012a14  mov     rcx, [rcx+10h]
0x180012a18  lea     r8, WPP_3f50365df99735211a88e8fb382b12e7_Traceguids
0x180012a1f  mov     edx, 2Fh ; '/'
0x180012a24  call    WPP_SF_
0x180012a29  mov     eax, ebx
0x180012a2b  mov     rbx, [rsp+28h+arg_0]
0x180012a30  add     rsp, 20h
0x180012a34  pop     rdi
0x180012a35  retn
```
