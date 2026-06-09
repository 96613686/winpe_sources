# HrGetStreamSize

- ea: `0x18000f1f0`
- end: `0x18000f237`
- name: `HrGetStreamSize`
- size: `71`
- prototype: `__int64 __fastcall(__int64 *, _DWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180003140`
- `0x180003250`
- `0x18000f440`
- `0x18000f6f0`
- `0x1800100f0`

## callees

- `0x18000f1f0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall HrGetStreamSize(__int64 *a1, _DWORD *a2)
{
  __int64 v2; // rax
  __int64 result; // rax
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+50h] [rbp+18h]

  v2 = *a1;
  v6 = 0;
  v5 = 0;
  result = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, __int64 *))(v2 + 40))(a1, 0, 2, &v5);
  if ( (int)result >= 0 )
    *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x18000f1f0  push    rbx
0x18000f1f2  sub     rsp, 30h
0x18000f1f6  mov     rax, [rcx]
0x18000f1f9  lea     r9, [rsp+38h+arg_0]
0x18000f1fe  mov     rbx, rdx
0x18000f201  mov     [rsp+38h+arg_10], 0
0x18000f20a  mov     rdx, [rsp+38h+arg_10]
0x18000f20f  mov     r8d, 2
0x18000f215  mov     [rsp+38h+arg_0], 0
0x18000f21e  mov     rax, [rax+28h]
0x18000f222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f227  test    eax, eax
0x18000f229  js      short loc_18000F231
0x18000f22b  mov     ecx, dword ptr [rsp+38h+arg_0]
0x18000f22f  mov     [rbx], ecx
0x18000f231  add     rsp, 30h
0x18000f235  pop     rbx
0x18000f236  retn
```
