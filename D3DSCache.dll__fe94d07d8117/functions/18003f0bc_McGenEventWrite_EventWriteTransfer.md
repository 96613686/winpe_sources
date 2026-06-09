# McGenEventWrite_EventWriteTransfer

- ea: `0x18003f0bc`
- end: `0x18003f10e`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f410`
- `0x180020f90`
- `0x18003cbb8`
- `0x18003efe8`
- `0x18003f040`
- `0x180046d0c`
- `0x180046d7c`
- `0x180046e00`
- `0x180046e58`
- `0x180046ef8`
- `0x180046fb8`
- `0x180047028`
- `0x180047098`
- `0x180049d98`
- `0x18004f2d4`
- `0x180050324`
- `0x180050438`

## callees

- `0x18003f0bc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003f103`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003f103`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_1800C64E8;
  if ( qword_1800C64E8 )
  {
    UserData->Ptr = qword_1800C64E8;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EventWriteTransfer(D3DShaderCacheEtwProviderGuid_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18003f0bc  sub     rsp, 38h
0x18003f0c0  mov     rcx, cs:qword_1800C64E8
0x18003f0c7  mov     rax, [rsp+38h+arg_20]
0x18003f0cc  test    rcx, rcx
0x18003f0cf  jnz     short loc_18003F0D9
0x18003f0d1  mov     [rax], rcx
0x18003f0d4  xor     r8d, r8d
0x18003f0d7  jmp     short loc_18003F0E5
0x18003f0d9  mov     [rax], rcx
0x18003f0dc  mov     r8d, 2
0x18003f0e2  movzx   ecx, word ptr [rcx]
0x18003f0e5  mov     [rax+8], ecx
0x18003f0e8  mov     [rax+0Ch], r8d
0x18003f0ec  xor     r8d, r8d; ActivityId
0x18003f0ef  mov     rcx, cs:D3DShaderCacheEtwProviderGuid_Context; RegHandle
0x18003f0f6  mov     [rsp+38h+UserData], rax; UserData
0x18003f0fb  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18003f100  xor     r9d, r9d; RelatedActivityId
0x18003f103  call    cs:__imp_EventWriteTransfer
0x18003f109  add     rsp, 38h
0x18003f10d  retn
```
