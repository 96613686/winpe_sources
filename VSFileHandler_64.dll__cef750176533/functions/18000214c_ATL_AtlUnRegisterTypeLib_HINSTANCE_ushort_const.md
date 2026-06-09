# ATL::AtlUnRegisterTypeLib(HINSTANCE__ *,ushort const *)

- ea: `0x18000214c`
- end: `0x18000222e`
- name: `?AtlUnRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z`
- size: `226`
- prototype: `__int64 __fastcall(HINSTANCE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001490`

## callees

- `0x180001f88`
- `0x18000214c`
- `0x180007700`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800021a6`
- `KERNEL32!GetModuleHandleW` at `0x1800021a6`
- `KERNEL32!GetProcAddress` at `0x1800021bb`
- `KERNEL32!GetProcAddress` at `0x1800021bb`
- `OLEAUT32!__imp_SysFreeString` at `0x180002213`
- `OLEAUT32!__imp_SysFreeString` at `0x180002213`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x1800021c9`

## string_xrefs

- `0x18000219f`: `OLEAUT32.DLL`

## pseudocode

```c
__int64 __fastcall ATL::AtlUnRegisterTypeLib(HINSTANCE a1, const unsigned __int16 *a2)
{
  int v2; // ebx
  HMODULE ModuleHandleW; // rax
  void *ProcAddress; // r10
  __int64 v6; // [rsp+30h] [rbp-28h] BYREF
  struct ITypeLib *v7; // [rsp+38h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-18h] BYREF

  bstrString = 0;
  v7 = 0;
  v2 = ATL::AtlLoadTypeLib(a1, a2, &bstrString, &v7);
  if ( v2 >= 0 )
  {
    v2 = ((__int64 (__fastcall *)(struct ITypeLib *, __int64 *))v7->lpVtbl->GetLibAttr)(v7, &v6);
    if ( v2 >= 0 )
    {
      if ( !ATL::_AtlRegisterPerUser
        || (ModuleHandleW = GetModuleHandleW(L"OLEAUT32.DLL")) == 0
        || (ProcAddress = GetProcAddress(ModuleHandleW, "UnRegisterTypeLibForUser")) == 0 )
      {
        ProcAddress = UnRegisterTypeLib;
      }
      v2 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))ProcAddress)(
             v6,
             *(unsigned __int16 *)(v6 + 24),
             *(unsigned __int16 *)(v6 + 26),
             *(unsigned int *)(v6 + 16),
             *(_DWORD *)(v6 + 20));
      ((void (__fastcall *)(struct ITypeLib *, __int64))v7->lpVtbl->ReleaseTLibAttr)(v7, v6);
    }
  }
  if ( v7 )
    ((void (__fastcall *)(struct ITypeLib *))v7->lpVtbl->Release)(v7);
  SysFreeString(bstrString);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000214c  mov     r11, rsp
0x18000214f  push    rbx
0x180002150  sub     rsp, 50h
0x180002154  mov     rax, cs:__security_cookie
0x18000215b  xor     rax, rsp
0x18000215e  mov     [rsp+58h+var_10], rax
0x180002163  and     qword ptr [r11-18h], 0
0x180002168  lea     r9, [r11-20h]; struct ITypeLib **
0x18000216c  and     qword ptr [r11-20h], 0
0x180002171  lea     r8, [r11-18h]; unsigned __int16 **
0x180002175  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x18000217a  mov     ebx, eax
0x18000217c  test    eax, eax
0x18000217e  js      short loc_1800021FE
0x180002180  mov     rcx, [rsp+58h+var_20]
0x180002185  lea     rdx, [rsp+58h+var_28]
0x18000218a  mov     rax, [rcx]
0x18000218d  call    qword ptr [rax+38h]
0x180002190  mov     ebx, eax
0x180002192  test    eax, eax
0x180002194  js      short loc_1800021FE
0x180002196  cmp     cs:?_AtlRegisterPerUser@ATL@@3_NA, 1; bool ATL::_AtlRegisterPerUser
0x18000219d  jnz     short loc_1800021C9
0x18000219f  lea     rcx, ModuleName; "OLEAUT32.DLL"
0x1800021a6  call    cs:__imp_GetModuleHandleW
0x1800021ac  test    rax, rax
0x1800021af  jz      short loc_1800021C9
0x1800021b1  lea     rdx, aUnregistertype; "UnRegisterTypeLibForUser"
0x1800021b8  mov     rcx, rax; hModule
0x1800021bb  call    cs:__imp_GetProcAddress
0x1800021c1  mov     r10, rax
0x1800021c4  test    rax, rax
0x1800021c7  jnz     short loc_1800021D0
0x1800021c9  mov     r10, cs:__imp_UnRegisterTypeLib
0x1800021d0  mov     rcx, [rsp+58h+var_28]
0x1800021d5  mov     eax, [rcx+14h]
0x1800021d8  mov     r9d, [rcx+10h]
0x1800021dc  movzx   r8d, word ptr [rcx+1Ah]
0x1800021e1  movzx   edx, word ptr [rcx+18h]
0x1800021e5  mov     [rsp+58h+var_38], eax
0x1800021e9  call    r10
0x1800021ec  mov     rcx, [rsp+58h+var_20]
0x1800021f1  mov     ebx, eax
0x1800021f3  mov     rdx, [rsp+58h+var_28]
0x1800021f8  mov     rax, [rcx]
0x1800021fb  call    qword ptr [rax+60h]
0x1800021fe  mov     rcx, [rsp+58h+var_20]
0x180002203  test    rcx, rcx
0x180002206  jz      short loc_18000220E
0x180002208  mov     rax, [rcx]
0x18000220b  call    qword ptr [rax+10h]
0x18000220e  mov     rcx, [rsp+58h+bstrString]; bstrString
0x180002213  call    cs:__imp_SysFreeString
0x180002219  mov     eax, ebx
0x18000221b  mov     rcx, [rsp+58h+var_10]
0x180002220  xor     rcx, rsp; StackCookie
0x180002223  call    __security_check_cookie
0x180002228  add     rsp, 50h
0x18000222c  pop     rbx
0x18000222d  retn
```
