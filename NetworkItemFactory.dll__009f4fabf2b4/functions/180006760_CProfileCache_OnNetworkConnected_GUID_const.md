# CProfileCache::OnNetworkConnected(_GUID const *)

- ea: `0x180006760`
- end: `0x1800067aa`
- name: `?OnNetworkConnected@CProfileCache@@UEAAJPEBU_GUID@@@Z`
- size: `74`
- prototype: `__int64 __fastcall(CProfileCache *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000589c`
- `0x180006760`
- `0x180006ef4`

## pseudocode

```c
__int64 __fastcall CProfileCache::OnNetworkConnected(CProfileCache *this, const struct _GUID *a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_cf095e51d6be376dc6c0faef7764f3c8_Traceguids);
  }
  return CProfileCache::_UpdateMapping(this);
}

```

## disassembly

```asm
0x180006760  push    rbx
0x180006762  sub     rsp, 20h
0x180006766  mov     rbx, rcx
0x180006769  mov     rcx, cs:WPP_GLOBAL_Control
0x180006770  lea     rax, WPP_GLOBAL_Control
0x180006777  cmp     rcx, rax
0x18000677a  jz      short loc_18000679D
0x18000677c  cmp     byte ptr [rcx+19h], 4
0x180006780  jb      short loc_18000679D
0x180006782  test    byte ptr [rcx+1Ch], 2
0x180006786  jz      short loc_18000679D
0x180006788  mov     rcx, [rcx+10h]
0x18000678c  lea     r8, WPP_cf095e51d6be376dc6c0faef7764f3c8_Traceguids
0x180006793  mov     edx, 0Bh
0x180006798  call    WPP_SF_
0x18000679d  mov     rcx, rbx; this
0x1800067a0  add     rsp, 20h
0x1800067a4  pop     rbx
0x1800067a5  jmp     ?_UpdateMapping@CProfileCache@@AEAAJXZ; CProfileCache::_UpdateMapping(void)
```
