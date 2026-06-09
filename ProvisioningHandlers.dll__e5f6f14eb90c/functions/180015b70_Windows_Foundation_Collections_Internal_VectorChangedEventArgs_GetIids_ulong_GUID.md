# Windows::Foundation::Collections::Internal::VectorChangedEventArgs::GetIids(ulong *,_GUID * *)

- ea: `0x180015b70`
- end: `0x180015bd8`
- name: `?GetIids@VectorChangedEventArgs@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `104`
- prototype: `__int64 __fastcall(Windows::Foundation::Collections::Internal::VectorChangedEventArgs *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180015b70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015b92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015b92`

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
0x180015b70  mov     [rsp+arg_0], rbx
0x180015b75  push    rdi
0x180015b76  sub     rsp, 20h
0x180015b7a  mov     qword ptr [r8], 0
0x180015b81  mov     ecx, 20h ; ' '; cb
0x180015b86  mov     dword ptr [rdx], 0
0x180015b8c  mov     rbx, r8
0x180015b8f  mov     rdi, rdx
0x180015b92  call    cs:__imp_CoTaskMemAlloc
0x180015b99  nop     dword ptr [rax+rax+00h]
0x180015b9e  test    rax, rax
0x180015ba1  jnz     short loc_180015BAA
0x180015ba3  mov     eax, 8007000Eh
0x180015ba8  jmp     short loc_180015BCC
0x180015baa  movups  xmm0, xmmword ptr cs:_GUID_575933df_34fe_4480_af15_07691f3d5d9b.Data1
0x180015bb1  movdqu  xmmword ptr [rax], xmm0
0x180015bb5  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180015bbc  movdqu  xmmword ptr [rax+10h], xmm1
0x180015bc1  mov     dword ptr [rdi], 2
0x180015bc7  mov     [rbx], rax
0x180015bca  xor     eax, eax
0x180015bcc  mov     rbx, [rsp+28h+arg_0]
0x180015bd1  add     rsp, 20h
0x180015bd5  pop     rdi
0x180015bd6  retn
```
