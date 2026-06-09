# Windows::System::CProcessMemoryReport::GetIids(ulong *,_GUID * *)

- ea: `0x180018420`
- end: `0x18001848d`
- name: `?GetIids@CProcessMemoryReport@System@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::System::CProcessMemoryReport *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800184a0`

## callees

- `0x180018420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018442`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018442`

## pseudocode

```c
__int64 __fastcall Windows::System::CProcessMemoryReport::GetIids(
        Windows::System::CProcessMemoryReport *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_087305a8_9b70_4782_8741_3a982b6ce5e4;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180018420  mov     [rsp+arg_0], rbx
0x180018425  push    rdi
0x180018426  sub     rsp, 20h
0x18001842a  mov     qword ptr [r8], 0
0x180018431  mov     ecx, 30h ; '0'; cb
0x180018436  mov     dword ptr [rdx], 0
0x18001843c  mov     rbx, r8
0x18001843f  mov     rdi, rdx
0x180018442  call    cs:__imp_CoTaskMemAlloc
0x180018448  test    rax, rax
0x18001844b  jnz     short loc_180018454
0x18001844d  mov     eax, 8007000Eh
0x180018452  jmp     short loc_180018482
0x180018454  movups  xmm0, xmmword ptr cs:_GUID_087305a8_9b70_4782_8741_3a982b6ce5e4.Data1
0x18001845b  movdqu  xmmword ptr [rax], xmm0
0x18001845f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180018466  movdqu  xmmword ptr [rax+10h], xmm1
0x18001846b  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x180018472  movdqu  xmmword ptr [rax+20h], xmm0
0x180018477  mov     dword ptr [rdi], 3
0x18001847d  mov     [rbx], rax
0x180018480  xor     eax, eax
0x180018482  mov     rbx, [rsp+28h+arg_0]
0x180018487  add     rsp, 20h
0x18001848b  pop     rdi
0x18001848c  retn
```
