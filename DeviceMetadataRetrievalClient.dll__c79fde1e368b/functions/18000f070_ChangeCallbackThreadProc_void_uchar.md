# ChangeCallbackThreadProc(void *,uchar)

- ea: `0x18000f070`
- end: `0x18000f14d`
- name: `?ChangeCallbackThreadProc@@YAXPEAXE@Z`
- size: `221`
- prototype: `void __fastcall(PVOID, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180004dc4`
- `0x18000b3fc`
- `0x18000f070`
- `0x1800135cc`
- `0x180014010`

## import_xrefs

- `KERNEL32!SleepEx` at `0x18000f0d9`
- `KERNEL32!SleepEx` at `0x18000f0d9`
- `KERNEL32!FindNextChangeNotification` at `0x18000f0f9`
- `KERNEL32!FindNextChangeNotification` at `0x18000f0f9`

## pseudocode

```c
void __fastcall ChangeCallbackThreadProc(PVOID a1, __int64 a2)
{
  char v2; // di
  void *v4; // rcx
  __int64 v5; // rdx
  RTL_SRWLOCK *v6; // rcx
  __int64 v7; // rcx

  if ( a1 )
  {
    v2 = a2;
    if ( *(_DWORD *)a1 == 1128808740 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a3cc2cf962863938c4e740311496c24e_Traceguids);
      if ( v2 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v4, a2);
      SleepEx(0x3E8u, 0);
      v6 = (RTL_SRWLOCK *)*((_QWORD *)a1 + 1);
      if ( v6 && LODWORD(v6->Ptr) == 1229866053 )
        ScanSystem(v6, v5);
      if ( !FindNextChangeNotification(*((HANDLE *)a1 + 3))
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a3cc2cf962863938c4e740311496c24e_Traceguids);
      }
      v7 = *((_QWORD *)a1 + 5);
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
    }
  }
}

```

## disassembly

```asm
0x18000f070  test    rcx, rcx
0x18000f073  jz      locret_18000F14C
0x18000f079  mov     [rsp+arg_0], rbx
0x18000f07e  mov     [rsp+arg_8], rsi
0x18000f083  push    rdi
0x18000f084  sub     rsp, 20h
0x18000f088  cmp     dword ptr [rcx], 43484124h
0x18000f08e  mov     dil, dl
0x18000f091  mov     rbx, rcx
0x18000f094  jnz     loc_18000F13D
0x18000f09a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0a1  lea     rsi, WPP_GLOBAL_Control
0x18000f0a8  cmp     rcx, rsi
0x18000f0ab  jz      short loc_18000F0C8
0x18000f0ad  test    byte ptr [rcx+1Ch], 8
0x18000f0b1  jz      short loc_18000F0C8
0x18000f0b3  mov     rcx, [rcx+10h]
0x18000f0b7  lea     r8, WPP_a3cc2cf962863938c4e740311496c24e_Traceguids
0x18000f0be  mov     edx, 0Ch
0x18000f0c3  call    WPP_SF_
0x18000f0c8  test    dil, dil
0x18000f0cb  jz      short loc_18000F0D2
0x18000f0cd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f0d2  xor     edx, edx; bAlertable
0x18000f0d4  mov     ecx, 3E8h; dwMilliseconds
0x18000f0d9  call    cs:__imp_SleepEx
0x18000f0df  mov     rcx, [rbx+8]; struct _INDEX_STRUCT *
0x18000f0e3  test    rcx, rcx
0x18000f0e6  jz      short loc_18000F0F5
0x18000f0e8  cmp     dword ptr [rcx], 494E4445h
0x18000f0ee  jnz     short loc_18000F0F5
0x18000f0f0  call    ScanSystem
0x18000f0f5  mov     rcx, [rbx+18h]; hChangeHandle
0x18000f0f9  call    cs:__imp_FindNextChangeNotification
0x18000f0ff  test    eax, eax
0x18000f101  jnz     short loc_18000F128
0x18000f103  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f10a  cmp     rcx, rsi
0x18000f10d  jz      short loc_18000F128
0x18000f10f  test    byte ptr [rcx+1Ch], 1
0x18000f113  jz      short loc_18000F128
0x18000f115  mov     rcx, [rcx+10h]
0x18000f119  lea     edx, [rax+0Dh]
0x18000f11c  lea     r8, WPP_a3cc2cf962863938c4e740311496c24e_Traceguids
0x18000f123  call    WPP_SF_
0x18000f128  mov     rcx, [rbx+28h]
0x18000f12c  test    rcx, rcx
0x18000f12f  jz      short loc_18000F13D
0x18000f131  mov     rax, [rcx]
0x18000f134  mov     rax, [rax+18h]
0x18000f138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f13d  mov     rbx, [rsp+28h+arg_0]
0x18000f142  mov     rsi, [rsp+28h+arg_8]
0x18000f147  add     rsp, 20h
0x18000f14b  pop     rdi
0x18000f14c  retn
```
