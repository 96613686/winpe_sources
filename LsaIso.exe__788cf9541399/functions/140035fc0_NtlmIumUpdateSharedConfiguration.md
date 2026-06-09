# NtlmIumUpdateSharedConfiguration

- ea: `0x140035fc0`
- end: `0x140036031`
- name: `NtlmIumUpdateSharedConfiguration`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x140035fc0`
- `0x140036038`
- `0x140036080`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140035fd7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140035fd7`
- `NtlmShared!MsvpUpdateSharedConfiguration` at `0x140035ff4`
- `NtlmShared!MsvpUpdateSharedConfiguration` at `0x140035ff4`

## string_xrefs

- `0x140035fff`: `NtlmIumUpdateSharedConfiguration`

## pseudocode

```c
__int64 __fastcall NtlmIumUpdateSharedConfiguration(__int64 a1, __int64 a2, __int64 a3)
{
  int updated; // eax
  const char *v5; // r8
  unsigned int v6; // ebx

  if ( qword_140052C50 == a1 )
  {
    if ( a2 && a3 )
    {
      updated = MsvpUpdateSharedConfiguration(a2, a3);
      v6 = updated;
      if ( updated < 0 )
        NtlmTraceErrorWithStatusViaWpp("NtlmIumUpdateSharedConfiguration", 0x55Au, "NtlmFailure", updated);
      else
        NtlmTraceInfoViaWpp("NtlmIumUpdateSharedConfiguration", 0x55Au, v5);
      return v6;
    }
    else
    {
      return 3221225485LL;
    }
  }
  else
  {
    Sleep(5u);
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x140035fc0  push    rbx
0x140035fc2  sub     rsp, 20h
0x140035fc6  cmp     cs:qword_140052C50, rcx
0x140035fcd  mov     rax, rdx
0x140035fd0  jz      short loc_140035FE4
0x140035fd2  mov     ecx, 5; dwMilliseconds
0x140035fd7  call    cs:__imp_Sleep
0x140035fdd  mov     eax, 0C0000022h
0x140035fe2  jmp     short loc_14003602B
0x140035fe4  test    rax, rax
0x140035fe7  jz      short loc_140036026
0x140035fe9  test    r8, r8
0x140035fec  jz      short loc_140036026
0x140035fee  mov     rdx, r8
0x140035ff1  mov     rcx, rax
0x140035ff4  call    cs:__imp_MsvpUpdateSharedConfiguration
0x140035ffa  mov     edx, 55Ah; unsigned int
0x140035fff  lea     rcx, aNtlmiumupdates; "NtlmIumUpdateSharedConfiguration"
0x140036006  mov     ebx, eax
0x140036008  test    eax, eax
0x14003600a  js      short loc_140036013
0x14003600c  call    ?NtlmTraceInfoViaWpp@@YAXPEBDK0@Z; NtlmTraceInfoViaWpp(char const *,ulong,char const *)
0x140036011  jmp     short loc_140036022
0x140036013  mov     r9d, ebx; int
0x140036016  lea     r8, aNtlmfailure; "NtlmFailure"
0x14003601d  call    ?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z; NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)
0x140036022  mov     eax, ebx
0x140036024  jmp     short loc_14003602B
0x140036026  mov     eax, 0C000000Dh
0x14003602b  add     rsp, 20h
0x14003602f  pop     rbx
0x140036030  retn
```
