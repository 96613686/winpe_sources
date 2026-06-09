# Service_Release(void)

- ea: `0x180002a70`
- end: `0x180002afa`
- name: `?Service_Release@@YAJXZ`
- size: `138`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800018c0`
- `0x1800027c0`
- `0x1800069d0`
- `0x18000e260`
- `0x18000e360`

## callees

- `0x180002a70`
- `0x180007f28`
- `0x18000dfd4`

## pseudocode

```c
__int64 Service_Release(void)
{
  unsigned __int32 v0; // ebx

  if ( g_RefCount <= 0
    && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids);
  }
  v0 = _InterlockedDecrement(&g_RefCount);
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v0);
  }
  return v0;
}

```

## disassembly

```asm
0x180002a70  mov     [rsp+arg_0], rbx
0x180002a75  push    rdi
0x180002a76  sub     rsp, 20h
0x180002a7a  cmp     cs:?g_RefCount@@3JA, 0; long g_RefCount
0x180002a81  lea     rdi, WPP_GLOBAL_Control
0x180002a88  jg      short loc_180002AB1
0x180002a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a91  cmp     rcx, rdi
0x180002a94  jz      short loc_180002AB1
0x180002a96  test    byte ptr [rcx+1Ch], 2
0x180002a9a  jz      short loc_180002AB1
0x180002a9c  mov     rcx, [rcx+10h]
0x180002aa0  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180002aa7  mov     edx, 13h
0x180002aac  call    WPP_SF_
0x180002ab1  mov     ebx, 0FFFFFFFFh
0x180002ab6  lock xadd cs:?g_RefCount@@3JA, ebx; long g_RefCount
0x180002abe  dec     ebx
0x180002ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ac7  cmp     rcx, rdi
0x180002aca  jz      short loc_180002AED
0x180002acc  test    dword ptr [rcx+1Ch], 200h
0x180002ad3  jz      short loc_180002AED
0x180002ad5  mov     rcx, [rcx+10h]
0x180002ad9  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180002ae0  mov     edx, 14h
0x180002ae5  mov     r9d, ebx
0x180002ae8  call    WPP_SF_d
0x180002aed  mov     eax, ebx
0x180002aef  mov     rbx, [rsp+28h+arg_0]
0x180002af4  add     rsp, 20h
0x180002af8  pop     rdi
0x180002af9  retn
```
