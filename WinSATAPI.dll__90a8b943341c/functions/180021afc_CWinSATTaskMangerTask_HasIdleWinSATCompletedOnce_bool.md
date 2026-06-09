# CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)

- ea: `0x180021afc`
- end: `0x180021bb8`
- name: `?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z`
- size: `188`
- prototype: `bool __fastcall(CWinSATTaskMangerTask *__hidden this, bool *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800213a4`
- `0x180021898`
- `0x180021bc0`
- `0x180021f00`

## callees

- `0x18001b790`
- `0x180021afc`
- `0x18002d59c`

## string_xrefs

- `0x180021b61`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021b5a`: `cannot read the %s value from the registry`
- `0x180021b4b`: `IdleAssessmentCompletionCount`

## pseudocode

```c
char __fastcall CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(CWinSATTaskMangerTask *this, bool *a2)
{
  int v2; // r8d
  unsigned int v5; // eax
  char result; // al
  int v7; // eax
  char v8; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+50h] [rbp+18h] BYREF

  v2 = *((_DWORD *)this + 48);
  if ( v2 )
  {
    *a2 = v2 != 1;
  }
  else
  {
    v8 = 0;
    v9 = 0;
    v5 = RegHelper::ReadDWORDValue(this, a2, &v9, &v8);
    if ( v5 )
    {
      Record_Win32Error_w(
        "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
        0x110u,
        v5,
        (char)L"IdleAssessmentCompletionCount");
      *a2 = 0;
      result = 0;
      *((_DWORD *)this + 48) = 1;
      return result;
    }
    v7 = v9;
    if ( v8 )
      v7 = 0;
    if ( v7 )
    {
      *a2 = 1;
      *((_DWORD *)this + 48) = 2;
    }
    else
    {
      *a2 = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180021afc  mov     [rsp+arg_8], rbx
0x180021b01  mov     [rsp+arg_18], rsi
0x180021b06  push    rdi
0x180021b07  sub     rsp, 30h
0x180021b0b  mov     r8d, [rcx+0C0h]
0x180021b12  xor     esi, esi
0x180021b14  mov     rbx, rdx
0x180021b17  mov     rdi, rcx
0x180021b1a  test    r8d, r8d
0x180021b1d  jz      short loc_180021B2F
0x180021b1f  cmp     r8d, 1
0x180021b23  jz      short loc_180021B2A
0x180021b25  mov     byte ptr [rdx], 1
0x180021b28  jmp     short loc_180021BA5
0x180021b2a  mov     [rdx], sil
0x180021b2d  jmp     short loc_180021BA5
0x180021b2f  lea     r9, [rsp+38h+arg_0]
0x180021b34  mov     [rsp+38h+arg_0], sil
0x180021b39  lea     r8, [rsp+38h+arg_10]
0x180021b3e  mov     [rsp+38h+arg_10], esi
0x180021b42  call    ?ReadDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEAKPEA_N@Z; RegHelper::ReadDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong &,bool *)
0x180021b47  test    eax, eax
0x180021b49  jz      short loc_180021B83
0x180021b4b  lea     rcx, aIdleassessment; "IdleAssessmentCompletionCount"
0x180021b52  mov     r8d, eax; unsigned int
0x180021b55  mov     qword ptr [rsp+38h+var_18], rcx; char
0x180021b5a  lea     r9, aCannotReadTheS; "cannot read the %s value from the regis"...
0x180021b61  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021b68  mov     edx, 110h; unsigned int
0x180021b6d  call    Record_Win32Error_w
0x180021b72  mov     [rbx], sil
0x180021b75  xor     al, al
0x180021b77  mov     dword ptr [rdi+0C0h], 1
0x180021b81  jmp     short loc_180021BA7
0x180021b83  cmp     [rsp+38h+arg_0], sil
0x180021b88  mov     eax, [rsp+38h+arg_10]
0x180021b8c  cmovnz  eax, esi
0x180021b8f  test    eax, eax
0x180021b91  jz      short loc_180021BA2
0x180021b93  mov     byte ptr [rbx], 1
0x180021b96  mov     dword ptr [rdi+0C0h], 2
0x180021ba0  jmp     short loc_180021BA5
0x180021ba2  mov     [rbx], sil
0x180021ba5  mov     al, 1
0x180021ba7  mov     rbx, [rsp+38h+arg_8]
0x180021bac  mov     rsi, [rsp+38h+arg_18]
0x180021bb1  add     rsp, 30h
0x180021bb5  pop     rdi
0x180021bb6  retn
```
