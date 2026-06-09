# std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x18001e808`
- end: `0x18001e894`
- name: `??1_Reallocation_guard@?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA@XZ`
- size: `140`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001e128`

## callees

- `0x180002cc0`
- `0x180016fe4`
- `0x18001e808`

## pseudocode

```c
void __fastcall std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  _QWORD *v2; // rsi
  _QWORD *i; // rbx
  __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  void *v6; // rax

  if ( a1[1] )
  {
    v2 = (_QWORD *)a1[4];
    for ( i = (_QWORD *)a1[3]; i != v2; ++i )
    {
      if ( *i )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(i);
    }
    v4 = a1[1];
    v5 = 8LL * a1[2];
    if ( v5 < 0x1000 )
    {
      v6 = (void *)a1[1];
    }
    else
    {
      v6 = *(void **)(v4 - 8);
      if ( (unsigned __int64)(v4 - (_QWORD)v6 - 8) > 0x1F )
        __fastfail(5u);
      v5 += 39LL;
    }
    operator delete(v6, v5);
  }
}

```

## disassembly

```asm
0x18001e808  mov     [rsp+arg_0], rbx
0x18001e80d  mov     [rsp+arg_8], rsi
0x18001e812  push    rdi
0x18001e813  sub     rsp, 20h
0x18001e817  cmp     qword ptr [rcx+8], 0
0x18001e81c  mov     rdi, rcx
0x18001e81f  jz      short loc_18001E884
0x18001e821  mov     rsi, [rcx+20h]
0x18001e825  mov     rbx, [rcx+18h]
0x18001e829  jmp     short loc_18001E83D
0x18001e82b  cmp     qword ptr [rbx], 0
0x18001e82f  jz      short loc_18001E839
0x18001e831  mov     rcx, rbx
0x18001e834  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e839  add     rbx, 8
0x18001e83d  cmp     rbx, rsi
0x18001e840  jnz     short loc_18001E82B
0x18001e842  mov     rax, [rdi+10h]
0x18001e846  mov     rcx, [rdi+8]
0x18001e84a  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18001e852  cmp     rdx, 1000h
0x18001e859  jb      short loc_18001E879
0x18001e85b  mov     rax, [rcx-8]
0x18001e85f  sub     rcx, rax
0x18001e862  sub     rcx, 8
0x18001e866  cmp     rcx, 1Fh
0x18001e86a  ja      short loc_18001E872
0x18001e86c  add     rdx, 27h ; '''
0x18001e870  jmp     short loc_18001E87C
0x18001e872  mov     ecx, 5
0x18001e877  int     29h; Win8: RtlFailFast(ecx)
0x18001e879  mov     rax, rcx
0x18001e87c  mov     rcx, rax; void *
0x18001e87f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e884  mov     rbx, [rsp+28h+arg_0]
0x18001e889  mov     rsi, [rsp+28h+arg_8]
0x18001e88e  add     rsp, 20h
0x18001e892  pop     rdi
0x18001e893  retn
```
