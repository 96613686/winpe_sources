# CWinSATTaskMangerTask::IncrimentWinSATIdleRunCount(ulong &)

- ea: `0x180021bc0`
- end: `0x180021c63`
- name: `?IncrimentWinSATIdleRunCount@CWinSATTaskMangerTask@@AEAA_NAEAK@Z`
- size: `163`
- prototype: `bool __fastcall(CWinSATTaskMangerTask *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800209a8`

## callees

- `0x18001b790`
- `0x180021afc`
- `0x180021bc0`
- `0x18002d4dc`

## string_xrefs

- `0x180021c41`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021c37`: `Cannot incriment %s in the registry`

## pseudocode

```c
bool __fastcall CWinSATTaskMangerTask::IncrimentWinSATIdleRunCount(CWinSATTaskMangerTask *this, unsigned int *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  unsigned int v6; // eax
  bool v8; // [rsp+50h] [rbp+18h] BYREF

  v3 = RegHelper::IncrimentDWORDValue(this, L"IdleWinSATRunCount", a2);
  v4 = v3;
  if ( v3 )
  {
    Record_Win32Error_w(
      "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
      0xDEu,
      v3,
      (char)L"IdleWinSATRunCount");
  }
  else
  {
    v8 = 0;
    if ( CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(this, &v8) )
    {
      if ( v8 )
      {
        v6 = RegHelper::IncrimentDWORDValue(v5, L"IdleWinSATRunAfterCount", &v8);
        v4 = v6;
        if ( v6 )
          Record_Win32Error_w(
            "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
            0xECu,
            v6,
            (char)L"IdleWinSATRunAfterCount");
      }
    }
  }
  return v4 == 0;
}

```

## disassembly

```asm
0x180021bc0  mov     [rsp+arg_0], rbx
0x180021bc5  mov     [rsp+arg_8], rsi
0x180021bca  push    rdi
0x180021bcb  sub     rsp, 30h
0x180021bcf  mov     r8, rdx
0x180021bd2  lea     rsi, aIdlewinsatrunc; "IdleWinSATRunCount"
0x180021bd9  mov     rdx, rsi
0x180021bdc  mov     rdi, rcx
0x180021bdf  call    ?IncrimentDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEAK@Z; RegHelper::IncrimentDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong &)
0x180021be4  mov     ebx, eax
0x180021be6  test    eax, eax
0x180021be8  jz      short loc_180021BF6
0x180021bea  mov     qword ptr [rsp+38h+var_18], rsi
0x180021bef  mov     edx, 0DEh
0x180021bf4  jmp     short loc_180021C37
0x180021bf6  lea     rdx, [rsp+38h+arg_10]; bool *
0x180021bfb  mov     [rsp+38h+arg_10], 0
0x180021c00  mov     rcx, rdi; this
0x180021c03  call    ?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z; CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)
0x180021c08  test    al, al
0x180021c0a  jz      short loc_180021C4D
0x180021c0c  cmp     [rsp+38h+arg_10], 0
0x180021c11  jz      short loc_180021C4D
0x180021c13  lea     rdi, aIdlewinsatruna; "IdleWinSATRunAfterCount"
0x180021c1a  mov     rdx, rdi
0x180021c1d  lea     r8, [rsp+38h+arg_10]
0x180021c22  call    ?IncrimentDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEAK@Z; RegHelper::IncrimentDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong &)
0x180021c27  mov     ebx, eax
0x180021c29  test    eax, eax
0x180021c2b  jz      short loc_180021C4D
0x180021c2d  mov     qword ptr [rsp+38h+var_18], rdi; char
0x180021c32  mov     edx, 0ECh; unsigned int
0x180021c37  lea     r9, aCannotIncrimen; "Cannot incriment %s in the registry"
0x180021c3e  mov     r8d, eax; unsigned int
0x180021c41  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021c48  call    Record_Win32Error_w
0x180021c4d  mov     rsi, [rsp+38h+arg_8]
0x180021c52  test    ebx, ebx
0x180021c54  mov     rbx, [rsp+38h+arg_0]
0x180021c59  setz    al
0x180021c5c  add     rsp, 30h
0x180021c60  pop     rdi
0x180021c61  retn
```
