# ATL::AtlUnRegisterTypeLib(HINSTANCE__ *,ushort const *)

- ea: `0x180002de8`
- end: `0x180002ed3`
- name: `?AtlUnRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z`
- size: `235`
- prototype: `__int64 __fastcall(HINSTANCE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001650`

## callees

- `0x180002c24`
- `0x180002de8`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180002e57`
- `KERNEL32!GetProcAddress` at `0x180002e57`
- `KERNEL32!GetModuleHandleW` at `0x180002e42`
- `KERNEL32!GetModuleHandleW` at `0x180002e42`
- `OLEAUT32!__imp_SysFreeString` at `0x180002ec5`
- `OLEAUT32!__imp_SysFreeString` at `0x180002ec5`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x180002e65`

## string_xrefs

- `0x180002e3b`: `OLEAUT32.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ATL::AtlUnRegisterTypeLib(HINSTANCE a1, const unsigned __int16 *a2)
{
  int v2; // ebx
  HMODULE ModuleHandleW; // rax
  void *ProcAddress; // r10
  struct ITypeLib *v6; // [rsp+48h] [rbp+10h] BYREF
  __int64 v7; // [rsp+50h] [rbp+18h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp+20h] BYREF

  bstrString = 0;
  v6 = 0;
  v2 = ATL::AtlLoadTypeLib(a1, a2, &bstrString, &v6);
  if ( v2 >= 0 )
  {
    v2 = ((__int64 (__fastcall *)(struct ITypeLib *, __int64 *))v6->lpVtbl->GetLibAttr)(v6, &v7);
    if ( v2 >= 0 )
    {
      if ( !ATL::_AtlRegisterPerUser
        || (ModuleHandleW = GetModuleHandleW(L"OLEAUT32.DLL")) == 0
        || (ProcAddress = GetProcAddress(ModuleHandleW, "UnRegisterTypeLibForUser")) == 0 )
      {
        ProcAddress = UnRegisterTypeLib;
      }
      v2 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))ProcAddress)(
             v7,
             *(unsigned __int16 *)(v7 + 24),
             *(unsigned __int16 *)(v7 + 26),
             *(unsigned int *)(v7 + 16),
             *(_DWORD *)(v7 + 20));
      ((void (__fastcall *)(struct ITypeLib *, __int64))v6->lpVtbl->ReleaseTLibAttr)(v6, v7);
    }
  }
  if ( v6 )
    ((void (__fastcall *)(struct ITypeLib *))v6->lpVtbl->Release)(v6);
  SysFreeString(bstrString);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180002de8  mov     rax, rsp
0x180002deb  mov     [rax+10h], rdx
0x180002def  push    rbx
0x180002df0  sub     rsp, 30h
0x180002df4  and     qword ptr [rax+20h], 0
0x180002df9  and     qword ptr [rax+10h], 0
0x180002dfe  lea     r9, [rax+10h]; struct ITypeLib **
0x180002e02  lea     r8, [rax+20h]; unsigned __int16 **
0x180002e06  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x180002e0b  mov     ebx, eax
0x180002e0d  test    eax, eax
0x180002e0f  js      loc_180002EA8
0x180002e15  mov     rcx, [rsp+38h+arg_8]
0x180002e1a  mov     rax, [rcx]
0x180002e1d  lea     rdx, [rsp+38h+arg_10]
0x180002e22  mov     rax, [rax+38h]
0x180002e26  call    cs:__guard_dispatch_icall_fptr
0x180002e2c  mov     ebx, eax
0x180002e2e  test    eax, eax
0x180002e30  js      short loc_180002EA8
0x180002e32  cmp     cs:?_AtlRegisterPerUser@ATL@@3_NA, 1; bool ATL::_AtlRegisterPerUser
0x180002e39  jnz     short loc_180002E65
0x180002e3b  lea     rcx, ModuleName; "OLEAUT32.DLL"
0x180002e42  call    cs:__imp_GetModuleHandleW
0x180002e48  test    rax, rax
0x180002e4b  jz      short loc_180002E65
0x180002e4d  lea     rdx, aUnregistertype; "UnRegisterTypeLibForUser"
0x180002e54  mov     rcx, rax; hModule
0x180002e57  call    cs:__imp_GetProcAddress
0x180002e5d  mov     r10, rax
0x180002e60  test    rax, rax
0x180002e63  jnz     short loc_180002E6C
0x180002e65  mov     r10, cs:__imp_UnRegisterTypeLib
0x180002e6c  mov     rcx, [rsp+38h+arg_10]
0x180002e71  mov     eax, [rcx+14h]
0x180002e74  mov     [rsp+38h+var_18], eax
0x180002e78  mov     r9d, [rcx+10h]
0x180002e7c  movzx   r8d, word ptr [rcx+1Ah]
0x180002e81  movzx   edx, word ptr [rcx+18h]
0x180002e85  mov     rax, r10
0x180002e88  call    cs:__guard_dispatch_icall_fptr
0x180002e8e  mov     ebx, eax
0x180002e90  mov     rcx, [rsp+38h+arg_8]
0x180002e95  mov     rax, [rcx]
0x180002e98  mov     rdx, [rsp+38h+arg_10]
0x180002e9d  mov     rax, [rax+60h]
0x180002ea1  call    cs:__guard_dispatch_icall_fptr
0x180002ea7  nop
0x180002ea8  mov     rcx, [rsp+38h+arg_8]
0x180002ead  test    rcx, rcx
0x180002eb0  jz      short loc_180002EC0
0x180002eb2  mov     rax, [rcx]
0x180002eb5  mov     rax, [rax+10h]
0x180002eb9  call    cs:__guard_dispatch_icall_fptr
0x180002ebf  nop
0x180002ec0  mov     rcx, [rsp+38h+bstrString]; bstrString
0x180002ec5  call    cs:__imp_SysFreeString
0x180002ecb  mov     eax, ebx
0x180002ecd  add     rsp, 30h
0x180002ed1  pop     rbx
0x180002ed2  retn
```
