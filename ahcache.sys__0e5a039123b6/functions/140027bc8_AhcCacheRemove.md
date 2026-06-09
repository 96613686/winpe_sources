# AhcCacheRemove

- ea: `0x140027bc8`
- end: `0x140027c93`
- name: `AhcCacheRemove`
- size: `203`
- prototype: `__int64 __fastcall(PERESOURCE *, _OWORD *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x14002b850`

## callees

- `0x140027bc8`
- `0x14003e364`
- `0x140043bb0`
- `0x140043f88`
- `0x1400440d8`

## string_xrefs

- `0x140027c12`: `Failed to acquire entry for Update [%x]`
- `0x140027c23`: `AhcCacheRemove`
- `0x140027c59`: `AhcCacheRemove`
- `0x140027c48`: `Failed to Remove entry [%x]`

## pseudocode

```c
__int64 __fastcall AhcCacheRemove(PERESOURCE *a1, _OWORD *a2, void *a3, unsigned int a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  PERESOURCE *v10; // [rsp+30h] [rbp-18h] BYREF
  volatile signed __int32 *v11; // [rsp+38h] [rbp-10h] BYREF

  v10 = 0;
  v11 = 0;
  v6 = AhcpCacheEntryAcquire(&v10, &v11, (__int64)a1, a2, a3, 1);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = AhcpCacheEntryFilter(v10, a4);
    v7 = v8;
    if ( v8 >= 0 )
      v7 = 0;
    else
      AslLogCallPrintf(1, "AhcCacheRemove", 2053, "Failed to Remove entry [%x]", v8);
    AhcpCacheEntryReleaseForWrite(a1, v10, (__int64)v11);
  }
  else
  {
    AslLogCallPrintf(1, "AhcCacheRemove", 2042, "Failed to acquire entry for Update [%x]", v6);
  }
  return v7;
}

```

## disassembly

```asm
0x140027bc8  mov     rax, rsp
0x140027bcb  mov     [rax+8], rbx
0x140027bcf  mov     [rax+10h], rsi
0x140027bd3  push    rdi
0x140027bd4  sub     rsp, 40h
0x140027bd8  mov     dword ptr [rax-20h], 1
0x140027bdf  mov     esi, r9d
0x140027be2  mov     [rax-28h], r8
0x140027be6  mov     rdi, rcx
0x140027be9  mov     r8, rcx; int
0x140027bec  mov     qword ptr [rax-18h], 0
0x140027bf4  mov     r9, rdx; int
0x140027bf7  mov     qword ptr [rax-10h], 0
0x140027bff  lea     rcx, [rax-18h]; int
0x140027c03  lea     rdx, [rax-10h]; int
0x140027c07  call    AhcpCacheEntryAcquire
0x140027c0c  mov     ebx, eax
0x140027c0e  test    eax, eax
0x140027c10  jns     short loc_140027C36
0x140027c12  lea     r9, aFailedToAcquir_4; "Failed to acquire entry for Update [%x]"
0x140027c19  mov     [rsp+48h+var_28], eax
0x140027c1d  mov     r8d, 7FAh
0x140027c23  lea     rdx, aAhccacheremove; "AhcCacheRemove"
0x140027c2a  mov     ecx, 1
0x140027c2f  call    AslLogCallPrintf
0x140027c34  jmp     short loc_140027C80
0x140027c36  mov     rcx, [rsp+48h+var_18]
0x140027c3b  mov     edx, esi
0x140027c3d  call    AhcpCacheEntryFilter
0x140027c42  mov     ebx, eax
0x140027c44  test    eax, eax
0x140027c46  jns     short loc_140027C6C
0x140027c48  lea     r9, aFailedToRemove; "Failed to Remove entry [%x]"
0x140027c4f  mov     [rsp+48h+var_28], eax
0x140027c53  mov     r8d, 805h
0x140027c59  lea     rdx, aAhccacheremove; "AhcCacheRemove"
0x140027c60  mov     ecx, 1
0x140027c65  call    AslLogCallPrintf
0x140027c6a  jmp     short loc_140027C6E
0x140027c6c  xor     ebx, ebx
0x140027c6e  mov     r8, [rsp+48h+var_10]
0x140027c73  mov     rcx, rdi
0x140027c76  mov     rdx, [rsp+48h+var_18]
0x140027c7b  call    AhcpCacheEntryReleaseForWrite
0x140027c80  mov     rsi, [rsp+48h+arg_8]
0x140027c85  mov     eax, ebx
0x140027c87  mov     rbx, [rsp+48h+arg_0]
0x140027c8c  add     rsp, 40h
0x140027c90  pop     rdi
0x140027c91  retn
```
