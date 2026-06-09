# std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>(void)

- ea: `0x18001e75c`
- end: `0x18001e802`
- name: `??1?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA@XZ`
- size: `166`
- prototype: `void __fastcall(__int64)`
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001e414`
- `0x18001e750`
- `0x18001e8a0`
- `0x18001e9c0`
- `0x18001f690`
- `0x180023c04`
- `0x180023e54`
- `0x180028a16`

## callees

- `0x180002cc0`
- `0x180016fe4`
- `0x18001e75c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::~vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>(
        __int64 a1)
{
  char *v1; // rbx
  char *v3; // rsi
  char *v4; // rcx
  unsigned __int64 v5; // rdx
  char *v6; // rax

  v1 = *(char **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(char **)(a1 + 8);
    while ( v1 != v3 )
    {
      if ( *(_QWORD *)v1 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1);
      v1 += 8;
    }
    v4 = *(char **)a1;
    v5 = 8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3);
    if ( v5 < 0x1000 )
    {
      v6 = *(char **)a1;
    }
    else
    {
      v6 = (char *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)(v4 - v6 - 8) > 0x1F )
        __fastfail(5u);
      v5 += 39LL;
    }
    operator delete(v6, v5);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18001e75c  mov     [rsp+arg_0], rbx
0x18001e761  mov     [rsp+arg_8], rsi
0x18001e766  push    rdi
0x18001e767  sub     rsp, 20h
0x18001e76b  mov     rbx, [rcx]
0x18001e76e  mov     rdi, rcx
0x18001e771  test    rbx, rbx
0x18001e774  jz      short loc_18001E7F2
0x18001e776  mov     rsi, [rcx+8]
0x18001e77a  jmp     short loc_18001E78E
0x18001e77c  cmp     qword ptr [rbx], 0
0x18001e780  jz      short loc_18001E78A
0x18001e782  mov     rcx, rbx
0x18001e785  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e78a  add     rbx, 8
0x18001e78e  cmp     rbx, rsi
0x18001e791  jnz     short loc_18001E77C
0x18001e793  mov     rcx, [rdi]
0x18001e796  mov     rax, [rdi+10h]
0x18001e79a  sub     rax, rcx
0x18001e79d  sar     rax, 3
0x18001e7a1  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18001e7a9  cmp     rdx, 1000h
0x18001e7b0  jb      short loc_18001E7D0
0x18001e7b2  mov     rax, [rcx-8]
0x18001e7b6  sub     rcx, rax
0x18001e7b9  sub     rcx, 8
0x18001e7bd  cmp     rcx, 1Fh
0x18001e7c1  ja      short loc_18001E7C9
0x18001e7c3  add     rdx, 27h ; '''
0x18001e7c7  jmp     short loc_18001E7D3
0x18001e7c9  mov     ecx, 5
0x18001e7ce  int     29h; Win8: RtlFailFast(ecx)
0x18001e7d0  mov     rax, rcx
0x18001e7d3  mov     rcx, rax; void *
0x18001e7d6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e7db  mov     qword ptr [rdi], 0
0x18001e7e2  mov     qword ptr [rdi+8], 0
0x18001e7ea  mov     qword ptr [rdi+10h], 0
0x18001e7f2  mov     rbx, [rsp+28h+arg_0]
0x18001e7f7  mov     rsi, [rsp+28h+arg_8]
0x18001e7fc  add     rsp, 20h
0x18001e800  pop     rdi
0x18001e801  retn
```
