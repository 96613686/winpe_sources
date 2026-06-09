# Windows::Graphics::Capture::Server::CaptureWindowFilter::GetIids(ulong *,_GUID * *)

- ea: `0x18001c5e0`
- end: `0x18001c64d`
- name: `?GetIids@CaptureWindowFilter@Server@Capture@Graphics@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server::CaptureWindowFilter *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c660`

## callees

- `0x18001c5e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c602`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c602`

## pseudocode

```c
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureWindowFilter::GetIids(
        Windows::Graphics::Capture::Server::CaptureWindowFilter *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_baed0176_8704_558a_928a_7710baaa81a8;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001c5e0  mov     [rsp+arg_0], rbx
0x18001c5e5  push    rdi
0x18001c5e6  sub     rsp, 20h
0x18001c5ea  mov     qword ptr [r8], 0
0x18001c5f1  mov     ecx, 30h ; '0'; cb
0x18001c5f6  mov     dword ptr [rdx], 0
0x18001c5fc  mov     rbx, r8
0x18001c5ff  mov     rdi, rdx
0x18001c602  call    cs:__imp_CoTaskMemAlloc
0x18001c608  test    rax, rax
0x18001c60b  jnz     short loc_18001C614
0x18001c60d  mov     eax, 8007000Eh
0x18001c612  jmp     short loc_18001C642
0x18001c614  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18001c61b  movdqu  xmmword ptr [rax], xmm0
0x18001c61f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001c626  movdqu  xmmword ptr [rax+10h], xmm1
0x18001c62b  movups  xmm0, xmmword ptr cs:_GUID_baed0176_8704_558a_928a_7710baaa81a8.Data1
0x18001c632  movdqu  xmmword ptr [rax+20h], xmm0
0x18001c637  mov     dword ptr [rdi], 3
0x18001c63d  mov     [rbx], rax
0x18001c640  xor     eax, eax
0x18001c642  mov     rbx, [rsp+28h+arg_0]
0x18001c647  add     rsp, 20h
0x18001c64b  pop     rdi
0x18001c64c  retn
```
