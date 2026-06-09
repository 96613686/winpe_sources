# AhcApiClear

- ea: `0x14002b128`
- end: `0x14002b25f`
- name: `AhcApiClear`
- size: `311`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400497bc`

## callees

- `0x1400256f8`
- `0x140025ea8`
- `0x1400260f8`
- `0x140027d34`
- `0x140029954`
- `0x14002b128`
- `0x14003e364`
- `0x1400438c4`
- `0x140045d6c`

## string_xrefs

- `0x14002b215`: `Failed to save cdb store to registry [%x]`
- `0x14002b235`: `Failed to save sdb timestamp to registry [%x]`
- `0x14002b140`: `Failed to pass security check [%x]`
- `0x14002b1a7`: `Failed to write cache to registry [%x]`

## pseudocode

```c
__int64 __fastcall AhcApiClear(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 v5; // r8
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  int v10; // [rsp+20h] [rbp-38h]
  __int128 v11; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+40h] [rbp-18h]

  v2 = AhcVerifyAdminContext();
  v3 = v2;
  if ( v2 >= 0 )
  {
    v6 = *(_QWORD *)(a1 + 24);
    if ( v6 )
      AhcCacheClear(v6, 0xFFFFFFFFLL);
    v7 = *(_DWORD *)(a1 + 56);
    *(_OWORD *)(a1 + 40) = 0;
    *(_OWORD *)(a1 + 56) = 0;
    *(_OWORD *)(a1 + 72) = 0;
    *(_DWORD *)(a1 + 88) = 0;
    *(_DWORD *)(a1 + 40) = 52;
    *(_DWORD *)(a1 + 56) = v7;
    v2 = AhcCacheWriteRegistry(a1);
    v3 = v2;
    if ( v2 >= 0 )
    {
      if ( *(_QWORD *)(a1 + 24) )
      {
        v11 = 0;
        DWORD1(v11) = 1;
        v12 = 0;
        AhcCheckForChange(a1, &v11);
      }
      v8 = *(_QWORD *)(a1 + 32);
      if ( v8 )
      {
        v2 = AhcCdbRefresh(v8);
        v3 = v2;
        if ( v2 < 0 )
        {
          v4 = "Failed to refresh cdb store [%x]";
          v5 = 1055;
          goto LABEL_3;
        }
        v2 = AhcCdbWriteRegistry(a1);
        v3 = v2;
        if ( v2 < 0 )
        {
          v4 = "Failed to save cdb store to registry [%x]";
          v5 = 1065;
          goto LABEL_3;
        }
        v2 = AhcCdbPersistTimeStamps(a1);
        v3 = v2;
        if ( v2 < 0 )
        {
          v4 = "Failed to save sdb timestamp to registry [%x]";
          v5 = 1071;
          goto LABEL_3;
        }
      }
      *(_QWORD *)(a1 + 112) = 3600000;
      return 0;
    }
    v4 = "Failed to write cache to registry [%x]";
    v5 = 1042;
  }
  else
  {
    v4 = "Failed to pass security check [%x]";
    v5 = 1007;
  }
LABEL_3:
  v10 = v2;
  AslLogCallPrintf(1, "AhcApiClear", v5, v4, v10);
  return v3;
}

