# SecurityMitigationsBrokerStatics::GetIids(ulong *,_GUID * *)

- ea: `0x180003ba0`
- end: `0x180003c01`
- name: `?GetIids@SecurityMitigationsBrokerStatics@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(SecurityMitigationsBrokerStatics *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003c10`

## callees

- `0x180003ba0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003bc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003bc2`

## pseudocode

```c
__int64 __fastcall SecurityMitigationsBrokerStatics::GetIids(
        SecurityMitigationsBrokerStatics *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  v5[1] = GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180003ba0  mov     [rsp+arg_0], rbx
0x180003ba5  push    rdi
0x180003ba6  sub     rsp, 20h
0x180003baa  mov     qword ptr [r8], 0
0x180003bb1  mov     ecx, 20h ; ' '; cb
0x180003bb6  mov     dword ptr [rdx], 0
0x180003bbc  mov     rbx, r8
0x180003bbf  mov     rdi, rdx
0x180003bc2  call    cs:__imp_CoTaskMemAlloc
0x180003bc8  test    rax, rax
0x180003bcb  jnz     short loc_180003BD4
0x180003bcd  mov     eax, 8007000Eh
0x180003bd2  jmp     short loc_180003BF6
0x180003bd4  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x180003bdb  movdqu  xmmword ptr [rax], xmm0
0x180003bdf  movups  xmm1, xmmword ptr cs:_GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data1
0x180003be6  movdqu  xmmword ptr [rax+10h], xmm1
0x180003beb  mov     dword ptr [rdi], 2
0x180003bf1  mov     [rbx], rax
0x180003bf4  xor     eax, eax
0x180003bf6  mov     rbx, [rsp+28h+arg_0]
0x180003bfb  add     rsp, 20h
0x180003bff  pop     rdi
0x180003c00  retn
```
