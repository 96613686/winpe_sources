# Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceRuntimeInfo::GetIids(ulong *,_GUID * *)

- ea: `0x180007d70`
- end: `0x180007dd1`
- name: `?GetIids@PlatformDiagnosticTraceRuntimeInfo@TraceReporting@Diagnostics@System@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceRuntimeInfo *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007d70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007d92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007d92`

## pseudocode

```c
__int64 __fastcall Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceRuntimeInfo::GetIids(
        Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceRuntimeInfo *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_3d4d5e2d_01d8_4768_8554_1eb1ca610986;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180007d70  mov     [rsp+arg_0], rbx
0x180007d75  push    rdi
0x180007d76  sub     rsp, 20h
0x180007d7a  mov     qword ptr [r8], 0
0x180007d81  mov     ecx, 20h ; ' '; cb
0x180007d86  mov     dword ptr [rdx], 0
0x180007d8c  mov     rbx, r8
0x180007d8f  mov     rdi, rdx
0x180007d92  call    cs:__imp_CoTaskMemAlloc
0x180007d98  test    rax, rax
0x180007d9b  jnz     short loc_180007DA4
0x180007d9d  mov     eax, 8007000Eh
0x180007da2  jmp     short loc_180007DC6
0x180007da4  movups  xmm0, xmmword ptr cs:_GUID_3d4d5e2d_01d8_4768_8554_1eb1ca610986.Data1
0x180007dab  movdqu  xmmword ptr [rax], xmm0
0x180007daf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180007db6  movdqu  xmmword ptr [rax+10h], xmm1
0x180007dbb  mov     dword ptr [rdi], 2
0x180007dc1  mov     [rbx], rax
0x180007dc4  xor     eax, eax
0x180007dc6  mov     rbx, [rsp+28h+arg_0]
0x180007dcb  add     rsp, 20h
0x180007dcf  pop     rdi
0x180007dd0  retn
```