```

## disassembly

```asm
0x14002b128  mov     [rsp+arg_0], rbx
0x14002b12d  push    rdi
0x14002b12e  sub     rsp, 50h
0x14002b132  mov     rdi, rcx
0x14002b135  call    AhcVerifyAdminContext
0x14002b13a  mov     ebx, eax
0x14002b13c  test    eax, eax
0x14002b13e  jns     short loc_14002B167
0x14002b140  lea     r9, aFailedToPassSe; "Failed to pass security check [%x]"
0x14002b147  mov     r8d, 3EFh
0x14002b14d  lea     rdx, aAhcapiclear; "AhcApiClear"
0x14002b154  mov     [rsp+58h+var_38], eax
0x14002b158  mov     ecx, 1
0x14002b15d  call    AslLogCallPrintf
0x14002b162  jmp     loc_14002B251
0x14002b167  mov     rcx, [rdi+18h]
0x14002b16b  test    rcx, rcx
0x14002b16e  jz      short loc_14002B178
0x14002b170  or      edx, 0FFFFFFFFh
0x14002b173  call    AhcCacheClear
0x14002b178  mov     eax, [rdi+38h]
0x14002b17b  xorps   xmm0, xmm0
0x14002b17e  movups  xmmword ptr [rdi+28h], xmm0
0x14002b182  xor     ecx, ecx
0x14002b184  movups  xmmword ptr [rdi+38h], xmm0
0x14002b188  movups  xmmword ptr [rdi+48h], xmm0
0x14002b18c  mov     [rdi+58h], ecx
0x14002b18f  mov     rcx, rdi
0x14002b192  mov     dword ptr [rdi+28h], 34h ; '4'
0x14002b199  mov     [rdi+38h], eax
0x14002b19c  call    AhcCacheWriteRegistry
0x14002b1a1  mov     ebx, eax
0x14002b1a3  test    eax, eax
0x14002b1a5  jns     short loc_14002B1B6
0x14002b1a7  lea     r9, aFailedToWriteC; "Failed to write cache to registry [%x]"
0x14002b1ae  mov     r8d, 412h
0x14002b1b4  jmp     short loc_14002B14D
0x14002b1b6  cmp     qword ptr [rdi+18h], 0
0x14002b1bb  jz      short loc_14002B1E1
0x14002b1bd  xorps   xmm0, xmm0
0x14002b1c0  lea     rdx, [rsp+58h+var_28]
0x14002b1c5  xor     eax, eax
0x14002b1c7  mov     rcx, rdi
0x14002b1ca  movups  [rsp+58h+var_28], xmm0
0x14002b1cf  mov     dword ptr [rsp+58h+var_28+4], 1
0x14002b1d7  mov     [rsp+58h+var_18], rax
0x14002b1dc  call    AhcCheckForChange
0x14002b1e1  mov     rcx, [rdi+20h]
0x14002b1e5  test    rcx, rcx
0x14002b1e8  jz      short loc_14002B247
0x14002b1ea  call    AhcCdbRefresh
0x14002b1ef  mov     ebx, eax
0x14002b1f1  test    eax, eax
0x14002b1f3  jns     short loc_14002B207
0x14002b1f5  lea     r9, aFailedToRefres; "Failed to refresh cdb store [%x]"
0x14002b1fc  mov     r8d, 41Fh
0x14002b202  jmp     loc_14002B14D
0x14002b207  mov     rcx, rdi
0x14002b20a  call    AhcCdbWriteRegistry
0x14002b20f  mov     ebx, eax
0x14002b211  test    eax, eax
0x14002b213  jns     short loc_14002B227
0x14002b215  lea     r9, aFailedToSaveCd_0; "Failed to save cdb store to registry [%"...
0x14002b21c  mov     r8d, 429h
0x14002b222  jmp     loc_14002B14D
0x14002b227  mov     rcx, rdi
0x14002b22a  call    AhcCdbPersistTimeStamps
0x14002b22f  mov     ebx, eax
0x14002b231  test    eax, eax
0x14002b233  jns     short loc_14002B247
0x14002b235  lea     r9, aFailedToSaveSd; "Failed to save sdb timestamp to registr"...
0x14002b23c  mov     r8d, 42Fh
0x14002b242  jmp     loc_14002B14D
0x14002b247  mov     qword ptr [rdi+70h], 36EE80h
0x14002b24f  xor     ebx, ebx
0x14002b251  mov     eax, ebx
0x14002b253  mov     rbx, [rsp+58h+arg_0]
0x14002b258  add     rsp, 50h
0x14002b25c  pop     rdi
0x14002b25d  retn
```
