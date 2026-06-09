# CFDNotification::OnUpdate(tagQueryUpdateAction,unsigned __int64,IFunctionInstance *)

- ea: `0x180005fd0`
- end: `0x180006002`
- name: `?OnUpdate@CFDNotification@@UEAAJW4tagQueryUpdateAction@@_KPEAUIFunctionInstance@@@Z`
- size: `50`
- prototype: `__int64 __fastcall(CFDNotification *this, enum tagQueryUpdateAction, __int64, struct IFunctionInstance *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CFDNotification::OnUpdate(
        CFDNotification *this,
        enum tagQueryUpdateAction a2,
        __int64 a3,
        struct IFunctionInstance *a4)
{
  *((_DWORD *)this + 6) = (*(__int64 (__fastcall **)(_QWORD, struct IFunctionInstance *, GUID *, char *))(**((_QWORD **)this + 6) + 24LL))(
                            *((_QWORD *)this + 6),
                            a4,
                            &GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9,
                            (char *)this + 40);
  return 0;
}

```

## disassembly

```asm
0x180005fd0  push    rbx
0x180005fd2  sub     rsp, 30h
0x180005fd6  mov     rbx, rcx
0x180005fd9  lea     r8, _GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9
0x180005fe0  mov     rcx, [rcx+30h]
0x180005fe4  mov     rdx, r9
0x180005fe7  lea     r9, [rbx+28h]
0x180005feb  mov     rax, [rcx]
0x180005fee  mov     rax, [rax+18h]
0x180005ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ff7  mov     [rbx+18h], eax
0x180005ffa  xor     eax, eax
0x180005ffc  add     rsp, 30h
0x180006000  pop     rbx
0x180006001  retn
```
