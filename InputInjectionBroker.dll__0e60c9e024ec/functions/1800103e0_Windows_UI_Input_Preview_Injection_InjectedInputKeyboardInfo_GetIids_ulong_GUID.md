# Windows::UI::Input::Preview::Injection::InjectedInputKeyboardInfo::GetIids(ulong *,_GUID * *)

- ea: `0x1800103e0`
- end: `0x180010441`
- name: `?GetIids@InjectedInputKeyboardInfo@Injection@Preview@Input@UI@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(Windows::UI::Input::Preview::Injection::InjectedInputKeyboardInfo *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800103e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010402`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010402`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Preview::Injection::InjectedInputKeyboardInfo::GetIids(
        Windows::UI::Input::Preview::Injection::InjectedInputKeyboardInfo *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_4b46d140_2b6a_5ffa_7eae_bd077b052acd;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800103e0  mov     [rsp+arg_0], rbx
0x1800103e5  push    rdi
0x1800103e6  sub     rsp, 20h
0x1800103ea  mov     qword ptr [r8], 0
0x1800103f1  mov     ecx, 20h ; ' '; cb
0x1800103f6  mov     dword ptr [rdx], 0
0x1800103fc  mov     rbx, r8
0x1800103ff  mov     rdi, rdx
0x180010402  call    cs:__imp_CoTaskMemAlloc
0x180010408  test    rax, rax
0x18001040b  jnz     short loc_180010414
0x18001040d  mov     eax, 8007000Eh
0x180010412  jmp     short loc_180010436
0x180010414  movups  xmm0, xmmword ptr cs:_GUID_4b46d140_2b6a_5ffa_7eae_bd077b052acd.Data1
0x18001041b  movdqu  xmmword ptr [rax], xmm0
0x18001041f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180010426  movdqu  xmmword ptr [rax+10h], xmm1
0x18001042b  mov     dword ptr [rdi], 2
0x180010431  mov     [rbx], rax
0x180010434  xor     eax, eax
0x180010436  mov     rbx, [rsp+28h+arg_0]
0x18001043b  add     rsp, 20h
0x18001043f  pop     rdi
0x180010440  retn
```
