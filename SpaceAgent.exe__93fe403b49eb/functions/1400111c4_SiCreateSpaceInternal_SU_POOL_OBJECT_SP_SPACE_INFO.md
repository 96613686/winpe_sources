# SiCreateSpaceInternal(_SU_POOL_OBJECT *,_SP_SPACE_INFO *)

- ea: `0x1400111c4`
- end: `0x14001123f`
- name: `?SiCreateSpaceInternal@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@@Z`
- size: `123`
- prototype: `int __fastcall(struct _SU_POOL_OBJECT *, struct _SP_SPACE_INFO *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010b5c`
- `0x140010f8c`

## callees

- `0x1400111c4`
- `0x140011fb4`
- `0x140012164`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x14001122e`
- `KERNEL32!DeviceIoControl` at `0x14001122e`

## pseudocode

```c
int __fastcall SiCreateSpaceInternal(struct _SU_POOL_OBJECT *a1, struct _SP_SPACE_INFO *a2)
{
  int result; // eax
  DWORD BytesReturned; // [rsp+60h] [rbp+18h] BYREF

  BytesReturned = 0;
  result = SiIsSpaceTemplateCompatible(a1, a2);
  if ( result )
  {
    result = SiValidateSpace(a1, a2, 0);
    if ( result )
      return DeviceIoControl(Spaceport, 0xE7C810u, a2, *((_DWORD *)a2 + 1), 0, 0, &BytesReturned, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1400111c4  mov     [rsp+arg_0], rbx
0x1400111c9  push    rdi
0x1400111ca  sub     rsp, 40h
0x1400111ce  mov     rbx, rdx
0x1400111d1  mov     [rsp+48h+BytesReturned], 0
0x1400111d9  mov     rdi, rcx
0x1400111dc  call    ?SiIsSpaceTemplateCompatible@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@@Z; SiIsSpaceTemplateCompatible(_SU_POOL_OBJECT *,_SP_SPACE_INFO *)
0x1400111e1  test    eax, eax
0x1400111e3  jz      short loc_140011234
0x1400111e5  xor     r8d, r8d; unsigned __int8
0x1400111e8  mov     rdx, rbx; struct _SP_SPACE_INFO *
0x1400111eb  mov     rcx, rdi; struct _SU_POOL_OBJECT *
0x1400111ee  call    ?SiValidateSpace@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@E@Z; SiValidateSpace(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,uchar)
0x1400111f3  test    eax, eax
0x1400111f5  jz      short loc_140011234
0x1400111f7  mov     r9d, [rbx+4]; nInBufferSize
0x1400111fb  lea     rax, [rsp+48h+BytesReturned]
0x140011200  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x140011207  mov     r8, rbx; lpInBuffer
0x14001120a  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x140011213  mov     edx, 0E7C810h; dwIoControlCode
0x140011218  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x14001121d  mov     [rsp+48h+nOutBufferSize], 0; nOutBufferSize
0x140011225  mov     [rsp+48h+lpOutBuffer], 0; lpOutBuffer
0x14001122e  call    cs:__imp_DeviceIoControl
0x140011234  mov     rbx, [rsp+48h+arg_0]
0x140011239  add     rsp, 40h
0x14001123d  pop     rdi
0x14001123e  retn
```
