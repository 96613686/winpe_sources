# CWinSATTaskMangerTask::ReadErrorCountRegKey(ulong &)

- ea: `0x180021cc0`
- end: `0x180021d7b`
- name: `?ReadErrorCountRegKey@CWinSATTaskMangerTask@@AEAA_NAEAK@Z`
- size: `187`
- prototype: `bool(CWinSATTaskMangerTask *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800213a4`

## callees

- `0x18000ee1c`
- `0x1800161e0`
- `0x18001b790`
- `0x180021c6c`
- `0x180021cc0`

## string_xrefs

- `0x180021cfe`: `cannot open the winast API registry key`
- `0x180021d0b`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021d6d`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021d5e`: `cannot read the task error count from the registry`
- `0x180021d28`: `TaskErrorCount`

## pseudocode

```c
char __fastcall CWinSATTaskMangerTask::ReadErrorCountRegKey(CWinSATTaskMangerTask *this, unsigned int *a2)
{
  char v2; // bl
  unsigned int v4; // eax
  unsigned int DWORDValue; // eax
  char v7[40]; // [rsp+20h] [rbp-28h] BYREF

  v2 = 0;
  memset(v7, 0, 24);
  v4 = ATL::CRegKey::Open(
         (ATL::CRegKey *)v7,
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI",
         0xF003Fu);
  if ( v4 )
  {
    Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", 0x4Au, v4, v7[0]);
    ATL::CRegKey::Close((ATL::CRegKey *)v7);
    return 0;
  }
  DWORDValue = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v7, L"TaskErrorCount", a2);
  if ( DWORDValue )
  {
    if ( DWORDValue != 2 )
    {
      Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", 0x52u, DWORDValue, v7[0]);
      goto LABEL_7;
    }
    *a2 = 0;
  }
  v2 = 1;
LABEL_7:
  ATL::CRegKey::Close((ATL::CRegKey *)v7);
  return v2;
}

```

## disassembly

```asm
0x180021cc0  mov     rax, rsp
0x180021cc3  mov     [rax+8], rbx
0x180021cc7  push    rdi
0x180021cc8  sub     rsp, 40h
0x180021ccc  xor     ebx, ebx
0x180021cce  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180021cd5  mov     rdi, rdx
0x180021cd8  mov     [rax-28h], rbx
0x180021cdc  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180021ce3  mov     [rax-20h], rbx
0x180021ce7  mov     r9d, 0F003Fh; unsigned int
0x180021ced  mov     [rax-18h], rbx
0x180021cf1  lea     rcx, [rax-28h]; this
0x180021cf5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180021cfa  test    eax, eax
0x180021cfc  jz      short loc_180021D25
0x180021cfe  lea     r9, aCannotOpenTheW; "cannot open the winast API registry key"
0x180021d05  mov     r8d, eax; unsigned int
0x180021d08  lea     edx, [rbx+4Ah]; unsigned int
0x180021d0b  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021d12  call    Record_Win32Error_w
0x180021d17  lea     rcx, [rsp+48h+var_28]; this
0x180021d1c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180021d21  xor     al, al
0x180021d23  jmp     short loc_180021D52
0x180021d25  mov     r8, rdi; unsigned int *
0x180021d28  lea     rdx, aTaskerrorcount; "TaskErrorCount"
0x180021d2f  lea     rcx, [rsp+48h+var_28]; this
0x180021d34  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180021d39  test    eax, eax
0x180021d3b  jz      short loc_180021D44
0x180021d3d  cmp     eax, 2
0x180021d40  jnz     short loc_180021D5E
0x180021d42  mov     [rdi], ebx
0x180021d44  mov     bl, 1
0x180021d46  lea     rcx, [rsp+48h+var_28]; this
0x180021d4b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180021d50  mov     al, bl
0x180021d52  mov     rbx, [rsp+48h+arg_0]
0x180021d57  add     rsp, 40h
0x180021d5b  pop     rdi
0x180021d5c  retn
0x180021d5e  lea     r9, aCannotReadTheT; "cannot read the task error count from t"...
0x180021d65  mov     r8d, eax; unsigned int
0x180021d68  mov     edx, 52h ; 'R'; unsigned int
0x180021d6d  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021d74  call    Record_Win32Error_w
0x180021d79  jmp     short loc_180021D46
```
