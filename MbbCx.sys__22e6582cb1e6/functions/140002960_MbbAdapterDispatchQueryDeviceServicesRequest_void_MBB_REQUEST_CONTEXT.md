# MbbAdapterDispatchQueryDeviceServicesRequest(void *,_MBB_REQUEST_CONTEXT *)

- ea: `0x140002960`
- end: `0x140002a2c`
- name: `?MbbAdapterDispatchQueryDeviceServicesRequest@@YAHPEAXPEAU_MBB_REQUEST_CONTEXT@@@Z`
- size: `204`
- prototype: `__int64 __fastcall(void *, struct _MBB_REQUEST_CONTEXT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140002960`
- `0x1400051ac`
- `0x1400206cc`
- `0x140020988`

## pseudocode

```c
__int64 __fastcall MbbAdapterDispatchQueryDeviceServicesRequest(void *a1, struct _MBB_REQUEST_CONTEXT *a2)
{
  int v3; // edx
  unsigned int v4; // ebx
  int v5; // r9d
  unsigned int v6; // eax
  int v8; // [rsp+28h] [rbp-40h]
  char v9; // [rsp+30h] [rbp-38h]
  __int128 v10; // [rsp+40h] [rbp-28h] BYREF
  int v11; // [rsp+50h] [rbp-18h]

  v11 = 16;
  v10 = MBB_UUID_BASIC_CONNECT;
  v4 = MbbUtilSetupCommandMessage((__int64)a2, (__int64)&v10, 0, 0, 0);
  if ( v4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v5 = 16;
      v9 = v4;
      v8 = *((_DWORD *)a2 + 4);
LABEL_8:
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v3,
        1,
        v5,
        (__int64)WPP_94691144733c3f1d26776b6e97df90bb_Traceguids,
        v8,
        v9);
    }
  }
  else
  {
    v6 = MbbUtilSendMessageFragmentsAndLog(a2);
    v4 = v6;
    if ( v6 && v6 != 259 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v5 = 17;
      v9 = v6;
      v8 = *((_DWORD *)a2 + 4);
      goto LABEL_8;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140002960  mov     rax, rsp
0x140002963  mov     [rax+8], rbx
0x140002967  push    rdi
0x140002968  sub     rsp, 60h
0x14000296c  movups  xmm0, cs:MBB_UUID_BASIC_CONNECT
0x140002973  mov     rdi, rdx
0x140002976  mov     dword ptr [rax-18h], 10h
0x14000297d  xor     r9d, r9d
0x140002980  mov     dword ptr [rax-48h], 0
0x140002987  xor     r8d, r8d
0x14000298a  lea     rdx, [rax-28h]
0x14000298e  mov     rcx, rdi
0x140002991  movdqu  xmmword ptr [rax-28h], xmm0
0x140002996  call    ?MbbUtilSetupCommandMessage@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_COMMAND@@W4_MBB_COMMAND_TYPE@@PEAEK@Z; MbbUtilSetupCommandMessage(_MBB_REQUEST_CONTEXT *,_MBB_COMMAND *,_MBB_COMMAND_TYPE,uchar *,ulong)
0x14000299b  mov     ebx, eax
0x14000299d  test    eax, eax
0x14000299f  jz      short loc_1400029C4
0x1400029a1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400029a8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400029af  jz      short loc_140002A1E
0x1400029b1  mov     ecx, [rdi+10h]
0x1400029b4  mov     r9d, 10h
0x1400029ba  mov     dword ptr [rsp+68h+var_38], ebx
0x1400029be  mov     [rsp+68h+var_40], ecx
0x1400029c2  jmp     short loc_1400029FA
0x1400029c4  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x1400029c7  call    ?MbbUtilSendMessageFragmentsAndLog@@YAHPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbUtilSendMessageFragmentsAndLog(_MBB_REQUEST_CONTEXT *)
0x1400029cc  mov     ebx, eax
0x1400029ce  test    eax, eax
0x1400029d0  jz      short loc_140002A1E
0x1400029d2  cmp     eax, 103h
0x1400029d7  jz      short loc_140002A1E
0x1400029d9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400029e0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400029e7  jz      short loc_140002A1E
0x1400029e9  mov     eax, [rdi+10h]
0x1400029ec  mov     r9d, 11h
0x1400029f2  mov     dword ptr [rsp+68h+var_38], ebx
0x1400029f6  mov     [rsp+68h+var_40], eax
0x1400029fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a01  lea     rax, WPP_94691144733c3f1d26776b6e97df90bb_Traceguids
0x140002a08  mov     r8d, 1
0x140002a0e  mov     [rsp+68h+var_48], rax
0x140002a13  mov     dl, 2
0x140002a15  mov     rcx, [rcx+40h]
0x140002a19  call    WPP_RECORDER_SF_DD
0x140002a1e  mov     eax, ebx
0x140002a20  mov     rbx, [rsp+68h+arg_0]
0x140002a25  add     rsp, 60h
0x140002a29  pop     rdi
0x140002a2a  retn
```
