# Windows::Foundation::Collections::Internal::VectorChangedEventArgs::GetIids(ulong *,_GUID * *)

- ea: `0x180015e30`
- end: `0x180015e91`
- name: `?GetIids@VectorChangedEventArgs@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(Windows::Foundation::Collections::Internal::VectorChangedEventArgs *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180015e30`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180015e52`
- `ole32!CoTaskMemAlloc` at `0x180015e52`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::VectorChangedEventArgs::GetIids(
        Windows::Foundation::Collections::Internal::VectorChangedEventArgs *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_575933df_34fe_4480_af15_07691f3d5d9b;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180015e30  mov     [rsp+arg_0], rbx
0x180015e35  push    rdi
0x180015e36  sub     rsp, 20h
0x180015e3a  mov     qword ptr [r8], 0
0x180015e41  mov     ecx, 20h ; ' '; cb
0x180015e46  mov     dword ptr [rdx], 0
0x180015e4c  mov     rbx, r8
0x180015e4f  mov     rdi, rdx
0x180015e52  call    cs:__imp_CoTaskMemAlloc
0x180015e58  test    rax, rax
0x180015e5b  jnz     short loc_180015E64
0x180015e5d  mov     eax, 8007000Eh
0x180015e62  jmp     short loc_180015E86
0x180015e64  movups  xmm0, xmmword ptr cs:_GUID_575933df_34fe_4480_af15_07691f3d5d9b.Data1
0x180015e6b  movdqu  xmmword ptr [rax], xmm0
0x180015e6f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180015e76  movdqu  xmmword ptr [rax+10h], xmm1
0x180015e7b  mov     dword ptr [rdi], 2
0x180015e81  mov     [rbx], rax
0x180015e84  xor     eax, eax
0x180015e86  mov     rbx, [rsp+28h+arg_0]
0x180015e8b  add     rsp, 20h
0x180015e8f  pop     rdi
0x180015e90  retn
```
