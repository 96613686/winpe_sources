# SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::StaticCallbackHelper<_lambda_f7de781bee7f4cacf0dda90014912c9b_>::Callback(HWND__ *,__int64)

- ea: `0x180034ae0`
- end: `0x180034b26`
- name: `?Callback@?$StaticCallbackHelper@V_lambda_f7de781bee7f4cacf0dda90014912c9b_@@@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@SAHPEAUHWND__@@_J@Z`
- size: `70`
- prototype: `__int64 __fastcall(HWND, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180034ae0`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180034afd`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180034afd`

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
0x180034ae0  mov     [rsp+arg_0], rbx
0x180034ae5  push    rdi
0x180034ae6  sub     rsp, 20h
0x180034aea  mov     rbx, rdx
0x180034aed  mov     [rsp+28h+dwProcessId], 0
0x180034af5  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180034afa  mov     rdi, rcx
0x180034afd  call    cs:__imp_GetWindowThreadProcessId
0x180034b03  mov     eax, [rbx+8]
0x180034b06  cmp     [rsp+28h+dwProcessId], eax
0x180034b0a  jnz     short loc_180034B16
0x180034b0c  mov     rax, [rbx]
0x180034b0f  mov     [rax], rdi
0x180034b12  xor     eax, eax
0x180034b14  jmp     short loc_180034B1B
0x180034b16  mov     eax, 1
0x180034b1b  mov     rbx, [rsp+28h+arg_0]
0x180034b20  add     rsp, 20h
0x180034b24  pop     rdi
0x180034b25  retn
```
