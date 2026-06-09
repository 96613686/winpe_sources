# CPcmPin::UpdateMpmPlayStatus(long)

- ea: `0x14001efb0`
- end: `0x14001effd`
- name: `?UpdateMpmPlayStatus@CPcmPin@@AEAAXJ@Z`
- size: `77`
- prototype: `void __fastcall(CPcmPin *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140083af4`

## callees

- `0x140006410`
- `0x14001efb0`
- `0x14001f2b8`

## import_xrefs

- `btampm!BtaMpmUpdatePlayStatus` at `0x14001efdb`
- `btampm!BtaMpmUpdatePlayStatus` at `0x14001efdb`

## pseudocode

```c
void __fastcall CPcmPin::UpdateMpmPlayStatus(CPcmPin *this, int a2)
{
  _QWORD *v3; // [rsp+20h] [rbp-18h] BYREF
  utl::_RefCountBase *v4; // [rsp+28h] [rbp-10h]

  A2DP_Device::GetMPMContext(*((_QWORD *)this + 4), &v3);
  if ( v3 )
    BtaMpmUpdatePlayStatus(*v3, a2 == 3);
  if ( v4 )
    utl::_RefCountBase::_DecStrong(v4);
}

```

## disassembly

```asm
0x14001efb0  push    rbx
0x14001efb2  sub     rsp, 30h
0x14001efb6  mov     rcx, [rcx+20h]
0x14001efba  mov     ebx, edx
0x14001efbc  lea     rdx, [rsp+38h+var_18]
0x14001efc1  call    ?GetMPMContext@A2DP_Device@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@utl@@XZ; A2DP_Device::GetMPMContext(void)
0x14001efc6  mov     rcx, [rsp+38h+var_18]
0x14001efcb  test    rcx, rcx
0x14001efce  jz      short loc_14001EFE7
0x14001efd0  mov     rcx, [rcx]
0x14001efd3  xor     edx, edx
0x14001efd5  cmp     ebx, 3
0x14001efd8  setz    dl
0x14001efdb  call    cs:__imp_BtaMpmUpdatePlayStatus
0x14001efe2  nop     dword ptr [rax+rax+00h]
0x14001efe7  mov     rcx, [rsp+38h+var_10]; this
0x14001efec  test    rcx, rcx
0x14001efef  jz      short loc_14001EFF6
0x14001eff1  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001eff6  add     rsp, 30h
0x14001effa  pop     rbx
0x14001effb  retn
```
