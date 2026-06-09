# Microsoft::WRL::Details::Make<PidlEnum,std::shared_ptr<RfbQueryBase> &,ulong &>(std::shared_ptr<RfbQueryBase> &,ulong &)

- ea: `0x180014a38`
- end: `0x180014afc`
- name: `??$Make@VPidlEnum@@AEAV?$shared_ptr@VRfbQueryBase@@@std@@AEAK@Details@WRL@Microsoft@@YA?AV?$ComPtr@VPidlEnum@@@12@AEAV?$shared_ptr@VRfbQueryBase@@@std@@AEAK@Z`
- size: `196`
- prototype: `__int64 *__fastcall(__int64 *, __int128 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800152e0`

## callees

- `0x1800020d0`
- `0x1800020f4`
- `0x180009700`
- `0x180009a90`
- `0x180014a38`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::Details::Make<PidlEnum,std::shared_ptr<RfbQueryBase> &,unsigned long &>(
        __int64 *a1,
        __int128 *a2,
        unsigned int *a3)
{
  void *v6; // rax
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 v11; // r8
  __int128 v13; // [rsp+38h] [rbp-20h] BYREF

  *a1 = 0;
  v6 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
  if ( v6 )
  {
    v7 = *a3;
    v13 = 0;
    v8 = *((_QWORD *)a2 + 1);
    if ( v8 )
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
    v13 = *a2;
    v10 = PidlEnum::PidlEnum(v6, &v13, v7);
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEnumIDList>::Release(
        *a1,
        v9,
        v11);
    *a1 = v10;
  }
  return a1;
}

```

## disassembly

```asm
0x180014a38  mov     rax, rsp
0x180014a3b  mov     [rax+10h], rbx
0x180014a3f  mov     [rax+18h], rsi
0x180014a43  mov     [rax+8], rcx
0x180014a47  push    rdi
0x180014a48  sub     rsp, 50h
0x180014a4c  mov     rsi, r8
0x180014a4f  mov     rdi, rdx
0x180014a52  mov     rbx, rcx
0x180014a55  mov     dword ptr [rax-38h], 0
0x180014a5c  mov     qword ptr [rcx], 0
0x180014a63  mov     dword ptr [rax-38h], 1
0x180014a6a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014a71  mov     ecx, 30h ; '0'; unsigned __int64
0x180014a76  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014a7b  mov     [rsp+58h+arg_18], rax
0x180014a80  mov     [rsp+58h+var_30], rax
0x180014a85  test    rax, rax
0x180014a88  jz      short loc_180014ADB
0x180014a8a  mov     [rsp+58h+var_28], rax
0x180014a8f  mov     r8d, [rsi]
0x180014a92  xorps   xmm0, xmm0
0x180014a95  movdqu  [rsp+58h+var_20], xmm0
0x180014a9b  mov     rcx, [rdi+8]
0x180014a9f  test    rcx, rcx
0x180014aa2  jz      short loc_180014AA8
0x180014aa4  lock inc dword ptr [rcx+8]
0x180014aa8  mov     rcx, [rdi]
0x180014aab  mov     qword ptr [rsp+58h+var_20], rcx
0x180014ab0  mov     rcx, [rdi+8]
0x180014ab4  mov     qword ptr [rsp+58h+var_20+8], rcx
0x180014ab9  lea     rdx, [rsp+58h+var_20]
0x180014abe  mov     rcx, rax
0x180014ac1  call    ??0PidlEnum@@QEAA@V?$shared_ptr@VRfbQueryBase@@@std@@K@Z; PidlEnum::PidlEnum(std::shared_ptr<RfbQueryBase>,ulong)
0x180014ac6  mov     rdi, rax
0x180014ac9  mov     rcx, [rbx]
0x180014acc  test    rcx, rcx
0x180014acf  jz      short loc_180014AD6
0x180014ad1  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEnumIDList@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEnumIDList>::Release(void)
0x180014ad6  mov     [rbx], rdi
0x180014ad9  xor     eax, eax
0x180014adb  test    rax, rax
0x180014ade  jz      short loc_180014AE8
0x180014ae0  mov     rcx, rax; Block
0x180014ae3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014ae8  mov     rax, rbx
0x180014aeb  mov     rbx, [rsp+58h+arg_8]
0x180014af0  mov     rsi, [rsp+58h+arg_10]
0x180014af5  add     rsp, 50h
0x180014af9  pop     rdi
0x180014afa  retn
```
