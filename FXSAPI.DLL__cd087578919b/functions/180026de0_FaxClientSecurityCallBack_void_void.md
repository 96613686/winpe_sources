# FaxClientSecurityCallBack(void *,void *)

- ea: `0x180026de0`
- end: `0x180026ee8`
- name: `?FaxClientSecurityCallBack@@YAJPEAX0@Z`
- size: `264`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180026de0`
- `0x18002bb58`
- `0x1800332d8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180026e84`
- `msvcrt!_wcsicmp` at `0x180026e84`

## pseudocode

```c
__int64 __fastcall FaxClientSecurityCallBack(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int RpcStringBindingInfo; // eax
  unsigned int v4; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids);
  }
  RpcStringBindingInfo = GetRpcStringBindingInfo(Context);
  if ( RpcStringBindingInfo )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_6e3acdab872831c35b7514c03928d94f_Traceguids,
        RpcStringBindingInfo);
    }
    return 5;
  }
  v4 = 0;
  if ( _wcsicmp(0, L"ncacn_ip_tcp") )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids);
    }
    return 5;
  }
  return v4;
}

```

## disassembly

```asm
0x180026de0  mov     [rsp+arg_0], rbx
0x180026de5  push    r14
0x180026de7  sub     rsp, 20h
0x180026deb  mov     rbx, rdx
0x180026dee  mov     [rsp+28h+String1], 0
0x180026df7  mov     rcx, cs:WPP_GLOBAL_Control
0x180026dfe  lea     r14, WPP_GLOBAL_Control
0x180026e05  cmp     rcx, r14
0x180026e08  jz      short loc_180026E2E
0x180026e0a  test    dword ptr [rcx+1Ch], 1000h
0x180026e11  jz      short loc_180026E2E
0x180026e13  cmp     byte ptr [rcx+19h], 5
0x180026e17  jb      short loc_180026E2E
0x180026e19  mov     rcx, [rcx+10h]
0x180026e1d  lea     r8, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids
0x180026e24  mov     edx, 15h
0x180026e29  call    WPP_SF_
0x180026e2e  lea     r8, [rsp+28h+String1]
0x180026e33  xor     edx, edx
0x180026e35  mov     rcx, rbx; ClientBinding
0x180026e38  call    GetRpcStringBindingInfo
0x180026e3d  test    eax, eax
0x180026e3f  jz      short loc_180026E76
0x180026e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e48  cmp     rcx, r14
0x180026e4b  jz      short loc_180026EC2
0x180026e4d  test    dword ptr [rcx+1Ch], 1000h
0x180026e54  jz      short loc_180026EC2
0x180026e56  cmp     byte ptr [rcx+19h], 2
0x180026e5a  jb      short loc_180026EC2
0x180026e5c  mov     rcx, [rcx+10h]
0x180026e60  lea     r8, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids
0x180026e67  mov     edx, 16h
0x180026e6c  mov     r9d, eax
0x180026e6f  call    WPP_SF_d
0x180026e74  jmp     short loc_180026EC2
0x180026e76  mov     rcx, [rsp+28h+String1]; String1
0x180026e7b  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x180026e82  xor     ebx, ebx
0x180026e84  call    cs:__imp__wcsicmp
0x180026e8b  nop     dword ptr [rax+rax+00h]
0x180026e90  test    eax, eax
0x180026e92  jz      short loc_180026EC7
0x180026e94  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e9b  cmp     rcx, r14
0x180026e9e  jz      short loc_180026EC2
0x180026ea0  test    dword ptr [rcx+1Ch], 1000h
0x180026ea7  jz      short loc_180026EC2
0x180026ea9  cmp     byte ptr [rcx+19h], 2
0x180026ead  jb      short loc_180026EC2
0x180026eaf  mov     rcx, [rcx+10h]
0x180026eb3  lea     edx, [rbx+17h]
0x180026eb6  lea     r8, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids
0x180026ebd  call    WPP_SF_
0x180026ec2  mov     ebx, 5
0x180026ec7  cmp     [rsp+28h+String1], 0
0x180026ecd  jz      short loc_180026ED9
0x180026ecf  mov     rcx, [rsp+28h+String1]; lpMem
0x180026ed4  call    pMemFree
0x180026ed9  mov     eax, ebx
0x180026edb  mov     rbx, [rsp+28h+arg_0]
0x180026ee0  add     rsp, 20h
0x180026ee4  pop     r14
0x180026ee6  retn
```
