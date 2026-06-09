# BdeCfgpGetDiskAlignment(unsigned __int64,ulong *)

- ea: `0x180006104`
- end: `0x18000622b`
- name: `?BdeCfgpGetDiskAlignment@@YAJ_KPEAK@Z`
- size: `295`
- prototype: `LSTATUS __fastcall(unsigned __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180002f54`

## callees

- `0x180006104`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1800061f8`
- `ADVAPI32!RegGetValueW` at `0x1800061f8`
- `ADVAPI32!RegOpenKeyExW` at `0x180006164`
- `ADVAPI32!RegOpenKeyExW` at `0x180006164`

## string_xrefs

- `0x180006156`: `System\CurrentControlSet\Services\vds\Alignment\`

## pseudocode

```c
LSTATUS __fastcall BdeCfgpGetDiskAlignment(unsigned __int64 a1, unsigned int *a2)
{
  LSTATUS result; // eax
  bool v5; // cc
  const WCHAR *v6; // r8
  unsigned int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+68h] [rbp+20h] BYREF

  pvData = 0;
  hkey = 0;
  if ( !a1 || !a2 )
    return -2147024809;
  pcbData = 4;
  *a2 = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\vds\\Alignment\\",
             0,
             0x20019u,
             &hkey);
  v5 = result <= 0;
  if ( result )
    goto LABEL_4;
  if ( a1 >= 0x100000000LL )
  {
    if ( a1 >= 0x200000000LL )
    {
      v6 = L"Between8_32GB";
      if ( a1 >= 0x800000000LL )
        v6 = L"GreaterThan32GB";
    }
    else
    {
      v6 = L"Between4_8GB";
    }
  }
  else
  {
    v6 = L"LessThan4GB";
  }
  result = RegGetValueW(hkey, 0, v6, 0x10u, 0, &pvData, &pcbData);
  v5 = result <= 0;
  if ( result )
  {
LABEL_4:
    if ( !v5 )
      return (unsigned __int16)result | 0x80070000;
  }
  else if ( pvData )
  {
    result = 0;
    *a2 = pvData;
  }
  else
  {
    return -1063256037;
  }
  return result;
}

```

## disassembly

```asm
0x180006104  mov     rax, rsp
0x180006107  mov     [rax+10h], rbx
0x18000610b  push    rdi
0x18000610c  sub     rsp, 40h
0x180006110  mov     dword ptr [rax+8], 0
0x180006117  mov     rdi, rdx
0x18000611a  mov     qword ptr [rax+20h], 0
0x180006122  mov     rbx, rcx
0x180006125  test    rcx, rcx
0x180006128  jz      loc_18000621B
0x18000612e  test    rdx, rdx
0x180006131  jz      loc_18000621B
0x180006137  mov     dword ptr [rax+18h], 4
0x18000613e  lea     rax, [rax+20h]
0x180006142  mov     dword ptr [rdx], 0
0x180006148  mov     r9d, 20019h; samDesired
0x18000614e  xor     r8d, r8d; ulOptions
0x180006151  mov     [rsp+48h+phkResult], rax; phkResult
0x180006156  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\vd"...
0x18000615d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006164  call    cs:__imp_RegOpenKeyExW
0x18000616a  test    eax, eax
0x18000616c  jz      short loc_180006181
0x18000616e  jle     loc_180006220
0x180006174  movzx   eax, ax
0x180006177  or      eax, 80070000h
0x18000617c  jmp     loc_180006220
0x180006181  mov     rax, 100000000h
0x18000618b  cmp     rbx, rax
0x18000618e  jnb     short loc_180006199
0x180006190  lea     r8, aLessthan4gb; "LessThan4GB"
0x180006197  jmp     short loc_1800061D0
0x180006199  mov     rax, 200000000h
0x1800061a3  cmp     rbx, rax
0x1800061a6  jnb     short loc_1800061B1
0x1800061a8  lea     r8, aBetween48gb; "Between4_8GB"
0x1800061af  jmp     short loc_1800061D0
0x1800061b1  mov     rax, 800000000h
0x1800061bb  lea     r8, aBetween832gb; "Between8_32GB"
0x1800061c2  cmp     rbx, rax
0x1800061c5  lea     rcx, Value; "GreaterThan32GB"
0x1800061cc  cmovnb  r8, rcx; lpValue
0x1800061d0  mov     rcx, [rsp+48h+hkey]; hkey
0x1800061d5  lea     rax, [rsp+48h+arg_10]
0x1800061da  mov     [rsp+48h+pcbData], rax; pcbData
0x1800061df  xor     edx, edx; lpSubKey
0x1800061e1  lea     rax, [rsp+48h+arg_0]
0x1800061e6  mov     [rsp+48h+pvData], rax; pvData
0x1800061eb  mov     [rsp+48h+phkResult], 0; pdwType
0x1800061f4  lea     r9d, [rdx+10h]; dwFlags
0x1800061f8  call    cs:__imp_RegGetValueW
0x1800061fe  test    eax, eax
0x180006200  jnz     loc_18000616E
0x180006206  mov     ecx, [rsp+48h+arg_0]
0x18000620a  test    ecx, ecx
0x18000620c  jnz     short loc_180006215
0x18000620e  mov     eax, 0C0A0001Bh
0x180006213  jmp     short loc_180006220
0x180006215  xor     eax, eax
0x180006217  mov     [rdi], ecx
0x180006219  jmp     short loc_180006220
0x18000621b  mov     eax, 80070057h
0x180006220  mov     rbx, [rsp+48h+arg_8]
0x180006225  add     rsp, 40h
0x180006229  pop     rdi
0x18000622a  retn
```
