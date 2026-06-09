# BthServStopAutoConfigServiceMonitor(void)

- ea: `0x18001b628`
- end: `0x18001b733`
- name: `?BthServStopAutoConfigServiceMonitor@@YAXXZ`
- size: `267`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000ad78`
- `0x18000b348`
- `0x18001b9d8`

## callees

- `0x1800110fc`
- `0x18001b628`
- `0x18001b73c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6d5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001b6b1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001b6b1`

## pseudocode

```c
void BthServStopAutoConfigServiceMonitor(void)
{
  _BYTE *v0; // rcx
  char v1; // bl
  bool v2; // dl
  HLOCAL v3; // rax
  SC_HANDLE v4; // rcx

  v0 = WPP_GLOBAL_Control;
  v1 = 1;
  v2 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v0 = WPP_GLOBAL_Control;
  }
  v3 = pInterfaceGuid;
  if ( pInterfaceGuid )
  {
    if ( *((_QWORD *)pInterfaceGuid + 12) )
    {
      v4 = (SC_HANDLE)*((_QWORD *)pInterfaceGuid + 13);
      if ( v4 )
      {
        CloseServiceHandle(v4);
        *((_QWORD *)pInterfaceGuid + 13) = 0;
      }
      CloseWlanApi();
      v3 = pInterfaceGuid;
    }
    LocalFree(v3);
    v0 = WPP_GLOBAL_Control;
    pInterfaceGuid = 0;
  }
  if ( v0 == (_BYTE *)&WPP_GLOBAL_Control || v0[25] < 4u )
    v1 = 0;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v0 + 2),
      v1,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v0 + 5));
}

```

## disassembly

```asm
0x18001b628  push    rbx
0x18001b62a  push    rbp
0x18001b62b  push    rsi
0x18001b62c  push    r14
0x18001b62e  sub     rsp, 58h
0x18001b632  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b639  lea     rsi, WPP_GLOBAL_Control
0x18001b640  mov     bl, 1
0x18001b642  cmp     rcx, rsi
0x18001b645  jz      short loc_18001B651
0x18001b647  cmp     byte ptr [rcx+19h], 4
0x18001b64b  jb      short loc_18001B651
0x18001b64d  mov     dl, bl
0x18001b64f  jmp     short loc_18001B653
0x18001b651  xor     dl, dl
0x18001b653  lea     rbp, WPP_RECORDER_INITIALIZED
0x18001b65a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001b661  lea     r14, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001b668  setnz   r8b
0x18001b66c  test    dl, dl
0x18001b66e  jnz     short loc_18001B675
0x18001b670  test    r8b, r8b
0x18001b673  jz      short loc_18001B695
0x18001b675  mov     r9, [rcx+28h]
0x18001b679  mov     rcx, [rcx+10h]
0x18001b67d  mov     [rsp+78h+var_40], r14
0x18001b682  mov     [rsp+78h+var_48], 38h ; '8'
0x18001b689  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001b68e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b695  mov     rax, cs:pInterfaceGuid
0x18001b69c  test    rax, rax
0x18001b69f  jz      short loc_18001B6ED
0x18001b6a1  cmp     qword ptr [rax+60h], 0
0x18001b6a6  jz      short loc_18001B6D2
0x18001b6a8  mov     rcx, [rax+68h]; hSCObject
0x18001b6ac  test    rcx, rcx
0x18001b6af  jz      short loc_18001B6C6
0x18001b6b1  call    cs:__imp_CloseServiceHandle
0x18001b6b7  mov     rax, cs:pInterfaceGuid
0x18001b6be  mov     qword ptr [rax+68h], 0
0x18001b6c6  call    ?CloseWlanApi@@YAXXZ; CloseWlanApi(void)
0x18001b6cb  mov     rax, cs:pInterfaceGuid
0x18001b6d2  mov     rcx, rax; hMem
0x18001b6d5  call    cs:__imp_LocalFree
0x18001b6db  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6e2  mov     cs:pInterfaceGuid, 0
0x18001b6ed  cmp     rcx, rsi
0x18001b6f0  jz      short loc_18001B6F8
0x18001b6f2  cmp     byte ptr [rcx+19h], 4
0x18001b6f6  jnb     short loc_18001B6FA
0x18001b6f8  xor     bl, bl
0x18001b6fa  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001b701  setnz   r8b
0x18001b705  test    bl, bl
0x18001b707  jnz     short loc_18001B70E
0x18001b709  test    r8b, r8b
0x18001b70c  jz      short loc_18001B729
0x18001b70e  mov     r9, [rcx+28h]
0x18001b712  mov     dl, bl
0x18001b714  mov     rcx, [rcx+10h]
0x18001b718  mov     [rsp+78h+var_40], r14
0x18001b71d  mov     [rsp+78h+var_48], 39h ; '9'
0x18001b724  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001b729  add     rsp, 58h
0x18001b72d  pop     r14
0x18001b72f  pop     rsi
0x18001b730  pop     rbp
0x18001b731  pop     rbx
0x18001b732  retn
```
