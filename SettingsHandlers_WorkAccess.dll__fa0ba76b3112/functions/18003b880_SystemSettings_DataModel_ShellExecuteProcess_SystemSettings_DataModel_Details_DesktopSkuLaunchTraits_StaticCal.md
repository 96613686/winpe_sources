# SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::StaticCallbackHelper<_lambda_f7de781bee7f4cacf0dda90014912c9b_>::Callback(HWND__ *,__int64)

- ea: `0x18003b880`
- end: `0x18003b8cd`
- name: `?Callback@?$StaticCallbackHelper@V_lambda_f7de781bee7f4cacf0dda90014912c9b_@@@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@SAHPEAUHWND__@@_J@Z`
- size: `77`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x18003b880`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18003b89d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18003b89d`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::StaticCallbackHelper<_lambda_f7de781bee7f4cacf0dda90014912c9b_>::Callback(
        HWND a1,
        __int64 a2)
{
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  dwProcessId = 0;
  GetWindowThreadProcessId(a1, &dwProcessId);
  if ( dwProcessId != *(_DWORD *)(a2 + 8) )
    return 1;
  **(_QWORD **)a2 = a1;
  return 0;
}

```

## disassembly

```asm
0x18003b880  mov     [rsp+arg_0], rbx
0x18003b885  push    rdi
0x18003b886  sub     rsp, 20h
0x18003b88a  mov     rbx, rdx
0x18003b88d  mov     [rsp+28h+dwProcessId], 0
0x18003b895  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x18003b89a  mov     rdi, rcx
0x18003b89d  call    cs:__imp_GetWindowThreadProcessId
0x18003b8a4  nop     dword ptr [rax+rax+00h]
0x18003b8a9  mov     eax, [rbx+8]
0x18003b8ac  cmp     [rsp+28h+dwProcessId], eax
0x18003b8b0  jnz     short loc_18003B8BC
0x18003b8b2  mov     rax, [rbx]
0x18003b8b5  mov     [rax], rdi
0x18003b8b8  xor     eax, eax
0x18003b8ba  jmp     short loc_18003B8C1
0x18003b8bc  mov     eax, 1
0x18003b8c1  mov     rbx, [rsp+28h+arg_0]
0x18003b8c6  add     rsp, 20h
0x18003b8ca  pop     rdi
0x18003b8cb  retn
```
