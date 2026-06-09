# Windows::Foundation::Collections::Internal::VectorChangedEventArgs::GetIids(ulong *,_GUID * *)

- ea: `0x18001ecb0`
- end: `0x18001ed11`
- name: `?GetIids@VectorChangedEventArgs@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(Windows::Foundation::Collections::Internal::VectorChangedEventArgs *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ecb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ecd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ecd2`

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
0x18001ecb0  mov     [rsp+arg_0], rbx
0x18001ecb5  push    rdi
0x18001ecb6  sub     rsp, 20h
0x18001ecba  mov     qword ptr [r8], 0
0x18001ecc1  mov     ecx, 20h ; ' '; cb
0x18001ecc6  mov     dword ptr [rdx], 0
0x18001eccc  mov     rbx, r8
0x18001eccf  mov     rdi, rdx
0x18001ecd2  call    cs:__imp_CoTaskMemAlloc
0x18001ecd8  test    rax, rax
0x18001ecdb  jnz     short loc_18001ECE4
0x18001ecdd  mov     eax, 8007000Eh
0x18001ece2  jmp     short loc_18001ED06
0x18001ece4  movups  xmm0, xmmword ptr cs:_GUID_575933df_34fe_4480_af15_07691f3d5d9b.Data1
0x18001eceb  movdqu  xmmword ptr [rax], xmm0
0x18001ecef  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001ecf6  movdqu  xmmword ptr [rax+10h], xmm1
0x18001ecfb  mov     dword ptr [rdi], 2
0x18001ed01  mov     [rbx], rax
0x18001ed04  xor     eax, eax
0x18001ed06  mov     rbx, [rsp+28h+arg_0]
0x18001ed0b  add     rsp, 20h
0x18001ed0f  pop     rdi
0x18001ed10  retn
```
