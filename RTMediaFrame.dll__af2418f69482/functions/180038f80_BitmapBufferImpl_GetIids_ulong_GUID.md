# BitmapBufferImpl::GetIids(ulong *,_GUID * *)

- ea: `0x180038f80`
- end: `0x180038ff6`
- name: `?GetIids@BitmapBufferImpl@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `118`
- prototype: `__int64 __fastcall(BitmapBufferImpl *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039000`
- `0x180039010`
- `0x180039020`

## callees

- `0x180038f2c`
- `0x180038f80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038fa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038fa2`

## pseudocode

```c
__int64 __fastcall BitmapBufferImpl::GetIids(BitmapBufferImpl *this, unsigned int *a2, struct _GUID **a3)
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
  *v5 = GUID_a53e04c4_399c_438c_b28f_a63a6b83d1a1;
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
0x180038f80  mov     [rsp+arg_0], rbx
0x180038f85  push    rdi
0x180038f86  sub     rsp, 20h
0x180038f8a  mov     qword ptr [r8], 0
0x180038f91  mov     ecx, 40h ; '@'; cb
0x180038f96  mov     dword ptr [rdx], 0
0x180038f9c  mov     rbx, r8
0x180038f9f  mov     rdi, rdx
0x180038fa2  call    cs:__imp_CoTaskMemAlloc
0x180038fa8  mov     r8, rax
0x180038fab  test    rax, rax
0x180038fae  jnz     short loc_180038FB7
0x180038fb0  mov     eax, 8007000Eh
0x180038fb5  jmp     short loc_180038FEB
0x180038fb7  movups  xmm0, xmmword ptr cs:_GUID_a53e04c4_399c_438c_b28f_a63a6b83d1a1.Data1
0x180038fbe  lea     rdx, [rsp+28h+arg_8]
0x180038fc3  mov     [rsp+28h+arg_8], 2
0x180038fcb  movdqu  xmmword ptr [rax], xmm0
0x180038fcf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180038fd6  movdqu  xmmword ptr [rax+10h], xmm1
0x180038fdb  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VMediaBufferImpl@@@Details@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<MediaBufferImpl>>::FillArrayWithIid(ulong *,_GUID *)
0x180038fe0  mov     dword ptr [rdi], 4
0x180038fe6  xor     eax, eax
0x180038fe8  mov     [rbx], r8
0x180038feb  mov     rbx, [rsp+28h+arg_0]
0x180038ff0  add     rsp, 20h
0x180038ff4  pop     rdi
0x180038ff5  retn
```
