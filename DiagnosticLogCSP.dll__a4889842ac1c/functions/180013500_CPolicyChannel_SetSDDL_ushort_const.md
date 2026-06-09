# CPolicyChannel::SetSDDL(ushort const *)

- ea: `0x180013500`
- end: `0x180013588`
- name: `?SetSDDL@CPolicyChannel@@QEAAJPEBG@Z`
- size: `136`
- prototype: `int(CPolicyChannel *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ced0`

## callees

- `0x180001104`
- `0x180001b60`
- `0x180011624`
- `0x180013500`

## string_xrefs

- `0x180013518`: `ChannelAccess`

## pseudocode

```c
__int64 __fastcall CPolicyChannel::SetSDDL(HKEY *this, const BYTE *a2)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int v5; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+38h] [rbp-40h] BYREF
  int *v7; // [rsp+58h] [rbp-20h]
  __int64 v8; // [rsp+60h] [rbp-18h]

  v2 = CRegUtils::SetStringValue(this, L"ChannelAccess", a2);
  v3 = v2;
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v5 = v2;
    v7 = (int *)&v5;
    v8 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180048E90, (unsigned __int8 *)byte_18003FF2F, 0, 0, 3u, &v6);
  }
  return v3;
}

```

## disassembly

```asm
0x180013500  push    rbx
0x180013502  sub     rsp, 70h
0x180013506  mov     rax, cs:__security_cookie
0x18001350d  xor     rax, rsp
0x180013510  mov     [rsp+78h+var_10], rax
0x180013515  mov     r8, rdx; unsigned __int16 *
0x180013518  lea     rdx, aChannelaccess; "ChannelAccess"
0x18001351f  call    ?SetStringValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBG1@Z; CRegUtils::SetStringValue(ATL::CRegKey &,ushort const *,ushort const *)
0x180013524  mov     ebx, eax
0x180013526  mov     ecx, cs:dword_180048E90
0x18001352c  cmp     ecx, 5
0x18001352f  jbe     short loc_180013573
0x180013531  mov     [rsp+78h+var_48], eax
0x180013535  lea     rax, [rsp+78h+var_48]
0x18001353a  mov     [rsp+78h+var_20], rax
0x18001353f  mov     [rsp+78h+var_18], 4
0x180013548  lea     rax, [rsp+78h+var_40]
0x18001354d  mov     [rsp+78h+var_50], rax
0x180013552  mov     [rsp+78h+var_58], 3
0x18001355a  xor     r9d, r9d
0x18001355d  xor     r8d, r8d
0x180013560  lea     rdx, byte_18003FF2F
0x180013567  lea     rcx, dword_180048E90
0x18001356e  call    _tlgWriteTransfer_EventWriteTransfer
0x180013573  mov     eax, ebx
0x180013575  mov     rcx, [rsp+78h+var_10]
0x18001357a  xor     rcx, rsp; StackCookie
0x18001357d  call    __security_check_cookie
0x180013582  add     rsp, 70h
0x180013586  pop     rbx
0x180013587  retn
```
