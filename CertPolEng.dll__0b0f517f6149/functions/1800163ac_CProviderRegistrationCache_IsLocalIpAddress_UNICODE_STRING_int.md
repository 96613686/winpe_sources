# CProviderRegistrationCache::IsLocalIpAddress(_UNICODE_STRING *,int *)

- ea: `0x1800163ac`
- end: `0x180016403`
- name: `?IsLocalIpAddress@CProviderRegistrationCache@@QEAAJPEAU_UNICODE_STRING@@PEAH@Z`
- size: `87`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *__hidden this, struct _UNICODE_STRING *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002560`

## callees

- `0x1800163ac`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::IsLocalIpAddress(
        CProviderRegistrationCache *this,
        struct _UNICODE_STRING *a2,
        int *a3)
{
  __int64 (__fastcall *v3)(struct _UNICODE_STRING *, int *, int *); // rax
  __int64 result; // rax
  int v6; // [rsp+30h] [rbp+8h] BYREF

  v3 = (__int64 (__fastcall *)(struct _UNICODE_STRING *, int *, int *))*((_QWORD *)this + 34);
  if ( !v3 )
    return 3221225474LL;
  v6 = 0;
  result = v3(a2, a3, &v6);
  if ( (int)result >= 0 )
  {
    if ( *a3 )
      return v6 != 0 ? 0xC0000022 : 0;
    else
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800163ac  push    rbx
0x1800163ae  sub     rsp, 20h
0x1800163b2  mov     rax, [rcx+110h]
0x1800163b9  mov     rbx, r8
0x1800163bc  mov     r9, rdx
0x1800163bf  test    rax, rax
0x1800163c2  jz      short loc_1800163F8
0x1800163c4  lea     r8, [rsp+28h+arg_0]
0x1800163c9  mov     [rsp+28h+arg_0], 0
0x1800163d1  mov     rdx, rbx
0x1800163d4  mov     rcx, r9
0x1800163d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163dc  test    eax, eax
0x1800163de  js      short loc_1800163FD
0x1800163e0  cmp     dword ptr [rbx], 0
0x1800163e3  jz      short loc_1800163F4
0x1800163e5  mov     eax, [rsp+28h+arg_0]
0x1800163e9  neg     eax
0x1800163eb  sbb     eax, eax
0x1800163ed  and     eax, 0C0000022h
0x1800163f2  jmp     short loc_1800163FD
0x1800163f4  xor     eax, eax
0x1800163f6  jmp     short loc_1800163FD
0x1800163f8  mov     eax, 0C0000002h
0x1800163fd  add     rsp, 20h
0x180016401  pop     rbx
0x180016402  retn
```
