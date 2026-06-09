# winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(void)

- ea: `0x18001b924`
- end: `0x18001b97d`
- name: `?Description@?$consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo@UIWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `89`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180018440`
- `0x180023c04`
- `0x180023e54`
- `0x180025290`

## callees

- `0x18001b924`
- `0x18001d50c`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v2; // rcx
  int v4; // eax
  int v6; // [rsp+28h] [rbp-20h] BYREF
  __int128 v7; // [rsp+30h] [rbp-18h]
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  v2 = *a1;
  v8 = 0;
  v6 = 0;
  v7 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 64LL))(v2, &v8);
  if ( v4 < 0 )
    winrt::throw_hresult((unsigned int)v4, &v6);
  *a2 = v8;
  return a2;
}

```

## disassembly

```asm
0x18001b924  push    rbx
0x18001b926  sub     rsp, 40h
0x18001b92a  mov     rcx, [rcx]
0x18001b92d  mov     rbx, rdx
0x18001b930  mov     [rsp+48h+arg_0], 0
0x18001b939  lea     rdx, [rsp+48h+arg_0]
0x18001b93e  xorps   xmm0, xmm0
0x18001b941  mov     [rsp+48h+var_20], 0
0x18001b949  movdqu  [rsp+48h+var_18], xmm0
0x18001b94f  mov     rax, [rcx]
0x18001b952  mov     rax, [rax+40h]
0x18001b956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b95b  test    eax, eax
0x18001b95d  js      short loc_18001B970
0x18001b95f  mov     rax, [rsp+48h+arg_0]
0x18001b964  mov     [rbx], rax
0x18001b967  mov     rax, rbx
0x18001b96a  add     rsp, 40h
0x18001b96e  pop     rbx
0x18001b96f  retn
0x18001b970  lea     rdx, [rsp+48h+var_20]
0x18001b975  mov     ecx, eax
0x18001b977  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
