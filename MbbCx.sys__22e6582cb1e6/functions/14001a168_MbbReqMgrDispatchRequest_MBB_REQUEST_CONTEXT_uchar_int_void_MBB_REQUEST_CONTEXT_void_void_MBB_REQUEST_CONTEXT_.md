# MbbReqMgrDispatchRequest(_MBB_REQUEST_CONTEXT *,uchar,int (*)(void *,_MBB_REQUEST_CONTEXT *),void (*)(void *,_MBB_REQUEST_CONTEXT *,int),void (*)(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong))

- ea: `0x14001a168`
- end: `0x14001a200`
- name: `?MbbReqMgrDispatchRequest@@YAHPEAU_MBB_REQUEST_CONTEXT@@EP6AHPEAX0@ZP6AX10H@ZP6AX0HW4_MBB_STATUS@@PEAEK@Z@Z`
- size: `152`
- prototype: `__int64 __fastcall(union _LARGE_INTEGER *, char, int (*)(void *, struct _MBB_REQUEST_CONTEXT *), void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int), void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int))`
- caller_count: `18`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140002024`
- `0x140002278`
- `0x1400024cc`
- `0x140003534`
- `0x140003744`
- `0x140003ab0`
- `0x140003d30`
- `0x140004004`
- `0x14000431c`
- `0x14000459c`
- `0x140004844`
- `0x14000f478`
- `0x140011e94`
- `0x140013c08`
- `0x1400174d8`
- `0x14001ea18`
- `0x14002ec90`
- `0x14002f228`

## callees

- `0x14001a168`
- `0x14001b818`
- `0x14001c328`

## import_xrefs

- `NDIS!NdisGetSystemUpTimeEx` at `0x14001a1a6`
- `NDIS!NdisGetSystemUpTimeEx` at `0x14001a1a6`

## pseudocode

```c
__int64 __fastcall MbbReqMgrDispatchRequest(
        union _LARGE_INTEGER *a1,
        char a2,
        int (*a3)(void *, struct _MBB_REQUEST_CONTEXT *),
        void (*a4)(void *, struct _MBB_REQUEST_CONTEXT *, int),
        void (__high *a5)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int))
{
  if ( a1 && a3 )
  {
    a1[69].QuadPart = (LONGLONG)a5;
    LOBYTE(a1[61].LowPart) = a2;
    a1[67].QuadPart = (LONGLONG)a3;
    a1[68].QuadPart = (LONGLONG)a4;
    BYTE1(a1[61].LowPart) = 0;
    NdisGetSystemUpTimeEx(a1 + 14);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))MbxQueueMessage)((union _LARGE_INTEGER)a1[6].QuadPart, 0, a1);
    return 259;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qq(WPP_GLOBAL_Control->DeviceExtension, a2, (_DWORD)a3, (_DWORD)a4);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14001a168  push    rbx
0x14001a16a  sub     rsp, 40h
0x14001a16e  mov     rbx, rcx
0x14001a171  test    rcx, rcx
0x14001a174  jz      short loc_14001A1CA
0x14001a176  test    r8, r8
0x14001a179  jz      short loc_14001A1CA
0x14001a17b  mov     rax, [rsp+48h+arg_20]
0x14001a180  mov     [rcx+228h], rax
0x14001a187  mov     [rcx+1E8h], dl
0x14001a18d  mov     [rcx+218h], r8
0x14001a194  mov     [rcx+220h], r9
0x14001a19b  mov     byte ptr [rcx+1E9h], 0
0x14001a1a2  add     rcx, 70h ; 'p'; pSystemUpTime
0x14001a1a6  call    cs:__imp_NdisGetSystemUpTimeEx
0x14001a1ad  nop     dword ptr [rax+rax+00h]
0x14001a1b2  mov     rcx, [rbx+30h]
0x14001a1b6  xor     r9d, r9d
0x14001a1b9  mov     r8, rbx
0x14001a1bc  xor     edx, edx
0x14001a1be  call    ?MbxQueueMessage@@YAHPEAU_MBB_REQUEST_MANAGER@@W4MBX_MESSAGE@@PEAX2@Z; MbxQueueMessage(_MBB_REQUEST_MANAGER *,MBX_MESSAGE,void *,void *)
0x14001a1c3  mov     eax, 103h
0x14001a1c8  jmp     short loc_14001A1F9
0x14001a1ca  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a1d1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a1d8  jz      short loc_14001A1F4
0x14001a1da  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a1e1  mov     [rsp+48h+var_18], r8
0x14001a1e6  mov     [rsp+48h+var_20], rbx
0x14001a1eb  mov     rcx, [rcx+40h]
0x14001a1ef  call    WPP_RECORDER_SF_qq
0x14001a1f4  mov     eax, 0C000000Dh
0x14001a1f9  add     rsp, 40h
0x14001a1fd  pop     rbx
0x14001a1fe  retn
```
