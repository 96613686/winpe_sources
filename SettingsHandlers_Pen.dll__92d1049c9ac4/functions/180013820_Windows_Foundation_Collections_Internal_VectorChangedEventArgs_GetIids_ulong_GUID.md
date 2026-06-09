# Windows::Foundation::Collections::Internal::VectorChangedEventArgs::GetIids(ulong *,_GUID * *)

- ea: `0x180013820`
- end: `0x180013881`
- name: `?GetIids@VectorChangedEventArgs@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(Windows::Foundation::Collections::Internal::VectorChangedEventArgs *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013820`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013842`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013842`

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
0x180013820  mov     [rsp+arg_0], rbx
0x180013825  push    rdi
0x180013826  sub     rsp, 20h
0x18001382a  mov     qword ptr [r8], 0
0x180013831  mov     ecx, 20h ; ' '; cb
0x180013836  mov     dword ptr [rdx], 0
0x18001383c  mov     rbx, r8
0x18001383f  mov     rdi, rdx
0x180013842  call    cs:__imp_CoTaskMemAlloc
0x180013848  test    rax, rax
0x18001384b  jnz     short loc_180013854
0x18001384d  mov     eax, 8007000Eh
0x180013852  jmp     short loc_180013876
0x180013854  movups  xmm0, xmmword ptr cs:_GUID_575933df_34fe_4480_af15_07691f3d5d9b.Data1
0x18001385b  movdqu  xmmword ptr [rax], xmm0
0x18001385f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180013866  movdqu  xmmword ptr [rax+10h], xmm1
0x18001386b  mov     dword ptr [rdi], 2
0x180013871  mov     [rbx], rax
0x180013874  xor     eax, eax
0x180013876  mov     rbx, [rsp+28h+arg_0]
0x18001387b  add     rsp, 20h
0x18001387f  pop     rdi
0x180013880  retn
```
