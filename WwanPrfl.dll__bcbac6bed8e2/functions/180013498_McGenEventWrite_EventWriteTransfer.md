# McGenEventWrite_EventWriteTransfer

- ea: `0x180013498`
- end: `0x1800134f2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `90`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800134f8`

## callees

- `0x180013498`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800134e7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800134e7`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  __int64 *v5; // rcx
  ULONG v6; // edx

  v5 = (__int64 *)off_18001F008;
  if ( off_18001F008 )
  {
    UserData->Ptr = (ULONGLONG)off_18001F008;
    v6 = 2;
    LODWORD(v5) = *(unsigned __int16 *)v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EventWriteTransfer(WwanControlGuid_Context, &WwanMem_c34, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x180013498  sub     rsp, 38h
0x18001349c  mov     rcx, cs:off_18001F008
0x1800134a3  mov     r8d, 2
0x1800134a9  mov     rax, [rsp+38h+arg_20]
0x1800134ae  test    rcx, rcx
0x1800134b1  jnz     short loc_1800134BA
0x1800134b3  mov     [rax], rcx
0x1800134b6  xor     edx, edx
0x1800134b8  jmp     short loc_1800134C3
0x1800134ba  mov     [rax], rcx
0x1800134bd  mov     edx, r8d
0x1800134c0  movzx   ecx, word ptr [rcx]
0x1800134c3  mov     [rax+8], ecx
0x1800134c6  xor     r9d, r9d; RelatedActivityId
0x1800134c9  mov     [rax+0Ch], edx
0x1800134cc  lea     rdx, WwanMem_c34; EventDescriptor
0x1800134d3  mov     rcx, cs:WwanControlGuid_Context; RegHandle
0x1800134da  mov     [rsp+38h+UserData], rax; UserData
0x1800134df  mov     [rsp+38h+UserDataCount], r8d; UserDataCount
0x1800134e4  xor     r8d, r8d; ActivityId
0x1800134e7  call    cs:__imp_EventWriteTransfer
0x1800134ed  add     rsp, 38h
0x1800134f1  retn
```
