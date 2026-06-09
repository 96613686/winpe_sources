# AhcPersist

- ea: `0x14002a6b4`
- end: `0x14002a75b`
- name: `AhcPersist`
- size: `167`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14002a764`
- `0x14002c7f0`

## callees

- `0x1400256f8`
- `0x140025ea8`
- `0x140027d34`
- `0x14002a6b4`
- `0x14003e364`

## string_xrefs

- `0x14002a6ed`: `Failed to save statistics and cache to registry [%x]`
- `0x14002a71f`: `Failed to save cdb store to registry [%x]`
- `0x14002a73c`: `Failed to save sdb timestamp to registry [%x]`

## pseudocode

```c
__int64 __fastcall AhcPersist(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 v5; // r8
  int v7; // [rsp+20h] [rbp-18h]

  AslLogCallPrintf(3, "AhcPersist", 297, "Enter.");
  v2 = AhcCacheWriteRegistry(a1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v2 = AhcCdbWriteRegistry(a1);
    v3 = v2;
    if ( v2 >= 0 )
    {
      v2 = AhcCdbPersistTimeStamps(a1);
      v3 = v2;
      if ( v2 >= 0 )
        return 0;
      v4 = "Failed to save sdb timestamp to registry [%x]";
      v5 = 330;
    }
    else
    {
      v4 = "Failed to save cdb store to registry [%x]";
      v5 = 323;
    }
  }
  else
  {
    v4 = "Failed to save statistics and cache to registry [%x]";
    v5 = 312;
  }
  v7 = v2;
  AslLogCallPrintf(1, "AhcPersist", v5, v4, v7);
  return v3;
}

```

## disassembly

```asm
0x14002a6b4  mov     [rsp+arg_0], rbx
0x14002a6b9  push    rdi
0x14002a6ba  sub     rsp, 30h
0x14002a6be  mov     rdi, rcx
0x14002a6c1  lea     r9, aEnter; "Enter."
0x14002a6c8  mov     ecx, 3
0x14002a6cd  lea     rdx, aAhcpersist; "AhcPersist"
0x14002a6d4  mov     r8d, 129h
0x14002a6da  call    AslLogCallPrintf
0x14002a6df  mov     rcx, rdi
0x14002a6e2  call    AhcCacheWriteRegistry
0x14002a6e7  mov     ebx, eax
0x14002a6e9  test    eax, eax
0x14002a6eb  jns     short loc_14002A711
0x14002a6ed  lea     r9, aFailedToSaveSt_1; "Failed to save statistics and cache to "...
0x14002a6f4  mov     r8d, 138h
0x14002a6fa  lea     rdx, aAhcpersist; "AhcPersist"
0x14002a701  mov     [rsp+38h+var_18], eax
0x14002a705  mov     ecx, 1
0x14002a70a  call    AslLogCallPrintf
0x14002a70f  jmp     short loc_14002A74D
0x14002a711  mov     rcx, rdi
0x14002a714  call    AhcCdbWriteRegistry
0x14002a719  mov     ebx, eax
0x14002a71b  test    eax, eax
0x14002a71d  jns     short loc_14002A72E
0x14002a71f  lea     r9, aFailedToSaveCd_0; "Failed to save cdb store to registry [%"...
0x14002a726  mov     r8d, 143h
0x14002a72c  jmp     short loc_14002A6FA
0x14002a72e  mov     rcx, rdi
0x14002a731  call    AhcCdbPersistTimeStamps
0x14002a736  mov     ebx, eax
0x14002a738  test    eax, eax
0x14002a73a  jns     short loc_14002A74B
0x14002a73c  lea     r9, aFailedToSaveSd; "Failed to save sdb timestamp to registr"...
0x14002a743  mov     r8d, 14Ah
0x14002a749  jmp     short loc_14002A6FA
0x14002a74b  xor     ebx, ebx
0x14002a74d  mov     eax, ebx
0x14002a74f  mov     rbx, [rsp+38h+arg_0]
0x14002a754  add     rsp, 30h
0x14002a758  pop     rdi
0x14002a759  retn
```
