# AudioBufferImpl::GetIids(ulong *,_GUID * *)

- ea: `0x180039650`
- end: `0x1800396c6`
- name: `?GetIids@AudioBufferImpl@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `118`
- prototype: `__int64 __fastcall(AudioBufferImpl *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800396d0`
- `0x1800396e0`
- `0x1800396f0`

## callees

- `0x180038f2c`
- `0x180039650`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039672`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039672`

## pseudocode

```c
__int64 __fastcall AudioBufferImpl::GetIids(AudioBufferImpl *this, unsigned int *a2, struct _GUID **a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 2;
  *v5 = GUID_35175827_724b_4c6a_b130_f6537f9ae0d0;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<MediaBufferImpl>>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 4;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180039650  mov     [rsp+arg_0], rbx
0x180039655  push    rdi
0x180039656  sub     rsp, 20h
0x18003965a  mov     qword ptr [r8], 0
0x180039661  mov     ecx, 40h ; '@'; cb
0x180039666  mov     dword ptr [rdx], 0
0x18003966c  mov     rbx, r8
0x18003966f  mov     rdi, rdx
0x180039672  call    cs:__imp_CoTaskMemAlloc
0x180039678  mov     r8, rax
0x18003967b  test    rax, rax
0x18003967e  jnz     short loc_180039687
0x180039680  mov     eax, 8007000Eh
0x180039685  jmp     short loc_1800396BB
0x180039687  movups  xmm0, xmmword ptr cs:_GUID_35175827_724b_4c6a_b130_f6537f9ae0d0.Data1
0x18003968e  lea     rdx, [rsp+28h+arg_8]
0x180039693  mov     [rsp+28h+arg_8], 2
0x18003969b  movdqu  xmmword ptr [rax], xmm0
0x18003969f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800396a6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800396ab  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VMediaBufferImpl@@@Details@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<MediaBufferImpl>>::FillArrayWithIid(ulong *,_GUID *)
0x1800396b0  mov     dword ptr [rdi], 4
0x1800396b6  xor     eax, eax
0x1800396b8  mov     [rbx], r8
0x1800396bb  mov     rbx, [rsp+28h+arg_0]
0x1800396c0  add     rsp, 20h
0x1800396c4  pop     rdi
0x1800396c5  retn
```
