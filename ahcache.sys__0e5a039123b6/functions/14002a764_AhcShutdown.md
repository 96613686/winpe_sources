# AhcShutdown

- ea: `0x14002a764`
- end: `0x14002a890`
- name: `AhcShutdown`
- size: `300`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14002c890`
- `0x14002cae0`

## callees

- `0x140027af4`
- `0x140029320`
- `0x14002a6b4`
- `0x14002a764`
- `0x14002ade8`
- `0x14002bd74`
- `0x14003e364`
- `0x140045d44`
- `0x1400552bc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14002a829`
- `ntoskrnl!ZwClose` at `0x14002a829`

## string_xrefs

- `0x14002a79d`: `Failed to save cache data to registry [%x]`

## pseudocode

```c
__int64 __fastcall AhcShutdown(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // edi
  __int64 v4; // rcx
  __int64 v5; // rcx
  REGHANDLE *v6; // rcx
  struct _ERESOURCE *v7; // rcx
  struct _ERESOURCE *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rdx

  AslLogCallPrintf(3, "AhcShutdown", 370, "Enter.");
  v2 = AhcPersist(a1);
  v3 = v2;
  if ( v2 >= 0 )
    v3 = 0;
  else
    AslLogCallPrintf(1, "AhcShutdown", 385, "Failed to save cache data to registry [%x]", v2);
  v4 = *(_QWORD *)(a1 + 24);
  if ( v4 )
  {
    AhcCacheDelete(v4);
    *(_QWORD *)(a1 + 24) = 0;
  }
  v5 = *(_QWORD *)(a1 + 32);
  if ( v5 )
  {
    AhcCdbDelete(v5);
    *(_QWORD *)(a1 + 32) = 0;
  }
  v6 = *(REGHANDLE **)(a1 + 104);
  if ( v6 )
  {
    AhcSdbQueryDelete(v6);
    *(_QWORD *)(a1 + 104) = 0;
  }
  v7 = *(struct _ERESOURCE **)(a1 + 720);
  if ( v7 )
  {
    AhcLockDelete(v7);
    *(_QWORD *)(a1 + 720) = 0;
  }
  if ( *(_QWORD *)a1 )
  {
    ZwClose(*(HANDLE *)a1);
    *(_QWORD *)a1 = 0;
  }
  v8 = *(struct _ERESOURCE **)(a1 + 16);
  if ( v8 )
    AhcLockDelete(v8);
  CitmShutdown(a1);
  v10 = *(_QWORD *)(a1 + 688);
  if ( v10 )
  {
    AslFree(v9, v10);
    *(_QWORD *)(a1 + 688) = 0;
  }
  if ( !*(_DWORD *)(a1 + 704) )
    g_AslLogPfnVPrintf = 0;
  return v3;
}

```

## disassembly

```asm
0x14002a764  mov     [rsp+arg_0], rbx
0x14002a769  push    rdi
0x14002a76a  sub     rsp, 30h
0x14002a76e  mov     rbx, rcx
0x14002a771  lea     r9, aEnter; "Enter."
0x14002a778  mov     ecx, 3
0x14002a77d  lea     rdx, aAhcshutdown; "AhcShutdown"
0x14002a784  mov     r8d, 172h
0x14002a78a  call    AslLogCallPrintf
0x14002a78f  mov     rcx, rbx
0x14002a792  call    AhcPersist
0x14002a797  mov     edi, eax
0x14002a799  test    eax, eax
0x14002a79b  jns     short loc_14002A7C1
0x14002a79d  lea     r9, aFailedToSaveCa; "Failed to save cache data to registry ["...
0x14002a7a4  mov     [rsp+38h+var_18], eax
0x14002a7a8  mov     r8d, 181h
0x14002a7ae  lea     rdx, aAhcshutdown; "AhcShutdown"
0x14002a7b5  mov     ecx, 1
0x14002a7ba  call    AslLogCallPrintf
0x14002a7bf  jmp     short loc_14002A7C3
0x14002a7c1  xor     edi, edi
0x14002a7c3  mov     rcx, [rbx+18h]
0x14002a7c7  test    rcx, rcx
0x14002a7ca  jz      short loc_14002A7D9
0x14002a7cc  call    AhcCacheDelete
0x14002a7d1  mov     qword ptr [rbx+18h], 0
0x14002a7d9  mov     rcx, [rbx+20h]
0x14002a7dd  test    rcx, rcx
0x14002a7e0  jz      short loc_14002A7EF
0x14002a7e2  call    AhcCdbDelete
0x14002a7e7  mov     qword ptr [rbx+20h], 0
0x14002a7ef  mov     rcx, [rbx+68h]
0x14002a7f3  test    rcx, rcx
0x14002a7f6  jz      short loc_14002A805
0x14002a7f8  call    AhcSdbQueryDelete
0x14002a7fd  mov     qword ptr [rbx+68h], 0
0x14002a805  mov     rcx, [rbx+2D0h]; void *
0x14002a80c  test    rcx, rcx
0x14002a80f  jz      short loc_14002A821
0x14002a811  call    AhcLockDelete
0x14002a816  mov     qword ptr [rbx+2D0h], 0
0x14002a821  mov     rcx, [rbx]; Handle
0x14002a824  test    rcx, rcx
0x14002a827  jz      short loc_14002A83C
0x14002a829  call    cs:__imp_ZwClose
0x14002a830  nop     dword ptr [rax+rax+00h]
0x14002a835  mov     qword ptr [rbx], 0
0x14002a83c  mov     rcx, [rbx+10h]; void *
0x14002a840  test    rcx, rcx
0x14002a843  jz      short loc_14002A84A
0x14002a845  call    AhcLockDelete
0x14002a84a  mov     rcx, rbx
0x14002a84d  call    CitmShutdown
0x14002a852  mov     rdx, [rbx+2B0h]
0x14002a859  test    rdx, rdx
0x14002a85c  jz      short loc_14002A86E
0x14002a85e  call    AslFree
0x14002a863  mov     qword ptr [rbx+2B0h], 0
0x14002a86e  cmp     dword ptr [rbx+2C0h], 0
0x14002a875  jnz     short loc_14002A882
0x14002a877  mov     cs:g_AslLogPfnVPrintf, 0
0x14002a882  mov     rbx, [rsp+38h+arg_0]
0x14002a887  mov     eax, edi
0x14002a889  add     rsp, 30h
0x14002a88d  pop     rdi
0x14002a88e  retn
```
