# AhcCacheCreate

- ea: `0x1400279dc`
- end: `0x140027aee`
- name: `AhcCacheCreate`
- size: `274`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002a3dc`

## callees

- `0x1400275a0`
- `0x1400279dc`
- `0x140027af4`
- `0x14003e364`
- `0x14005498c`
- `0x140054c34`

## string_xrefs

- `0x1400279ea`: `AhcCacheCreate`
- `0x140027a26`: `Failed to allocate memory for cache object`
- `0x140027a9f`: `Failed to create store [%x]`
- `0x140027abc`: `Failed to create cache lock [%x]`

## pseudocode

```c
__int64 __fastcall AhcCacheCreate(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdi
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // r8
  const char *v11; // r9
  __int64 v13; // [rsp+20h] [rbp-48h]

  AslLogCallPrintf(3, "AhcCacheCreate", 1722, "Enter.");
  v6 = AslAlloc(v5, 24, 1);
  v7 = v6;
  if ( v6 )
  {
    *(_QWORD *)(v6 + 16) = a3;
    v9 = AhcStoreCreate(
           (int)v6 + 8,
           1024,
           a3,
           (unsigned int)AhcpCacheEntryAlloc,
           (__int64)AhcpCacheEntryFree,
           (__int64)AhcpCacheEntryCopy,
           (__int64)AhcpCacheEntrySave,
           (__int64)AhcpCacheEntryLoad);
    v8 = v9;
    if ( v9 >= 0 )
    {
      v9 = AhcLockCreate(v7);
      v8 = v9;
      if ( v9 >= 0 )
      {
        *a1 = v7;
        return 0;
      }
      v10 = 1763;
      v11 = "Failed to create cache lock [%x]";
    }
    else
    {
      v10 = 1752;
      v11 = "Failed to create store [%x]";
    }
    LODWORD(v13) = v9;
    AslLogCallPrintf(1, "AhcCacheCreate", v10, v11, v13);
    AhcCacheDelete(v7);
  }
  else
  {
    AslLogCallPrintf(1, "AhcCacheCreate", 1731, "Failed to allocate memory for cache object");
    return (unsigned int)-1073741801;
  }
  return v8;
}

```

## disassembly

```asm
0x1400279dc  push    rbx
0x1400279de  push    rbp
0x1400279df  push    rsi
0x1400279e0  push    rdi
0x1400279e1  push    r14
0x1400279e3  sub     rsp, 40h
0x1400279e7  mov     rbx, r8
0x1400279ea  lea     rbp, aAhccachecreate; "AhcCacheCreate"
0x1400279f1  mov     r14, rcx
0x1400279f4  lea     r9, aEnter; "Enter."
0x1400279fb  mov     rdx, rbp
0x1400279fe  mov     r8d, 6BAh
0x140027a04  mov     ecx, 3
0x140027a09  call    AslLogCallPrintf
0x140027a0e  mov     esi, 1
0x140027a13  mov     r8d, esi
0x140027a16  lea     edx, [rsi+17h]
0x140027a19  call    AslAlloc
0x140027a1e  mov     rdi, rax
0x140027a21  test    rax, rax
0x140027a24  jnz     short loc_140027A47
0x140027a26  lea     r9, aFailedToAlloca_4; "Failed to allocate memory for cache obj"...
0x140027a2d  mov     r8d, 6C3h
0x140027a33  mov     rdx, rbp
0x140027a36  mov     ecx, esi
0x140027a38  call    AslLogCallPrintf
0x140027a3d  mov     ebx, 0C0000017h
0x140027a42  jmp     loc_140027AE0
0x140027a47  mov     [rax+10h], rbx
0x140027a4b  lea     rcx, [rax+8]
0x140027a4f  lea     rax, AhcpCacheEntryLoad
0x140027a56  mov     r8, rbx
0x140027a59  mov     [rsp+68h+var_30], rax
0x140027a5e  lea     r9, AhcpCacheEntryAlloc
0x140027a65  lea     rax, AhcpCacheEntrySave
0x140027a6c  mov     edx, 400h
0x140027a71  mov     [rsp+68h+var_38], rax
0x140027a76  lea     rax, AhcpCacheEntryCopy
0x140027a7d  mov     [rsp+68h+var_40], rax
0x140027a82  lea     rax, AhcpCacheEntryFree
0x140027a89  mov     [rsp+68h+var_48], rax
0x140027a8e  call    AhcStoreCreate
0x140027a93  mov     ebx, eax
0x140027a95  test    eax, eax
0x140027a97  jns     short loc_140027AA8
0x140027a99  mov     r8d, 6D8h
0x140027a9f  lea     r9, aFailedToCreate_10; "Failed to create store [%x]"
0x140027aa6  jmp     short loc_140027AC3
0x140027aa8  mov     rcx, rdi
0x140027aab  call    AhcLockCreate
0x140027ab0  mov     ebx, eax
0x140027ab2  test    eax, eax
0x140027ab4  jns     short loc_140027ADB
0x140027ab6  mov     r8d, 6E3h
0x140027abc  lea     r9, aFailedToCreate_12; "Failed to create cache lock [%x]"
0x140027ac3  mov     rdx, rbp
0x140027ac6  mov     dword ptr [rsp+68h+var_48], eax
0x140027aca  mov     ecx, esi
0x140027acc  call    AslLogCallPrintf
0x140027ad1  mov     rcx, rdi
0x140027ad4  call    AhcCacheDelete
0x140027ad9  jmp     short loc_140027AE0
0x140027adb  mov     [r14], rdi
0x140027ade  xor     ebx, ebx
0x140027ae0  mov     eax, ebx
0x140027ae2  add     rsp, 40h
0x140027ae6  pop     r14
0x140027ae8  pop     rdi
0x140027ae9  pop     rsi
0x140027aea  pop     rbp
0x140027aeb  pop     rbx
0x140027aec  retn
```
