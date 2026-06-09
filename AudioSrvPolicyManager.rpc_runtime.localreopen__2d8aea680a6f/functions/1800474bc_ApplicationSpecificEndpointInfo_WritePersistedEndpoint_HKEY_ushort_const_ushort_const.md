# ApplicationSpecificEndpointInfo::WritePersistedEndpoint(HKEY__ *,ushort const *,ushort const *)

- ea: `0x1800474bc`
- end: `0x180047568`
- name: `?WritePersistedEndpoint@ApplicationSpecificEndpointInfo@@AEAAJPEAUHKEY__@@PEBG1@Z`
- size: `172`
- prototype: `__int64 __fastcall(ApplicationSpecificEndpointInfo *this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800463e8`
- `0x1800470a0`

## callees

- `0x18000a384`
- `0x180012844`
- `0x180023e98`
- `0x1800474bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047531`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047531`

## pseudocode

```c
__int64 __fastcall ApplicationSpecificEndpointInfo::WritePersistedEndpoint(
        ApplicationSpecificEndpointInfo *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v6; // eax
  const BYTE *v7; // r11
  unsigned int v8; // ebx
  unsigned int v10; // eax
  int lpData; // [rsp+20h] [rbp-18h]
  unsigned int lpDataa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned __int64 cbData; // [rsp+40h] [rbp+8h] BYREF

  cbData = 0;
  v6 = StringCbLengthW(a4, 0x104u, &cbData);
  v8 = v6;
  if ( v6 >= 0 )
  {
    v10 = RegSetValueExW(a2, a3, 0, 1u, v7, cbData);
    if ( v10 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x354,
               (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
               (const char *)v10,
               lpDataa);
    else
      return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x350,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
      (const char *)(unsigned int)v6,
      lpData);
    return v8;
  }
}

```

## disassembly

```asm
0x1800474bc  mov     rax, rsp
0x1800474bf  mov     [rax+10h], rbx
0x1800474c3  mov     [rax+18h], rsi
0x1800474c7  mov     [rax+8], rcx
0x1800474cb  push    rdi
0x1800474cc  sub     rsp, 30h
0x1800474d0  mov     rsi, rdx
0x1800474d3  mov     qword ptr [rax+8], 0
0x1800474db  mov     rdi, r8
0x1800474de  mov     edx, 104h; unsigned __int64
0x1800474e3  lea     r8, [rax+8]; unsigned __int64 *
0x1800474e7  mov     rcx, r9; unsigned __int16 *
0x1800474ea  mov     r11, r9
0x1800474ed  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800474f2  mov     ebx, eax
0x1800474f4  test    eax, eax
0x1800474f6  jns     short loc_180047515
0x1800474f8  mov     rcx, [rsp+38h]; this
0x1800474fd  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x180047504  mov     r9d, eax; char *
0x180047507  mov     edx, 350h; void *
0x18004750c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047511  mov     eax, ebx
0x180047513  jmp     short loc_180047558
0x180047515  mov     eax, dword ptr [rsp+38h+arg_0]
0x180047519  mov     r9d, 1; dwType
0x18004751f  mov     [rsp+38h+cbData], eax; cbData
0x180047523  xor     r8d, r8d; Reserved
0x180047526  mov     rdx, rdi; lpValueName
0x180047529  mov     [rsp+38h+lpData], r11; unsigned int
0x18004752e  mov     rcx, rsi; hKey
0x180047531  call    cs:__imp_RegSetValueExW
0x180047537  test    eax, eax
0x180047539  jz      short loc_180047556
0x18004753b  mov     rcx, [rsp+38h]; this
0x180047540  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x180047547  mov     r9d, eax; char *
0x18004754a  mov     edx, 354h; void *
0x18004754f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180047554  jmp     short loc_180047558
0x180047556  xor     eax, eax
0x180047558  mov     rbx, [rsp+38h+arg_8]
0x18004755d  mov     rsi, [rsp+38h+arg_10]
0x180047562  add     rsp, 30h
0x180047566  pop     rdi
0x180047567  retn
```
