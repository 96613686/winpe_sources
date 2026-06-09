# MsvpUpdateSharedConfiguration

- ea: `0x18000a480`
- end: `0x18000a4e9`
- name: `MsvpUpdateSharedConfiguration`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x180001d24`
- `0x18000a480`

## string_xrefs

- `0x18000a4bd`: `MsvpUpdateSharedConfiguration`

## pseudocode

```c
__int64 __fastcall MsvpUpdateSharedConfiguration(__int64 *a1, int *a2)
{
  __int64 v2; // rax
  int v4; // eax

  if ( !a1 || !a2 )
    return 3221225485LL;
  v2 = *a1;
  *(_QWORD *)a2 = *a1;
  if ( GlobalConfig )
  {
    v4 = 4;
    a2[1] = 1;
    if ( (unsigned int)*a2 > 4 )
      v4 = *a2;
    *a2 = v4;
    GlobalSharedConfig = *(_QWORD *)a2;
    NtlmTraceInfoViaWpp("MsvpUpdateSharedConfiguration", 0x28u, "NtlmSuccess");
  }
  else
  {
    GlobalSharedConfig = v2;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a480  sub     rsp, 28h
0x18000a484  test    rcx, rcx
0x18000a487  jz      short loc_18000A4DF
0x18000a489  test    rdx, rdx
0x18000a48c  jz      short loc_18000A4DF
0x18000a48e  mov     rax, [rcx]
0x18000a491  mov     [rdx], rax
0x18000a494  cmp     dword ptr cs:?GlobalConfig@@3U_NtlmGlobalConfiguration@@A, 0; _NtlmGlobalConfiguration GlobalConfig
0x18000a49b  jnz     short loc_18000A4A8
0x18000a49d  mov     cs:?GlobalSharedConfig@@3U_NtlmSharedConfiguration@@A, rax; _NtlmSharedConfiguration GlobalSharedConfig
0x18000a4a4  xor     eax, eax
0x18000a4a6  jmp     short loc_18000A4E4
0x18000a4a8  mov     eax, 4
0x18000a4ad  mov     dword ptr [rdx+4], 1
0x18000a4b4  cmp     [rdx], eax
0x18000a4b6  lea     r8, aNtlmsuccess; "NtlmSuccess"
0x18000a4bd  lea     rcx, aMsvpupdateshar_0; "MsvpUpdateSharedConfiguration"
0x18000a4c4  cmova   eax, [rdx]
0x18000a4c7  mov     [rdx], eax
0x18000a4c9  mov     rax, [rdx]
0x18000a4cc  mov     edx, 28h ; '('; unsigned int
0x18000a4d1  mov     cs:?GlobalSharedConfig@@3U_NtlmSharedConfiguration@@A, rax; _NtlmSharedConfiguration GlobalSharedConfig
0x18000a4d8  call    ?NtlmTraceInfoViaWpp@@YAXPEBDK0@Z; NtlmTraceInfoViaWpp(char const *,ulong,char const *)
0x18000a4dd  jmp     short loc_18000A4A4
0x18000a4df  mov     eax, 0C000000Dh
0x18000a4e4  add     rsp, 28h
0x18000a4e8  retn
```
