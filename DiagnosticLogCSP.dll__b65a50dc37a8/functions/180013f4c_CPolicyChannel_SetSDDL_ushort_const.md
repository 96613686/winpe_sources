# CPolicyChannel::SetSDDL(ushort const *)

- ea: `0x180013f4c`
- end: `0x180013fd5`
- name: `?SetSDDL@CPolicyChannel@@QEAAJPEBG@Z`
- size: `137`
- prototype: `int(CPolicyChannel *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d4f0`

## callees

- `0x180001108`
- `0x180001b90`
- `0x180011f58`
- `0x180013f4c`

## string_xrefs

- `0x180013f64`: `ChannelAccess`

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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v5 = v2;
    v7 = (int *)&v5;
    v8 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18004AE90, (unsigned __int8 *)byte_180041F2F, 0, 0, 3u, &v6);
  }
  return v3;
}

```

## disassembly

```asm
0x180013f4c  push    rbx
0x180013f4e  sub     rsp, 70h
0x180013f52  mov     rax, cs:__security_cookie
0x180013f59  xor     rax, rsp
0x180013f5c  mov     [rsp+78h+var_10], rax
0x180013f61  mov     r8, rdx; unsigned __int16 *
0x180013f64  lea     rdx, aChannelaccess; "ChannelAccess"
0x180013f6b  call    ?SetStringValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBG1@Z; CRegUtils::SetStringValue(ATL::CRegKey &,ushort const *,ushort const *)
0x180013f70  mov     ebx, eax
0x180013f72  mov     ecx, cs:dword_18004AE90
0x180013f78  cmp     ecx, 5
0x180013f7b  jbe     short loc_180013FBF
0x180013f7d  mov     [rsp+78h+var_48], eax
0x180013f81  lea     rax, [rsp+78h+var_48]
0x180013f86  mov     [rsp+78h+var_20], rax
0x180013f8b  mov     [rsp+78h+var_18], 4
0x180013f94  lea     rax, [rsp+78h+var_40]
0x180013f99  mov     [rsp+78h+var_50], rax
0x180013f9e  mov     [rsp+78h+var_58], 3
0x180013fa6  xor     r9d, r9d
0x180013fa9  xor     r8d, r8d
0x180013fac  lea     rdx, byte_180041F2F
0x180013fb3  lea     rcx, dword_18004AE90
0x180013fba  call    _tlgWriteTransfer_EventWriteTransfer
0x180013fbf  mov     eax, ebx
0x180013fc1  mov     rcx, [rsp+78h+var_10]
0x180013fc6  xor     rcx, rsp; StackCookie
0x180013fc9  call    __security_check_cookie
0x180013fce  add     rsp, 70h
0x180013fd2  pop     rbx
0x180013fd3  retn
```
