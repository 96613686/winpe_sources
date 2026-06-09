# WindowsInternal::ApplicationModel::Calls::AppLauncherStatics::GetIids(ulong *,_GUID * *)

- ea: `0x180003a80`
- end: `0x180003ae1`
- name: `?GetIids@AppLauncherStatics@Calls@ApplicationModel@WindowsInternal@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::AppLauncherStatics *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003af0`

## callees

- `0x180003a80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003aa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003aa2`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::AppLauncherStatics::GetIids(
        WindowsInternal::ApplicationModel::Calls::AppLauncherStatics *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  v5[1] = GUID_5393122d_07dd_45d3_9aed_acfbf1895eab;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180003a80  mov     [rsp+arg_0], rbx
0x180003a85  push    rdi
0x180003a86  sub     rsp, 20h
0x180003a8a  mov     qword ptr [r8], 0
0x180003a91  mov     ecx, 20h ; ' '; cb
0x180003a96  mov     dword ptr [rdx], 0
0x180003a9c  mov     rbx, r8
0x180003a9f  mov     rdi, rdx
0x180003aa2  call    cs:__imp_CoTaskMemAlloc
0x180003aa8  test    rax, rax
0x180003aab  jnz     short loc_180003AB4
0x180003aad  mov     eax, 8007000Eh
0x180003ab2  jmp     short loc_180003AD6
0x180003ab4  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x180003abb  movdqu  xmmword ptr [rax], xmm0
0x180003abf  movups  xmm1, xmmword ptr cs:_GUID_5393122d_07dd_45d3_9aed_acfbf1895eab.Data1
0x180003ac6  movdqu  xmmword ptr [rax+10h], xmm1
0x180003acb  mov     dword ptr [rdi], 2
0x180003ad1  mov     [rbx], rax
0x180003ad4  xor     eax, eax
0x180003ad6  mov     rbx, [rsp+28h+arg_0]
0x180003adb  add     rsp, 20h
0x180003adf  pop     rdi
0x180003ae0  retn
```
