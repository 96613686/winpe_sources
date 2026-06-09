# ATL::CRegistryVirtualMachine::DeleteKeyWithReplacement(HKEY__ *,ulong,ATL::RGSStrings *)

- ea: `0x18000ddf8`
- end: `0x18000deb7`
- name: `?DeleteKeyWithReplacement@CRegistryVirtualMachine@ATL@@QEAAJPEAUHKEY__@@KPEAURGSStrings@2@@Z`
- size: `191`
- prototype: `__int64 __fastcall(ATL::CRegistryVirtualMachine *this, HKEY, int, struct ATL::RGSStrings *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012b04`

## callees

- `0x18000d790`
- `0x18000ddf8`
- `0x18000fa28`
- `0x180011ccc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000de9f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000de9f`

## pseudocode

```c
__int64 __fastcall ATL::CRegistryVirtualMachine::DeleteKeyWithReplacement(
        ATL::CRegistryVirtualMachine *this,
        HKEY a2,
        int a3,
        struct ATL::RGSStrings *a4)
{
  int StringAtLoc; // edi
  void *v6; // rcx
  wchar_t *v7; // rdx
  unsigned int v8; // eax
  wchar_t *v10; // [rsp+30h] [rbp-30h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v12[3]; // [rsp+48h] [rbp-18h] BYREF

  v12[1] = 0;
  v12[2] = 0;
  Block[0] = 0;
  Block[1] = 0;
  v10 = 0;
  StringAtLoc = ATL::CRegistryVirtualMachine::GetStringAtLoc(
                  (_DWORD)this,
                  (_DWORD)a4,
                  a3,
                  (unsigned int)Block,
                  (__int64)&v10);
  if ( StringAtLoc >= 0 )
  {
    v12[0] = a2;
    if ( a2 )
    {
      v7 = (wchar_t *)Block[0];
      if ( v10 )
        v7 = v10;
      v8 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v12, v7);
      if ( (v8 & 0xFFFFFFFC) != 0 || v8 == 1 )
        StringAtLoc = ATL::AtlHresultFromWin32(v8);
    }
    if ( Block[0] )
    {
      v6 = Block[0];
LABEL_12:
      free(v6);
    }
  }
  else
  {
    v6 = Block[0];
    if ( Block[0] )
      goto LABEL_12;
  }
  return (unsigned int)StringAtLoc;
}

```

## disassembly

```asm
0x18000ddf8  mov     [rsp-8+arg_0], rsi
0x18000ddfd  mov     [rsp-8+arg_8], rdi
0x18000de02  push    rbp
0x18000de03  mov     rbp, rsp
0x18000de06  sub     rsp, 60h
0x18000de0a  mov     rsi, rdx
0x18000de0d  mov     [rbp+var_10], 0
0x18000de15  mov     rax, r9
0x18000de18  mov     [rbp+var_8], 0
0x18000de20  lea     rdx, [rbp+var_30]
0x18000de24  mov     [rbp+Block], 0
0x18000de2c  mov     [rsp+60h+var_40], rdx
0x18000de31  lea     r9, [rbp+Block]
0x18000de35  mov     rdx, rax
0x18000de38  mov     [rbp+var_20], 0
0x18000de40  mov     [rbp+var_30], 0
0x18000de48  call    ?GetStringAtLoc@CRegistryVirtualMachine@ATL@@QEAAJPEAURGSStrings@2@KAEAV?$CSimpleArray@_WV?$CSimpleArrayEqualHelper@_W@ATL@@@2@PEAPEA_W@Z; ATL::CRegistryVirtualMachine::GetStringAtLoc(ATL::RGSStrings *,ulong,ATL::CSimpleArray<wchar_t,ATL::CSimpleArrayEqualHelper<wchar_t>> &,wchar_t * *)
0x18000de4d  mov     edi, eax
0x18000de4f  test    eax, eax
0x18000de51  jns     short loc_18000DE5E
0x18000de53  mov     rcx, [rbp+Block]
0x18000de57  test    rcx, rcx
0x18000de5a  jz      short loc_18000DEA5
0x18000de5c  jmp     short loc_18000DE9F
0x18000de5e  mov     [rbp+var_18], rsi
0x18000de62  test    rsi, rsi
0x18000de65  jz      short loc_18000DE94
0x18000de67  mov     rax, [rbp+var_30]
0x18000de6b  lea     rcx, [rbp+var_18]; this
0x18000de6f  mov     rdx, [rbp+Block]
0x18000de73  test    rax, rax
0x18000de76  cmovnz  rdx, rax; wchar_t *
0x18000de7a  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18000de7f  test    eax, 0FFFFFFFCh
0x18000de84  jnz     short loc_18000DE8B
0x18000de86  cmp     eax, 1
0x18000de89  jnz     short loc_18000DE94
0x18000de8b  mov     ecx, eax; unsigned int
0x18000de8d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000de92  mov     edi, eax
0x18000de94  cmp     [rbp+Block], 0
0x18000de99  jz      short loc_18000DEA5
0x18000de9b  mov     rcx, [rbp+Block]; Block
0x18000de9f  call    cs:__imp_free
0x18000dea5  mov     rsi, [rsp+60h+arg_0]
0x18000deaa  mov     eax, edi
0x18000deac  mov     rdi, [rsp+60h+arg_8]
0x18000deb1  add     rsp, 60h
0x18000deb5  pop     rbp
0x18000deb6  retn
```
