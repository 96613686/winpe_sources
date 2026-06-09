# AhcpSdbQueryLookupExe

- ea: `0x140059d78`
- end: `0x140059f5a`
- name: `AhcpSdbQueryLookupExe`
- size: `482`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, __int64, int *, int *, __int64, __int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14005974c`

## callees

- `0x140038a88`
- `0x140039f80`
- `0x14003e364`
- `0x140045df8`
- `0x140046074`
- `0x140059d78`
- `0x14005a304`

## string_xrefs

- `0x140059e53`: `Failed to get sxs override manifest [%x]`
- `0x140059efd`: `Failed to query installer flags [%x]`

## pseudocode

```c
__int64 __fastcall AhcpSdbQueryLookupExe(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        int *a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        int a13)
{
  int v17; // eax
  int v18; // r8d
  unsigned int v19; // ebx
  int v20; // edx
  int SxsOverrideManifest; // eax
  const char *v22; // r9
  __int64 v23; // r8
  int v24; // r8d
  __int64 v26; // [rsp+20h] [rbp-68h]
  int v27; // [rsp+28h] [rbp-60h]
  PVOID P[9]; // [rsp+40h] [rbp-48h] BYREF

  P[0] = 0;
  v17 = AslFileMappingCreate(P, a10, a11);
  v19 = v17;
  if ( v17 >= 0 )
  {
    v20 = (int)P[0];
    *(_QWORD *)(a9 + 1752) = AhcpSdbQueryLogAttributeCheckResult;
    *(_QWORD *)(a9 + 1744) = AhcpSdbQueryDeviceQuery;
    SdbGetMatchingExeEx(a9, v20, v18, a13, a12, 0, a1);
    SxsOverrideManifest = AhcpSdbQueryGetSxsOverrideManifest(a2, a3, a9, a1);
    v19 = SxsOverrideManifest;
    if ( SxsOverrideManifest >= 0 )
    {
      if ( (unsigned int)SdbQueryFlagMask(a9, a1, 20494, a4) )
      {
        if ( (unsigned int)SdbQueryFlagMask(a9, a1, 20496, a5) )
        {
          if ( (unsigned int)SdbQueryFlagMask(a9, a1, 20497, a6) )
          {
            v24 = (*((_DWORD *)a1 + 48) >> 15) & 1;
            *a7 = (*((_DWORD *)a1 + 48) >> 5) & 1;
            v19 = 0;
            *a8 = v24;
            goto LABEL_13;
          }
          SxsOverrideManifest = -1073741480;
          v22 = "Failed to query installer flags [%x]";
          v19 = -1073741480;
          v23 = 822;
        }
        else
        {
          SxsOverrideManifest = -1073741480;
          v22 = "Failed to query runlevel flags [%x]";
          v19 = -1073741480;
          v23 = 813;
        }
      }
      else
      {
        SxsOverrideManifest = -1073741480;
        v22 = "Failed to query fusion flags [%x]";
        v19 = -1073741480;
        v23 = 803;
      }
    }
    else
    {
      v22 = "Failed to get sxs override manifest [%x]";
      v23 = 793;
    }
    LODWORD(v26) = SxsOverrideManifest;
    AslLogCallPrintf(1, "AhcpSdbQueryLookupExe", v23, v22, v26);
  }
  else
  {
    v27 = v17;
    AslLogCallPrintf(1, "AhcpSdbQueryLookupExe", 756, "Failed to initialize file mapping %ws [%x]", a10, v27);
  }
LABEL_13:
  AslFileMappingDelete(P[0]);
  return v19;
}

