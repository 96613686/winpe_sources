# Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfoFactory::CreateInstanceFromGamepadReading(Windows::Gaming::Input::GamepadReading,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfo * *)

- ea: `0x18000f2c0`
- end: `0x18000f39a`
- name: `?CreateInstanceFromGamepadReading@InjectedInputGamepadInfoFactory@Injection@Preview@Input@UI@Windows@@UEAAJUGamepadReading@4Gaming@6@PEAPEAUIInjectedInputGamepadInfo@23456@@Z`
- size: `218`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001e68`
- `0x18000f2c0`
- `0x180010f54`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfoFactory::CreateInstanceFromGamepadReading(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfo *v5; // rax
  unsigned int v6; // edi
  __int64 v7; // rax
  __int64 v8; // rbx

  *a3 = 0;
  v5 = (Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfo *)operator new(
                                                                             0x78u,
                                                                             (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    v7 = Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfo::InjectedInputGamepadInfo(v5);
    v8 = v7;
    if ( a2 )
    {
      *(_DWORD *)(v7 + 64) = *(_DWORD *)(a2 + 8);
      *(_QWORD *)(v7 + 72) = *(_QWORD *)(a2 + 32);
      *(_QWORD *)(v7 + 80) = *(_QWORD *)(a2 + 40);
      *(_QWORD *)(v7 + 88) = *(_QWORD *)(a2 + 16);
      *(_QWORD *)(v7 + 96) = *(_QWORD *)(a2 + 48);
      *(_QWORD *)(v7 + 104) = *(_QWORD *)(a2 + 56);
      *(_QWORD *)(v7 + 112) = *(_QWORD *)(a2 + 24);
      v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v7)(
             v7,
             &GUID_20ae9a3f_df11_4572_a9ab_d75b8a5e48ad,
             a3);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    else
    {
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x18000f2c0  mov     [rsp+arg_0], rbx
0x18000f2c5  mov     [rsp+arg_8], rsi
0x18000f2ca  push    rdi
0x18000f2cb  sub     rsp, 20h
0x18000f2cf  mov     rsi, r8
0x18000f2d2  mov     rdi, rdx
0x18000f2d5  mov     qword ptr [r8], 0
0x18000f2dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f2e3  mov     ecx, 78h ; 'x'; unsigned __int64
0x18000f2e8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f2ed  test    rax, rax
0x18000f2f0  jnz     short loc_18000F2FC
0x18000f2f2  mov     edi, 8007000Eh
0x18000f2f7  jmp     loc_18000F388
0x18000f2fc  mov     rcx, rax; this
0x18000f2ff  call    ??0InjectedInputGamepadInfo@Injection@Preview@Input@UI@Windows@@QEAA@XZ; Windows::UI::Input::Preview::Injection::InjectedInputGamepadInfo::InjectedInputGamepadInfo(void)
0x18000f304  mov     rbx, rax
0x18000f307  test    rdi, rdi
0x18000f30a  jz      short loc_18000F36E
0x18000f30c  mov     ecx, [rdi+8]
0x18000f30f  mov     [rax+40h], ecx
0x18000f312  mov     rcx, [rdi+20h]
0x18000f316  mov     [rax+48h], rcx
0x18000f31a  mov     rcx, [rdi+28h]
0x18000f31e  mov     [rax+50h], rcx
0x18000f322  mov     rcx, [rdi+10h]
0x18000f326  mov     [rax+58h], rcx
0x18000f32a  mov     rax, [rdi+30h]
0x18000f32e  mov     [rbx+60h], rax
0x18000f332  mov     rax, [rdi+38h]
0x18000f336  mov     [rbx+68h], rax
0x18000f33a  mov     rax, [rdi+18h]
0x18000f33e  mov     [rbx+70h], rax
0x18000f342  mov     rax, [rbx]
0x18000f345  mov     r8, rsi
0x18000f348  lea     rdx, _GUID_20ae9a3f_df11_4572_a9ab_d75b8a5e48ad
0x18000f34f  mov     rcx, rbx
0x18000f352  mov     rax, [rax]
0x18000f355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f35a  mov     edi, eax
0x18000f35c  mov     rax, [rbx]
0x18000f35f  mov     rcx, rbx
0x18000f362  mov     rax, [rax+10h]
0x18000f366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f36b  nop
0x18000f36c  jmp     short loc_18000F388
0x18000f36e  test    rbx, rbx
0x18000f371  jz      short loc_18000F383
0x18000f373  mov     rax, [rax]
0x18000f376  mov     rcx, rbx
0x18000f379  mov     rax, [rax+10h]
0x18000f37d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f382  nop
0x18000f383  mov     edi, 80070057h
0x18000f388  mov     eax, edi
0x18000f38a  mov     rbx, [rsp+28h+arg_0]
0x18000f38f  mov     rsi, [rsp+28h+arg_8]
0x18000f394  add     rsp, 20h
0x18000f398  pop     rdi
0x18000f399  retn
```
