# CWinSATTaskMangerTask::FinalConstruct(void)

- ea: `0x180020d34`
- end: `0x180020dd1`
- name: `?FinalConstruct@CWinSATTaskMangerTask@@QEAAJXZ`
- size: `157`
- prototype: `__int64 __fastcall(CWinSATTaskMangerTask *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016a90`
- `0x18001725c`

## callees

- `0x1800161e0`
- `0x180016210`
- `0x18001b790`
- `0x180020d34`
- `0x180033010`

## string_xrefs

- `0x180020d9e`: `Cannot create registry key %s`
- `0x180020dad`: `base\winsat\api-dll\winsattaskmangertask.cpp`

## pseudocode

```c
__int64 __fastcall CWinSATTaskMangerTask::FinalConstruct(
        CWinSATTaskMangerTask *this,
        __int64 a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  void (__fastcall *v5)(void *, __int64, _QWORD); // rax
  unsigned int v6; // eax
  unsigned int v8; // [rsp+20h] [rbp-48h]
  _QWORD v9[5]; // [rsp+40h] [rbp-28h] BYREF

  if ( !*((_BYTE *)this + 184) )
  {
    v5 = (void (__fastcall *)(void *, __int64, _QWORD))*((_QWORD *)this + 18);
    if ( v5 )
      v5(&unk_18004A8B0, 142082, 0);
    *((_BYTE *)this + 184) = 1;
  }
  memset(v9, 0, 24);
  v6 = ATL::CRegKey::Create(
         (ATL::CRegKey *)v9,
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI",
         a4,
         v8);
  if ( v6 )
    Record_Win32Error_w(
      "base\\winsat\\api-dll\\winsattaskmangertask.cpp",
      0x44u,
      v6,
      (char)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI");
  ATL::CRegKey::Close((ATL::CRegKey *)v9);
  return 0;
}

```

## disassembly

```asm
0x180020d34  push    rbx
0x180020d36  sub     rsp, 60h
0x180020d3a  cmp     byte ptr [rcx+0B8h], 0
0x180020d41  mov     rbx, rcx
0x180020d44  jnz     short loc_180020D6D
0x180020d46  mov     rax, [rcx+90h]
0x180020d4d  test    rax, rax
0x180020d50  jz      short loc_180020D66
0x180020d52  xor     r8d, r8d
0x180020d55  lea     rcx, unk_18004A8B0
0x180020d5c  mov     edx, 22B02h
0x180020d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d66  mov     byte ptr [rbx+0B8h], 1
0x180020d6d  and     [rsp+68h+var_28], 0
0x180020d73  lea     rbx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180020d7a  and     [rsp+68h+var_20], 0
0x180020d80  lea     rcx, [rsp+68h+var_28]; this
0x180020d85  and     [rsp+68h+var_18], 0
0x180020d8b  mov     r8, rbx; lpSubKey
0x180020d8e  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180020d95  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180020d9a  test    eax, eax
0x180020d9c  jz      short loc_180020DBE
0x180020d9e  lea     r9, aCannotCreateRe; "Cannot create registry key %s"
0x180020da5  mov     qword ptr [rsp+68h+var_48], rbx; char
0x180020daa  mov     r8d, eax; unsigned int
0x180020dad  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020db4  mov     edx, 44h ; 'D'; unsigned int
0x180020db9  call    Record_Win32Error_w
0x180020dbe  lea     rcx, [rsp+68h+var_28]; this
0x180020dc3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180020dc8  xor     eax, eax
0x180020dca  add     rsp, 60h
0x180020dce  pop     rbx
0x180020dcf  retn
```
