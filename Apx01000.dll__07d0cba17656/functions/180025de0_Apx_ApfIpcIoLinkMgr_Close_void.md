# Apx::ApfIpcIoLinkMgr::Close(void)

- ea: `0x180025de0`
- end: `0x180025ecd`
- name: `?Close@ApfIpcIoLinkMgr@Apx@@UEAAXXZ`
- size: `237`
- prototype: `void __fastcall(Apx::ApfIpcIoLinkMgr *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000a12c`
- `0x180025de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e8a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025e58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025e58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025e78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025e78`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180025e2f`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180025e46`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180025e2f`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180025e46`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180025e69`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180025e69`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLinkMgr::Close(Apx::ApfIpcIoLinkMgr *this)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
  if ( *((_QWORD *)this + 12) )
  {
    CM_Unregister_Notification();
    *((_QWORD *)this + 12) = 0;
  }
  if ( *((_QWORD *)this + 13) )
  {
    CM_Unregister_Notification();
    *((_QWORD *)this + 13) = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
  {
    CancelIoEx(v2, 0);
    v3 = (void *)*((_QWORD *)this + 11);
    if ( v3 )
    {
      CloseHandle(v3);
      *((_QWORD *)this + 11) = 0;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
}

```

## disassembly

```asm
0x180025de0  mov     [rsp+arg_0], rbx
0x180025de5  mov     [rsp+arg_8], rbp
0x180025dea  push    rdi
0x180025deb  sub     rsp, 20h
0x180025def  mov     rbx, rcx
0x180025df2  mov     rcx, cs:WPP_GLOBAL_Control
0x180025df9  lea     rbp, WPP_GLOBAL_Control
0x180025e00  cmp     rcx, rbp
0x180025e03  jz      short loc_180025E26
0x180025e05  test    byte ptr [rcx+1Ch], 1
0x180025e09  jz      short loc_180025E26
0x180025e0b  cmp     byte ptr [rcx+19h], 5
0x180025e0f  jb      short loc_180025E26
0x180025e11  mov     rcx, [rcx+10h]
0x180025e15  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180025e1c  mov     edx, 18h
0x180025e21  call    WPP_SF_
0x180025e26  mov     rcx, [rbx+60h]
0x180025e2a  test    rcx, rcx
0x180025e2d  jz      short loc_180025E3D
0x180025e2f  call    cs:__imp_CM_Unregister_Notification
0x180025e35  mov     qword ptr [rbx+60h], 0
0x180025e3d  mov     rcx, [rbx+68h]
0x180025e41  test    rcx, rcx
0x180025e44  jz      short loc_180025E54
0x180025e46  call    cs:__imp_CM_Unregister_Notification
0x180025e4c  mov     qword ptr [rbx+68h], 0
0x180025e54  lea     rcx, [rbx+10h]; lpCriticalSection
0x180025e58  call    cs:__imp_EnterCriticalSection
0x180025e5e  mov     rcx, [rbx+58h]; hFile
0x180025e62  test    rcx, rcx
0x180025e65  jz      short loc_180025E86
0x180025e67  xor     edx, edx; lpOverlapped
0x180025e69  call    cs:__imp_CancelIoEx
0x180025e6f  mov     rcx, [rbx+58h]; hObject
0x180025e73  test    rcx, rcx
0x180025e76  jz      short loc_180025E86
0x180025e78  call    cs:__imp_CloseHandle
0x180025e7e  mov     qword ptr [rbx+58h], 0
0x180025e86  lea     rcx, [rbx+10h]; lpCriticalSection
0x180025e8a  call    cs:__imp_LeaveCriticalSection
0x180025e90  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e97  cmp     rcx, rbp
0x180025e9a  jz      short loc_180025EBD
0x180025e9c  test    byte ptr [rcx+1Ch], 1
0x180025ea0  jz      short loc_180025EBD
0x180025ea2  cmp     byte ptr [rcx+19h], 5
0x180025ea6  jb      short loc_180025EBD
0x180025ea8  mov     rcx, [rcx+10h]
0x180025eac  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180025eb3  mov     edx, 19h
0x180025eb8  call    WPP_SF_
0x180025ebd  mov     rbx, [rsp+28h+arg_0]
0x180025ec2  mov     rbp, [rsp+28h+arg_8]
0x180025ec7  add     rsp, 20h
0x180025ecb  pop     rdi
0x180025ecc  retn
```
