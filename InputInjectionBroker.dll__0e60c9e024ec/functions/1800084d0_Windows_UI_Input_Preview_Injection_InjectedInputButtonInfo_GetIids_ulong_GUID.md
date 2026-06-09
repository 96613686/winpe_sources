# Windows::UI::Input::Preview::Injection::InjectedInputButtonInfo::GetIids(ulong *,_GUID * *)

- ea: `0x1800084d0`
- end: `0x180008531`
- name: `?GetIids@InjectedInputButtonInfo@Injection@Preview@Input@UI@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(Windows::UI::Input::Preview::Injection::InjectedInputButtonInfo *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800084d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800084f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800084f2`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Preview::Injection::InjectedInputButtonInfo::GetIids(
        Windows::UI::Input::Preview::Injection::InjectedInputButtonInfo *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_a2c657b1_3587_57eb_a052_560c1ac7d750;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800084d0  mov     [rsp+arg_0], rbx
0x1800084d5  push    rdi
0x1800084d6  sub     rsp, 20h
0x1800084da  mov     qword ptr [r8], 0
0x1800084e1  mov     ecx, 20h ; ' '; cb
0x1800084e6  mov     dword ptr [rdx], 0
0x1800084ec  mov     rbx, r8
0x1800084ef  mov     rdi, rdx
0x1800084f2  call    cs:__imp_CoTaskMemAlloc
0x1800084f8  test    rax, rax
0x1800084fb  jnz     short loc_180008504
0x1800084fd  mov     eax, 8007000Eh
0x180008502  jmp     short loc_180008526
0x180008504  movups  xmm0, xmmword ptr cs:_GUID_a2c657b1_3587_57eb_a052_560c1ac7d750.Data1
0x18000850b  movdqu  xmmword ptr [rax], xmm0
0x18000850f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180008516  movdqu  xmmword ptr [rax+10h], xmm1
0x18000851b  mov     dword ptr [rdi], 2
0x180008521  mov     [rbx], rax
0x180008524  xor     eax, eax
0x180008526  mov     rbx, [rsp+28h+arg_0]
0x18000852b  add     rsp, 20h
0x18000852f  pop     rdi
0x180008530  retn
```
