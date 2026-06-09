# std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>(void)

- ea: `0x18001fa3c`
- end: `0x18001fad3`
- name: `??1?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA@XZ`
- size: `151`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001f628`
- `0x18001fa30`
- `0x18001fae0`
- `0x18001fc00`
- `0x1800209b0`
- `0x180024e9c`
- `0x1800250f0`
- `0x18002a953`
- `0x18002ad57`

## callees

- `0x180002c74`
- `0x180017c3c`
- `0x18001fa3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18001fac6`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18001fac6`

## pseudocode

```c
void __fastcall std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(
        __int64 a1)
{
  __int64 *v1; // rbx
  __int64 *v3; // rsi
  __int64 *v4; // rcx
  unsigned __int64 v5; // rdx
  __int64 *v6; // r8
  unsigned __int64 v7; // rdx
  char *v8; // rcx

  v1 = *(__int64 **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(__int64 **)(a1 + 8);
    while ( v1 != v3 )
    {
      if ( *v1 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1);
      ++v1;
    }
    v4 = *(__int64 **)a1;
    v5 = (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v5 >= 0x1000 )
    {
      v6 = (__int64 *)*(v4 - 1);
      v7 = v5 + 39;
      v8 = (char *)((char *)v4 - (char *)v6);
      if ( (unsigned __int64)(v8 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v8, v7);
        __debugbreak();
        JUMPOUT(0x18001FAD3LL);
      }
      v4 = v6;
    }
    operator delete(v4);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18001fa3c  mov     [rsp+arg_0], rbx
0x18001fa41  mov     [rsp+arg_8], rsi
0x18001fa46  push    rdi
0x18001fa47  sub     rsp, 20h
0x18001fa4b  mov     rbx, [rcx]
0x18001fa4e  mov     rdi, rcx
0x18001fa51  test    rbx, rbx
0x18001fa54  jz      short loc_18001FAB5
0x18001fa56  mov     rsi, [rcx+8]
0x18001fa5a  jmp     short loc_18001FA6E
0x18001fa5c  cmp     qword ptr [rbx], 0
0x18001fa60  jz      short loc_18001FA6A
0x18001fa62  mov     rcx, rbx
0x18001fa65  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001fa6a  add     rbx, 8
0x18001fa6e  cmp     rbx, rsi
0x18001fa71  jnz     short loc_18001FA5C
0x18001fa73  mov     rcx, [rdi]
0x18001fa76  mov     rdx, [rdi+10h]
0x18001fa7a  sub     rdx, rcx
0x18001fa7d  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001fa81  cmp     rdx, 1000h
0x18001fa88  jb      short loc_18001FAA2
0x18001fa8a  mov     r8, [rcx-8]
0x18001fa8e  add     rdx, 27h ; '''; unsigned __int64
0x18001fa92  sub     rcx, r8
0x18001fa95  lea     rax, [rcx-8]
0x18001fa99  cmp     rax, 1Fh
0x18001fa9d  ja      short loc_18001FAC6
0x18001fa9f  mov     rcx, r8; void *
0x18001faa2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001faa7  and     qword ptr [rdi], 0
0x18001faab  and     qword ptr [rdi+8], 0
0x18001fab0  and     qword ptr [rdi+10h], 0
0x18001fab5  mov     rbx, [rsp+28h+arg_0]
0x18001faba  mov     rsi, [rsp+28h+arg_8]
0x18001fabf  add     rsp, 20h
0x18001fac3  pop     rdi
0x18001fac4  retn
0x18001fac6  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x18001facd  nop     dword ptr [rax+rax+00h]
0x18001fad2  int     3; Trap to Debugger
```
