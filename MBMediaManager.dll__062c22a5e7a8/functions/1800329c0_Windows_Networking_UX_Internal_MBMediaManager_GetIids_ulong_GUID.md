# Windows::Networking::UX::Internal::MBMediaManager::GetIids(ulong *,_GUID * *)

- ea: `0x1800329c0`
- end: `0x180032a2d`
- name: `?GetIids@MBMediaManager@Internal@UX@Networking@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MBMediaManager *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032a40`

## callees

- `0x1800329c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800329e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800329e2`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MBMediaManager::GetIids(
        Windows::Networking::UX::Internal::MBMediaManager *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_c612a6f2_49b0_47dd_a064_9b78b7aacdf7;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_04e84e57_eb65_49a0_b68c_520dc2a1a81a;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800329c0  mov     [rsp+arg_0], rbx
0x1800329c5  push    rdi
0x1800329c6  sub     rsp, 20h
0x1800329ca  mov     qword ptr [r8], 0
0x1800329d1  mov     ecx, 30h ; '0'; cb
0x1800329d6  mov     dword ptr [rdx], 0
0x1800329dc  mov     rbx, r8
0x1800329df  mov     rdi, rdx
0x1800329e2  call    cs:__imp_CoTaskMemAlloc
0x1800329e8  test    rax, rax
0x1800329eb  jnz     short loc_1800329F4
0x1800329ed  mov     eax, 8007000Eh
0x1800329f2  jmp     short loc_180032A22
0x1800329f4  movups  xmm0, xmmword ptr cs:_GUID_c612a6f2_49b0_47dd_a064_9b78b7aacdf7.Data1
0x1800329fb  movdqu  xmmword ptr [rax], xmm0
0x1800329ff  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180032a06  movdqu  xmmword ptr [rax+10h], xmm1
0x180032a0b  movups  xmm0, xmmword ptr cs:_GUID_04e84e57_eb65_49a0_b68c_520dc2a1a81a.Data1
0x180032a12  movdqu  xmmword ptr [rax+20h], xmm0
0x180032a17  mov     dword ptr [rdi], 3
0x180032a1d  mov     [rbx], rax
0x180032a20  xor     eax, eax
0x180032a22  mov     rbx, [rsp+28h+arg_0]
0x180032a27  add     rsp, 20h
0x180032a2b  pop     rdi
0x180032a2c  retn
```
