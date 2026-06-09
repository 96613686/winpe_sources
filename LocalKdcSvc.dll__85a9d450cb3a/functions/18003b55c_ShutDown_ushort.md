# ShutDown(ushort *)

- ea: `0x18003b55c`
- end: `0x18003b5d1`
- name: `?ShutDown@@YAJPEAG@Z`
- size: `117`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036d20`

## callees

- `0x180010278`
- `0x18003669c`
- `0x18003b55c`
- `0x180045b50`
- `0x18004b498`
- `0x18009c010`

## import_xrefs

- `Kerberos!KerbKdcCallBack` at `0x18003b5ab`
- `Kerberos!KerbKdcCallBack` at `0x18003b5ab`

## string_xrefs

- `0x18003b57d`: `Service`

## pseudocode

```c
__int64 __fastcall ShutDown(unsigned __int16 *a1)
{
  struct IKdcBackend *v1; // rax

  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, L"Service");
  v1 = GlobalKdcService::Get();
  (*(void (__fastcall **)(struct IKdcBackend *))(*(_QWORD *)v1 + 120LL))(v1);
  KerbKdcCallBack(0);
  g_kdcState = 0;
  EnterApiCall(2);
  LeaveApiCall();
  return 0;
}

```

## disassembly

```asm
0x18003b55c  sub     rsp, 28h
0x18003b560  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b567  lea     rax, WPP_GLOBAL_Control
0x18003b56e  cmp     rcx, rax
0x18003b571  jz      short loc_18003B595
0x18003b573  test    byte ptr [rcx+1Ch], 2
0x18003b577  jz      short loc_18003B595
0x18003b579  mov     rcx, [rcx+10h]
0x18003b57d  lea     r9, aService; "Service"
0x18003b584  mov     edx, 6Bh ; 'k'
0x18003b589  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x18003b590  call    WPP_SF_S
0x18003b595  call    ?Get@GlobalKdcService@@SAAEAUIKdcBackend@@XZ; GlobalKdcService::Get(void)
0x18003b59a  mov     rcx, rax
0x18003b59d  mov     rdx, [rax]
0x18003b5a0  mov     rax, [rdx+78h]
0x18003b5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5a9  xor     ecx, ecx
0x18003b5ab  call    cs:__imp_KerbKdcCallBack
0x18003b5b1  mov     ecx, 2
0x18003b5b6  mov     cs:?g_kdcState@@3W4KdcState@@A, 0; KdcState g_kdcState
0x18003b5c0  call    ?EnterApiCall@@YAJW4NeededKdcState@@@Z; EnterApiCall(NeededKdcState)
0x18003b5c5  call    ?LeaveApiCall@@YAXXZ; LeaveApiCall(void)
0x18003b5ca  xor     eax, eax
0x18003b5cc  add     rsp, 28h
0x18003b5d0  retn
```