```

## disassembly

```asm
0x140059d78  push    rbx
0x140059d7a  push    rbp
0x140059d7b  push    rsi
0x140059d7c  push    rdi
0x140059d7d  push    r14
0x140059d7f  push    r15
0x140059d81  sub     rsp, 58h
0x140059d85  mov     rsi, [rsp+88h+arg_48]
0x140059d8d  mov     r14, r8
0x140059d90  mov     r8, [rsp+88h+arg_50]
0x140059d98  mov     r15, rdx
0x140059d9b  mov     rdi, rcx
0x140059d9e  mov     [rsp+88h+P], 0
0x140059da7  mov     rdx, rsi
0x140059daa  lea     rcx, [rsp+88h+P]
0x140059daf  mov     rbp, r9
0x140059db2  call    AslFileMappingCreate
0x140059db7  mov     ebx, eax
0x140059db9  test    eax, eax
0x140059dbb  jns     short loc_140059DE9
0x140059dbd  mov     [rsp+88h+var_60], eax
0x140059dc1  lea     r9, aFailedToInitia_11; "Failed to initialize file mapping %ws ["...
0x140059dc8  mov     r8d, 2F4h
0x140059dce  mov     [rsp+88h+var_68], rsi
0x140059dd3  lea     rdx, aAhcpsdbquerylo_2; "AhcpSdbQueryLookupExe"
0x140059dda  mov     ecx, 1
0x140059ddf  call    AslLogCallPrintf
0x140059de4  jmp     loc_140059F40
0x140059de9  mov     rsi, [rsp+88h+arg_40]
0x140059df1  lea     rax, AhcpSdbQueryLogAttributeCheckResult
0x140059df8  mov     r9, qword ptr [rsp+88h+arg_60]; int
0x140059e00  mov     rcx, rsi; int
0x140059e03  mov     rdx, [rsp+88h+P]; int
0x140059e08  mov     [rsp+88h+var_58], rdi; void *
0x140059e0d  mov     [rsi+6D8h], rax
0x140059e14  lea     rax, AhcpSdbQueryDeviceQuery
0x140059e1b  mov     [rsi+6D0h], rax
0x140059e22  mov     rax, [rsp+88h+arg_58]
0x140059e2a  mov     [rsp+88h+var_60], 0; int
0x140059e32  mov     [rsp+88h+var_68], rax; __int64
0x140059e37  call    SdbGetMatchingExeEx
0x140059e3c  mov     r9, rdi
0x140059e3f  mov     r8, rsi
0x140059e42  mov     rdx, r14
0x140059e45  mov     rcx, r15
0x140059e48  call    AhcpSdbQueryGetSxsOverrideManifest
0x140059e4d  mov     ebx, eax
0x140059e4f  test    eax, eax
0x140059e51  jns     short loc_140059E7A
0x140059e53  lea     r9, aFailedToGetSxs_0; "Failed to get sxs override manifest [%x"...
0x140059e5a  mov     r8d, 319h
0x140059e60  lea     rdx, aAhcpsdbquerylo_2; "AhcpSdbQueryLookupExe"
0x140059e67  mov     dword ptr [rsp+88h+var_68], eax
0x140059e6b  mov     ecx, 1
0x140059e70  call    AslLogCallPrintf
0x140059e75  jmp     loc_140059F40
0x140059e7a  mov     r8d, 500Eh
0x140059e80  mov     r9, rbp
0x140059e83  mov     rdx, rdi
0x140059e86  mov     rcx, rsi
0x140059e89  call    SdbQueryFlagMask
0x140059e8e  test    eax, eax
0x140059e90  jnz     short loc_140059EA8
0x140059e92  mov     eax, 0C0000158h
0x140059e97  lea     r9, aFailedToQueryF_1; "Failed to query fusion flags [%x]"
0x140059e9e  mov     ebx, eax
0x140059ea0  mov     r8d, 323h
0x140059ea6  jmp     short loc_140059E60
0x140059ea8  mov     r9, [rsp+88h+arg_20]
0x140059eb0  mov     r8d, 5010h
0x140059eb6  mov     rdx, rdi
0x140059eb9  mov     rcx, rsi
0x140059ebc  call    SdbQueryFlagMask
0x140059ec1  test    eax, eax
0x140059ec3  jnz     short loc_140059EDB
0x140059ec5  mov     eax, 0C0000158h
0x140059eca  lea     r9, aFailedToQueryR; "Failed to query runlevel flags [%x]"
0x140059ed1  mov     ebx, eax
0x140059ed3  mov     r8d, 32Dh
0x140059ed9  jmp     short loc_140059E60
0x140059edb  mov     r9, [rsp+88h+arg_28]
0x140059ee3  mov     r8d, 5011h
0x140059ee9  mov     rdx, rdi
0x140059eec  mov     rcx, rsi
0x140059eef  call    SdbQueryFlagMask
0x140059ef4  test    eax, eax
0x140059ef6  jnz     short loc_140059F11
0x140059ef8  mov     eax, 0C0000158h
0x140059efd  lea     r9, aFailedToQueryI; "Failed to query installer flags [%x]"
0x140059f04  mov     ebx, eax
0x140059f06  mov     r8d, 336h
0x140059f0c  jmp     loc_140059E60
0x140059f11  mov     r8d, [rdi+0C0h]
0x140059f18  mov     edx, r8d
0x140059f1b  mov     rax, [rsp+88h+arg_30]
0x140059f23  shr     edx, 5
0x140059f26  and     edx, 1
0x140059f29  shr     r8d, 0Fh
0x140059f2d  and     r8d, 1
0x140059f31  mov     [rax], edx
0x140059f33  xor     ebx, ebx
0x140059f35  mov     rax, [rsp+88h+arg_38]
0x140059f3d  mov     [rax], r8d
0x140059f40  mov     rcx, [rsp+88h+P]; P
0x140059f45  call    AslFileMappingDelete
0x140059f4a  mov     eax, ebx
0x140059f4c  add     rsp, 58h
0x140059f50  pop     r15
0x140059f52  pop     r14
0x140059f54  pop     rdi
0x140059f55  pop     rsi
0x140059f56  pop     rbp
0x140059f57  pop     rbx
0x140059f58  retn
```
