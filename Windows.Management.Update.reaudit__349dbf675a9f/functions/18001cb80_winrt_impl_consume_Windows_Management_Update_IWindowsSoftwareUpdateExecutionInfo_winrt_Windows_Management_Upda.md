# winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(void)

- ea: `0x18001cb80`
- end: `0x18001cbd4`
- name: `?DeployInfo@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo@UIWindowsSoftwareUpdateExecutionInfo@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `84`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180019118`
- `0x180024e9c`
- `0x1800250f0`
- `0x18002664c`

## callees

- `0x18001cb80`
- `0x18001e7a4`
- `0x18002c010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v2; // rcx
  signed int v4; // eax
  __int64 v5; // r8
  unsigned int v7; // [rsp+28h] [rbp-20h] BYREF
  __int128 v8; // [rsp+30h] [rbp-18h]
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  v2 = *a1;
  v9 = 0;
  v7 = 0;
  v8 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 64LL))(v2, &v9);
  if ( v4 < 0 )
    winrt::throw_hresult(v4, &v7, v5);
  *a2 = v9;
  return a2;
}

```

## disassembly

```asm
0x18001cb80  push    rbx
0x18001cb82  sub     rsp, 40h
0x18001cb86  mov     rcx, [rcx]
0x18001cb89  mov     rbx, rdx
0x18001cb8c  and     [rsp+48h+arg_0], 0
0x18001cb92  lea     rdx, [rsp+48h+arg_0]
0x18001cb97  and     [rsp+48h+var_20], 0
0x18001cb9c  xorps   xmm0, xmm0
0x18001cb9f  movdqu  [rsp+48h+var_18], xmm0
0x18001cba5  mov     rax, [rcx]
0x18001cba8  mov     rax, [rax+40h]
0x18001cbac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbb1  test    eax, eax
0x18001cbb3  js      short loc_18001CBC7
0x18001cbb5  mov     rax, [rsp+48h+arg_0]
0x18001cbba  mov     [rbx], rax
0x18001cbbd  mov     rax, rbx
0x18001cbc0  add     rsp, 40h
0x18001cbc4  pop     rbx
0x18001cbc5  retn
0x18001cbc7  lea     rdx, [rsp+48h+var_20]
0x18001cbcc  mov     ecx, eax
0x18001cbce  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
